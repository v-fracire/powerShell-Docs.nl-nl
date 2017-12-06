---
ms.date: 2017-06-05
keywords: PowerShell-cmdlet
title: Doel van de Windows PowerShell ISE-objectmodel Scripting
ms.assetid: d176a131-ab0c-43ee-80c1-f824ab8e4a05
ms.openlocfilehash: 3256d8bff3885d266f0db6f52932e40c4beaf8b1
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2017
---
# <a name="purpose-of-the-windows-powershell-ise-scripting-object-model"></a><span data-ttu-id="9cf76-103">Doel van de Windows PowerShell ISE-objectmodel Scripting</span><span class="sxs-lookup"><span data-stu-id="9cf76-103">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>
  <span data-ttu-id="9cf76-104">Objecten zijn gekoppeld aan het formulier en de functie van Windows PowerShell Integrated Scripting Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="9cf76-104">Objects are associated with the form and function of Windows PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="9cf76-105">De objectverwijzing model biedt informatie over het lid eigenschappen en methoden die deze objecten beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="9cf76-105">The object model reference provides details about the member properties and methods that these objects expose.</span></span> <span data-ttu-id="9cf76-106">Voorbeelden zijn bedoeld om te zien hoe u scripts rechtstreeks toegang krijgen tot deze eigenschappen en methoden kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9cf76-106">Examples are provided to show how you can use scripts to directly access these methods and properties.</span></span> <span data-ttu-id="9cf76-107">Het uitvoeren van scripts objectmodel vergemakkelijkt het volgende bereik van taken.</span><span class="sxs-lookup"><span data-stu-id="9cf76-107">The scripting object model makes the following range of tasks easier.</span></span>

## <a name="customizing-the-appearance-of-windows-powershell-ise"></a><span data-ttu-id="9cf76-108">De vormgeving van Windows PowerShell ISE aanpassen</span><span class="sxs-lookup"><span data-stu-id="9cf76-108">Customizing the appearance of Windows PowerShell ISE</span></span>
 <span data-ttu-id="9cf76-109">Het objectmodel kunt u de, toepassingsinstellingen en opties wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9cf76-109">You can use the object model to modify the application settings and options.</span></span> <span data-ttu-id="9cf76-110">Bijvoorbeeld, kunt u deze aanpassen als volgt:</span><span class="sxs-lookup"><span data-stu-id="9cf76-110">For example, you can modify them as follows:</span></span>

- <span data-ttu-id="9cf76-111">U kunt de kleur van fouten, waarschuwingen, uitgebreide uitvoer wijzigen en foutopsporing levert.</span><span class="sxs-lookup"><span data-stu-id="9cf76-111">You can change the color of errors, warnings, verbose outputs, and debug outputs.</span></span>

- <span data-ttu-id="9cf76-112">U kunt ophalen of instellen van de achtergrondkleuren voor het opdrachtvenster, het deelvenster Uitvoer en het scriptvenster.</span><span class="sxs-lookup"><span data-stu-id="9cf76-112">You can get or set the background colors for the Command pane, the Output pane, and the Script pane.</span></span>

- <span data-ttu-id="9cf76-113">U kunt instellen dat de voorgrondkleur van het deelvenster Uitvoer.</span><span class="sxs-lookup"><span data-stu-id="9cf76-113">You can set the foreground color for the Output pane.</span></span>

- <span data-ttu-id="9cf76-114">U kunt de naam van het lettertype en de tekengrootte instellen voor Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="9cf76-114">You can set the font name and font size for Windows PowerShell ISE.</span></span>

- <span data-ttu-id="9cf76-115">U kunt waarschuwingen configureren.</span><span class="sxs-lookup"><span data-stu-id="9cf76-115">You can configure warnings.</span></span> <span data-ttu-id="9cf76-116">Deze instelling bevat waarschuwingen die zijn uitgegeven wanneer een bestand wordt geopend in meerdere tabbladen met PowerShell of als een script in het bestand wordt uitgevoerd voordat het bestand is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="9cf76-116">This setting includes warnings that are issued when a file is opened in multiple PowerShell tabs or when a script in the file is run before the file has been saved.</span></span>

- <span data-ttu-id="9cf76-117">U kunt schakelen tussen een weergave waarop het scriptvenster en het deelvenster Uitvoer side-by-side zijn en een weergave waarin het scriptvenster is boven op het deelvenster Uitvoer.</span><span class="sxs-lookup"><span data-stu-id="9cf76-117">You can switch between a view where the Script pane and the Output pane are side-by-side and a view where the Script pane is on top of the Output pane.</span></span> <span data-ttu-id="9cf76-118">U kunt het opdrachtvenster verankeren aan de onderkant of aan de bovenkant van het deelvenster Uitvoer.</span><span class="sxs-lookup"><span data-stu-id="9cf76-118">You can dock the Command pane to the bottom or the top of the Output pane.</span></span>

## <a name="enhancing-the-functionality-of-windows-powershell-ise"></a><span data-ttu-id="9cf76-119">Verbetering van de functionaliteit van Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="9cf76-119">Enhancing the functionality of Windows PowerShell ISE</span></span>
 <span data-ttu-id="9cf76-120">U kunt het objectmodel gebruiken voor het verbeteren van de functionaliteit van Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="9cf76-120">You can use the object model to enhance the functionality of Windows PowerShell ISE.</span></span> <span data-ttu-id="9cf76-121">U kunt bijvoorbeeld het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="9cf76-121">For example, you can:</span></span>

