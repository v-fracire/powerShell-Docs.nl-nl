---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: DSC voor Linux nxGroup Resource
ms.openlocfilehash: fcd1dfd3110b1358ed7ef9ca8d57154186b271f6
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-for-linux-nxgroup-resource"></a><span data-ttu-id="7c9f9-103">DSC voor Linux nxGroup Resource</span><span class="sxs-lookup"><span data-stu-id="7c9f9-103">DSC for Linux nxGroup Resource</span></span>

<span data-ttu-id="7c9f9-104">De **nxGroup** in PowerShell Desired State Configuration (DSC)-bron biedt een mechanisme voor het beheren van lokale groepen op een Linux-knooppunt.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-104">The **nxGroup** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c9f9-105">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="7c9f9-105">Syntax</span></span>

```powershell
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Ensure = <string> { Absent | Present }  ]
    [ Members = <string[]> ]
    [ MebersToInclude = <string[]>]
    [ MembersToExclude = <string[]> ]
    [ DependsOn = <string[]> ]
}

```

## <a name="properties"></a><span data-ttu-id="7c9f9-106">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="7c9f9-106">Properties</span></span>

|  <span data-ttu-id="7c9f9-107">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="7c9f9-107">Property</span></span> |  <span data-ttu-id="7c9f9-108">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7c9f9-108">Description</span></span> | 
|---|---|
| <span data-ttu-id="7c9f9-109">Groepsnaam</span><span class="sxs-lookup"><span data-stu-id="7c9f9-109">GroupName</span></span>| <span data-ttu-id="7c9f9-110">Hiermee geeft u de naam van de groep waarvoor u om te controleren of een specifieke status.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-110">Specifies the name of the group for which you want to ensure a specific state.</span></span>| 
| <span data-ttu-id="7c9f9-111">Zorg ervoor dat</span><span class="sxs-lookup"><span data-stu-id="7c9f9-111">Ensure</span></span>| <span data-ttu-id="7c9f9-112">Bepaalt of Controleer of de groep bestaat.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-112">Determines whether to check if the group exists.</span></span> <span data-ttu-id="7c9f9-113">Deze eigenschap instellen op 'Aanwezig' om te controleren of dat de groep bestaat.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-113">Set this property to "Present" to ensure the group exists.</span></span> <span data-ttu-id="7c9f9-114">Stel deze in op 'Ontbreekt' om te controleren of dat de groep bestaat niet.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-114">Set it to "Absent" to ensure the group does not exist.</span></span> <span data-ttu-id="7c9f9-115">De standaardwaarde is 'Aanwezig'.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-115">The default value is "Present".</span></span>| 
| <span data-ttu-id="7c9f9-116">Leden</span><span class="sxs-lookup"><span data-stu-id="7c9f9-116">Members</span></span>| <span data-ttu-id="7c9f9-117">Hiermee geeft u de leden die vormen van de groep.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-117">Specifies the members that form the group.</span></span>| 
| <span data-ttu-id="7c9f9-118">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="7c9f9-118">MembersToInclude</span></span>| <span data-ttu-id="7c9f9-119">Hiermee geeft u de gebruikers die u wilt zorgen lid zijn van de groep.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-119">Specifies the users who you want to ensure are members of the group.</span></span>| 
| <span data-ttu-id="7c9f9-120">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="7c9f9-120">MembersToExclude</span></span>| <span data-ttu-id="7c9f9-121">Hiermee geeft u de gebruikers die u wilt zorgen zijn geen leden van de groep.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-121">Specifies the users who you want to ensure are not members of the group.</span></span>| 
| <span data-ttu-id="7c9f9-122">PreferredGroupID</span><span class="sxs-lookup"><span data-stu-id="7c9f9-122">PreferredGroupID</span></span>| <span data-ttu-id="7c9f9-123">Wordt indien mogelijk de groeps-id ingesteld op de opgegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-123">Sets the group id to the provided value if possible.</span></span> <span data-ttu-id="7c9f9-124">Als de groeps-id momenteel in gebruik is, wordt de volgende beschikbare groeps-id wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-124">If the group id is currently in use, the next available group id is used.</span></span>| 
| <span data-ttu-id="7c9f9-125">dependsOn</span><span class="sxs-lookup"><span data-stu-id="7c9f9-125">DependsOn</span></span> | <span data-ttu-id="7c9f9-126">Hiermee wordt aangegeven dat de configuratie van een andere resource uitvoeren moet voordat deze bron is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-126">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="7c9f9-127">Bijvoorbeeld, als de **ID** van de resource is scriptblok configuratie die u wilt uitvoeren eerst **ResourceName** en het type **ResourceType**, de syntaxis voor het gebruik van deze de eigenschap is `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-127">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 

## <a name="example"></a><span data-ttu-id="7c9f9-128">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="7c9f9-128">Example</span></span>

<span data-ttu-id="7c9f9-129">Het volgende voorbeeld zorgt ervoor dat de gebruiker "monuser" bestaat en lid van de groep 'DBusers is'.</span><span class="sxs-lookup"><span data-stu-id="7c9f9-129">The following example ensures that the user “monuser” exists and is a member of the group "DBusers".</span></span>

```
Import-DSCResource -Module nx 

Node $node {

nxUser UserExample{
   UserName = "monuser"
   Description = "Monitoring user"
   Password  =    '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
   Ensure = "Present"
   HomeDirectory = "/home/monuser"
}
 
nxGroup GroupExample{
   GroupName = "DBusers"
   Ensure = "Present"
   MembersToInclude = "monuser"
   DependsOn = "[nxUser]UserExample"            
}
}
```
