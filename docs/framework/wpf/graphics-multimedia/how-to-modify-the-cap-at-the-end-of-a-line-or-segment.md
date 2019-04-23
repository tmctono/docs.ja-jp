---
title: '方法: 直線または線分の終点のキャップを変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 462e32520393a1c23809cce8eb3c130c13bc882f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977678"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="7bb56-102">方法: 直線または線分の終点のキャップを変更する</span><span class="sxs-lookup"><span data-stu-id="7bb56-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="7bb56-103">この例では、先頭または末尾の開いている図形を変更する方法を示しています<xref:System.Windows.Shapes.Shape>要素。</span><span class="sxs-lookup"><span data-stu-id="7bb56-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="7bb56-104">オープンの先頭に上限を変更する<xref:System.Windows.Shapes.Shape>を使用して、その<xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7bb56-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="7bb56-105">オープンの終点のキャップを変更する<xref:System.Windows.Shapes.Shape>を使用して、その<xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7bb56-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="7bb56-106">使用可能なライン キャップを表示するを参照してください。、<xref:System.Windows.Media.PenLineCap>列挙体。</span><span class="sxs-lookup"><span data-stu-id="7bb56-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bb56-107">このプロパティは、開いている図形をなど、 <xref:System.Windows.Shapes.Line>、 <xref:System.Windows.Shapes.Polyline>、または開いている<xref:System.Windows.Shapes.Path>要素。</span><span class="sxs-lookup"><span data-stu-id="7bb56-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="7bb56-108">次の例では、4 つを描画<xref:System.Windows.Shapes.Polyline>要素の各端にさまざまな図形を使用しています。</span><span class="sxs-lookup"><span data-stu-id="7bb56-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bb56-109">例</span><span class="sxs-lookup"><span data-stu-id="7bb56-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="7bb56-110">この例より大きなサンプルの一部です。サンプル全体については、次を参照してください。 [Shape 要素のサンプル](https://go.microsoft.com/fwlink/?LinkID=160037)します。</span><span class="sxs-lookup"><span data-stu-id="7bb56-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb56-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bb56-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
