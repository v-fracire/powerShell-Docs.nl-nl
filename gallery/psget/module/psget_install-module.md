---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: Galerie, powershell, cmdlet, psget
title: Installatie-Module
ms.openlocfilehash: c066f4b34a03206cc0f31e9d40144fd719d9e305
ms.sourcegitcommit: 58371abe9db4b9a0e4e1eb82d39a9f9e187355f9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2017
---
# <a name="install-module"></a><span data-ttu-id="de0ec-103">Installatie-Module</span><span class="sxs-lookup"><span data-stu-id="de0ec-103">Install-Module</span></span>

<span data-ttu-id="de0ec-104">Installeert de PowerShell-modules van online opslagplaatsen op de lokale computer.</span><span class="sxs-lookup"><span data-stu-id="de0ec-104">Installs the PowerShell modules from online repositories to the local computer.</span></span>

## <a name="description"></a><span data-ttu-id="de0ec-105">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="de0ec-105">Description</span></span>

<span data-ttu-id="de0ec-106">De cmdlet Install-Module downloadt van een of meer modules van een online galerie, valideert en installeert ze op de lokale computer aan het bereik van de gespecificeerde installatie.</span><span class="sxs-lookup"><span data-stu-id="de0ec-106">Install-Module cmdlet downloads one or more modules from an online gallery, validates and installs them on the local computer to the specified installation scope.</span></span>

<span data-ttu-id="de0ec-107">De cmdlet Install-Module ontvangt een of meer modules die voldoen aan opgegeven criteria vanuit een online-galerie, controleert of de zoekresultaten zijn geldige modules en kopieën module mappen naar de installatielocatie.</span><span class="sxs-lookup"><span data-stu-id="de0ec-107">The Install-Module cmdlet gets one or more modules that meet specified criteria from an online gallery, verifies that search results are valid modules, and copies module folders to the installation location.</span></span>

<span data-ttu-id="de0ec-108">Als er geen bereik is gedefinieerd, of wanneer de waarde van de bereikparameter AllUsers is, wordt de module naar %systemdrive%:\Program Files\WindowsPowerShell\Modules geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="de0ec-108">When no scope is defined, or when the value of the Scope parameter is AllUsers, the module is installed to %systemdrive%:\Program Files\WindowsPowerShell\Modules.</span></span> <span data-ttu-id="de0ec-109">Wanneer de waarde van bereik CurrentUser is, wordt de module geïnstalleerd in $home\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="de0ec-109">When the value of Scope is CurrentUser, the module is installed to $home\Documents\WindowsPowerShell\Modules.</span></span>

<span data-ttu-id="de0ec-110">U kunt uw resultaten op basis van de minimale en de exacte versie van de opgegeven modules filteren.</span><span class="sxs-lookup"><span data-stu-id="de0ec-110">You can filter your results based on minimum and exact versions of specified modules.</span></span>

- <span data-ttu-id="de0ec-111">Side-by-side-versie-ondersteuning in Windows PowerShell 5.0 of hoger</span><span class="sxs-lookup"><span data-stu-id="de0ec-111">Side-by-side version support on Windows PowerShell 5.0 or newer</span></span>
- <span data-ttu-id="de0ec-112">Ondersteuning voor de installatie van module afhankelijkheid</span><span class="sxs-lookup"><span data-stu-id="de0ec-112">Module dependency installation support</span></span>
- <span data-ttu-id="de0ec-113">**Niet-vertrouwde prompt:**acceptatie van de gebruiker is vereist voor het installeren van de modules van een niet-vertrouwde opslagplaats.</span><span class="sxs-lookup"><span data-stu-id="de0ec-113">**Untrusted prompt:**User acceptance is required for installing the modules from an untrusted repository.</span></span>
- <span data-ttu-id="de0ec-114">-Force opnieuw installeren van de geïnstalleerde module</span><span class="sxs-lookup"><span data-stu-id="de0ec-114">-Force reinstalls the installed module</span></span>
- <span data-ttu-id="de0ec-115">RequiredVersion installeert de opgegeven versie in SxS met bestaande versies op PowerShell versie 5.0 of hoger.</span><span class="sxs-lookup"><span data-stu-id="de0ec-115">RequiredVersion installs the specified version in SxS with existing versions on PowerShell version 5.0 or newer.</span></span>

