---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: Gebruik van DSC op Nano Server
ms.openlocfilehash: 2233106bfd07144132f95ea7957ebfa3248ca219
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="using-dsc-on-nano-server"></a><span data-ttu-id="3cf22-103">Gebruik van DSC op Nano Server</span><span class="sxs-lookup"><span data-stu-id="3cf22-103">Using DSC on Nano Server</span></span>

> <span data-ttu-id="3cf22-104">Van toepassing op: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3cf22-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="3cf22-105">**DSC op Nano Server** is een optioneel pakket in de `NanoServer\Packages` map van de Windows Server 2016-media.</span><span class="sxs-lookup"><span data-stu-id="3cf22-105">**DSC on Nano Server** is an optional package in the `NanoServer\Packages` folder of the Windows Server 2016 media.</span></span> <span data-ttu-id="3cf22-106">Het pakket kan worden geïnstalleerd wanneer u een VHD voor een Nano Server door op te geven maken **Microsoft-NanoServer-DSC-Package** als de waarde van de **pakketten** parameter van de **nieuw NanoServerImage**  functie.</span><span class="sxs-lookup"><span data-stu-id="3cf22-106">The package can be installed when you create a VHD for a Nano Server by specifying **Microsoft-NanoServer-DSC-Package** as the value of the **Packages** parameter of the **New-NanoServerImage** function.</span></span> <span data-ttu-id="3cf22-107">Als u een VHD voor een virtuele machine maakt, wordt door de opdracht er als volgt:</span><span class="sxs-lookup"><span data-stu-id="3cf22-107">For example, if you are creating a VHD for a virtual machine, the command would look like the following:</span></span>

```powershell
New-NanoServerImage -Edition Standard -DeploymentType Guest -MediaPath f:\ -BasePath .\Base -TargetPath .\Nano1\Nano.vhd -ComputerName Nano1 -Packages Microsoft-NanoServer-DSC-Package
```

