---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: WMF, powershell, setup
title: PowerShell-Engine verbeteringen in WMF 5.1
ms.openlocfilehash: 6c8000ccfc59ab46de95dc4f67161e12a5a41199
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
#<a name="powershell-engine-improvements"></a><span data-ttu-id="f0043-103">Verbeteringen van de PowerShell-Engine</span><span class="sxs-lookup"><span data-stu-id="f0043-103">PowerShell Engine Improvements</span></span>

<span data-ttu-id="f0043-104">De volgende verbeteringen aangebracht in de kern PowerShell-engine in WMF 5.1 geïmplementeerd:</span><span class="sxs-lookup"><span data-stu-id="f0043-104">The following improvements to the core PowerShell engine have been implemented in WMF 5.1:</span></span>


## <a name="performance"></a><span data-ttu-id="f0043-105">Prestaties</span><span class="sxs-lookup"><span data-stu-id="f0043-105">Performance</span></span> ##

<span data-ttu-id="f0043-106">Prestaties verbeterd in enkele belangrijke gebieden:</span><span class="sxs-lookup"><span data-stu-id="f0043-106">Performance has improved in some important areas:</span></span>

- <span data-ttu-id="f0043-107">Opstarten</span><span class="sxs-lookup"><span data-stu-id="f0043-107">Startup</span></span>
- <span data-ttu-id="f0043-108">Pipelining naar cmdlets zoals ForEach-Object en Where-Object is ongeveer 50% sneller</span><span class="sxs-lookup"><span data-stu-id="f0043-108">Pipelining to cmdlets like ForEach-Object and Where-Object is approximately 50% faster</span></span> 

<span data-ttu-id="f0043-109">Enkele voorbeeld-verbeteringen (uw resultaten kunnen variëren, afhankelijk van uw hardware):</span><span class="sxs-lookup"><span data-stu-id="f0043-109">Some example improvements (your results may vary depending on your hardware):</span></span> 

| <span data-ttu-id="f0043-110">Scenario</span><span class="sxs-lookup"><span data-stu-id="f0043-110">Scenario</span></span> | <span data-ttu-id="f0043-111">5.0-tijd (ms)</span><span class="sxs-lookup"><span data-stu-id="f0043-111">5.0 Time (ms)</span></span> | <span data-ttu-id="f0043-112">5.1-tijd (ms)</span><span class="sxs-lookup"><span data-stu-id="f0043-112">5.1 Time (ms)</span></span> |
| -------- | :---------------: | :---------------: |
| `powershell -command "echo 1"` | <span data-ttu-id="f0043-113">900</span><span class="sxs-lookup"><span data-stu-id="f0043-113">900</span></span> | <span data-ttu-id="f0043-114">250</span><span class="sxs-lookup"><span data-stu-id="f0043-114">250</span></span> |
| <span data-ttu-id="f0043-115">Eerste ooit PowerShell uitvoeren:`powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="f0043-115">First ever PowerShell run: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="f0043-116">30000</span><span class="sxs-lookup"><span data-stu-id="f0043-116">30000</span></span> | <span data-ttu-id="f0043-117">13000</span><span class="sxs-lookup"><span data-stu-id="f0043-117">13000</span></span> |
| <span data-ttu-id="f0043-118">Opdracht analysis-cache is gebouwd:`powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="f0043-118">Command analysis cache built: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="f0043-119">7000</span><span class="sxs-lookup"><span data-stu-id="f0043-119">7000</span></span> | <span data-ttu-id="f0043-120">520</span><span class="sxs-lookup"><span data-stu-id="f0043-120">520</span></span> |
| <code>1..1000000 &#124; % { }</code> | <span data-ttu-id="f0043-121">1400</span><span class="sxs-lookup"><span data-stu-id="f0043-121">1400</span></span> | <span data-ttu-id="f0043-122">750</span><span class="sxs-lookup"><span data-stu-id="f0043-122">750</span></span> |
  
> <span data-ttu-id="f0043-123">Opmerking één wijziging betrekking hebben op het starten van de mogelijk gevolgen hebben voor een aantal niet-ondersteunde scenario's.</span><span class="sxs-lookup"><span data-stu-id="f0043-123">Note One change related to startup might impact some unsupported scenarios.</span></span> 
> <span data-ttu-id="f0043-124">De bestanden niet meer worden gelezen door PowerShell `$pshome\*.ps1xml` --deze bestanden zijn geconverteerd naar C# om te voorkomen dat een bestand en CPU-overhead van de verwerking van de XML-bestanden.</span><span class="sxs-lookup"><span data-stu-id="f0043-124">PowerShell no longer reads the files `$pshome\*.ps1xml` -- these files have been converted to C# to avoid some file and CPU overhead of processing the XML files.</span></span> 
<span data-ttu-id="f0043-125">De bestanden nog steeds aanwezig voor ondersteuning van V2 side-by-side, dus als u de inhoud van het bestand wijzigt, heeft deze geen effect op V5, alleen V2.</span><span class="sxs-lookup"><span data-stu-id="f0043-125">The files still exist to support V2 side-by-side, so if you change the file contents, it will not have any effect to V5, only V2.</span></span> 
<span data-ttu-id="f0043-126">Houd er rekening mee dat de inhoud van deze bestanden wijzigen nooit een ondersteund scenario is.</span><span class="sxs-lookup"><span data-stu-id="f0043-126">Note that changing the contents of these files was never a supported scenario.</span></span>

<span data-ttu-id="f0043-127">Een andere zichtbare wijzigingen is hoe PowerShell slaat de geëxporteerde opdrachten en andere informatie voor modules die zijn geïnstalleerd op een systeem.</span><span class="sxs-lookup"><span data-stu-id="f0043-127">Another visible change is how PowerShell caches the exported commands and other information for modules that are installed on a system.</span></span> <span data-ttu-id="f0043-128">Voorheen werd door deze cache is opgeslagen in de map `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span><span class="sxs-lookup"><span data-stu-id="f0043-128">Previously, this cache was stored in the directory `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span></span> <span data-ttu-id="f0043-129">In WMF 5.1, de cache is een enkel bestand `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="f0043-129">In WMF 5.1, the cache is a single file `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span>
<span data-ttu-id="f0043-130">Zie [Module Analysis Cache](scenarios-features.md#module-analysis-cache) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f0043-130">See [Module Analysis Cache](scenarios-features.md#module-analysis-cache) for more details.</span></span>
