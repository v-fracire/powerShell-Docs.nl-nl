---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: Een DSC web pull-server instellen
ms.openlocfilehash: 03d4d148c87854b146091aa0e8d815b8c35def72
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2017
---
# <a name="setting-up-a-dsc-web-pull-server"></a><span data-ttu-id="183ad-103">Een DSC web pull-server instellen</span><span class="sxs-lookup"><span data-stu-id="183ad-103">Setting up a DSC web pull server</span></span>

> <span data-ttu-id="183ad-104">Van toepassing op: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="183ad-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="183ad-105">Een pull-server van de DSC-webservice is een webservice in IIS die gebruikmaakt van een OData-interface om DSC-configuratiebestanden te doelknooppunten wanneer die knooppunten van deze vragen.</span><span class="sxs-lookup"><span data-stu-id="183ad-105">A DSC web pull server is a web service in IIS that uses an OData interface to make DSC configuration files available to target nodes when those nodes ask for them.</span></span>

<span data-ttu-id="183ad-106">Vereisten voor het gebruik van een pull-server:</span><span class="sxs-lookup"><span data-stu-id="183ad-106">Requirements for using a pull server:</span></span>

* <span data-ttu-id="183ad-107">Een server met:</span><span class="sxs-lookup"><span data-stu-id="183ad-107">A server running:</span></span>
  - <span data-ttu-id="183ad-108">WMF/PowerShell 5.0 of hoger</span><span class="sxs-lookup"><span data-stu-id="183ad-108">WMF/PowerShell 5.0 or greater</span></span>
  - <span data-ttu-id="183ad-109">IIS-serverrol</span><span class="sxs-lookup"><span data-stu-id="183ad-109">IIS server role</span></span>
  - <span data-ttu-id="183ad-110">DSC-Service</span><span class="sxs-lookup"><span data-stu-id="183ad-110">DSC Service</span></span>
* <span data-ttu-id="183ad-111">In het ideale geval sommige betekent dat voor het genereren van een certificaat voor het beveiligen van referenties die zijn doorgegeven aan de lokale Configuration Manager (LCM) op de doelknooppunten</span><span class="sxs-lookup"><span data-stu-id="183ad-111">Ideally, some means of generating a certificate, to secure credentials passed to the Local Configuration Manager (LCM) on target nodes</span></span>

<span data-ttu-id="183ad-112">U kunt de IIS-serverrol en DSC-Service toevoegen met de wizard functies en onderdelen toevoegen in Serverbeheer of met behulp van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="183ad-112">You can add the IIS server role and DSC Service with the Add Roles and Features wizard in Server Manager, or by using PowerShell.</span></span> <span data-ttu-id="183ad-113">De voorbeeldscripts opgenomen in dit onderwerp wordt afgehandeld beide stappen u ook.</span><span class="sxs-lookup"><span data-stu-id="183ad-113">The sample scripts included in this topic will handle both of these steps for you as well.</span></span>

## <a name="using-the-xdscwebservice-resource"></a><span data-ttu-id="183ad-114">Met behulp van de resource xDSCWebService</span><span class="sxs-lookup"><span data-stu-id="183ad-114">Using the xDSCWebService resource</span></span>
<span data-ttu-id="183ad-115">De eenvoudigste manier voor het instellen van een pull-webserver is met de resource xWebService, opgenomen in de module xPSDesiredStateConfiguration.</span><span class="sxs-lookup"><span data-stu-id="183ad-115">The easiest way to set up a web pull server is to use the xWebService resource, included in the xPSDesiredStateConfiguration module.</span></span> <span data-ttu-id="183ad-116">De volgende stappen wordt uitgelegd hoe u de bron in een configuratie die de webservice heeft ingesteld.</span><span class="sxs-lookup"><span data-stu-id="183ad-116">The following steps explain how to use the resource in a configuration that sets up the web service.</span></span>

