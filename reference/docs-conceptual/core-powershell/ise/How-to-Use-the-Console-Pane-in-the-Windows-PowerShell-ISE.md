---
ms.date: 2017-06-05
keywords: PowerShell-cmdlet
title: Het gebruik van het consolevenster in de Windows PowerShell ISE
ms.assetid: 44d67705-87c7-4a69-a53e-6471fdebb757
ms.openlocfilehash: 59e97bbc12269d855c4f3715171636647d4cc634
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2017
---
# <a name="how-to-use-the-console-pane-in-the-windows-powershell-ise"></a><span data-ttu-id="478bc-103">Het gebruik van het consolevenster in de Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="478bc-103">How to Use the Console Pane in the Windows PowerShell ISE</span></span>
<span data-ttu-id="478bc-104">Het consolevenster in de Windows PowerShell Integrated Scripting Environment (ISE) werkt precies zoals het zelfstandige Windows PowerShell ISE-consolevenster.</span><span class="sxs-lookup"><span data-stu-id="478bc-104">The Console pane in the Windows PowerShell Integrated Scripting Environment (ISE) operates exactly like the stand-alone Windows PowerShell ISE console window.</span></span>

<span data-ttu-id="478bc-105">Als u wilt uitvoeren van een opdracht in het consolevenster, typt u een opdracht en druk op ENTER.</span><span class="sxs-lookup"><span data-stu-id="478bc-105">To run a command in the Console Pane, type a command, and then press ENTER.</span></span> <span data-ttu-id="478bc-106">Meerdere opdrachten die u wilt uitvoeren in de juiste volgorde, typt u SHIFT + ENTER tussen opdrachten.</span><span class="sxs-lookup"><span data-stu-id="478bc-106">To enter multiple commands that you want to execute in sequence, type SHIFT+ENTER between commands.</span></span> <span data-ttu-id="478bc-107">Zie [hoe gebruik Tab-aanvulling in het scriptvenster en consolevenster](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) voor hulp bij opdrachten te typen.</span><span class="sxs-lookup"><span data-stu-id="478bc-107">See [How to Use Tab Completion in the Script Pane and Console Pane](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) for help in typing commands.</span></span>

<span data-ttu-id="478bc-108">Als u wilt een opdracht op de werkbalk stoppen, klikt u op **bewerking stoppen**, of druk op CTRL + BREAK.</span><span class="sxs-lookup"><span data-stu-id="478bc-108">To stop a command, on the toolbar, click **Stop Operation**, or press CTRL+BREAK.</span></span> <span data-ttu-id="478bc-109">U kunt ook CTRL + C om te stoppen van een opdracht als de context niet-ambigue is gebruiken.</span><span class="sxs-lookup"><span data-stu-id="478bc-109">You can also use CTRL+C to stop a command if the context is unambiguous.</span></span> <span data-ttu-id="478bc-110">Bijvoorbeeld, als deel van de tekst in het huidige deelvenster is geselecteerd, klikt u vervolgens CTRL + C toegewezen aan de kopieerbewerking.</span><span class="sxs-lookup"><span data-stu-id="478bc-110">For example, if some text has been selected in the current Pane, then CTRL+C maps to the copy operation.</span></span>

<span data-ttu-id="478bc-111">Vanaf Windows PowerShell v3 is is het deelvenster Uitvoer gecombineerd met het consolevenster.</span><span class="sxs-lookup"><span data-stu-id="478bc-111">Beginning in Windows PowerShell v3, the Output pane was combined with the Console pane.</span></span> <span data-ttu-id="478bc-112">Dit heeft het voordeel van gedragen zoals zelfstandige Windows PowerShell-console en elimineert de verschillen in de procedures die zijn vereist als ze afzonderlijke zijn.</span><span class="sxs-lookup"><span data-stu-id="478bc-112">This has the benefit of behaving like the stand-alone Windows PowerShell console and eliminates the differences in procedures that were needed when they were separate.</span></span> <span data-ttu-id="478bc-113">U kunt:</span><span class="sxs-lookup"><span data-stu-id="478bc-113">You can:</span></span>

- <span data-ttu-id="478bc-114">Selecteer en kopieer de tekst van het consolevenster naar het Klembord plakken in een ander venster.</span><span class="sxs-lookup"><span data-stu-id="478bc-114">Select and copy text from the Console pane to the Clipboard for pasting in any other window.</span></span> <span data-ttu-id="478bc-115">Tekst selecteren, klikt u op en houd de muis in het deelvenster uitvoer tijdens het slepen van de muis boven de tekst die u wilt vastleggen.</span><span class="sxs-lookup"><span data-stu-id="478bc-115">To select text, click and hold the mouse in the output pane while dragging the mouse over the text you want to capture.</span></span> <span data-ttu-id="478bc-116">U kunt ook de pijltoetsen bij het bedrijf **SHIFT** om tekst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="478bc-116">You can also use the cursor arrow keys while holding **SHIFT** to select text.</span></span> <span data-ttu-id="478bc-117">Vervolgens drukt u op CTRL + C of klik op de **kopie** pictogram op de werkbalk.</span><span class="sxs-lookup"><span data-stu-id="478bc-117">Then press CTRL+C or click the **Copy** icon in the toolbar.</span></span>

- <span data-ttu-id="478bc-118">De geselecteerde tekst op een huidige cursorpositie plakken.</span><span class="sxs-lookup"><span data-stu-id="478bc-118">Paste the selected text at a current cursor position.</span></span> <span data-ttu-id="478bc-119">Klik op de **plakken** pictogram op de werkbalk.</span><span class="sxs-lookup"><span data-stu-id="478bc-119">Click the **Paste** icon on the toolbar.</span></span>

- <span data-ttu-id="478bc-120">Verwijdert alle tekst in het consolevenster.</span><span class="sxs-lookup"><span data-stu-id="478bc-120">Clear all the text in the Console pane.</span></span> <span data-ttu-id="478bc-121">Schakel het consolevenster, klikt u op de **consolevenster wissen** pictogram op de werkbalk of Voer de opdracht **wissen Host** of de alias **cls**.</span><span class="sxs-lookup"><span data-stu-id="478bc-121">To clear the Console pane, you can click the **Clear Console Pane** icon on the toolbar, or run the command **Clear-Host** or its alias, **cls**.</span></span>

## <a name="see-also"></a><span data-ttu-id="478bc-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="478bc-122">See Also</span></span>
- [<span data-ttu-id="478bc-123">Met behulp van de Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="478bc-123">Using the Windows PowerShell ISE</span></span>](Using-the-Windows-PowerShell-ISE.md)
