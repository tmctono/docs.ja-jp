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
ms.openlocfilehash: 016556fb825ddf60af7dc572d6fda7323b9bb09d
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671983"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="b3166-102">ScrollBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b3166-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="b3166-103">このトピックでは、 <xref:System.Windows.Controls.Primitives.ScrollBar>コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3166-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="b3166-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="b3166-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b3166-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3166-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="b3166-106">ScrollBar の部分</span><span class="sxs-lookup"><span data-stu-id="b3166-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="b3166-107">次の表に、 <xref:System.Windows.Controls.Primitives.ScrollBar>コントロールの名前付きの部分を示します。</span><span class="sxs-lookup"><span data-stu-id="b3166-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="b3166-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="b3166-108">Part</span></span>|<span data-ttu-id="b3166-109">種類</span><span class="sxs-lookup"><span data-stu-id="b3166-109">Type</span></span>|<span data-ttu-id="b3166-110">説明</span><span class="sxs-lookup"><span data-stu-id="b3166-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b3166-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="b3166-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="b3166-112">の位置を示す要素のコンテナー <xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="b3166-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="b3166-113">スクロールバーの状態</span><span class="sxs-lookup"><span data-stu-id="b3166-113">ScrollBar States</span></span>  
 <span data-ttu-id="b3166-114">次の表に、 <xref:System.Windows.Controls.Primitives.ScrollBar>コントロールの表示状態を示します。</span><span class="sxs-lookup"><span data-stu-id="b3166-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="b3166-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="b3166-115">VisualState Name</span></span>|<span data-ttu-id="b3166-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="b3166-116">VisualStateGroup Name</span></span>|<span data-ttu-id="b3166-117">説明</span><span class="sxs-lookup"><span data-stu-id="b3166-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="b3166-118">標準</span><span class="sxs-lookup"><span data-stu-id="b3166-118">Normal</span></span>|<span data-ttu-id="b3166-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b3166-119">CommonStates</span></span>|<span data-ttu-id="b3166-120">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="b3166-120">The default state.</span></span>|  
|<span data-ttu-id="b3166-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="b3166-121">MouseOver</span></span>|<span data-ttu-id="b3166-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b3166-122">CommonStates</span></span>|<span data-ttu-id="b3166-123">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="b3166-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="b3166-124">Disabled</span><span class="sxs-lookup"><span data-stu-id="b3166-124">Disabled</span></span>|<span data-ttu-id="b3166-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b3166-125">CommonStates</span></span>|<span data-ttu-id="b3166-126">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b3166-126">The control is disabled.</span></span>|  
|<span data-ttu-id="b3166-127">有効</span><span class="sxs-lookup"><span data-stu-id="b3166-127">Valid</span></span>|<span data-ttu-id="b3166-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b3166-128">ValidationStates</span></span>|<span data-ttu-id="b3166-129">コントロールは<xref:System.Windows.Controls.Validation>クラス<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>を使用し、添付プロパティは`false`です。</span><span class="sxs-lookup"><span data-stu-id="b3166-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b3166-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b3166-130">InvalidFocused</span></span>|<span data-ttu-id="b3166-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b3166-131">ValidationStates</span></span>|<span data-ttu-id="b3166-132">添付プロパティは`true`であり、コントロールにフォーカスがあります。 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b3166-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="b3166-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b3166-133">InvalidUnfocused</span></span>|<span data-ttu-id="b3166-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b3166-134">ValidationStates</span></span>|<span data-ttu-id="b3166-135">添付プロパティが`true`であり、コントロールにフォーカスがありません。 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b3166-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="b3166-136">ScrollBar ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="b3166-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="b3166-137">次の例は、 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Primitives.ScrollBar>コントロールのを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3166-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="b3166-138">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3166-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b3166-139">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3166-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3166-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3166-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b3166-141">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b3166-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b3166-142">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b3166-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b3166-143">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b3166-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="b3166-144">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b3166-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
