---
title: '方法: ストーリーボード アニメーション間で HandoffBehavior を指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: d7129d6a48bdf31dc4953bb450267ad3b38fdd17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651039"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="bfaaa-102">方法: ストーリーボード アニメーション間で HandoffBehavior を指定する</span><span class="sxs-lookup"><span data-stu-id="bfaaa-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="bfaaa-103">この例は、ストーリーボード アニメーション間でハンドオフ動作を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bfaaa-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="bfaaa-104"><xref:System.Windows.Media.Animation.BeginStoryboard> の <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> プロパティは、既にプロパティに適用されている既存のアニメーションと新しいアニメーションが相互作用する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfaaa-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfaaa-105">例</span><span class="sxs-lookup"><span data-stu-id="bfaaa-105">Example</span></span>  
 <span data-ttu-id="bfaaa-106">次の例では、マウス カーソルを合わせると拡大し、カーソルを離すと縮小する 2 つのボタンを作成しています。</span><span class="sxs-lookup"><span data-stu-id="bfaaa-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="bfaaa-107">ボタンにマウスを合わせてからカーソルをすぐに離すと、最初のアニメーションが終了する前に 2 番目のアニメーションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="bfaaa-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="bfaaa-108">このように 2 つのアニメーションが重なり、<xref:System.Windows.Media.Animation.HandoffBehavior.Compose> と <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> の <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> の値の違いを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bfaaa-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="bfaaa-109"><xref:System.Windows.Media.Animation.HandoffBehavior.Compose> の値を重複するアニメーションと組み合わされると、アニメーション間でのスムーズな画面切り替え効果が生まれます。一方、<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> の値を指定すると、新しいアニメーションが、前に重なっていたアニメーションを直ちに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="bfaaa-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="bfaaa-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfaaa-110">See also</span></span>

- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [<span data-ttu-id="bfaaa-111">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="bfaaa-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="bfaaa-112">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="bfaaa-112">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
