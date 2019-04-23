---
title: '方法: オブジェクトを回転させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: d1c4700a5dc8f6ed99043552999d8f014116da8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189668"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="26387-102">方法: オブジェクトを回転させる</span><span class="sxs-lookup"><span data-stu-id="26387-102">How to: Rotate an Object</span></span>
<span data-ttu-id="26387-103">次の例では、オブジェクトを回転させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="26387-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="26387-104">例では、最初に作成、<xref:System.Windows.Media.RotateTransform>を指定してその<xref:System.Windows.Media.RotateTransform.Angle%2A>(度単位)。</span><span class="sxs-lookup"><span data-stu-id="26387-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="26387-105">次の例では、回転、 <xref:System.Windows.Shapes.Polyline> 45 度の左上隅のオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="26387-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26387-106">例</span><span class="sxs-lookup"><span data-stu-id="26387-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="26387-107"><xref:System.Windows.Media.RotateTransform.CenterX%2A>と<xref:System.Windows.Media.RotateTransform.CenterY%2A>のプロパティ、<xref:System.Windows.Media.RotateTransform>ポイント オブジェクトが回転を指定します。</span><span class="sxs-lookup"><span data-stu-id="26387-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="26387-108">この中心点は、変換する要素の座標空間で表します。</span><span class="sxs-lookup"><span data-stu-id="26387-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="26387-109">既定では、回転は (0,0) に適用されます。これは変換対象のオブジェクトの左上隅です。</span><span class="sxs-lookup"><span data-stu-id="26387-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="26387-110">次の例では、回転、 <xref:System.Windows.Shapes.Polyline> (25, 50) にした、時計回りに 45 度のオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="26387-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="26387-111">次の図は、適用した結果、<xref:System.Windows.Media.Transform>に 2 つのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="26387-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="26387-112">![中心点が異なる 45 度の回転](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="26387-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="26387-113">異なる中心点を軸に 45 度回転させた 2 つのオブジェクト</span><span class="sxs-lookup"><span data-stu-id="26387-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="26387-114"><xref:System.Windows.Shapes.Polyline>前の例では、<xref:System.Windows.UIElement>します。</span><span class="sxs-lookup"><span data-stu-id="26387-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="26387-115">適用すると、<xref:System.Windows.Media.Transform>を<xref:System.Windows.UIElement.RenderTransform%2A>のプロパティを<xref:System.Windows.UIElement>、使用することができます、<xref:System.Windows.UIElement.RenderTransformOrigin%2A>の原点を指定するプロパティすべて<xref:System.Windows.Media.Transform>要素に適用します。</span><span class="sxs-lookup"><span data-stu-id="26387-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="26387-116"><xref:System.Windows.UIElement.RenderTransformOrigin%2A>プロパティは、相対座標を使用して、そのサイズがわからない場合でも、要素の中央に変換を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="26387-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="26387-117">詳細については、および例についてを参照してください。[を相対値での変換の原点を指定する](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)します。</span><span class="sxs-lookup"><span data-stu-id="26387-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="26387-118">完全なサンプルについては、「[2-D 変換のサンプル](https://go.microsoft.com/fwlink/?LinkID=158252)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="26387-118">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26387-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="26387-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="26387-120">変換の概要</span><span class="sxs-lookup"><span data-stu-id="26387-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="26387-121">方法トピック</span><span class="sxs-lookup"><span data-stu-id="26387-121">How-to Topics</span></span>](transformations-how-to-topics.md)
