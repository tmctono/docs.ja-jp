---
title: '方法: 開始後に、ストーリー ボードを制御します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 107391386dfbb718f9436d9a039b08439fbc3279
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762138"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="c2a94-102">方法: 開始後に、ストーリー ボードを制御します。</span><span class="sxs-lookup"><span data-stu-id="c2a94-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="c2a94-103">この例では、コントロールにコードを使って、<xref:System.Windows.Media.Animation.Storyboard>開始後。</span><span class="sxs-lookup"><span data-stu-id="c2a94-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="c2a94-104">ストーリー ボードを制御する[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を使用して、<xref:System.Windows.Trigger>と<xref:System.Windows.TriggerAction>オブジェクト。 例については、次を参照してください。 [、ストーリー ボード開始後の制御をイベント トリガーを使用して](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2a94-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="c2a94-105">使用するストーリー ボードを開始するには、その<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>メソッド、プロパティがアニメーション化して、ストーリー ボードを開始するストーリー ボードのアニメーションを分散します。</span><span class="sxs-lookup"><span data-stu-id="c2a94-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="c2a94-106">ストーリー ボードを制御するためには、使用する、<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>メソッドを指定して**true** 2 番目のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c2a94-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="c2a94-107">一時停止、再開、シーク、停止、高速化する、またはストーリー ボード、速度が低下または塗りつぶし期間まで進める、ストーリー ボードの対話型のメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2a94-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="c2a94-108">次には、ストーリー ボードの対話型のメソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c2a94-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
- <span data-ttu-id="c2a94-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>:ストーリー ボードを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="c2a94-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
- <span data-ttu-id="c2a94-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>:一時停止中のストーリー ボードを再開します。</span><span class="sxs-lookup"><span data-stu-id="c2a94-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
- <span data-ttu-id="c2a94-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>:ストーリー ボードの対話型速度を設定します。</span><span class="sxs-lookup"><span data-stu-id="c2a94-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
- <span data-ttu-id="c2a94-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>:指定した場所のストーリー ボードをシークします。</span><span class="sxs-lookup"><span data-stu-id="c2a94-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
- <span data-ttu-id="c2a94-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>:指定した場所にストーリー ボードをシークします。</span><span class="sxs-lookup"><span data-stu-id="c2a94-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="c2a94-114">異なり、<xref:System.Windows.Media.Animation.Storyboard.Seek%2A>メソッドでは、この操作は、次の目盛りの前に処理されます。</span><span class="sxs-lookup"><span data-stu-id="c2a94-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
- <span data-ttu-id="c2a94-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>:ある場合は、塗りつぶし期間、ストーリー ボードを進めます。</span><span class="sxs-lookup"><span data-stu-id="c2a94-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
- <span data-ttu-id="c2a94-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>:ストーリー ボードを停止します。</span><span class="sxs-lookup"><span data-stu-id="c2a94-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="c2a94-117">次の例では、いくつかのストーリー ボード メソッドは、ストーリー ボードを対話的に制御に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2a94-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="c2a94-118">**注:** トリガーを使用してストーリー ボードを制御するための例を参照する[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を参照してください[イベント トリガーを使用して、ストーリー ボード開始後に制御する](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2a94-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2a94-119">例</span><span class="sxs-lookup"><span data-stu-id="c2a94-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c2a94-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2a94-120">See also</span></span>

- [<span data-ttu-id="c2a94-121">開始後のストーリーボードをイベント トリガーを使用して制御する</span><span class="sxs-lookup"><span data-stu-id="c2a94-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
