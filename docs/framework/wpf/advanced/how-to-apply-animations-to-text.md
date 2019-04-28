---
title: '方法: アニメーションをテキストに適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 38aa432fecc5b5e10d8eb90be9c1c596728ed613
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776888"
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="55aa4-102">方法: アニメーションをテキストに適用する</span><span class="sxs-lookup"><span data-stu-id="55aa4-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="55aa4-103">アニメーションを利用すると、アプリケーションのテキストの表示方法や見た目を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="55aa4-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="55aa4-104">次の例のテキストの表示に影響を与えるさまざまな種類のアニメーションを使用して、<xref:System.Windows.Controls.TextBlock>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55aa4-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55aa4-105">例</span><span class="sxs-lookup"><span data-stu-id="55aa4-105">Example</span></span>  
 <span data-ttu-id="55aa4-106">次の例では、<xref:System.Windows.Media.Animation.DoubleAnimation>テキスト ブロックの幅をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="55aa4-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="55aa4-107">幅の値が 10 秒間、テキスト ブロックの幅から 0 に変化します。その後、幅の値を戻します。</span><span class="sxs-lookup"><span data-stu-id="55aa4-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="55aa4-108">この種類のアニメーションでワイプ効果を作ります。</span><span class="sxs-lookup"><span data-stu-id="55aa4-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="55aa4-109">次の例では、<xref:System.Windows.Media.Animation.DoubleAnimation>テキスト ブロックの不透明度をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="55aa4-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="55aa4-110">不透明度の値が 5 秒間、1.0 から 0 に変化し、その後、不透明度の値を戻します。</span><span class="sxs-lookup"><span data-stu-id="55aa4-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="55aa4-111">次の図の効果を示しています、<xref:System.Windows.Controls.TextBlock>コントロールからの不透明度を変更する`1.00`に`0.00`によって定義された 5 秒間隔中に、<xref:System.Windows.Media.Animation.Timeline.Duration%2A>します。</span><span class="sxs-lookup"><span data-stu-id="55aa4-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 ![不透明度を 1.00 から 0.00 に変更するテキスト。](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  
   
 <span data-ttu-id="55aa4-113">次の例では、<xref:System.Windows.Media.Animation.ColorAnimation>テキスト ブロックの前景色をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="55aa4-113">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="55aa4-114">前景色の値が 5 秒間、ある色から別の色に変化し、その後、色の値を戻します。</span><span class="sxs-lookup"><span data-stu-id="55aa4-114">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="55aa4-115">次の例では、<xref:System.Windows.Media.Animation.DoubleAnimation>テキスト ブロックを回転させる。</span><span class="sxs-lookup"><span data-stu-id="55aa4-115">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="55aa4-116">テキスト ブロックは 20 秒間、完全な回転を行い、その後、回転を引き続き繰り返します。</span><span class="sxs-lookup"><span data-stu-id="55aa4-116">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="55aa4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="55aa4-117">See also</span></span>

- [<span data-ttu-id="55aa4-118">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="55aa4-118">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
