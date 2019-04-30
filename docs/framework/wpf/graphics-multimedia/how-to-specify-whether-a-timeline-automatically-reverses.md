---
title: '方法: タイムラインを自動的に反転するかどうかを指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024665"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="b013c-102">方法: タイムラインを自動的に反転するかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="b013c-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="b013c-103">タイムラインの<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>プロパティは、順方向の反復が完了した後は、逆方向に再生があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b013c-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="b013c-104">次の例では、複数のアニメーションと同じ期間とターゲットの値ではなく、異なる<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>設定します。</span><span class="sxs-lookup"><span data-stu-id="b013c-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="b013c-105">示すためにどのように<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>プロパティの動作が異なる<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>を繰り返す一部のアニメーションの設定が設定されます。</span><span class="sxs-lookup"><span data-stu-id="b013c-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="b013c-106">最後のアニメーション表示方法、<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>プロパティの入れ子になったタイムラインに動作します。</span><span class="sxs-lookup"><span data-stu-id="b013c-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b013c-107">例</span><span class="sxs-lookup"><span data-stu-id="b013c-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
