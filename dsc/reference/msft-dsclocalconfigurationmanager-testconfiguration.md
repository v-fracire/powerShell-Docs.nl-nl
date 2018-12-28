---
ms.date: 06/12/2017
keywords: DSC, powershell, configuratie en installatie
title: De TestConfiguration-methode van de klasse MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: d746832b01310f43a7aae33dd0fa70c0928bb3e0
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2018
ms.locfileid: "53404438"
---
# <a name="testconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="72098-103">De TestConfiguration-methode van de klasse MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="72098-103">TestConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="72098-104">Het configuratiebestand voor verzendt naar de beheerd knooppunt en controleert of de huidige configuratie op basis van het document.</span><span class="sxs-lookup"><span data-stu-id="72098-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="72098-105">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="72098-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="72098-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="72098-106">Parameters</span></span>

<span data-ttu-id="72098-107">*configurationData* \[in\] omgevingsgegevens voor de confuguration.</span><span class="sxs-lookup"><span data-stu-id="72098-107">*configurationData* \[in\] Environment data for the confuguration.</span></span>

<span data-ttu-id="72098-108">*InDesiredState* \[uit\] bij resultaat, geeft aan of de beheerde knooppunt in de status die is opgegeven door het configuratiebestand.</span><span class="sxs-lookup"><span data-stu-id="72098-108">*InDesiredState* \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="72098-109">*ResourcesInDesiredState* \[uit\] bij resultaat, bevat een ingesloten exemplaar van de **MSFT_ResourceInDesiredState** klasse waarmee bronnen die zich in de gewenste status.</span><span class="sxs-lookup"><span data-stu-id="72098-109">*ResourcesInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="72098-110">*ResourcesNotInDesiredState* \[uit\] bij resultaat, bevat een ingesloten exemplaar van de **MSFT_ResourceNotInDesiredState** klasse die Hiermee geeft u de resources die zich niet in de gewenste status.</span><span class="sxs-lookup"><span data-stu-id="72098-110">*ResourcesNotInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="72098-111">Retourwaarde</span><span class="sxs-lookup"><span data-stu-id="72098-111">Return value</span></span>

<span data-ttu-id="72098-112">Retourneert nul op succes; Anders retourneert een foutcode.</span><span class="sxs-lookup"><span data-stu-id="72098-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="72098-113">Opmerkingen</span><span class="sxs-lookup"><span data-stu-id="72098-113">Remarks</span></span>

<span data-ttu-id="72098-114">Dit is een statische methode.</span><span class="sxs-lookup"><span data-stu-id="72098-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="72098-115">Vereisten</span><span class="sxs-lookup"><span data-stu-id="72098-115">Requirements</span></span>

<span data-ttu-id="72098-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="72098-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="72098-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="72098-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="72098-118">Zie ook</span><span class="sxs-lookup"><span data-stu-id="72098-118">See also</span></span>

[<span data-ttu-id="72098-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="72098-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)