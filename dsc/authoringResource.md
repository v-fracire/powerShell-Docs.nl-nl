---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: Aangepaste Windows PowerShell Desired State Configuration Resources bouwen
ms.openlocfilehash: 75b494db4ee6e381491decb11d35b60105217a0f
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a><span data-ttu-id="569f2-103">Aangepaste Windows PowerShell Desired State Configuration Resources bouwen</span><span class="sxs-lookup"><span data-stu-id="569f2-103">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>

> <span data-ttu-id="569f2-104">Van toepassing op: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="569f2-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="569f2-105">Windows PowerShell Desired State Configuration (DSC) met de ingebouwde resources die u gebruiken kunt om uw omgeving te configureren.</span><span class="sxs-lookup"><span data-stu-id="569f2-105">Windows PowerShell Desired State Configuration (DSC) has built-in resources that you can use to configure your environment.</span></span> <span data-ttu-id="569f2-106">(Zie voor meer informatie [ingebouwde Windows PowerShell Desired status configuratie-bronnen](builtInResource.md).) In dit onderwerp biedt een overzicht van het ontwikkelen van resources en koppelingen naar onderwerpen met specifieke informatie over en voorbeelden.</span><span class="sxs-lookup"><span data-stu-id="569f2-106">(For more information, see [Built-In Windows PowerShell Desired State Configuration Resources](builtInResource.md).) This topic provides an overview of developing resources and links to topics with specific information and examples.</span></span>

## <a name="dsc-resource-components"></a><span data-ttu-id="569f2-107">Onderdelen van DSC-resource</span><span class="sxs-lookup"><span data-stu-id="569f2-107">DSC resource components</span></span>

<span data-ttu-id="569f2-108">Een DSC-resource is een Windows PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="569f2-108">A DSC resource is a Windows PowerShell module.</span></span> <span data-ttu-id="569f2-109">De module bevat zowel het schema (de definitie van de configureerbare eigenschappen) en de implementatie (de code die het echte werk verricht dat door een opgegeven) voor de resource.</span><span class="sxs-lookup"><span data-stu-id="569f2-109">The module contains both the schema (the definition of the configurable properties) and the implementation (the code that does the actual work specified by a configuration) for the resource.</span></span> <span data-ttu-id="569f2-110">Een DSC-resource schema kan worden gedefinieerd in een MOF-bestand en de implementatie wordt uitgevoerd door een scriptmodule.</span><span class="sxs-lookup"><span data-stu-id="569f2-110">A DSC resource schema can be defined in a MOF file, and the implementation is performed by a script module.</span></span> <span data-ttu-id="569f2-111">U begint met de ondersteuning van PowerShell-klassen in versie 5, kunnen het schema en de implementatie zowel worden gedefinieerd in een klasse.</span><span class="sxs-lookup"><span data-stu-id="569f2-111">Beginning with the support of PowerShell classes in version 5, the schema and implementation can both be defined in a class.</span></span> <span data-ttu-id="569f2-112">De volgende onderwerpen wordt beschreven in meer detail DSC-resources te maken.</span><span class="sxs-lookup"><span data-stu-id="569f2-112">The following topics describe in more detail how to create DSC resources.</span></span>

* [<span data-ttu-id="569f2-113">Schrijven van een aangepaste DSC-resource met MOF</span><span class="sxs-lookup"><span data-stu-id="569f2-113">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md) 
* [<span data-ttu-id="569f2-114">Implementatie van een DSC-resource in C#</span><span class="sxs-lookup"><span data-stu-id="569f2-114">Implementing a DSC resource in C#</span></span>](authoringResourceMofCS.md) 
* [<span data-ttu-id="569f2-115">Schrijven van een aangepaste DSC-resource met PowerShell-klassen</span><span class="sxs-lookup"><span data-stu-id="569f2-115">Writing a custom DSC resource with PowerShell classes</span></span>](authoringResourceClass.md) 
* [<span data-ttu-id="569f2-116">Samengestelde bronnen: met een DSC-configuratie als een bron</span><span class="sxs-lookup"><span data-stu-id="569f2-116">Composite resources: Using a DSC configuration as a resource</span></span>](authoringResourceComposite.md) 
* [<span data-ttu-id="569f2-117">Het hulpprogramma voor het Resource-Designer</span><span class="sxs-lookup"><span data-stu-id="569f2-117">Using the Resource Designer tool</span></span>](authoringResourceMofDesigner.md) 
