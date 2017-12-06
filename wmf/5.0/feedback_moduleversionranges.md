---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: WMF, powershell, setup
ms.openlocfilehash: fa972b68015d9b6e14508ccda562cfa5ebd632ac
ms.sourcegitcommit: a5c0795ca6ec9332967bff9c151a8572feb1a53a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2017
---
# <a name="modules-support-for-declaring-version-ranges-1-etc"></a><span data-ttu-id="bcdfe-102">Modules ondersteuning voor het declareren van versie bereiken (1.*, enzovoort)</span><span class="sxs-lookup"><span data-stu-id="bcdfe-102">Modules support for declaring version ranges (1.*, etc)</span></span>
<span data-ttu-id="bcdfe-103">In combinatie met **- MinimumVersion**, **- MaximumVersion** nu kan de gebruiker get/import-module binnen een bepaald bereik.</span><span class="sxs-lookup"><span data-stu-id="bcdfe-103">Combined with **-MinimumVersion**, **-MaximumVersion** now allows user to get/import module within specific range.</span></span> <span data-ttu-id="bcdfe-104">De parameter bieden ook ondersteuning voor **.** *.</span><span class="sxs-lookup"><span data-stu-id="bcdfe-104">The parameter also support **.***.</span></span> <span data-ttu-id="bcdfe-105">Het volgende voorbeeld ziet u hoe het werkt:</span><span class="sxs-lookup"><span data-stu-id="bcdfe-105">The following example shows how it works:</span></span>

```powershell
Now, you can combine **-MinimumVersion** and **-MaximumVersion** to import module within specific range:

PS C:\> Import-Module psreadline -Verbose -MinimumVersion 1.0 -MaximumVersion 1.2.*

VERBOSE: Loading module from path 'C:\Program Files\WindowsPowerShell\Modules\psreadline\1.1\psreadline.psd1'.
VERBOSE: Importing cmdlet 'Get-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Get-PSReadlineOption'.
VERBOSE: Importing cmdlet 'Remove-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineKeyHandler'.
VERBOSE: Importing cmdlet 'Set-PSReadlineOption'.
VERBOSE: Importing function 'PSConsoleHostReadline'.
```
