---
title: ContextMenu のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: 6650d5a7be8ebe8fc2dcd7af7c854da669de87f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912328"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="5bb47-102">ContextMenu のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5bb47-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="5bb47-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.ContextMenu>コントロール。</span><span class="sxs-lookup"><span data-stu-id="5bb47-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="5bb47-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="5bb47-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5bb47-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bb47-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="5bb47-106">ContextMenu のパーツ</span><span class="sxs-lookup"><span data-stu-id="5bb47-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="5bb47-107"><xref:System.Windows.Controls.ContextMenu>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="5bb47-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="5bb47-108">作成するときに、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.ContextMenu>、テンプレートが含まれます、<xref:System.Windows.Controls.ItemsPresenter>内、 <xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="5bb47-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="5bb47-109">(、<xref:System.Windows.Controls.ItemsPresenter>内の各項目が表示されます、 <xref:System.Windows.Controls.ContextMenu>、<xref:System.Windows.Controls.ScrollViewer>コントロール内でスクロールできます)。</span><span class="sxs-lookup"><span data-stu-id="5bb47-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="5bb47-110">場合、<xref:System.Windows.Controls.ItemsPresenter>の直接の子ではない、<xref:System.Windows.Controls.ScrollViewer>を付ける必要があります、<xref:System.Windows.Controls.ItemsPresenter>名、`ItemsPresenter`します。</span><span class="sxs-lookup"><span data-stu-id="5bb47-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="5bb47-111">コンテキスト メニューの状態</span><span class="sxs-lookup"><span data-stu-id="5bb47-111">ContextMenu States</span></span>  
 <span data-ttu-id="5bb47-112">次の表のビジュアルの状態、<xref:System.Windows.Controls.ContextMenu>コントロール。</span><span class="sxs-lookup"><span data-stu-id="5bb47-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="5bb47-113">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="5bb47-113">VisualState Name</span></span>|<span data-ttu-id="5bb47-114">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="5bb47-114">VisualStateGroup Name</span></span>|<span data-ttu-id="5bb47-115">説明</span><span class="sxs-lookup"><span data-stu-id="5bb47-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5bb47-116">有効</span><span class="sxs-lookup"><span data-stu-id="5bb47-116">Valid</span></span>|<span data-ttu-id="5bb47-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bb47-117">ValidationStates</span></span>|<span data-ttu-id="5bb47-118">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="5bb47-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5bb47-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5bb47-119">InvalidFocused</span></span>|<span data-ttu-id="5bb47-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bb47-120">ValidationStates</span></span>|<span data-ttu-id="5bb47-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="5bb47-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5bb47-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5bb47-122">InvalidUnfocused</span></span>|<span data-ttu-id="5bb47-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5bb47-123">ValidationStates</span></span>|<span data-ttu-id="5bb47-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="5bb47-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="5bb47-125">ContextMenu ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="5bb47-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="5bb47-126">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.ContextMenu>コントロール。</span><span class="sxs-lookup"><span data-stu-id="5bb47-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="5bb47-127"><xref:System.Windows.Controls.ControlTemplate>は次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="5bb47-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5bb47-128">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bb47-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb47-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bb47-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5bb47-130">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5bb47-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5bb47-131">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="5bb47-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5bb47-132">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5bb47-132">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="5bb47-133">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="5bb47-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
