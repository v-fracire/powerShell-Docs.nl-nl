---
ms.date: 06/05/2017
keywords: PowerShell-cmdlet
title: Windows PowerShell starten
ms.assetid: 59b649a2-c90c-4cf4-bf95-a740c59148e7
ms.openlocfilehash: 9184e8b0e508610e7f4775f1032f3a69c93bb8c1
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2018
ms.locfileid: "53404446"
---
# <a name="starting-windows-powershell"></a><span data-ttu-id="289b8-103">Windows PowerShell starten</span><span class="sxs-lookup"><span data-stu-id="289b8-103">Starting Windows PowerShell</span></span>
<span data-ttu-id="289b8-104">PowerShell is een scripting engine dll die is ingesloten in meerdere hosts.</span><span class="sxs-lookup"><span data-stu-id="289b8-104">PowerShell is a scripting engine dll which is embedded into multiple hosts.</span></span>  <span data-ttu-id="289b8-105">De meest voorkomende host die u wilt beginnen zijn de interactieve opdrachtregel PowerShell.exe en de interactieve Scripting omgeving PowerShell_ISE.exe.</span><span class="sxs-lookup"><span data-stu-id="289b8-105">The most common host you will start are the interactive command line PowerShell.exe and the Interactive Scripting Environment PowerShell_ISE.exe.</span></span>

