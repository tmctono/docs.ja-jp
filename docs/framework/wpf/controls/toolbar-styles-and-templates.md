---
title: ToolBar のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: 1cbb8d54a544b70b4a484c06c6bb2e9ca25029da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790742"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="0db30-102">ToolBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0db30-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="0db30-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.ToolBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0db30-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="0db30-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="0db30-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0db30-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0db30-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="0db30-106">ツールバーの部分</span><span class="sxs-lookup"><span data-stu-id="0db30-106">ToolBar Parts</span></span>  
 <span data-ttu-id="0db30-107">次の表に、名前付きパーツ、<xref:System.Windows.Controls.ToolBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0db30-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="0db30-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="0db30-108">Part</span></span>|<span data-ttu-id="0db30-109">型</span><span class="sxs-lookup"><span data-stu-id="0db30-109">Type</span></span>|<span data-ttu-id="0db30-110">説明</span><span class="sxs-lookup"><span data-stu-id="0db30-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0db30-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="0db30-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="0db30-112">コントロールを格納しているオブジェクト、<xref:System.Windows.Controls.ToolBar>します。</span><span class="sxs-lookup"><span data-stu-id="0db30-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="0db30-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="0db30-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="0db30-114">オーバーフロー領域内にあるコントロールを格納しているオブジェクト、<xref:System.Windows.Controls.ToolBar>します。</span><span class="sxs-lookup"><span data-stu-id="0db30-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="0db30-115">作成するときに、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.ToolBar>、テンプレートが含まれます、<xref:System.Windows.Controls.ItemsPresenter>内、 <xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="0db30-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="0db30-116">(、<xref:System.Windows.Controls.ItemsPresenter>内の各項目が表示されます、 <xref:System.Windows.Controls.ToolBar>、<xref:System.Windows.Controls.ScrollViewer>コントロール内でスクロールできます)。</span><span class="sxs-lookup"><span data-stu-id="0db30-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="0db30-117">場合、<xref:System.Windows.Controls.ItemsPresenter>の直接の子ではない、<xref:System.Windows.Controls.ScrollViewer>を付ける必要があります、<xref:System.Windows.Controls.ItemsPresenter>名、`ItemsPresenter`します。</span><span class="sxs-lookup"><span data-stu-id="0db30-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="0db30-118">ツールバーの状態</span><span class="sxs-lookup"><span data-stu-id="0db30-118">ToolBar States</span></span>  
 <span data-ttu-id="0db30-119">次の表のビジュアルの状態、<xref:System.Windows.Controls.ToolBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0db30-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="0db30-120">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="0db30-120">VisualState Name</span></span>|<span data-ttu-id="0db30-121">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="0db30-121">VisualStateGroup Name</span></span>|<span data-ttu-id="0db30-122">説明</span><span class="sxs-lookup"><span data-stu-id="0db30-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0db30-123">有効</span><span class="sxs-lookup"><span data-stu-id="0db30-123">Valid</span></span>|<span data-ttu-id="0db30-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0db30-124">ValidationStates</span></span>|<span data-ttu-id="0db30-125">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="0db30-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0db30-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0db30-126">InvalidFocused</span></span>|<span data-ttu-id="0db30-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0db30-127">ValidationStates</span></span>|<span data-ttu-id="0db30-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="0db30-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0db30-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0db30-129">InvalidUnfocused</span></span>|<span data-ttu-id="0db30-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0db30-130">ValidationStates</span></span>|<span data-ttu-id="0db30-131"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="0db30-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="0db30-132">ツールバーの ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="0db30-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="0db30-133">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.ToolBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0db30-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="0db30-134">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="0db30-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0db30-135">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0db30-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db30-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="0db30-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0db30-137">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0db30-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0db30-138">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0db30-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0db30-139">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0db30-139">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="0db30-140">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0db30-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
