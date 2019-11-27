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
ms.openlocfilehash: 35fcd9c15bf44d15a08c16d58847698c5ec6e574
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283503"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="8937a-102">ラベルのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="8937a-102">Label Styles and Templates</span></span>
<span data-ttu-id="8937a-103">このトピックでは、<xref:System.Windows.Controls.Label> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8937a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="8937a-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="8937a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8937a-105">詳細については、「[コントロールのテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8937a-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="8937a-106">ラベルパーツ</span><span class="sxs-lookup"><span data-stu-id="8937a-106">Label Parts</span></span>  
 <span data-ttu-id="8937a-107"><xref:System.Windows.Controls.Label> コントロールには、名前付きの部分がありません。</span><span class="sxs-lookup"><span data-stu-id="8937a-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="8937a-108">ラベルの状態</span><span class="sxs-lookup"><span data-stu-id="8937a-108">Label States</span></span>  
 <span data-ttu-id="8937a-109">次の表は、<xref:System.Windows.Controls.Label> コントロールの表示状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="8937a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="8937a-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="8937a-110">VisualState Name</span></span>|<span data-ttu-id="8937a-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="8937a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="8937a-112">説明</span><span class="sxs-lookup"><span data-stu-id="8937a-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8937a-113">Valid</span><span class="sxs-lookup"><span data-stu-id="8937a-113">Valid</span></span>|<span data-ttu-id="8937a-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8937a-114">ValidationStates</span></span>|<span data-ttu-id="8937a-115">コントロールは <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false`ます。</span><span class="sxs-lookup"><span data-stu-id="8937a-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8937a-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8937a-116">InvalidFocused</span></span>|<span data-ttu-id="8937a-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8937a-117">ValidationStates</span></span>|<span data-ttu-id="8937a-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="8937a-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8937a-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8937a-119">InvalidUnfocused</span></span>|<span data-ttu-id="8937a-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8937a-120">ValidationStates</span></span>|<span data-ttu-id="8937a-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="8937a-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="8937a-122">ラベル ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="8937a-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="8937a-123">次の例は、<xref:System.Windows.Controls.Label> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8937a-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="8937a-124"><xref:System.Windows.Controls.ControlTemplate> では、次のリソースの1つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="8937a-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8937a-125">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8937a-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8937a-126">参照</span><span class="sxs-lookup"><span data-stu-id="8937a-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8937a-127">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="8937a-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8937a-128">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8937a-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8937a-129">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="8937a-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="8937a-130">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="8937a-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
