---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: PerformRequiredConfigurationChecks-methode van de klasse MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 26110b3920104da7343b8d55cf63440c12accbbc
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="performrequiredconfigurationchecks-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="1b6e5-103">PerformRequiredConfigurationChecks-methode van de klasse MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="1b6e5-103">PerformRequiredConfigurationChecks method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="1b6e5-104">Een consistentiecontrole begint met het gebruik van Taakplanner.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-104">Starts a consistency check by using the Task Scheduler.</span></span>

<a name="syntax"></a><span data-ttu-id="1b6e5-105">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="1b6e5-105">Syntax</span></span>
------

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

<a name="parameters"></a><span data-ttu-id="1b6e5-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="1b6e5-106">Parameters</span></span>
----------

<span data-ttu-id="1b6e5-107">*Vlaggen* \[in\]</span><span class="sxs-lookup"><span data-stu-id="1b6e5-107">*Flags* \[in\]</span></span>  
<span data-ttu-id="1b6e5-108">Een bitmasker waarmee het type van een consistentiecontrole uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-108">A bitmask that specifies the type of consistency check to run.</span></span> <span data-ttu-id="1b6e5-109">De volgende waarden geldig zijn en kunnen worden gecombineerd met behulp van een bitwise **of** bewerking:</span><span class="sxs-lookup"><span data-stu-id="1b6e5-109">The following values are valid, and can be combined by using a bitwise **OR** operation:</span></span>

|<span data-ttu-id="1b6e5-110">Value</span><span class="sxs-lookup"><span data-stu-id="1b6e5-110">Value</span></span> |<span data-ttu-id="1b6e5-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1b6e5-111">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="1b6e5-112">**1**</span><span class="sxs-lookup"><span data-stu-id="1b6e5-112">**1**</span></span> | <span data-ttu-id="1b6e5-113">Een normale consistentiecontrole.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-113">A normal consistency check.</span></span> |
|<span data-ttu-id="1b6e5-114">**2**</span><span class="sxs-lookup"><span data-stu-id="1b6e5-114">**2**</span></span> | <span data-ttu-id="1b6e5-115">Een vervolg van een consistentiecontrole uit na het opnieuw opstarten.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-115">A continuation of a consistency check after a reboot.</span></span> <span data-ttu-id="1b6e5-116">Deze waarde moet niet worden gecombineerd met andere waarden.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-116">This value should not be combined with other values.</span></span> |
|<span data-ttu-id="1b6e5-117">**4**</span><span class="sxs-lookup"><span data-stu-id="1b6e5-117">**4**</span></span> | <span data-ttu-id="1b6e5-118">De configuratie moet worden opgehaald uit de pull-server die is opgegeven in de metaconfiguratie voor het knooppunt.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-118">The configuration should be pulled from the pull server specified in the metaconfiguration for the node.</span></span> <span data-ttu-id="1b6e5-119">Deze waarde moet altijd worden gecombineerd met **1**, voor een waarde van **5**.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-119">This value should always be combined with **1**, for a value of **5**.</span></span> |
|<span data-ttu-id="1b6e5-120">**8**</span><span class="sxs-lookup"><span data-stu-id="1b6e5-120">**8**</span></span> | <span data-ttu-id="1b6e5-121">Status verzenden naar de rapportserver.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-121">Send status to the report server.</span></span> |

## <a name="return-value"></a><span data-ttu-id="1b6e5-122">Retourwaarde</span><span class="sxs-lookup"><span data-stu-id="1b6e5-122">Return value</span></span>
------------

<span data-ttu-id="1b6e5-123">Retourneert nul geslaagd; Anders retourneert een foutcode.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-123">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b6e5-124">Opmerkingen</span><span class="sxs-lookup"><span data-stu-id="1b6e5-124">Remarks</span></span>

<span data-ttu-id="1b6e5-125">Dit is een statische methode.</span><span class="sxs-lookup"><span data-stu-id="1b6e5-125">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1b6e5-126">Vereisten</span><span class="sxs-lookup"><span data-stu-id="1b6e5-126">Requirements</span></span>
------------
><span data-ttu-id="1b6e5-127">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="1b6e5-127">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="1b6e5-128">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="1b6e5-128">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="1b6e5-129">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1b6e5-129">See also</span></span>


[<span data-ttu-id="1b6e5-130">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="1b6e5-130">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 


