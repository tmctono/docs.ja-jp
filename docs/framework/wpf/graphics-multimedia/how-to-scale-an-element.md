---
title: '方法: 要素をスケーリングする'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 6decc10c954b51d64c6045c01f1264df35429862
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358614"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="872ec-102">方法: 要素をスケーリングする</span><span class="sxs-lookup"><span data-stu-id="872ec-102">How to: Scale an Element</span></span>
<span data-ttu-id="872ec-103">この例は、使用する方法を示します、<xref:System.Windows.Media.ScaleTransform>に要素をスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="872ec-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="872ec-104">使用して、<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>と<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>プロパティを指定する係数を使用して、要素のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="872ec-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="872ec-105">たとえば、 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 1.5 の値が元の幅の 150 パーセントに要素を拡大します。</span><span class="sxs-lookup"><span data-stu-id="872ec-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="872ec-106">A<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>値 0.5 は 50% 要素の高さを縮小します。</span><span class="sxs-lookup"><span data-stu-id="872ec-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="872ec-107">使用して、<xref:System.Windows.Media.ScaleTransform.CenterX%2A>と<xref:System.Windows.Media.ScaleTransform.CenterY%2A>プロパティをスケール操作の中心点を指定します。</span><span class="sxs-lookup"><span data-stu-id="872ec-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="872ec-108">既定で、<xref:System.Windows.Media.ScaleTransform>四角形の左上隅に対応するポイント (0, 0) で中央揃えで配置します。</span><span class="sxs-lookup"><span data-stu-id="872ec-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="872ec-109">これは、要素の移動およびも適用するため、サイズが大きくなるように見えるのでの効果を<xref:System.Windows.Media.Transform>オブジェクトが存在する座標空間を変更します。</span><span class="sxs-lookup"><span data-stu-id="872ec-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="872ec-110">次の例では、 <xref:System.Windows.Media.ScaleTransform> 50 での 50 のサイズを 2 倍に<xref:System.Windows.Shapes.Rectangle>します。</span><span class="sxs-lookup"><span data-stu-id="872ec-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="872ec-111"><xref:System.Windows.Media.ScaleTransform>両方の 0 (既定値) の値を持つ<xref:System.Windows.Media.ScaleTransform.CenterX%2A>と<xref:System.Windows.Media.ScaleTransform.CenterY%2A>します。</span><span class="sxs-lookup"><span data-stu-id="872ec-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="872ec-112">例</span><span class="sxs-lookup"><span data-stu-id="872ec-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="872ec-113">通常、設定<xref:System.Windows.Media.ScaleTransform.CenterX%2A>と<xref:System.Windows.Media.ScaleTransform.CenterY%2A>スケール オブジェクトの中心を: (<xref:System.Windows.FrameworkElement.Width%2A>/2、  <xref:System.Windows.FrameworkElement.Height%2A> /2)。</span><span class="sxs-lookup"><span data-stu-id="872ec-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="872ec-114">次の例では別<xref:System.Windows.Shapes.Rectangle>; のサイズが倍増するただし、この<xref:System.Windows.Media.ScaleTransform>両方の 25 の値を持つ<xref:System.Windows.Media.ScaleTransform.CenterX%2A>と<xref:System.Windows.Media.ScaleTransform.CenterY%2A>、四角形の中心に対応します。</span><span class="sxs-lookup"><span data-stu-id="872ec-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="872ec-115">次の図は、2 つの違いを示しています。<xref:System.Windows.Media.ScaleTransform>操作。</span><span class="sxs-lookup"><span data-stu-id="872ec-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="872ec-116">点線は、拡大/縮小する前の四角形のサイズと位置を示しています。</span><span class="sxs-lookup"><span data-stu-id="872ec-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="872ec-117">![中心点が異なる 2 倍のスケール](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="872ec-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="872ec-118">2 つの ScaleTransform 操作では、ScaleX と ScaleY の値は同じですが、中心点が異なっています。</span><span class="sxs-lookup"><span data-stu-id="872ec-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="872ec-119">完全なサンプルについては、「[2-D 変換のサンプル](https://go.microsoft.com/fwlink/?LinkID=158252)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="872ec-119">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="872ec-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="872ec-120">See also</span></span>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="872ec-121">変換の概要</span><span class="sxs-lookup"><span data-stu-id="872ec-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="872ec-122">方法トピック</span><span class="sxs-lookup"><span data-stu-id="872ec-122">How-to Topics</span></span>](transformations-how-to-topics.md)
