---
title: '方法: アニメーションの出力値をアニメーションの開始値に追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 945675d03a280e2394fdb0eab27c0978dc7cc320
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102610"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="65bc4-102">方法: アニメーションの出力値をアニメーションの開始値に追加する</span><span class="sxs-lookup"><span data-stu-id="65bc4-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="65bc4-103">この例では、アニメーションの開始値をアニメーションの出力値を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="65bc4-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65bc4-104">例</span><span class="sxs-lookup"><span data-stu-id="65bc4-104">Example</span></span>  
 <span data-ttu-id="65bc4-105"><xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>プロパティをアニメーション化されたプロパティの開始値 (基本値) に追加するアニメーションの出力値にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="65bc4-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="65bc4-106">使用することができます、<xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>最も基本的なアニメーションとほとんどのキー フレーム アニメーションのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="65bc4-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="65bc4-107">詳細については、次を参照してください。[アニメーションの概要](animation-overview.md)と[キー フレーム アニメーションの概要](key-frame-animations-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="65bc4-107">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="65bc4-108">次の例を使用する効果を示しています、<xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType>プロパティ<xref:System.Windows.Media.Animation.DoubleAnimation>を使用して、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType>プロパティ<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>。</span><span class="sxs-lookup"><span data-stu-id="65bc4-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="65bc4-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="65bc4-109">See also</span></span>

- [<span data-ttu-id="65bc4-110">反復サイクル中にアニメーション値を累積する</span><span class="sxs-lookup"><span data-stu-id="65bc4-110">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="65bc4-111">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="65bc4-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="65bc4-112">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="65bc4-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="65bc4-113">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="65bc4-113">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
