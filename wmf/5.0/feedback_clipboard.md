---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: WMF, powershell, setup
ms.openlocfilehash: 8d5f8cc8c85d584b195483e464e878857629a78e
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="clipboard-cmdlets"></a><span data-ttu-id="d90a2-102">Klembord-cmdlets</span><span class="sxs-lookup"><span data-stu-id="d90a2-102">Clipboard cmdlets</span></span>
<span data-ttu-id="d90a2-103">**Get-Klembord** en **Set Klembord** het eenvoudiger voor u om inhoud naar en van een Windows PowerShell-sessie te brengen.</span><span class="sxs-lookup"><span data-stu-id="d90a2-103">**Get-Clipboard** and **Set-Clipboard** make it easier for you to transfer content to and from a Windows PowerShell session.</span></span> <span data-ttu-id="d90a2-104">Bijvoorbeeld, als u Windows Verkenner gebruiken drie bestanden naar het Klembord te kopiëren (door ze te selecteren en op `ctrl-c`, bijvoorbeeld), u kunt vervolgens gemakkelijk toegang tot de inhoud van het Klembord als een lijst met bestanden:</span><span class="sxs-lookup"><span data-stu-id="d90a2-104">For example, if you use Windows Explorer to copy three files to the clipboard (by selecting them and pressing `ctrl-c`, for example), you can then easily access the contents of the clipboard as a list of files:</span></span>

```powershell 
PS C:\\&gt; Get-Clipboard -Format FileDropList

Directory: C:\\Users\\slee\\Downloads\\Example

Mode LastWriteTime Length Name

---- ------------- ------ ----

-a---- 4/14/2015 1:19 PM 0 File2.txt

-a---- 4/14/2015 1:19 PM 0 File3.txt

-a---- 4/14/2015 1:19 PM 0 File1.txt
```


<span data-ttu-id="d90a2-105">De Klembord-cmdlets ondersteunen afbeeldingen, audio-bestanden, bestandslijsten en tekst.</span><span class="sxs-lookup"><span data-stu-id="d90a2-105">The Clipboard cmdlets support images, audio files, file lists, and text.</span></span>
