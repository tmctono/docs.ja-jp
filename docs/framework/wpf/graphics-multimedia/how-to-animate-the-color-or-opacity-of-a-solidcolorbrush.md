---
title: '方法: SolidColorBrush の色または不透明度をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 610a7c4879b4ffe54940e8bc744dcca0711e84d2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593398"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="3ace0-102">方法: SolidColorBrush の色または不透明度をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="3ace0-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="3ace0-103">この例は、アニメーション化する方法を示しています、<xref:System.Windows.Media.SolidColorBrush.Color%2A>と<xref:System.Windows.Media.Brush.Opacity%2A>の<xref:System.Windows.Media.SolidColorBrush>します。</span><span class="sxs-lookup"><span data-stu-id="3ace0-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ace0-104">例</span><span class="sxs-lookup"><span data-stu-id="3ace0-104">Example</span></span>  
 <span data-ttu-id="3ace0-105">次の例では、アニメーション化する 3 つのアニメーションを使用して、<xref:System.Windows.Media.SolidColorBrush.Color%2A>と<xref:System.Windows.Media.Brush.Opacity%2A>の<xref:System.Windows.Media.SolidColorBrush>します。</span><span class="sxs-lookup"><span data-stu-id="3ace0-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="3ace0-106">最初のアニメーションを<xref:System.Windows.Media.Animation.ColorAnimation>、ブラシの色を変更<xref:System.Windows.Media.Colors.Gray%2A>マウスが四角形に入ったとき。</span><span class="sxs-lookup"><span data-stu-id="3ace0-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="3ace0-107">[次へ] のアニメーションでは、もう 1 つ<xref:System.Windows.Media.Animation.ColorAnimation>、ブラシの色を変更<xref:System.Windows.Media.Colors.Orange%2A>マウスから離したときに四角形。</span><span class="sxs-lookup"><span data-stu-id="3ace0-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="3ace0-108">最後のアニメーションを<xref:System.Windows.Media.Animation.DoubleAnimation>マウスの左ボタンが押されたときに、ブラシの不透明度を 0.0 に変更します。</span><span class="sxs-lookup"><span data-stu-id="3ace0-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="3ace0-109">さまざまな種類のブラシをアニメーション化する方法を示していますより完全なサンプルを参照してください、[ブラシのサンプル](https://go.microsoft.com/fwlink/?LinkID=159973)します。</span><span class="sxs-lookup"><span data-stu-id="3ace0-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="3ace0-110">アニメーションの詳細については、次を参照してください。、[アニメーションの概要](animation-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="3ace0-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="3ace0-111">この例のコードを使用して、他のアニメーション例と一貫性を保つのため、<xref:System.Windows.Media.Animation.Storyboard>アニメーションを適用するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3ace0-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="3ace0-112">ただし、コード内で 1 つのアニメーションを適用する場合は使いやすく、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>メソッドを使用してではなく、<xref:System.Windows.Media.Animation.Storyboard>します。</span><span class="sxs-lookup"><span data-stu-id="3ace0-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="3ace0-113">例については、「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ace0-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ace0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ace0-114">See also</span></span>

- [<span data-ttu-id="3ace0-115">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="3ace0-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3ace0-116">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="3ace0-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="3ace0-117">ブラシのサンプル</span><span class="sxs-lookup"><span data-stu-id="3ace0-117">Brushes Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159973)