<span data-ttu-id="3cf22-108">Zie voor meer informatie over het installeren en gebruiken van Nano Server, evenals de Nano Server met PowerShell op afstand beheren [aan de slag met Nano Server](https://technet.microsoft.com/en-us/library/mt126167.aspx).</span><span class="sxs-lookup"><span data-stu-id="3cf22-108">For information about installing and using Nano Server, as well as how to manage Nano Server with PowerShell Remoting, see [Getting Started with Nano Server](https://technet.microsoft.com/en-us/library/mt126167.aspx).</span></span>


## <a name="dsc-features-available-on-nano-server"></a><span data-ttu-id="3cf22-109">DSC-functies die beschikbaar zijn op Nano Server</span><span class="sxs-lookup"><span data-stu-id="3cf22-109">DSC features available on Nano Server</span></span>

 <span data-ttu-id="3cf22-110">Omdat Nano Server alleen een beperkte set van vergeleken met een volledige versie van Windows Server-API's ondersteunt, heeft DSC op Nano Server geen volledig functionele pariteit met DSC op volledige SKU's voor de tijd die wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3cf22-110">Because Nano Server supports only a limited set of APIs compared to a full version of Windows Server, DSC on Nano Server does not have full functional parity with DSC running on full SKUs for the time being.</span></span> <span data-ttu-id="3cf22-111">DSC op Nano Server is in de actieve ontwikkeling en is nog niet voltooid functie.</span><span class="sxs-lookup"><span data-stu-id="3cf22-111">DSC on Nano Server is in active development and is not yet feature complete.</span></span>
 
 <span data-ttu-id="3cf22-112">De volgende DSC-functies zijn momenteel beschikbaar op Nano Server:</span><span class="sxs-lookup"><span data-stu-id="3cf22-112">The following DSC features are currently available on Nano Server:</span></span> 


* <span data-ttu-id="3cf22-113">Zowel push als pull-modi</span><span class="sxs-lookup"><span data-stu-id="3cf22-113">Both push and pull modes</span></span>

* <span data-ttu-id="3cf22-114">Alle DSC-cmdlets die bestaan op een volledige versie van Windows Server, waaronder het volgende:</span><span class="sxs-lookup"><span data-stu-id="3cf22-114">All DSC cmdlets that exist on a full version of Windows Server, including the following:</span></span> 
  * [<span data-ttu-id="3cf22-115">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="3cf22-115">Get-DscLocalConfigurationManager</span></span>](https://technet.microsoft.com/en-us/library/dn407378.aspx)
  * [<span data-ttu-id="3cf22-116">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="3cf22-116">Set-DscLocalConfigurationManager</span></span>](https://technet.microsoft.com/en-us/library/dn521621.aspx)   
  * [<span data-ttu-id="3cf22-117">Schakel DscDebug</span><span class="sxs-lookup"><span data-stu-id="3cf22-117">Enable-DscDebug</span></span>](https://technet.microsoft.com/en-us/library/mt517870.aspx)
  * [<span data-ttu-id="3cf22-118">Schakel DscDebug</span><span class="sxs-lookup"><span data-stu-id="3cf22-118">Disable-DscDebug</span></span>](https://technet.microsoft.com/en-us/library/mt517872.aspx)       
  * [<span data-ttu-id="3cf22-119">Start DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cf22-119">Start-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/dn521623.aspx)
  * [<span data-ttu-id="3cf22-120">Stop DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cf22-120">Stop-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/mt143542.aspx)
  * [<span data-ttu-id="3cf22-121">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cf22-121">Get-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/dn407379.aspx)
  * [<span data-ttu-id="3cf22-122">Test DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cf22-122">Test-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/dn407382.aspx)      
  * [<span data-ttu-id="3cf22-123">Publiceren DscConfiguraiton</span><span class="sxs-lookup"><span data-stu-id="3cf22-123">Publish-DscConfiguraiton</span></span>](https://technet.microsoft.com/en-us/library/mt517875.aspx) 
  * [<span data-ttu-id="3cf22-124">Update DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cf22-124">Update-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/mt143541.aspx)
  * [<span data-ttu-id="3cf22-125">Restore DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cf22-125">Restore-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/dn407383.aspx)
  * [<span data-ttu-id="3cf22-126">Verwijder DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="3cf22-126">Remove-DscConfigurationDocument</span></span>](https://technet.microsoft.com/en-us/library/mt143544.aspx)
  * [<span data-ttu-id="3cf22-127">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="3cf22-127">Get-DscConfigurationStatus</span></span>](https://technet.microsoft.com/en-us/library/mt517868.aspx)
  * [<span data-ttu-id="3cf22-128">Aanroepen DscResource</span><span class="sxs-lookup"><span data-stu-id="3cf22-128">Invoke-DscResource</span></span>](https://technet.microsoft.com/en-us/library/mt517869.aspx)
  * [<span data-ttu-id="3cf22-129">Zoeken naar DscResource</span><span class="sxs-lookup"><span data-stu-id="3cf22-129">Find-DscResource</span></span>](https://technet.microsoft.com/en-us/library/mt517874.aspx)
  * [<span data-ttu-id="3cf22-130">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="3cf22-130">Get-DscResource</span></span>](https://technet.microsoft.com/en-us/library/dn521625.aspx)
  * [<span data-ttu-id="3cf22-131">Nieuwe DscChecksum</span><span class="sxs-lookup"><span data-stu-id="3cf22-131">New-DscChecksum</span></span>](https://technet.microsoft.com/en-us/library/dn521622.aspx)    

* <span data-ttu-id="3cf22-132">Compileren van configuraties (Zie [DSC-configuraties](configurations.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-132">Compiling configurations (see [DSC configurations](configurations.md))</span></span>

  <span data-ttu-id="3cf22-133">**Probleem:** wachtwoordversleuteling (Zie [beveiligen van het MOF-bestand](securemof.md)) tijdens het configureren van de compilatie niet werkt.</span><span class="sxs-lookup"><span data-stu-id="3cf22-133">**Issue:** Password encryption (see [Securing the MOF File](securemof.md)) during configuration compilation doesn't work.</span></span>

* <span data-ttu-id="3cf22-134">Metaconfigurations compileren (Zie [configureren van de lokale Configuration Manager](metaConfig.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-134">Compiling metaconfigurations (see [Configuring the Local Configuration Manager](metaConfig.md))</span></span>

* <span data-ttu-id="3cf22-135">Een bron op onder de gebruikerscontext wordt uitgevoerd (Zie [DSC uitgevoerd met de referenties van gebruiker (RunAs)](runAsUser.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-135">Running a resource under user context (see [Running DSC with user credentials (RunAs)](runAsUser.md))</span></span>

* <span data-ttu-id="3cf22-136">Klasse-bronnen (Zie [schrijven van een aangepaste DSC-resource met PowerShell klassen](authoringResourceClass.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-136">Class-based resources (see [Writing a custom DSC resource with PowerShell classes](authoringResourceClass.md))</span></span>

* <span data-ttu-id="3cf22-137">Foutopsporing van DSC-resources (Zie [foutopsporing DSC-resources](debugresource.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-137">Debugging of DSC resources (see [Debugging DSC resources](debugresource.md))</span></span>
  
  <span data-ttu-id="3cf22-138">**Probleem:** werkt niet als een resource maakt gebruik van PsDscRunAsCredential (Zie [DSC uitgevoerd met gebruikersreferenties](runAsUser.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-138">**Issue:** Doesn't work if a resource is using PsDscRunAsCredential (see [Running DSC with user credentials](runAsUser.md))</span></span>

* [<span data-ttu-id="3cf22-139">Cross-knooppunt afhankelijkheden opgeven</span><span class="sxs-lookup"><span data-stu-id="3cf22-139">Specifying cross-node dependencies</span></span>](crossNodeDependencies.md) 

* [<span data-ttu-id="3cf22-140">Resource-versies</span><span class="sxs-lookup"><span data-stu-id="3cf22-140">Resource versioning</span></span>](sxsResource.md)

* <span data-ttu-id="3cf22-141">Pull-client (configuraties en resources) (Zie [instellen van een pull-client met behulp van configuratienamen](pullClientConfigNames.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-141">Pull client (configurations & resources) (see [Setting up a pull client using configuration names](pullClientConfigNames.md))</span></span>

* [<span data-ttu-id="3cf22-142">Gedeeltelijke configuraties (pull & push)</span><span class="sxs-lookup"><span data-stu-id="3cf22-142">Partial configurations (pull & push)</span></span>](partialConfigs.md)

* [<span data-ttu-id="3cf22-143">Melden van pull-server</span><span class="sxs-lookup"><span data-stu-id="3cf22-143">Reporting to pull server</span></span>](reportServer.md) 

* <span data-ttu-id="3cf22-144">MOF-versleuteling</span><span class="sxs-lookup"><span data-stu-id="3cf22-144">MOF encryption</span></span>

* <span data-ttu-id="3cf22-145">Logboekregistratie van gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="3cf22-145">Event logging</span></span>

* <span data-ttu-id="3cf22-146">Rapportage van Azure Automation DSC</span><span class="sxs-lookup"><span data-stu-id="3cf22-146">Azure Automation DSC reporting</span></span>

* <span data-ttu-id="3cf22-147">Resources die volledig functioneel zijn</span><span class="sxs-lookup"><span data-stu-id="3cf22-147">Resources that are fully functional</span></span>
  * [<span data-ttu-id="3cf22-148">Archief</span><span class="sxs-lookup"><span data-stu-id="3cf22-148">Archive</span></span>](archiveResource.md)
  * [<span data-ttu-id="3cf22-149">Omgeving</span><span class="sxs-lookup"><span data-stu-id="3cf22-149">Environment</span></span>](environmentResource.md)
  * [<span data-ttu-id="3cf22-150">Bestand</span><span class="sxs-lookup"><span data-stu-id="3cf22-150">File</span></span>](fileResource.md)
  * [<span data-ttu-id="3cf22-151">Logboek</span><span class="sxs-lookup"><span data-stu-id="3cf22-151">Log</span></span>](logResource.md)
  * <span data-ttu-id="3cf22-152">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="3cf22-152">ProcessSet</span></span>
  * [<span data-ttu-id="3cf22-153">Register</span><span class="sxs-lookup"><span data-stu-id="3cf22-153">Registry</span></span>](registryResource.md)
  * [<span data-ttu-id="3cf22-154">Script</span><span class="sxs-lookup"><span data-stu-id="3cf22-154">Script</span></span>](scriptResource.md)
  * <span data-ttu-id="3cf22-155">WindowsPackageCab</span><span class="sxs-lookup"><span data-stu-id="3cf22-155">WindowsPackageCab</span></span>
  * [<span data-ttu-id="3cf22-156">WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="3cf22-156">WindowsProcess</span></span>](windowsProcessResource.md)
  * <span data-ttu-id="3cf22-157">WaitForAll (Zie [geven cross-knooppunt afhankelijkheden](crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-157">WaitForAll (see [Specifying cross-node dependencies](crossNodeDependencies.md))</span></span>
  * <span data-ttu-id="3cf22-158">WaitForAny (Zie [geven cross-knooppunt afhankelijkheden](crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-158">WaitForAny (see [Specifying cross-node dependencies](crossNodeDependencies.md))</span></span>
  * <span data-ttu-id="3cf22-159">WaitForSome (Zie [geven cross-knooppunt afhankelijkheden](crossNodeDependencies.md))</span><span class="sxs-lookup"><span data-stu-id="3cf22-159">WaitForSome (see [Specifying cross-node dependencies](crossNodeDependencies.md))</span></span>

* <span data-ttu-id="3cf22-160">Resources die gedeeltelijk functioneel zijn</span><span class="sxs-lookup"><span data-stu-id="3cf22-160">Resources that are partially functional</span></span>
  * [<span data-ttu-id="3cf22-161">Groep</span><span class="sxs-lookup"><span data-stu-id="3cf22-161">Group</span></span>](groupResource.md)
  * <span data-ttu-id="3cf22-162">GroupSet</span><span class="sxs-lookup"><span data-stu-id="3cf22-162">GroupSet</span></span>
  
  <span data-ttu-id="3cf22-163">**Probleem:** hierboven resources mislukken als specifieke exemplaar tweemaal wordt genoemd (met dezelfde configuratie tweemaal)</span><span class="sxs-lookup"><span data-stu-id="3cf22-163">**Issue:** Above resources fail if specific instance is called twice (running the same configuration twice)</span></span>
  
  * [<span data-ttu-id="3cf22-164">Service</span><span class="sxs-lookup"><span data-stu-id="3cf22-164">Service</span></span>](serviceResource.md)
  * <span data-ttu-id="3cf22-165">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="3cf22-165">ServiceSet</span></span>
  
  <span data-ttu-id="3cf22-166">**Probleem:** werkt alleen voor (status)-service starten/stoppen.</span><span class="sxs-lookup"><span data-stu-id="3cf22-166">**Issue:** Only works for starting/stopping (status) service.</span></span> <span data-ttu-id="3cf22-167">Mislukt, als een probeert te wijzigen van andere service-kenmerken zoals startuptype, referenties, beschrijving, enzovoort...</span><span class="sxs-lookup"><span data-stu-id="3cf22-167">Fails, if one tries to change other service attributes like startuptype, credentials, description etc..</span></span> <span data-ttu-id="3cf22-168">De opgetreden fout is vergelijkbaar met:</span><span class="sxs-lookup"><span data-stu-id="3cf22-168">The error thrown is similar to:</span></span>
  
  <span data-ttu-id="3cf22-169">*Kan type [management.managementobject] niet vinden: Controleer of de assembly met dit type is geladen.*</span><span class="sxs-lookup"><span data-stu-id="3cf22-169">*Cannot find type [management.managementobject]: verify that the assembly containing this type is loaded.*</span></span>
  
* <span data-ttu-id="3cf22-170">Resources die geen functionele</span><span class="sxs-lookup"><span data-stu-id="3cf22-170">Resources that are not functional</span></span>
  * [<span data-ttu-id="3cf22-171">Gebruiker</span><span class="sxs-lookup"><span data-stu-id="3cf22-171">User</span></span>](userResource.md)
  

## <a name="dsc-features-not-available-on-nano-server"></a><span data-ttu-id="3cf22-172">DSC-functies niet beschikbaar op Nano Server</span><span class="sxs-lookup"><span data-stu-id="3cf22-172">DSC features not available on Nano Server</span></span>

<span data-ttu-id="3cf22-173">De volgende DSC-functies zijn momenteel niet beschikbaar op Nano Server:</span><span class="sxs-lookup"><span data-stu-id="3cf22-173">The following DSC features are not currently available on Nano Server:</span></span>

* <span data-ttu-id="3cf22-174">Ontsleutelen van MOF-document met versleutelde wachtwoord(en)</span><span class="sxs-lookup"><span data-stu-id="3cf22-174">Decrypting MOF document with encrypted password(s)</span></span> 
* <span data-ttu-id="3cf22-175">Pull-Server kan niet op dit moment instellen van een pull-server op Nano Server</span><span class="sxs-lookup"><span data-stu-id="3cf22-175">Pull Server--you cannot currently set up a pull server on Nano Server</span></span>
* <span data-ttu-id="3cf22-176">Iets dat zich niet in de lijst met de functie werkt</span><span class="sxs-lookup"><span data-stu-id="3cf22-176">Anything that is not in the list of feature works</span></span>

## <a name="using-custom-dsc-resources-on-nano-server"></a><span data-ttu-id="3cf22-177">Met behulp van aangepaste DSC-resources op Nano Server</span><span class="sxs-lookup"><span data-stu-id="3cf22-177">Using custom DSC resources on Nano Server</span></span>
 
<span data-ttu-id="3cf22-178">Als gevolg van een beperkte sets van Windows-API's en CLR-bibliotheken die beschikbaar is op Nano Server werken DSC-resources die op de volledige CLR-versie van Windows werken mogelijk niet op Nano Server.</span><span class="sxs-lookup"><span data-stu-id="3cf22-178">Due to a limited sets of Windows APIs and CLR libraries available on Nano Server, DSC resources that work on the full CLR version of Windows do not necessarily work on Nano Server.</span></span> <span data-ttu-id="3cf22-179">Volledige end-to-end testen voordat u een aangepaste DSC-resources in een productieomgeving implementeert.</span><span class="sxs-lookup"><span data-stu-id="3cf22-179">Complete end-to-end testing before deploying any DSC custom resources to a production environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cf22-180">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3cf22-180">See Also</span></span>
- [<span data-ttu-id="3cf22-181">Aan de slag met Nano Server</span><span class="sxs-lookup"><span data-stu-id="3cf22-181">Getting Started with Nano Server</span></span>](https://technet.microsoft.com/en-us/library/mt126167.aspx)
