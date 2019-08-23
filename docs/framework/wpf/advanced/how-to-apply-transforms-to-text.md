---
title: '方法: テキストに変換を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: b749d21c1b5940d216e244393eeb3c133dc153b6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956481"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="ec3d1-102">方法: テキストに変換を適用する</span><span class="sxs-lookup"><span data-stu-id="ec3d1-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="ec3d1-103">変換を利用すると、アプリケーションのテキストの表示を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="ec3d1-104">次の例では、さまざまな種類のレンダリング変換を使用して、 <xref:System.Windows.Controls.TextBlock>コントロールのテキストの表示に影響を与えています。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec3d1-105">例</span><span class="sxs-lookup"><span data-stu-id="ec3d1-105">Example</span></span>  
 <span data-ttu-id="ec3d1-106">次は、x と y の 2 次元平面に指定した点を中心にテキストを回転させた例です。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 ![RotateTransform を使用して回転したテキスト](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 <span data-ttu-id="ec3d1-108">次のコード例では<xref:System.Windows.Media.RotateTransform> 、を使用してテキストを回転させます。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-108">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="ec3d1-109">値<xref:System.Windows.Media.RotateTransform.Angle%2A> 90 を指定すると、要素は時計回りに90度回転します。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-109">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="ec3d1-110">テキストの 2 行目を x 軸に沿って 150% 拡大し、3 行目を y 軸に沿って 150% 拡大した例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-110">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 ![ScaleTransform を使用してスケールされたテキスト](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg) 
  
 <span data-ttu-id="ec3d1-112">次のコード例では<xref:System.Windows.Media.ScaleTransform> 、を使用して、元のサイズからテキストをスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-112">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
> <span data-ttu-id="ec3d1-113">テキストの拡大縮小は、テキストのフォント サイズを増やすことと同じではありません。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-113">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="ec3d1-114">フォント サイズは、サイズを変えても最良の解像度が得られるように、互いに依存せずに計算されます。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-114">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="ec3d1-115">一方で、テキストの拡大縮小では、元のサイズのテキストの比率が維持されます。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-115">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="ec3d1-116">x 軸に沿って傾斜させたテキストの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-116">The following example shows text skewed along the x-axis.</span></span>  
  
 ![SkewTransform を使用して傾斜させたテキスト](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)
   
 <span data-ttu-id="ec3d1-118">次のコード例では<xref:System.Windows.Media.SkewTransform> 、を使用してテキストを傾斜します。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-118">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="ec3d1-119">傾斜はスキューと呼ばれることもありますが、一様でない方法で座標空間を拡大する変換です。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-119">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="ec3d1-120">この例では、2 つのテキスト文字列が x 座標に沿って -30° と 30° とに傾斜します。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-120">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="ec3d1-121">次の例では、x 軸と y 軸に沿ってテキストが変換または移動されます。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-121">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 ![TranslateTransform を使用するテキスト オフセット](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 <span data-ttu-id="ec3d1-123">次のコード例では<xref:System.Windows.Media.TranslateTransform> 、を使用してテキストをオフセットします。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-123">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="ec3d1-124">この例では、メインのテキストの下にわずかに中心をずらしたコピーが付き、影のような効果を作っています。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-124">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
> <span data-ttu-id="ec3d1-125">に<xref:System.Windows.Media.Effects.DropShadowBitmapEffect>は、シャドウ効果を提供するための豊富な機能セットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-125">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="ec3d1-126">詳細については、「[影付きテキストを作成](how-to-create-text-with-a-shadow.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec3d1-126">For more information, see [Create Text with a Shadow](how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec3d1-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec3d1-127">See also</span></span>

- [<span data-ttu-id="ec3d1-128">アニメーションをテキストに適用する</span><span class="sxs-lookup"><span data-stu-id="ec3d1-128">Apply Animations to Text</span></span>](how-to-apply-animations-to-text.md)
