---
ms.date: 06/12/2017
keywords: DSC, powershell, configuratie en installatie
title: Referentieopties in de configuratiegegevens
ms.openlocfilehash: a1ecccfd0560903fa8c1cec9a4d57e7217be7f6c
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403986"
---
# <a name="credentials-options-in-configuration-data"></a><span data-ttu-id="b9a0a-103">Referentieopties in de configuratiegegevens</span><span class="sxs-lookup"><span data-stu-id="b9a0a-103">Credentials Options in Configuration Data</span></span>
><span data-ttu-id="b9a0a-104">Van toepassing op: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b9a0a-104">Applies To: Windows PowerShell 5.0</span></span>

## <a name="plain-text-passwords-and-domain-users"></a><span data-ttu-id="b9a0a-105">Tekst zonder opmaak wachtwoorden en domeingebruikers</span><span class="sxs-lookup"><span data-stu-id="b9a0a-105">Plain Text Passwords and Domain Users</span></span>

<span data-ttu-id="b9a0a-106">DSC-configuraties met een referentie zonder versleuteling wordt een foutbericht over ongecodeerde wachtwoorden worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-106">DSC configurations containing a credential without encryption will generate an error message about plain text passwords.</span></span>
<span data-ttu-id="b9a0a-107">DSC wordt ook een waarschuwing gegenereerd wanneer met domeinreferenties.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-107">Also, DSC will generate a warning when using domain credentials.</span></span>
<span data-ttu-id="b9a0a-108">Gebruik de trefwoorden DSC-configuratie gegevens als u wilt onderdrukken deze fout- en waarschuwingsberichten:</span><span class="sxs-lookup"><span data-stu-id="b9a0a-108">To suppress these error and warning messages use the DSC configuration data keywords:</span></span>
* <span data-ttu-id="b9a0a-109">**PsDscAllowPlainTextPassword**</span><span class="sxs-lookup"><span data-stu-id="b9a0a-109">**PsDscAllowPlainTextPassword**</span></span>
* <span data-ttu-id="b9a0a-110">**PsDscAllowDomainUser**</span><span class="sxs-lookup"><span data-stu-id="b9a0a-110">**PsDscAllowDomainUser**</span></span>

