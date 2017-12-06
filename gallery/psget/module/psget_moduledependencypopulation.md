---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: Galerie, powershell, cmdlet, psget
title: psget_moduledependencypopulation
ms.openlocfilehash: 126cd65ac35a31f4118474bc36dac1836ec0f22e
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="logic-for-preparing-the-module-dependencies-during-publish-operation"></a><span data-ttu-id="d794f-103">Logica voor het voorbereiden van de module afhankelijkheden tijdens publicatiebewerking</span><span class="sxs-lookup"><span data-stu-id="d794f-103">Logic for preparing the module dependencies during Publish operation</span></span>
1.  <span data-ttu-id="d794f-104">Modules die worden vermeld als deel van RequiredModules worden beschouwd als afhankelijkheden.</span><span class="sxs-lookup"><span data-stu-id="d794f-104">Modules listed as part of RequiredModules are considered as dependencies.</span></span>
2.  <span data-ttu-id="d794f-105">Modules die worden vermeld als deel van NestedModules, waarvan base module bevindt zich niet onder de opgegeven module base, worden beschouwd als afhankelijkheden.</span><span class="sxs-lookup"><span data-stu-id="d794f-105">Modules listed as part of NestedModules, whose module base is not under the specified module base, are considered as dependencies.</span></span>

3.  <span data-ttu-id="d794f-106">Hierboven afhankelijkheden moet beschikbaar zijn in de doelopslagplaats met hetzelfde, anders publiceren bewerking leidt tot een fout opgetreden.</span><span class="sxs-lookup"><span data-stu-id="d794f-106">Above dependencies should be available on the same target repository, otherwise publish operation will result in an error.</span></span>
    <span data-ttu-id="d794f-107">Bijvoorbeeld: als 'SnippetPx' niet beschikbaar in de opslagplaats is, hieronder fout gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="d794f-107">For example: If 'SnippetPx' is not available on the repository, below error will be thrown.</span></span>
    ```powershell
    Publish-PSArtifactUtility : PowerShellGet cannot resolve the module dependency 'SnippetPx' of the module 'TypePx' on the repository 'LocalRepo'. Verify that the dependent module 'SnippetPx' is available in the repository 'LocalRepo'. If this dependent
    'SnippetPx' is managed externally, add it to the ExternalModuleDependencies entry in the PSData section of the module manifest.
    ```
4.  <span data-ttu-id="d794f-108">Enkele afhankelijkheden module extern kunnen worden beheerd, in dat geval ze moeten worden toegevoegd aan de vermelding ExternalModuleDependencies in de sectie PSData van de module-manifest.</span><span class="sxs-lookup"><span data-stu-id="d794f-108">Some module dependencies can be managed externally, in that case they should be added to the ExternalModuleDependencies entry in the PSData section of the module manifest.</span></span>
    <span data-ttu-id="d794f-109">Hieronder onderdeel in het bovenstaande foutbericht</span><span class="sxs-lookup"><span data-stu-id="d794f-109">Below part in the above error message</span></span>
    ```powershell
    If this dependent 'SnippetPx' is managed externally, add it to the ExternalModuleDependencies entry in the PSData section of the module manifest.
    ```

<span data-ttu-id="d794f-110">*Tijdens de installatie van de beleidsmodule hierboven voorbereide afhankelijkheden wordt lijst gebruikt voor het installeren van de afhankelijkheden.*</span><span class="sxs-lookup"><span data-stu-id="d794f-110">*During the module installation, above prepared dependencies list is used for installing the dependencies.*</span></span>

<span data-ttu-id="d794f-111">*Zorg ervoor dat uw module afhankelijkheden beschikbaar onder $env zijn: PSModulePath op uw systeem tijdens de bewerking publiceren.*</span><span class="sxs-lookup"><span data-stu-id="d794f-111">*Please ensure that your module’s dependencies are available under $env:PSModulePath on your system during publish operation.*</span></span>