- <span data-ttu-id="9cf76-122">Toevoegen en wijzigen van het exemplaar van Windows PowerShell ISE zelf.</span><span class="sxs-lookup"><span data-stu-id="9cf76-122">Add and modify the instance of Windows PowerShell ISE itself.</span></span> <span data-ttu-id="9cf76-123">Bijvoorbeeld, om te wijzigen van de menu's, kunt u nieuwe menu-items toevoegen en de nieuwe menu-items worden toegewezen aan de scripts.</span><span class="sxs-lookup"><span data-stu-id="9cf76-123">For example, to change the menus, you can add new menu items and map the new menu items to scripts.</span></span>

- <span data-ttu-id="9cf76-124">Scripts maken die de taken die u uitvoeren kunt met behulp van de knoppen en menuopdrachten in Windows PowerShell ISE uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="9cf76-124">Create scripts that perform some of the tasks that you can perform by using the menu commands and buttons in Windows PowerShell ISE.</span></span> <span data-ttu-id="9cf76-125">Bijvoorbeeld, u kunt toevoegen, verwijderen of Selecteer een PowerShell-tabblad.</span><span class="sxs-lookup"><span data-stu-id="9cf76-125">For example, you can add, remove, or select a PowerShell tab.</span></span>

- <span data-ttu-id="9cf76-126">Aanvullende taken die kunnen worden uitgevoerd met behulp van menuopdrachten en knoppen.</span><span class="sxs-lookup"><span data-stu-id="9cf76-126">Complement tasks that can be performed by using menu commands and buttons.</span></span> <span data-ttu-id="9cf76-127">U kunt bijvoorbeeld een PowerShell-tabblad wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9cf76-127">For example, you can rename a PowerShell tab.</span></span>

- <span data-ttu-id="9cf76-128">Tekst buffers voor het opdrachtvenster, het deelvenster Uitvoer en het scriptvenster die gekoppeld aan een bestand zijn bewerken.</span><span class="sxs-lookup"><span data-stu-id="9cf76-128">Manipulate text buffers for the Command pane, the Output pane, and the Script pane that are associated with a file.</span></span> <span data-ttu-id="9cf76-129">U kunt bijvoorbeeld het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="9cf76-129">For example, you can:</span></span>

    -   <span data-ttu-id="9cf76-130">Ophalen of instellen van alle tekst.</span><span class="sxs-lookup"><span data-stu-id="9cf76-130">Get or set all text.</span></span>

    -   <span data-ttu-id="9cf76-131">Ophalen of instellen van een tekstselectie.</span><span class="sxs-lookup"><span data-stu-id="9cf76-131">Get or set a text selection.</span></span>

    -   <span data-ttu-id="9cf76-132">Uitvoeren van een script of een geselecteerde deel van een script uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="9cf76-132">Run a script or run a selected portion of a script.</span></span>

    -   <span data-ttu-id="9cf76-133">Een regel in beeld schuiven.</span><span class="sxs-lookup"><span data-stu-id="9cf76-133">Scroll a line into view.</span></span>

    -   <span data-ttu-id="9cf76-134">Tekst op een invoegpositie invoegen.</span><span class="sxs-lookup"><span data-stu-id="9cf76-134">Insert text at a caret position.</span></span>

    -   <span data-ttu-id="9cf76-135">Selecteer een blok van tekst.</span><span class="sxs-lookup"><span data-stu-id="9cf76-135">Select a block of text.</span></span>

    -   <span data-ttu-id="9cf76-136">Het regelnummer van de laatste ophalen.</span><span class="sxs-lookup"><span data-stu-id="9cf76-136">Get the last line number.</span></span>

- <span data-ttu-id="9cf76-137">Bestandsbewerkingen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="9cf76-137">Perform file operations.</span></span> <span data-ttu-id="9cf76-138">U kunt bijvoorbeeld het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="9cf76-138">For example, you can:</span></span>

    -   <span data-ttu-id="9cf76-139">Openen van een bestand, een bestand opslaan of een bestand opslaan met behulp van een andere naam.</span><span class="sxs-lookup"><span data-stu-id="9cf76-139">Open a file, save a file, or save a file by using a different name.</span></span>

    -   <span data-ttu-id="9cf76-140">Bepalen of een bestand is gewijzigd nadat het laatst is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="9cf76-140">Determine whether a file has been changed after it was last saved.</span></span>

    -   <span data-ttu-id="9cf76-141">De bestandsnaam niet ophalen.</span><span class="sxs-lookup"><span data-stu-id="9cf76-141">Get the file name.</span></span>

    -   <span data-ttu-id="9cf76-142">Selecteer een bestand.</span><span class="sxs-lookup"><span data-stu-id="9cf76-142">Select a file.</span></span>

## <a name="automating-tasks"></a><span data-ttu-id="9cf76-143">Taken automatiseren</span><span class="sxs-lookup"><span data-stu-id="9cf76-143">Automating tasks</span></span>
 <span data-ttu-id="9cf76-144">U kunt het uitvoeren van scripts objectmodel sneltoetsen voor regelmatige bewerkingen maken.</span><span class="sxs-lookup"><span data-stu-id="9cf76-144">You can use the scripting object model to create keyboard shortcuts for frequent operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cf76-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9cf76-145">See Also</span></span>
- [<span data-ttu-id="9cf76-146">De hiërarchie ISE</span><span class="sxs-lookup"><span data-stu-id="9cf76-146">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md) 
- [<span data-ttu-id="9cf76-147">Naslaginformatie voor Windows PowerShell ISE-objectmodel</span><span class="sxs-lookup"><span data-stu-id="9cf76-147">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md) 
- [<span data-ttu-id="9cf76-148">De Windows PowerShell ISE-objectmodel Scripting</span><span class="sxs-lookup"><span data-stu-id="9cf76-148">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)

  