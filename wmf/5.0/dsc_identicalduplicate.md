---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: WMF, powershell, setup
ms.openlocfilehash: d3a625d05eaf4e7448b4abf90499f6a94e2f7718
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="allowing-for-identical-duplicate-resources-in-a-configuration"></a><span data-ttu-id="0c696-102">Identieke dubbele Resources in een configuratie toestaan</span><span class="sxs-lookup"><span data-stu-id="0c696-102">Allowing for Identical Duplicate Resources in a Configuration</span></span>

<span data-ttu-id="0c696-103">DSC niet toestaan of conflicterende resourcedefinities binnen een configuratie verwerkt.</span><span class="sxs-lookup"><span data-stu-id="0c696-103">DSC does not allow or handle conflicting resource definitions within a configuration.</span></span> <span data-ttu-id="0c696-104">In plaats van het conflict op te lossen, gewoon is mislukt.</span><span class="sxs-lookup"><span data-stu-id="0c696-104">Instead of trying to resolve the conflict, it simply fails.</span></span> <span data-ttu-id="0c696-105">Als het hergebruik van de configuratie wordt meer door samengestelde bronnen worden gebruikt, wordt vaker enzovoort conflicten optreden.</span><span class="sxs-lookup"><span data-stu-id="0c696-105">As configuration reuse becomes more utilized through composite resources, etc. conflicts will occur more often.</span></span> <span data-ttu-id="0c696-106">Wanneer u conflicterende resourcedefinities identiek zijn, moet DSC smart en dit toestaan.</span><span class="sxs-lookup"><span data-stu-id="0c696-106">When conflicting resource definitions are identical, DSC should be smart and allow this.</span></span> <span data-ttu-id="0c696-107">Met deze release ondersteuning wordt voor meerdere resource-exemplaren die identiek zijn gedefinieerd:</span><span class="sxs-lookup"><span data-stu-id="0c696-107">With this release, we support having multiple resource instances that have identical definitions:</span></span>

```powershell
Configuration IIS_FrontEnd
{
    WindowsFeature FE_IIS         #Identical resource
    {
        Ensure = 'Present'
        Name = 'Web-Server'
    }

    WindowsFeature FTP
    {
        Ensure = 'Present'
        Name = 'Web-FTP-Server'
    }
}

Configuration IIS_Worker
{
    WindowsFeature Worker_IIS      #Identical resource
    {
        Ensure = 'Present'
        Name = 'Web-Server'
    }

    WindowsFeature ASP
    {
        Ensure = 'Present'
        Name = 'Web-ASP-Net45'
    }
}

Configuration WebApplication
{
    IIS_Frontend Web {}

    IIS_Worker ASP {}
}
```

<span data-ttu-id="0c696-108">In eerdere versies is het resultaat een compilatie is mislukt vanwege een conflict tussen de WindowsFeature FE_IIS en WindowsFeature Worker_IIS exemplaren probeert om te controleren of de rol 'Webserver' is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="0c696-108">In previous releases, the result would be a failed compilation due to a conflict between the WindowsFeature FE_IIS and WindowsFeature Worker_IIS instances trying to ensure the 'Web-Server' role is installed.</span></span> <span data-ttu-id="0c696-109">U ziet dat *alle* van de eigenschappen die worden geconfigureerd in deze twee configuraties identiek zijn.</span><span class="sxs-lookup"><span data-stu-id="0c696-109">Notice that *all* of the properties that are being configured are identical in these two configurations.</span></span> <span data-ttu-id="0c696-110">Aangezien *alle* van de eigenschappen in deze twee bronnen identiek zijn, resulteert dit in een geslaagde compilatie nu.</span><span class="sxs-lookup"><span data-stu-id="0c696-110">Since *all* of the properties in these two resources are identical, this will result in a successful compilation now.</span></span> 

<span data-ttu-id="0c696-111">Als een van de eigenschappen van verschillen tussen de twee bronnen, worden deze niet gezien identiek en compilatie mislukt:</span><span class="sxs-lookup"><span data-stu-id="0c696-111">If any of the properties are different between the two resources, they will not be considered identical and compilation will fail:</span></span>

```powershell
Configuration IIS_FrontEnd
{
    WindowsFeature FE_IIS
    {
        Ensure = 'Present'     # Ensure is Present here
        Name = 'Web-Server'
    }

    WindowsFeature FTP
    {
        Ensure = 'Present'
        Name = 'Web-FTP-Server'
    }
}

Configuration IIS_Worker
{
    WindowsFeature Worker_IIS
    {
        Ensure = 'Absent'      # Ensure property is Absent instead of Present
        Name = 'Web-Server'
    }

    WindowsFeature ASP
    {
        Ensure = 'Present'
        Name = 'Web-ASP-Net45'
    }
}

Configuration WebApplication
{
    IIS_Frontend Web {}

    IIS_Worker ASP {}
}
```

<span data-ttu-id="0c696-112">Deze configuratie vergelijkbaar mislukken omdat de WindowsFeature FE_IIS en WindowsFeature Worker_IIS resources niet langer identiek zijn en daarom in strijd.</span><span class="sxs-lookup"><span data-stu-id="0c696-112">This very similar configuration will fail because the WindowsFeature FE_IIS and the WindowsFeature Worker_IIS resources are no longer identical and therefore conflict.</span></span>
