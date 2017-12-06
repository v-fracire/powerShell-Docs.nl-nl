---
ms.date: 2017-06-05
keywords: PowerShell-cmdlet
title: Het Object ISEAddOnTool
ms.assetid: ce84d8bc-07ba-41f6-bdde-d6f3fddcd1e3
ms.openlocfilehash: b813fcac547c8069e84741081a3ceb00044bab87
ms.sourcegitcommit: 3720ce4efb6735694cfb53a1b793d949af5d1bc5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/29/2017
---
# <a name="the-iseaddontool-object"></a><span data-ttu-id="3b324-103">Het Object ISEAddOnTool</span><span class="sxs-lookup"><span data-stu-id="3b324-103">The ISEAddOnTool Object</span></span>
  <span data-ttu-id="3b324-104">Een **ISEAddonTool** object vertegenwoordigt een geïnstalleerde invoegtoepassing hulpprogramma dat aanvullende functionaliteit voor Windows PowerShell ISE biedt.</span><span class="sxs-lookup"><span data-stu-id="3b324-104">An **ISEAddonTool** object represents an installed add-on tool that provides additional functionality toWindows PowerShell ISE.</span></span> <span data-ttu-id="3b324-105">Een voorbeeld is de **opdrachten** hulpprogramma dat u kunt weergeven door te klikken op **weergave**, klikt u vervolgens **weergeven opdracht invoegtoepassing**.</span><span class="sxs-lookup"><span data-stu-id="3b324-105">An example is the **Commands** tool that you can display by clicking **View**, then **Show Command Add-on**.</span></span> <span data-ttu-id="3b324-106">Dit hulpprogramma vervolgens toegankelijk is voor u het bewerken van de verschillende beschikbare **ISEAddOnTool** objecten.</span><span class="sxs-lookup"><span data-stu-id="3b324-106">This tool is then accessible to you by manipulating the various available **ISEAddOnTool** objects.</span></span>

 <span data-ttu-id="3b324-107">Elke invoegtoepassing hulpprogramma kan worden gekoppeld aan het deelvenster met verticale of horizontale deelvenster.</span><span class="sxs-lookup"><span data-stu-id="3b324-107">Each add-on tool can be associated with either the vertical pane or the horizontal pane.</span></span> <span data-ttu-id="3b324-108">De verticale deelvenster is de rechterrand van Windows PowerShell ISE gedokt.</span><span class="sxs-lookup"><span data-stu-id="3b324-108">The vertical pane is docked to the right edge of Windows PowerShell ISE.</span></span> <span data-ttu-id="3b324-109">De horizontale deelvenster is de onderrand gedokt.</span><span class="sxs-lookup"><span data-stu-id="3b324-109">The horizontal pane is docked to the bottom edge.</span></span>

 <span data-ttu-id="3b324-110">Elk tabblad PowerShell in Windows PowerShell ISE kunt hebben een eigen set hulpprogramma's voor invoegtoepassing geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="3b324-110">Each PowerShell tab in Windows PowerShell ISE can have its own set of add-on tools installed.</span></span> <span data-ttu-id="3b324-111">Zie [$psISE.CurrentPowerShellTab.HorizontalAddOnTools](The-PowerShellTab-Object.md) en [$psISE.CurrentPowerShellTab.VerticalAddOnTools](The-PowerShellTab-Object.md) voor toegang tot de verzameling van hulpprogramma's beschikbaar zijn voor het momenteel geselecteerde tabblad of de dezelfde eigenschappen op een van de **PowerShellTab** objecten in de [$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md) verzamelingsobject.</span><span class="sxs-lookup"><span data-stu-id="3b324-111">See [$psISE.CurrentPowerShellTab.HorizontalAddOnTools](The-PowerShellTab-Object.md) and [$psISE.CurrentPowerShellTab.VerticalAddOnTools](The-PowerShellTab-Object.md) to access the collection of tools available to the currently selected tab or the same properties on any of the **PowerShellTab** objects in the [$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md) collection object.</span></span>