> [!NOTE]
> <span data-ttu-id="b9a0a-111">Opslag/verzending van niet-versleutelde wachtwoorden in platte tekst is in het algemeen niet beveiligd.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-111">Storing/transmitting plaintext passwords unencrypted is generally not secure.</span></span> <span data-ttu-id="b9a0a-112">Referenties beveiligen met behulp van de technieken die verderop in dit onderwerp aan bod wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-112">Securing credentials by using the techniques covered later in this topic is recommended.</span></span>
> <span data-ttu-id="b9a0a-113">De service Azure Automation DSC kunt u om referenties op om te worden gecompileerd in configuraties en veilig opgeslagen centraal te beheren.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-113">The Azure Automation DSC service allows you to centrally manage credentials to be compiled in configurations and stored securely.</span></span>
> <span data-ttu-id="b9a0a-114">Zie voor informatie: [DSC-configuraties compileren / Referentieassets](/azure/automation/automation-dsc-compile#credential-assets)</span><span class="sxs-lookup"><span data-stu-id="b9a0a-114">For information, see: [Compiling DSC Configurations / Credential Assets](/azure/automation/automation-dsc-compile#credential-assets)</span></span>

<span data-ttu-id="b9a0a-115">Hier volgt een voorbeeld van het doorgeven van referenties met tekst zonder opmaak:</span><span class="sxs-lookup"><span data-stu-id="b9a0a-115">The following is an example of passing plain text credentials:</span></span>

```powershell
#Prompt user for their credentials
#credentials will be unencrypted in the MOF
$promptedCreds = get-credential -Message "Please enter your credentials to generate a DSC MOF:"

# Store passwords in plaintext, in the document itself
# will also be stored in plaintext in the mof
$password = "ThisIsAPlaintextPassword" | ConvertTo-SecureString -asPlainText -Force
$username = "User1"
[PSCredential] $credential = New-Object System.Management.Automation.PSCredential($username,$password)

# DSC requires explicit confirmation before storing passwords insecurely
$ConfigurationData = @{
    AllNodes = @(
        @{
            # The "*" means "all nodes named in ConfigData" so we don't have to repeat ourselves
            NodeName="*"
            PSDscAllowPlainTextPassword = $true
        },
        #however, each node still needs to be explicitly defined for "*" to have meaning
        @{
            NodeName = "TestMachine1"
        },
        #we can also use a property to define node-specific passwords, although this is no more secure
        @{
            NodeName = "TestMachine2";
            UserName = "User2"
            LocalPassword = "ThisIsYetAnotherPlaintextPassword"
        }
        )
}
configuration unencryptedPasswordDemo
{
    Node "TestMachine1"
    {
        # We use the plaintext password to generate a new account
        User User1
        {
            UserName = $username
            Password = $credential
            Description = "local account"
            Ensure = "Present"
            Disabled = $false
            PasswordNeverExpires = $true
            PasswordChangeRequired = $false
        }
        # We use the prompted password to add this account to the local admins group
        Group addToAdmin
        {
            # Ensure the user exists before we add the user to a group
            DependsOn = "[User]User1"
            Credential = $promptedCreds
            GroupName = "Administrators"
            Ensure = "Present"
            MembersToInclude = "User1"
        }
    }

    Node "TestMachine2"
    {
        # Now we'll use a node-specific password to this machine
        $password = $Node.LocalPassword | ConvertTo-SecureString -asPlainText -Force
        $username = $node.UserName
        [PSCredential] $nodeCred = New-Object System.Management.Automation.PSCredential($username,$password)

        User User2
        {
            UserName = $username
            Password = $nodeCred
            Description = "local account"
            Ensure = "Present"
            Disabled = $false
            PasswordNeverExpires = $true
            PasswordChangeRequired = $false
        }

        Group addToAdmin
        {
            Credential = $promptedCreds
            GroupName = "Administrators"
            DependsOn = "[User]User2"
            Ensure = "Present"
            MembersToInclude = "User2"
        }
    }

}
# We declared the ConfigurationData in a local variable, but we need to pass it in to our configuration function
# We need to invoke the configuration function we created to generate a MOF
unencryptedPasswordDemo -ConfigurationData $ConfigurationData
# We need to pass the MOF to the machines we named.
#-wait: doesn't use jobs so we get blocked at the prompt until the configuration is done
#-verbose: so we can see what's going on and catch any errors
#-force: for testing purposes, I run start-dscconfiguration frequently + want to make sure i'm
#        not blocked by previous configurations that are still running
Start-DscConfiguration ./unencryptedPasswordDemo -verbose -wait -force
```

## <a name="handling-credentials-in-dsc"></a><span data-ttu-id="b9a0a-116">Verwerken van de referenties in DSC</span><span class="sxs-lookup"><span data-stu-id="b9a0a-116">Handling Credentials in DSC</span></span>

<span data-ttu-id="b9a0a-117">DSC-configuratieresources run as- `Local System` standaard.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-117">DSC configuration resources run as `Local System` by default.</span></span>
<span data-ttu-id="b9a0a-118">Sommige resources moeten echter een referentie, bijvoorbeeld wanneer de `Package` resource nodig heeft voor het installeren van software die onder een bepaalde gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-118">However, some resources need a credential, for example when the `Package` resource needs to install software under a specific user account.</span></span>

<span data-ttu-id="b9a0a-119">Eerder gebruikte vastgelegde `Credential` eigenschapsnaam voor het afhandelen van dit.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-119">Earlier resources used a hard-coded `Credential` property name to handle this.</span></span>
<span data-ttu-id="b9a0a-120">WMF 5.0 toegevoegd automatisch `PsDscRunAsCredential` eigenschap voor alle resources.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-120">WMF 5.0 added an automatic `PsDscRunAsCredential` property for all resources.</span></span>
<span data-ttu-id="b9a0a-121">Voor informatie over het gebruik van `PsDscRunAsCredential`, Zie [DSC uitvoeren met gebruikersreferenties](runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="b9a0a-121">For information about using `PsDscRunAsCredential`, see [Running DSC with user credentials](runAsUser.md).</span></span>
<span data-ttu-id="b9a0a-122">Nieuwere resources en aangepaste resources kunnen u deze automatische eigenschap gebruiken in plaats van het maken van hun eigen eigenschap voor referenties.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-122">Newer resources and custom resources can use this automatic property instead of creating their own property for credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="b9a0a-123">Het ontwerp van sommige resources zijn meerdere referenties gebruiken om een bepaalde reden en hebben ze hun eigen referentie-eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-123">The design of some resources are to use multiple credentials for a specific reason, and they will have their own credential properties.</span></span>

<span data-ttu-id="b9a0a-124">Eigenschappen van een resource gebruiken op de beschikbare referentie niet vinden een `Get-DscResource -Name ResourceName -Syntax` of de Intellisense in de ISE (`CTRL+SPACE`).</span><span class="sxs-lookup"><span data-stu-id="b9a0a-124">To find the available credential properties on a resource use either `Get-DscResource -Name ResourceName -Syntax` or the Intellisense in the ISE (`CTRL+SPACE`).</span></span>

```powershell
PS C:\> Get-DscResource -Name Group -Syntax
Group [String] #ResourceName
{
    GroupName = [string]
    [Credential = [PSCredential]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Members = [string[]]]
    [MembersToExclude = [string[]]]
    [MembersToInclude = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

<span data-ttu-id="b9a0a-125">In dit voorbeeld wordt een [groep](../resources/resources.md) -resource in de `PSDesiredStateConfiguration` ingebouwde DSC-resource-module.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-125">This example uses a [Group](../resources/resources.md) resource from the `PSDesiredStateConfiguration` built-in DSC resource module.</span></span>
<span data-ttu-id="b9a0a-126">Het kan maken van lokale groepen en leden toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-126">It can create local groups and add or remove members.</span></span>
<span data-ttu-id="b9a0a-127">Accepteert zowel de `Credential` eigenschap en de automatische `PsDscRunAsCredential` eigenschap.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-127">It accepts both the `Credential` property and the automatic `PsDscRunAsCredential` property.</span></span>
<span data-ttu-id="b9a0a-128">Echter, de resource maakt alleen gebruik van de `Credential` eigenschap.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-128">However, the resource only uses the `Credential` property.</span></span>

<span data-ttu-id="b9a0a-129">Voor meer informatie over de `PsDscRunAsCredential` eigenschap, Zie [DSC uitvoeren met gebruikersreferenties](runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="b9a0a-129">For more information about the `PsDscRunAsCredential` property, see [Running DSC with user credentials](runAsUser.md).</span></span>

## <a name="example-the-group-resource-credential-property"></a><span data-ttu-id="b9a0a-130">Voorbeeld: De bron van gebruikersgroep referentie-eigenschap</span><span class="sxs-lookup"><span data-stu-id="b9a0a-130">Example: The Group resource Credential property</span></span>

<span data-ttu-id="b9a0a-131">DSC wordt uitgevoerd onder `Local System`, zodat deze heeft al machtigingen om lokale gebruikers en groepen te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-131">DSC runs under `Local System`, so it already has permissions to change local users and groups.</span></span>
<span data-ttu-id="b9a0a-132">Als het lid toegevoegd een lokaal account is, zijn er is geen referentie is nodig.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-132">If the member added is a local account, then no credential is necessary.</span></span>
<span data-ttu-id="b9a0a-133">Als de `Group` resource wordt een domeinaccount toegevoegd aan de lokale groep en vervolgens een referentie nodig is.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-133">If the `Group` resource adds a domain account to the local group, then a credential is necessary.</span></span>

<span data-ttu-id="b9a0a-134">Anonieme query's naar Active Directory zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-134">Anonymous queries to Active Directory are not allowed.</span></span>
<span data-ttu-id="b9a0a-135">De `Credential` eigenschap van de `Group` resource is het domeinaccount dat wordt gebruikt om te zoeken in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-135">The `Credential` property of the `Group` resource is the domain account used to query Active Directory.</span></span>
<span data-ttu-id="b9a0a-136">Voor de meeste doeleinden mogelijk een algemeen gebruikersaccount, standaard kunnen gebruikers *lezen* meeste van de objecten in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-136">For most purposes this could be a generic user account, because by default users can *read* most of the objects in Active Directory.</span></span>

## <a name="example-configuration"></a><span data-ttu-id="b9a0a-137">Voorbeeld van een configuratie</span><span class="sxs-lookup"><span data-stu-id="b9a0a-137">Example Configuration</span></span>

<span data-ttu-id="b9a0a-138">De volgende voorbeeldcode maakt gebruik van DSC voor het vullen van een lokale groep met een domeingebruiker:</span><span class="sxs-lookup"><span data-stu-id="b9a0a-138">The following example code uses DSC to populate a local group with a domain user:</span></span>

```powershell
Configuration DomainCredentialExample
{
    param
    (
        [PSCredential] $DomainCredential
    )
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $DomainCredential
        }
    }
}

