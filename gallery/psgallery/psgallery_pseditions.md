---
ms.date: 2017-06-12
contributor: JKeithB
ms.topic: conceptual
keywords: Galerie, powershell, cmdlet, psgallery
title: psgallery_pseditions
ms.openlocfilehash: 6634da5c2dadee9c0c6470b3d3e8883e6d02160f
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="items-with-compatible-powershell-editions"></a><span data-ttu-id="1fcdb-103">Items met compatibel PowerShell-edities</span><span class="sxs-lookup"><span data-stu-id="1fcdb-103">Items with compatible PowerShell Editions</span></span>
<span data-ttu-id="1fcdb-104">Vanaf versie 5.1 is PowerShell beschikbaar in verschillende edities die staan voor verschillende functies en platformcompatibiliteit.</span><span class="sxs-lookup"><span data-stu-id="1fcdb-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="1fcdb-105">**Desktop-editie:** deze editie is gebaseerd op .NET Framework en biedt compatibiliteit met scripts en modules die zijn gericht op versies van PowerShell die worden uitgevoerd op edities van Windows met een volledige footprint zoals Server Core en Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="1fcdb-105">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="1fcdb-106">**Core-editie:** deze editie is gebaseerd op .NET Framework en biedt compatibiliteit met scripts en modules die zijn gericht op versies van PowerShell die worden uitgevoerd op edities van Windows met een verminderde footprint zoals Nano Server en Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="1fcdb-106">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

## <a name="powershell-gallery-extracts-supported-pseditions-metadata-and-allows-you-to-filters-the-items-compatible-for-specific-powershell-editions"></a><span data-ttu-id="1fcdb-107">PowerShell Gallery extraheert ondersteunde PSEditions metagegevens en kunt u filters de items compatibel voor specifieke PowerShell-edities</span><span class="sxs-lookup"><span data-stu-id="1fcdb-107">PowerShell Gallery extracts supported PSEditions metadata and allows you to filters the items compatible for specific PowerShell Editions</span></span>

<span data-ttu-id="1fcdb-108">Als een artikel heeft compatibel PSEditions opgegeven, worden deze weergegeven als onderdeel van PowerShell-edities in de pagina item weergeven en ook in de resultaten van de items.</span><span class="sxs-lookup"><span data-stu-id="1fcdb-108">If an item has compatible PSEditions specified, they will be listed as part of 'PowerShell Editions' in the item display page and also in items results.</span></span>
<span data-ttu-id="1fcdb-109">![Pagina van de item weergeven met PSEditions](Images/ItemDisplayPageWithPSEditions.PNG)</span><span class="sxs-lookup"><span data-stu-id="1fcdb-109">![Item display page with PSEditions](Images/ItemDisplayPageWithPSEditions.PNG)</span></span>

## <a name="search-for-items-in-the-gallery-ui-which-works-on-powershellcore"></a><span data-ttu-id="1fcdb-110">Zoeken naar items in de gebruikersinterface die op PowerShellCore werkt-galerie</span><span class="sxs-lookup"><span data-stu-id="1fcdb-110">Search for items in the gallery UI which works on PowerShellCore</span></span>
<span data-ttu-id="1fcdb-111">Codes gebruiken: Tags en 'PSEdition_Desktop': 'PSEdition_Core' met filters voor de items in PowerShell Gallery.</span><span class="sxs-lookup"><span data-stu-id="1fcdb-111">Use Tags:"PSEdition_Desktop" and Tags:"PSEdition_Core" to filters the items on PowerShell Gallery.</span></span>

### <a name="use-tagspseditioncore-to-search-items-compatible-with-powershell-core-edition"></a><span data-ttu-id="1fcdb-112">Codes gebruiken: 'PSEdition_Core' om te zoeken items compatibel met PowerShell Core Edition.</span><span class="sxs-lookup"><span data-stu-id="1fcdb-112">Use Tags:"PSEdition_Core" to search items compatible with PowerShell Core Edition.</span></span>
![Zoekresultaten voor objecten die compatibel is met Core PSEdition](Images/SearchResultsWithPSEditions.PNG)

### <a name="use-tagspseditiondesktop-to-search-items-compatible-with-powershell-desktop-edition"></a><span data-ttu-id="1fcdb-114">Codes gebruiken: 'PSEdition_Desktop' om te zoeken items die compatibel is met PowerShell Desktop Edition.</span><span class="sxs-lookup"><span data-stu-id="1fcdb-114">Use Tags:"PSEdition_Desktop" to search items compatible with PowerShell Desktop Edition.</span></span>
![Zoekresultaten voor objecten die compatibel is met het bureaublad PSEdition](Images/SearchResultsWithPSEdition_Desktop.PNG)

## <a name="more-details-on-authoring-and-finding-the-items-with-compatible-powershell-editions"></a><span data-ttu-id="1fcdb-116">Meer informatie over het ontwerpen en zoeken van de items met compatibel PowerShell-edities</span><span class="sxs-lookup"><span data-stu-id="1fcdb-116">More details on authoring and finding the items with compatible PowerShell Editions</span></span>
### <a name="modules-with-pseditionspsgetmodulemodulewithpseditionsupportmd"></a>[<span data-ttu-id="1fcdb-117">Modules met PSEditions</span><span class="sxs-lookup"><span data-stu-id="1fcdb-117">Modules with PSEditions</span></span>](../psget/module/modulewithpseditionsupport.md)
### <a name="scripts-with-pseditionspsgetscriptscriptwithpseditionsupportmd"></a>[<span data-ttu-id="1fcdb-118">Scripts met PSEditions</span><span class="sxs-lookup"><span data-stu-id="1fcdb-118">Scripts with PSEditions</span></span>](../psget/script/scriptwithpseditionsupport.md)