1. <span data-ttu-id="183ad-117">Roep de [Install-Module](https://technet.microsoft.com/en-us/library/dn807162.aspx) cmdlet voor het installeren van de **xPSDesiredStateConfiguration** module.</span><span class="sxs-lookup"><span data-stu-id="183ad-117">Call the [Install-Module](https://technet.microsoft.com/en-us/library/dn807162.aspx) cmdlet to install the **xPSDesiredStateConfiguration** module.</span></span> <span data-ttu-id="183ad-118">**Opmerking**: **Install-Module** is opgenomen in de **PowerShellGet** module die is opgenomen in PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="183ad-118">**Note**: **Install-Module** is included in the **PowerShellGet** module, which is included in PowerShell 5.0.</span></span> <span data-ttu-id="183ad-119">U kunt downloaden via de **PowerShellGet** -module voor PowerShell 3.0 en 4.0 op [PackageManagement PowerShell-Modules Preview](https://www.microsoft.com/en-us/download/details.aspx?id=49186).</span><span class="sxs-lookup"><span data-stu-id="183ad-119">You can download the **PowerShellGet** module for PowerShell 3.0 and 4.0 at [PackageManagement PowerShell Modules Preview](https://www.microsoft.com/en-us/download/details.aspx?id=49186).</span></span> 
1. <span data-ttu-id="183ad-120">Een SSL-certificaat ophalen voor de DSC-Pull-server via een vertrouwde certificeringsinstantie zich binnen uw organisatie of een openbare CA.</span><span class="sxs-lookup"><span data-stu-id="183ad-120">Get an SSL certificate for the DSC Pull server from a trusted Certificate Authority, either within your organization or a public authority.</span></span> <span data-ttu-id="183ad-121">Het certificaat dat is ontvangen van de instantie is meestal de PFX-indeling.</span><span class="sxs-lookup"><span data-stu-id="183ad-121">The certificate received from the authority is usually in the PFX format.</span></span> <span data-ttu-id="183ad-122">Installeer het certificaat op het knooppunt dat de DSC-Pull-server op de standaardlocatie CERT: \LocalMachine\My moet worden.</span><span class="sxs-lookup"><span data-stu-id="183ad-122">Install the certificate on the node that will become the DSC Pull server in the default location which should be CERT:\LocalMachine\My.</span></span> <span data-ttu-id="183ad-123">Noteer de certificaatvingerafdruk van het.</span><span class="sxs-lookup"><span data-stu-id="183ad-123">Make a note of the certificate thumbprint.</span></span>
1. <span data-ttu-id="183ad-124">Selecteer een GUID moet worden gebruikt als de registratiesleutel.</span><span class="sxs-lookup"><span data-stu-id="183ad-124">Select a GUID to be used as the Registration Key.</span></span> <span data-ttu-id="183ad-125">Voor het genereren van een met behulp van PowerShell, typ het volgende achter de PS-prompt en druk op enter: '``` [guid]::newGuid()```'of'```New-Guid```'.</span><span class="sxs-lookup"><span data-stu-id="183ad-125">To generate one using PowerShell enter the following at the PS prompt and press enter: '``` [guid]::newGuid()```' or '```New-Guid```'.</span></span> <span data-ttu-id="183ad-126">Deze sleutel wordt door de knooppunten van de client worden gebruikt als een gedeelde sleutel om te verifiëren tijdens de registratie.</span><span class="sxs-lookup"><span data-stu-id="183ad-126">This key will be used by client nodes as a shared key to authenticate during registration.</span></span> <span data-ttu-id="183ad-127">Zie de sectie registratiesleutel hieronder voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="183ad-127">For more information see the Registration Key section below.</span></span>
1. <span data-ttu-id="183ad-128">Start in de PowerShell ISE (F5) het volgende configuratiescript (opgenomen in de map voorbeeld van de **xPSDesiredStateConfiguration** module als Sample_xDscWebService.ps1).</span><span class="sxs-lookup"><span data-stu-id="183ad-128">In the PowerShell ISE, start (F5) the following configuration script (included in the Example folder of the  **xPSDesiredStateConfiguration** module as Sample_xDscWebService.ps1).</span></span> <span data-ttu-id="183ad-129">Dit script is ingesteld van de pull-server.</span><span class="sxs-lookup"><span data-stu-id="183ad-129">This script sets up the pull server.</span></span>
  
    ```powershell
    configuration Sample_xDscPullServer
    { 
        param  
        ( 
                [string[]]$NodeName = 'localhost', 

                [ValidateNotNullOrEmpty()] 
                [string] $certificateThumbPrint,

                [Parameter(Mandatory)]
                [ValidateNotNullOrEmpty()]
                [string] $RegistrationKey 
         ) 
         
         Import-DSCResource -ModuleName xPSDesiredStateConfiguration
         Import-DSCResource –ModuleName PSDesiredStateConfiguration

         Node $NodeName 
         { 
             WindowsFeature DSCServiceFeature 
             { 
                 Ensure = 'Present'
                 Name   = 'DSC-Service'             
             } 

             xDscWebService PSDSCPullServer 
             { 
                 Ensure                   = 'Present' 
                 EndpointName             = 'PSDSCPullServer' 
                 Port                     = 8080 
                 PhysicalPath             = "$env:SystemDrive\inetpub\PSDSCPullServer" 
                 CertificateThumbPrint    = $certificateThumbPrint          
                 ModulePath               = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules" 
                 ConfigurationPath        = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration" 
                 State                    = 'Started'
                 DependsOn                = '[WindowsFeature]DSCServiceFeature'     
                 UseSecurityBestPractices = $false
             } 

            File RegistrationKeyFile
            {
                Ensure          = 'Present'
                Type            = 'File'
                DestinationPath = "$env:ProgramFiles\WindowsPowerShell\DscService\RegistrationKeys.txt"
                Contents        = $RegistrationKey
            }
        }
    }

    ```

1. <span data-ttu-id="183ad-130">Voer de configuratie, voor het doorgeven van de vingerafdruk van het SSL-certificaat als de **certificateThumbPrint** parameter en de registratie van een GUID sleutel als de **RegistrationKey** parameter:</span><span class="sxs-lookup"><span data-stu-id="183ad-130">Run the configuration, passing the thumbprint of the SSL certificate as the **certificateThumbPrint** parameter and a GUID registration key as the **RegistrationKey** parameter:</span></span>

    ```powershell
    # To find the Thumbprint for an installed SSL certificate for use with the pull server list all certificates in your local store 
    # and then copy the thumbprint for the appropriate certificate by reviewing the certificate subjects
    dir Cert:\LocalMachine\my

    # Then include this thumbprint when running the configuration
    Sample_xDSCPullServer -certificateThumbprint 'A7000024B753FA6FFF88E966FD6E19301FAE9CCC' -RegistrationKey '140a952b-b9d6-406b-b416-e0f759c9c0e4' -OutputPath c:\Configs\PullServer

    # Run the compiled configuration to make the target node a DSC Pull Server
    Start-DscConfiguration -Path c:\Configs\PullServer -Wait -Verbose
    ```

## <a name="registration-key"></a><span data-ttu-id="183ad-131">Registratiesleutel</span><span class="sxs-lookup"><span data-stu-id="183ad-131">Registration Key</span></span>
<span data-ttu-id="183ad-132">Als u wilt toestaan client knooppunten om te registreren bij de server, zodat ze configuratienamen in plaats van een configuratie-ID gebruiken kunnen, een registratiesleutel die is gemaakt door de bovenstaande configuratie wordt opgeslagen in een bestand met de naam `RegistrationKeys.txt` in `C:\Program Files\WindowsPowerShell\DscService`.</span><span class="sxs-lookup"><span data-stu-id="183ad-132">To allow client nodes to register with the server so that they can use configuration names instead of a configuration ID, a registration key which was created by the above configuration is saved in a file named `RegistrationKeys.txt` in `C:\Program Files\WindowsPowerShell\DscService`.</span></span> <span data-ttu-id="183ad-133">De registratiesleutel fungeert als een gedeeld geheim gebruikt tijdens de initiële registratie door de client met de pull-server.</span><span class="sxs-lookup"><span data-stu-id="183ad-133">The registration key functions as a shared secret used during the initial registration by the client with the pull server.</span></span> <span data-ttu-id="183ad-134">De client genereert een zelfondertekend certificaat dat is gebruikt voor een unieke verificatie naar de pull-server wanneer de registratie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="183ad-134">The client will generate a self-signed certificate which is used to uniquely authenticate to the pull server once registration is successfully completed.</span></span> <span data-ttu-id="183ad-135">De vingerafdruk van dit certificaat wordt lokaal opgeslagen en die zijn gekoppeld aan de URL van de pull-server.</span><span class="sxs-lookup"><span data-stu-id="183ad-135">The thumbprint of this certificate is stored locally and associated with the URL of the pull server.</span></span>
> <span data-ttu-id="183ad-136">**Opmerking**: registratiesleutels worden niet ondersteund in PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="183ad-136">**Note**: Registration keys are not supported in PowerShell 4.0.</span></span> 

<span data-ttu-id="183ad-137">Om te configureren van een knooppunt om te verifiëren met de pull-server van de registratie van de moet sleutel in de metaconfiguratie voor elk doelknooppunt die zal worden geregistreerd met deze pull-server.</span><span class="sxs-lookup"><span data-stu-id="183ad-137">In order to configure a node to authenticate with the pull server the registration key needs to be in the metaconfiguration for any target node that will be registering with this pull server.</span></span> <span data-ttu-id="183ad-138">Houd er rekening mee dat de **RegistrationKey** in de onderstaande metaconfiguratie wordt verwijderd nadat de doelmachine heeft geregistreerd en de waarde '140a952b-b9d6-406b-b416-e0f759c9c0e4' moet overeenkomen met de waarde die is opgeslagen in de RegistrationKeys.txt-bestand op de pull-server.</span><span class="sxs-lookup"><span data-stu-id="183ad-138">Note that the **RegistrationKey** in the metaconfiguration below is removed after the target machine has successfully registered, and that the value '140a952b-b9d6-406b-b416-e0f759c9c0e4' must match the value stored in the RegistrationKeys.txt file on the pull server.</span></span> <span data-ttu-id="183ad-139">Altijd worden beschouwd door de waarde van de registratie-sleutel veilig, omdat elke doelcomputer registreren bij de pull-server geïnstalleerd is toegestaan.</span><span class="sxs-lookup"><span data-stu-id="183ad-139">Always treat the registration key value securely, because knowing it allows any target machine to register with the pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode          = 'Pull'
            RefreshFrequencyMins = 30 
            RebootNodeIfNeeded   = $true
        }
        
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL          = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey    = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('ClientConfig')
        }   
        
        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL       = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
        }
    }
}