$cred = Get-Credential -UserName contoso\genericuser -Message "Password please"
DomainCredentialExample -DomainCredential $cred
```

<span data-ttu-id="b9a0a-139">Deze code genereert een fout en de waarschuwing weergegeven:</span><span class="sxs-lookup"><span data-stu-id="b9a0a-139">This code generates both an error and warning message:</span></span>

```
ConvertTo-MOFInstance : System.InvalidOperationException error processing
property 'Credential' OF TYPE 'Group': Converting and storing encrypted
passwords as plain text is not recommended. For more information on securing
credentials in MOF file, please refer to MSDN blog:
http://go.microsoft.com/fwlink/?LinkId=393729

At line:11 char:9
+   Group
At line:297 char:16
+     $aliasId = ConvertTo-MOFInstance $keywordName $canonicalizedValue
+                ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Write-Error], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessProperty,ConvertTo-MOFInstance

WARNING: It is not recommended to use domain credential for node 'localhost'.
In order to suppress the warning, you can add a property named
'PSDscAllowDomainUser' with a value of $true to your DSC configuration data
for node 'localhost'.
```

<span data-ttu-id="b9a0a-140">In dit voorbeeld heeft twee problemen:</span><span class="sxs-lookup"><span data-stu-id="b9a0a-140">This example has two issues:</span></span>
1. <span data-ttu-id="b9a0a-141">Een fout wordt uitgelegd dat ongecodeerde wachtwoorden worden niet aanbevolen</span><span class="sxs-lookup"><span data-stu-id="b9a0a-141">An error explains that plain text passwords are not recommended</span></span>
2. <span data-ttu-id="b9a0a-142">Een waarschuwing wordt beschermd tegen het gebruik van een domeinreferentie</span><span class="sxs-lookup"><span data-stu-id="b9a0a-142">A warning advises against using a domain credential</span></span>

## <a name="psdscallowplaintextpassword"></a><span data-ttu-id="b9a0a-143">PsDscAllowPlainTextPassword</span><span class="sxs-lookup"><span data-stu-id="b9a0a-143">PsDscAllowPlainTextPassword</span></span>

<span data-ttu-id="b9a0a-144">Het eerste foutbericht heeft een URL met de documentatie.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-144">The first error message has a URL with documentation.</span></span>
<span data-ttu-id="b9a0a-145">Deze koppeling wordt uitgelegd hoe u voor het versleutelen van wachtwoorden met een [ConfigurationData](./configData.md) structuur en een certificaat.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-145">This link explains how to encrypt passwords using a [ConfigurationData](./configData.md) structure and a certificate.</span></span>
<span data-ttu-id="b9a0a-146">Voor meer informatie over certificaten en DSC [leest u dit bericht](http://aka.ms/certs4dsc).</span><span class="sxs-lookup"><span data-stu-id="b9a0a-146">For more information on certificates and DSC [read this post](http://aka.ms/certs4dsc).</span></span>

<span data-ttu-id="b9a0a-147">Als u wilt afdwingen dat een wachtwoord als tekst zonder opmaak, de resource vereist de `PsDscAllowPlainTextPassword` sleutelwoord in de configuratiegegevens sectie als volgt:</span><span class="sxs-lookup"><span data-stu-id="b9a0a-147">To force a plain text password, the resource requires the `PsDscAllowPlainTextPassword` keyword in the configuration data section as follows:</span></span>

```powershell
Configuration DomainCredentialExample
{
    param
    (
        [PSCredential] $DomainCredential
    )
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $DomainCredential
        }
    }
}

