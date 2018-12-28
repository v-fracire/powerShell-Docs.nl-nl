---
ms.date: 06/05/2017
keywords: PowerShell-cmdlet
title: Bijlage 1 - Compatibiliteitsaliassen
ms.assetid: 96ad921e-1a57-463e-8e60-424faf8b6ef8
ms.openlocfilehash: 113bbee1af185f98777df5767022d54accb69447
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2018
ms.locfileid: "53404598"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="9929a-103">Bijlage 1 - Compatibiliteitsaliassen</span><span class="sxs-lookup"><span data-stu-id="9929a-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="9929a-104">Windows PowerShell heeft verschillende overgang aliassen die UNIX- en Cmd gebruikers bekende opdrachtnamen gebruiken in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9929a-104">Windows PowerShell has several transition aliases that allow UNIX and Cmd users to use familiar command names in Windows PowerShell.</span></span> <span data-ttu-id="9929a-105">De meest voorkomende aliassen worden weergegeven in de onderstaande tabel, samen met de Windows PowerShell-opdracht achter de alias en de standaard Windows PowerShell-alias als er een bestaat.</span><span class="sxs-lookup"><span data-stu-id="9929a-105">The most common aliases are shown in the table below, along with the Windows PowerShell command behind the alias and the standard Windows PowerShell alias if one exists.</span></span>

<span data-ttu-id="9929a-106">Hier vindt u de Windows PowerShell-opdracht die een alias verwijst naar uit in Windows PowerShell met de cmdlet Get-Alias.</span><span class="sxs-lookup"><span data-stu-id="9929a-106">You can find the Windows PowerShell command that any alias points to from within Windows PowerShell by using the Get-Alias cmdlet.</span></span> <span data-ttu-id="9929a-107">Typ bijvoorbeeld **get-alias cls**.</span><span class="sxs-lookup"><span data-stu-id="9929a-107">For example, type **get-alias cls**.</span></span>

```
CommandType     Name                            Definition
-----------     ----                            ----------
Alias           cls                             Clear-Host
```

