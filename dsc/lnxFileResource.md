---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: DSC voor Linux nxFile Resource
ms.openlocfilehash: 14f1ae31a8409b8874d76a91b8b29595e30fbb46
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-for-linux-nxfile-resource"></a><span data-ttu-id="6251e-103">DSC voor Linux nxFile Resource</span><span class="sxs-lookup"><span data-stu-id="6251e-103">DSC for Linux nxFile Resource</span></span>

<span data-ttu-id="6251e-104">De **nxFile** in PowerShell Desired State Configuration (DSC)-bron biedt een mechanisme op voor het beheren van bestanden en mappen op een Linux-knooppunt.</span><span class="sxs-lookup"><span data-stu-id="6251e-104">The **nxFile** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to to manage files and directories on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="6251e-105">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="6251e-105">Syntax</span></span>

```
nxFile <string> #ResourceName
{
    DestinationPath = <string>
    [ SourcePath = <string> ]
    [ Ensure = <string> { Absent | Present }  ]
    [ Type = <string> { directory | file | link } ]
    [ Contents = <string> ]
    [ Checksum = <string> { ctime | mtime | md5 }  ]
    [ Recurse = <bool> ]
    [ Force = <bool> ]
    [ Links = <string> { follow | manage } ]
    [ Group = <string> ]
    [ Mode = <string> ]
    [ Owner = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="6251e-106">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="6251e-106">Properties</span></span>

|  <span data-ttu-id="6251e-107">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="6251e-107">Property</span></span> |  <span data-ttu-id="6251e-108">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6251e-108">Description</span></span> | 
|---|---|
| <span data-ttu-id="6251e-109">Doelpad</span><span class="sxs-lookup"><span data-stu-id="6251e-109">DestinationPath</span></span>| <span data-ttu-id="6251e-110">Hiermee geeft u de locatie op waar u om te controleren of de status voor een bestand of map.</span><span class="sxs-lookup"><span data-stu-id="6251e-110">Specifies the location where you want to ensure the state for a file or directory.</span></span>| 
| <span data-ttu-id="6251e-111">Bronpad</span><span class="sxs-lookup"><span data-stu-id="6251e-111">SourcePath</span></span>| <span data-ttu-id="6251e-112">Hiermee geeft u het pad van waaruit de bron van het bestand of map kopiëren.</span><span class="sxs-lookup"><span data-stu-id="6251e-112">Specifies the path from which to copy the file or folder resource.</span></span> <span data-ttu-id="6251e-113">Dit pad is mogelijk een lokaal pad of een `http/https/ftp` URL.</span><span class="sxs-lookup"><span data-stu-id="6251e-113">This path may be a local path, or an `http/https/ftp` URL.</span></span> <span data-ttu-id="6251e-114">Externe `http/https/ftp` URL's worden alleen ondersteund wanneer de waarde van de **Type** eigenschap bestand is.</span><span class="sxs-lookup"><span data-stu-id="6251e-114">Remote `http/https/ftp` URLs are only supported when the value of the **Type** property is file.</span></span>| 
| <span data-ttu-id="6251e-115">Zorg ervoor dat</span><span class="sxs-lookup"><span data-stu-id="6251e-115">Ensure</span></span>| <span data-ttu-id="6251e-116">Bepaalt of Controleer of het bestand bestaat.</span><span class="sxs-lookup"><span data-stu-id="6251e-116">Determines whether to check if the file exists.</span></span> <span data-ttu-id="6251e-117">Deze eigenschap instellen op 'Aanwezig' om te controleren of dat het bestand bestaat.</span><span class="sxs-lookup"><span data-stu-id="6251e-117">Set this property to "Present" to ensure the file exists.</span></span> <span data-ttu-id="6251e-118">Stel deze in op 'Ontbreekt' om te controleren of dat het bestand bestaat niet.</span><span class="sxs-lookup"><span data-stu-id="6251e-118">Set it to "Absent" to ensure the file does not exist.</span></span> <span data-ttu-id="6251e-119">De standaardwaarde is 'Aanwezig'.</span><span class="sxs-lookup"><span data-stu-id="6251e-119">The default value is "Present".</span></span>| 
| <span data-ttu-id="6251e-120">Type</span><span class="sxs-lookup"><span data-stu-id="6251e-120">Type</span></span>| <span data-ttu-id="6251e-121">Hiermee geeft u op of de resource die wordt geconfigureerd een map of een bestand is.</span><span class="sxs-lookup"><span data-stu-id="6251e-121">Specifies whether the resource being configured is a directory or a file.</span></span> <span data-ttu-id="6251e-122">Deze eigenschap instellen op 'map' om aan te geven dat de resource een map is.</span><span class="sxs-lookup"><span data-stu-id="6251e-122">Set this property to "directory" to indicate that the resource is a directory.</span></span> <span data-ttu-id="6251e-123">Stel deze in op 'file' om aan te geven dat de resource een bestand is.</span><span class="sxs-lookup"><span data-stu-id="6251e-123">Set it to "file" to indicate that the resource is a file.</span></span> <span data-ttu-id="6251e-124">De standaardwaarde is "bestand"</span><span class="sxs-lookup"><span data-stu-id="6251e-124">The default value is "file"</span></span>| 
| <span data-ttu-id="6251e-125">Inhoud</span><span class="sxs-lookup"><span data-stu-id="6251e-125">Contents</span></span>| <span data-ttu-id="6251e-126">Hiermee geeft u de inhoud van een bestand, zoals een bepaalde tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="6251e-126">Specifies the contents of a file, such as a particular string.</span></span>| 
| <span data-ttu-id="6251e-127">Controlesom</span><span class="sxs-lookup"><span data-stu-id="6251e-127">Checksum</span></span>| <span data-ttu-id="6251e-128">Definieert het type moet worden gebruikt bij het bepalen of twee bestanden hetzelfde zijn.</span><span class="sxs-lookup"><span data-stu-id="6251e-128">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="6251e-129">Als **controlesom** niet is opgegeven, alleen de naam van bestand of map wordt gebruikt voor vergelijking.</span><span class="sxs-lookup"><span data-stu-id="6251e-129">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="6251e-130">Waarden zijn: 'ctime', 'mtime' of 'md5'.</span><span class="sxs-lookup"><span data-stu-id="6251e-130">Values are: "ctime", "mtime", or "md5".</span></span>| 
| <span data-ttu-id="6251e-131">Recurse</span><span class="sxs-lookup"><span data-stu-id="6251e-131">Recurse</span></span>| <span data-ttu-id="6251e-132">Hiermee wordt aangegeven als submappen opgenomen worden.</span><span class="sxs-lookup"><span data-stu-id="6251e-132">Indicates if subdirectories are included.</span></span> <span data-ttu-id="6251e-133">Deze eigenschap instellen op **$true** om aan te geven dat u wilt dat de submappen worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="6251e-133">Set this property to **$true** to indicate that you want subdirectories to be included.</span></span> <span data-ttu-id="6251e-134">De standaardwaarde is **$false**.</span><span class="sxs-lookup"><span data-stu-id="6251e-134">The default is **$false**.</span></span> <span data-ttu-id="6251e-135">**Opmerking:** deze eigenschap is alleen geldig wanneer de **Type** eigenschap is ingesteld op de directory.</span><span class="sxs-lookup"><span data-stu-id="6251e-135">**Note:** This property is only valid when the **Type** property is set to directory.</span></span>| 
| <span data-ttu-id="6251e-136">Force</span><span class="sxs-lookup"><span data-stu-id="6251e-136">Force</span></span>| <span data-ttu-id="6251e-137">Bepaalde bestandsbewerkingen (zoals een bestand te overschrijven of verwijderen van een map die is niet leeg) leidt tot een fout opgetreden.</span><span class="sxs-lookup"><span data-stu-id="6251e-137">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="6251e-138">Met behulp van de **Force** eigenschap heeft een dergelijke fouten.</span><span class="sxs-lookup"><span data-stu-id="6251e-138">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="6251e-139">De standaardwaarde is **$false**.</span><span class="sxs-lookup"><span data-stu-id="6251e-139">The default value is **$false**.</span></span>| 
| <span data-ttu-id="6251e-140">Koppelingen</span><span class="sxs-lookup"><span data-stu-id="6251e-140">Links</span></span>| <span data-ttu-id="6251e-141">Hiermee geeft u het gewenste gedrag voor symbolische koppelingen.</span><span class="sxs-lookup"><span data-stu-id="6251e-141">Specifies the desired behavior for symbolic links.</span></span> <span data-ttu-id="6251e-142">Deze eigenschap instellen op 'volgen' symbolische koppelingen volgen en reageren op de doel-koppelingen (bijvoorbeeld)</span><span class="sxs-lookup"><span data-stu-id="6251e-142">Set this property to "follow" to follow symbolic links and act on the links target (for example.</span></span> <span data-ttu-id="6251e-143">Kopieer het bestand in plaats van de koppeling).</span><span class="sxs-lookup"><span data-stu-id="6251e-143">copy the file instead of the link).</span></span> <span data-ttu-id="6251e-144">Deze eigenschap instellen op 'beheren' om te reageren op de koppeling (bijvoorbeeld)</span><span class="sxs-lookup"><span data-stu-id="6251e-144">Set this property to "manage" to act on the link (for example.</span></span> <span data-ttu-id="6251e-145">Kopieer de koppeling zelf).</span><span class="sxs-lookup"><span data-stu-id="6251e-145">copy the link itself).</span></span> <span data-ttu-id="6251e-146">Deze eigenschap instellen op 'negeren' om door te negeren symbolische koppelingen.</span><span class="sxs-lookup"><span data-stu-id="6251e-146">Set this property to "ignore" to ignore symbolic links.</span></span>| 
| <span data-ttu-id="6251e-147">Groep</span><span class="sxs-lookup"><span data-stu-id="6251e-147">Group</span></span>| <span data-ttu-id="6251e-148">De naam van de **groep** eigenaar van het bestand of map.</span><span class="sxs-lookup"><span data-stu-id="6251e-148">The name of the **Group** to own the file or directory.</span></span>| 
| <span data-ttu-id="6251e-149">Modus</span><span class="sxs-lookup"><span data-stu-id="6251e-149">Mode</span></span>| <span data-ttu-id="6251e-150">Hiermee geeft u de gewenste machtigingen voor de resource octaal of symbolische-notatie.</span><span class="sxs-lookup"><span data-stu-id="6251e-150">Specifies the desired permissions for the resource, in octal or symbolic notation.</span></span> <span data-ttu-id="6251e-151">(bijvoorbeeld 777 of rwxrwxrwx).</span><span class="sxs-lookup"><span data-stu-id="6251e-151">(for example, 777 or rwxrwxrwx).</span></span> <span data-ttu-id="6251e-152">Als symbolische notatie wordt gebruikt, bieden niet het eerste teken waarmee wordt aangegeven van de map of bestand.</span><span class="sxs-lookup"><span data-stu-id="6251e-152">If using symbolic notation, do not provide the first character which indicates directory or file.</span></span>| 
| <span data-ttu-id="6251e-153">dependsOn</span><span class="sxs-lookup"><span data-stu-id="6251e-153">DependsOn</span></span> | <span data-ttu-id="6251e-154">Hiermee wordt aangegeven dat de configuratie van een andere resource uitvoeren moet voordat deze bron is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="6251e-154">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="6251e-155">Bijvoorbeeld, als de **ID** van de resource is scriptblok configuratie die u wilt uitvoeren eerst **ResourceName** en het type **ResourceType**, de syntaxis voor het gebruik van deze de eigenschap is `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="6251e-155">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 