### <a name="scope"></a><span data-ttu-id="de0ec-116">Bereik</span><span class="sxs-lookup"><span data-stu-id="de0ec-116">Scope</span></span>
<span data-ttu-id="de0ec-117">Hiermee geeft u het bereik van de installatie van de module.</span><span class="sxs-lookup"><span data-stu-id="de0ec-117">Specifies the installation scope of the module.</span></span> <span data-ttu-id="de0ec-118">De acceptabele waarden voor deze parameter zijn: AllUsers en CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="de0ec-118">The acceptable values for this parameter are: AllUsers and CurrentUser.</span></span>

<span data-ttu-id="de0ec-119">Het bereik van de installatie standaard is AllUsers.</span><span class="sxs-lookup"><span data-stu-id="de0ec-119">The default installation scope is AllUsers.</span></span>

<span data-ttu-id="de0ec-120">Het bereik AllUsers kunt modules worden geïnstalleerd op een locatie die toegankelijk is voor alle gebruikers van de computer, dat wil zeggen, "$env: SystemDrive\Program Files\WindowsPowerShell\Modules '.</span><span class="sxs-lookup"><span data-stu-id="de0ec-120">The AllUsers scope lets modules be installed in a location that is accessible to all users of the computer, that is, "$env:SystemDrive\Program Files\WindowsPowerShell\Modules".</span></span>

<span data-ttu-id="de0ec-121">Het bereik CurrentUser kunt modules worden geïnstalleerd tot '$home\Documents\WindowsPowerShell\Modules', zodat de module alleen beschikbaar voor de huidige gebruiker is.</span><span class="sxs-lookup"><span data-stu-id="de0ec-121">The CurrentUser scope lets modules be installed only to "$home\Documents\WindowsPowerShell\Modules", so that the module is available only to the current user.</span></span>

## <a name="notes"></a><span data-ttu-id="de0ec-122">Opmerkingen</span><span class="sxs-lookup"><span data-stu-id="de0ec-122">Notes</span></span>

<span data-ttu-id="de0ec-123">Deze cmdlet wordt uitgevoerd op Windows PowerShell 3.0 of latere versies van Windows PowerShell op Windows 7 of Windows 2008 R2 en latere versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="de0ec-123">This cmdlet runs on Windows PowerShell 3.0 or later releases of Windows PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="de0ec-124">Als een geïnstalleerde module kan niet worden geïmporteerd (dat wil zeggen, als er geen een psm1-, .psd1- of DLL-bestand met dezelfde naam in de map), mislukt de installatie tenzij u de parameter Force aan de opdracht toevoegen.</span><span class="sxs-lookup"><span data-stu-id="de0ec-124">If an installed module cannot be imported (that is, if it does not have a .psm1, .psd1, or .dll of the same name within the folder), installation fails unless you add the Force parameter to your command.</span></span>

