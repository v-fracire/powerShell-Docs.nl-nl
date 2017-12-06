---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: Bron van het DSC-Service
ms.openlocfilehash: 611729e5d971ebaf15ac947454cffadc6797927b
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-service-resource"></a><span data-ttu-id="ac657-103">Bron van het DSC-Service</span><span class="sxs-lookup"><span data-stu-id="ac657-103">DSC Service Resource</span></span>

> <span data-ttu-id="ac657-104">Van toepassing op: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ac657-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>


<span data-ttu-id="ac657-105">De **Service** in Windows PowerShell Desired State Configuration (DSC)-bron biedt een mechanisme voor het beheren van services in het doelknooppunt.</span><span class="sxs-lookup"><span data-stu-id="ac657-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac657-106">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="ac657-106">Syntax</span></span>

```
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Path = [string] ]
}
```

## <a name="properties"></a><span data-ttu-id="ac657-107">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="ac657-107">Properties</span></span>

|  <span data-ttu-id="ac657-108">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="ac657-108">Property</span></span>  |  <span data-ttu-id="ac657-109">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ac657-109">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="ac657-110">Naam</span><span class="sxs-lookup"><span data-stu-id="ac657-110">Name</span></span>| <span data-ttu-id="ac657-111">Geeft de servicenaam.</span><span class="sxs-lookup"><span data-stu-id="ac657-111">Indicates the service name.</span></span> <span data-ttu-id="ac657-112">Houd er rekening mee dat soms dit van de weergegeven naam verschilt.</span><span class="sxs-lookup"><span data-stu-id="ac657-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="ac657-113">U kunt een lijst van de services en de huidige staat met de cmdlet Get-Service ophalen.</span><span class="sxs-lookup"><span data-stu-id="ac657-113">You can get a list of the services and their current state with the Get-Service cmdlet.</span></span>| 
| <span data-ttu-id="ac657-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="ac657-114">BuiltInAccount</span></span>| <span data-ttu-id="ac657-115">Hiermee geeft u het account aanmelden om te gebruiken voor de service.</span><span class="sxs-lookup"><span data-stu-id="ac657-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="ac657-116">De waarden die zijn toegestaan voor deze eigenschap zijn: **LocalService**, **LocalSystem**, en **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="ac657-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span>| 
| <span data-ttu-id="ac657-117">referentie</span><span class="sxs-lookup"><span data-stu-id="ac657-117">Credential</span></span>| <span data-ttu-id="ac657-118">Hiermee geeft u referenties voor het account waaronder de service wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ac657-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="ac657-119">Deze eigenschap en de __BuiltinAccount__ eigenschap kan niet samen worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ac657-119">This property and the __BuiltinAccount__ property cannot be used together.</span></span>| 
| <span data-ttu-id="ac657-120">dependsOn</span><span class="sxs-lookup"><span data-stu-id="ac657-120">DependsOn</span></span>| <span data-ttu-id="ac657-121">Hiermee wordt aangegeven dat de configuratie van een andere resource uitvoeren moet voordat deze bron is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="ac657-121">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="ac657-122">Bijvoorbeeld, als de ID van de resourceconfiguratie scriptblok die u wilt uitvoeren eerst is __ResourceName__ en het type __ResourceType__, de syntaxis voor het gebruik van deze eigenschap is `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="ac657-122">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 
| <span data-ttu-id="ac657-123">StartupType</span><span class="sxs-lookup"><span data-stu-id="ac657-123">StartupType</span></span>| <span data-ttu-id="ac657-124">Hiermee geeft het opstarttype voor de service.</span><span class="sxs-lookup"><span data-stu-id="ac657-124">Indicates the startup type for the service.</span></span> <span data-ttu-id="ac657-125">De waarden die zijn toegestaan voor deze eigenschap zijn: **automatische**, **uitgeschakelde**, en **handmatig**</span><span class="sxs-lookup"><span data-stu-id="ac657-125">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**</span></span>| 
| <span data-ttu-id="ac657-126">Status</span><span class="sxs-lookup"><span data-stu-id="ac657-126">State</span></span>| <span data-ttu-id="ac657-127">Geeft de status die u wilt zorgen voor de service.</span><span class="sxs-lookup"><span data-stu-id="ac657-127">Indicates the state you want to ensure for the service.</span></span>| 
| <span data-ttu-id="ac657-128">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ac657-128">Description</span></span> | <span data-ttu-id="ac657-129">Hiermee geeft u de beschrijving van de doelservice.</span><span class="sxs-lookup"><span data-stu-id="ac657-129">Indicates the description of the target service.</span></span>| 
| <span data-ttu-id="ac657-130">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ac657-130">DisplayName</span></span> | <span data-ttu-id="ac657-131">Geeft de naam van de doelservice.</span><span class="sxs-lookup"><span data-stu-id="ac657-131">Indicates the display name of the target service.</span></span>| 
| <span data-ttu-id="ac657-132">Zorg ervoor dat</span><span class="sxs-lookup"><span data-stu-id="ac657-132">Ensure</span></span> | <span data-ttu-id="ac657-133">Hiermee wordt aangegeven of de doelservice op het systeem bestaat.</span><span class="sxs-lookup"><span data-stu-id="ac657-133">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="ac657-134">Deze eigenschap instellen op **afwezig** om ervoor te zorgen dat de doelservice niet bestaat.</span><span class="sxs-lookup"><span data-stu-id="ac657-134">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="ac657-135">Instellen op **aanwezig** (de standaardwaarde) zorgt ervoor dat de doelservice bestaat.</span><span class="sxs-lookup"><span data-stu-id="ac657-135">Setting it to **Present** (the default value) ensures that target service exists.</span></span>|
| <span data-ttu-id="ac657-136">Pad</span><span class="sxs-lookup"><span data-stu-id="ac657-136">Path</span></span> | <span data-ttu-id="ac657-137">Geeft het pad naar het binaire bestand voor een nieuwe service.</span><span class="sxs-lookup"><span data-stu-id="ac657-137">Indicates the path to the binary file for a new service.</span></span>| 

## <a name="example"></a><span data-ttu-id="ac657-138">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="ac657-138">Example</span></span>

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        } 
    }
}
```
