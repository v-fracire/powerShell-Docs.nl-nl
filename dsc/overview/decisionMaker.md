---
ms.date: 06/12/2017
keywords: DSC, powershell, configuratie en installatie
title: Overzicht Desired State Configuration voor besluitvormers
ms.openlocfilehash: ce554d4bb994d4b1816d9d9c24599e4ef0e1c593
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403952"
---
# <a name="desired-state-configuration-overview-for-decision-makers"></a><span data-ttu-id="d749e-103">Overzicht Desired State Configuration voor besluitvormers</span><span class="sxs-lookup"><span data-stu-id="d749e-103">Desired State Configuration Overview for Decision Makers</span></span>

<span data-ttu-id="d749e-104">Dit document beschrijft de zakelijke voordelen van het gebruik van Windows PowerShell Desired State Configuration (DSC).</span><span class="sxs-lookup"><span data-stu-id="d749e-104">This document describes the business benefits of using Windows PowerShell Desired State Configuration (DSC).</span></span> <span data-ttu-id="d749e-105">Het is niet een technische handleiding.</span><span class="sxs-lookup"><span data-stu-id="d749e-105">It is not a technical guide.</span></span>

## <a name="what-is-desired-state-configuration"></a><span data-ttu-id="d749e-106">Wat Is er Desired State Configuration?</span><span class="sxs-lookup"><span data-stu-id="d749e-106">What Is Desired State Configuration?</span></span>

<span data-ttu-id="d749e-107">PowerShell Desired State Configuration is een beheerplatform voor de configuratie die is ingebouwd in Windows die is gebaseerd op open standaarden.</span><span class="sxs-lookup"><span data-stu-id="d749e-107">PowerShell Desired State Configuration is a configuration management platform built into Windows that is based on open standards.</span></span> <span data-ttu-id="d749e-108">DSC is flexibel genoeg om betrouwbare en consistente manier werken in elke fase van de levenscyclus van de implementatie (ontwikkeling, testen, Pre-productie, productie), en tijdens de scale-out.</span><span class="sxs-lookup"><span data-stu-id="d749e-108">DSC is flexible enough to function reliably and consistently in each stage of the deployment lifecycle (development, test, pre-production, production), as well as during scale-out.</span></span>