## <a name="additional-information"></a><span data-ttu-id="6251e-156">Als u meer informatie</span><span class="sxs-lookup"><span data-stu-id="6251e-156">Additional Information</span></span>


<span data-ttu-id="6251e-157">Linux- en Windows verschillende regeleindeteken in tekstbestanden standaard en dit kan leiden tot onverwachte resultaten bij het configureren van een aantal bestanden op een Linux-computer met __nxFile__.</span><span class="sxs-lookup"><span data-stu-id="6251e-157">Linux and Windows use different line break characters in text files by default, and this can cause unexpected results when configuring some files on a Linux computer with __nxFile__.</span></span> <span data-ttu-id="6251e-158">Er zijn meerdere manieren voor het beheren van de inhoud van een Linux-bestand zonder problemen veroorzaakt door een onverwachte regeleindeteken:</span><span class="sxs-lookup"><span data-stu-id="6251e-158">There are multiple ways to manage the content of a Linux file while avoiding issues caused by unexpected line break characters:</span></span>

<span data-ttu-id="6251e-159">Stap 1: Het bestand kopiëren vanaf een externe bron (http, https of ftp): een bestand op Linux maken met de gewenste inhoud, en de knooppunten die u configureert Faseren op een webserver of FTP-server toegankelijk is.</span><span class="sxs-lookup"><span data-stu-id="6251e-159">Step 1: Copy the file from a remote source (http, https, or ftp): create a file on Linux with the desired contents, and stage it on a web or ftp server accessible the node(s) you will configure.</span></span> <span data-ttu-id="6251e-160">Definieer de __bronpad__ eigenschap in de __nxFile__ resource met de webserver of FTP-URL naar het bestand.</span><span class="sxs-lookup"><span data-stu-id="6251e-160">Define the __SourcePath__ property in the __nxFile__ resource with the web or ftp URL to the file.</span></span>

