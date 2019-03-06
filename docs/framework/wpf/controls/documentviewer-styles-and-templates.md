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
ms.openlocfilehash: b120359e63c2916e82b79b2f7b7f1aa5426be99c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369644"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="16c17-102">DocumentViewer のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="16c17-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="16c17-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.DocumentViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="16c17-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="16c17-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="16c17-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="16c17-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16c17-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="16c17-106">DocumentViewer のパーツ</span><span class="sxs-lookup"><span data-stu-id="16c17-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="16c17-107">次の表に、名前付きパーツ、<xref:System.Windows.Controls.DocumentViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="16c17-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="16c17-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="16c17-108">Part</span></span>|<span data-ttu-id="16c17-109">型</span><span class="sxs-lookup"><span data-stu-id="16c17-109">Type</span></span>|<span data-ttu-id="16c17-110">説明</span><span class="sxs-lookup"><span data-stu-id="16c17-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="16c17-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="16c17-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="16c17-112">コンテンツと領域をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="16c17-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="16c17-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="16c17-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="16c17-114">既定では下部にある検索ボックス。</span><span class="sxs-lookup"><span data-stu-id="16c17-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="16c17-115">DocumentViewer の状態</span><span class="sxs-lookup"><span data-stu-id="16c17-115">DocumentViewer States</span></span>  
 <span data-ttu-id="16c17-116">次の表のビジュアルの状態、<xref:System.Windows.Controls.DocumentViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="16c17-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="16c17-117">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="16c17-117">VisualState Name</span></span>|<span data-ttu-id="16c17-118">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="16c17-118">VisualStateGroup Name</span></span>|<span data-ttu-id="16c17-119">説明</span><span class="sxs-lookup"><span data-stu-id="16c17-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="16c17-120">有効</span><span class="sxs-lookup"><span data-stu-id="16c17-120">Valid</span></span>|<span data-ttu-id="16c17-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="16c17-121">ValidationStates</span></span>|<span data-ttu-id="16c17-122">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="16c17-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="16c17-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="16c17-123">InvalidFocused</span></span>|<span data-ttu-id="16c17-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="16c17-124">ValidationStates</span></span>|<span data-ttu-id="16c17-125"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="16c17-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="16c17-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="16c17-126">InvalidUnfocused</span></span>|<span data-ttu-id="16c17-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="16c17-127">ValidationStates</span></span>|<span data-ttu-id="16c17-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="16c17-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="16c17-129">DocumentViewer ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="16c17-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="16c17-130">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.DocumentViewer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="16c17-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="16c17-131">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="16c17-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="16c17-132">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16c17-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c17-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="16c17-133">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="16c17-134">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="16c17-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="16c17-135">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="16c17-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="16c17-136">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="16c17-136">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="16c17-137">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="16c17-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
