---
ms.date: 2017-08-09
keywords: PowerShell-cmdlet, downloaden, installeren, setup, windows 10, windows 8.1, windows 8.0, windows 7
title: Windows PowerShell installeren
ms.openlocfilehash: 781bf50b6ac649e72bcdbb708555275fb7422d94
ms.sourcegitcommit: 3720ce4efb6735694cfb53a1b793d949af5d1bc5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/29/2017
---
# <a name="installing-windows-powershell"></a><span data-ttu-id="df7ae-103">Windows PowerShell installeren</span><span class="sxs-lookup"><span data-stu-id="df7ae-103">Installing Windows PowerShell</span></span>

<span data-ttu-id="df7ae-104">PowerShell wordt geleverd in elke Windows, Windows 7 SP1 en Windows Server 2008 R2 SP1 vanaf standaard geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="df7ae-104">PowerShell comes installed by default in every Windows, starting with Windows 7 SP1 and Windows Server 2008 R2 SP1.</span></span>

<span data-ttu-id="df7ae-105">Linux-, Mac OS- en Windows-gebruikers die u wilt installeren **PowerShell 6** (bèta) in hun machines moet:</span><span class="sxs-lookup"><span data-stu-id="df7ae-105">Linux, macOS, and Windows users that would like to install **PowerShell 6** (beta), in their machines, need to:</span></span>

