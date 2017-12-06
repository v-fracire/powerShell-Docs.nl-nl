---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: DSC-PackageManagement Resource
ms.openlocfilehash: a984fbf5db561a696d89b60dde8b92096c6e4924
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-packagemanagement-resource"></a><span data-ttu-id="9f134-103">DSC-PackageManagement Resource</span><span class="sxs-lookup"><span data-stu-id="9f134-103">DSC PackageManagement Resource</span></span>

> <span data-ttu-id="9f134-104">Van toepassing op: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="9f134-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="9f134-105">De **PackageManagement** in Windows PowerShell Desired State Configuration (DSC)-bron biedt een mechanisme om te installeren of verwijderen van pakketten in een doelknooppunt Package Management.</span><span class="sxs-lookup"><span data-stu-id="9f134-105">The **PackageManagement** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Package Management packages on a target node.</span></span> <span data-ttu-id="9f134-106">Deze resource vereist de **PackageManagement** module beschikbaar is via http://PowerShellGallery.com.</span><span class="sxs-lookup"><span data-stu-id="9f134-106">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f134-107">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="9f134-107">Syntax</span></span>

```
PackageManagement [string] #ResourceName
{
    Name = [string]
    [ Source = [string] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ RequiredVersion = [string] ]
    [ MinimumVersion = [string] ]
    [ MaximumVersion = [string] ]
    [ SourceCredential = [PSCredential] ]
    [ ProviderName = [string] ]
    [ AdditionalParameters = [Microsoft.Management.Infrastructure.CimInstance[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="9f134-108">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="9f134-108">Properties</span></span>
|  <span data-ttu-id="9f134-109">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="9f134-109">Property</span></span>  |  <span data-ttu-id="9f134-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="9f134-110">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="9f134-111">Naam</span><span class="sxs-lookup"><span data-stu-id="9f134-111">Name</span></span>| <span data-ttu-id="9f134-112">Hiermee geeft u de naam van het pakket dat moet worden geïnstalleerd of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9f134-112">Specifies the name of the Package to be installed or uninstalled.</span></span>| 
| <span data-ttu-id="9f134-113">Bron</span><span class="sxs-lookup"><span data-stu-id="9f134-113">Source</span></span>| <span data-ttu-id="9f134-114">Hiermee geeft u de naam van de pakketbron waar het pakket kan worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="9f134-114">Specifies the name of the package source where the package can be found.</span></span> <span data-ttu-id="9f134-115">Dit kan een URI of een bron die is geregistreerd bij registreren PackageSource of PackageManagementSource DSC-resource.</span><span class="sxs-lookup"><span data-stu-id="9f134-115">This can either be a URI or a source registered with Register-PackageSource or PackageManagementSource DSC resource.</span></span> <span data-ttu-id="9f134-116">De DSC-resource MSFT_PackageManagementSource kunt ook een pakketbron registreren.</span><span class="sxs-lookup"><span data-stu-id="9f134-116">The DSC resource MSFT_PackageManagementSource can also register a package source.</span></span>| 
| <span data-ttu-id="9f134-117">Zorg ervoor dat</span><span class="sxs-lookup"><span data-stu-id="9f134-117">Ensure</span></span>| <span data-ttu-id="9f134-118">Bepaalt of het pakket moet worden geïnstalleerd of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9f134-118">Determines whether the package is to be installed or uninstalled.</span></span>| 
| <span data-ttu-id="9f134-119">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="9f134-119">RequiredVersion</span></span>| <span data-ttu-id="9f134-120">Hiermee geeft u de exacte versie van het pakket dat u wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="9f134-120">Specifies the exact version of the package that you want to install.</span></span> <span data-ttu-id="9f134-121">Als u deze parameter niet opgeeft, wordt de nieuwste versie van het pakket dat ook voldoet aan alle maximale versie van het opgegeven met de parameter MaximumVersion geïnstalleerd in deze DSC-resource.</span><span class="sxs-lookup"><span data-stu-id="9f134-121">If you do not specify this parameter, this DSC resource installs the newest available version of the package that also satisfies any maximum version specified by the MaximumVersion parameter.</span></span>| 
| <span data-ttu-id="9f134-122">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="9f134-122">MinimumVersion</span></span>| <span data-ttu-id="9f134-123">Hiermee geeft u de minimaal toegestane versie van het pakket dat u wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="9f134-123">Specifies the minimum allowed version of the package that you want to install.</span></span> <span data-ttu-id="9f134-124">Als u deze parameter niet toevoegt, wordt deze DSC-resource intalls de hoogste versie van het pakket dat ook voldoet aan alle maximale versie van het opgegeven opgegeven door de parameter MaximumVersion.</span><span class="sxs-lookup"><span data-stu-id="9f134-124">If you do not add this parameter, this DSC resource intalls the highest available version of the package that also satisfies any maximum specified version specified by the MaximumVersion parameter.</span></span>| 
| <span data-ttu-id="9f134-125">MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="9f134-125">MaximumVersion</span></span>| <span data-ttu-id="9f134-126">Hiermee geeft u de maximaal toegestane versie van het pakket dat u wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="9f134-126">Specifies the maximum allowed version of the package that you want to install.</span></span> <span data-ttu-id="9f134-127">Als u deze parameter niet opgeeft, installeert deze DSC-resource de hoogste nummer beschikbare versie van het pakket.</span><span class="sxs-lookup"><span data-stu-id="9f134-127">If you do not specify this parameter, this DSC resource installs the highest-numbered available version of the package.</span></span>| 
| <span data-ttu-id="9f134-128">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="9f134-128">SourceCredential</span></span> | <span data-ttu-id="9f134-129">Hiermee geeft u een gebruikersaccount met rechten voor het installeren van een pakket voor een opgegeven pakket-provider of de bron.</span><span class="sxs-lookup"><span data-stu-id="9f134-129">Specifies a user account that has rights to install a package for a specified package provider or source.</span></span>| 
| <span data-ttu-id="9f134-130">ProviderName</span><span class="sxs-lookup"><span data-stu-id="9f134-130">ProviderName</span></span>| <span data-ttu-id="9f134-131">Hiermee geeft u een providernaam pakket waarnaar als bereik voor uw zoekopdracht pakket.</span><span class="sxs-lookup"><span data-stu-id="9f134-131">Specifies a package provider name to which to scope your package search.</span></span> <span data-ttu-id="9f134-132">U kunt providernamen pakket ophalen door de cmdlet Get-PackageProvider.</span><span class="sxs-lookup"><span data-stu-id="9f134-132">You can get package provider names by running the Get-PackageProvider cmdlet.</span></span>| 
| <span data-ttu-id="9f134-133">AdditionalParameters</span><span class="sxs-lookup"><span data-stu-id="9f134-133">AdditionalParameters</span></span>| <span data-ttu-id="9f134-134">Provider specifieke parameters die worden doorgegeven als een hashtabel.</span><span class="sxs-lookup"><span data-stu-id="9f134-134">Provider specific parameters that are passed as an Hashtable.</span></span> <span data-ttu-id="9f134-135">U kunt bijvoorbeeld aanvullende parameters zoals doelpad doorgeven voor NuGet-provider.</span><span class="sxs-lookup"><span data-stu-id="9f134-135">For example, for NuGet provider you can pass additional parameters like DestinationPath.</span></span>| 

## <a name="additional-parameters"></a><span data-ttu-id="9f134-136">Extra Parameters</span><span class="sxs-lookup"><span data-stu-id="9f134-136">Additional Parameters</span></span>
<span data-ttu-id="9f134-137">De volgende tabel geeft een lijst met opties voor de eigenschap AdditionalParameters.</span><span class="sxs-lookup"><span data-stu-id="9f134-137">The following table lists options for the AdditionalParameters property.</span></span>
|  <span data-ttu-id="9f134-138">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f134-138">Parameter</span></span>  | <span data-ttu-id="9f134-139">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="9f134-139">Description</span></span>   | 
|---|---|
| <span data-ttu-id="9f134-140">Doelpad</span><span class="sxs-lookup"><span data-stu-id="9f134-140">DestinationPath</span></span>| <span data-ttu-id="9f134-141">Gebruikt door providers zoals de ingebouwde Nuget-Provider.</span><span class="sxs-lookup"><span data-stu-id="9f134-141">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="9f134-142">Hiermee geeft u een locatie waar u het pakket worden geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="9f134-142">Specifies a file location where you want the package to be installed.</span></span>|
| <span data-ttu-id="9f134-143">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="9f134-143">InstallationPolicy</span></span>| <span data-ttu-id="9f134-144">Gebruikt door providers zoals de ingebouwde Nuget-Provider.</span><span class="sxs-lookup"><span data-stu-id="9f134-144">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="9f134-145">Hiermee bepaalt u of u het pakket bron vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="9f134-145">Determines whether you trust the package's source.</span></span> <span data-ttu-id="9f134-146">Een van: 'Niet vertrouwd', 'Vertrouwd'.</span><span class="sxs-lookup"><span data-stu-id="9f134-146">One of: "Untrusted", "Trusted".</span></span>|

## <a name="example"></a><span data-ttu-id="9f134-147">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="9f134-147">Example</span></span>

<span data-ttu-id="9f134-148">Dit voorbeeld installeert de **JQuery** NuGet-pakket en **GistProvider** PowerShell module met behulp van de **PackageManagement** DSC-resource.</span><span class="sxs-lookup"><span data-stu-id="9f134-148">This example installs the **JQuery** NuGet package and **GistProvider** PowerShell module using the **PackageManagement** DSC resource.</span></span> <span data-ttu-id="9f134-149">In dit voorbeeld eerst zorgt ervoor dat de vereiste pakket bronnen beschikbaar zijn en vervolgens definieert de verwachte status van de **JQuery** en **GistProvider** pakketten (NuGet en PowerShell, respectievelijk).</span><span class="sxs-lookup"><span data-stu-id="9f134-149">This example first ensures the required package sources are available then defines the expected state of the **JQuery** and **GistProvider** packages (NuGet and PowerShell, respectively).</span></span>

```powershell
Configuration PackageTest
{    
    PackageManagementSource SourceRepository 
    { 
        Ensure      = "Present" 
        Name        = "MyNuget" 
        ProviderName= "Nuget" 
        SourceUri   = "http://nuget.org/api/v2/"   
        InstallationPolicy ="Trusted" 
    }    
    
    PackageManagementSource PSGallery 
    { 
        Ensure      = "Present" 
        Name        = "psgallery" 
        ProviderName= "PowerShellGet" 
        SourceUri   = "https://www.powershellgallery.com/api/v2/"   
        InstallationPolicy ="Trusted" 
    } 
          
    PackageManagement NugetPackage 
    { 
        Ensure               = "Present"  
        Name                 = "JQuery"
        AdditionalParameters = "$env:HomeDrive\nuget"
        RequiredVersion      = "2.0.1" 
        DependsOn            = "[PackageManagementSource]SourceRepository" 
    }
    
    PackageManagement PSModule 
    { 
        Ensure               = "Present"  
        Name                 = "gistprovider"
        Source               = "PSGallery"
        DependsOn            = "[PackageManagementSource]PSGallery" 
    }
}
```