<span data-ttu-id="de0ec-125">Als een versie van de module op de computer overeenkomt met de opgegeven waarde voor de parameter Name en u de parameter MinimumVersion of RequiredVersion niet hebt toegevoegd, wordt de installatie-Module achtergrond blijft zonder dat u installeert deze module.</span><span class="sxs-lookup"><span data-stu-id="de0ec-125">If a version of the module on the computer matches the value specified for the Name parameter, and you have not added the MinimumVersion or RequiredVersion parameter, Install-Module silently continues without installing that module.</span></span> <span data-ttu-id="de0ec-126">Als de MinimumVersion of RequiredVersion parameters worden opgegeven en de bestaande module komt niet overeen met de waarden in die parameter, treedt er een fout op.</span><span class="sxs-lookup"><span data-stu-id="de0ec-126">If the MinimumVersion or RequiredVersion parameters are specified, and the existing module does not match the values in that parameter, then an error occurs.</span></span> <span data-ttu-id="de0ec-127">Meer specifiek: als de versie van de momenteel geïnstalleerde module lager is dan de waarde van de parameter MinimumVersion of niet gelijk zijn aan de waarde van de parameter RequiredVersion is een fout optreedt.</span><span class="sxs-lookup"><span data-stu-id="de0ec-127">To be more specific: if the version of the currently-installed module is either lower than the value of the MinimumVersion parameter, or not equal to the value of the RequiredVersion parameter, an error occurs.</span></span> <span data-ttu-id="de0ec-128">Als de versie van de geïnstalleerde module groter dan de waarde van de parameter MinimumVersion of gelijk zijn aan de waarde van de parameter RequiredVersion is, wordt de installatie-Module achtergrond blijft zonder dat u installeert deze module.</span><span class="sxs-lookup"><span data-stu-id="de0ec-128">If the version of the installed module is greater than the value of the MinimumVersion parameter, or equal to the value of the RequiredVersion parameter, Install-Module silently continues without installing that module.</span></span>

<span data-ttu-id="de0ec-129">Installatie-Module een fout geretourneerd als er geen module in de on line galerie die overeenkomt met de opgegeven naam bestaat.</span><span class="sxs-lookup"><span data-stu-id="de0ec-129">Install-Module returns an error if no module exists in the online gallery that matches the specified name.</span></span>

<span data-ttu-id="de0ec-130">Geef een matrix met de modulenamen van de, gescheiden door komma's voor het installeren van meerdere modules.</span><span class="sxs-lookup"><span data-stu-id="de0ec-130">To install multiple modules, specify an array of the module names, separated by commas.</span></span> <span data-ttu-id="de0ec-131">U kunt MinimumVersion of RequiredVersion niet toevoegen als u meerdere modulenamen opgeeft.</span><span class="sxs-lookup"><span data-stu-id="de0ec-131">You cannot add MinimumVersion or RequiredVersion if you specify multiple module names.</span></span>

<span data-ttu-id="de0ec-132">Standaard worden modules geïnstalleerd in de map Program Files om verwarring te voorkomen dat tijdens de installatie van Windows PowerShell Desired State Configuration (DSC) resources. U kunt meerdere PSGetItemInfo objecten naar installatie-Module; overbrengen Dit is een andere manier voor het opgeven van meerdere modules installeren in één opdracht.</span><span class="sxs-lookup"><span data-stu-id="de0ec-132">By default, modules are installed to the Program Files folder, to prevent confusion when you are installing Windows PowerShell Desired State Configuration (DSC) resources.You can pipe multiple PSGetItemInfo objects to Install-Module; this is another way of specifying multiple modules to install in a single command.</span></span>

<span data-ttu-id="de0ec-133">Om te voorkomen dat de actieve modules die schadelijke code, geïnstalleerd bevatten worden modules niet automatisch geïmporteerd door de installatie.</span><span class="sxs-lookup"><span data-stu-id="de0ec-133">To help prevent running modules that contain malicious code, installed modules are not automatically imported by installation.</span></span> <span data-ttu-id="de0ec-134">Als een best practice, module code evalueren voordat u cmdlets of functies voor de eerste keer uitgevoerd in een module.</span><span class="sxs-lookup"><span data-stu-id="de0ec-134">As a security best practice, evaluate module code before running any cmdlets or functions in a module for the first time.</span></span>


