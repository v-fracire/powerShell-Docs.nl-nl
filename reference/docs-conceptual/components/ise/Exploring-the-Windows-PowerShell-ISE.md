---
ms.date: 06/05/2017
keywords: PowerShell-cmdlet
title: Kennismaking met Windows PowerShell ISE
ms.assetid: e0d2c6e8-5126-40e7-a1e1-d1cff29fe94a
ms.openlocfilehash: 059651f159fb2636a93167709134788e90d062b8
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2018
ms.locfileid: "53404458"
---
# <a name="exploring-the-windows-powershell-ise"></a><span data-ttu-id="dc97f-103">Kennismaking met Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="dc97f-103">Exploring the Windows PowerShell ISE</span></span>

<span data-ttu-id="dc97f-104">U kunt de Windows PowerShell® Integrated Scripting Environment (ISE) gebruiken om te maken, uitvoeren en fouten opsporen in opdrachten en scripts.</span><span class="sxs-lookup"><span data-stu-id="dc97f-104">You can use the Windows PowerShell® Integrated Scripting Environment (ISE) to create, run, and debug commands and scripts.</span></span> <span data-ttu-id="dc97f-105">De Windows PowerShell ISE bestaat uit de in de menubalk, Windows PowerShell-tabbladen, de werkbalk, script tabbladen, een scriptvenster, een consolevenster, een statusbalk, een schuifregelaar tekst-grootte en contextgevoelige Help.</span><span class="sxs-lookup"><span data-stu-id="dc97f-105">The Windows PowerShell ISE consists of the menu bar, Windows PowerShell tabs, the toolbar, script tabs, a Script Pane, a Console Pane, a status bar, a text-size slider and context-sensitive Help.</span></span>

> [!NOTE]
> <span data-ttu-id="dc97f-106">Beginnen met Windows PowerShell ISE 3.0, de opdracht en de uitvoer deelvensters zijn gecombineerd in één Console-venster.</span><span class="sxs-lookup"><span data-stu-id="dc97f-106">Beginning with Windows PowerShell ISE 3.0 the Command and Output Panes were combined into a single Console Pane.</span></span>

## <a name="menu-bar"></a><span data-ttu-id="dc97f-107">In de menubalk</span><span class="sxs-lookup"><span data-stu-id="dc97f-107">Menu Bar</span></span>