<span data-ttu-id="289b8-106">Zie voor informatie over het starten van Windows PowerShell® op Windows Server® 2012 R2, Windows® 8.1, Windows Server 2012 en Windows 8 [Common Management Tasks and Navigation](https://technet.microsoft.com/library/hh831491.aspx).</span><span class="sxs-lookup"><span data-stu-id="289b8-106">To start Windows PowerShell® on Windows Server® 2012 R2, Windows® 8.1, Windows Server 2012, and Windows 8, see [Common Management Tasks and Navigation](https://technet.microsoft.com/library/hh831491.aspx).</span></span>

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="289b8-107">Starten van Windows PowerShell op oudere versies van Windows</span><span class="sxs-lookup"><span data-stu-id="289b8-107">How to Start Windows PowerShell on Earlier Versions of Windows</span></span>

<span data-ttu-id="289b8-108">In deze sectie wordt uitgelegd hoe u start Windows PowerShell en Windows PowerShell Integrated Scripting Environment (ISE) op Windows® 7, Windows Server® 2008 R2 en Windows Server® 2008.</span><span class="sxs-lookup"><span data-stu-id="289b8-108">This section explains how to start Windows PowerShell and Windows PowerShell Integrated Scripting Environment (ISE) on Windows® 7, Windows Server® 2008 R2, and Windows Server® 2008.</span></span> <span data-ttu-id="289b8-109">Hierin wordt ook uitgelegd hoe u de optionele functie inschakelt voor Windows PowerShell ISE in Windows PowerShell 2.0 op Windows Server® 2008 R2 en Windows Server® 2008.</span><span class="sxs-lookup"><span data-stu-id="289b8-109">It also explains how to enable the optional feature for Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server® 2008 R2 and Windows Server® 2008.</span></span>

<span data-ttu-id="289b8-110">Een van de volgende methoden gebruiken om te beginnen de geïnstalleerde versie van Windows PowerShell 3.0 of 4.0 voor Windows PowerShell, indien van toepassing.</span><span class="sxs-lookup"><span data-stu-id="289b8-110">Use any of the following methods to start the installed version of Windows PowerShell 3.0, or Windows PowerShell 4.0, where applicable.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="289b8-111">Vanuit het startmenu</span><span class="sxs-lookup"><span data-stu-id="289b8-111">From the Start Menu</span></span>

- <span data-ttu-id="289b8-112">Klik op **Start**, type **PowerShell**, en klik vervolgens op **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="289b8-112">Click **Start**, type **PowerShell**, and then click **Windows PowerShell**.</span></span>
- <span data-ttu-id="289b8-113">Uit de **Start** menu, klikt u op **Start**, klikt u op **alle programma's**, klikt u op **accessoires**, klikt u op de **Windows PowerShell**  map en klik vervolgens op **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="289b8-113">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="289b8-114">Bij de opdrachtprompt</span><span class="sxs-lookup"><span data-stu-id="289b8-114">At the Command Prompt</span></span>

<span data-ttu-id="289b8-115">In Cmd.exe, de Windows PowerShell of Windows PowerShell ISE, voor het starten van Windows PowerShell, typt u:</span><span class="sxs-lookup"><span data-stu-id="289b8-115">In Cmd.exe, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell
```

<span data-ttu-id="289b8-116">U kunt de parameters van het programma PowerShell.exe ook gebruiken om aan te passen van de sessie.</span><span class="sxs-lookup"><span data-stu-id="289b8-116">You can also use the parameters of the PowerShell.exe program to customize the session.</span></span> <span data-ttu-id="289b8-117">Zie voor meer informatie, [PowerShell.exe-opdrachtregel Help](../core-powershell/console/PowerShell.exe-Command-Line-Help.md).</span><span class="sxs-lookup"><span data-stu-id="289b8-117">For more information, see [PowerShell.exe Command-Line Help](../core-powershell/console/PowerShell.exe-Command-Line-Help.md).</span></span>

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="289b8-118">Met Administrative bevoegdheden ('als administrator uitvoeren")</span><span class="sxs-lookup"><span data-stu-id="289b8-118">With Administrative privileges ("Run as administrator")</span></span>

<span data-ttu-id="289b8-119">Klik op **Start**, type **PowerShell**, met de rechtermuisknop op **Windows PowerShell**, en klik vervolgens op **als administrator uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="289b8-119">Click **Start**, type **PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="289b8-120">Windows PowerShell ISE starten op eerdere versies van Windows</span><span class="sxs-lookup"><span data-stu-id="289b8-120">How to Start Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="289b8-121">Gebruik een van de volgende methoden om te starten van Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="289b8-121">Use any of the following methods to start Windows PowerShell ISE.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="289b8-122">Vanuit het startmenu</span><span class="sxs-lookup"><span data-stu-id="289b8-122">From the Start Menu</span></span>

- <span data-ttu-id="289b8-123">Klik op **Start**, type **ISE**, en klik vervolgens op **Windows PowerShell ISE**.</span><span class="sxs-lookup"><span data-stu-id="289b8-123">Click **Start**, type **ISE**, and then click **Windows PowerShell ISE**.</span></span>
- <span data-ttu-id="289b8-124">Uit de **Start** menu, klikt u op **Start**, klikt u op **alle programma's**, klikt u op **accessoires**, klikt u op de **Windows PowerShell**  map en klik vervolgens op **Windows PowerShell ISE**.</span><span class="sxs-lookup"><span data-stu-id="289b8-124">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell ISE**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="289b8-125">Bij de opdrachtprompt</span><span class="sxs-lookup"><span data-stu-id="289b8-125">At the Command Prompt</span></span>

<span data-ttu-id="289b8-126">In Cmd.exe, de Windows PowerShell of Windows PowerShell ISE, voor het starten van Windows PowerShell, typt u:</span><span class="sxs-lookup"><span data-stu-id="289b8-126">In Cmd.exe, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell_ISE
```

<span data-ttu-id="289b8-127">of</span><span class="sxs-lookup"><span data-stu-id="289b8-127">or</span></span>

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="289b8-128">Met Administrative bevoegdheden ('als administrator uitvoeren")</span><span class="sxs-lookup"><span data-stu-id="289b8-128">With Administrative privileges ("Run as administrator")</span></span>

<span data-ttu-id="289b8-129">Klik op **Start**, type **ISE**, met de rechtermuisknop op **Windows PowerShell ISE**, en klik vervolgens op **als administrator uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="289b8-129">Click **Start**, type **ISE**, right-click **Windows PowerShell ISE**, and then click **Run as administrator**.</span></span>

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="289b8-130">Windows PowerShell ISE op eerdere versies van Windows inschakelen</span><span class="sxs-lookup"><span data-stu-id="289b8-130">How to Enable Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="289b8-131">In Windows PowerShell 4.0 en Windows PowerShell 3.0, is Windows PowerShell ISE standaard ingeschakeld op alle versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="289b8-131">In Windows PowerShell 4.0 and Windows PowerShell 3.0, Windows PowerShell ISE is enabled by default on all versions of Windows.</span></span> <span data-ttu-id="289b8-132">Als deze nog niet is ingeschakeld, Windows Management Framework 4.0 of Windows Management Framework 3.0 ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="289b8-132">If it is not already enabled, Windows Management Framework 4.0 or Windows Management Framework 3.0 enables it.</span></span>

<span data-ttu-id="289b8-133">In Windows PowerShell 2.0, is Windows PowerShell ISE standaard ingeschakeld op Windows 7.</span><span class="sxs-lookup"><span data-stu-id="289b8-133">In Windows PowerShell 2.0, Windows PowerShell ISE is enabled by default on Windows 7.</span></span> <span data-ttu-id="289b8-134">Op Windows Server 2008 R2 en Windows Server 2008 is het echter een optionele functie.</span><span class="sxs-lookup"><span data-stu-id="289b8-134">However, on Windows Server 2008 R2 and Windows Server 2008, it is an optional feature.</span></span>

<span data-ttu-id="289b8-135">Gebruik de volgende procedure om in te schakelen in Windows PowerShell ISE in Windows PowerShell 2.0 op Windows Server 2008 R2 of Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="289b8-135">To enable Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server 2008 R2 or Windows Server 2008, use the following procedure.</span></span>

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="289b8-136">Om in te schakelen van Windows PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="289b8-136">To enable Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

1. <span data-ttu-id="289b8-137">Start Serverbeheer.</span><span class="sxs-lookup"><span data-stu-id="289b8-137">Start Server Manager.</span></span>
2. <span data-ttu-id="289b8-138">Klik op **functies** en klik vervolgens op **onderdelen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="289b8-138">Click **Features** and then click **Add Features**.</span></span>
3. <span data-ttu-id="289b8-139">Klik in onderdelen selecteren op de Windows PowerShell Integrated Scripting Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="289b8-139">In Select Features, click Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="starting-the-32-bit-version-of-windows-powershell"></a><span data-ttu-id="289b8-140">De 32-bits versie van Windows PowerShell starten</span><span class="sxs-lookup"><span data-stu-id="289b8-140">Starting the 32-Bit Version of Windows PowerShell</span></span>

<span data-ttu-id="289b8-141">Wanneer u Windows PowerShell op een 64-bits computer installeert **Windows PowerShell (x86)**, een 32-bits versie van Windows PowerShell is geïnstalleerd naast de 64-bits versie.</span><span class="sxs-lookup"><span data-stu-id="289b8-141">When you install Windows PowerShell on a 64-bit computer, **Windows PowerShell (x86)**, a 32-bit version of Windows PowerShell is installed in addition to the 64-bit version.</span></span> <span data-ttu-id="289b8-142">Wanneer u Windows PowerShell uitvoert, wordt standaard de 64-bits versie uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="289b8-142">When you run Windows PowerShell, the 64-bit version runs by default.</span></span>

<span data-ttu-id="289b8-143">Moet u mogelijk af en toe om uit te voeren **Windows PowerShell (x86)**, zoals wanneer u van een module gebruikmaakt die de 32-bits versie vereist of als u op afstand verbinding met een 32-bits computer.</span><span class="sxs-lookup"><span data-stu-id="289b8-143">However, you might occasionally need to run **Windows PowerShell (x86)**, such as when you are using a module that requires the 32-bit version or when you are connecting remotely to a 32-bit computer.</span></span>

<span data-ttu-id="289b8-144">Gebruik een van de volgende procedures voor het starten van een 32-bits versie van Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="289b8-144">To start a 32-bit version of Windows PowerShell, use any of the following procedures.</span></span>

#### <a name="in-windows-server-2012-r2"></a><span data-ttu-id="289b8-145">In Windows Server® 2012 R2</span><span class="sxs-lookup"><span data-stu-id="289b8-145">In Windows Server® 2012 R2</span></span>

- <span data-ttu-id="289b8-146">Op de **Start** scherm, typt u **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-146">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="289b8-147">Klik op de **Windows PowerShell x86** tegel.</span><span class="sxs-lookup"><span data-stu-id="289b8-147">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="289b8-148">In **Serverbeheer**, uit de **extra** in het menu **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-148">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-149">Op het bureaublad van de cursor verplaatsen naar de rechterbovenhoek, klikt u op **zoeken**, type **PowerShell x86** en klik vervolgens op **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-149">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-150">Via de opdrachtregel, typ: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="289b8-150">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-server-2012"></a><span data-ttu-id="289b8-151">In Windows Server® 2012</span><span class="sxs-lookup"><span data-stu-id="289b8-151">In Windows Server® 2012</span></span>

- <span data-ttu-id="289b8-152">Op de **Start** scherm, typt u **PowerShell** en klik vervolgens op **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-152">On the **Start** screen, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-153">In **Serverbeheer**, uit de **extra** in het menu **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-153">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-154">Op het bureaublad van de cursor verplaatsen naar de rechterbovenhoek, klikt u op **zoeken**, type **PowerShell** en klik vervolgens op **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-154">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-155">Via de opdrachtregel, typ: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="289b8-155">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-81"></a><span data-ttu-id="289b8-156">In Windows® 8.1</span><span class="sxs-lookup"><span data-stu-id="289b8-156">In Windows® 8.1</span></span>

- <span data-ttu-id="289b8-157">Op de **Start** scherm, typt u **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-157">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="289b8-158">Klik op de **Windows PowerShell x86** tegel.</span><span class="sxs-lookup"><span data-stu-id="289b8-158">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="289b8-159">Als u werkt met [Remote Server Administration Tools](https://go.microsoft.com/fwlink/?LinkID=304145) voor Windows 8.1, kunt u ook Windows PowerShell x86 vanuit openen de **Server ManagerTools** menu.</span><span class="sxs-lookup"><span data-stu-id="289b8-159">If you are running [Remote Server Administration Tools](https://go.microsoft.com/fwlink/?LinkID=304145) for Windows 8.1, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span>
  <span data-ttu-id="289b8-160">Selecteer **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-160">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-161">Op het bureaublad van de cursor verplaatsen naar de rechterbovenhoek, klikt u op **zoeken**, type **PowerShell x86** en klik vervolgens op **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-161">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-162">Via de opdrachtregel, typ: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="289b8-162">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-8"></a><span data-ttu-id="289b8-163">In Windows® 8</span><span class="sxs-lookup"><span data-stu-id="289b8-163">In Windows® 8</span></span>

- <span data-ttu-id="289b8-164">Op de **Start** scherm, plaatst u de cursor op de rechter bovenhoek, klikt u op **instellingen**, klikt u op **tegels**, sluiten en verplaatst u de **weergeven Systeembeheer** schuifregelaar op Ja.</span><span class="sxs-lookup"><span data-stu-id="289b8-164">On the **Start** screen, move the cursor to the upper right corner, click **Settings**, click **Tiles**, and then move the **Show Administrative Tools** slider to Yes.</span></span> <span data-ttu-id="289b8-165">Typ vervolgens **PowerShell** en klikt u op **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-165">Then, type **PowerShell** and click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-166">Als u werkt met [Remote Server Administration Tools](https://www.microsoft.com/download/details.aspx?id=28972) voor Windows 8, kunt u ook Windows PowerShell x86 vanuit openen de **Server ManagerTools** menu.</span><span class="sxs-lookup"><span data-stu-id="289b8-166">If you are running [Remote Server Administration Tools](https://www.microsoft.com/download/details.aspx?id=28972) for Windows 8, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="289b8-167">Selecteer **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-167">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-168">Op de **Start** scherm of het bureaublad, typt u **PowerShell (x86)** en klik vervolgens op **Windows PowerShell (x86)**.</span><span class="sxs-lookup"><span data-stu-id="289b8-168">On the **Start** screen or the desktop, type **PowerShell (x86)** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="289b8-169">Via de opdrachtregel, typ: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="289b8-169">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>