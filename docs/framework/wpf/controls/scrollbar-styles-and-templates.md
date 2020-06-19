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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283408"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="65d4e-102">ScrollBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="65d4e-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="65d4e-103">このトピックでは、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="65d4e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="65d4e-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="65d4e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="65d4e-105">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="65d4e-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="65d4e-106">ScrollBar のパーツ</span><span class="sxs-lookup"><span data-stu-id="65d4e-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="65d4e-107">次の表は、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="65d4e-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="65d4e-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="65d4e-108">Part</span></span>|<span data-ttu-id="65d4e-109">種類</span><span class="sxs-lookup"><span data-stu-id="65d4e-109">Type</span></span>|<span data-ttu-id="65d4e-110">説明</span><span class="sxs-lookup"><span data-stu-id="65d4e-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="65d4e-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="65d4e-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="65d4e-112"><xref:System.Windows.Controls.Primitives.ScrollBar> の位置を示す要素のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="65d4e-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="65d4e-113">ScrollBar の状態</span><span class="sxs-lookup"><span data-stu-id="65d4e-113">ScrollBar States</span></span>  
 <span data-ttu-id="65d4e-114">次の表は、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="65d4e-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="65d4e-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="65d4e-115">VisualState Name</span></span>|<span data-ttu-id="65d4e-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="65d4e-116">VisualStateGroup Name</span></span>|<span data-ttu-id="65d4e-117">説明</span><span class="sxs-lookup"><span data-stu-id="65d4e-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="65d4e-118">標準</span><span class="sxs-lookup"><span data-stu-id="65d4e-118">Normal</span></span>|<span data-ttu-id="65d4e-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65d4e-119">CommonStates</span></span>|<span data-ttu-id="65d4e-120">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="65d4e-120">The default state.</span></span>|  
|<span data-ttu-id="65d4e-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="65d4e-121">MouseOver</span></span>|<span data-ttu-id="65d4e-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65d4e-122">CommonStates</span></span>|<span data-ttu-id="65d4e-123">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="65d4e-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="65d4e-124">無効</span><span class="sxs-lookup"><span data-stu-id="65d4e-124">Disabled</span></span>|<span data-ttu-id="65d4e-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="65d4e-125">CommonStates</span></span>|<span data-ttu-id="65d4e-126">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="65d4e-126">The control is disabled.</span></span>|  
|<span data-ttu-id="65d4e-127">有効</span><span class="sxs-lookup"><span data-stu-id="65d4e-127">Valid</span></span>|<span data-ttu-id="65d4e-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65d4e-128">ValidationStates</span></span>|<span data-ttu-id="65d4e-129">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="65d4e-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="65d4e-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="65d4e-130">InvalidFocused</span></span>|<span data-ttu-id="65d4e-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65d4e-131">ValidationStates</span></span>|<span data-ttu-id="65d4e-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="65d4e-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="65d4e-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="65d4e-133">InvalidUnfocused</span></span>|<span data-ttu-id="65d4e-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65d4e-134">ValidationStates</span></span>|<span data-ttu-id="65d4e-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="65d4e-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="65d4e-136">ScrollBar の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="65d4e-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="65d4e-137">次の例は、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="65d4e-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="65d4e-138">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="65d4e-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="65d4e-139">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65d4e-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d4e-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="65d4e-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="65d4e-141">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="65d4e-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="65d4e-142">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="65d4e-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="65d4e-143">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="65d4e-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="65d4e-144">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="65d4e-144">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
