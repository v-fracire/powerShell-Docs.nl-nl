---
ms.date: 06/05/2017
keywords: PowerShell-cmdlet
title: De Windows PowerShell 2.0-engine installeren
ms.assetid: 82928f2b-f96a-4ae6-a0d0-6e7b181da308
ms.openlocfilehash: b625b61b4e191402074f57ea2e942f800dbbcd53
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2018
ms.locfileid: "53404313"
---
# <a name="installing-the-windows-powershell-20-engine"></a><span data-ttu-id="99354-103">De Windows PowerShell 2.0-engine installeren</span><span class="sxs-lookup"><span data-stu-id="99354-103">Installing the Windows PowerShell 2.0 Engine</span></span>
<span data-ttu-id="99354-104">In dit onderwerp wordt uitgelegd hoe u de Windows PowerShell 2.0-Engine installeren.</span><span class="sxs-lookup"><span data-stu-id="99354-104">This topic explains how to install the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="99354-105">Windows PowerShell 3.0 is ontworpen om te worden ook compatibel met Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="99354-105">Windows PowerShell 3.0 is designed to be backwards compatible with Windows PowerShell 2.0.</span></span> <span data-ttu-id="99354-106">-Cmdlets, providers, -modules, modules en scripts die zijn geschreven voor Windows PowerShell 2.0 uitvoeren in Windows PowerShell 3.0 en Windows PowerShell 4.0 ongewijzigd.</span><span class="sxs-lookup"><span data-stu-id="99354-106">Cmdlets, providers, snap-ins, modules, and scripts written for Windows PowerShell 2.0 run unchanged in Windows PowerShell 3.0 and Windows PowerShell 4.0.</span></span> <span data-ttu-id="99354-107">Echter, vanwege een wijziging in het beleid van de runtime-activering in Microsoft .NET Framework 4, Windows PowerShell-host-programma's die zijn geschreven voor Windows PowerShell 2.0 en gecompileerd met Common Language Runtime (CLR) 2.0 kunnen niet worden uitgevoerd zonder aanpassingen in later versies van Windows PowerShell, die is gecompileerd met CLR-4.0.</span><span class="sxs-lookup"><span data-stu-id="99354-107">However, due to a change in the runtime activation policy in Microsoft .NET Framework 4, Windows PowerShell host programs that were written for Windows PowerShell 2.0 and compiled with Common Language Runtime (CLR) 2.0 cannot run without modification in later releases of Windows PowerShell, which is compiled with CLR 4.0.</span></span>

<span data-ttu-id="99354-108">Als u wilt behouden voor achterwaartse compatibiliteit met opdrachten en host-programma's die worden beïnvloed door deze wijzigingen, worden de engines voor Windows PowerShell 2.0, Windows PowerShell 3.0 en Windows PowerShell 4.0 ontworpen om uit te voeren side-by-side.</span><span class="sxs-lookup"><span data-stu-id="99354-108">To maintain backward compatibility with commands and host programs that are affected by these changes, the Windows PowerShell 2.0, Windows PowerShell 3.0, and Windows PowerShell 4.0 engines are designed to run side-by-side.</span></span> <span data-ttu-id="99354-109">De Windows PowerShell 2.0-Engine is ook opgenomen in Windows Server 2012 R2, Windows 8.1, Windows 8, Windows Server 2012 en Windows Management Framework 3.0.</span><span class="sxs-lookup"><span data-stu-id="99354-109">Also, the Windows PowerShell 2.0 Engine is included in Windows Server 2012 R2, Windows 8.1, Windows 8, Windows Server 2012, and Windows Management Framework 3.0.</span></span> <span data-ttu-id="99354-110">De Windows PowerShell 2.0-Engine moet worden gebruikt alleen wanneer een bestaand script is bedoeld of hostprogramma kan niet worden uitgevoerd omdat deze niet compatibel met Windows PowerShell 3.0, Windows PowerShell 4.0 of Microsoft .NET Framework 4 is.</span><span class="sxs-lookup"><span data-stu-id="99354-110">The Windows PowerShell 2.0 Engine is intended to be used only when an existing script or host program cannot run because it is incompatible with Windows PowerShell 3.0, Windows PowerShell 4.0, or Microsoft .NET Framework 4.</span></span> <span data-ttu-id="99354-111">Dergelijke gevallen wordt wordt een zeldzaam verwacht.</span><span class="sxs-lookup"><span data-stu-id="99354-111">Such cases are expected to be rare.</span></span>

