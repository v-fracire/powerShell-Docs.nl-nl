---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: Galerie, powershell, cmdlet, psget
title: modulewithpseditionsupport
ms.openlocfilehash: 8122756b78e18fe55daef5c46dc299b87ddcaf1a
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="modules-with-compatible-powershell-editions"></a><span data-ttu-id="67583-103">Modules met compatibel PowerShell-edities</span><span class="sxs-lookup"><span data-stu-id="67583-103">Modules with compatible PowerShell Editions</span></span>
<span data-ttu-id="67583-104">Vanaf versie 5.1 is PowerShell beschikbaar in verschillende edities die staan voor verschillende functies en platformcompatibiliteit.</span><span class="sxs-lookup"><span data-stu-id="67583-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="67583-105">**Desktop-editie:** deze editie is gebaseerd op .NET Framework en biedt compatibiliteit met scripts en modules die zijn gericht op versies van PowerShell die worden uitgevoerd op edities van Windows met een volledige footprint zoals Server Core en Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="67583-105">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="67583-106">**Core-editie:** deze editie is gebaseerd op .NET Framework en biedt compatibiliteit met scripts en modules die zijn gericht op versies van PowerShell die worden uitgevoerd op edities van Windows met een verminderde footprint zoals Nano Server en Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="67583-106">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

## <a name="the-running-edition-of-powershell-is-shown-in-the-psedition-property-of-psversiontable"></a><span data-ttu-id="67583-107">De actieve editie van PowerShell wordt weergegeven in de eigenschap PSEdition van $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="67583-107">The running edition of PowerShell is shown in the PSEdition property of $PSVersionTable.</span></span>
```powershell
$PSVersionTable

Name                           Value
----                           -----
PSVersion                      5.1.14300.1000
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
CLRVersion                     4.0.30319.42000
BuildVersion                   10.0.14300.1000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

## <a name="module-authors-can-declare-their-modules-to-be-compatible-with-one-or-more-powershell-editions-using-the-compatiblepseditions-module-manifest-key-this-key-is-only-supported-on-powershell-51-or-later"></a><span data-ttu-id="67583-108">Auteurs van modules kunnen hun modules zo opstellen dat deze compatibel zijn met een of meer PowerShell-edities door de sleutel voor het modulemanifestbestand CompatiblePSEditions te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="67583-108">Module authors can declare their modules to be compatible with one or more PowerShell editions using the CompatiblePSEditions module manifest key.</span></span> <span data-ttu-id="67583-109">Deze sleutel wordt alleen ondersteund in PowerShell 5.1 of hoger.</span><span class="sxs-lookup"><span data-stu-id="67583-109">This key is only supported on PowerShell 5.1 or later.</span></span>
<span data-ttu-id="67583-110">*Opmerking* nadat een module-manifest is opgegeven met de sleutel CompatiblePSEditions, deze niet kan worden geïmporteerd in lagere versies van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67583-110">*NOTE* Once a module manifest is specified with the CompatiblePSEditions key, it can not be imported on lower versions of PowerShell.</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion 5.1
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
Desktop
Core

$ModuleInfo | Get-Member CompatiblePSEditions

   TypeName: System.Management.Automation.PSModuleInfo

Name                 MemberType Definition
----                 ---------- ----------
CompatiblePSEditions Property   System.Collections.Generic.IEnumerable[string] CompatiblePSEditions {get;}

```
<span data-ttu-id="67583-111">Bij het ophalen van een lijst met beschikbare modules kunt u de lijst filteren op PowerShell-editie.</span><span class="sxs-lookup"><span data-stu-id="67583-111">When getting a list of available modules, you can filter the list by PowerShell edition.</span></span>
```powershell
Get-Module -ListAvailable -PSEdition Desktop

    Directory: C:\Program Files\WindowsPowerShell\Modules


ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Manifest   1.0        ModuleWithPSEditions

Get-Module -ListAvailable -PSEdition Core | % CompatiblePSEditions
Desktop
Core

```

## <a name="module-authors-can-publish-a-single-module-targeting-to-either-or-both-powershell-editions-desktop-and-core"></a><span data-ttu-id="67583-112">Module auteurs kunnen een module enkele die gericht is op een of beide PowerShell versies (Desktop en Core) publiceren</span><span class="sxs-lookup"><span data-stu-id="67583-112">Module authors can publish a single module targeting to either or both PowerShell editions (Desktop and Core)</span></span> 

