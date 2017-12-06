---
ms.date: 2017-06-05
keywords: PowerShell-cmdlet
title: Introducing the Windows PowerShell ISE
ms.openlocfilehash: 75242c20548e2e83397867214417a48806c897ec
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2017
---
# <a name="introducing-the-windows-powershell-ise"></a><span data-ttu-id="ccd9b-103">Introducing the Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="ccd9b-103">Introducing the Windows PowerShell ISE</span></span>
<span data-ttu-id="ccd9b-104">De Windows PowerShell Integrated Scripting Environment (ISE) is een hosttoepassing voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-104">The Windows PowerShell Integrated Scripting Environment (ISE) is a host application for Windows PowerShell.</span></span> <span data-ttu-id="ccd9b-105">In Windows PowerShell ISE kunt u uitvoeren van opdrachten en schrijven, testen en fouten opsporen in scripts in één Windows gebaseerde grafische gebruikersinterface met het bewerken van meerdere regels, tab-Aanvulling syntaxiskleuren, selectief worden uitgevoerd, contextgevoelige help en ondersteuning voor talen van rechts naar links.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-105">In Windows PowerShell ISE, you can run commands and write, test, and debug scripts in a single Windows-based graphic user interface with multiline editing, tab completion, syntax coloring, selective execution, context-sensitive help, and support for right-to-left languages.</span></span>
<span data-ttu-id="ccd9b-106">U kunt menu-items en sneltoetsen gebruiken om uit te voeren veel van dezelfde taken die u in de Windows PowerShell-console uitvoeren wilt.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-106">You can use menu items and keyboard shortcuts to perform many of the same tasks that you would perform in the Windows PowerShell console.</span></span>  <span data-ttu-id="ccd9b-107">Bijvoorbeeld, wanneer u een script in de Windows PowerShell ISE debug, om in te stellen van een regel onderbrekingspunt in een script met de rechtermuisknop op de regel code, en klik vervolgens op **onderbrekingspunt**.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-107">For example, when you debug a script in the Windows PowerShell ISE, to set a line breakpoint in a script, right-click the line of code, and then click **Toggle Breakpoint**.</span></span>

<span data-ttu-id="ccd9b-108">Probeer deze functies in Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-108">Try these features in Windows PowerShell ISE.</span></span>

- <span data-ttu-id="ccd9b-109">Bewerken van meerdere regels: voor het invoegen van een lege regel onder de huidige regel in het opdrachtvenster, drukt u op SHIFT + ENTER.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-109">Multiline editing: To insert a blank line under the current line in the Command pane, press SHIFT+ENTER.</span></span>

- <span data-ttu-id="ccd9b-110">Selectief uitvoering: voor het onderdeel van een script uitvoeren, selecteert u de tekst die u wilt uitvoeren en klik vervolgens op de **-Script uitvoeren** knop.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-110">Selective execution: To run part of a script, select the text you want to run, and then click the **Run Script** button.</span></span> <span data-ttu-id="ccd9b-111">Of druk op F5.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-111">Or, press F5.</span></span>

- <span data-ttu-id="ccd9b-112">Contextgevoelige help: Type **Invoke-Item**, en druk op F1.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-112">Context-sensitive help: Type **Invoke-Item**, and then press F1.</span></span> <span data-ttu-id="ccd9b-113">Hiermee opent u het Help-bestand naar de Help-onderwerp voor de **Invoke-Item** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-113">The Help file opens to the Help topic for the **Invoke-Item** cmdlet.</span></span>

<span data-ttu-id="ccd9b-114">De Windows PowerShell ISE kunt u bepaalde aspecten van de weergave aanpassen.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-114">The Windows PowerShell ISE lets you customize some aspects of its appearance.</span></span> <span data-ttu-id="ccd9b-115">Ook heeft een eigen Windows PowerShell-profiel, waarin u functies, aliassen, variabelen en opdrachten die u gebruikt in de Windows PowerShell ISE kunt opslaan.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-115">It also has its own Windows PowerShell profile, where you can store functions, aliases, variables, and commands you use in the Windows PowerShell ISE.</span></span>

### <a name="to-start-the-windows-powershell-ise"></a><span data-ttu-id="ccd9b-116">Starten van de Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="ccd9b-116">To start the Windows PowerShell ISE</span></span>

1. <span data-ttu-id="ccd9b-117">Voer een van de volgende handelingen uit:</span><span class="sxs-lookup"><span data-stu-id="ccd9b-117">Do one of the following:</span></span>

    -   <span data-ttu-id="ccd9b-118">Klik op **Start**, wijs **alle programma's**, wijs **Windows PowerShell V2**, en klik vervolgens op **Windows PowerShell ISE**.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-118">Click **Start**, point to **All Programs**, point to **Windows PowerShell V2**, and then click **Windows PowerShell ISE**.</span></span>

    -   <span data-ttu-id="ccd9b-119">In de Windows PowerShell-console Cmd.exe of in het vak uitvoeren, type, **powershell_ise.exe**.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-119">In the Windows PowerShell console Cmd.exe, or in the Run box, type, **powershell_ise.exe**.</span></span>

### <a name="to-get-help-in-the-windows-powershell-ise"></a><span data-ttu-id="ccd9b-120">Om hulp te krijgen in de Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="ccd9b-120">To get Help in the Windows PowerShell ISE</span></span>

- <span data-ttu-id="ccd9b-121">Op de **Help** menu, klikt u op **Windows PowerShell Help**.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-121">On the **Help** menu, click **Windows PowerShell Help**.</span></span> <span data-ttu-id="ccd9b-122">Of druk op F1.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-122">Or, press F1.</span></span> <span data-ttu-id="ccd9b-123">Windows PowerShell ISE- en Windows PowerShell, inclusief alle van de Help-informatie van de cmdlet Get-Help beschrijving van het bestand dat wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="ccd9b-123">The file that opens describes Windows PowerShell ISE and Windows PowerShell, including all of the help available from the Get-Help cmdlet.</span></span>