<span data-ttu-id="99354-112">De Windows PowerShell 2.0-Engine is een optionele functie van Windows Server 2012 R2, Windows 8.1, Windows® 8 en Windows Server® 2012.</span><span class="sxs-lookup"><span data-stu-id="99354-112">The Windows PowerShell 2.0 Engine is an optional feature of Windows Server 2012 R2, Windows 8.1, Windows® 8 and Windows Server® 2012.</span></span> <span data-ttu-id="99354-113">In eerdere versies van Windows tijdens de installatie van Windows Management Framework 3.0, vervangt de installatie van Windows PowerShell 3.0 volledig de Windows PowerShell 2.0-installatie in de installatiemap van Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99354-113">On earlier versions of Windows, when you install Windows Management Framework 3.0, the Windows PowerShell 3.0 installation completely replaces the Windows PowerShell 2.0 installation in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="99354-114">De Windows PowerShell 2.0-Engine wordt echter bewaard.</span><span class="sxs-lookup"><span data-stu-id="99354-114">However, the Windows PowerShell 2.0 Engine is retained.</span></span>

<span data-ttu-id="99354-115">Zie voor meer informatie over het starten van de Windows PowerShell 2.0-Engine [vanaf de Windows PowerShell 2.0-Engine](../getting-started/Starting-the-Windows-PowerShell-2.0-Engine.md).</span><span class="sxs-lookup"><span data-stu-id="99354-115">For information about starting the Windows PowerShell 2.0 Engine, see [Starting the Windows PowerShell 2.0 Engine](../getting-started/Starting-the-Windows-PowerShell-2.0-Engine.md).</span></span>

## <a name="on-windows-81-and-windows-8"></a><span data-ttu-id="99354-116">Op Windows 8.1 en Windows 8</span><span class="sxs-lookup"><span data-stu-id="99354-116">On Windows 8.1 and Windows 8</span></span>
<span data-ttu-id="99354-117">Op Windows 8.1 en Windows 8, is de Windows PowerShell 2.0-Engine-functie standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="99354-117">On Windows 8.1 and Windows 8, the Windows PowerShell 2.0 Engine feature is turned on by default.</span></span> <span data-ttu-id="99354-118">Als u wilt gebruiken, moet u echter de optie inschakelen voor Microsoft .NET Framework 3.5, die vereist is.</span><span class="sxs-lookup"><span data-stu-id="99354-118">However, to use it, you need to turn on the option for Microsoft .NET Framework 3.5, which it requires.</span></span> <span data-ttu-id="99354-119">In deze sectie wordt ook uitgelegd hoe u de Windows PowerShell 2.0-Engine-functie inschakelen in of uit.</span><span class="sxs-lookup"><span data-stu-id="99354-119">This section also explains how to turn the Windows PowerShell 2.0 Engine feature on and off.</span></span>

#### <a name="to-turn-on-net-framework-35"></a><span data-ttu-id="99354-120">.NET Framework 3.5 inschakelen</span><span class="sxs-lookup"><span data-stu-id="99354-120">To turn on .NET Framework 3.5</span></span>

1. <span data-ttu-id="99354-121">Op de **Start** scherm, typt u **Windows functies**.</span><span class="sxs-lookup"><span data-stu-id="99354-121">On the **Start** screen, type **Windows Features**.</span></span>

2. <span data-ttu-id="99354-122">Op de **Apps** klikt u op **instellingen**, en klik vervolgens op **schakelt u Windows-onderdelen in- of uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="99354-122">On the **Apps** bar, click **Settings**, and then click **Turn Windows features on or off**.</span></span>

