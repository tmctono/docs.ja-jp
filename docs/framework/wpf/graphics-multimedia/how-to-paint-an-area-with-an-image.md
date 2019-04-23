---
title: '方法: イメージで領域を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 2b88982e7a8d196c31869dc74aac636d78f68386
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207813"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="5c669-102">方法: イメージで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="5c669-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="5c669-103">この例は、使用する方法を示します、<xref:System.Windows.Media.ImageBrush>イメージで領域を塗りつぶすクラス。</span><span class="sxs-lookup"><span data-stu-id="5c669-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="5c669-104"><xref:System.Windows.Media.ImageBrush>で指定された 1 つのイメージを表示します。 その<xref:System.Windows.Media.ImageBrush.ImageSource%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5c669-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c669-105">例</span><span class="sxs-lookup"><span data-stu-id="5c669-105">Example</span></span>  
 <span data-ttu-id="5c669-106">次の例の描画、 <xref:System.Windows.Controls.Control.Background%2A> 、ボタンを使用して、<xref:System.Windows.Media.ImageBrush>します。</span><span class="sxs-lookup"><span data-stu-id="5c669-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="5c669-107">既定で、<xref:System.Windows.Media.ImageBrush>イメージ、描画している領域を完全に埋めるを引き伸ばします。</span><span class="sxs-lookup"><span data-stu-id="5c669-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="5c669-108">前の例のようにイメージを引き伸ばしてボタンを塗りつぶすと、イメージにゆがみが生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="5c669-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="5c669-109">設定してこの動作を制御することができます、<xref:System.Windows.Media.TileBrush.Stretch%2A>プロパティの<xref:System.Windows.Media.TileBrush>に<xref:System.Windows.Media.Stretch.Uniform>または<xref:System.Windows.Media.Stretch.UniformToFill>、それが原因で、イメージの縦横比を維持するブラシ。</span><span class="sxs-lookup"><span data-stu-id="5c669-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="5c669-110">設定した場合、<xref:System.Windows.Media.TileBrush.Viewport%2A>と<xref:System.Windows.Media.TileBrush.TileMode%2A>のプロパティ、 <xref:System.Windows.Media.ImageBrush>、繰り返しパターンを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5c669-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="5c669-111">次の例は、イメージから作成したパターンを使用してボタンを塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="5c669-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="5c669-112">詳細については、<xref:System.Windows.Media.ImageBrush>クラスを参照してください[イメージ、描画、およびビジュアル](painting-with-images-drawings-and-visuals.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c669-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="5c669-113">このコード例はに対して提供されている例の一部、<xref:System.Windows.Media.ImageBrush>クラス。</span><span class="sxs-lookup"><span data-stu-id="5c669-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="5c669-114">サンプル全体については、次を参照してください。 [ImageBrush のサンプル](https://go.microsoft.com/fwlink/?LinkID=160005)します。</span><span class="sxs-lookup"><span data-stu-id="5c669-114">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c669-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c669-115">See also</span></span>

- [<span data-ttu-id="5c669-116">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="5c669-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