1. <span data-ttu-id="df7ae-106">PowerShell voor specifieke besturingssystemen en versie, ophalen uit [GitHub](https://github.com/powershell/powershell#get-powershell)</span><span class="sxs-lookup"><span data-stu-id="df7ae-106">Get PowerShell for the specific OS and version, from [GitHub](https://github.com/powershell/powershell#get-powershell)</span></span>
1. <span data-ttu-id="df7ae-107">Volg de installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="df7ae-107">Follow the installation instructions</span></span>
  - [<span data-ttu-id="df7ae-108">Linux</span><span class="sxs-lookup"><span data-stu-id="df7ae-108">Linux</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
  - [<span data-ttu-id="df7ae-109">Mac OS</span><span class="sxs-lookup"><span data-stu-id="df7ae-109">macOS</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)
  - [<span data-ttu-id="df7ae-110">Windows</span><span class="sxs-lookup"><span data-stu-id="df7ae-110">Windows</span></span>](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/windows.md#msi)

<span data-ttu-id="df7ae-111">PowerShell 6 is ook beschikbaar voor Docker; Zie [Docker installatie](https://github.com/PowerShell/PowerShell/tree/master/docker) instructies.</span><span class="sxs-lookup"><span data-stu-id="df7ae-111">PowerShell 6 is also available for Docker; see [Docker installation](https://github.com/PowerShell/PowerShell/tree/master/docker) instructions.</span></span>

## <a name="finding-powershell-in-windows-10-81-80-and-7"></a><span data-ttu-id="df7ae-112">Het vinden van PowerShell in Windows 10, 8.1, 8.0 en 7</span><span class="sxs-lookup"><span data-stu-id="df7ae-112">Finding PowerShell in Windows 10, 8.1, 8.0, and 7</span></span>

<span data-ttu-id="df7ae-113">Soms zoeken PowerShell kan-console of ISE (Integrated Scripting Environment) in Windows moeilijk zijn, zoals de locatie wordt verplaatst van één versie van Windows naar de volgende.</span><span class="sxs-lookup"><span data-stu-id="df7ae-113">Sometimes locating PowerShell console or ISE (Integrated Scripting Environment) in Windows can be difficult, as it's location moves from one version of Windows to the next.</span></span>

<span data-ttu-id="df7ae-114">De volgende tabellen kunt u PowerShell niet vinden in uw Windows-versie.</span><span class="sxs-lookup"><span data-stu-id="df7ae-114">The following tables should help you find PowerShell in your Windows version.</span></span>
<span data-ttu-id="df7ae-115">Alle versies die hier zijn de oorspronkelijke versie als vrijgegeven met geen updates.</span><span class="sxs-lookup"><span data-stu-id="df7ae-115">All versions listed here are the original version, as released, with no updates.</span></span>

### <a name="for-console"></a><span data-ttu-id="df7ae-116">Voor de Console</span><span class="sxs-lookup"><span data-stu-id="df7ae-116">For Console</span></span>

<span data-ttu-id="df7ae-117">Versie</span><span class="sxs-lookup"><span data-stu-id="df7ae-117">Version</span></span> | <span data-ttu-id="df7ae-118">Locatie</span><span class="sxs-lookup"><span data-stu-id="df7ae-118">Location</span></span>
-- | --
<span data-ttu-id="df7ae-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="df7ae-119">Windows 10</span></span> | <span data-ttu-id="df7ae-120">Klik op pictogram linksboven lagere hoek Windows, begint te typen van PowerShell</span><span class="sxs-lookup"><span data-stu-id="df7ae-120">Click left lower corner Windows icon, start typing PowerShell</span></span>
<span data-ttu-id="df7ae-121">Windows 8.1, 8.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-121">Windows 8.1, 8.0</span></span> | <span data-ttu-id="df7ae-122">Start PowerShell te typen op het startscherm.</span><span class="sxs-lookup"><span data-stu-id="df7ae-122">On the start screen, start typing PowerShell.</span></span><br/><span data-ttu-id="df7ae-123">Als een waarde op het bureaublad, klikt u op links lagere hoek pictogram van Windows, begint te typen van PowerShell</span><span class="sxs-lookup"><span data-stu-id="df7ae-123">If on desktop, click left lower corner Windows icon, start typing PowerShell</span></span>
<span data-ttu-id="df7ae-124">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="df7ae-124">Windows 7 SP1</span></span> | <span data-ttu-id="df7ae-125">Klik op links lagere hoek Windows pictogram op de zoekopdracht vak begin typen PowerShell</span><span class="sxs-lookup"><span data-stu-id="df7ae-125">Click left lower corner Windows icon, on the search box start typing PowerShell</span></span>

### <a name="for-ise"></a><span data-ttu-id="df7ae-126">Voor ISE</span><span class="sxs-lookup"><span data-stu-id="df7ae-126">For ISE</span></span>

<span data-ttu-id="df7ae-127">Versie</span><span class="sxs-lookup"><span data-stu-id="df7ae-127">Version</span></span> | <span data-ttu-id="df7ae-128">Locatie</span><span class="sxs-lookup"><span data-stu-id="df7ae-128">Location</span></span>
-- | --
<span data-ttu-id="df7ae-129">Windows 10</span><span class="sxs-lookup"><span data-stu-id="df7ae-129">Windows 10</span></span> | <span data-ttu-id="df7ae-130">Klik op pictogram linksboven lagere hoek Windows, begint te typen ISE</span><span class="sxs-lookup"><span data-stu-id="df7ae-130">Click left lower corner Windows icon, start typing ISE</span></span>
<span data-ttu-id="df7ae-131">Windows 8.1, 8.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-131">Windows 8.1, 8.0</span></span> | <span data-ttu-id="df7ae-132">Typ op het startscherm **PowerShell ISE**.</span><span class="sxs-lookup"><span data-stu-id="df7ae-132">On the start screen, type **PowerShell ISE**.</span></span><br/><span data-ttu-id="df7ae-133">Als op bureaublad, klikt u op lagere hoek Windows pictogram, typ **PowerShell ISE**</span><span class="sxs-lookup"><span data-stu-id="df7ae-133">If on desktop, click left lower corner Windows icon, type **PowerShell ISE**</span></span>
<span data-ttu-id="df7ae-134">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="df7ae-134">Windows 7 SP1</span></span> | <span data-ttu-id="df7ae-135">Klik op links lagere hoek Windows pictogram op de zoekopdracht vak begin typen PowerShell</span><span class="sxs-lookup"><span data-stu-id="df7ae-135">Click left lower corner Windows icon, on the search box start typing PowerShell</span></span>

## <a name="finding-powershell-in-windows-server-versions"></a><span data-ttu-id="df7ae-136">Het vinden van PowerShell in Windows Server-versies</span><span class="sxs-lookup"><span data-stu-id="df7ae-136">Finding PowerShell in Windows Server versions</span></span>

<span data-ttu-id="df7ae-137">Beginnen met Windows Server 2008 R2, worden Windows-besturingssysteem geïnstalleerd zonder de grafische gebruikersinterface (GUI).</span><span class="sxs-lookup"><span data-stu-id="df7ae-137">Starting with Windows Server 2008 R2, Windows operating system can be installed without the graphical user interface (GUI).</span></span>
<span data-ttu-id="df7ae-138">Versies van Windows Server zonder de gebruikersinterface zijn benoemde **Core** versies en edities met de gebruikersinterface zijn benoemde **bureaublad**.</span><span class="sxs-lookup"><span data-stu-id="df7ae-138">Editions of Windows Server without GUI are named **Core** editions, and editions with the GUI are named **Desktop**.</span></span>

### <a name="windows-server-core-editions"></a><span data-ttu-id="df7ae-139">Windows Server Core-versies</span><span class="sxs-lookup"><span data-stu-id="df7ae-139">Windows Server Core editions</span></span>

<span data-ttu-id="df7ae-140">In alle edities van de Core, wanneer u zich bij de server aanmeldt krijgt u een Windows-opdrachtpromptvenster.</span><span class="sxs-lookup"><span data-stu-id="df7ae-140">In all Core editions, when you log to the server you get a Windows command prompt window.</span></span>

<span data-ttu-id="df7ae-141">Type `powershell` en druk op **ENTER** PowerShell starten binnen de opdrachtpromptsessie.</span><span class="sxs-lookup"><span data-stu-id="df7ae-141">Type `powershell` and press **ENTER** to start PowerShell inside the command prompt session.</span></span> <span data-ttu-id="df7ae-142">Type `exit` de PowerShell-sessie te beëindigen en terugkeren naar de opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="df7ae-142">Type `exit` to terminate the PowerShell session and return to command prompt.</span></span>

### <a name="windows-server-desktop-editions"></a><span data-ttu-id="df7ae-143">Bureaublad van Windows Server-edities</span><span class="sxs-lookup"><span data-stu-id="df7ae-143">Windows Server Desktop editions</span></span>

<span data-ttu-id="df7ae-144">In alle edities van bureaublad, klik op het pictogram links lagere hoek Windows, begint te typen van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df7ae-144">In all desktop editions, click the left lower corner Windows icon, start typing PowerShell.</span></span>
<span data-ttu-id="df7ae-145">Krijgt u zowel de console en de ISE-opties.</span><span class="sxs-lookup"><span data-stu-id="df7ae-145">You get both console and ISE options.</span></span>

<span data-ttu-id="df7ae-146">De enige uitzondering aan de bovenstaande regel is de ISE in Windows Server 2008 R2 SP1; in dit geval, klik op het pictogram links lagere hoek Windows, typ PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="df7ae-146">The only exception to the above rule is the ISE in Windows Server 2008 R2 SP1; in this case, click the left lower corner Windows icon, type PowerShell ISE.</span></span>

## <a name="how-to-check-the-version-of-powershell"></a><span data-ttu-id="df7ae-147">Het controleren van de versie van PowerShell</span><span class="sxs-lookup"><span data-stu-id="df7ae-147">How to check the version of PowerShell</span></span>

<span data-ttu-id="df7ae-148">Als u wilt zoeken op welke versie van PowerShell die u hebt geïnstalleerd, start u een PowerShell-console (of de ISE) en type `$PSVersionTable` en druk op **ENTER**.</span><span class="sxs-lookup"><span data-stu-id="df7ae-148">To find which version of PowerShell you have installed, start a PowerShell console (or the ISE) and type `$PSVersionTable` and press **ENTER**.</span></span>

## <a name="upgrading-existing-windows-powershell"></a><span data-ttu-id="df7ae-149">Upgraden van bestaande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df7ae-149">Upgrading existing Windows PowerShell</span></span>

<span data-ttu-id="df7ae-150">Het installatiepakket voor PowerShell wordt geleverd in een installatieprogramma WMF.</span><span class="sxs-lookup"><span data-stu-id="df7ae-150">The installation package for PowerShell comes inside a WMF installer.</span></span>
<span data-ttu-id="df7ae-151">De versie van het installatieprogramma WMF overeenkomt met de versie van PowerShell; Er is geen zelfstandige installatieprogramma voor Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df7ae-151">The version of the WMF installer matches the version of PowerShell; there's no stand alone installer for Windows PowerShell.</span></span>

<span data-ttu-id="df7ae-152">Als u wilt bijwerken van uw huidige versie van PowerShell in Windows gebruik u de volgende tabel om te vinden van het installatieprogramma voor de versie van PowerShell die u bijwerken wilt naar.</span><span class="sxs-lookup"><span data-stu-id="df7ae-152">If you need to update your existing version of PowerShell, in Windows, use the following table to locate the installer for the version of PowerShell you want to update to.</span></span>

<span data-ttu-id="df7ae-153">Windows</span><span class="sxs-lookup"><span data-stu-id="df7ae-153">Windows</span></span> | <span data-ttu-id="df7ae-154">PS 3.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-154">PS 3.0</span></span> | <span data-ttu-id="df7ae-155">PS 4.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-155">PS 4.0</span></span> | <span data-ttu-id="df7ae-156">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-156">PS 5.0</span></span> | <span data-ttu-id="df7ae-157">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="df7ae-157">PS 5.1</span></span> |
--|--|--|--|--|
<span data-ttu-id="df7ae-158">Windows 10 (Zie Note1)</span><span class="sxs-lookup"><span data-stu-id="df7ae-158">Windows 10 (see Note1)</span></span><br/><span data-ttu-id="df7ae-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="df7ae-159">Windows Server 2016</span></span> | - | - | - | <span data-ttu-id="df7ae-160">geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="df7ae-160">installed</span></span>
<span data-ttu-id="df7ae-161">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="df7ae-161">Windows 8.1</span></span><br/><span data-ttu-id="df7ae-162">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="df7ae-162">Windows Server 2012 R2</span></span> | - | <span data-ttu-id="df7ae-163">geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="df7ae-163">installed</span></span> | [<span data-ttu-id="df7ae-164">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-164">WMF 5.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [<span data-ttu-id="df7ae-165">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="df7ae-165">WMF 5.1</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
<span data-ttu-id="df7ae-166">Windows 8</span><span class="sxs-lookup"><span data-stu-id="df7ae-166">Windows 8</span></span><br/><span data-ttu-id="df7ae-167">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="df7ae-167">Windows Server 2012</span></span> | <span data-ttu-id="df7ae-168">geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="df7ae-168">installed</span></span> | [<span data-ttu-id="df7ae-169">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-169">WMF 4.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [<span data-ttu-id="df7ae-170">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-170">WMF 5.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [<span data-ttu-id="df7ae-171">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="df7ae-171">WMF 5.1</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
<span data-ttu-id="df7ae-172">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="df7ae-172">Windows 7 SP1</span></span><br/><span data-ttu-id="df7ae-173">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="df7ae-173">Windows Server 2008 R2 SP1</span></span> | [<span data-ttu-id="df7ae-174">WMF 3.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-174">WMF 3.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=34595) | [<span data-ttu-id="df7ae-175">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-175">WMF 4.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [<span data-ttu-id="df7ae-176">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="df7ae-176">WMF 5.0</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [<span data-ttu-id="df7ae-177">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="df7ae-177">WMF 5.1</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54616)

> <span data-ttu-id="df7ae-178">**Opmerking 1**:</span><span class="sxs-lookup"><span data-stu-id="df7ae-178">**Note 1**:</span></span>
  >>
  >> <span data-ttu-id="df7ae-179">Op de eerste release van Windows 10, met automatische updates is ingeschakeld, wordt PowerShell van versie 5.0-5.1 bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="df7ae-179">On the initial release of Windows 10, with automatic updates enabled, PowerShell gets updated from version 5.0 to 5.1.</span></span>
  >>
  >> <span data-ttu-id="df7ae-180">Als de oorspronkelijke versie van Windows 10 niet via de Windows-Updates bijgewerkt is, is de versie van PowerShell 5.0.</span><span class="sxs-lookup"><span data-stu-id="df7ae-180">If the original version of Windows 10 is not updated through Windows Updates, the version of PowerShell is 5.0.</span></span>

## <a name="need-azure-powershell"></a><span data-ttu-id="df7ae-181">Moet u Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="df7ae-181">Need Azure PowerShell</span></span>

<span data-ttu-id="df7ae-182">Als u zoekt **Azure PowerShell**, kan worden gestart met [overzicht van Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure).</span><span class="sxs-lookup"><span data-stu-id="df7ae-182">If you're looking for **Azure PowerShell**, you could start with [Overview of Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure).</span></span>

<span data-ttu-id="df7ae-183">Wat u moet mogelijk anders is [installeren en configureren van Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps)</span><span class="sxs-lookup"><span data-stu-id="df7ae-183">Otherwise, what you might need is [Install and configure Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps)</span></span>

## <a name="see-also"></a><span data-ttu-id="df7ae-184">Zie ook</span><span class="sxs-lookup"><span data-stu-id="df7ae-184">See Also</span></span>

- [<span data-ttu-id="df7ae-185">Systeemvereisten voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df7ae-185">Windows PowerShell System Requirements</span></span>](Windows-PowerShell-System-Requirements.md)
- [<span data-ttu-id="df7ae-186">Windows PowerShell starten</span><span class="sxs-lookup"><span data-stu-id="df7ae-186">Starting Windows PowerShell</span></span>](Starting-Windows-PowerShell.md)