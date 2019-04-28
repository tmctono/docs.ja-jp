---
title: '方法: ブラシを変換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: a83f3b1c046e94faa8816e8c310f438b4711048a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769380"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="90647-102">方法: ブラシを変換する</span><span class="sxs-lookup"><span data-stu-id="90647-102">How to: Transform a Brush</span></span>
<span data-ttu-id="90647-103">この例は、変換する方法を示しています。<xref:System.Windows.Media.Brush>その 2 つの変換プロパティを使用して、オブジェクト:<xref:System.Windows.Media.Brush.RelativeTransform%2A>と<xref:System.Windows.Media.Brush.Transform%2A>します。</span><span class="sxs-lookup"><span data-stu-id="90647-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="90647-104">次の例を使用して、<xref:System.Windows.Media.RotateTransform>の内容を回転する、 <xref:System.Windows.Media.ImageBrush> 45 度。</span><span class="sxs-lookup"><span data-stu-id="90647-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="90647-105">次の図は、<xref:System.Windows.Media.ImageBrush>せず、<xref:System.Windows.Media.RotateTransform>で、<xref:System.Windows.Media.RotateTransform>に適用される、<xref:System.Windows.Media.Brush.RelativeTransform%2A>プロパティを使用して、<xref:System.Windows.Media.RotateTransform>に適用、<xref:System.Windows.Media.Brush.Transform%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="90647-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="90647-106">![ブラシの RelativeTransform と Transform の設定](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="90647-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="90647-107">例</span><span class="sxs-lookup"><span data-stu-id="90647-107">Example</span></span>  
 <span data-ttu-id="90647-108">最初の例では、適用、<xref:System.Windows.Media.RotateTransform>を<xref:System.Windows.Media.Brush.RelativeTransform%2A>のプロパティ、<xref:System.Windows.Media.ImageBrush>します。</span><span class="sxs-lookup"><span data-stu-id="90647-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="90647-109"><xref:System.Windows.Media.RotateTransform.CenterX%2A>と<xref:System.Windows.Media.RotateTransform.CenterY%2A>のプロパティを<xref:System.Windows.Media.RotateTransform>オブジェクトの両方が、このコンテンツの中心点の相対座標である 0.5 に設定します。</span><span class="sxs-lookup"><span data-stu-id="90647-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="90647-110">結果として、<xref:System.Windows.Media.ImageBrush>コンテンツがその中心を回転します。</span><span class="sxs-lookup"><span data-stu-id="90647-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="90647-111">2 番目の例でも適用されます、<xref:System.Windows.Media.RotateTransform>を<xref:System.Windows.Media.ImageBrush>。 ただし、この例では、<xref:System.Windows.Media.Brush.Transform%2A>プロパティの代わりに、<xref:System.Windows.Media.Brush.RelativeTransform%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="90647-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="90647-112">ブラシをその中心の周りを回転するには、設定、<xref:System.Windows.Media.RotateTransform.CenterX%2A>と<xref:System.Windows.Media.RotateTransform.CenterY%2A>のプロパティ、<xref:System.Windows.Media.RotateTransform>絶対座標にオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="90647-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="90647-113">このブラシは、175 x 90 ピクセルの四角形を描画するため、四角形の中心点は (87.5, 45) になります。</span><span class="sxs-lookup"><span data-stu-id="90647-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="90647-114">方法の説明については<xref:System.Windows.Media.Brush.RelativeTransform%2A>と<xref:System.Windows.Media.Brush.Transform%2A>プロパティの動作を参照してください、[ブラシの変換の概要](brush-transformation-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="90647-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="90647-115">完全なサンプルについては、「[ブラシのサンプル](https://go.microsoft.com/fwlink/?LinkID=159973)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90647-115">For the complete sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="90647-116">ブラシの詳細については、「[純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90647-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90647-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="90647-117">See also</span></span>

- [<span data-ttu-id="90647-118">ブラシの変換の概要</span><span class="sxs-lookup"><span data-stu-id="90647-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="90647-119">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="90647-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="90647-120">変換の概要</span><span class="sxs-lookup"><span data-stu-id="90647-120">Transforms Overview</span></span>](transforms-overview.md)
