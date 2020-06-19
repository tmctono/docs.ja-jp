---
title: DocumentViewer のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: ac1dc4f74a8e8f3ad2e84c6d50239ec827306c28
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283533"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="89a7e-102">DocumentViewer のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="89a7e-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="89a7e-103">このトピックでは、<xref:System.Windows.Controls.DocumentViewer> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="89a7e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="89a7e-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="89a7e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="89a7e-105">詳細については、「[コントロールのためにテンプレートを作成する](../../../desktop-wpf/themes/how-to-create-apply-template.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89a7e-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="89a7e-106">DocumentViewer のパーツ</span><span class="sxs-lookup"><span data-stu-id="89a7e-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="89a7e-107">次の表は、<xref:System.Windows.Controls.DocumentViewer> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="89a7e-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="89a7e-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="89a7e-108">Part</span></span>|<span data-ttu-id="89a7e-109">種類</span><span class="sxs-lookup"><span data-stu-id="89a7e-109">Type</span></span>|<span data-ttu-id="89a7e-110">説明</span><span class="sxs-lookup"><span data-stu-id="89a7e-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="89a7e-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="89a7e-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="89a7e-112">コンテンツとスクロール領域。</span><span class="sxs-lookup"><span data-stu-id="89a7e-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="89a7e-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="89a7e-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="89a7e-114">既定で一番下に配置される検索ボックス。</span><span class="sxs-lookup"><span data-stu-id="89a7e-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="89a7e-115">DocumentViewer の状態</span><span class="sxs-lookup"><span data-stu-id="89a7e-115">DocumentViewer States</span></span>  
 <span data-ttu-id="89a7e-116">次の表は、<xref:System.Windows.Controls.DocumentViewer> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="89a7e-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="89a7e-117">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="89a7e-117">VisualState Name</span></span>|<span data-ttu-id="89a7e-118">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="89a7e-118">VisualStateGroup Name</span></span>|<span data-ttu-id="89a7e-119">説明</span><span class="sxs-lookup"><span data-stu-id="89a7e-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="89a7e-120">有効</span><span class="sxs-lookup"><span data-stu-id="89a7e-120">Valid</span></span>|<span data-ttu-id="89a7e-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="89a7e-121">ValidationStates</span></span>|<span data-ttu-id="89a7e-122">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="89a7e-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="89a7e-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="89a7e-123">InvalidFocused</span></span>|<span data-ttu-id="89a7e-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="89a7e-124">ValidationStates</span></span>|<span data-ttu-id="89a7e-125"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="89a7e-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="89a7e-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="89a7e-126">InvalidUnfocused</span></span>|<span data-ttu-id="89a7e-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="89a7e-127">ValidationStates</span></span>|<span data-ttu-id="89a7e-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="89a7e-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="89a7e-129">DocumentViewer の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="89a7e-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="89a7e-130">次の例は、<xref:System.Windows.Controls.DocumentViewer> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="89a7e-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="89a7e-131">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="89a7e-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="89a7e-132">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89a7e-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a7e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="89a7e-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="89a7e-134">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="89a7e-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="89a7e-135">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="89a7e-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="89a7e-136">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="89a7e-136">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="89a7e-137">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="89a7e-137">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
