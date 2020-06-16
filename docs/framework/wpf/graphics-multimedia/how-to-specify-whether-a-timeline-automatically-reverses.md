---
title: '方法: タイムラインを自動的に反転するかどうかを指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024665"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="7f7d6-102">方法: タイムラインを自動的に反転するかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="7f7d6-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="7f7d6-103">タイムラインの <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> プロパティによって、前方の反復が完了した後、逆方向に再生するかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="7f7d6-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="7f7d6-104">次の例ではいくつかのアニメーションを確認できますが、継続時間とターゲット値が同じでも、<xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 設定が異なっています。</span><span class="sxs-lookup"><span data-stu-id="7f7d6-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="7f7d6-105"><xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 設定を変えたときの <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> プロパティの動作を見せる目的で、一部のアプリケーションが繰り返されるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="7f7d6-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="7f7d6-106">最後のアニメーションでは、入れ子になっているタイムラインでの <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> プロパティの動作を示します。</span><span class="sxs-lookup"><span data-stu-id="7f7d6-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f7d6-107">例</span><span class="sxs-lookup"><span data-stu-id="7f7d6-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
