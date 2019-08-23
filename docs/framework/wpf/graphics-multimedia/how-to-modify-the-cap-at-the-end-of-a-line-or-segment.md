---
title: '方法: 直線または線分の終点のキャップを変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 53487417636dae8d855fe70b7b9255351a2dfb1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916130"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="17d1b-102">方法: 直線または線分の終点のキャップを変更する</span><span class="sxs-lookup"><span data-stu-id="17d1b-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="17d1b-103">この例は、開い<xref:System.Windows.Shapes.Shape>ている要素の先頭または末尾にある図形を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="17d1b-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="17d1b-104">開い<xref:System.Windows.Shapes.Shape>ているの先頭でキャップを変更するには、 <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>そのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="17d1b-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="17d1b-105">開い<xref:System.Windows.Shapes.Shape>ているの端にあるキャップを変更するには<xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> 、そのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="17d1b-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="17d1b-106">使用可能なラインキャップを表示するに<xref:System.Windows.Media.PenLineCap>は、列挙体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17d1b-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17d1b-107">このプロパティは<xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Polyline>、、、または開い<xref:System.Windows.Shapes.Path>ている要素など、開いている図形にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="17d1b-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="17d1b-108">次の例では<xref:System.Windows.Shapes.Polyline> 、4つの要素を描画し、それぞれの端に異なる形状のセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="17d1b-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17d1b-109">例</span><span class="sxs-lookup"><span data-stu-id="17d1b-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="17d1b-110">この例は、大規模なサンプルに含まれています。完全なサンプルについては、「 [Shape Elements sample](https://go.microsoft.com/fwlink/?LinkID=160037)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17d1b-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d1b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="17d1b-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