```
Import-DSCResource -Module nx
Node $Node
{
nxFile resolvConf
{
    SourcePath = "http://10.185.85.11/conf/resolv.conf"
    DestinationPath = "/etc/resolv.conf"
    Mode = "644"        
    Type = "file"
    
}
        
}
```


<span data-ttu-id="6251e-161">Stap 2: De inhoud van het bestand in het PowerShell-script met lezen [Get-inhoud](https://technet.microsoft.com/en-us/library/hh849787.aspx) nadat u de __$OFS__ eigenschap om de Linux-regeleinde-teken te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6251e-161">Step 2: Read the file contents in the PowerShell script with [Get-Content](https://technet.microsoft.com/en-us/library/hh849787.aspx) after setting the __$OFS__ property to use the Linux line-break character.</span></span>


```
Import-DSCResource -Module nx
Node $Node
{
$OFS = "`n"
$Contents = Get-Content C:\temp\resolv.conf

nxFile resolvConf
{
    DestinationPath = "/etc/resolv.conf"
    Mode = "644"        
    Type = "file"
    Contents = "$Contents"
}

}
```


<span data-ttu-id="6251e-162">Stap 3: Een PowerShell-functie gebruiken Windows regeleinden vervangt door de regeleindetekens Linux.</span><span class="sxs-lookup"><span data-stu-id="6251e-162">Step 3: Use a PowerShell function to replace Windows line breaks with Linux line-break characters.</span></span>

```
Function LinuxString($inputStr){
    $outputStr = $inputStr.Replace("`r`n","`n")
    $ouputStr += "`n"
    Return $outputStr
}