$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowPlainTextPassword = $true
        }
    )
}

$cred = Get-Credential -UserName contoso\genericuser -Message "Password please"
DomainCredentialExample -DomainCredential $cred -ConfigurationData $cd
```

> [!NOTE]
> <span data-ttu-id="b9a0a-148">`NodeName` kan niet gelijk zijn aan sterretje, de naam van een specifiek knooppunt is verplicht.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-148">`NodeName` cannot equal asterisk, a specific node name is mandatory.</span></span>

<span data-ttu-id="b9a0a-149">**Microsoft adviseert om te voorkomen dat ongecodeerde wachtwoorden vanwege de aanzienlijke beveiligingsrisico's.**</span><span class="sxs-lookup"><span data-stu-id="b9a0a-149">**Microsoft advises to avoid plain text passwords due to the significant security risk.**</span></span>

## <a name="domain-credentials"></a><span data-ttu-id="b9a0a-150">Domeinreferenties</span><span class="sxs-lookup"><span data-stu-id="b9a0a-150">Domain Credentials</span></span>

<span data-ttu-id="b9a0a-151">Het voorbeeld van de configuratie-script opnieuw is uitgevoerd (met of zonder versleuteling), nog steeds worden gegenereerd voor de waarschuwing die met behulp van een domein-account voor een referentie wordt niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-151">Running the example configuration script again (with or without encryption), still generates the warning that using a domain account for a credential is not recommended.</span></span>
<span data-ttu-id="b9a0a-152">Met behulp van een lokaal account wordt voorkomen dat potentiële blootstelling van domeinreferenties die kan worden gebruikt op andere servers.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-152">Using a local account eliminates potential exposure of domain credentials that could be used on other servers.</span></span>

<span data-ttu-id="b9a0a-153">**Als u referenties voor DSC-resources, moet u een lokaal account liever via een domeinaccount, indien mogelijk.**</span><span class="sxs-lookup"><span data-stu-id="b9a0a-153">**When using credentials with DSC resources, prefer a local account over a domain account when possible.**</span></span>

<span data-ttu-id="b9a0a-154">Als er een '\' of '\@' in de `Username` eigenschap van de referentie en vervolgens de DSC zal worden beschouwd als een domeinaccount.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-154">If there is a '\' or '@' in the `Username` property of the credential, then DSC will treat it as a domain account.</span></span>
<span data-ttu-id="b9a0a-155">Er is een uitzondering voor 'localhost', '127.0.0.1' en ':: 1" in het domeingedeelte van de naam van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-155">There is an exception for "localhost", "127.0.0.1", and "::1" in the domain portion of the user name.</span></span>

## <a name="psdscallowdomainuser"></a><span data-ttu-id="b9a0a-156">PSDscAllowDomainUser</span><span class="sxs-lookup"><span data-stu-id="b9a0a-156">PSDscAllowDomainUser</span></span>

<span data-ttu-id="b9a0a-157">In de DSC `Group` resourcevoorbeeld hierboven, uitvoeren van query's een Active Directory-domein *vereist* een domeinaccount.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-157">In the DSC `Group` resource example above, querying an Active Directory domain *requires* a domain account.</span></span>
<span data-ttu-id="b9a0a-158">In dit geval voegen de `PSDscAllowDomainUser` eigenschap in op de `ConfigurationData` blokkeren als volgt:</span><span class="sxs-lookup"><span data-stu-id="b9a0a-158">In this case add the `PSDscAllowDomainUser` property to the `ConfigurationData` block as follows:</span></span>

```powershell
$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowDomainUser = $true
            # PSDscAllowPlainTextPassword = $true
            CertificateFile = "C:\PublicKeys\server1.cer"
        }
    )
}
```

<span data-ttu-id="b9a0a-159">Het configuratiescript wordt nu het MOF-bestand met geen fouten of waarschuwingen hebben gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="b9a0a-159">Now the configuration script will generate the MOF file with no errors or warnings.</span></span>