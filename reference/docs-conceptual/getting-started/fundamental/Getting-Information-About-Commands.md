---
ms.date: 2017-06-05
keywords: PowerShell-cmdlet
title: Informatie ophalen over opdrachten
ms.assetid: 56f8e5b4-d97c-4e59-abbe-bf13e464eb0d
ms.openlocfilehash: 98e449110860ea81939d6ec0b7b1a8534a2da2aa
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="getting-information-about-commands"></a><span data-ttu-id="3d1df-103">Informatie ophalen over opdrachten</span><span class="sxs-lookup"><span data-stu-id="3d1df-103">Getting Information About Commands</span></span>
<span data-ttu-id="3d1df-104">De Windows PowerShell **Get-Command** cmdlet haalt alle opdrachten die beschikbaar in de huidige sessie zijn.</span><span class="sxs-lookup"><span data-stu-id="3d1df-104">The Windows PowerShell **Get-Command** cmdlet gets all commands that are available in your current session.</span></span> <span data-ttu-id="3d1df-105">Wanneer u typt **Get-Command** bij een Windows PowerShell-prompt ziet u uitvoer die vergelijkbaar is met het volgende:</span><span class="sxs-lookup"><span data-stu-id="3d1df-105">When you type **Get-Command** at a Windows PowerShell prompt, you will see output similar to the following:</span></span>

```
PS> Get-Command
CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Add-Content                     Add-Content [-Path] <String[...
Cmdlet          Add-History                     Add-History [[-InputObject] ...
Cmdlet          Add-Member                      Add-Member [-MemberType] <PS...
...
```

<span data-ttu-id="3d1df-106">Dit lijkt veel uitvoer zoals de uitvoer van de Help van Cmd.exe: een tabellaire samenvatting van interne opdrachten.</span><span class="sxs-lookup"><span data-stu-id="3d1df-106">This output looks a lot like the Help output of Cmd.exe: a tabular summary of internal commands.</span></span> <span data-ttu-id="3d1df-107">In het fragment van de **Get-Command** opdracht uitvoer hierboven, om de opdracht heeft een CommandType Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3d1df-107">In the excerpt of the **Get-Command** command output shown above, every command shown has a CommandType of Cmdlet.</span></span> <span data-ttu-id="3d1df-108">Een cmdlet zich van Windows PowerShell intrinsieke opdrachttype - een type dat overeenkomt met ongeveer tot de **dir** en **cd** opdrachten van Cmd.exe en dient te worden in de houders UNIX zoals BASH.</span><span class="sxs-lookup"><span data-stu-id="3d1df-108">A cmdlet is Windows PowerShell's intrinsic command type - a type that corresponds roughly to the **dir** and **cd** commands of Cmd.exe and to built-ins in UNIX shells such as BASH.</span></span>

<span data-ttu-id="3d1df-109">In de uitvoer van de **Get-Command** opdracht, de definities eindigen op de weglatingstekens (...) om aan te geven dat de inhoud door PowerShell kan niet worden weergegeven in de beschikbare ruimte.</span><span class="sxs-lookup"><span data-stu-id="3d1df-109">In the output of the **Get-Command** command, all the definitions end with ellipses (...) to indicate that PowerShell cannot display all the content in the available space.</span></span> <span data-ttu-id="3d1df-110">Wanneer de uitvoer wordt weergegeven in Windows PowerShell, de uitvoer als tekst indelingen en vervolgens rangschikt zodat de gegevens correct in het venster past.</span><span class="sxs-lookup"><span data-stu-id="3d1df-110">When Windows PowerShell displays output, it formats the output as text and then arranges it to make the data fit cleanly into the window.</span></span> <span data-ttu-id="3d1df-111">We zullen hebben over deze later in de sectie op formatters.</span><span class="sxs-lookup"><span data-stu-id="3d1df-111">We will talk about this later in the section on formatters.</span></span>

<span data-ttu-id="3d1df-112">De **Get-Command** cmdlet heeft een **syntaxis** parameter die de syntaxis van elke cmdlet opgehaald.</span><span class="sxs-lookup"><span data-stu-id="3d1df-112">The **Get-Command** cmdlet has a **Syntax** parameter that gets the syntax of each cmdlet.</span></span> <span data-ttu-id="3d1df-113">Als u de syntaxis van de cmdlet Get-Help, gebruikt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="3d1df-113">To get the syntax of the Get-Help cmdlet, use the following command:</span></span>

<span data-ttu-id="3d1df-114">**GET-opdracht Get-Help-syntaxis**</span><span class="sxs-lookup"><span data-stu-id="3d1df-114">**Get-Command Get-Help -Syntax**</span></span>

```
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Full] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Detailed] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Examples] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Parameter <String>] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]
```