Import-DSCResource -Module nx
Node $Node
{

$Contents = @'
search contoso.com
domain contoso.com
nameserver 10.185.85.11
'@

$Contents = LinuxString $Contents

nxFile resolvConf
{
    DestinationPath = "/etc/resolv.conf"
    Mode = "644"        
    Type = "file"
    Contents = $Contents
    
}
}
```

## <a name="example"></a><span data-ttu-id="6251e-163">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="6251e-163">Example</span></span>

<span data-ttu-id="6251e-164">Het volgende voorbeeld zorgt ervoor dat de map `/opt/mydir` bestaat, en of een bestand met de opgegeven inhoud deze map bestaat.</span><span class="sxs-lookup"><span data-stu-id="6251e-164">The following example ensures that the directory `/opt/mydir` exists, and that a file with specified contents exists this directory.</span></span>

```
Import-DSCResource -Module nx 

Node $node {
nxFile DirectoryExample
{
   Ensure = "Present"
   DestinationPath = "/opt/mydir"
   Type = "Directory"
}

nxFile FileExample
{
    Ensure = "Present"
    Destinationpath = "/opt/mydir/myfile"
    Contents=@"
#!/bin/bash`necho "hello world"`n
"@ 
    Mode = “755”
    DependsOn = "[nxFile]DirectoryExample"
} 
}
```
