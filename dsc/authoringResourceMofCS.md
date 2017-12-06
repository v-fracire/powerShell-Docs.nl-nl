---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: DSC, powershell, configuratie, setup
title: Een DSC-resource in C# ontwerpen
ms.openlocfilehash: c1dc97d4e05499d03450d6172d9674b06a674393
ms.sourcegitcommit: 3720ce4efb6735694cfb53a1b793d949af5d1bc5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/29/2017
---
# <a name="authoring-a-dsc-resource-in-c"></a><span data-ttu-id="0cb9f-103">Een DSC-resource in C# ontwerpen</span><span class="sxs-lookup"><span data-stu-id="0cb9f-103">Authoring a DSC resource in C#</span></span>

> <span data-ttu-id="0cb9f-104">Van toepassing op: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="0cb9f-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="0cb9f-105">Normaal gesproken is een aangepaste bron van Windows PowerShell Desired State Configuration (DSC) geïmplementeerd in een PowerShell-script.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-105">Typically, a Windows PowerShell Desired State Configuration (DSC) custom resource is implemented in a PowerShell script.</span></span> <span data-ttu-id="0cb9f-106">U kunt echter ook de functionaliteit van een aangepaste DSC-resource implementeren met de cmdlets in C# schrijven.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-106">However, you can also implement the functionality of a DSC custom resource by writing cmdlets in C#.</span></span> <span data-ttu-id="0cb9f-107">Zie voor een inleiding op cmdlets in C# schrijven [schrijven van een Windows PowerShell-Cmdlet](https://technet.microsoft.com/en-us/library/dd878294.aspx).</span><span class="sxs-lookup"><span data-stu-id="0cb9f-107">For an introduction on writing cmdlets in C#, see [Writing a Windows PowerShell Cmdlet](https://technet.microsoft.com/en-us/library/dd878294.aspx).</span></span>

<span data-ttu-id="0cb9f-108">Het proces van het maken van het MOF-schema, de mapstructuur maken, importeren en met behulp van uw aangepaste DSC-resource zijn niet alleen uit voor informatie over het implementeren van de resource in C# als cmdlets hetzelfde zoals beschreven in [schrijven van een aangepaste DSC-resource met MOF](authoringResourceMOF.md).</span><span class="sxs-lookup"><span data-stu-id="0cb9f-108">Aside from implementing the resource in C# as cmdlets, the process of creating the MOF schema, creating the folder structure, importing and using your custom DSC resource are the same as described in [Writing a custom DSC resource with MOF](authoringResourceMOF.md).</span></span>

## <a name="writing-a-cmdlet-based-resource"></a><span data-ttu-id="0cb9f-109">Schrijven van een resource op basis van een cmdlet</span><span class="sxs-lookup"><span data-stu-id="0cb9f-109">Writing a cmdlet-based resource</span></span>
<span data-ttu-id="0cb9f-110">In dit voorbeeld implementeert we een eenvoudige resource die u een tekstbestand en de inhoud ervan beheert.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-110">For this example, we will implement a simple resource that manages a text file and its contents.</span></span>

### <a name="writing-the-mof-schema"></a><span data-ttu-id="0cb9f-111">Schrijven van het MOF-schema</span><span class="sxs-lookup"><span data-stu-id="0cb9f-111">Writing the MOF schema</span></span>

<span data-ttu-id="0cb9f-112">Hieronder volgt de MOF resourcedefinitie.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-112">The following is the MOF resource definition.</span></span>

```
[ClassVersion("1.0.0"), FriendlyName("xDemoFile")]
class MSFT_XDemoFile : OMI_BaseResource
{
                [Key, Description("path")] String Path;
                [Write, Description("Should the file be present"), ValueMap{"Present","Absent"}, Values{"Present","Absent"}] String Ensure;
                [Write, Description("Contentof file.")] String Content;                   
};
```

### <a name="setting-up-the-visual-studio-project"></a><span data-ttu-id="0cb9f-113">Instellen van de Visual Studio-project</span><span class="sxs-lookup"><span data-stu-id="0cb9f-113">Setting up the Visual Studio project</span></span>
#### <a name="setting-up-a-cmdlet-project"></a><span data-ttu-id="0cb9f-114">Instellen van een cmdlet-project</span><span class="sxs-lookup"><span data-stu-id="0cb9f-114">Setting up a cmdlet project</span></span>

