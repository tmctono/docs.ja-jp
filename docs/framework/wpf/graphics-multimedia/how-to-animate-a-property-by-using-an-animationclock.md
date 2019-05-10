---
title: '方法: AnimationClock を使用してプロパティをアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: 13d91e8589c40d84ba374ffc613388e24407796a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591287"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="ddf5e-102">方法: AnimationClock を使用してプロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ddf5e-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="ddf5e-103">この例は、使用する方法を示します<xref:System.Windows.Media.Animation.Clock>プロパティをアニメーション化するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ddf5e-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="ddf5e-104">依存関係プロパティをアニメーション化するには次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="ddf5e-104">There are three ways to animate a dependency property:</span></span>  
  
- <span data-ttu-id="ddf5e-105">作成、<xref:System.Windows.Media.Animation.AnimationTimeline>を使用してそのプロパティに関連付けると、<xref:System.Windows.Media.Animation.Storyboard>します。</span><span class="sxs-lookup"><span data-stu-id="ddf5e-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
- <span data-ttu-id="ddf5e-106">オブジェクトの<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>メソッドは、1 つを適用する<xref:System.Windows.Media.Animation.AnimationTimeline>対象のプロパティにします。</span><span class="sxs-lookup"><span data-stu-id="ddf5e-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
- <span data-ttu-id="ddf5e-107">作成、<xref:System.Windows.Media.Animation.AnimationClock>から、<xref:System.Windows.Media.Animation.AnimationTimeline>プロパティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ddf5e-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="ddf5e-108"><xref:System.Windows.Media.Animation.Storyboard> オブジェクトおよび<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>メソッドを使用すると、直接の作成とクロックを配布せずにプロパティをアニメーション化する (例については、次を参照してください[ストーリー ボードを使用してプロパティをアニメーション化する](how-to-animate-a-property-by-using-a-storyboard.md)と[プロパティせずアニメーション化します。ストーリー ボードを使用して](how-to-animate-a-property-without-using-a-storyboard.md))。クロックは作成され、自動的に配布します。</span><span class="sxs-lookup"><span data-stu-id="ddf5e-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddf5e-109">例</span><span class="sxs-lookup"><span data-stu-id="ddf5e-109">Example</span></span>  
 <span data-ttu-id="ddf5e-110">次の例を作成する方法を示しています、<xref:System.Windows.Media.Animation.AnimationClock>同様の 2 つのプロパティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ddf5e-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="ddf5e-111">対話的に制御する方法を示す例については、 <xref:System.Windows.Media.Animation.Clock> 、開始後を参照してください。[クロックを対話的に制御](how-to-interactively-control-a-clock.md)します。</span><span class="sxs-lookup"><span data-stu-id="ddf5e-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf5e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddf5e-112">See also</span></span>

- [<span data-ttu-id="ddf5e-113">ストーリーボードを使ってプロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ddf5e-113">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="ddf5e-114">ストーリーボードを使用せずにプロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ddf5e-114">Animate a Property Without Using a Storyboard</span></span>](how-to-animate-a-property-without-using-a-storyboard.md)
- [<span data-ttu-id="ddf5e-115">プロパティ アニメーションの手法の概要</span><span class="sxs-lookup"><span data-stu-id="ddf5e-115">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
