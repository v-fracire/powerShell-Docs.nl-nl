---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: WMF, powershell, setup
ms.openlocfilehash: 32f8e20889ddc526def4b925e8d0761a2e851e19
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="unified-and-consistent-state-and-status-representation"></a><span data-ttu-id="8ce10-102">Uniforme en consistente status en de weergave Status</span><span class="sxs-lookup"><span data-stu-id="8ce10-102">Unified and Consistent State and Status Representation</span></span>

<span data-ttu-id="8ce10-103">Een reeks verbeteringen zijn aangebracht in deze release voor automatische LCM toestand en status van de DSC gebouwd.</span><span class="sxs-lookup"><span data-stu-id="8ce10-103">A series of enhancements have been made in this release for automations built LCM state and DSC status.</span></span> <span data-ttu-id="8ce10-104">Dit omvat uniforme en consistente status en status verklaringen, beheerbare datetime-eigenschap van status objecten geretourneerd door de cmdlet Get-DscConfigurationStatus en verbeterde LCM status details eigenschap die is geretourneerd door Get-DscLocalConfigurationManager cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8ce10-104">These include unified and consistent state and status representations, manageable datetime property of status objects returned by Get-DscConfigurationStatus cmdlet and enhanced LCM state details property returned by Get-DscLocalConfigurationManager cmdlet.</span></span>

<span data-ttu-id="8ce10-105">De weergave van LCM status en de status van de DSC-bewerking worden herzien en uniform volgens de volgende regels:</span><span class="sxs-lookup"><span data-stu-id="8ce10-105">The representation of LCM state and DSC operation status are revisited and unified according to following rules:</span></span>
1.  <span data-ttu-id="8ce10-106">NotProcessed weer resource heeft geen gevolgen voor LCM toestand en DSC-status.</span><span class="sxs-lookup"><span data-stu-id="8ce10-106">Notprocessed resource does not impact LCM state and DSC status.</span></span>
2.  <span data-ttu-id="8ce10-107">LCM stoppen verdere resources voor het verwerken zodra er een resource die aanvragen van opnieuw opstarten wordt aangetroffen.</span><span class="sxs-lookup"><span data-stu-id="8ce10-107">LCM stop processing further resources once it encounters a resource that requests reboot.</span></span>
3.  <span data-ttu-id="8ce10-108">Een resource die aanvragen van opnieuw opstarten is niet in de gewenste status totdat opnieuw opstarten feitelijk plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="8ce10-108">A resource that requests reboot is not in desired state until reboot actually happens.</span></span>
4.  <span data-ttu-id="8ce10-109">Na het vaststellen van een resource die is mislukt, houdt LCM verwerking van verdere resources zo lang ze zijn niet afhankelijk van de fout een.</span><span class="sxs-lookup"><span data-stu-id="8ce10-109">After encountering a resource that fails, LCM keeps processing further resources as long as they are not dependent on the failure one.</span></span>
5.  <span data-ttu-id="8ce10-110">De algehele status geretourneerd door de cmdlet Get-DscConfigurationStatus is de super set van alle resources status.</span><span class="sxs-lookup"><span data-stu-id="8ce10-110">The overall status returned by Get-DscConfigurationStatus cmdlet is the super set of all resources’ status.</span></span>
6.  <span data-ttu-id="8ce10-111">De status PendingReboot is een hoofdverzameling van PendingConfiguration status.</span><span class="sxs-lookup"><span data-stu-id="8ce10-111">The PendingReboot state is a superset of PendingConfiguration state.</span></span>

<span data-ttu-id="8ce10-112">De volgende tabel ziet u de resulterende toestand en status gerelateerd eigenschappen onder enkele typische scenario's.</span><span class="sxs-lookup"><span data-stu-id="8ce10-112">The table below illustrates the resultant state and status related properties under a few typical scenarios.</span></span>

