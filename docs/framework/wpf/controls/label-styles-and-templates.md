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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696250"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="0c1c0-102">ラベルのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0c1c0-102">Label Styles and Templates</span></span>
<span data-ttu-id="0c1c0-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.Label>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="0c1c0-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0c1c0-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="0c1c0-106">ラベル部分</span><span class="sxs-lookup"><span data-stu-id="0c1c0-106">Label Parts</span></span>  
 <span data-ttu-id="0c1c0-107"><xref:System.Windows.Controls.Label>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="0c1c0-108">ラベルの状態</span><span class="sxs-lookup"><span data-stu-id="0c1c0-108">Label States</span></span>  
 <span data-ttu-id="0c1c0-109">次の表のビジュアルの状態、<xref:System.Windows.Controls.Label>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="0c1c0-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="0c1c0-110">VisualState Name</span></span>|<span data-ttu-id="0c1c0-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="0c1c0-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0c1c0-112">説明</span><span class="sxs-lookup"><span data-stu-id="0c1c0-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0c1c0-113">有効</span><span class="sxs-lookup"><span data-stu-id="0c1c0-113">Valid</span></span>|<span data-ttu-id="0c1c0-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0c1c0-114">ValidationStates</span></span>|<span data-ttu-id="0c1c0-115">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0c1c0-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0c1c0-116">InvalidFocused</span></span>|<span data-ttu-id="0c1c0-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0c1c0-117">ValidationStates</span></span>|<span data-ttu-id="0c1c0-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0c1c0-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0c1c0-119">InvalidUnfocused</span></span>|<span data-ttu-id="0c1c0-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0c1c0-120">ValidationStates</span></span>|<span data-ttu-id="0c1c0-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="0c1c0-122">ControlTemplate の例をラベルします。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="0c1c0-123">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Label>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="0c1c0-124"><xref:System.Windows.Controls.ControlTemplate>次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0c1c0-125">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c1c0-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c1c0-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c1c0-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0c1c0-127">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0c1c0-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0c1c0-128">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0c1c0-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0c1c0-129">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0c1c0-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="0c1c0-130">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0c1c0-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
