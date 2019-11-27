---
title: ScrollBar のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 7093a78555aefd73f9bb05c0a7b5fab6b66176fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283408"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="d8997-102">ScrollBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="d8997-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="d8997-103">このトピックでは、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d8997-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="d8997-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="d8997-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d8997-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8997-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="d8997-106">ScrollBar の部分</span><span class="sxs-lookup"><span data-stu-id="d8997-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="d8997-107">次の表に、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールの名前付きの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="d8997-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="d8997-108">要素</span><span class="sxs-lookup"><span data-stu-id="d8997-108">Part</span></span>|<span data-ttu-id="d8997-109">種類</span><span class="sxs-lookup"><span data-stu-id="d8997-109">Type</span></span>|<span data-ttu-id="d8997-110">説明</span><span class="sxs-lookup"><span data-stu-id="d8997-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d8997-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="d8997-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="d8997-112"><xref:System.Windows.Controls.Primitives.ScrollBar>の位置を示す要素のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="d8997-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="d8997-113">スクロールバーの状態</span><span class="sxs-lookup"><span data-stu-id="d8997-113">ScrollBar States</span></span>  
 <span data-ttu-id="d8997-114">次の表は、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8997-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="d8997-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="d8997-115">VisualState Name</span></span>|<span data-ttu-id="d8997-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="d8997-116">VisualStateGroup Name</span></span>|<span data-ttu-id="d8997-117">説明</span><span class="sxs-lookup"><span data-stu-id="d8997-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="d8997-118">標準</span><span class="sxs-lookup"><span data-stu-id="d8997-118">Normal</span></span>|<span data-ttu-id="d8997-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d8997-119">CommonStates</span></span>|<span data-ttu-id="d8997-120">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="d8997-120">The default state.</span></span>|  
|<span data-ttu-id="d8997-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d8997-121">MouseOver</span></span>|<span data-ttu-id="d8997-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d8997-122">CommonStates</span></span>|<span data-ttu-id="d8997-123">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="d8997-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="d8997-124">無効</span><span class="sxs-lookup"><span data-stu-id="d8997-124">Disabled</span></span>|<span data-ttu-id="d8997-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d8997-125">CommonStates</span></span>|<span data-ttu-id="d8997-126">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d8997-126">The control is disabled.</span></span>|  
|<span data-ttu-id="d8997-127">Valid</span><span class="sxs-lookup"><span data-stu-id="d8997-127">Valid</span></span>|<span data-ttu-id="d8997-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d8997-128">ValidationStates</span></span>|<span data-ttu-id="d8997-129">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="d8997-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d8997-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d8997-130">InvalidFocused</span></span>|<span data-ttu-id="d8997-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d8997-131">ValidationStates</span></span>|<span data-ttu-id="d8997-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティが `true`、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="d8997-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="d8997-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d8997-133">InvalidUnfocused</span></span>|<span data-ttu-id="d8997-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d8997-134">ValidationStates</span></span>|<span data-ttu-id="d8997-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティが `true`、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="d8997-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="d8997-136">ScrollBar ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="d8997-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="d8997-137">次の例は、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8997-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="d8997-138">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8997-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d8997-139">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8997-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8997-140">参照</span><span class="sxs-lookup"><span data-stu-id="d8997-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d8997-141">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="d8997-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d8997-142">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d8997-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d8997-143">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="d8997-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="d8997-144">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="d8997-144">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