| <span data-ttu-id="8ce10-113">**Scenario**</span><span class="sxs-lookup"><span data-stu-id="8ce10-113">**Scenario**</span></span>                    | <span data-ttu-id="8ce10-114">**LCMState\***</span><span class="sxs-lookup"><span data-stu-id="8ce10-114">**LCMState\***</span></span>       | <span data-ttu-id="8ce10-115">**Status**</span><span class="sxs-lookup"><span data-stu-id="8ce10-115">**Status**</span></span> | <span data-ttu-id="8ce10-116">**Opnieuw opstarten aangevraagd**</span><span class="sxs-lookup"><span data-stu-id="8ce10-116">**Reboot Requested**</span></span>  | <span data-ttu-id="8ce10-117">**ResourcesInDesiredState**</span><span class="sxs-lookup"><span data-stu-id="8ce10-117">**ResourcesInDesiredState**</span></span>  | <span data-ttu-id="8ce10-118">**ResourcesNotInDesiredState**</span><span class="sxs-lookup"><span data-stu-id="8ce10-118">**ResourcesNotInDesiredState**</span></span> |
|---------------------------------|----------------------|------------|---------------|------------------------------|--------------------------------|
| <span data-ttu-id="8ce10-119">S**^**</span><span class="sxs-lookup"><span data-stu-id="8ce10-119">S**^**</span></span>                          | <span data-ttu-id="8ce10-120">Actieve</span><span class="sxs-lookup"><span data-stu-id="8ce10-120">Idle</span></span>                 | <span data-ttu-id="8ce10-121">Geslaagd</span><span class="sxs-lookup"><span data-stu-id="8ce10-121">Success</span></span>    | <span data-ttu-id="8ce10-122">$false</span><span class="sxs-lookup"><span data-stu-id="8ce10-122">$false</span></span>        | <span data-ttu-id="8ce10-123">S</span><span class="sxs-lookup"><span data-stu-id="8ce10-123">S</span></span>                            | <span data-ttu-id="8ce10-124">$null</span><span class="sxs-lookup"><span data-stu-id="8ce10-124">$null</span></span>                          |
| <span data-ttu-id="8ce10-125">F**^**</span><span class="sxs-lookup"><span data-stu-id="8ce10-125">F**^**</span></span>                          | <span data-ttu-id="8ce10-126">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ce10-126">PendingConfiguration</span></span> | <span data-ttu-id="8ce10-127">Mislukt</span><span class="sxs-lookup"><span data-stu-id="8ce10-127">Failure</span></span>    | <span data-ttu-id="8ce10-128">$false</span><span class="sxs-lookup"><span data-stu-id="8ce10-128">$false</span></span>        | <span data-ttu-id="8ce10-129">$null</span><span class="sxs-lookup"><span data-stu-id="8ce10-129">$null</span></span>                        | <span data-ttu-id="8ce10-130">F</span><span class="sxs-lookup"><span data-stu-id="8ce10-130">F</span></span>                              |
| <span data-ttu-id="8ce10-131">S, F</span><span class="sxs-lookup"><span data-stu-id="8ce10-131">S,F</span></span>                             | <span data-ttu-id="8ce10-132">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ce10-132">PendingConfiguration</span></span> | <span data-ttu-id="8ce10-133">Mislukt</span><span class="sxs-lookup"><span data-stu-id="8ce10-133">Failure</span></span>    | <span data-ttu-id="8ce10-134">$false</span><span class="sxs-lookup"><span data-stu-id="8ce10-134">$false</span></span>        | <span data-ttu-id="8ce10-135">S</span><span class="sxs-lookup"><span data-stu-id="8ce10-135">S</span></span>                            | <span data-ttu-id="8ce10-136">F</span><span class="sxs-lookup"><span data-stu-id="8ce10-136">F</span></span>                              |
| <span data-ttu-id="8ce10-137">F, S</span><span class="sxs-lookup"><span data-stu-id="8ce10-137">F,S</span></span>                             | <span data-ttu-id="8ce10-138">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ce10-138">PendingConfiguration</span></span> | <span data-ttu-id="8ce10-139">Mislukt</span><span class="sxs-lookup"><span data-stu-id="8ce10-139">Failure</span></span>    | <span data-ttu-id="8ce10-140">$false</span><span class="sxs-lookup"><span data-stu-id="8ce10-140">$false</span></span>        | <span data-ttu-id="8ce10-141">S</span><span class="sxs-lookup"><span data-stu-id="8ce10-141">S</span></span>                            | <span data-ttu-id="8ce10-142">F</span><span class="sxs-lookup"><span data-stu-id="8ce10-142">F</span></span>                              |
| <span data-ttu-id="8ce10-143">S<sub>1</sub>, F, S<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="8ce10-143">S<sub>1</sub>, F, S<sub>2</sub></span></span> | <span data-ttu-id="8ce10-144">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ce10-144">PendingConfiguration</span></span> | <span data-ttu-id="8ce10-145">Mislukt</span><span class="sxs-lookup"><span data-stu-id="8ce10-145">Failure</span></span>    | <span data-ttu-id="8ce10-146">$false</span><span class="sxs-lookup"><span data-stu-id="8ce10-146">$false</span></span>        | <span data-ttu-id="8ce10-147">S<sub>1</sub>, S<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="8ce10-147">S<sub>1</sub>, S<sub>2</sub></span></span> | <span data-ttu-id="8ce10-148">F</span><span class="sxs-lookup"><span data-stu-id="8ce10-148">F</span></span>                              |
| <span data-ttu-id="8ce10-149">F<sub>1</sub>, S, F<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="8ce10-149">F<sub>1</sub>, S, F<sub>2</sub></span></span> | <span data-ttu-id="8ce10-150">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8ce10-150">PendingConfiguration</span></span> | <span data-ttu-id="8ce10-151">Mislukt</span><span class="sxs-lookup"><span data-stu-id="8ce10-151">Failure</span></span>    | <span data-ttu-id="8ce10-152">$false</span><span class="sxs-lookup"><span data-stu-id="8ce10-152">$false</span></span>        | <span data-ttu-id="8ce10-153">S</span><span class="sxs-lookup"><span data-stu-id="8ce10-153">S</span></span>                            | <span data-ttu-id="8ce10-154">F<sub>1</sub>, F<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="8ce10-154">F<sub>1</sub>, F<sub>2</sub></span></span>   |
| <span data-ttu-id="8ce10-155">S, r</span><span class="sxs-lookup"><span data-stu-id="8ce10-155">S, r</span></span>                            | <span data-ttu-id="8ce10-156">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="8ce10-156">PendingReboot</span></span>        | <span data-ttu-id="8ce10-157">Geslaagd</span><span class="sxs-lookup"><span data-stu-id="8ce10-157">Success</span></span>    | <span data-ttu-id="8ce10-158">$true</span><span class="sxs-lookup"><span data-stu-id="8ce10-158">$true</span></span>         | <span data-ttu-id="8ce10-159">S</span><span class="sxs-lookup"><span data-stu-id="8ce10-159">S</span></span>                            | <span data-ttu-id="8ce10-160">r</span><span class="sxs-lookup"><span data-stu-id="8ce10-160">r</span></span>                              |
| <span data-ttu-id="8ce10-161">F, r</span><span class="sxs-lookup"><span data-stu-id="8ce10-161">F, r</span></span>                            | <span data-ttu-id="8ce10-162">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="8ce10-162">PendingReboot</span></span>        | <span data-ttu-id="8ce10-163">Mislukt</span><span class="sxs-lookup"><span data-stu-id="8ce10-163">Failure</span></span>    | <span data-ttu-id="8ce10-164">$true</span><span class="sxs-lookup"><span data-stu-id="8ce10-164">$true</span></span>         | <span data-ttu-id="8ce10-165">$null</span><span class="sxs-lookup"><span data-stu-id="8ce10-165">$null</span></span>                        | <span data-ttu-id="8ce10-166">F, r</span><span class="sxs-lookup"><span data-stu-id="8ce10-166">F, r</span></span>                           |
| <span data-ttu-id="8ce10-167">r, S</span><span class="sxs-lookup"><span data-stu-id="8ce10-167">r, S</span></span>                            | <span data-ttu-id="8ce10-168">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="8ce10-168">PendingReboot</span></span>        | <span data-ttu-id="8ce10-169">Geslaagd</span><span class="sxs-lookup"><span data-stu-id="8ce10-169">Success</span></span>    | <span data-ttu-id="8ce10-170">$true</span><span class="sxs-lookup"><span data-stu-id="8ce10-170">$true</span></span>         | <span data-ttu-id="8ce10-171">$null</span><span class="sxs-lookup"><span data-stu-id="8ce10-171">$null</span></span>                        | <span data-ttu-id="8ce10-172">r</span><span class="sxs-lookup"><span data-stu-id="8ce10-172">r</span></span>                              |
| <span data-ttu-id="8ce10-173">r, F</span><span class="sxs-lookup"><span data-stu-id="8ce10-173">r, F</span></span>                            | <span data-ttu-id="8ce10-174">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="8ce10-174">PendingReboot</span></span>        | <span data-ttu-id="8ce10-175">Geslaagd</span><span class="sxs-lookup"><span data-stu-id="8ce10-175">Success</span></span>    | <span data-ttu-id="8ce10-176">$true</span><span class="sxs-lookup"><span data-stu-id="8ce10-176">$true</span></span>         | <span data-ttu-id="8ce10-177">$null</span><span class="sxs-lookup"><span data-stu-id="8ce10-177">$null</span></span>                        | <span data-ttu-id="8ce10-178">r</span><span class="sxs-lookup"><span data-stu-id="8ce10-178">r</span></span>                              |

