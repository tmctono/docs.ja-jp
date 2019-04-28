---
title: '方法: ストーリーボード アニメーション間で HandoffBehavior を指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: d7129d6a48bdf31dc4953bb450267ad3b38fdd17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651039"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="92188-102">方法: ストーリーボード アニメーション間で HandoffBehavior を指定する</span><span class="sxs-lookup"><span data-stu-id="92188-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="92188-103">この例では、ストーリー ボード アニメーション間のハンドオフ動作を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="92188-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="92188-104"><xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>プロパティの<xref:System.Windows.Media.Animation.BeginStoryboard>新しいアニメーションを指定します。 プロパティに既に適用されている既存の対話します。</span><span class="sxs-lookup"><span data-stu-id="92188-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92188-105">例</span><span class="sxs-lookup"><span data-stu-id="92188-105">Example</span></span>  
 <span data-ttu-id="92188-106">次の例では、2 つのボタン上にマウス カーソルを移動すると拡大、カーソルがすぐに移動すると、縮小を作成します。</span><span class="sxs-lookup"><span data-stu-id="92188-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="92188-107">ボタンの上にマウス カーソルをすばやく削除して場合、は、1 つ目が終了する前に、2 番目のアニメーションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="92188-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="92188-108">間の差が表示されるこのような 2 つのアニメーションが重なっている場合は、<xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>値<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>と<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>します。</span><span class="sxs-lookup"><span data-stu-id="92188-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="92188-109">値<xref:System.Windows.Media.Animation.HandoffBehavior.Compose>の値の中にアニメーション間で遷移をスムーズに重なり合うアニメーションを組み合わせて<xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>新しいアニメーションをすぐに重複する前のアニメーションを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="92188-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="92188-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="92188-110">See also</span></span>

- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [<span data-ttu-id="92188-111">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="92188-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="92188-112">アニメーションとタイミングに関するトピック</span><span class="sxs-lookup"><span data-stu-id="92188-112">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