<span data-ttu-id="67583-113">Een module enkele Desktop- en Core edities kunt werken, moet in die module auteur vereist logica toevoegen in beide RootModule of in de module-manifest $PSEdition-variabele.</span><span class="sxs-lookup"><span data-stu-id="67583-113">A single module can work on both Desktop and Core editions, in that module author has to add required logic in either RootModule or in the module manifest using $PSEdition variable.</span></span>
<span data-ttu-id="67583-114">Modules kunnen twee soorten gecompileerde dll die gericht is op zowel CoreCLR als FullCLR hebben.</span><span class="sxs-lookup"><span data-stu-id="67583-114">Modules can have two sets of compiled DLLs targeting both CoreCLR and FullCLR.</span></span>
<span data-ttu-id="67583-115">Hier vindt u het aantal opties voor uw module met logica voor het juiste DLL's laden van het pakket.</span><span class="sxs-lookup"><span data-stu-id="67583-115">Here are the couple of options to package your module with logic for loading proper dlls.</span></span>

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a><span data-ttu-id="67583-116">Optie 1: Een module gebruiken om meerdere versies en meerdere edities van PowerShell verpakking</span><span class="sxs-lookup"><span data-stu-id="67583-116">Option 1: Packaging a module for targeting multiple versions and multiple editions of PowerShell</span></span>

#### <a name="module-folder-contents"></a><span data-ttu-id="67583-117">Module Mapinhoud weergeven</span><span class="sxs-lookup"><span data-stu-id="67583-117">Module folder contents</span></span>
- <span data-ttu-id="67583-118">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="67583-118">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span> 
- <span data-ttu-id="67583-119">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="67583-119">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span> 
- <span data-ttu-id="67583-120">PSScriptAnalyzer.psd1</span><span class="sxs-lookup"><span data-stu-id="67583-120">PSScriptAnalyzer.psd1</span></span>
- <span data-ttu-id="67583-121">PSScriptAnalyzer.psm1</span><span class="sxs-lookup"><span data-stu-id="67583-121">PSScriptAnalyzer.psm1</span></span>
- <span data-ttu-id="67583-122">ScriptAnalyzer.format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="67583-122">ScriptAnalyzer.format.ps1xml</span></span>
- <span data-ttu-id="67583-123">ScriptAnalyzer.types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="67583-123">ScriptAnalyzer.types.ps1xml</span></span>
- <span data-ttu-id="67583-124">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="67583-124">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span> 
- <span data-ttu-id="67583-125">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="67583-125">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span> 
- <span data-ttu-id="67583-126">en-US\about_PSScriptAnalyzer.help.txt</span><span class="sxs-lookup"><span data-stu-id="67583-126">en-US\about_PSScriptAnalyzer.help.txt</span></span>
- <span data-ttu-id="67583-127">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span><span class="sxs-lookup"><span data-stu-id="67583-127">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span></span>
- <span data-ttu-id="67583-128">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="67583-128">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span> 
- <span data-ttu-id="67583-129">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="67583-129">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span> 
- <span data-ttu-id="67583-130">Settings\CmdletDesign.psd1</span><span class="sxs-lookup"><span data-stu-id="67583-130">Settings\CmdletDesign.psd1</span></span>
- <span data-ttu-id="67583-131">Settings\DSC.psd1</span><span class="sxs-lookup"><span data-stu-id="67583-131">Settings\DSC.psd1</span></span>
- <span data-ttu-id="67583-132">Settings\ScriptFunctions.psd1</span><span class="sxs-lookup"><span data-stu-id="67583-132">Settings\ScriptFunctions.psd1</span></span>
- <span data-ttu-id="67583-133">Settings\ScriptingStyle.psd1</span><span class="sxs-lookup"><span data-stu-id="67583-133">Settings\ScriptingStyle.psd1</span></span>
- <span data-ttu-id="67583-134">Settings\ScriptSecurity.psd1</span><span class="sxs-lookup"><span data-stu-id="67583-134">Settings\ScriptSecurity.psd1</span></span>

