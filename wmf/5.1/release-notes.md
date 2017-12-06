---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: WMF, powershell, setup
title: WMF 5.1 Release-opmerkingen
ms.openlocfilehash: ce9bc7791facfcc2cce9468689e88a26154bda7d
ms.sourcegitcommit: 3f49bd2e0b786e69c71393c00ad85d05a8466753
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2017
---
# <a name="windows-management-framework-wmf-51-release-notes"></a><span data-ttu-id="c1f56-103">Windows Management Framework (WMF) 5.1 Release-opmerkingen</span><span class="sxs-lookup"><span data-stu-id="c1f56-103">Windows Management Framework (WMF) 5.1 Release Notes</span></span> #

<span data-ttu-id="c1f56-104">WMF 5.1 bevat de onderdelen die PowerShell, WMI, WinRM en Software Inventory Logging (SIL) die zijn uitgebracht met Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="c1f56-104">WMF 5.1 includes the PowerShell, WMI, WinRM, and Software Inventory Logging (SIL) components that were released with Windows Server 2016.</span></span>
<span data-ttu-id="c1f56-105">WMF 5.1 kan worden geïnstalleerd op Windows 7, Windows 8.1, Windows Server 2008 R2, 2012 en 2012 R2, en biedt een aantal verbeteringen ten opzichte van WMF 5.0 RTM inclusief:</span><span class="sxs-lookup"><span data-stu-id="c1f56-105">WMF 5.1 can be installed on Windows 7, Windows 8.1, Windows Server 2008 R2, 2012, and 2012 R2, and provides a number of improvements over WMF 5.0 RTM including:</span></span>

- <span data-ttu-id="c1f56-106">Nieuwe cmdlets: lokale gebruikers en groepen; Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="c1f56-106">New cmdlets: local users and groups; Get-ComputerInfo</span></span>
- <span data-ttu-id="c1f56-107">PowerShellGet verbeteringen bestaan onder andere het afdwingen van ondertekende modules en JEA modules installeren</span><span class="sxs-lookup"><span data-stu-id="c1f56-107">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="c1f56-108">PackageManagement is ondersteuning toegevoegd voor Containers CBS Setup EXE installatie CAB-pakketten</span><span class="sxs-lookup"><span data-stu-id="c1f56-108">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="c1f56-109">Verbeteringen voor klassen DSC en PowerShell foutopsporing</span><span class="sxs-lookup"><span data-stu-id="c1f56-109">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="c1f56-110">Beveiligingsverbeteringen, inclusief de handhaving van catalogus ondertekend modules dat afkomstig is van de Pull-Server en wanneer u PowerShellGet-cmdlets</span><span class="sxs-lookup"><span data-stu-id="c1f56-110">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="c1f56-111">Antwoorden op een aantal gebruikersaanvragen en problemen</span><span class="sxs-lookup"><span data-stu-id="c1f56-111">Responses to a number of user requests and issues</span></span>

<span data-ttu-id="c1f56-112">**Belangrijke opmerkingen:**</span><span class="sxs-lookup"><span data-stu-id="c1f56-112">**Important notes:**</span></span>

- <span data-ttu-id="c1f56-113">**WMF 5.1 vereist .NET Framework 4.5.2** (of hoger).</span><span class="sxs-lookup"><span data-stu-id="c1f56-113">**WMF 5.1 requires the .NET Framework 4.5.2** (or above).</span></span> <span data-ttu-id="c1f56-114">Installatie wordt voltooid, maar de belangrijkste functies mislukken als .NET 4.5.2 (of hoger) is niet geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="c1f56-114">Installation will succeed, but key features will fail if .NET 4.5.2 (or above) is not installed.</span></span> <span data-ttu-id="c1f56-115">Instructies zijn beschikbaar in de [installeren en configureren van WMF 5.1 ](https://msdn.microsoft.com/en-us/powershell/wmf/5.1/install-configure) onderwerp.</span><span class="sxs-lookup"><span data-stu-id="c1f56-115">Instructions are available in the [Install and Configure WMF 5.1 ](https://msdn.microsoft.com/en-us/powershell/wmf/5.1/install-configure) topic.</span></span>
- <span data-ttu-id="c1f56-116">WMF 5.1 Preview moet worden verwijderd voordat het installeren van WMF 5.1 RTM.</span><span class="sxs-lookup"><span data-stu-id="c1f56-116">WMF 5.1 Preview must be uninstalled before installing WMF 5.1 RTM.</span></span>
- <span data-ttu-id="c1f56-117">WMF 5.1 kan rechtstreeks via WMF 5.0 of WMF 4.0 worden geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="c1f56-117">WMF 5.1 may be installed directly over WMF 5.0 or WMF 4.0.</span></span>
- <span data-ttu-id="c1f56-118">Het is __niet vereist__ WMF 4.0 installeren voordat u WMF 5.1 op Windows 7 en Windows Server 2008 R2 installeert.</span><span class="sxs-lookup"><span data-stu-id="c1f56-118">It is __not required__ to install WMF 4.0 prior to installing WMF 5.1 on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="c1f56-119">Die was een probleem voor de evaluatieversie van WMF 5.1 en opgelost.</span><span class="sxs-lookup"><span data-stu-id="c1f56-119">That was an issue for the WMF 5.1 Preview release, and has been resolved.</span></span>  

