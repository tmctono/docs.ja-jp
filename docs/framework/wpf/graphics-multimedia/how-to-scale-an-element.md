---
title: '方法 : 要素をスケーリングする'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112051"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="66d7a-102">方法 : 要素をスケーリングする</span><span class="sxs-lookup"><span data-stu-id="66d7a-102">How to: Scale an Element</span></span>
<span data-ttu-id="66d7a-103">この例では、 を<xref:System.Windows.Media.ScaleTransform>使用して要素をスケーリングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="66d7a-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="66d7a-104">プロパティ<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>と<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>プロパティを使用して、指定した係数で要素のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="66d7a-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="66d7a-105">たとえば、値が<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>1.5 の場合、要素は元の幅の 150% に伸ばされます。</span><span class="sxs-lookup"><span data-stu-id="66d7a-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="66d7a-106">値<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>を 0.5 に設定すると、要素の高さが 50% 縮小されます。</span><span class="sxs-lookup"><span data-stu-id="66d7a-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="66d7a-107">プロパティ<xref:System.Windows.Media.ScaleTransform.CenterX%2A>と<xref:System.Windows.Media.ScaleTransform.CenterY%2A>プロパティを使用して、スケール操作の中心となる点を指定します。</span><span class="sxs-lookup"><span data-stu-id="66d7a-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="66d7a-108">既定では、a<xref:System.Windows.Media.ScaleTransform>は、四角形の左上隅に対応する点 (0,0) を中心に配置されます。</span><span class="sxs-lookup"><span data-stu-id="66d7a-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="66d7a-109">これは、要素を移動し、<xref:System.Windows.Media.Transform>より大きく見えるようにする効果があります。</span><span class="sxs-lookup"><span data-stu-id="66d7a-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="66d7a-110">次の例では、<xref:System.Windows.Media.ScaleTransform>を使用して 50 倍の 50<xref:System.Windows.Shapes.Rectangle>倍のサイズを使用します。</span><span class="sxs-lookup"><span data-stu-id="66d7a-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="66d7a-111">と<xref:System.Windows.Media.ScaleTransform>の両方<xref:System.Windows.Media.ScaleTransform.CenterX%2A>に 0 (既定値) の<xref:System.Windows.Media.ScaleTransform.CenterY%2A>値があります。</span><span class="sxs-lookup"><span data-stu-id="66d7a-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66d7a-112">例</span><span class="sxs-lookup"><span data-stu-id="66d7a-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="66d7a-113">通常、スケールされる<xref:System.Windows.Media.ScaleTransform.CenterX%2A>オブジェクト<xref:System.Windows.Media.ScaleTransform.CenterY%2A>の中心に設定し、<xref:System.Windows.FrameworkElement.Height%2A>次の値を設定します<xref:System.Windows.FrameworkElement.Width%2A>。</span><span class="sxs-lookup"><span data-stu-id="66d7a-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="66d7a-114">次の例では、<xref:System.Windows.Shapes.Rectangle>サイズが 2 倍になった別の例を示します。ただし、この<xref:System.Windows.Media.ScaleTransform>値は、両方の値と<xref:System.Windows.Media.ScaleTransform.CenterX%2A><xref:System.Windows.Media.ScaleTransform.CenterY%2A>の値が、四角形の中心に対応します。</span><span class="sxs-lookup"><span data-stu-id="66d7a-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="66d7a-115">次の図は、2 つの<xref:System.Windows.Media.ScaleTransform>操作の違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="66d7a-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="66d7a-116">点線は、拡大/縮小する前の四角形のサイズと位置を示しています。</span><span class="sxs-lookup"><span data-stu-id="66d7a-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="66d7a-117">![中心点が異なる 2 倍の拡大](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="66d7a-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="66d7a-118">2 つの ScaleTransform 操作では、ScaleX と ScaleY の値は同じですが、中心点が異なっています。</span><span class="sxs-lookup"><span data-stu-id="66d7a-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="66d7a-119">完全なサンプルについては[、2D 変換のサンプルを](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)参照してください。</span><span class="sxs-lookup"><span data-stu-id="66d7a-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d7a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="66d7a-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="66d7a-121">変換の概要</span><span class="sxs-lookup"><span data-stu-id="66d7a-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="66d7a-122">ハウツートピック</span><span class="sxs-lookup"><span data-stu-id="66d7a-122">How-to Topics</span></span>](transformations-how-to-topics.md)
