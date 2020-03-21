---
title: '方法 : イメージで領域を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186050"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="a5580-102">方法 : イメージで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="a5580-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="a5580-103">この例では、クラスを使用<xref:System.Windows.Media.ImageBrush>してイメージを持つ領域を描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5580-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="a5580-104">プロパティ<xref:System.Windows.Media.ImageBrush>で指定された単一のイメージを<xref:System.Windows.Media.ImageBrush.ImageSource%2A>表示します。</span><span class="sxs-lookup"><span data-stu-id="a5580-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5580-105">例</span><span class="sxs-lookup"><span data-stu-id="a5580-105">Example</span></span>  
 <span data-ttu-id="a5580-106">次の例では、<xref:System.Windows.Controls.Control.Background%2A>を使用してボタンの<xref:System.Windows.Media.ImageBrush>を描画します。</span><span class="sxs-lookup"><span data-stu-id="a5580-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="a5580-107">既定では、イメージ<xref:System.Windows.Media.ImageBrush>が拡大し、ペイントしている領域全体が完全に塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="a5580-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="a5580-108">前の例のようにイメージを引き伸ばしてボタンを塗りつぶすと、イメージにゆがみが生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="a5580-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="a5580-109">この動作を制御するには、 または<xref:System.Windows.Media.TileBrush.Stretch%2A><xref:System.Windows.Media.Stretch.UniformToFill>の<xref:System.Windows.Media.TileBrush>プロパティ<xref:System.Windows.Media.Stretch.Uniform>を設定して、ブラシがイメージの縦横比を保持します。</span><span class="sxs-lookup"><span data-stu-id="a5580-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="a5580-110">の プロパティと<xref:System.Windows.Media.TileBrush.Viewport%2A><xref:System.Windows.Media.TileBrush.TileMode%2A>プロパティを<xref:System.Windows.Media.ImageBrush>設定すると、繰り返しパターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a5580-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="a5580-111">次の例は、イメージから作成したパターンを使用してボタンを塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="a5580-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="a5580-112">クラスの<xref:System.Windows.Media.ImageBrush>詳細については、「[イメージ、描画、およびビジュアルを使用したペイント](painting-with-images-drawings-and-visuals.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5580-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="a5580-113">このコード例は、クラスに用意されている大きな例の<xref:System.Windows.Media.ImageBrush>一部です。</span><span class="sxs-lookup"><span data-stu-id="a5580-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="a5580-114">完全なサンプルについては、「[イメージブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5580-114">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5580-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5580-115">See also</span></span>

- [<span data-ttu-id="a5580-116">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="a5580-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
