---
title: '方法 : ToolTip を配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 0f52703e4fe127daa40f220280f084b2026580cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186950"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="8d418-102">方法 : ToolTip を配置する</span><span class="sxs-lookup"><span data-stu-id="8d418-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="8d418-103">この例では、画面上のツールヒントの位置を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8d418-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d418-104">例</span><span class="sxs-lookup"><span data-stu-id="8d418-104">Example</span></span>  
 <span data-ttu-id="8d418-105">ツールヒントは、 クラスと<xref:System.Windows.Controls.ToolTip><xref:System.Windows.Controls.ToolTipService>クラスの両方で定義された 5 つのプロパティのセットを使用して配置できます。</span><span class="sxs-lookup"><span data-stu-id="8d418-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="8d418-106">次の表は、これら 2 つの 5 つのプロパティ セットを示し、クラスに従って参照ドキュメントへのリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="8d418-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="8d418-107">クラスに応じた対応するツールヒントプロパティ</span><span class="sxs-lookup"><span data-stu-id="8d418-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="8d418-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>クラスプロパティ</span><span class="sxs-lookup"><span data-stu-id="8d418-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="8d418-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>クラスプロパティ</span><span class="sxs-lookup"><span data-stu-id="8d418-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="8d418-110">オブジェクトを使用してツールヒントの内容を<xref:System.Windows.Controls.ToolTip>定義する場合は、どちらのクラスのプロパティを使用しても問題ありません。ただし、プロパティ<xref:System.Windows.Controls.ToolTipService>が優先されます。</span><span class="sxs-lookup"><span data-stu-id="8d418-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="8d418-111">オブジェクトとして<xref:System.Windows.Controls.ToolTipService><xref:System.Windows.Controls.ToolTip>定義されていないツールチップのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d418-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="8d418-112">次の図は、これらのプロパティを使用してツールヒントを配置する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d418-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="8d418-113">ただし、これらの[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]図の例では、クラスによって定義されるプロパティを設定する方法を<xref:System.Windows.Controls.ToolTip>示していますが、<xref:System.Windows.Controls.ToolTipService>クラスの対応するプロパティは同じレイアウト規則に従います。</span><span class="sxs-lookup"><span data-stu-id="8d418-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="8d418-114">[配置] プロパティで使用できる値の詳細については、「[ポップアップ配置の動作](popup-placement-behavior.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d418-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  

 <span data-ttu-id="8d418-115">次の図は、Placement プロパティを使用したツールヒントの配置を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d418-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![配置プロパティを使用してツールヒントの配置を示す図。](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 <span data-ttu-id="8d418-117">次の図は、配置および配置矩形プロパティを使用して、ツールヒントの配置を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d418-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>

 ![配置四角形プロパティを使用してツールヒントの配置を示す図。](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 <span data-ttu-id="8d418-119">次の図は、[配置]、[配置]、および [オフセット] プロパティを使用したツールヒントの配置を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d418-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>
  
 ![Offset プロパティを使用したツールヒントの配置を示す図。](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="8d418-121"><xref:System.Windows.Controls.ToolTip>プロパティを使用して、コンテンツがオブジェクトであるツールヒントの位置を指定する方法を次の<xref:System.Windows.Controls.ToolTip>例に示します。</span><span class="sxs-lookup"><span data-stu-id="8d418-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="8d418-122">プロパティを使用<xref:System.Windows.Controls.ToolTipService>して、コンテンツがオブジェクトではないツールヒントの位置を指定する方法を次の例<xref:System.Windows.Controls.ToolTip>に示します。</span><span class="sxs-lookup"><span data-stu-id="8d418-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="8d418-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d418-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="8d418-124">ハウツートピック</span><span class="sxs-lookup"><span data-stu-id="8d418-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="8d418-125">ToolTip の概要</span><span class="sxs-lookup"><span data-stu-id="8d418-125">ToolTip Overview</span></span>](tooltip-overview.md)
