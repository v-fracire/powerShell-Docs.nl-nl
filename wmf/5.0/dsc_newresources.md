---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: WMF, powershell, setup
ms.openlocfilehash: ab49a0ae10f9ad32966944a1dcf8125619bde141
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="new-built-in-dsc-resources"></a><span data-ttu-id="de94b-102">Nieuwe ingebouwde DSC-resources</span><span class="sxs-lookup"><span data-stu-id="de94b-102">New built-in DSC resources</span></span>

<span data-ttu-id="de94b-103">WMF 5.0 RTM heeft 4 nieuwe DSC-resources:</span><span class="sxs-lookup"><span data-stu-id="de94b-103">WMF 5.0 RTM has 4 new DSC resources:</span></span> 
* <span data-ttu-id="de94b-104">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="de94b-104">WindowsFeatureSet</span></span>
* <span data-ttu-id="de94b-105">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="de94b-105">WindowsOptionalFeatureSet</span></span>
* <span data-ttu-id="de94b-106">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="de94b-106">ServiceSet</span></span>
* <span data-ttu-id="de94b-107">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="de94b-107">ProcessSet</span></span> 

<span data-ttu-id="de94b-108">Deze resources zijn een gemakkelijke manier voor het configureren van meerdere exemplaren die gebruikmaken van een aanroep van één resource.</span><span class="sxs-lookup"><span data-stu-id="de94b-108">These resources provide an easy way to configure multiple instances using a single resource call.</span></span>

## <a name="windowsfeatureset"></a><span data-ttu-id="de94b-109">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="de94b-109">WindowsFeatureSet</span></span>

```powershell
# Get the syntax of WindowsFeatureSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name WindowsFeatureSet -Syntax

WindowsFeatureSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Name = [String[]]
    [Ensure = [String]]
    [Source = [String]]
    [IncludeAllSubFeature = [Boolean]]
    [Credential = [PSCredential]]
    [LogPath = [String]]
}
```

## <a name="windowsoptionalfeatureset"></a><span data-ttu-id="de94b-110">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="de94b-110">WindowsOptionalFeatureSet</span></span> 

```powershell
# Get the syntax of WindowsOptionalFeatureSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name WindowsOptionalFeatureSet -Syntax

WindowsOptionalFeatureSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Name = [String[]]
    Ensure = [String]
    [Source = [String[]]]
    [RemoveFilesOnDisable = [Boolean]]
    [LogPath = [String]]
    [NoWindowsUpdateCheck = [Boolean]]
    [LogLevel = [String]]
}
```

## <a name="serviceset"></a><span data-ttu-id="de94b-111">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="de94b-111">ServiceSet</span></span> 

```powershell
# Get the syntax of ServiceSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name ServiceSet -Syntax

ServiceSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Name = [String[]]
    [StartupType = [String]]
    [BuiltInAccount = [String]]
    [State = [String]]
    [Ensure = [String]]
    [Credential = [PSCredential]]
}
```

## <a name="processset"></a><span data-ttu-id="de94b-112">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="de94b-112">ProcessSet</span></span> 

```powershell
# Get the syntax of ProcessSet resource
Get-DscResource -Module psdesiredstateconfiguration -Name ProcessSet -Syntax

ProcessSet [String] #ResourceName
{
    [DependsOn = [String[]]]
    Path = [String[]]
    [Credential = [PSCredential]]
    [Ensure = [String]]
    [StandardOutputPath = [String]]
    [StandardErrorPath = [String]]
    [StandardInputPath = [String]]
    [WorkingDirectory = [String]]
}
```