|<span data-ttu-id="9929a-108">Opdracht CMD</span><span class="sxs-lookup"><span data-stu-id="9929a-108">CMD Command</span></span>|<span data-ttu-id="9929a-109">UNIX-opdracht</span><span class="sxs-lookup"><span data-stu-id="9929a-109">UNIX Command</span></span>|<span data-ttu-id="9929a-110">PS-Opdracht</span><span class="sxs-lookup"><span data-stu-id="9929a-110">PS Command</span></span>|<span data-ttu-id="9929a-111">PS Alias</span><span class="sxs-lookup"><span data-stu-id="9929a-111">PS Alias</span></span>|
|---------------|----------------|--------------|------------|
|<span data-ttu-id="9929a-112">**dir**</span><span class="sxs-lookup"><span data-stu-id="9929a-112">**dir**</span></span>|<span data-ttu-id="9929a-113">**Ls**</span><span class="sxs-lookup"><span data-stu-id="9929a-113">**ls**</span></span>|<span data-ttu-id="9929a-114">**Get-ChildItem**</span><span class="sxs-lookup"><span data-stu-id="9929a-114">**Get-ChildItem**</span></span>|<span data-ttu-id="9929a-115">**GCI**</span><span class="sxs-lookup"><span data-stu-id="9929a-115">**gci**</span></span>|
|<span data-ttu-id="9929a-116">**CLS**</span><span class="sxs-lookup"><span data-stu-id="9929a-116">**cls**</span></span>|<span data-ttu-id="9929a-117">**Wissen**</span><span class="sxs-lookup"><span data-stu-id="9929a-117">**clear**</span></span>|<span data-ttu-id="9929a-118">**Clear-Host** (functie)</span><span class="sxs-lookup"><span data-stu-id="9929a-118">**Clear-Host** (function)</span></span>|<span data-ttu-id="9929a-119">**CLS**</span><span class="sxs-lookup"><span data-stu-id="9929a-119">**cls**</span></span>|
|<span data-ttu-id="9929a-120">**DEL, wissen, rmdir**</span><span class="sxs-lookup"><span data-stu-id="9929a-120">**del, erase, rmdir**</span></span>|<span data-ttu-id="9929a-121">**RM**</span><span class="sxs-lookup"><span data-stu-id="9929a-121">**rm**</span></span>|<span data-ttu-id="9929a-122">**Item verwijderen**</span><span class="sxs-lookup"><span data-stu-id="9929a-122">**Remove-Item**</span></span>|<span data-ttu-id="9929a-123">**gereserveerde instanties**</span><span class="sxs-lookup"><span data-stu-id="9929a-123">**ri**</span></span>|
|<span data-ttu-id="9929a-124">**Kopiëren**</span><span class="sxs-lookup"><span data-stu-id="9929a-124">**copy**</span></span>|<span data-ttu-id="9929a-125">**CP**</span><span class="sxs-lookup"><span data-stu-id="9929a-125">**cp**</span></span>|<span data-ttu-id="9929a-126">**Copy-Item**</span><span class="sxs-lookup"><span data-stu-id="9929a-126">**Copy-Item**</span></span>|<span data-ttu-id="9929a-127">**CI**</span><span class="sxs-lookup"><span data-stu-id="9929a-127">**ci**</span></span>|
|<span data-ttu-id="9929a-128">**verplaatsen**</span><span class="sxs-lookup"><span data-stu-id="9929a-128">**move**</span></span>|<span data-ttu-id="9929a-129">**MV**</span><span class="sxs-lookup"><span data-stu-id="9929a-129">**mv**</span></span>|<span data-ttu-id="9929a-130">**Item verplaatsen**</span><span class="sxs-lookup"><span data-stu-id="9929a-130">**Move-Item**</span></span>|<span data-ttu-id="9929a-131">**MI**</span><span class="sxs-lookup"><span data-stu-id="9929a-131">**mi**</span></span>|
|<span data-ttu-id="9929a-132">**Wijzig de naam**</span><span class="sxs-lookup"><span data-stu-id="9929a-132">**rename**</span></span>|<span data-ttu-id="9929a-133">**MV**</span><span class="sxs-lookup"><span data-stu-id="9929a-133">**mv**</span></span>|<span data-ttu-id="9929a-134">**Rename-Item**</span><span class="sxs-lookup"><span data-stu-id="9929a-134">**Rename-Item**</span></span>|<span data-ttu-id="9929a-135">**rni**</span><span class="sxs-lookup"><span data-stu-id="9929a-135">**rni**</span></span>|
|<span data-ttu-id="9929a-136">**Type**</span><span class="sxs-lookup"><span data-stu-id="9929a-136">**type**</span></span>|<span data-ttu-id="9929a-137">**CAT**</span><span class="sxs-lookup"><span data-stu-id="9929a-137">**cat**</span></span>|<span data-ttu-id="9929a-138">**Get-inhoud**</span><span class="sxs-lookup"><span data-stu-id="9929a-138">**Get-Content**</span></span>|<span data-ttu-id="9929a-139">**GC-exemplaar**</span><span class="sxs-lookup"><span data-stu-id="9929a-139">**gc**</span></span>|
|<span data-ttu-id="9929a-140">**cd**</span><span class="sxs-lookup"><span data-stu-id="9929a-140">**cd**</span></span>|<span data-ttu-id="9929a-141">**cd**</span><span class="sxs-lookup"><span data-stu-id="9929a-141">**cd**</span></span>|<span data-ttu-id="9929a-142">**Locatie instellen**</span><span class="sxs-lookup"><span data-stu-id="9929a-142">**Set-Location**</span></span>|<span data-ttu-id="9929a-143">**SL**</span><span class="sxs-lookup"><span data-stu-id="9929a-143">**sl**</span></span>|
|<span data-ttu-id="9929a-144">**MD**</span><span class="sxs-lookup"><span data-stu-id="9929a-144">**md**</span></span>|<span data-ttu-id="9929a-145">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="9929a-145">**mkdir**</span></span>|<span data-ttu-id="9929a-146">**Nieuw Item**</span><span class="sxs-lookup"><span data-stu-id="9929a-146">**New-Item**</span></span>|<span data-ttu-id="9929a-147">**Ni**</span><span class="sxs-lookup"><span data-stu-id="9929a-147">**ni**</span></span>|
|<span data-ttu-id="9929a-148">**pushd**</span><span class="sxs-lookup"><span data-stu-id="9929a-148">**pushd**</span></span>|<span data-ttu-id="9929a-149">**pushd**</span><span class="sxs-lookup"><span data-stu-id="9929a-149">**pushd**</span></span>|<span data-ttu-id="9929a-150">**Push-locatie**</span><span class="sxs-lookup"><span data-stu-id="9929a-150">**Push-Location**</span></span>|<span data-ttu-id="9929a-151">**pushd**</span><span class="sxs-lookup"><span data-stu-id="9929a-151">**pushd**</span></span>|
|<span data-ttu-id="9929a-152">**popd**</span><span class="sxs-lookup"><span data-stu-id="9929a-152">**popd**</span></span>|<span data-ttu-id="9929a-153">**popd**</span><span class="sxs-lookup"><span data-stu-id="9929a-153">**popd**</span></span>|<span data-ttu-id="9929a-154">**Pop-locatie**</span><span class="sxs-lookup"><span data-stu-id="9929a-154">**Pop-Location**</span></span>|<span data-ttu-id="9929a-155">**popd**</span><span class="sxs-lookup"><span data-stu-id="9929a-155">**popd**</span></span>|