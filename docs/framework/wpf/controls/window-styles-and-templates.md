---
title: ウィンドウのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: ebd21829591b8fefe87aeba0b86280f18eff4f06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62023833"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="4307c-102">ウィンドウのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="4307c-102">Window Styles and Templates</span></span>
<span data-ttu-id="4307c-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Window>コントロール。</span><span class="sxs-lookup"><span data-stu-id="4307c-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="4307c-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="4307c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4307c-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4307c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="4307c-106">ウィンドウの一部</span><span class="sxs-lookup"><span data-stu-id="4307c-106">Window Parts</span></span>  
 <span data-ttu-id="4307c-107"><xref:System.Windows.Window>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="4307c-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="4307c-108">ウィンドウの状態</span><span class="sxs-lookup"><span data-stu-id="4307c-108">Window States</span></span>  
 <span data-ttu-id="4307c-109">次の表のビジュアルの状態、<xref:System.Windows.Window>コントロール。</span><span class="sxs-lookup"><span data-stu-id="4307c-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="4307c-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="4307c-110">VisualState Name</span></span>|<span data-ttu-id="4307c-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="4307c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="4307c-112">説明</span><span class="sxs-lookup"><span data-stu-id="4307c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4307c-113">有効</span><span class="sxs-lookup"><span data-stu-id="4307c-113">Valid</span></span>|<span data-ttu-id="4307c-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4307c-114">ValidationStates</span></span>|<span data-ttu-id="4307c-115">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="4307c-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4307c-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4307c-116">InvalidFocused</span></span>|<span data-ttu-id="4307c-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4307c-117">ValidationStates</span></span>|<span data-ttu-id="4307c-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="4307c-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4307c-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4307c-119">InvalidUnfocused</span></span>|<span data-ttu-id="4307c-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4307c-120">ValidationStates</span></span>|<span data-ttu-id="4307c-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="4307c-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="4307c-122">ウィンドウの ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="4307c-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="4307c-123">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Window>コントロール。</span><span class="sxs-lookup"><span data-stu-id="4307c-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="4307c-124"><xref:System.Windows.Controls.ControlTemplate>次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="4307c-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4307c-125">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4307c-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4307c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="4307c-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4307c-127">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="4307c-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4307c-128">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4307c-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4307c-129">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="4307c-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="4307c-130">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4307c-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
