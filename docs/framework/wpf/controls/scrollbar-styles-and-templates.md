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
ms.openlocfilehash: f85a6fb31adac71541eed31a1ccfde9e06028af7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361149"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="651a1-102">ScrollBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="651a1-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="651a1-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.Primitives.ScrollBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="651a1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="651a1-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="651a1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="651a1-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="651a1-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="651a1-106">スクロール バーの部品</span><span class="sxs-lookup"><span data-stu-id="651a1-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="651a1-107">次の表に、名前付きパーツ、<xref:System.Windows.Controls.Primitives.ScrollBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="651a1-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="651a1-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="651a1-108">Part</span></span>|<span data-ttu-id="651a1-109">型</span><span class="sxs-lookup"><span data-stu-id="651a1-109">Type</span></span>|<span data-ttu-id="651a1-110">説明</span><span class="sxs-lookup"><span data-stu-id="651a1-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="651a1-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="651a1-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="651a1-112">位置を示す要素のコンテナー、<xref:System.Windows.Controls.Primitives.ScrollBar>します。</span><span class="sxs-lookup"><span data-stu-id="651a1-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="651a1-113">スクロール バーの状態</span><span class="sxs-lookup"><span data-stu-id="651a1-113">ScrollBar States</span></span>  
 <span data-ttu-id="651a1-114">次の表のビジュアルの状態、<xref:System.Windows.Controls.Primitives.ScrollBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="651a1-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="651a1-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="651a1-115">VisualState Name</span></span>|<span data-ttu-id="651a1-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="651a1-116">VisualStateGroup Name</span></span>|<span data-ttu-id="651a1-117">説明</span><span class="sxs-lookup"><span data-stu-id="651a1-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="651a1-118">標準</span><span class="sxs-lookup"><span data-stu-id="651a1-118">Normal</span></span>|<span data-ttu-id="651a1-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="651a1-119">CommonStates</span></span>|<span data-ttu-id="651a1-120">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="651a1-120">The default state.</span></span>|  
|<span data-ttu-id="651a1-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="651a1-121">MouseOver</span></span>|<span data-ttu-id="651a1-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="651a1-122">CommonStates</span></span>|<span data-ttu-id="651a1-123">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="651a1-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="651a1-124">無効</span><span class="sxs-lookup"><span data-stu-id="651a1-124">Disabled</span></span>|<span data-ttu-id="651a1-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="651a1-125">CommonStates</span></span>|<span data-ttu-id="651a1-126">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="651a1-126">The control is disabled.</span></span>|  
|<span data-ttu-id="651a1-127">有効</span><span class="sxs-lookup"><span data-stu-id="651a1-127">Valid</span></span>|<span data-ttu-id="651a1-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="651a1-128">ValidationStates</span></span>|<span data-ttu-id="651a1-129">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="651a1-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="651a1-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="651a1-130">InvalidFocused</span></span>|<span data-ttu-id="651a1-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="651a1-131">ValidationStates</span></span>|<span data-ttu-id="651a1-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="651a1-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="651a1-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="651a1-133">InvalidUnfocused</span></span>|<span data-ttu-id="651a1-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="651a1-134">ValidationStates</span></span>|<span data-ttu-id="651a1-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="651a1-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="651a1-136">ScrollBar の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="651a1-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="651a1-137">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Primitives.ScrollBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="651a1-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="651a1-138">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="651a1-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="651a1-139">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="651a1-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="651a1-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="651a1-140">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="651a1-141">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="651a1-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="651a1-142">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="651a1-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="651a1-143">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="651a1-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="651a1-144">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="651a1-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