## <a name="cmdlet-syntax"></a><span data-ttu-id="de0ec-135">De syntaxis van cmdlet</span><span class="sxs-lookup"><span data-stu-id="de0ec-135">Cmdlet syntax</span></span>
```powershell
Get-Command -Name Install-Module -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="de0ec-136">Verwijzing naar het online help van cmdlet</span><span class="sxs-lookup"><span data-stu-id="de0ec-136">Cmdlet online help reference</span></span>

[<span data-ttu-id="de0ec-137">Installatie-Module</span><span class="sxs-lookup"><span data-stu-id="de0ec-137">Install-Module</span></span>](http://go.microsoft.com/fwlink/?LinkID=398573)

## <a name="example-commands"></a><span data-ttu-id="de0ec-138">Voorbeeldopdrachten</span><span class="sxs-lookup"><span data-stu-id="de0ec-138">Example commands</span></span>

```powershell

# Install a module by name
Install-Module -Name MyDscModule

# Install multiple modules
Install-Module ContosoClient,ContosoServer

# Install a module using its minimum version
Install-Module -Name ContosoServer -MinimumVersion 1.0

# Install a specific version of a module
Install-Module -Name ContosoServer -RequiredVersion 1.1.3

# Install a specific prerelease version of a module
Install-Module -Name ContosoServer -RequiredVersion 1.1.3-alpha -AllowPrerelease

# Install the latest version of a module by name, including prelrelease versions if one exists
Install-Module -Name ContosoServer -AllowPrerelease

# Install the latest version of a module to $home\Documents\WindowsPowerShell\Modules.
Install-Module -Name ContosoServer -Scope CurrentUser

# if a module is already available under $env:PSModulePath, below command fails with 'ModuleAlreadyInstalled,Install-Package,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage'
Install-Module ContosoServer -RequiredVersion 1.5

# if a module is already available under $env:PSModulePath, below command fails with 'ModuleAlreadyInstalled,Install-Package,Microsoft.PowerShell.PackageManagement.Cmdlets.InstallPackage'
Install-Module ContosoServer -MinimumVersion 2.5

# Install multiple modules from multiple registered repositories
Install-Module ContosoClient,ContosoServer -Repository PSGallery, PrivatePSGallery

# Install a module with -WhatIf
Install-Module ContosoClient -WhatIf

# Install a module with -Confirm. A prompt will be displayed to confirm the installation.
Install-Module ContosoClient -WhatIf

# -Force option reinstalls the installed module
Install-Module ContosoClient -Force

# Install a module with dependencies
Install-Module -Name 
```

## <a name="install-module-cmdlet-in-pipeline-operations"></a><span data-ttu-id="de0ec-139">De cmdlet Install-Module in pipeline-bewerkingen</span><span class="sxs-lookup"><span data-stu-id="de0ec-139">Install-Module cmdlet in pipeline operations</span></span>

```powershell

# Find a module and install it
Find-Module -Name "MyDSC*" | Install-Module

# Find a module and install it to the CurrentUser scope
Find-Module -Name "MyDSC*" | Install-Module -Scope CurrentUser

# Find commands by name and install them
# The first command finds the specified commands in the INT repository, and then uses the pipeline operator to pass them to Install-Module to install them.
# The second command uses Get-InstalledModule to verify the modules from the prior command are installed.
Find-Command -Repository "INT" -Name Get-ContosoClient,Get-ContosoServer | Install-Module
Get-InstalledModule

# This command finds the resource named MyResource and passes it to the Install-Module cmdlet by using the pipeline operator. The Install-Module cmdlet installs the module for the resource. 
# If you pipe multiple resources to the Install-Module cmdlet from the same module, Install-Module attempts to install the module only once. 
Find-DscResource -Name "MyResource" | Install-Module
Get-InstalledModule

# Find multiple role capabilities and install them
Find-RoleCapability -Name MyJeaRole, Maintenance | Install-Module
Get-InstalledModule

