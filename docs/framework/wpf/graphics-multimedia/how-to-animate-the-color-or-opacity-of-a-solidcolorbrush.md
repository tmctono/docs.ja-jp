---
title: '方法 : SolidColorBrush の色または不透明度をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452884"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="7fcb8-102">方法 : SolidColorBrush の色または不透明度をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="7fcb8-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="7fcb8-103">この例では、<xref:System.Windows.Media.SolidColorBrush>の <xref:System.Windows.Media.SolidColorBrush.Color%2A> と <xref:System.Windows.Media.Brush.Opacity%2A> をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fcb8-104">例</span><span class="sxs-lookup"><span data-stu-id="7fcb8-104">Example</span></span>  
 <span data-ttu-id="7fcb8-105">次の例では、3つのアニメーションを使用して、<xref:System.Windows.Media.SolidColorBrush>の <xref:System.Windows.Media.SolidColorBrush.Color%2A> と <xref:System.Windows.Media.Brush.Opacity%2A> をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="7fcb8-106">最初のアニメーション (<xref:System.Windows.Media.Animation.ColorAnimation>) は、マウスが四角形に入ったときにブラシの色を <xref:System.Windows.Media.Colors.Gray%2A> に変更します。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="7fcb8-107">次のアニメーション (もう1つの <xref:System.Windows.Media.Animation.ColorAnimation>) では、マウスポインターを四角形から離したときに、ブラシの色が <xref:System.Windows.Media.Colors.Orange%2A> に変更されます。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="7fcb8-108"><xref:System.Windows.Media.Animation.DoubleAnimation>の最後のアニメーションでは、マウスの左ボタンが押されたときにブラシの不透明度が0.0 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="7fcb8-109">さまざまな種類のブラシをアニメーション化する方法を示す完全なサンプルについては、「[ブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="7fcb8-110">アニメーションの詳細については、「[アニメーションの概要](animation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="7fcb8-111">他のアニメーションの例との一貫性を保つために、この例のコードバージョンでは、<xref:System.Windows.Media.Animation.Storyboard> オブジェクトを使用してアニメーションを適用します。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="7fcb8-112">ただし、コードで1つのアニメーションを適用する場合は、<xref:System.Windows.Media.Animation.Storyboard>を使用する代わりに、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> メソッドを使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="7fcb8-113">例については、「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fcb8-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fcb8-114">参照</span><span class="sxs-lookup"><span data-stu-id="7fcb8-114">See also</span></span>

- [<span data-ttu-id="7fcb8-115">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="7fcb8-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7fcb8-116">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="7fcb8-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="7fcb8-117">ブラシのサンプル</span><span class="sxs-lookup"><span data-stu-id="7fcb8-117">Brushes Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