### <a name="displaying-available-command-types"></a><span data-ttu-id="3d1df-115">Beschikbare opdrachttypen weergeven</span><span class="sxs-lookup"><span data-stu-id="3d1df-115">Displaying Available Command Types</span></span>
<span data-ttu-id="3d1df-116">De **Get-Command** opdracht de lijst bevat niet alle opdrachten die beschikbaar is in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d1df-116">The **Get-Command** command does not list every command that is available in Windows PowerShell.</span></span> <span data-ttu-id="3d1df-117">In plaats daarvan de **Get-Command** opdracht geeft alleen de cmdlets in de huidige sessie.</span><span class="sxs-lookup"><span data-stu-id="3d1df-117">Instead, the **Get-Command** command lists only the cmdlets in the current session.</span></span> <span data-ttu-id="3d1df-118">Enkele andere soorten opdrachten daadwerkelijk wordt ondersteund door Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d1df-118">Windows PowerShell actually supports several other types of commands.</span></span> <span data-ttu-id="3d1df-119">Aliassen, functies en scripts zijn ook Windows PowerShell-opdrachten, hoewel ze niet in de Windows PowerShell User's Guide in detail worden besproken.</span><span class="sxs-lookup"><span data-stu-id="3d1df-119">Aliases, functions, and scripts are also Windows PowerShell commands, although they are not discussed in detail in the Windows PowerShell User's Guide.</span></span> <span data-ttu-id="3d1df-120">Externe bestanden die uitvoerbare zijn of een handler van het type geregistreerd bestand ook worden ingedeeld als opdrachten.</span><span class="sxs-lookup"><span data-stu-id="3d1df-120">External files that are executable, or have a registered file type handler, are also classified as commands.</span></span>

<span data-ttu-id="3d1df-121">Als u alle opdrachten in de sessie, typt u:</span><span class="sxs-lookup"><span data-stu-id="3d1df-121">To get all commands in the session, type:</span></span>

```
Get-Command *
```

<span data-ttu-id="3d1df-122">Omdat deze lijst externe bestanden in uw zoekpad bevat, kan het duizenden items bevatten.</span><span class="sxs-lookup"><span data-stu-id="3d1df-122">Because this list includes external files in your search path, it may contain thousands of items.</span></span> <span data-ttu-id="3d1df-123">Dit is meer handig om te kijken naar een beperkte reeks opdrachten.</span><span class="sxs-lookup"><span data-stu-id="3d1df-123">It is more useful to look at a reduced set of commands.</span></span>

<span data-ttu-id="3d1df-124">Als u ingebouwde opdrachten van andere typen, gebruikt de **CommandType** parameter van de **Get-Command** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3d1df-124">To get native commands of other types, use the **CommandType** parameter of the **Get-Command** cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="3d1df-125">Het sterretje (\*) wordt gebruikt voor de vergelijking argumenten in Windows PowerShell-opdracht met jokertekens.</span><span class="sxs-lookup"><span data-stu-id="3d1df-125">The asterisk (\*) is used for wildcard matching in Windows PowerShell command arguments.</span></span> <span data-ttu-id="3d1df-126">De \* betekent 'overeenkomstig met een of meer van de tekens'.</span><span class="sxs-lookup"><span data-stu-id="3d1df-126">The \* means "match one or more of any characters".</span></span> <span data-ttu-id="3d1df-127">U kunt typen **Get-Command een\&#42;** vinden alle opdrachten die met de letter beginnen "a".</span><span class="sxs-lookup"><span data-stu-id="3d1df-127">You can type **Get-Command a\&#42;** to find all commands that begin with the letter "a".</span></span> <span data-ttu-id="3d1df-128">In tegenstelling tot jokerteken identieke in Cmd.exe jokertekens van Windows PowerShell ook overeen met een periode.</span><span class="sxs-lookup"><span data-stu-id="3d1df-128">Unlike wildcard matching in Cmd.exe, Windows PowerShell's wildcard will also match a period.</span></span>

<span data-ttu-id="3d1df-129">Als u de opdracht-aliassen die de toegewezen bijnaam van opdrachten, typt u:</span><span class="sxs-lookup"><span data-stu-id="3d1df-129">To get command aliases, which are the assigned nicknames of commands, type:</span></span>

```
Get-Command -CommandType Alias
```

<span data-ttu-id="3d1df-130">Als u de functies in de huidige sessie, typt u:</span><span class="sxs-lookup"><span data-stu-id="3d1df-130">To get the functions in the current session, type:</span></span>

```
Get-Command -CommandType Function
```

<span data-ttu-id="3d1df-131">Als scripts in de Windows PowerShell-zoekpad weergeven, typt u:</span><span class="sxs-lookup"><span data-stu-id="3d1df-131">To display scripts in Windows PowerShell's search path, type:</span></span>

```
Get-Command -CommandType Script
```
