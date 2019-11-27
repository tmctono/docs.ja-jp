---
title: StatusBar のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 843c9003edbe94115719a63a968eda3833515a85
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283369"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="bf915-102">StatusBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bf915-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="bf915-103">このトピックでは、<xref:System.Windows.Controls.Primitives.StatusBar> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bf915-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="bf915-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="bf915-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bf915-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf915-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="bf915-106">StatusBar パーツ</span><span class="sxs-lookup"><span data-stu-id="bf915-106">StatusBar Parts</span></span>  
 <span data-ttu-id="bf915-107"><xref:System.Windows.Controls.Primitives.StatusBar> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="bf915-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="bf915-108">ステータスバーの状態</span><span class="sxs-lookup"><span data-stu-id="bf915-108">StatusBar States</span></span>  
 <span data-ttu-id="bf915-109">次の表は、<xref:System.Windows.Controls.Primitives.StatusBar> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf915-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="bf915-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="bf915-110">VisualState Name</span></span>|<span data-ttu-id="bf915-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="bf915-111">VisualStateGroup Name</span></span>|<span data-ttu-id="bf915-112">説明</span><span class="sxs-lookup"><span data-stu-id="bf915-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bf915-113">Valid</span><span class="sxs-lookup"><span data-stu-id="bf915-113">Valid</span></span>|<span data-ttu-id="bf915-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bf915-114">ValidationStates</span></span>|<span data-ttu-id="bf915-115">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="bf915-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bf915-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bf915-116">InvalidFocused</span></span>|<span data-ttu-id="bf915-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bf915-117">ValidationStates</span></span>|<span data-ttu-id="bf915-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="bf915-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bf915-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bf915-119">InvalidUnfocused</span></span>|<span data-ttu-id="bf915-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bf915-120">ValidationStates</span></span>|<span data-ttu-id="bf915-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="bf915-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="bf915-122">StatusBarItem パーツ</span><span class="sxs-lookup"><span data-stu-id="bf915-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="bf915-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="bf915-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="bf915-124">ステータスバーの状態</span><span class="sxs-lookup"><span data-stu-id="bf915-124">StatusBar States</span></span>  
 <span data-ttu-id="bf915-125">次の表は、<xref:System.Windows.Controls.Primitives.StatusBarItem> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf915-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="bf915-126">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="bf915-126">VisualState Name</span></span>|<span data-ttu-id="bf915-127">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="bf915-127">VisualStateGroup Name</span></span>|<span data-ttu-id="bf915-128">説明</span><span class="sxs-lookup"><span data-stu-id="bf915-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bf915-129">Valid</span><span class="sxs-lookup"><span data-stu-id="bf915-129">Valid</span></span>|<span data-ttu-id="bf915-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bf915-130">ValidationStates</span></span>|<span data-ttu-id="bf915-131">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="bf915-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bf915-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bf915-132">InvalidFocused</span></span>|<span data-ttu-id="bf915-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bf915-133">ValidationStates</span></span>|<span data-ttu-id="bf915-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="bf915-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bf915-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bf915-135">InvalidUnfocused</span></span>|<span data-ttu-id="bf915-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bf915-136">ValidationStates</span></span>|<span data-ttu-id="bf915-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="bf915-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="bf915-138">StatusBar ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="bf915-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="bf915-139">次の例は、<xref:System.Windows.Controls.Primitives.StatusBar> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf915-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="bf915-140"><xref:System.Windows.Controls.ControlTemplate> では、次のリソースの1つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="bf915-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bf915-141">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf915-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf915-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf915-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bf915-143">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bf915-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="bf915-144">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="bf915-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="bf915-145">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bf915-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="bf915-146">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="bf915-146">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
