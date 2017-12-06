---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: Ingebouwde Desired State Configuration Resources voor Linux
ms.openlocfilehash: b85f32f7559d89bda566d35462cc613d73424c50
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="built-in-desired-state-configuration-resources-for-linux"></a><span data-ttu-id="45ec7-103">Ingebouwde Desired State Configuration Resources voor Linux</span><span class="sxs-lookup"><span data-stu-id="45ec7-103">Built-In Desired State Configuration Resources for Linux</span></span>

<span data-ttu-id="45ec7-104">Resources zijn bouwstenen die u gebruiken kunt om een script PowerShell Desired State Configuration (DSC) te schrijven.</span><span class="sxs-lookup"><span data-stu-id="45ec7-104">Resources are building blocks that you can use to write a PowerShell Desired State Configuration (DSC) script.</span></span> <span data-ttu-id="45ec7-105">DSC voor Linux wordt geleverd met een set ingebouwde functionaliteit voor het configureren van resources, zoals bestanden en mappen, pakketten, omgevingsvariabelen en services en processen.</span><span class="sxs-lookup"><span data-stu-id="45ec7-105">DSC for Linux comes with a set of built-in functionality for configuring resources such as files and folders, packages, environment variables, and services and processes.</span></span>

## <a name="built-in-resources"></a><span data-ttu-id="45ec7-106">Ingebouwde resources</span><span class="sxs-lookup"><span data-stu-id="45ec7-106">Built-in resources</span></span> 

<span data-ttu-id="45ec7-107">De volgende tabel bevat een lijst van deze resources en koppelingen naar onderwerpen waarin ze in detail beschreven.</span><span class="sxs-lookup"><span data-stu-id="45ec7-107">The following table provides a list of these resources and links to topics that describe them in detail.</span></span>

* <span data-ttu-id="45ec7-108">[nxArchive Resource](lnxArchiveResource.md)--biedt een mechanisme voor het uitpakken van bestanden te archiveren (tar, .zip) op een specifiek pad.</span><span class="sxs-lookup"><span data-stu-id="45ec7-108">[nxArchive Resource](lnxArchiveResource.md)--Provides a mechanism to unpack archive (.tar, .zip) files at a specific path.</span></span>
* <span data-ttu-id="45ec7-109">[nxEnvironment Resource](lnxEnvironmentResource.md)--omgevingsvariabelen op doelknooppunten beheert.</span><span class="sxs-lookup"><span data-stu-id="45ec7-109">[nxEnvironment Resource](lnxEnvironmentResource.md)--Manages environment variables on target nodes.</span></span> 
* <span data-ttu-id="45ec7-110">[nxFile Resource](lnxFileResource.md)--Linux beheert bestanden en mappen.</span><span class="sxs-lookup"><span data-stu-id="45ec7-110">[nxFile Resource](lnxFileResource.md)--Manages Linux files and directories.</span></span> 
* <span data-ttu-id="45ec7-111">[nxFileLine Resource](lnxFileLineResource.md)--beheert afzonderlijke regels in een Linux-bestand.</span><span class="sxs-lookup"><span data-stu-id="45ec7-111">[nxFileLine Resource](lnxFileLineResource.md)--Manages individual lines in a Linux file.</span></span> 
* <span data-ttu-id="45ec7-112">[nxGroup Resource](lnxGroupResource.md)--beheert lokale Linux-groepen.</span><span class="sxs-lookup"><span data-stu-id="45ec7-112">[nxGroup Resource](lnxGroupResource.md)--Manages local Linux groups.</span></span> 
* <span data-ttu-id="45ec7-113">[nxPackage Resource](lnxPackageResource.md)--beheert pakketten op Linux-knooppunten.</span><span class="sxs-lookup"><span data-stu-id="45ec7-113">[nxPackage Resource](lnxPackageResource.md)--Manages packages on Linux nodes.</span></span>
* <span data-ttu-id="45ec7-114">[nxScript Resource](lnxScriptResource.md)--scripts op de doelknooppunten wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="45ec7-114">[nxScript Resource](lnxScriptResource.md)--Runs scripts on target nodes.</span></span>
* <span data-ttu-id="45ec7-115">[nxService Resource](lnxServiceResource.md)--beheert Linux-services (daemons).</span><span class="sxs-lookup"><span data-stu-id="45ec7-115">[nxService Resource](lnxServiceResource.md)--Manages Linux services (daemons).</span></span>
* <span data-ttu-id="45ec7-116">[nxSshAuthorizedKeys Resource](lnxSshAuthorizedKeysResource.md)--beheert openbare ssh-sleutels voor een Linux-gebruiker.</span><span class="sxs-lookup"><span data-stu-id="45ec7-116">[nxSshAuthorizedKeys Resource](lnxSshAuthorizedKeysResource.md)--Manages public ssh keys for a Linux user.</span></span> 
* <span data-ttu-id="45ec7-117">[nxUser Resource](lnxUserResource.md)--lokale Linux-gebruikers beheert.</span><span class="sxs-lookup"><span data-stu-id="45ec7-117">[nxUser Resource](lnxUserResource.md)--Manages local Linux users.</span></span> 
  