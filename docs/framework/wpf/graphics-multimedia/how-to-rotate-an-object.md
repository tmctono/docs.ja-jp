---
title: '方法 : オブジェクトを回転させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112064"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="cc98c-102">方法 : オブジェクトを回転させる</span><span class="sxs-lookup"><span data-stu-id="cc98c-102">How to: Rotate an Object</span></span>
<span data-ttu-id="cc98c-103">次の例では、オブジェクトを回転させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cc98c-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="cc98c-104">この例では、まず<xref:System.Windows.Media.RotateTransform>a を<xref:System.Windows.Media.RotateTransform.Angle%2A>作成し、次に度を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc98c-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="cc98c-105">次の使用例は、オブジェクト<xref:System.Windows.Shapes.Polyline>を左上隅を中心に 45 度回転します。</span><span class="sxs-lookup"><span data-stu-id="cc98c-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc98c-106">例</span><span class="sxs-lookup"><span data-stu-id="cc98c-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="cc98c-107">の<xref:System.Windows.Media.RotateTransform.CenterX%2A><xref:System.Windows.Media.RotateTransform.CenterY%2A>プロパティと<xref:System.Windows.Media.RotateTransform>プロパティは、オブジェクトを回転するポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc98c-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="cc98c-108">この中心点は、変換する要素の座標空間で表します。</span><span class="sxs-lookup"><span data-stu-id="cc98c-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="cc98c-109">既定では、回転は (0,0) に適用されます。これは変換対象のオブジェクトの左上隅です。</span><span class="sxs-lookup"><span data-stu-id="cc98c-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="cc98c-110">次の例では、オブジェクト<xref:System.Windows.Shapes.Polyline>を点(25,50)を中心に時計回りに 45 度回転します。</span><span class="sxs-lookup"><span data-stu-id="cc98c-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="cc98c-111">次の図は、2 つのオブジェクトに<xref:System.Windows.Media.Transform>a を適用した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="cc98c-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="cc98c-112">![中心点が異なる 45 度の回転](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="cc98c-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="cc98c-113">異なる中心点を軸に 45 度回転させた 2 つのオブジェクト</span><span class="sxs-lookup"><span data-stu-id="cc98c-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="cc98c-114">前<xref:System.Windows.Shapes.Polyline>の例のは<xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="cc98c-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="cc98c-115">プロパティ<xref:System.Windows.Media.Transform><xref:System.Windows.UIElement.RenderTransform%2A>に<xref:System.Windows.UIElement>を適用する場合、プロパティを<xref:System.Windows.UIElement.RenderTransformOrigin%2A>使用して、要素に適用するすべての<xref:System.Windows.Media.Transform>要素の原点を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cc98c-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="cc98c-116">プロパティは<xref:System.Windows.UIElement.RenderTransformOrigin%2A>相対座標を使用するため、サイズがわからない場合でも、要素の中心に変換を適用できます。</span><span class="sxs-lookup"><span data-stu-id="cc98c-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="cc98c-117">詳細および例については、「[相対値を使用して変換の原点を指定する](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc98c-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="cc98c-118">完全なサンプルについては[、2D 変換のサンプルを](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc98c-118">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc98c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc98c-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="cc98c-120">変換の概要</span><span class="sxs-lookup"><span data-stu-id="cc98c-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="cc98c-121">ハウツートピック</span><span class="sxs-lookup"><span data-stu-id="cc98c-121">How-to Topics</span></span>](transformations-how-to-topics.md)