#### <a name="contents-of-psscriptanalyzerpsd1-file"></a><span data-ttu-id="67583-135">Inhoud van PSScriptAnalyzer.psd1 bestand</span><span class="sxs-lookup"><span data-stu-id="67583-135">Contents of PSScriptAnalyzer.psd1 file</span></span>

```powershell
@{
 
# Author of this module
Author = 'Microsoft Corporation'

# Script module or binary module file associated with this manifest.
RootModule = 'PSScriptAnalyzer.psm1'

# Version number of this module.
ModuleVersion = '1.6.1'

# ---
}
```

#### <a name="contents-of-psscriptanalyzerpsm1-file"></a><span data-ttu-id="67583-136">Inhoud van PSScriptAnalyzer.psm1 bestand</span><span class="sxs-lookup"><span data-stu-id="67583-136">Contents of PSScriptAnalyzer.psm1 file</span></span>
<span data-ttu-id="67583-137">Hieronder logica laadt de vereiste assembly's, afhankelijk van de huidige editie of versie.</span><span class="sxs-lookup"><span data-stu-id="67583-137">Below logic loads the required assemblies depending on the current edition or version.</span></span>

```powershell
#
# Script module for module 'PSScriptAnalyzer'
#
Set-StrictMode -Version Latest

# Set up some helper variables to make it easier to work with the module
$PSModule = $ExecutionContext.SessionState.Module
$PSModuleRoot = $PSModule.ModuleBase

# Import the appropriate nested binary module based on the current PowerShell version
$binaryModuleRoot = $PSModuleRoot


if (($PSVersionTable.Keys -contains "PSEdition") -and ($PSVersionTable.PSEdition -ne 'Desktop')) {
    $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'coreclr'
}
else
{
    if ($PSVersionTable.PSVersion -lt [Version]'5.0') {
        $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'PSv3'
    }    
}

$binaryModulePath = Join-Path -Path $binaryModuleRoot -ChildPath 'Microsoft.Windows.PowerShell.ScriptAnalyzer.dll'
$binaryModule = Import-Module -Name $binaryModulePath -PassThru

# When the module is unloaded, remove the nested binary module that was loaded with it
$PSModule.OnRemove = {
    Remove-Module -ModuleInfo $binaryModule
} 

```

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls-and-nestedrequired-modules"></a><span data-ttu-id="67583-138">Optie 2: $PSEdition-variabele gebruiken in de PSD1-bestand laden van de juiste DLL's en modules geneste/vereist</span><span class="sxs-lookup"><span data-stu-id="67583-138">Option 2: Use $PSEdition variable in the PSD1 file to load the proper DLLs and Nested/Required modules</span></span>

<span data-ttu-id="67583-139">In PS 5.1 of nieuwer, worden de globale variabele $PSEdition is toegestaan in het manifestbestand van de module.</span><span class="sxs-lookup"><span data-stu-id="67583-139">In PS 5.1 or newer, $PSEdition global variable is allowed in the module manifest file.</span></span>
<span data-ttu-id="67583-140">Met deze variabele kan opgeven module-auteur de voorwaardelijke waarden in het manifestbestand van de module.</span><span class="sxs-lookup"><span data-stu-id="67583-140">Using this variable, module author can specify the conditional values in the module manifest file.</span></span> <span data-ttu-id="67583-141">$PSEdition variabele kan worden verwezen in de van de beperkte taalmodus of een gegevenssectie.</span><span class="sxs-lookup"><span data-stu-id="67583-141">$PSEdition variable can be referenced in restricted language mode or a Data section.</span></span> 

<span data-ttu-id="67583-142">*Opmerking* zodra een module-manifest wordt opgegeven met de sleutel CompatiblePSEditions of $PSEdition variabele gebruikt, deze niet kan worden geïmporteerd in lagere versies van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67583-142">*NOTE* Once a module manifest is specified with the CompatiblePSEditions key or uses $PSEdition variable, it can not be imported on lower versions of PowerShell.</span></span>


#### <a name="sample-module-manifest-file-with-compatiblepseditions-key"></a><span data-ttu-id="67583-143">Voorbeeld module manifestbestand met CompatiblePSEditions sleutel</span><span class="sxs-lookup"><span data-stu-id="67583-143">Sample module manifest file with CompatiblePSEditions key</span></span>

