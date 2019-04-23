---
title: ボタンのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: ec64c7c2051b12cba01135054a90e54864b7386a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116338"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="a1301-102">ボタンのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a1301-102">Button Styles and Templates</span></span>
<span data-ttu-id="a1301-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a1301-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="a1301-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="a1301-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a1301-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1301-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="a1301-106">ボタンのパーツ</span><span class="sxs-lookup"><span data-stu-id="a1301-106">Button Parts</span></span>  
 <span data-ttu-id="a1301-107"><xref:System.Windows.Controls.Button>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="a1301-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="a1301-108">ボタンの状態</span><span class="sxs-lookup"><span data-stu-id="a1301-108">Button States</span></span>  
 <span data-ttu-id="a1301-109">次の表のビジュアルの状態、<xref:System.Windows.Controls.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a1301-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="a1301-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="a1301-110">VisualState Name</span></span>|<span data-ttu-id="a1301-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="a1301-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a1301-112">説明</span><span class="sxs-lookup"><span data-stu-id="a1301-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a1301-113">標準</span><span class="sxs-lookup"><span data-stu-id="a1301-113">Normal</span></span>|<span data-ttu-id="a1301-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a1301-114">CommonStates</span></span>|<span data-ttu-id="a1301-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="a1301-115">The default state.</span></span>|  
|<span data-ttu-id="a1301-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a1301-116">MouseOver</span></span>|<span data-ttu-id="a1301-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a1301-117">CommonStates</span></span>|<span data-ttu-id="a1301-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="a1301-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="a1301-119">押されている</span><span class="sxs-lookup"><span data-stu-id="a1301-119">Pressed</span></span>|<span data-ttu-id="a1301-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a1301-120">CommonStates</span></span>|<span data-ttu-id="a1301-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="a1301-121">The control is pressed.</span></span>|  
|<span data-ttu-id="a1301-122">無効</span><span class="sxs-lookup"><span data-stu-id="a1301-122">Disabled</span></span>|<span data-ttu-id="a1301-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a1301-123">CommonStates</span></span>|<span data-ttu-id="a1301-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a1301-124">The control is disabled.</span></span>|  
|<span data-ttu-id="a1301-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="a1301-125">Focused</span></span>|<span data-ttu-id="a1301-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a1301-126">FocusStates</span></span>|<span data-ttu-id="a1301-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="a1301-127">The control has focus.</span></span>|  
|<span data-ttu-id="a1301-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="a1301-128">Unfocused</span></span>|<span data-ttu-id="a1301-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a1301-129">FocusStates</span></span>|<span data-ttu-id="a1301-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="a1301-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="a1301-131">有効</span><span class="sxs-lookup"><span data-stu-id="a1301-131">Valid</span></span>|<span data-ttu-id="a1301-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a1301-132">ValidationStates</span></span>|<span data-ttu-id="a1301-133">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="a1301-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a1301-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a1301-134">InvalidFocused</span></span>|<span data-ttu-id="a1301-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a1301-135">ValidationStates</span></span>|<span data-ttu-id="a1301-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`コントロールにフォーカスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="a1301-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="a1301-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a1301-137">InvalidUnfocused</span></span>|<span data-ttu-id="a1301-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a1301-138">ValidationStates</span></span>|<span data-ttu-id="a1301-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`コントロールにフォーカスがないとします。</span><span class="sxs-lookup"><span data-stu-id="a1301-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="a1301-140">ボタン ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="a1301-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="a1301-141">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a1301-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="a1301-142">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1301-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a1301-143">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1301-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1301-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1301-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a1301-145">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a1301-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a1301-146">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a1301-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a1301-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a1301-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="a1301-148">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a1301-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