<span data-ttu-id="8ce10-179">^ S<sub>ik</sub>: een reeks resources die F toegepast<sub>ik</sub>: een reeks resources die wordt toegepast zonder succes r: een bron die opnieuw opstarten vereist\*</span><span class="sxs-lookup"><span data-stu-id="8ce10-179">^ S<sub>i</sub>: A series of resources that applied successfully F<sub>i</sub>: A series of resources that applied unsuccessfully r: A resource that requires reboot \*</span></span>

```powershell
$LCMState = (Get-DscLocalConfigurationManager).LCMState
$Status = (Get-DscConfigurationStatus).Status

$RebootRequested = (Get-DscConfigurationStatus).RebootRequested

$ResourcesInDesiredState = (Get-DscConfigurationStatus).ResourcesInDesiredState

$ResourcesNotInDesiredState = (Get-DscConfigurationStatus).ResourcesNotInDesiredState
```
## <a name="enhancement-in-get-dscconfigurationstatus-cmdlet"></a><span data-ttu-id="8ce10-180">Uitbreiding in de cmdlet Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="8ce10-180">Enhancement in Get-DscConfigurationStatus cmdlet</span></span>

<span data-ttu-id="8ce10-181">Er zijn enkele verbeteringen zijn aangebracht aan de cmdlet Get-DscConfigurationStatus in deze release.</span><span class="sxs-lookup"><span data-stu-id="8ce10-181">A few enhancements have been made to Get-DscConfigurationStatus cmdlet in this release.</span></span> <span data-ttu-id="8ce10-182">De eigenschap StartDate van objecten die worden geretourneerd door de cmdlet is eerder van het tekenreekstype.</span><span class="sxs-lookup"><span data-stu-id="8ce10-182">Previously, the StartDate property of objects returned by the cmdlet is of String type.</span></span> <span data-ttu-id="8ce10-183">Nu is van het type Datetime, waardoor complexe te selecteren en filteren eenvoudiger op basis van de intrinsieke eigenschappen van een datum/tijd-object.</span><span class="sxs-lookup"><span data-stu-id="8ce10-183">Now, it is of Datetime type, which enables complex selecting and filtering easier based on the intrinsic properties of a Datetime object.</span></span>
```powershell
(Get-DscConfigurationStatus).StartDate | fl \*
DateTime : Friday, November 13, 2015 1:39:44 PM
Date : 11/13/2015 12:00:00 AM
Day : 13
DayOfWeek : Friday
DayOfYear : 317
Hour : 13
Kind : Local
Millisecond : 886
Minute : 39
Month : 11
Second : 44
Ticks : 635830187848860000
TimeOfDay : 13:39:44.8860000
Year : 2015
```

