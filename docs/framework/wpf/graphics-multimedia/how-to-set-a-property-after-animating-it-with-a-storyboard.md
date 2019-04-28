---
title: '方法: ストーリーボードを使用してアニメーション化した後にプロパティを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 2e1389392c6465ed56b2c71e53b2e3c1947acbe2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651104"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="1965c-102">方法: ストーリーボードを使用してアニメーション化した後にプロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="1965c-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="1965c-103">場合によっては、表示にアニメーション化した後、プロパティの値を変更できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="1965c-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1965c-104">例</span><span class="sxs-lookup"><span data-stu-id="1965c-104">Example</span></span>  
 <span data-ttu-id="1965c-105">次の例では、<xref:System.Windows.Media.Animation.Storyboard>の色をアニメーション化するために使用、<xref:System.Windows.Media.SolidColorBrush>します。</span><span class="sxs-lookup"><span data-stu-id="1965c-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="1965c-106">ストーリー ボードは、ボタンがクリックされたときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="1965c-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="1965c-107"><xref:System.Windows.Media.Animation.Timeline.Completed>プログラムが通知されるように、イベントが処理されるときに、<xref:System.Windows.Media.Animation.ColorAnimation>が完了するとします。</span><span class="sxs-lookup"><span data-stu-id="1965c-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="1965c-108">例</span><span class="sxs-lookup"><span data-stu-id="1965c-108">Example</span></span>  
 <span data-ttu-id="1965c-109">後に、<xref:System.Windows.Media.Animation.ColorAnimation>が完了したら、プログラム、ブラシの色を青に変更しよう。</span><span class="sxs-lookup"><span data-stu-id="1965c-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="1965c-110">何もする前のコードが表示されない: によって提供される、ブラシは黄色、これは、値、<xref:System.Windows.Media.Animation.ColorAnimation>ブラシをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="1965c-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="1965c-111">基になるプロパティの値 (基本値) は実際に青に変更します。</span><span class="sxs-lookup"><span data-stu-id="1965c-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="1965c-112">ただし、有効な場合、または、現在の値は黄色ため、<xref:System.Windows.Media.Animation.ColorAnimation>は基本の値をまだオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="1965c-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="1965c-113">基本の値をもう一度有効な値をする場合は、プロパティへの影響からアニメーションを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1965c-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="1965c-114">ストーリー ボード アニメーションでそれを行う 3 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="1965c-114">There are three ways to do this with storyboard animations:</span></span>  
  
- <span data-ttu-id="1965c-115">アニメーションの<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>プロパティを <xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="1965c-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
- <span data-ttu-id="1965c-116">ストーリー ボード全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="1965c-116">Remove the entire Storyboard.</span></span>  
  
- <span data-ttu-id="1965c-117">個々 のプロパティからアニメーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="1965c-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="1965c-118">Stop に設定されて、アニメーションの FillBehavior プロパティ</span><span class="sxs-lookup"><span data-stu-id="1965c-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="1965c-119">設定して<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>に<xref:System.Windows.Media.Animation.FillBehavior.Stop>、アクティブな期間の末尾に達した後、ターゲット プロパティに影響することを停止するアニメーションに指示します。</span><span class="sxs-lookup"><span data-stu-id="1965c-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="1965c-120">ストーリー ボード全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="1965c-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="1965c-121">使用して、<xref:System.Windows.Media.Animation.RemoveStoryboard>トリガーまたは<xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>メソッド、そのターゲット プロパティの影響を与えることを停止するストーリー ボード アニメーションがわかります。</span><span class="sxs-lookup"><span data-stu-id="1965c-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="1965c-122">この方法と設定の違い、<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>プロパティは、ストーリー ボードを削除することができますにいつでも、while、<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>プロパティは、アニメーションがアクティブな期間の末尾に達したときにのみ効果が。</span><span class="sxs-lookup"><span data-stu-id="1965c-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="1965c-123">個々 のプロパティからアニメーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="1965c-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="1965c-124">プロパティに影響を与えるからアニメーションを停止する別の手法は、使用する、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>アニメーション化されているオブジェクトのメソッド。</span><span class="sxs-lookup"><span data-stu-id="1965c-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="1965c-125">最初のパラメーターとしてアニメーション化されているプロパティを指定し、 `null` 2 つ目として。</span><span class="sxs-lookup"><span data-stu-id="1965c-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="1965c-126">この手法は、非ストーリー ボード アニメーションに対しても機能します。</span><span class="sxs-lookup"><span data-stu-id="1965c-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1965c-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1965c-127">See also</span></span>

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [<span data-ttu-id="1965c-128">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="1965c-128">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="1965c-129">プロパティ アニメーションの手法の概要</span><span class="sxs-lookup"><span data-stu-id="1965c-129">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
