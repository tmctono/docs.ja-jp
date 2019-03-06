---
title: '方法: 線を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a194fad5471cafcb567aa00522a597a4186ef4af
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374188"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="73fd6-102">方法: 線を描画する</span><span class="sxs-lookup"><span data-stu-id="73fd6-102">How to: Draw a Line</span></span>
<span data-ttu-id="73fd6-103">この例を使用して線を描画する方法を示します、<xref:System.Windows.Shapes.Line>要素。</span><span class="sxs-lookup"><span data-stu-id="73fd6-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="73fd6-104">線を描画するために作成、<xref:System.Windows.Shapes.Line>要素。</span><span class="sxs-lookup"><span data-stu-id="73fd6-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="73fd6-105">使用して、その<xref:System.Windows.Shapes.Line.X1%2A>と<xref:System.Windows.Shapes.Line.Y1%2A>; の開始ポイントを設定して使用するプロパティの<xref:System.Windows.Shapes.Line.X2%2A>と<xref:System.Windows.Shapes.Line.Y2%2A>エンドポイントを設定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="73fd6-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="73fd6-106">最後に、設定、<xref:System.Windows.Shapes.Shape.Stroke%2A>と<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>線なしの行が表示されないためです。</span><span class="sxs-lookup"><span data-stu-id="73fd6-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="73fd6-107">設定、<xref:System.Windows.Shapes.Shape.Fill%2A>行要素も何も起こりません、行は内部があるないためです。</span><span class="sxs-lookup"><span data-stu-id="73fd6-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="73fd6-108">次の例は、内で 3 つの行を描画、<xref:System.Windows.Controls.Canvas>要素。</span><span class="sxs-lookup"><span data-stu-id="73fd6-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73fd6-109">例</span><span class="sxs-lookup"><span data-stu-id="73fd6-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="73fd6-110">この例より大きなサンプルの一部です。サンプル全体については、次を参照してください。 [Shape 要素のサンプル](https://go.microsoft.com/fwlink/?LinkID=160037)します。</span><span class="sxs-lookup"><span data-stu-id="73fd6-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73fd6-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="73fd6-111">See also</span></span>
- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="73fd6-112">Shape 要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="73fd6-112">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
