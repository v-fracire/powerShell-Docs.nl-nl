---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: Logboek van de DSC-Resource
ms.openlocfilehash: 72c9c5a9b8e2a4ed4ce43cfd792572ce95b502b3
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-log-resource"></a><span data-ttu-id="bb305-103">Logboek van de DSC-Resource</span><span class="sxs-lookup"><span data-stu-id="bb305-103">DSC Log Resource</span></span> 

> <span data-ttu-id="bb305-104">Van toepassing op: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="bb305-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="bb305-105">De __logboek__ in Windows PowerShell Desired State Configuration (DSC)-bron biedt een mechanisme voor berichten schrijven naar het gebeurtenislogboek van de Microsoft-Windows-gewenst status Configuration/analysen.</span><span class="sxs-lookup"><span data-stu-id="bb305-105">The __Log__ resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to write messages to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

```
Syntax

Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
}
```

<span data-ttu-id="bb305-106">Opmerking: Standaard alleen de operationele logboeken voor DSC zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bb305-106">NOTE: By default only the Operational logs for DSC are enabled.</span></span>
<span data-ttu-id="bb305-107">Voordat het analytische logboek beschikbaar of zichtbaar is, moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="bb305-107">Before the Analytic log will be available or visible, it must be enabled.</span></span>
<span data-ttu-id="bb305-108">Zie het volgende artikel.</span><span class="sxs-lookup"><span data-stu-id="bb305-108">See the following article.</span></span>

[<span data-ttu-id="bb305-109">Waar zijn de gebeurtenislogboeken DSC?</span><span class="sxs-lookup"><span data-stu-id="bb305-109">Where are DSC Event Logs?</span></span>](https://msdn.microsoft.com/en-us/powershell/dsc/troubleshooting#where-are-dsc-event-logs)

## <a name="properties"></a><span data-ttu-id="bb305-110">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="bb305-110">Properties</span></span>
|  <span data-ttu-id="bb305-111">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="bb305-111">Property</span></span>  |  <span data-ttu-id="bb305-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bb305-112">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="bb305-113">Bericht</span><span class="sxs-lookup"><span data-stu-id="bb305-113">Message</span></span>| <span data-ttu-id="bb305-114">Hiermee geeft u het bericht dat u wilt schrijven naar het gebeurtenislogboek Microsoft-Windows-Desired status Configuration/analysen.</span><span class="sxs-lookup"><span data-stu-id="bb305-114">Indicates the message you want to write to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>| 
| <span data-ttu-id="bb305-115">dependsOn</span><span class="sxs-lookup"><span data-stu-id="bb305-115">DependsOn</span></span> | <span data-ttu-id="bb305-116">Geeft aan dat de configuratie van een andere resource moet worden uitgevoerd voordat dit logboekbericht wordt geschreven.</span><span class="sxs-lookup"><span data-stu-id="bb305-116">Indicates that the configuration of another resource must run before this log message gets written.</span></span> <span data-ttu-id="bb305-117">Bijvoorbeeld, als de ID van de resourceconfiguratie scriptblok die u wilt uitvoeren eerst is __ResourceName__ en het type __ResourceType__, de syntaxis voor het gebruik van deze eigenschap is `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="bb305-117">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 

## <a name="example"></a><span data-ttu-id="bb305-118">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="bb305-118">Example</span></span>

<span data-ttu-id="bb305-119">Het volgende voorbeeld laat zien hoe een bericht in het gebeurtenislogboek Microsoft-Windows-Desired status Configuration/analysen opnemen.</span><span class="sxs-lookup"><span data-stu-id="bb305-119">The following example shows how to include a message in the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

> <span data-ttu-id="bb305-120">**Opmerking**: als u [Test DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) aan deze resource is geconfigureerd, wordt altijd geretourneerd **$false**.</span><span class="sxs-lookup"><span data-stu-id="bb305-120">**Note**: if you run [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) with this resource configured, it will always return **$false**.</span></span>

```powershell 
Configuration logResourceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node localhost

    {
        Log LogExample
        {
            Message = "This message will appear in the Microsoft-Windows-Desired State Configuration/Analytic event log."
        }
    }
}
```