3. <span data-ttu-id="99354-123">In de **Windows functies** Klik **.NET Framework 3.5 (inclusief .NET 2.0 en 3.0** om deze te selecteren.</span><span class="sxs-lookup"><span data-stu-id="99354-123">In the **Windows Features** box, click **.NET Framework 3.5 (includes .NET 2.0 and 3.0** to select it.</span></span>

    <span data-ttu-id="99354-124">Wanneer u selecteert **.NET Framework 3.5 (inclusief .NET 2.0 en 3.0**, het vak ingevuld om aan te geven dat slechts een deel van de functie is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="99354-124">When you select **.NET Framework 3.5 (includes .NET 2.0 and 3.0**, the box fills to indicate that only part of the feature is selected.</span></span> <span data-ttu-id="99354-125">Dit is echter voldoende voor de Windows PowerShell 2.0-Engine.</span><span class="sxs-lookup"><span data-stu-id="99354-125">However, this is sufficient for the Windows PowerShell 2.0 Engine.</span></span>

#### <a name="to-turn-the-windows-powershell-20-engine-on-and-off"></a><span data-ttu-id="99354-126">Om in te schakelen van de Windows PowerShell 2.0-Engine in- en uitschakelen</span><span class="sxs-lookup"><span data-stu-id="99354-126">To turn the Windows PowerShell 2.0 Engine on and off</span></span>

1. <span data-ttu-id="99354-127">Op de **Start** scherm, typt u **Windows functies**.</span><span class="sxs-lookup"><span data-stu-id="99354-127">On the **Start** screen, type **Windows Features**.</span></span>

2. <span data-ttu-id="99354-128">Op de **Apps** klikt u op **instellingen**, en klik vervolgens op **schakelt u Windows-onderdelen in- of uitschakelen**.</span><span class="sxs-lookup"><span data-stu-id="99354-128">On the **Apps** bar, click **Settings**, and then click **Turn Windows features on or off**.</span></span>

3. <span data-ttu-id="99354-129">In de **Windows functies** Vouw de **Windows PowerShell 2.0** knooppunt en klik op de **Windows PowerShell 2.0-Engine** in om te selecteren in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="99354-129">In the **Windows Features** box, expand the **Windows PowerShell 2.0** node, and click the **Windows PowerShell 2.0 Engine** box to select or clear it.</span></span>

## <a name="on-windows-server-2012-r2-and-windows-server-2012"></a><span data-ttu-id="99354-130">Op Windows Server 2012 R2 en WindowsServer 2012</span><span class="sxs-lookup"><span data-stu-id="99354-130">On Windows Server 2012 R2 and Windows Server 2012</span></span>
<span data-ttu-id="99354-131">Gebruik de volgende procedures voor de Windows PowerShell 2.0-Engine en Microsoft .NET Framework 3.5-onderdelen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="99354-131">Use the following procedures to add the Windows PowerShell 2.0 Engine and Microsoft .NET Framework 3.5 features.</span></span> <span data-ttu-id="99354-132">De Windows PowerShell 2.0-Engine is Microsoft .NET Framework, 2.0.50727 ten minste vereist.</span><span class="sxs-lookup"><span data-stu-id="99354-132">The Windows PowerShell 2.0 Engine requires Microsoft .NET Framework 2.0.50727 at a minimum.</span></span> <span data-ttu-id="99354-133">Deze vereiste wordt voldaan door Microsoft .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="99354-133">This requirement is fulfilled by Microsoft .NET Framework 3.5.</span></span>

#### <a name="to-add-the-net-framework-35-feature"></a><span data-ttu-id="99354-134">De functie .NET Framework 3.5 toe te voegen</span><span class="sxs-lookup"><span data-stu-id="99354-134">To add the .NET Framework 3.5 feature</span></span>

1. <span data-ttu-id="99354-135">In **Serverbeheer**, uit de **beheren** in het menu **functies en onderdelen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="99354-135">In **Server Manager**, from the **Manage** menu, select **Add Roles and Features**.</span></span>

    <span data-ttu-id="99354-136">Of in **Serverbeheer**, klikt u op **alle Servers**, met de rechtermuisknop op de naam van een server en selecteer vervolgens **functies en onderdelen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="99354-136">Or in **Server Manager**, click **All Servers**, right-click a server name, and then select **Add Roles and Features**.</span></span>

2. <span data-ttu-id="99354-137">Op de **installatietype** weergeeft, schakelt **op basis van functie of onderdeel gebaseerde installatie**.</span><span class="sxs-lookup"><span data-stu-id="99354-137">On the **Installation Type** page, select **Role-based or feature-based installation**.</span></span>

3. <span data-ttu-id="99354-138">Op de **functies** pagina uit, vouw de **.NET Framework 3.5-onderdelen** knooppunt en selecteert u **.NET Framework 3.5 (inclusief .NET 2.0 en 3.0)**.</span><span class="sxs-lookup"><span data-stu-id="99354-138">On the **Features** page, expand the **.NET 3.5 Framework Features** node and select **.NET Framework 3.5 (includes .NET 2.0 and 3.0)**.</span></span>

    <span data-ttu-id="99354-139">De andere opties onder dat knooppunt zijn niet vereist voor de Windows PowerShell 2.0-Engine.</span><span class="sxs-lookup"><span data-stu-id="99354-139">The other options under that node are not required for the Windows PowerShell 2.0 Engine.</span></span>

#### <a name="to-add-the-windows-powershell-20-engine-feature"></a><span data-ttu-id="99354-140">De Windows PowerShell 2.0-Engine-functie toe te voegen</span><span class="sxs-lookup"><span data-stu-id="99354-140">To add the Windows PowerShell 2.0 Engine feature</span></span>

- <span data-ttu-id="99354-141">In **Serverbeheer**, uit de **beheren** in het menu **functies en onderdelen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="99354-141">In **Server Manager**, from the **Manage** menu, select **Add Roles and Features**.</span></span>

    <span data-ttu-id="99354-142">Of **Serverbeheer**, klikt u op **alle Servers**, met de rechtermuisknop op de naam van een server en selecteer vervolgens **functies en onderdelen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="99354-142">Or **Server Manager**, click **All Servers**, right-click a server name, and then select **Add Roles and Features**.</span></span>

- <span data-ttu-id="99354-143">Op de **installatietype** weergeeft, schakelt **op basis van functie of onderdeel gebaseerde installatie**.</span><span class="sxs-lookup"><span data-stu-id="99354-143">On the **Installation Type** page, select **Role-based or feature-based installation**.</span></span>

- <span data-ttu-id="99354-144">Op de **functies** pagina uit, vouw de **Windows PowerShell (geïnstalleerd)** knooppunt en selecteert u **Windows PowerShell 2.0-Engine**.</span><span class="sxs-lookup"><span data-stu-id="99354-144">On the **Features** page, expand the **Windows PowerShell (Installed)** node and select **Windows PowerShell 2.0 Engine**.</span></span>

<span data-ttu-id="99354-145">Zie voor meer informatie over het starten van de Windows PowerShell 2.0-Engine [vanaf de Windows PowerShell 2.0-Engine](../getting-started/Starting-the-Windows-PowerShell-2.0-Engine.md).</span><span class="sxs-lookup"><span data-stu-id="99354-145">For information about starting the Windows PowerShell 2.0 Engine, see [Starting the Windows PowerShell 2.0 Engine](../getting-started/Starting-the-Windows-PowerShell-2.0-Engine.md).</span></span>

## <a name="on-earlier-systems"></a><span data-ttu-id="99354-146">Op oudere systemen</span><span class="sxs-lookup"><span data-stu-id="99354-146">On Earlier Systems</span></span>
<span data-ttu-id="99354-147">De [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkID=293881) -pakket voor Windows PowerShell 4.0 op Windows 7, Windows Server 2008 R2 en Windows Server 2012 installeren bevat de Windows PowerShell 2.0-Engine.</span><span class="sxs-lookup"><span data-stu-id="99354-147">The [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkID=293881) package that installs Windows PowerShell 4.0 on Windows 7, Windows Server 2008 R2, and Windows Server 2012, includes the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="99354-148">De Windows PowerShell 2.0-Engine is ingeschakeld en gereed voor gebruik, indien nodig, zonder aanvullende installatie, installatie of configuratie.</span><span class="sxs-lookup"><span data-stu-id="99354-148">The Windows PowerShell 2.0 Engine is enabled and ready to use, if necessary, without additional installation, setup, or configuration.</span></span>

<span data-ttu-id="99354-149">Het pakket Windows Management Framework 3.0 voor Windows PowerShell 3.0 op Windows 7, Windows Server 2008 R2 en Windows Server 2008 installeert, bevat de Windows PowerShell 2.0-Engine.</span><span class="sxs-lookup"><span data-stu-id="99354-149">The Windows Management Framework 3.0 package that installs Windows PowerShell 3.0 on Windows 7, Windows Server 2008 R2, and Windows Server 2008, includes the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="99354-150">De Windows PowerShell 2.0-Engine is ingeschakeld en gereed voor gebruik, indien nodig, zonder aanvullende installatie, installatie of configuratie.</span><span class="sxs-lookup"><span data-stu-id="99354-150">The Windows PowerShell 2.0 Engine is enabled and ready to use, if necessary, without additional installation, setup, or configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="99354-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="99354-151">See Also</span></span>
- [<span data-ttu-id="99354-152">Windows PowerShell-systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="99354-152">Windows PowerShell System Requirements</span></span>](Windows-PowerShell-System-Requirements.md)
- [<span data-ttu-id="99354-153">Windows PowerShell installeren</span><span class="sxs-lookup"><span data-stu-id="99354-153">Installing Windows PowerShell</span></span>](Installing-Windows-PowerShell.md)
- [<span data-ttu-id="99354-154">Windows PowerShell starten</span><span class="sxs-lookup"><span data-stu-id="99354-154">Starting Windows PowerShell</span></span>](https://technet.microsoft.com/en-us/library/8ec8c2d7-8e7c-4722-a3d2-498fe5739a8e)
- [<span data-ttu-id="99354-155">De Windows PowerShell 2.0-engine starten</span><span class="sxs-lookup"><span data-stu-id="99354-155">Starting the Windows PowerShell 2.0 Engine</span></span>](../getting-started/Starting-the-Windows-PowerShell-2.0-Engine.md)