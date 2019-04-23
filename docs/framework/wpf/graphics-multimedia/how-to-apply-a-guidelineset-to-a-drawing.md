---
title: '方法: 描画に GuidelineSet を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 134236c5beca806b747d45f20764cc82ddd8a4e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217810"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="60cd3-102">方法: 描画に GuidelineSet を適用する</span><span class="sxs-lookup"><span data-stu-id="60cd3-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="60cd3-103">この例では、適用、<xref:System.Windows.Media.GuidelineSet>を<xref:System.Windows.Media.DrawingGroup>。</span><span class="sxs-lookup"><span data-stu-id="60cd3-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="60cd3-104"><xref:System.Windows.Media.DrawingGroup>クラスは、唯一の種類の<xref:System.Windows.Media.Drawing>を持つ、<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="60cd3-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="60cd3-105">適用する、<xref:System.Windows.Media.GuidelineSet>の別の型に<xref:System.Windows.Media.Drawing>、追加、<xref:System.Windows.Media.DrawingGroup>し、適用、<xref:System.Windows.Media.GuidelineSet>を<xref:System.Windows.Media.DrawingGroup>。</span><span class="sxs-lookup"><span data-stu-id="60cd3-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60cd3-106">例</span><span class="sxs-lookup"><span data-stu-id="60cd3-106">Example</span></span>  
 <span data-ttu-id="60cd3-107">次の例では、2 つ作成されます<xref:System.Windows.Media.DrawingGroup>はほとんど同じです。 唯一の違いは、オブジェクト: 2 つ目<xref:System.Windows.Media.DrawingGroup>が、<xref:System.Windows.Media.GuidelineSet>と 1 つ目はありません。</span><span class="sxs-lookup"><span data-stu-id="60cd3-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="60cd3-108">この例からの出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="60cd3-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="60cd3-109">2 つの間の差。 レンダリングため<xref:System.Windows.Media.DrawingGroup>オブジェクトは、あまり目立たない、図面の特定の部分を拡大します。</span><span class="sxs-lookup"><span data-stu-id="60cd3-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="60cd3-110">![GuidelineSet が有効/無効な DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="60cd3-110">![A DrawingGroup with and without a GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="60cd3-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="60cd3-111">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [<span data-ttu-id="60cd3-112">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="60cd3-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