```powershell
@{ 
# - - -
 
# Script module or binary module file associated with this manifest.
RootModule = if($PSEdition -eq 'Core')
{
'coreclr\MyCoreClrRM.dll'
}
else # Desktop
{
'clr\MyFullClrRM.dll'
}
 
# Supported PSEditions
CompatiblePSEditions = 'Desktop', 'Core'
 
# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
NestedModules = if($PSEdition -eq 'Core')
{
'coreclr\MyCoreClrNM1.dll',
'coreclr\MyCoreClrNM2.dll'
}
else # Desktop
{
'clr\MyFullClrNM1.dll',
'clr\MyFullClrNM2.dll'
}
 
# -- - -
}
```

#### <a name="module-contents"></a><span data-ttu-id="67583-144">Module-inhoud</span><span class="sxs-lookup"><span data-stu-id="67583-144">Module contents</span></span>

```powershell

PS C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions> dir -Recurse
 
    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions
 
Mode                LastWriteTime         Length Name                                                                                
----                -------------         ------ ----                                                                                
d-----         7/5/2016   1:37 PM                clr                                                                                 
d-----         7/5/2016   1:36 PM                coreclr                                                                             
-a----         7/5/2016   1:34 PM           4906 ModuleWithEditions.psd1                                                             
 
    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\clr
 
Mode                LastWriteTime         Length Name                                                                                
----                -------------         ------ ----                                                                                
-a----         7/5/2016   1:35 PM              0 MyFullClrNM1.dll                                                                    
-a----         7/5/2016   1:35 PM              0 MyFullClrNM2.dll                                                                    
-a----         7/5/2016   1:35 PM              0 MyFullClrRM.dl                                                                      
 
    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\coreclr
 
Mode                LastWriteTime         Length Name                                                                                
----                -------------         ------ ----                                                                                
-a----         7/5/2016   1:35 PM              0 MyCoreClrNM1.dll                                                                    
-a----         7/5/2016   1:35 PM              0 MyCoreClrNM2.dll                                                                    
-a----         7/5/2016   1:35 PM              0 MyCoreClrRM.dl                                                                      
```

## <a name="powershell-gallery-users-can-find-the-list-of-modules-supported-on-a-specific-powershell-edition-using-tags-pseditiondesktop-and-pseditoncore"></a><span data-ttu-id="67583-145">Gebruikers van PowerShell Gallery vindt de lijst met modules die worden ondersteund op een specifieke editie van PowerShell met tags PSEdition_Desktop en PSEditon_Core.</span><span class="sxs-lookup"><span data-stu-id="67583-145">PowerShell Gallery users can find the list of modules supported on a specific PowerShell Edition using tags PSEdition_Desktop and PSEditon_Core.</span></span>
<span data-ttu-id="67583-146">Modules zonder tags PSEdition_Desktop en PSEditon_Core worden beschouwd als te werken in PowerShell Desktop-edities.</span><span class="sxs-lookup"><span data-stu-id="67583-146">Modules without PSEdition_Desktop and PSEditon_Core tags are considered to work fine on PowerShell Desktop editions.</span></span>

```powershell

# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEditon_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEditon_Core

```


## <a name="more-details"></a><span data-ttu-id="67583-147">meer informatie</span><span class="sxs-lookup"><span data-stu-id="67583-147">More details</span></span>
### <a name="scripts-with-pseditionsscriptscriptwithpseditionsupportmd"></a>[<span data-ttu-id="67583-148">Scripts met PSEditions</span><span class="sxs-lookup"><span data-stu-id="67583-148">Scripts with PSEditions</span></span>](../script/scriptwithpseditionsupport.md)
### <a name="pseditions-support-on-powershellgallerypsgallerypsgallerypseditionsmd"></a>[<span data-ttu-id="67583-149">Ondersteuning voor PSEditions op PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="67583-149">PSEditions support on PowerShellGallery</span></span>](../../psgallery/psgallery_pseditions.md)
### <a name="update-module-manifest-psgetupdate-modulemanifestmd"></a><span data-ttu-id="67583-150">[Update module-manifest] (./psget_update-modulemanifest.md)</span><span class="sxs-lookup"><span data-stu-id="67583-150">[Update module manifest] (./psget_update-modulemanifest.md)</span></span>