<span data-ttu-id="d749e-109">DSC draait om [configuraties](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d749e-109">DSC centers around [configurations](../configurations/configurations.md).</span></span>
<span data-ttu-id="d749e-110">Een configuratie is een gemakkelijk leesbare-document met een beschrijving van een omgeving die bestaan uit computers ("knooppunten") met specifieke kenmerken.</span><span class="sxs-lookup"><span data-stu-id="d749e-110">A configuration is an easy-to-read document that describes an environment made up of computers ("nodes") with specific characteristics.</span></span>
<span data-ttu-id="d749e-111">Deze kenmerken kunnen worden net zo eenvoudig als u ervoor te zorgen dat een specifieke Windows-functie is ingeschakeld of een stuk complexer is zoals het implementeren van SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d749e-111">These characteristics can be as simple as ensuring a specific Windows feature is enabled or as complex as deploying SharePoint.</span></span>

<span data-ttu-id="d749e-112">DSC heeft ook bewaking en rapportage ingebouwd.</span><span class="sxs-lookup"><span data-stu-id="d749e-112">DSC also has monitoring and reporting built in.</span></span>
<span data-ttu-id="d749e-113">Als een systeem niet meer compatibel zijn is, kan DSC waarschuwen en Neem maatregelen om te corrigeren van het systeem.</span><span class="sxs-lookup"><span data-stu-id="d749e-113">If a system is no longer compliant, DSC can raise an alert and act to correct the system.</span></span>

## <a name="benefits-of-using-desired-state-configuration"></a><span data-ttu-id="d749e-114">Voordelen van het gebruik van Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="d749e-114">Benefits of Using Desired State Configuration</span></span>

<span data-ttu-id="d749e-115">Configuraties zijn ontworpen om gemakkelijk lezen, die zijn opgeslagen en bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="d749e-115">Configurations are designed to be easily read, stored, and updated.</span></span>
<span data-ttu-id="d749e-116">Configuraties declareren dat de doelapparaten status moeten zich in, in plaats van het schrijven van instructies voor het plaatsen die status hebben.</span><span class="sxs-lookup"><span data-stu-id="d749e-116">Configurations declare the state target devices should be in, instead of writing instructions for how to put them in that state.</span></span>
<span data-ttu-id="d749e-117">Hierdoor kunt u veel minder kostbaar zijn om te leren, vast, implementeren en onderhouden van de configuratie met behulp van DSC.</span><span class="sxs-lookup"><span data-stu-id="d749e-117">This makes it much less costly to learn, adopt, implement, and maintain configuration through DSC.</span></span>

<span data-ttu-id="d749e-118">Het maken van configuraties betekent dat complexe implementatiestappen worden vastgelegd als een 'één betrouwbare bron' op één locatie.</span><span class="sxs-lookup"><span data-stu-id="d749e-118">Creating configurations means that complex deployment steps are captured as a "single source of truth" in a single location.</span></span>
<span data-ttu-id="d749e-119">Hierdoor kunt u herhaalde implementaties van een specifieke set computers veel minder gevoelig voor fouten.</span><span class="sxs-lookup"><span data-stu-id="d749e-119">This makes repeated deployments of a specific set of machines much less error-prone.</span></span>
<span data-ttu-id="d749e-120">Op zijn beurt, waardoor implementaties sneller en betrouwbaarder waardoor een snelle doorlooptijd op complexe implementaties.</span><span class="sxs-lookup"><span data-stu-id="d749e-120">In turn, making deployments faster and more reliable which enables a quick turnaround on complex deployments.</span></span>

<span data-ttu-id="d749e-121">Er zijn ook configuraties deelbaar via de [PowerShell Gallery](https://powershellgallery.com) wat betekent dat algemene scenario's en aanbevolen procedures bestaat mogelijk al voor het werk dat moet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="d749e-121">Configurations are also shareable via the [PowerShell Gallery](https://powershellgallery.com) meaning common scenarios and best practices might already exist for the work that needs to be done.</span></span>


## <a name="desired-state-configuration-and-devops"></a><span data-ttu-id="d749e-122">Desired State Configuration en DevOps</span><span class="sxs-lookup"><span data-stu-id="d749e-122">Desired State Configuration and DevOps</span></span>

<span data-ttu-id="d749e-123">DSC is ontworpen met [DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx) Denk eraan dat u een combinatie van mensen, processen en hulpprogramma's die voor snelle implementatie en herhalen zeer zorgen gericht op het leveren van een waarde voor eindgebruikers, intern of extern.</span><span class="sxs-lookup"><span data-stu-id="d749e-123">DSC was designed with [DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx) in mind, a combination of people, processes, and tools that allow for rapid deployment and iteration focused on delivering value to end users whether internal or external.</span></span>
<span data-ttu-id="d749e-124">Met een configuratie voor één definiëren van een omgeving betekent dat ontwikkelaars kunnen hun vereisten in een configuratie met coderen, controleert u dat de configuratie in broncodebeheer en bewerking teams kan de implementatie eenvoudig code zonder te hoeven doorlopen gevoelig voor fouten handmatige processen.</span><span class="sxs-lookup"><span data-stu-id="d749e-124">Having a single configuration define an environment means that developers can encode their requirements into a configuration, check that configuration into source control, and operation teams can easily deploy code without having to go through error-prone manual processes.</span></span>

<span data-ttu-id="d749e-125">Firewallconfiguraties zijn ook [gegevensgestuurde](../configurations/configData.md), waardoor het gemakkelijker voor ops om te bepalen en omgevingen zonder tussenkomst van ontwikkelaars te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d749e-125">Configurations are also [data-driven](../configurations/configData.md), which makes it easier for ops to identify and change environments without developer intervention.</span></span>

## <a name="desired-state-configuration-on-premises-and-off-premises"></a><span data-ttu-id="d749e-126">On-Premises en buiten het bedrijf Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="d749e-126">Desired State Configuration On-Premises and Off-Premises</span></span>
<span data-ttu-id="d749e-127">DSC kan worden gebruikt voor het beheren van zowel on-premises en off-premises implementaties.</span><span class="sxs-lookup"><span data-stu-id="d749e-127">DSC can be used to manage both on-premise and off-premise deployments.</span></span>
<span data-ttu-id="d749e-128">Voor on-premises oplossingen, DSC heeft een [pull-server](../pull-server/pullServer.md) die kunnen worden gebruikt voor centraliseer het beheer van computers en rapporteren van hun status.</span><span class="sxs-lookup"><span data-stu-id="d749e-128">For on-premise solutions, DSC has a [pull server](../pull-server/pullServer.md) that can be used to centralize management of machines and report on their status.</span></span>
<span data-ttu-id="d749e-129">Voor cloudoplossingen kan DSC worden gebruikt waar Windows kan worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="d749e-129">For cloud solutions, DSC is usable wherever Windows is usable.</span></span>
<span data-ttu-id="d749e-130">Er zijn ook speciale aanbiedingen van Azure is gebouwd op Desired State Configuration, zoals [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/), die centraliseert rapportage van DSC.</span><span class="sxs-lookup"><span data-stu-id="d749e-130">There are also specific offerings from Azure built on Desired State Configuration, such as [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/), which centralizes reporting of DSC.</span></span>

## <a name="dsc-and-compatibility"></a><span data-ttu-id="d749e-131">DSC en compatibiliteit</span><span class="sxs-lookup"><span data-stu-id="d749e-131">DSC and Compatibility</span></span>

<span data-ttu-id="d749e-132">DSC werd geïntroduceerd in Windows Server 2012 R2, is het beschikbaar voor eerdere besturingssystemen via het pakket voor Windows Management Framework (WMF).</span><span class="sxs-lookup"><span data-stu-id="d749e-132">Although DSC was introduced in Windows Server 2012 R2, it is available for down-level operating systems via the Windows Management Framework (WMF) package.</span></span>
<span data-ttu-id="d749e-133">Meer informatie over de WMF vindt u op de [PowerShell startpagina](/powershell/).</span><span class="sxs-lookup"><span data-stu-id="d749e-133">More information about the WMF can be found on the [PowerShell homepage](/powershell/).</span></span>

<span data-ttu-id="d749e-134">DSC kan ook worden gebruikt voor het beheren van Linux.</span><span class="sxs-lookup"><span data-stu-id="d749e-134">DSC can also be used to manage Linux.</span></span> <span data-ttu-id="d749e-135">Zie voor meer informatie, [aan de slag met DSC voor Linux](../getting-started/lnxGettingStarted.md).</span><span class="sxs-lookup"><span data-stu-id="d749e-135">For more information, see [Getting Started with DSC for Linux](../getting-started/lnxGettingStarted.md).</span></span>