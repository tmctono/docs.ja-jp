---
title: '方法: 開始後のストーリーボードをイベント トリガーを使用して制御する'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 32591edd065a8122b84ff14102f672ccf6001d67
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855847"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="6f4bb-102">方法: 開始後のストーリーボードをイベント トリガーを使用して制御する</span><span class="sxs-lookup"><span data-stu-id="6f4bb-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>

<span data-ttu-id="6f4bb-103">この例では、の開始<xref:System.Windows.Media.Animation.Storyboard>後にを制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="6f4bb-104">を使用<xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]してを開始する<xref:System.Windows.Media.Animation.BeginStoryboard>には、を使用します。これにより、アニメーションがアニメーション化されてオブジェクトとプロパティに配分され、ストーリーボードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="6f4bb-105">プロパティ<xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>を指定<xref:System.Windows.Media.Animation.BeginStoryboard>して名前を指定すると、制御可能なストーリーボードになります。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="6f4bb-106">その後、ストーリーボードを開始後に対話的に制御できます。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-106">You can then interactively control the storyboard after it starts.</span></span>

<span data-ttu-id="6f4bb-107">次のストーリーボードアクションをオブジェクト<xref:System.Windows.EventTrigger>と共に使用して、ストーリーボードを制御します。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>

- <span data-ttu-id="6f4bb-108"><xref:System.Windows.Media.Animation.PauseStoryboard>:ストーリーボードを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>

- <span data-ttu-id="6f4bb-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>:一時停止したストーリーボードを再開します。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>

- <span data-ttu-id="6f4bb-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>:ストーリーボードの速度を変更します。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>

- <span data-ttu-id="6f4bb-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>:ストーリーボードがある場合は、そのストーリーボードをその塗りつぶし期間の末尾に進めます。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>

- <span data-ttu-id="6f4bb-112"><xref:System.Windows.Media.Animation.StopStoryboard>:ストーリーボードを停止します。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>

- <span data-ttu-id="6f4bb-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>:ストーリーボードを削除し、リソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>

## <a name="example"></a><span data-ttu-id="6f4bb-114">例</span><span class="sxs-lookup"><span data-stu-id="6f4bb-114">Example</span></span>

<span data-ttu-id="6f4bb-115">次の例では、制御可能なストーリーボードアクションを使用して、ストーリーボードを対話的に制御します。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>

> [!NOTE]
> <span data-ttu-id="6f4bb-116">コードを使用してストーリーボードを制御する例については、「[対話的なメソッドを使用してストーリーボードを開始した後にコントロールを制御](how-to-control-a-storyboard-after-it-starts.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-116">To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

<span data-ttu-id="6f4bb-117">その他の例については、「[アニメーションの例ギャラリー](https://go.microsoft.com/fwlink/?LinkID=159969)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f4bb-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f4bb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f4bb-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="6f4bb-119">対話型メソッドを使用してストーリーボードを開始後に制御する</span><span class="sxs-lookup"><span data-stu-id="6f4bb-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="6f4bb-120">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="6f4bb-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6f4bb-121">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="6f4bb-121">Storyboards Overview</span></span>](storyboards-overview.md)
