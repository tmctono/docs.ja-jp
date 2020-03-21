---
title: '方法 : 背景として使用するイメージの縦横比を保持する'
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186030"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a><span data-ttu-id="ebcd0-102">方法 : 背景として使用するイメージの縦横比を保持する</span><span class="sxs-lookup"><span data-stu-id="ebcd0-102">How to: Preserve the Aspect Ratio of an Image Used as a Background</span></span>
<span data-ttu-id="ebcd0-103">この例では、イメージのア<xref:System.Windows.Media.TileBrush.Stretch%2A>スペクト比<xref:System.Windows.Media.ImageBrush>を保持するために、 のプロパティを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of an <xref:System.Windows.Media.ImageBrush> in order to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="ebcd0-104">既定では、を使用<xref:System.Windows.Media.ImageBrush>して領域をペイントすると、その内容が出力領域全体に広がって表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-104">By default, when you use an <xref:System.Windows.Media.ImageBrush> to paint an area, its content stretches to completely fill the output area.</span></span> <span data-ttu-id="ebcd0-105">出力領域とイメージの縦横比が異なる場合は、この引き伸ばしによってイメージがゆがめられます。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-105">When the output area and the image have different aspect ratios, the image is distorted by this stretching.</span></span>  
  
 <span data-ttu-id="ebcd0-106">イメージの<xref:System.Windows.Media.ImageBrush>縦横比を保持するには、プロパティを<xref:System.Windows.Media.TileBrush.Stretch%2A><xref:System.Windows.Media.Stretch.Uniform>or に<xref:System.Windows.Media.Stretch.UniformToFill>設定します。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-106">To make an <xref:System.Windows.Media.ImageBrush> preserve the aspect ratio of its image, set the <xref:System.Windows.Media.TileBrush.Stretch%2A> property to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebcd0-107">例</span><span class="sxs-lookup"><span data-stu-id="ebcd0-107">Example</span></span>  
 <span data-ttu-id="ebcd0-108">2 つのオブジェクトを<xref:System.Windows.Media.ImageBrush>使用して 2 つの四角形を描画する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-108">The following example uses two <xref:System.Windows.Media.ImageBrush> objects to paint two rectangles.</span></span> <span data-ttu-id="ebcd0-109">これらの四角形は 300 × 150 ピクセルで、どちらも 300 × 300 ピクセルのイメージを保持しています。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-109">Each rectangle is 300 by 150 pixels and each contains a 300 by 300 pixel image.</span></span> <span data-ttu-id="ebcd0-110">最初<xref:System.Windows.Media.TileBrush.Stretch%2A>のブラシのプロパティは に<xref:System.Windows.Media.Stretch.Uniform>設定され、2<xref:System.Windows.Media.TileBrush.Stretch%2A>番目のブラシのプロパティは<xref:System.Windows.Media.Stretch.UniformToFill>に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-110">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the first brush is set to <xref:System.Windows.Media.Stretch.Uniform>, and the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the second brush is set to <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 <span data-ttu-id="ebcd0-111">次の図は、設定が<xref:System.Windows.Media.TileBrush.Stretch%2A><xref:System.Windows.Media.Stretch.Uniform>[ ] の最初のブラシの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-111">The following illustration shows the output of the first brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.Uniform>.</span></span>  
  
 <span data-ttu-id="ebcd0-112">![Uniform 拡大を使用した ImageBrush](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span><span class="sxs-lookup"><span data-stu-id="ebcd0-112">![ImageBrush with Uniform stretching](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span></span>  
  
 <span data-ttu-id="ebcd0-113">次の図は、2 番目のブラシの出力を<xref:System.Windows.Media.TileBrush.Stretch%2A>示しています。 <xref:System.Windows.Media.Stretch.UniformToFill></span><span class="sxs-lookup"><span data-stu-id="ebcd0-113">The next illustration shows the output of the second brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 <span data-ttu-id="ebcd0-114">![UniformToFill 拡大を使用した ImageBrush](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span><span class="sxs-lookup"><span data-stu-id="ebcd0-114">![ImageBrush with UniformToFill stretching](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span></span>  
  
 <span data-ttu-id="ebcd0-115">プロパティは、<xref:System.Windows.Media.TileBrush.Stretch%2A>他<xref:System.Windows.Media.TileBrush>のオブジェクト 、つまり、および<xref:System.Windows.Media.DrawingBrush><xref:System.Windows.Media.VisualBrush>に対して同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-115">Note that the <xref:System.Windows.Media.TileBrush.Stretch%2A> property behaves identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="ebcd0-116">その他<xref:System.Windows.Media.TileBrush>のオブジェクト<xref:System.Windows.Media.ImageBrush>の詳細については、「[イメージ、描画、およびビジュアルを使用したペイント](painting-with-images-drawings-and-visuals.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-116">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="ebcd0-117">また、<xref:System.Windows.Media.TileBrush.Stretch%2A>このプロパティは、<xref:System.Windows.Media.TileBrush>コンテンツが出力領域に収まるように伸びる方法を指定するように見えますが、実際<xref:System.Windows.Media.TileBrush>にはコンテンツが基本タイルを埋めるように伸びる方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-117">Note also that, although the <xref:System.Windows.Media.TileBrush.Stretch%2A> property appears to specify how the <xref:System.Windows.Media.TileBrush> content stretches to fit its output area, it actually specifies how the <xref:System.Windows.Media.TileBrush> content stretches to fill its base tile.</span></span> <span data-ttu-id="ebcd0-118">詳細については、<xref:System.Windows.Media.TileBrush> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-118">For more information, see <xref:System.Windows.Media.TileBrush>.</span></span>  
  
 <span data-ttu-id="ebcd0-119">このコード例は、クラスに用意されている大きな例の<xref:System.Windows.Media.ImageBrush>一部です。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-119">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="ebcd0-120">完全なサンプルについては、「[イメージブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebcd0-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebcd0-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebcd0-121">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="ebcd0-122">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="ebcd0-122">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
