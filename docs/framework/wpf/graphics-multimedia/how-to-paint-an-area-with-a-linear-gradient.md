---
title: '方法: 線形グラデーションを使用して領域を塗りつぶす'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 92c9ccd846dbbce043d13e6ba82b9fa8e72fa8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916172"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="2e1a5-102">方法: 線形グラデーションを使用して領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="2e1a5-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="2e1a5-103">この例では、 <xref:System.Windows.Media.LinearGradientBrush>クラスを使用して、線状グラデーションで領域を塗りつぶす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="2e1a5-104">次の例では、 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle>のは、黄色から赤、青から黄緑に遷移する対角線の線形グラデーションで塗りつぶされています。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e1a5-105">例</span><span class="sxs-lookup"><span data-stu-id="2e1a5-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="2e1a5-106">次の図は、前の例で作成したグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="2e1a5-107">![対角線方向の線形グラデーション](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="2e1a5-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="2e1a5-108">水平方向の線形グラデーションを作成するに<xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>は<xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 、の<xref:System.Windows.Media.LinearGradientBrush>およびのを (0, 0.5) と (1, 0.5) に変更します。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="2e1a5-109">次の例では、 <xref:System.Windows.Shapes.Rectangle>は水平線形グラデーションで塗りつぶされています。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="2e1a5-110">次の図は、前の例で作成したグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="2e1a5-111">![水平方向の線形グラデーション](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="2e1a5-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="2e1a5-112">垂直方向の線形グラデーションを作成するに<xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>は<xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 、の<xref:System.Windows.Media.LinearGradientBrush>とのを (0.5, 0) および (0.5, 1) に変更します。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="2e1a5-113">次の例<xref:System.Windows.Shapes.Rectangle>では、が垂直方向の線形グラデーションで塗りつぶされています。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="2e1a5-114">次の図は、前の例で作成したグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="2e1a5-115">![垂直方向の線状グラデーション](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="2e1a5-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e1a5-116">このトピックの例では、開始点と終了点を設定するための既定の座標系を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="2e1a5-117">既定の座標系は、境界ボックスに対して相対的です。0 は境界ボックスの 0% を示し、1 は境界ボックスの 100% を示します。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="2e1a5-118">この座標系を変更するには、 <xref:System.Windows.Media.GradientBrush.MappingMode%2A>プロパティを値<xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2e1a5-119">絶対座標系は、境界ボックスに相対しません。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="2e1a5-120">値は、ローカル空間に直接変換されます。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="2e1a5-121">さらに別の例については、「[ブラシのサンプル](https://go.microsoft.com/fwlink/?LinkID=159973)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="2e1a5-122">グラデーションおよびその他の種類のブラシの詳細については、「[純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e1a5-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
