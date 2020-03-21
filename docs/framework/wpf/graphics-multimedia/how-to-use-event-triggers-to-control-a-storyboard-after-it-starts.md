---
title: '方法 : 開始後のストーリーボードをイベント トリガーを使用して制御する'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186703"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="8f713-102">方法 : 開始後のストーリーボードをイベント トリガーを使用して制御する</span><span class="sxs-lookup"><span data-stu-id="8f713-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="8f713-103">この例では、開始後に<xref:System.Windows.Media.Animation.Storyboard>a を制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8f713-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="8f713-104">を使用<xref:System.Windows.Media.Animation.Storyboard>[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]して を開始するには<xref:System.Windows.Media.Animation.BeginStoryboard>、 を使用してアニメーションをアニメーション化したオブジェクトとプロパティにアニメーションを配信し、ストーリーボードを開始します。</span><span class="sxs-lookup"><span data-stu-id="8f713-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="8f713-105">プロパティを指定<xref:System.Windows.Media.Animation.BeginStoryboard>して名前を指定する場合は、そのプロパティを制御可能なストーリーボードにします。 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A></span><span class="sxs-lookup"><span data-stu-id="8f713-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="8f713-106">ストーリーボードの開始後に、ストーリーボードを対話的に制御できます。</span><span class="sxs-lookup"><span data-stu-id="8f713-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="8f713-107">次のストーリーボード アクションをオブジェクト<xref:System.Windows.EventTrigger>と共に使用して、ストーリーボードを制御します。</span><span class="sxs-lookup"><span data-stu-id="8f713-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="8f713-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: ストーリーボードを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="8f713-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="8f713-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: 一時停止したストーリーボードを再開します。</span><span class="sxs-lookup"><span data-stu-id="8f713-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="8f713-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: ストーリーボードの速度を変更します。</span><span class="sxs-lookup"><span data-stu-id="8f713-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="8f713-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: ストーリーボードの塗りつぶし期間が終了する場合は、その塗りつぶし期間の終了まで進めます。</span><span class="sxs-lookup"><span data-stu-id="8f713-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="8f713-112"><xref:System.Windows.Media.Animation.StopStoryboard>: ストーリーボードを停止します。</span><span class="sxs-lookup"><span data-stu-id="8f713-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="8f713-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: ストーリーボードを削除し、リソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="8f713-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="8f713-114">例</span><span class="sxs-lookup"><span data-stu-id="8f713-114">Example</span></span>

<span data-ttu-id="8f713-115">次の例では、制御可能なストーリーボード アクションを使用して、ストーリーボードを対話的に制御します。</span><span class="sxs-lookup"><span data-stu-id="8f713-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="8f713-116">コードを使用してストーリーボードを制御する例については、「[対話型メソッドを使用してストーリーボードを開始した後でストーリーボードを制御する](how-to-control-a-storyboard-after-it-starts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f713-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="8f713-117">その他の例については、「[アニメーションの例ギャラリー](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f713-117">For additional examples, see the [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f713-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f713-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="8f713-119">対話型メソッドを使用してストーリーボードを開始後に制御する</span><span class="sxs-lookup"><span data-stu-id="8f713-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="8f713-120">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="8f713-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="8f713-121">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="8f713-121">Storyboards Overview</span></span>](storyboards-overview.md)