## <a name="methods"></a><span data-ttu-id="3b324-112">Methoden</span><span class="sxs-lookup"><span data-stu-id="3b324-112">Methods</span></span>
 <span data-ttu-id="3b324-113">Er zijn geen Windows PowerShell ISE-specifieke-methoden beschikbaar voor objecten van deze klasse.</span><span class="sxs-lookup"><span data-stu-id="3b324-113">There are no Windows PowerShell ISE-specific methods available for objects of this class.</span></span>

## <a name="properties"></a><span data-ttu-id="3b324-114">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="3b324-114">Properties</span></span>

### <a name="control"></a><span data-ttu-id="3b324-115">Beheer</span><span class="sxs-lookup"><span data-stu-id="3b324-115">Control</span></span>
  <span data-ttu-id="3b324-116">Ondersteunde Windows PowerShell ISE 3.0 en hoger, en niet aanwezig in eerdere versies.</span><span class="sxs-lookup"><span data-stu-id="3b324-116">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="3b324-117">De **besturingselement** eigenschap leestoegang tot veel van de details van het hulpprogramma van de invoegtoepassing opdrachten bevat.</span><span class="sxs-lookup"><span data-stu-id="3b324-117">The **Control** property provides read access to many of the details of the Commands add-on tool.</span></span>

```
# View the properties of the Commands add-on tool.
# (assumes that it is visible in the vertical pane)
$psISE.CurrentVisibleVerticalTool.Control
HostObject                  : Microsoft.PowerShell.Host.ISE.ObjectModelRoot
Content                     :
HasContent                  :
ContentTemplate             :
ContentTemplateSelector     :
ContentStringFormat         :
BorderBrush                 :
BorderThickness             :
Background                  :
Foreground                  :
FontFamily                  :
FontSize                    :
FontStretch                 :
FontStyle                   :
FontWeight                  :
HorizontalContentAlignment  :
VerticalContentAlignment    :
TabIndex                    :
IsTabStop                   :
Padding                     :
Template                    : System.Windows.Controls.ControlTemplate
Style                       :
OverridesDefaultStyle       :
UseLayoutRounding           :
Triggers                    : {}
TemplatedParent             :
Resources                   : {System.Windows.Controls.TabItem}
DataContext                 :
BindingGroup                :
Language                    :
Name                        :
Tag                         :
InputScope                  :
ActualWidth                 : 370.75
ActualHeight                : 676.559097412109
LayoutTransform             :
Width                       :
MinWidth                    :
MaxWidth                    :
Height                      :
MinHeight                   :
MaxHeight                   :
FlowDirection               : LeftToRight
Margin                      :
HorizontalAlignment         :
VerticalAlignment           :
FocusVisualStyle            :
Cursor                      :
ForceCursor                 :
IsInitialized               : True
IsLoaded                    :
ToolTip                     :
ContextMenu                 :
Parent                      :
HasAnimatedProperties       :
InputBindings               :
CommandBindings             :
AllowDrop                   :
DesiredSize                 : 227.66,676.559097412109
IsMeasureValid              : True
IsArrangeValid              : True
RenderSize                  : 370.75,676.559097412109
RenderTransform             :
RenderTransformOrigin       :
IsMouseDirectlyOver         : False
IsMouseOver                 : False
IsStylusOver                : False
IsKeyboardFocusWithin       : False
IsMouseCaptured             :
IsMouseCaptureWithin        : False
IsStylusDirectlyOver        : False
IsStylusCaptured            :
IsStylusCaptureWithin       : False
IsKeyboardFocused           : False
IsInputMethodEnabled        :
Opacity                     :
OpacityMask                 :
BitmapEffect                :
Effect                      :
BitmapEffectInput           :
CacheMode                   :
Uid                         :
Visibility                  : Visible
ClipToBounds                : False
Clip                        :
SnapsToDevicePixels         : False
IsFocused                   :
IsEnabled                   :
IsHitTestVisible            :
IsVisible                   : True
Focusable                   :
PersistId                   : 1
IsManipulationEnabled       :
AreAnyTouchesOver           : False
AreAnyTouchesDirectlyOver   :
AreAnyTouchesCapturedWithin : False
AreAnyTouchesCaptured       :
TouchesCaptured             : {}
TouchesCapturedWithin       : {}
TouchesOver                 : {}
TouchesDirectlyOver         : {}
DependencyObjectType        : System.Windows.DependencyObjectType
IsSealed                    : False
Dispatcher                  : System.Windows.Threading.Dispatcher

```