<span data-ttu-id="8ce10-184">Hier volgt een voorbeeld waarin alle records voor DSC-bewerking is uitgevoerd op dezelfde dag van week vandaag retourneert.</span><span class="sxs-lookup"><span data-stu-id="8ce10-184">Following is an example that returns all DSC operation records happened on the same day of week as today.</span></span>
```powershell
(Get-DscConfigurationStatus –All) | where { $\_.startdate.dayofweek -eq (Get-Date).DayOfWeek }
```

<span data-ttu-id="8ce10-185">Records van bewerkingen die geen wijzigingen knooppuntconfiguratie aanbrengen, (dat wil zeggen leesbewerkingen alleen) worden geëlimineerd.</span><span class="sxs-lookup"><span data-stu-id="8ce10-185">Records of operations that do not make changes to node’s configuration (i.e. read only operations) are eliminated.</span></span> <span data-ttu-id="8ce10-186">Daarom Test-DscConfiguration Get DscConfiguration bewerkingen zijn niet langer verontreinigde objecten van de cmdlet Get-DscConfigurationStatus geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="8ce10-186">Therefore, Test-DscConfiguration, Get-DscConfiguration operations are no longer adulterated in returned objects from Get-DscConfigurationStatus cmdlet.</span></span>
<span data-ttu-id="8ce10-187">Records van de bewerking meta configuratie-instelling wordt toegevoegd aan het retourtype van de cmdlet Get-DscConfigurationStatus.</span><span class="sxs-lookup"><span data-stu-id="8ce10-187">Records of meta configuration setting operation is added to the return of Get-DscConfigurationStatus cmdlet.</span></span>