<span data-ttu-id="dc97f-108">De menubalk bevat de **bestand**, **bewerken**, **weergave**, **extra**, **Debug**,  **Invoegtoepassingen**, en **Help** menu's.</span><span class="sxs-lookup"><span data-stu-id="dc97f-108">The menu bar contains the **File**, **Edit**, **View**, **Tools**, **Debug**, **Add-ons**, and **Help** menus.</span></span> <span data-ttu-id="dc97f-109">De knoppen op de menu's kunnen u taken met betrekking tot scripts schrijven en actieve en actieve opdrachten in de Windows PowerShell ISE uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="dc97f-109">The buttons on the menus allow you to perform tasks related to writing and running scripts and running commands in the Windows PowerShell ISE.</span></span> <span data-ttu-id="dc97f-110">Bovendien een [invoegtoepassing hulpprogramma](../../core-powershell/ise/The-ISEAddOnTool-Object.md) mag worden geplaatst op de menubalk, door het uitvoeren van scripts die gebruikmaken van de [de objectmodelhiërarchie van ISE](../../core-powershell/ise/The-ISE-Object-Model-Hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="dc97f-110">Additionally, an [add-on tool](../../core-powershell/ise/The-ISEAddOnTool-Object.md) may be placed on the menu bar by running scripts that use the [The ISE Object Model Hierarchy](../../core-powershell/ise/The-ISE-Object-Model-Hierarchy.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dc97f-111">In Windows PowerShell ISE 2.0, de **extra** en **invoegtoepassingen** menu's zijn niet aanwezig.</span><span class="sxs-lookup"><span data-stu-id="dc97f-111">In Windows PowerShell ISE 2.0, The **Tools** and **Add-ons** menus were not present.</span></span>

## <a name="windows-powershell-tabs"></a><span data-ttu-id="dc97f-112">Windows PowerShell tabbladen</span><span class="sxs-lookup"><span data-stu-id="dc97f-112">Windows PowerShell Tabs</span></span>

<span data-ttu-id="dc97f-113">Een Windows PowerShell-tabblad is de omgeving waarin een Windows PowerShell-script wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="dc97f-113">A Windows PowerShell tab is the environment in which a Windows PowerShell script runs.</span></span> <span data-ttu-id="dc97f-114">U kunt nieuwe Windows PowerShell-tabbladen openen in de Windows PowerShell ISE op afzonderlijke omgevingen maken op uw lokale computer of op externe computers.</span><span class="sxs-lookup"><span data-stu-id="dc97f-114">You can open new Windows PowerShell tabs in the Windows PowerShell ISE to create separate environments on your local computer or on remote computers.</span></span> <span data-ttu-id="dc97f-115">Er kunnen maximaal acht PowerShell tabbladen tegelijkertijd openen.</span><span class="sxs-lookup"><span data-stu-id="dc97f-115">You may have a maximum of eight PowerShell tabs simultaneously open.</span></span>

## <a name="toolbar"></a><span data-ttu-id="dc97f-116">Werkbalk</span><span class="sxs-lookup"><span data-stu-id="dc97f-116">Toolbar</span></span>

<span data-ttu-id="dc97f-117">De volgende knoppen bevinden zich op de werkbalk.</span><span class="sxs-lookup"><span data-stu-id="dc97f-117">The following buttons are located on the toolbar.</span></span>

|<span data-ttu-id="dc97f-118">Knop</span><span class="sxs-lookup"><span data-stu-id="dc97f-118">Button</span></span>|<span data-ttu-id="dc97f-119">Functie</span><span class="sxs-lookup"><span data-stu-id="dc97f-119">Function</span></span>|
|----------|------------|
|<span data-ttu-id="dc97f-120">**Nieuw**</span><span class="sxs-lookup"><span data-stu-id="dc97f-120">**New**</span></span>|<span data-ttu-id="dc97f-121">Hiermee opent u een nieuw script.</span><span class="sxs-lookup"><span data-stu-id="dc97f-121">Opens a new script.</span></span>|
|<span data-ttu-id="dc97f-122">**Open**</span><span class="sxs-lookup"><span data-stu-id="dc97f-122">**Open**</span></span>|<span data-ttu-id="dc97f-123">Hiermee opent u een bestaand script of een bestand.</span><span class="sxs-lookup"><span data-stu-id="dc97f-123">Opens an existing script or file.</span></span>|
|<span data-ttu-id="dc97f-124">**Opslaan**</span><span class="sxs-lookup"><span data-stu-id="dc97f-124">**Save**</span></span>|<span data-ttu-id="dc97f-125">Hiermee slaat u een script of een bestand.</span><span class="sxs-lookup"><span data-stu-id="dc97f-125">Saves a script or file.</span></span>|
|<span data-ttu-id="dc97f-126">**Knippen**</span><span class="sxs-lookup"><span data-stu-id="dc97f-126">**Cut**</span></span>|<span data-ttu-id="dc97f-127">De geselecteerde tekst knippen en vervolgens gekopieerd naar het Klembord.</span><span class="sxs-lookup"><span data-stu-id="dc97f-127">Cuts the selected text and copies it to the clipboard.</span></span>|
|<span data-ttu-id="dc97f-128">**Kopiëren**</span><span class="sxs-lookup"><span data-stu-id="dc97f-128">**Copy**</span></span>|<span data-ttu-id="dc97f-129">De geselecteerde tekst naar het Klembord gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="dc97f-129">Copies the selected text to the clipboard.</span></span>|
|<span data-ttu-id="dc97f-130">**Plakken**</span><span class="sxs-lookup"><span data-stu-id="dc97f-130">**Paste**</span></span>|<span data-ttu-id="dc97f-131">De inhoud van het Klembord op de cursorlocatie geplakt.</span><span class="sxs-lookup"><span data-stu-id="dc97f-131">Pastes the contents of the clipboard at the cursor location.</span></span>|
|<span data-ttu-id="dc97f-132">**Deelvenster Uitvoer wissen**</span><span class="sxs-lookup"><span data-stu-id="dc97f-132">**Clear Output Pane**</span></span>|<span data-ttu-id="dc97f-133">Hiermee schakelt u alle inhoud in het deelvenster Uitvoer.</span><span class="sxs-lookup"><span data-stu-id="dc97f-133">Clears all content in the Output Pane.</span></span>|
|<span data-ttu-id="dc97f-134">**Ongedaan maken**</span><span class="sxs-lookup"><span data-stu-id="dc97f-134">**Undo**</span></span>|<span data-ttu-id="dc97f-135">De bewerking die zojuist is uitgevoerd, ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="dc97f-135">Reverses the action that was just performed.</span></span>|
|<span data-ttu-id="dc97f-136">**Redo**</span><span class="sxs-lookup"><span data-stu-id="dc97f-136">**Redo**</span></span>|<span data-ttu-id="dc97f-137">Voert de actie die alleen ongedaan is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="dc97f-137">Performs the action that was just undone.</span></span>|
|<span data-ttu-id="dc97f-138">**Script uitvoeren**</span><span class="sxs-lookup"><span data-stu-id="dc97f-138">**Run Script**</span></span>|<span data-ttu-id="dc97f-139">Een script wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="dc97f-139">Runs a script.</span></span>|
|<span data-ttu-id="dc97f-140">**Selectie uitvoeren**</span><span class="sxs-lookup"><span data-stu-id="dc97f-140">**Run Selection**</span></span>|<span data-ttu-id="dc97f-141">Een geselecteerde gedeelte van een script wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="dc97f-141">Runs a selected portion of a script.</span></span>|
|<span data-ttu-id="dc97f-142">**Uitvoering stoppen**</span><span class="sxs-lookup"><span data-stu-id="dc97f-142">**Stop Execution**</span></span>|<span data-ttu-id="dc97f-143">Hiermee stopt u een script dat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="dc97f-143">Stops a script that is running.</span></span>|
|<span data-ttu-id="dc97f-144">**Nieuwe externe PowerShell-tabblad**</span><span class="sxs-lookup"><span data-stu-id="dc97f-144">**New Remote PowerShell Tab**</span></span>|<span data-ttu-id="dc97f-145">Hiermee maakt u een nieuwe PowerShell-tabblad waarmee een sessie op een externe computer.</span><span class="sxs-lookup"><span data-stu-id="dc97f-145">Creates a new PowerShell Tab that establishes a session on a remote computer.</span></span> <span data-ttu-id="dc97f-146">Een dialoogvenster wordt weergegeven en vraagt u om in te voeren van gegevens die zijn vereist om de externe verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="dc97f-146">A dialog box appears and prompts you to enter details required to establish the remote connection.</span></span>|
|<span data-ttu-id="dc97f-147">**Start PowerShell.exe**</span><span class="sxs-lookup"><span data-stu-id="dc97f-147">**Start PowerShell.exe**</span></span>|<span data-ttu-id="dc97f-148">Hiermee opent een PowerShell-Console.</span><span class="sxs-lookup"><span data-stu-id="dc97f-148">Opens a PowerShell Console.</span></span>|
|<span data-ttu-id="dc97f-149">**Script deelvenster-bovenaan weergeven**</span><span class="sxs-lookup"><span data-stu-id="dc97f-149">**Show Script Pane Top**</span></span>|<span data-ttu-id="dc97f-150">Het scriptvenster verplaatst naar de bovenkant in de weergave.</span><span class="sxs-lookup"><span data-stu-id="dc97f-150">Moves the Script Pane to the top in the display.</span></span>|
|<span data-ttu-id="dc97f-151">**Scriptvenster rechts weergeven**</span><span class="sxs-lookup"><span data-stu-id="dc97f-151">**Show Script Pane Right**</span></span>|<span data-ttu-id="dc97f-152">Het scriptvenster verplaatst naar rechts in de weergave.</span><span class="sxs-lookup"><span data-stu-id="dc97f-152">Moves the Script Pane to the right in the display.</span></span>|
|<span data-ttu-id="dc97f-153">**Gemaximaliseerd scriptvenster weergeven**</span><span class="sxs-lookup"><span data-stu-id="dc97f-153">**Show Script Pane Maximized**</span></span>|<span data-ttu-id="dc97f-154">Het scriptvenster maximaliseert.</span><span class="sxs-lookup"><span data-stu-id="dc97f-154">Maximizes the Script Pane.</span></span>|

## <a name="script-tab"></a><span data-ttu-id="dc97f-155">Tabblad script</span><span class="sxs-lookup"><span data-stu-id="dc97f-155">Script Tab</span></span>

<span data-ttu-id="dc97f-156">Geeft de naam van het script dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="dc97f-156">Displays the name of the script you are editing.</span></span> <span data-ttu-id="dc97f-157">U kunt klikken op een tabblad script om te selecteren van het script dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="dc97f-157">You can click a script tab to select the script you want to edit.</span></span>

<span data-ttu-id="dc97f-158">Wanneer u naar het tabblad script verwijzen, wordt het volledig gekwalificeerde pad naar het scriptbestand in een tooltip weergegeven.</span><span class="sxs-lookup"><span data-stu-id="dc97f-158">When you point to the script tab, the fully qualified path to the script file appears in a tooltip.</span></span>

## <a name="script-pane"></a><span data-ttu-id="dc97f-159">Scriptvenster</span><span class="sxs-lookup"><span data-stu-id="dc97f-159">Script Pane</span></span>

<span data-ttu-id="dc97f-160">Hiermee kunt u scripts maken en uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="dc97f-160">Allows you to create and run scripts.</span></span> <span data-ttu-id="dc97f-161">U kunt openen, bewerken en bestaande scripts uitvoeren in het scriptvenster.</span><span class="sxs-lookup"><span data-stu-id="dc97f-161">You can open, edit and run existing scripts in the Script Pane.</span></span>

## <a name="output-pane"></a><span data-ttu-id="dc97f-162">Deelvenster Uitvoer</span><span class="sxs-lookup"><span data-stu-id="dc97f-162">Output Pane</span></span>

<span data-ttu-id="dc97f-163">Geeft de resultaten van de opdrachten en scripts die u hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="dc97f-163">Displays the results of the commands and scripts you have run.</span></span> <span data-ttu-id="dc97f-164">U kunt ook kopiëren en schakelt u de inhoud in het deelvenster Uitvoer.</span><span class="sxs-lookup"><span data-stu-id="dc97f-164">You can also copy and clear the contents in the Output Pane.</span></span>

## <a name="command-pane"></a><span data-ttu-id="dc97f-165">Deelvenster van de opdracht</span><span class="sxs-lookup"><span data-stu-id="dc97f-165">Command Pane</span></span>

<span data-ttu-id="dc97f-166">Kunt u het schrijven van opdrachten.</span><span class="sxs-lookup"><span data-stu-id="dc97f-166">Allows you to write commands.</span></span> <span data-ttu-id="dc97f-167">U kunt een opdracht een regel of een met meerdere regels in het deelvenster opdracht uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="dc97f-167">You can run a one line command or a multiline command in the Command Pane.</span></span> <span data-ttu-id="dc97f-168">Druk op SHIFT + ENTER drukken om elke regel van een met meerdere regels opdracht en druk op ENTER na de laatste regel voor het uitvoeren van de opdracht met meerdere regels.</span><span class="sxs-lookup"><span data-stu-id="dc97f-168">Press SHIFT+ENTER to enter each line of a multiline command, and press ENTER after the last line to execute the multiline command.</span></span> <span data-ttu-id="dc97f-169">De prompt weergegeven boven op het opdrachtvenster ziet u het pad naar de huidige werkmap.</span><span class="sxs-lookup"><span data-stu-id="dc97f-169">The prompt displayed on top of the Command Pane shows the path to the current working directory.</span></span>

## <a name="status-bar"></a><span data-ttu-id="dc97f-170">Statusbalk</span><span class="sxs-lookup"><span data-stu-id="dc97f-170">Status Bar</span></span>

<span data-ttu-id="dc97f-171">Hiermee kunt u zien of de opdrachten en scripts die u uitvoert voltooid zijn.</span><span class="sxs-lookup"><span data-stu-id="dc97f-171">Allows you to see whether the commands and scripts that you run are complete.</span></span> <span data-ttu-id="dc97f-172">De statusbalk is zeer onder aan de weergave.</span><span class="sxs-lookup"><span data-stu-id="dc97f-172">The status bar is at the very bottom of the display.</span></span> <span data-ttu-id="dc97f-173">Geselecteerde gedeelten van foutberichten worden weergegeven op de statusbalk.</span><span class="sxs-lookup"><span data-stu-id="dc97f-173">Selected portions of error messages are displayed on the status bar.</span></span>

## <a name="text-size-slider"></a><span data-ttu-id="dc97f-174">Tekengrootte: schuifregelaar</span><span class="sxs-lookup"><span data-stu-id="dc97f-174">Text-Size Slider</span></span>

<span data-ttu-id="dc97f-175">Vergroot of verkleint u de grootte van de tekst op het scherm.</span><span class="sxs-lookup"><span data-stu-id="dc97f-175">Increases or decreases the size of the text on the screen.</span></span>

## <a name="help"></a><span data-ttu-id="dc97f-176">Help</span><span class="sxs-lookup"><span data-stu-id="dc97f-176">Help</span></span>

<span data-ttu-id="dc97f-177">Help voor Windows PowerShell ISE is beschikbaar in de TechNet-bibliotheek op het Web.</span><span class="sxs-lookup"><span data-stu-id="dc97f-177">Help for Windows PowerShell ISE is available on the Web in the TechNet Library.</span></span> <span data-ttu-id="dc97f-178">U kunt de Help openen door te klikken op **Help van Windows PowerShell ISE** op de **Help** menu of druk op F1 drukt overal, behalve wanneer de cursor op de cmdletnaam van een in het scriptvenster of in het consolevenster.</span><span class="sxs-lookup"><span data-stu-id="dc97f-178">You can open the Help by clicking **Windows PowerShell ISE Help** on the **Help** menu or by pressing the F1 key anywhere except when the cursor is on a cmdlet name in either the Script Pane or the Console Pane.</span></span> <span data-ttu-id="dc97f-179">Uit de **Help** menu kunt u ook uitvoeren de cmdlet Update-Help, en het opdrachtvenster die u helpt bij het maken van opdrachten door alle parameters voor een cmdlet weergegeven en u in de parameters in te vullen in te schakelen weer een formulier kunt u eenvoudig te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="dc97f-179">From the **Help** menu you can also run the Update-Help cmdlet, and display the Command Window which assists you in constructing commands by showing you all of the parameters for a cmdlet and enabling you to fill in the parameters in an easy-to-use form.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc97f-180">Zie ook</span><span class="sxs-lookup"><span data-stu-id="dc97f-180">See Also</span></span>

- [<span data-ttu-id="dc97f-181">Maak kennis met de Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="dc97f-181">Introducing the Windows PowerShell ISE</span></span>](../../core-powershell/ise/Introducing-the-Windows-PowerShell-ISE.md)