1. <span data-ttu-id="0cb9f-115">Visual Studio niet openen.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-115">Open Visual Studio.</span></span>
1. <span data-ttu-id="0cb9f-116">Maak een C#-project en geef de naam op.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-116">Create a C# project and provide the name.</span></span>
1. <span data-ttu-id="0cb9f-117">Selecteer **Class Library** uit de beschikbare sjablonen.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-117">Select **Class Library** from the available project templates.</span></span>
1. <span data-ttu-id="0cb9f-118">Klik op **Ok**.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-118">Click **Ok**.</span></span>
1. <span data-ttu-id="0cb9f-119">Een assembly-verwijzing naar System.Automation.Management.dll toevoegen aan uw project.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-119">Add an assembly reference to System.Automation.Management.dll to your project.</span></span>
1. <span data-ttu-id="0cb9f-120">De assemblynaam overeenkomt met de naam van de resource wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-120">Change the assembly name to match the resource name.</span></span> <span data-ttu-id="0cb9f-121">In dit geval de assembly moet worden met de naam **MSFT_XDemoFile**.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-121">In this case, the assembly should be named **MSFT_XDemoFile**.</span></span>

### <a name="writing-the-cmdlet-code"></a><span data-ttu-id="0cb9f-122">De cmdlet-code schrijven</span><span class="sxs-lookup"><span data-stu-id="0cb9f-122">Writing the cmdlet code</span></span>

<span data-ttu-id="0cb9f-123">De volgende C#-code implementeert de **Get-TargetResource**, **Set TargetResource**, en **Test TargetResource** cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-123">The following C# code implements the **Get-TargetResource**, **Set-TargetResource**, and **Test-TargetResource** cmdlets.</span></span>

```C#


namespace cSharpDSCResourceExample
{
    using System;
    using System.Collections.Generic;
    using System.IO;
    using System.Management.Automation;  // Windows PowerShell assembly.

    #region Get-TargetResource

    [OutputType(typeof(System.Collections.Hashtable))]
    [Cmdlet(VerbsCommon.Get, "TargetResource")]
    public class GetTargetResource : PSCmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        /// <summary>
        /// Implement the logic to return the current state of the resource as a hashtable with keys being the resource properties 
        /// and the values are the corresponding current value on the machine.
        /// </summary>
        protected override void ProcessRecord()
        {
            var currentResourceState = new Dictionary<string, string>();
            if (File.Exists(Path))
            {
                currentResourceState.Add("Ensure", "Present");

                // read current content 
                string CurrentContent = "";
                using (var reader = new StreamReader(Path))
                {
                    CurrentContent = reader.ReadToEnd();
                }
                currentResourceState.Add("Content", CurrentContent);
            }
            else
            {
                currentResourceState.Add("Ensure", "Absent");
                currentResourceState.Add("Content", "");
            }
            // write the hashtable in the PS console.
            WriteObject(currentResourceState);
        }
    }
    
    # endregion

    #region Set-TargetResource
    [OutputType(typeof(void))]
    [Cmdlet(VerbsCommon.Set, "TargetResource")]
    public class SetTargetResource : PSCmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        [Parameter(Mandatory = false)]
        
        [ValidateSet("Present", "Absent", IgnoreCase = true)]
        public string Ensure {
            get
            {
                // set the default to present.
               return (this._ensure ?? "Present") ;
            }
            set
            {
                this._ensure = value;
            }
        }

        [Parameter(Mandatory = false)]
        public string Content {
            get { return (string.IsNullOrEmpty(this._content) ? "" : this._content); }
            set { this._content = value; }
        }

        private string _ensure;
        private string _content;

        /// <summary>
        /// Implement the logic to set the state of the machine to the desired state.
        /// </summary>
        protected override void ProcessRecord()
        {
            WriteVerbose(string.Format("Running set with parameters {0}{1}{2}", Path, Ensure, Content));
            if (File.Exists(Path))
            {
                if (Ensure.Equals("absent", StringComparison.InvariantCultureIgnoreCase))
                {
                    File.Delete(Path);
                }
                else
                {
                    // file already exist and ensure "present" is specified. start writing the content to a file
                    if (!string.IsNullOrEmpty(Content))
                    {
                        string existingContent = null;
                        using (var reader = new StreamReader(Path))
                        {
                            existingContent = reader.ReadToEnd();
                        }
                        // check if the content of the file mathes the content passed 
                        if (!existingContent.Equals(Content, StringComparison.InvariantCultureIgnoreCase))
                        {
                            WriteVerbose("Existing content did not match with desired content updating the content of the file");
                            using (var writer = new StreamWriter(Path))
                            {
                                writer.Write(Content);
                                writer.Flush();
                            }
                        }
                    }
                }

            }
            else
            {
                if (Ensure.Equals("present", StringComparison.InvariantCultureIgnoreCase))
                {
                    // if nothing is passed for content just write "" otherwise write the content passed.
                    using (var writer = new StreamWriter(Path))
                    {
                        WriteVerbose(string.Format("Creating a file under path {0} with content {1}", Path, Content));
                        writer.Write(Content);
                    }
                }

            }
            
            /* if you need to reboot the VM. please add the following two line of code.
            PSVariable DscMachineStatus = new PSVariable("DSCMachineStatus", 1, ScopedItemOptions.AllScope);
            this.SessionState.PSVariable.Set(DscMachineStatus);
             */     

        }

    }

    # endregion

    #region Test-TargetResource

    [Cmdlet("Test", "TargetResource")]
    [OutputType(typeof(Boolean))]
    public class TestTargetResource : PSCmdlet
    {   
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        [Parameter(Mandatory = false)]

        [ValidateSet("Present", "Absent", IgnoreCase = true)]
        public string Ensure
        {
            get
            {
                // set the default to present.
                return (this._ensure ?? "Present");
            }
            set
            {
                this._ensure = value;
            }
        }

        [Parameter(Mandatory = false)]
        public string Content
        {
            get { return (string.IsNullOrEmpty(this._content) ? "" : this._content); }
            set { this._content = value; }
        }

        private string _ensure;
        private string _content;

        /// <summary>
        /// Return a boolean value which indicates wheather the current machine is in desired state or not.
        /// </summary>
        protected override void ProcessRecord()
        {
            if (File.Exists(Path)) 
            {
                if( Ensure.Equals("absent", StringComparison.InvariantCultureIgnoreCase))
                {
                    WriteObject(false);
                }
                else
                {
                    // check if the content matches

                    string existingContent = null;
                    using (var stream = new StreamReader(Path))
                    {
                        existingContent = stream.ReadToEnd();
                    }

                    WriteObject(Content.Equals(existingContent, StringComparison.InvariantCultureIgnoreCase));
                }
            }
            else
            {
                WriteObject(Ensure.Equals("Absent", StringComparison.InvariantCultureIgnoreCase));
            }
        }        
    }

    # endregion

}
```

