---
title: '方法: 線形グラデーションを使用して領域を塗りつぶす'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: c48ff13811d784ecc7042b73b964a9e6f2d42a34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921920"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="5b5ae-102">方法: 線形グラデーションを使用して領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="5b5ae-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="5b5ae-103">この例は、使用する方法を示します、<xref:System.Windows.Media.LinearGradientBrush>線形グラデーションを使用して領域を描画するクラス。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="5b5ae-104">次の例では、<xref:System.Windows.Shapes.Shape.Fill%2A>の<xref:System.Windows.Shapes.Rectangle>が黄色から緑に青に赤に遷移対角線方向の線形グラデーションで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b5ae-105">例</span><span class="sxs-lookup"><span data-stu-id="5b5ae-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="5b5ae-106">次の図は、前の例で作成したグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="5b5ae-107">![対角線方向の線形グラデーション](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="5b5ae-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="5b5ae-108">水平方向の線形グラデーションを作成するには、変更、<xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>と<xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>の<xref:System.Windows.Media.LinearGradientBrush>(0,0.5) に (1,0.5) とします。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="5b5ae-109">次の例では、<xref:System.Windows.Shapes.Rectangle>が水平方向の線形グラデーションで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="5b5ae-110">次の図は、前の例で作成したグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="5b5ae-111">![水平方向の線形グラデーション](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="5b5ae-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="5b5ae-112">垂直方向の線形グラデーションを作成するには、変更、<xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>と<xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>の<xref:System.Windows.Media.LinearGradientBrush>(0.5,0) に (0.5,1) とします。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="5b5ae-113">次の例では、<xref:System.Windows.Shapes.Rectangle>が垂直方向の線形グラデーションで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="5b5ae-114">次の図は、前の例で作成したグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="5b5ae-115">![垂直方向の線形グラデーション](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="5b5ae-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b5ae-116">このトピックの例では、始点と終点を設定するための既定の座標系を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="5b5ae-117">既定の座標系は、境界ボックスに対して相対的です。0、境界ボックスの 0% を示し、1 は境界ボックスの 100% を示します。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="5b5ae-118">この座標系を設定して変更することができます、<xref:System.Windows.Media.GradientBrush.MappingMode%2A>プロパティ値を<xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5b5ae-119">絶対座標系は、境界ボックスに相対しません。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="5b5ae-120">値は、ローカル空間に直接変換されます。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="5b5ae-121">さらに別の例については、「[ブラシのサンプル](https://go.microsoft.com/fwlink/?LinkID=159973)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="5b5ae-122">グラデーションおよびその他の種類のブラシの詳細については、「[純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b5ae-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