### <a name="isvisible"></a><span data-ttu-id="3b324-118">IsVisible</span><span class="sxs-lookup"><span data-stu-id="3b324-118">IsVisible</span></span>
  <span data-ttu-id="3b324-119">Ondersteunde Windows PowerShell ISE 3.0 en hoger, en niet aanwezig in eerdere versies.</span><span class="sxs-lookup"><span data-stu-id="3b324-119">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="3b324-120">De eigenschap van het Boolean-waarde die aangeeft of het hulpprogramma invoegtoepassing zichtbaar in het deelvenster toegewezen is.</span><span class="sxs-lookup"><span data-stu-id="3b324-120">The Boolean property that indicates whether the add-on tool is currently visible in its assigned pane.</span></span> <span data-ttu-id="3b324-121">Als zichtbaar is, kunt u instellen de **IsVisible** eigenschap **$false** verbergen van het hulpprogramma of stel de **IsVisible** eigenschap **$true** om ervoor te een invoegtoepassing hulpprogramma zichtbaar op het tabblad PowerShell. Houd er rekening mee dat wanneer een invoegtoepassing hulpprogramma verborgen is, niet meer toegankelijk zijn via is de **CurrentVisibleHorizontalTool** of **CurrentVisibleVerticalTool** objecten en daarom kan niet worden doorgevoerd zichtbaar met behulp van Deze eigenschap voor dat object.</span><span class="sxs-lookup"><span data-stu-id="3b324-121">If it is visible, you can set the **IsVisible** property to **$false** to hide the tool, or set the **IsVisible** property to **$true** to make an add-on tool visible on its PowerShell tab. Note that after an add-on tool is hidden, it is no longer accessible through the **CurrentVisibleHorizontalTool** or **CurrentVisibleVerticalTool** objects, and therefore cannot be made visible by using this property on that object.</span></span>

```
# Hide the current tool in the vertical tool pane
$psISE.CurrentVisibleVerticalTool.IsVisible = $false
# Show the first tool on the currently selected PowerShell tab
$psISE.CurrentPowerShellTab.VerticalAddOnTools[0].IsVisible=$true

```

### <a name="name"></a><span data-ttu-id="3b324-122">Naam</span><span class="sxs-lookup"><span data-stu-id="3b324-122">Name</span></span>
  <span data-ttu-id="3b324-123">Ondersteunde Windows PowerShell ISE 3.0 en hoger, en niet aanwezig in eerdere versies.</span><span class="sxs-lookup"><span data-stu-id="3b324-123">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

 <span data-ttu-id="3b324-124">De alleen-lezen eigenschap die de naam van het hulpprogramma invoegtoepassing krijgt.</span><span class="sxs-lookup"><span data-stu-id="3b324-124">The read-only property that gets the name of the add-on tool.</span></span>

```
# Gets the name of the visible vertical pane add-on tool.
$psISE.CurrentVisibleVerticalTool.name
Commands

```

## <a name="see-also"></a><span data-ttu-id="3b324-125">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3b324-125">See Also</span></span>
- [<span data-ttu-id="3b324-126">Het Object ISEAddOnToolCollection</span><span class="sxs-lookup"><span data-stu-id="3b324-126">The ISEAddOnToolCollection Object</span></span>](The-ISEAddOnToolCollection-Object.md)
- [<span data-ttu-id="3b324-127">De Windows PowerShell ISE-objectmodel Scripting</span><span class="sxs-lookup"><span data-stu-id="3b324-127">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="3b324-128">Naslaginformatie voor Windows PowerShell ISE-objectmodel</span><span class="sxs-lookup"><span data-stu-id="3b324-128">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md)
- [<span data-ttu-id="3b324-129">De hiërarchie ISE</span><span class="sxs-lookup"><span data-stu-id="3b324-129">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