<span data-ttu-id="8ce10-188">Hieronder volgt een voorbeeld van resultaat geretourneerd door Get-DscConfigurationStatus – alle cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8ce10-188">Following is an example of result returned from Get-DscConfigurationStatus –All cmdlet.</span></span>
```powershell
All configuration operations:

Status StartDate Type RebootRequested
------ --------- ---- ---------------
Success 11/13/2015 11:38:16 AM Consistency False
Success 11/13/2015 11:23:16 AM Reboot False
Success 11/13/2015 11:21:43 AM Reboot True
Success 11/13/2015 11:20:44 AM Initial True
Success 11/13/2015 11:20:44 AM LocalConfigurationManager False
```

## <a name="enhancement-in-get-dsclocalconfigurationmanager-cmdlet"></a><span data-ttu-id="8ce10-189">Uitbreiding in de cmdlet Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="8ce10-189">Enhancement in Get-DscLocalConfigurationManager cmdlet</span></span>
<span data-ttu-id="8ce10-190">Een nieuw veld van LCMStateDetail is toegevoegd aan het object dat wordt geretourneerd door de cmdlet Get-DscLocalConfigurationManager.</span><span class="sxs-lookup"><span data-stu-id="8ce10-190">A new field of LCMStateDetail is added to the object returned from Get-DscLocalConfigurationManager cmdlet.</span></span> <span data-ttu-id="8ce10-191">Dit veld wordt gevuld wanneer LCMState 'Bezet' is.</span><span class="sxs-lookup"><span data-stu-id="8ce10-191">This field is populated when LCMState is “Busy”.</span></span> <span data-ttu-id="8ce10-192">Het kan worden opgehaald met de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8ce10-192">It can be retrieved by following cmdlet:</span></span>
```powershell
(Get-DscLocalConfigurationManager).LCMStateDetail
```

<span data-ttu-id="8ce10-193">Hier volgt een voorbeeld van uitvoer van een doorlopende bewaking van een configuratie die twee keer opnieuw opstarten op een externe knooppunt vereist.</span><span class="sxs-lookup"><span data-stu-id="8ce10-193">Following is an example output of a continuous monitoring on a configuration that requires two reboots on a remote node.</span></span>
```powershell
Start a configuration that requires two reboots

Monitor LCM State:
LCM State: Busy, LCM is applying a new configuration.
LCM State: PendingReboot,
Machine is rebooting...
LCM State: Busy, LCM is continuing applying configuration after last reboot.
LCM State: PendingReboot,
Machine is rebooting...
LCM State: Busy, LCM is continuing applying configuration after last reboot.
LCM State: Idle,
LCM State: Busy, LCM is performing a consistency check.
LCM State: Idle,
```
