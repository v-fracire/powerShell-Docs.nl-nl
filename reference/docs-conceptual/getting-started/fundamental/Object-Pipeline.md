---
ms.date: 2017-06-05
keywords: PowerShell-cmdlet
title: Object-Pipeline
ms.assetid: 523d8ae4-d743-47a4-b79a-806130ca688a
ms.openlocfilehash: 3fa41cc744cf3ab66fc5ef186ead8eb919429a76
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="object-pipeline"></a><span data-ttu-id="e9a08-103">Object-Pipeline</span><span class="sxs-lookup"><span data-stu-id="e9a08-103">Object Pipeline</span></span>
<span data-ttu-id="e9a08-104">Pijplijnen fungeren als een reeks verbonden segmenten van de pipe.</span><span class="sxs-lookup"><span data-stu-id="e9a08-104">Pipelines act like a series of connected segments of pipe.</span></span> <span data-ttu-id="e9a08-105">Items verplaatst langs de pijplijn is doorlaten van elk segment.</span><span class="sxs-lookup"><span data-stu-id="e9a08-105">Items moving along the pipeline pass through each segment.</span></span> <span data-ttu-id="e9a08-106">Voor het maken van een pijplijn in Windows PowerShell, u verbinding maakt opdrachten samen met de pipe-operator ' | '.</span><span class="sxs-lookup"><span data-stu-id="e9a08-106">To create a pipeline in Windows PowerShell, you connect commands together with the pipe operator "|".</span></span> <span data-ttu-id="e9a08-107">De uitvoer van elke opdracht wordt gebruikt als invoer voor de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="e9a08-107">The output of each command is used as input to the next command.</span></span>

<span data-ttu-id="e9a08-108">Pijplijnen zijn weliswaar het meest waardevolle concept gebruikt in opdrachtregelinterfaces.</span><span class="sxs-lookup"><span data-stu-id="e9a08-108">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="e9a08-109">Juist gebruik, pijplijnen niet alleen minder moeite hoeven die zijn betrokken bij het invoeren van complexe opdrachten, maar ook gemakkelijker om te zien van de werkstroom in de opdrachten.</span><span class="sxs-lookup"><span data-stu-id="e9a08-109">Properly used, pipelines not only reduce the effort involved in entering complex commands, but also make it easier to see the flow of work in the commands.</span></span> <span data-ttu-id="e9a08-110">Een gerelateerde nuttig kenmerk van pijplijnen is of omdat deze afzonderlijk op elk item werken, er geen wijzigen op basis van of u nul, een of veel items in de pijplijn moet.</span><span class="sxs-lookup"><span data-stu-id="e9a08-110">A related useful characteristic of pipelines is that because they operate on each item separately, you do not have to modify them based on whether you will have zero, one, or many items in the pipeline.</span></span> <span data-ttu-id="e9a08-111">Bovendien elke opdracht in een pijplijn (een pipeline-element genoemd) wordt de uitvoer meestal doorgegeven aan de volgende opdracht in de pipeline-per-item.</span><span class="sxs-lookup"><span data-stu-id="e9a08-111">Furthermore, each command in a pipeline (called a pipeline element) usually passes its output to the next command in the pipeline item-by-item.</span></span> <span data-ttu-id="e9a08-112">Dit meestal vermindert de behoefte aan bronnen van complexe opdrachten en kunt u beginnen onmiddellijk ophalen van de uitvoer.</span><span class="sxs-lookup"><span data-stu-id="e9a08-112">This usually reduces the resource demand of complex commands and allows you to begin getting the output immediately.</span></span>

<span data-ttu-id="e9a08-113">In dit hoofdstuk we beschrijven hoe de Windows PowerShell-pijplijn verschilt van de pijplijnen van de meest populaire houders en vervolgens demonstreren sommige hulpmiddelen die u gebruiken kunt bij het besturingselement pijplijn uitvoer en om te zien hoe de pijplijn werkt.</span><span class="sxs-lookup"><span data-stu-id="e9a08-113">In this chapter, we will describe how the Windows PowerShell pipeline differs from the pipelines of most popular shells, and then demonstrate some basic tools that you can use to help control pipeline output and also to see how the pipeline operates.</span></span>
