---
title: ラベルのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: d2bb348fc9c0348fd8093452e022df7ab4e0b3f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137086"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="b0a6a-102">ラベルのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b0a6a-102">Label Styles and Templates</span></span>
<span data-ttu-id="b0a6a-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.Label>コントロール。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="b0a6a-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b0a6a-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="b0a6a-106">ラベル部分</span><span class="sxs-lookup"><span data-stu-id="b0a6a-106">Label Parts</span></span>  
 <span data-ttu-id="b0a6a-107"><xref:System.Windows.Controls.Label>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="b0a6a-108">ラベルの状態</span><span class="sxs-lookup"><span data-stu-id="b0a6a-108">Label States</span></span>  
 <span data-ttu-id="b0a6a-109">次の表のビジュアルの状態、<xref:System.Windows.Controls.Label>コントロール。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="b0a6a-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="b0a6a-110">VisualState Name</span></span>|<span data-ttu-id="b0a6a-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="b0a6a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="b0a6a-112">説明</span><span class="sxs-lookup"><span data-stu-id="b0a6a-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b0a6a-113">有効</span><span class="sxs-lookup"><span data-stu-id="b0a6a-113">Valid</span></span>|<span data-ttu-id="b0a6a-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b0a6a-114">ValidationStates</span></span>|<span data-ttu-id="b0a6a-115">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b0a6a-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b0a6a-116">InvalidFocused</span></span>|<span data-ttu-id="b0a6a-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b0a6a-117">ValidationStates</span></span>|<span data-ttu-id="b0a6a-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b0a6a-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b0a6a-119">InvalidUnfocused</span></span>|<span data-ttu-id="b0a6a-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b0a6a-120">ValidationStates</span></span>|<span data-ttu-id="b0a6a-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="b0a6a-122">ControlTemplate の例をラベルします。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="b0a6a-123">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Label>コントロール。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="b0a6a-124"><xref:System.Windows.Controls.ControlTemplate>次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b0a6a-125">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0a6a-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a6a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0a6a-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b0a6a-127">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b0a6a-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b0a6a-128">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b0a6a-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b0a6a-129">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b0a6a-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="b0a6a-130">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b0a6a-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