### <a name="deploying-the-resource"></a><span data-ttu-id="0cb9f-124">De resource implementeren</span><span class="sxs-lookup"><span data-stu-id="0cb9f-124">Deploying the resource</span></span>

<span data-ttu-id="0cb9f-125">De gecompileerde dll-bestand moet worden opgeslagen in een bestandsstructuur die vergelijkbaar is met een resource op basis van scripts.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-125">The compiled dll file should be saved in a file structure similar to a script-based resource.</span></span> <span data-ttu-id="0cb9f-126">Hieronder vindt u de mapstructuur voor deze bron.</span><span class="sxs-lookup"><span data-stu-id="0cb9f-126">The following is the folder structure for this resource.</span></span>

```
$env: psmodulepath (folder)
    |- MyDscResources (folder)
        |- MyDscResources.psd1 (file, required)     
        |- DSCResources (folder)
            |- MSFT_XDemoFile (folder)
                |- MSFT_XDemoFile.psd1 (file, optional)
                |- MSFT_XDemoFile.dll (file, required)
                |- MSFT_XDemoFile.schema.mof (file, required)
```

### <a name="see-also"></a><span data-ttu-id="0cb9f-127">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0cb9f-127">See Also</span></span>
#### <a name="concepts"></a><span data-ttu-id="0cb9f-128">Concepten</span><span class="sxs-lookup"><span data-stu-id="0cb9f-128">Concepts</span></span>
[<span data-ttu-id="0cb9f-129">Schrijven van een aangepaste DSC-resource met MOF</span><span class="sxs-lookup"><span data-stu-id="0cb9f-129">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
#### <a name="other-resources"></a><span data-ttu-id="0cb9f-130">Andere bronnen</span><span class="sxs-lookup"><span data-stu-id="0cb9f-130">Other Resources</span></span>
[<span data-ttu-id="0cb9f-131">Schrijven van een Windows PowerShell-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0cb9f-131">Writing a Windows PowerShell Cmdlet</span></span>](https://msdn.microsoft.com/en-us/library/dd878294.aspx)
