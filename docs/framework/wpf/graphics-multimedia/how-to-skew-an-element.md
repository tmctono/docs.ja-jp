---
title: '方法 : 要素を傾斜させる'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112025"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="ac653-102">方法 : 要素を傾斜させる</span><span class="sxs-lookup"><span data-stu-id="ac653-102">How to: Skew an Element</span></span>
<span data-ttu-id="ac653-103">この例では、 を<xref:System.Windows.Media.SkewTransform>使用して要素を傾斜させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ac653-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="ac653-104">傾斜 (スキューと呼ばれることもあります) は、一様でない方法で座標空間を拡大する変換です。</span><span class="sxs-lookup"><span data-stu-id="ac653-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="ac653-105">一般的な a<xref:System.Windows.Media.SkewTransform>の用途の 1 つは、2D オブジェクトの 3D 深度をシミュレートする場合です。</span><span class="sxs-lookup"><span data-stu-id="ac653-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating 3D depth in 2D objects.</span></span>  
  
 <span data-ttu-id="ac653-106">プロパティと<xref:System.Windows.Media.SkewTransform.CenterX%2A><xref:System.Windows.Media.SkewTransform.CenterY%2A>プロパティを使用して、 の中心<xref:System.Windows.Media.SkewTransform>点を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac653-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="ac653-107">プロパティ<xref:System.Windows.Media.SkewTransform.AngleX%2A>と<xref:System.Windows.Media.SkewTransform.AngleY%2A>プロパティを使用して、X 軸と Y 軸のスキュー角度を指定し、これらの軸に沿って現在の座標系を傾斜させます。</span><span class="sxs-lookup"><span data-stu-id="ac653-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="ac653-108">傾斜変換の効果を予測するには、元の座標系<xref:System.Windows.Media.SkewTransform.AngleX%2A>に対して x 軸の値を傾斜させるとします。</span><span class="sxs-lookup"><span data-stu-id="ac653-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="ac653-109">したがって、30<xref:System.Windows.Media.SkewTransform.AngleX%2A>の場合、y 軸は原点を 30 度回転し、その原点から 30 度ずつ x- の値を歪めます。</span><span class="sxs-lookup"><span data-stu-id="ac653-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="ac653-110">同様に、30 の値は<xref:System.Windows.Media.SkewTransform.AngleY%2A>、原点から 30 度ずつ図形の y- 値を歪めます。</span><span class="sxs-lookup"><span data-stu-id="ac653-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="ac653-111">これは、座標系の x または y での 30 度の平行移動 (移動) と同じ効果はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac653-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="ac653-112">次の使用例は、45 度の水平傾斜を<xref:System.Windows.Shapes.Rectangle>中心点 (0,0) から a に適用します。</span><span class="sxs-lookup"><span data-stu-id="ac653-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac653-113">例</span><span class="sxs-lookup"><span data-stu-id="ac653-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="ac653-114">次の例では、45 度の水平傾斜を<xref:System.Windows.Shapes.Rectangle>中心点 (25,25) から a に適用します。</span><span class="sxs-lookup"><span data-stu-id="ac653-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="ac653-115">次の使用例は、45 度の垂直傾斜を<xref:System.Windows.Shapes.Rectangle>中心点 (25,25) から a に適用します。</span><span class="sxs-lookup"><span data-stu-id="ac653-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="ac653-116">次の図は、この例で使用されている各種の傾斜を示しています。</span><span class="sxs-lookup"><span data-stu-id="ac653-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="ac653-117">![SkewTransform の例](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="ac653-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="ac653-118">説明した 3 つの SkewTransform の例</span><span class="sxs-lookup"><span data-stu-id="ac653-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="ac653-119">完全なサンプルについては[、2D 変換のサンプルを](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac653-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac653-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac653-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="ac653-121">変換の概要</span><span class="sxs-lookup"><span data-stu-id="ac653-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="ac653-122">ハウツートピック</span><span class="sxs-lookup"><span data-stu-id="ac653-122">How-to Topics</span></span>](transformations-how-to-topics.md)