```

## <a name="side-by-side-version-support-on-powershell-50-or-newer"></a><span data-ttu-id="de0ec-140">Ondersteuning voor side-by-Side-versie in PowerShell 5.0 of hoger</span><span class="sxs-lookup"><span data-stu-id="de0ec-140">Side-by-Side Version Support on PowerShell 5.0 or newer</span></span>

<span data-ttu-id="de0ec-141">PowerShellGet ondersteunt de side-by-side (SxS) module versie-ondersteuning in installatie-Module, Update-Module en Publish-Module-cmdlets die worden uitgevoerd in Windows PowerShell 5.0 of hoger.</span><span class="sxs-lookup"><span data-stu-id="de0ec-141">PowerShellGet supports the side-by-side (SxS) module version support in Install-Module, Update-Module, and Publish-Module cmdlets that run in Windows PowerShell 5.0 or newer.</span></span>

### <a name="install-module-examples"></a><span data-ttu-id="de0ec-142">Voorbeelden van Install-Module</span><span class="sxs-lookup"><span data-stu-id="de0ec-142">Install-Module examples</span></span>

```powershell
# Install a version of the module
Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.0 -Repository PSGallery
Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase

Name : PSScriptAnalyzer
Version : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

# Install another version of the module in Side-by-Side with already installed version.
Install-Module -Name PSScriptAnalyzer -RequiredVersion 1.1.1 -Repository PSGallery
Get-Module -ListAvailable -Name PSScriptAnalyzer | Format-List Name,Version,ModuleBase

Name       : PSScriptAnalyzer 
Version    : 1.1.1
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.1
Name       : PSScriptAnalyzer
Version    : 1.1.0
ModuleBase : C:\Program Files\WindowsPowerShell\Modules\PSScriptAnalyzer\1.1.0

# Get all versions of an installed module
Get-InstalledModule -Name PSScriptAnalyzer -AllVersions
Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.1.0      PSScriptAnalyzer                    PSGallery            PSScriptAnalyzer provides script analysis... 
1.1.1      PSScriptAnalyzer                    PSGallery            PSScriptAnalyzer provides script analysis...


```

## <a name="install-module-with-its-dependencies"></a><span data-ttu-id="de0ec-143">Module met de bijbehorende afhankelijkheden installeren</span><span class="sxs-lookup"><span data-stu-id="de0ec-143">Install module with its dependencies</span></span>

```powershell

# Find a module
Find-Module -Name TypePx -Repository PSGallery

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
2.0.1.20   TypePx                              PSGallery            The TypePx module adds properties and methods to the m...

# Find a module and its dependencies
Find-Module -Name TypePx -Repository PSGallery -IncludeDependencies

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
2.0.1.20   TypePx                              PSGallery            The TypePx module adds properties and methods to the m...
1.0.5.18   SnippetPx                           PSGallery            The SnippetPx module enhances the snippet experience i...

# Discover the dependencies list without adding -IncludeDependencies
$result = Find-Module -Name TypePx -Repository PSGallery
$result.Dependencies

Name                           Value
----                           -----
Name                           SnippetPx
CanonicalId                    powershellget:SnippetPx/#https://www.powershellgallery.com/api/v2/


# Now install the module along with its dependencies
Install-Module -Name TypePx -Repository PSGallery -Verbose