PullClientConfigID -OutputPath c:\Configs\TargetNodes
```
> <span data-ttu-id="183ad-140">**Opmerking**: de **ReportServerWeb** sectie kan worden verzonden naar de pull-server melden.</span><span class="sxs-lookup"><span data-stu-id="183ad-140">**Note**: The **ReportServerWeb** section allows reporting data to be sent to the pull server.</span></span> 

<span data-ttu-id="183ad-141">Het ontbreken van de **ConfigurationID** eigenschap in het bestand metaconfiguratie impliciet betekent dat pull-server ondersteunt de V2-versie van het protocol voor pull-server zodat een initiële registratie is vereist.</span><span class="sxs-lookup"><span data-stu-id="183ad-141">The lack of the **ConfigurationID** property in the metaconfiguration file implicitly means that pull server is supporting the V2 version of the pull server protocol so an initial registration is required.</span></span> <span data-ttu-id="183ad-142">Als u daarentegen de aanwezigheid van een **ConfigurationID** betekent dat de V1-versie van het pull-protocol wordt gebruikt en er geen registratie-verwerking is.</span><span class="sxs-lookup"><span data-stu-id="183ad-142">Conversely, the presence of a **ConfigurationID** means that the V1 version of the pull server protocol is used and there is no registration processing.</span></span>

><span data-ttu-id="183ad-143">**Opmerking**: In een PUSH-scenario is een fout bestaat in de huidige officieel uitgegeven die het nodig zijn voor het definiëren van een eigenschap ConfigurationID in het bestand metaconfiguratie voor knooppunten die nooit zijn geregistreerd bij een pull-server maakt.</span><span class="sxs-lookup"><span data-stu-id="183ad-143">**Note**: In a PUSH scenario, a bug exists in the current relase that makes it necessary to define a ConfigurationID property in the metaconfiguration file for nodes that have never registered with a pull server.</span></span> <span data-ttu-id="183ad-144">Hiermee wordt het protocol V1-Pull-Server dwingen en registratie foutberichten voorkomen.</span><span class="sxs-lookup"><span data-stu-id="183ad-144">This will force the V1 Pull Server protocol and avoid registration failure messages.</span></span>

## <a name="placing-configurations-and-resources"></a><span data-ttu-id="183ad-145">Configuraties en resources plaatsen</span><span class="sxs-lookup"><span data-stu-id="183ad-145">Placing configurations and resources</span></span>

<span data-ttu-id="183ad-146">Nadat de pull server setup is voltooid, de mappen die zijn gedefinieerd door de **ConfigurationPath** en **ModulePath** eigenschappen in de configuratie van de pull-server zijn waar u modules en configuraties worden geplaatst die beschikbaar zal zijn voor de doelknooppunten om op te halen.</span><span class="sxs-lookup"><span data-stu-id="183ad-146">After the pull server setup completes, the folders defined by the **ConfigurationPath** and **ModulePath** properties in the pull server configuration are where you will place modules and configurations that will be available for target nodes to pull.</span></span> <span data-ttu-id="183ad-147">Deze bestanden moeten in een specifieke indeling om de pull-server ze correct te verwerken.</span><span class="sxs-lookup"><span data-stu-id="183ad-147">These files need to be in a specific format in order for the pull server to correctly process them.</span></span> 

### <a name="dsc-resource-module-package-format"></a><span data-ttu-id="183ad-148">DSC-resource module pakket-indeling</span><span class="sxs-lookup"><span data-stu-id="183ad-148">DSC resource module package format</span></span>

<span data-ttu-id="183ad-149">Elke resource module moet worden ingepakt en met de naam op basis van het volgende patroon volgen `{Module Name}_{Module Version}.zip`.</span><span class="sxs-lookup"><span data-stu-id="183ad-149">Each resource module needs to be zipped and named according the following pattern `{Module Name}_{Module Version}.zip`.</span></span> <span data-ttu-id="183ad-150">Bijvoorbeeld, een module met de naam xWebAdminstration met een moduleversie van 3.1.2.0 de naam 'xWebAdministration_3.2.1.0.zip'.</span><span class="sxs-lookup"><span data-stu-id="183ad-150">For example, a module named xWebAdminstration with a module version of 3.1.2.0 would be named 'xWebAdministration_3.2.1.0.zip'.</span></span> <span data-ttu-id="183ad-151">Elke versie van een module moet worden opgenomen in een enkel zip-bestand.</span><span class="sxs-lookup"><span data-stu-id="183ad-151">Each version of a module must be contained in a single zip file.</span></span> <span data-ttu-id="183ad-152">Omdat er slechts één versie van een resource in elke zip-bestand in WMF 5.0 met de indeling van de module hebt toegevoegd wordt ondersteuning voor meerdere moduleversies van de in een enkele map wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="183ad-152">Since there is only a single version of a resource in each zip file the module format added in WMF 5.0 with support for multiple module versions in a single directory is not supported.</span></span> <span data-ttu-id="183ad-153">Dit betekent dat voordat verpakking van DSC-resource-modules voor gebruik met pull-server u moet een kleine wijziging aanbrengen in de mapstructuur.</span><span class="sxs-lookup"><span data-stu-id="183ad-153">This means that before packaging up DSC resource modules for use with pull server you will need to make a small change to the directory structure.</span></span> <span data-ttu-id="183ad-154">De standaardindeling van modules met van DSC-resource in WMF 5.0 is ' {Modulemap}\{moduleversie} \DscResources\{DSC-Resourcemap}\'.</span><span class="sxs-lookup"><span data-stu-id="183ad-154">The default format of modules containing DSC resource in WMF 5.0 is '{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\'.</span></span> <span data-ttu-id="183ad-155">Pakketten voor de pull-server te verwijderen en daarna de **{moduleversie}** map zodat het pad ' {Modulemap} \DscResources\{DSC-Resourcemap}\'.</span><span class="sxs-lookup"><span data-stu-id="183ad-155">Before packaging up for the pull server simply remove the **{Module version}** folder so the path becomes '{Module Folder}\DscResources\{DSC Resource Folder}\'.</span></span> <span data-ttu-id="183ad-156">Zip de map met deze wijziging, zoals hierboven wordt beschreven op en plaats deze zip-bestanden in de **ModulePath** map.</span><span class="sxs-lookup"><span data-stu-id="183ad-156">With this change, zip the folder as described above and place these zip files in the **ModulePath** folder.</span></span>

<span data-ttu-id="183ad-157">Gebruik `new-dscchecksum {module zip file}` een controlesom-bestand voor de toegevoegde module te maken.</span><span class="sxs-lookup"><span data-stu-id="183ad-157">Use `new-dscchecksum {module zip file}` to create a checksum file for the newly-added module.</span></span>

### <a name="configuration-mof-format"></a><span data-ttu-id="183ad-158">Configuratie MOF-indeling</span><span class="sxs-lookup"><span data-stu-id="183ad-158">Configuration MOF format</span></span> 
<span data-ttu-id="183ad-159">Een configuratie MOF-bestand moet worden gekoppeld aan een bestand controlesom zodat een LCM in een doelknooppunt kunt de configuratie valideren.</span><span class="sxs-lookup"><span data-stu-id="183ad-159">A configuration MOF file needs to be paired with a checksum file so that an LCM on a target node can validate the configuration.</span></span> <span data-ttu-id="183ad-160">Aanroepen voor het maken van een controlesom, de [nieuw DSCCheckSum](https://technet.microsoft.com/en-us/library/dn521622.aspx) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="183ad-160">To create a checksum, call the [New-DSCCheckSum](https://technet.microsoft.com/en-us/library/dn521622.aspx) cmdlet.</span></span> <span data-ttu-id="183ad-161">De cmdlet heeft een **pad** parameter waarmee de map waarin de configuratie van de MOF zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="183ad-161">The cmdlet takes a **Path** parameter that specifies the folder where the configuration MOF is located.</span></span> <span data-ttu-id="183ad-162">De cmdlet maakt een controlesom-bestand met de naam `ConfigurationMOFName.mof.checksum`, waarbij `ConfigurationMOFName` is de naam van het mof-bestand voor configuratie.</span><span class="sxs-lookup"><span data-stu-id="183ad-162">The cmdlet creates a checksum file named `ConfigurationMOFName.mof.checksum`, where `ConfigurationMOFName` is the name of the configuration mof file.</span></span> <span data-ttu-id="183ad-163">Als er meer dan één configuratie MOF-bestanden in de opgegeven map, wordt een controlesom gemaakt voor elke configuratie in de map.</span><span class="sxs-lookup"><span data-stu-id="183ad-163">If there are more than one configuration MOF files in the specified folder, a checksum is created for each configuration in the folder.</span></span> <span data-ttu-id="183ad-164">Plaats de MOF-bestanden en hun bijbehorende controlesom-bestanden in de de **ConfigurationPath** map.</span><span class="sxs-lookup"><span data-stu-id="183ad-164">Place the MOF files and their associated checksum files in the the **ConfigurationPath** folder.</span></span>

><span data-ttu-id="183ad-165">**Opmerking**: als u het MOF-bestand van de configuratie op een manier wijzigt, moet u ook het bestand controlesom opnieuw.</span><span class="sxs-lookup"><span data-stu-id="183ad-165">**Note**: If you change the configuration MOF file in any way, you must also recreate the checksum file.</span></span>

## <a name="tooling"></a><span data-ttu-id="183ad-166">Tooling</span><span class="sxs-lookup"><span data-stu-id="183ad-166">Tooling</span></span>
<span data-ttu-id="183ad-167">Om de instelling gezamenlijk valideren en het beheren van de eenvoudiger, pull-server de volgende hulpprogramma's zijn opgenomen als voorbeelden in de meest recente versie van de module xPSDesiredStateConfiguration:</span><span class="sxs-lookup"><span data-stu-id="183ad-167">In order to make setting up, validating and managing the pull server easier, the following tools are included as examples in the latest version of the xPSDesiredStateConfiguration module:</span></span>
1. <span data-ttu-id="183ad-168">Een module die u helpt met het verpakken van DSC-resource-modules en de configuratiebestanden voor gebruik op de pull-server.</span><span class="sxs-lookup"><span data-stu-id="183ad-168">A module that will help with packaging DSC resource modules and configuration files for use on the pull server.</span></span> <span data-ttu-id="183ad-169">[PublishModulesAndMofsToPullServer.psm1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PublishModulesAndMofsToPullServer.psm1).</span><span class="sxs-lookup"><span data-stu-id="183ad-169">[PublishModulesAndMofsToPullServer.psm1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PublishModulesAndMofsToPullServer.psm1).</span></span> <span data-ttu-id="183ad-170">De volgende voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="183ad-170">Examples below:</span></span>

    ```powershell
        # Example 1 - Package all versions of given modules installed locally and MOF files are in c:\LocalDepot
         $moduleList = @("xWebAdministration", "xPhp") 
         Publish-DSCModuleAndMof -Source C:\LocalDepot -ModuleNameList $moduleList 

         # Example 2 - Package modules and mof documents from c:\LocalDepot
         Publish-DSCModuleAndMof -Source C:\LocalDepot -Force
    ```

1. <span data-ttu-id="183ad-171">Een script dat de pull-server valideert is correct geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="183ad-171">A script that validates the pull server is configured correctly.</span></span> <span data-ttu-id="183ad-172">[PullServerSetupTests.ps1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PullServerDeploymentVerificationTest/PullServerSetupTests.ps1).</span><span class="sxs-lookup"><span data-stu-id="183ad-172">[PullServerSetupTests.ps1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PullServerDeploymentVerificationTest/PullServerSetupTests.ps1).</span></span>


## <a name="pull-client-configuration"></a><span data-ttu-id="183ad-173">Pull-clientconfiguratie</span><span class="sxs-lookup"><span data-stu-id="183ad-173">Pull client configuration</span></span> 
<span data-ttu-id="183ad-174">De volgende onderwerpen wordt instellen van de pull-clients in detail beschreven:</span><span class="sxs-lookup"><span data-stu-id="183ad-174">The following topics describe setting up pull clients in detail:</span></span>

* [<span data-ttu-id="183ad-175">Instellen van een DSC-pull-client met behulp van een configuratie-ID</span><span class="sxs-lookup"><span data-stu-id="183ad-175">Setting up a DSC pull client using a configuration ID</span></span>](pullClientConfigID.md)
* [<span data-ttu-id="183ad-176">Instellen van een DSC-pull-client met behulp van configuratienamen</span><span class="sxs-lookup"><span data-stu-id="183ad-176">Setting up a DSC pull client using configuration names</span></span>](pullClientConfigNames.md)
* [<span data-ttu-id="183ad-177">Gedeeltelijke configuraties</span><span class="sxs-lookup"><span data-stu-id="183ad-177">Partial configurations</span></span>](partialConfigs.md)


## <a name="see-also"></a><span data-ttu-id="183ad-178">Zie ook</span><span class="sxs-lookup"><span data-stu-id="183ad-178">See also</span></span>
* [<span data-ttu-id="183ad-179">Windows PowerShell Desired State Configuration-overzicht</span><span class="sxs-lookup"><span data-stu-id="183ad-179">Windows PowerShell Desired State Configuration Overview</span></span>](overview.md)
* [<span data-ttu-id="183ad-180">Configuraties vast te stellen</span><span class="sxs-lookup"><span data-stu-id="183ad-180">Enacting configurations</span></span>](enactingConfigurations.md)
* [<span data-ttu-id="183ad-181">Met behulp van een DSC-rapportserver</span><span class="sxs-lookup"><span data-stu-id="183ad-181">Using a DSC report server</span></span>](reportServer.md)
