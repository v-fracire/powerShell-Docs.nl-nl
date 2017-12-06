---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: DSC-WindowsPackageCab Resource
ms.openlocfilehash: 9b1bf3cb95abcbe46976ae0fd328280a3a8d7f28
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-windowspackagecab-resource"></a><span data-ttu-id="f7467-103">DSC-WindowsPackageCab Resource</span><span class="sxs-lookup"><span data-stu-id="f7467-103">DSC WindowsPackageCab Resource</span></span>

> <span data-ttu-id="f7467-104">Van toepassing op: Windows PowerShell 5.1 en hoger</span><span class="sxs-lookup"><span data-stu-id="f7467-104">Applies To: Windows PowerShell 5.1 and later</span></span>

<span data-ttu-id="f7467-105">De **WindowsPackageCab** in Windows PowerShell Desired State Configuration (DSC)-bron biedt een mechanisme om te installeren of verwijderen van Windows-CAB-pakketten in een doelknooppunt.</span><span class="sxs-lookup"><span data-stu-id="f7467-105">The **WindowsPackageCab** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Windows cabinet (.cab) packages on a target node.</span></span>

<span data-ttu-id="f7467-106">Het doelknooppunt moet de DISM-PowerShell-module geïnstalleerd hebben.</span><span class="sxs-lookup"><span data-stu-id="f7467-106">The target node must have the DISM PowerShell module installed.</span></span> <span data-ttu-id="f7467-107">Zie voor informatie [Gebruik DISM in Windows PowerShell](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/manufacture/desktop/use-dism-in-windows-powershell-s14).</span><span class="sxs-lookup"><span data-stu-id="f7467-107">For information, see [Use DISM in Windows PowerShell](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/manufacture/desktop/use-dism-in-windows-powershell-s14).</span></span> 


## <a name="syntax"></a><span data-ttu-id="f7467-108">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="f7467-108">Syntax</span></span>

```
{
    Name = [string]
    Ensure = [string] { Absent | Present }
    SourcePath = [string]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="f7467-109">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="f7467-109">Properties</span></span>

|  <span data-ttu-id="f7467-110">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="f7467-110">Property</span></span>  |  <span data-ttu-id="f7467-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f7467-111">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="f7467-112">Naam</span><span class="sxs-lookup"><span data-stu-id="f7467-112">Name</span></span>| <span data-ttu-id="f7467-113">Geeft de naam van het pakket voor u wilt een specifieke status zorgen.</span><span class="sxs-lookup"><span data-stu-id="f7467-113">Indicates the name of the package for you want to ensure a specific state.</span></span>| 
| <span data-ttu-id="f7467-114">Zorg ervoor dat</span><span class="sxs-lookup"><span data-stu-id="f7467-114">Ensure</span></span>| <span data-ttu-id="f7467-115">Hiermee wordt aangegeven of het pakket is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="f7467-115">Indicates if the package is installed.</span></span> <span data-ttu-id="f7467-116">Deze eigenschap instellen op 'Afwezig' controleert u dat het pakket niet is geïnstalleerd (of het pakket verwijderen als deze is geïnstalleerd).</span><span class="sxs-lookup"><span data-stu-id="f7467-116">Set this property to "Absent" to ensure the package is not installed (or uninstall the package if it is installed).</span></span> <span data-ttu-id="f7467-117">Instellen om "" (de standaardwaarde) om te controleren of dat het pakket is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="f7467-117">Set it to "Present" (the default value) to ensure the package is installed.</span></span>|
| <span data-ttu-id="f7467-118">Pad</span><span class="sxs-lookup"><span data-stu-id="f7467-118">Path</span></span>| <span data-ttu-id="f7467-119">Geeft het pad waar het pakket zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="f7467-119">Indicates the path where the package resides.</span></span>| 
| <span data-ttu-id="f7467-120">Logboekpad</span><span class="sxs-lookup"><span data-stu-id="f7467-120">LogPath</span></span>| <span data-ttu-id="f7467-121">Hiermee geeft u het volledige pad waar u de provider een logboekbestand om te installeren of verwijderen van het pakket opslaan.</span><span class="sxs-lookup"><span data-stu-id="f7467-121">Indicates the full path where you want the provider to save a log file to install or uninstall the package.</span></span>| 
| <span data-ttu-id="f7467-122">dependsOn</span><span class="sxs-lookup"><span data-stu-id="f7467-122">DependsOn</span></span> | <span data-ttu-id="f7467-123">Hiermee wordt aangegeven dat de configuratie van een andere resource uitvoeren moet voordat deze bron is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="f7467-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="f7467-124">Bijvoorbeeld, als de ID van de resourceconfiguratie scriptblok die u wilt uitvoeren eerst is **ResourceName** en het type **ResourceType**, de syntaxis voor het gebruik van deze eigenschap is ' DependsOn = '[ ResourceType] ResourceName' ''.</span><span class="sxs-lookup"><span data-stu-id="f7467-124">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`\`.</span></span>| 

## <a name="example"></a><span data-ttu-id="f7467-125">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="f7467-125">Example</span></span>

<span data-ttu-id="f7467-126">De volgende voorbeeldconfiguratie parameters nodig heeft, en zorgt ervoor dat het CAB-bestand opgegeven door de `$Name` parameter is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="f7467-126">The following example configuration takes input parameters, and ensures that the .cab file specified by the `$Name` parameter is installed.</span></span>

```powershell
Configuration Sample_WindowsPackageCab
{
    param
    (
        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name,

        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $SourcePath,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $LogPath
    )

    Import-DscResource -ModuleName 'PSDscResources'

    WindowsPackageCab WindowsPackageCab1
    {
        Name = $Name
        Ensure = 'Present'
        SourcePath = $SourcePath
        LogPath = $LogPath
    }
}
```