VERBOSE: Repository details, Name = 'PSGallery', Location = 'https://www.powershellgallery.com/api/v2/'; IsTrusted =
'False'; IsRegistered = 'True'.
VERBOSE: Using the provider 'PowerShellGet' for searching packages.
VERBOSE: Using the specified source names : 'PSGallery'.
VERBOSE: Getting the provider object for the PackageManagement Provider 'NuGet'.
VERBOSE: The specified Location is 'https://www.powershellgallery.com/api/v2/' and PackageManagementProvider is
'NuGet'.
VERBOSE: Searching repository 'https://www.powershellgallery.com/api/v2/FindPackagesById()?id='TypePx'' for ''.
VERBOSE: Total package yield:'1' for the specified package 'TypePx'.
VERBOSE: Performing the operation "Install-Module" on target "Version '2.0.1.20' of module 'TypePx'".

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change its
InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from
'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
VERBOSE: The installation scope is specified to be 'AllUsers'.
VERBOSE: The specified module will be installed in 'C:\Program Files\WindowsPowerShell\Modules'.
VERBOSE: The specified Location is 'NuGet' and PackageManagementProvider is 'NuGet'.
VERBOSE: Downloading module 'TypePx' with version '2.0.1.20' from the repository
'https://www.powershellgallery.com/api/v2/'.
VERBOSE: Searching repository 'https://www.powershellgallery.com/api/v2/FindPackagesById()?id='TypePx'' for ''.
VERBOSE: Searching repository 'https://www.powershellgallery.com/api/v2/FindPackagesById()?id='SnippetPx'' for ''.
VERBOSE: InstallPackage' - name='SnippetPx',
version='1.0.5.18',destination='C:\Users\manikb\AppData\Local\Temp\1027042896'
VERBOSE: DownloadPackage' - name='SnippetPx',
version='1.0.5.18',destination='C:\Users\manikb\AppData\Local\Temp\1027042896\SnippetPx\SnippetPx.nupkg',
uri='https://www.powershellgallery.com/api/v2/package/SnippetPx/1.0.5.18'
VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/SnippetPx/1.0.5.18'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/SnippetPx/1.0.5.18'.
VERBOSE: Completed downloading 'SnippetPx'.
VERBOSE: Hash for package 'SnippetPx' does not match hash provided from the server.
VERBOSE: InstallPackageLocal' - name='SnippetPx',
version='1.0.5.18',destination='C:\Users\manikb\AppData\Local\Temp\1027042896'
VERBOSE: InstallPackage' - name='TypePx',
version='2.0.1.20',destination='C:\Users\manikb\AppData\Local\Temp\1027042896'
VERBOSE: DownloadPackage' - name='TypePx',
version='2.0.1.20',destination='C:\Users\manikb\AppData\Local\Temp\1027042896\TypePx\TypePx.nupkg',
uri='https://www.powershellgallery.com/api/v2/package/TypePx/2.0.1.20'
VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/TypePx/2.0.1.20'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/TypePx/2.0.1.20'.
VERBOSE: Completed downloading 'TypePx'.
VERBOSE: Hash for package 'TypePx' does not match hash provided from the server.
VERBOSE: InstallPackageLocal' - name='TypePx',
version='2.0.1.20',destination='C:\Users\manikb\AppData\Local\Temp\1027042896'
VERBOSE: Installing the dependency module 'SnippetPx' with version '1.0.5.18' for the module 'TypePx'.
VERBOSE: Module 'SnippetPx' was installed successfully to path 'C:\Program
Files\WindowsPowerShell\Modules\SnippetPx\1.0.5.18'.
VERBOSE: Module 'TypePx' was installed successfully to path 'C:\Program
Files\WindowsPowerShell\Modules\TypePx\2.0.1.20'.


# Get the installed modules
Get-InstalledModule

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.0.5.18   SnippetPx                           PSGallery            The SnippetPx module enhances the snippet experience i...
2.0.1.20   TypePx                              PSGallery            The TypePx module adds properties and methods to the m...

```

## <a name="error-scenarios"></a><span data-ttu-id="de0ec-144">Fout bij scenario 's</span><span class="sxs-lookup"><span data-stu-id="de0ec-144">Error scenarios</span></span>

```powershell

# Below command fails with 'NameShouldNotContainWildcardCharacters,Install-Module'
Install-Module ContosoServe*

# Below command fails with 'VersionRangeAndRequiredVersionCannotBeSpecifiedTogether,Install-Module'
Install-Module ContosoServer -MinimumVersion 1.0 -RequiredVersion 5.0

# Below command fails with 'VersionParametersAreAllowedOnlyWithSingleName,Install-Module'
Install-Module ContosoClient,ContosoServer -RequiredVersion 2.0

# Below command fails with 'VersionParametersAreAllowedOnlyWithSingleName,Install-Module'
Install-Module ContosoClient,ContosoServer -MinimumVersion 2.0

```
