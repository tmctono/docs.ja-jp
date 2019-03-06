---
title: '方法: クロックの状態が変化したときに通知を受け取る'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
ms.openlocfilehash: dc3fffb88ce59ceb908d6febd2f078820513b641
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363138"
---
# <a name="how-to-receive-notification-when-a-clocks-state-changes"></a><span data-ttu-id="91bb3-102">方法: クロックの状態が変化したときに通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="91bb3-102">How to: Receive Notification When a Clock's State Changes</span></span>
<span data-ttu-id="91bb3-103">クロックの<xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated>イベントが発生したときにその<xref:System.Windows.Media.Animation.Clock.CurrentState%2A>はクロックが開始または停止するなど、無効になります。</span><span class="sxs-lookup"><span data-stu-id="91bb3-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="91bb3-104">このイベントを使用して直接登録できます、 <xref:System.Windows.Media.Animation.Clock>、またはを使用して登録することができます、<xref:System.Windows.Media.Animation.Timeline>します。</span><span class="sxs-lookup"><span data-stu-id="91bb3-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="91bb3-105">次の例では、<xref:System.Windows.Media.Animation.Storyboard>と 2 つ<xref:System.Windows.Media.Animation.DoubleAnimation>オブジェクトが 2 つの四角形の幅をアニメーション化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="91bb3-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="91bb3-106"><xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>クロックの状態の変更をリッスンするイベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="91bb3-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91bb3-107">例</span><span class="sxs-lookup"><span data-stu-id="91bb3-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="91bb3-108">次の図は、親タイムラインとしてアニメーションの異なる状態を入力します (*ストーリー ボード*) が進行します。</span><span class="sxs-lookup"><span data-stu-id="91bb3-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="91bb3-109">![2 つのアニメーションとストーリー ボードの状態をクロック](./media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="91bb3-109">![Clock states for a Storyboard with two animations](./media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="91bb3-110">次の表は、位置、時刻を示します*Animation1*の<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="91bb3-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="91bb3-111">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="91bb3-111">Time (Seconds)</span></span>|<span data-ttu-id="91bb3-112">1</span><span class="sxs-lookup"><span data-stu-id="91bb3-112">1</span></span>|<span data-ttu-id="91bb3-113">10</span><span class="sxs-lookup"><span data-stu-id="91bb3-113">10</span></span>|<span data-ttu-id="91bb3-114">19</span><span class="sxs-lookup"><span data-stu-id="91bb3-114">19</span></span>|<span data-ttu-id="91bb3-115">21</span><span class="sxs-lookup"><span data-stu-id="91bb3-115">21</span></span>|<span data-ttu-id="91bb3-116">30</span><span class="sxs-lookup"><span data-stu-id="91bb3-116">30</span></span>|<span data-ttu-id="91bb3-117">39</span><span class="sxs-lookup"><span data-stu-id="91bb3-117">39</span></span>|  
|<span data-ttu-id="91bb3-118">状態</span><span class="sxs-lookup"><span data-stu-id="91bb3-118">State</span></span>|<span data-ttu-id="91bb3-119">アクティブ</span><span class="sxs-lookup"><span data-stu-id="91bb3-119">Active</span></span>|<span data-ttu-id="91bb3-120">アクティブ</span><span class="sxs-lookup"><span data-stu-id="91bb3-120">Active</span></span>|<span data-ttu-id="91bb3-121">停止</span><span class="sxs-lookup"><span data-stu-id="91bb3-121">Stopped</span></span>|<span data-ttu-id="91bb3-122">アクティブ</span><span class="sxs-lookup"><span data-stu-id="91bb3-122">Active</span></span>|<span data-ttu-id="91bb3-123">アクティブ</span><span class="sxs-lookup"><span data-stu-id="91bb3-123">Active</span></span>|<span data-ttu-id="91bb3-124">停止</span><span class="sxs-lookup"><span data-stu-id="91bb3-124">Stopped</span></span>|  
  
 <span data-ttu-id="91bb3-125">次の表は、位置、時刻を示します*Animation2*の<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="91bb3-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="91bb3-126">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="91bb3-126">Time (Seconds)</span></span>|<span data-ttu-id="91bb3-127">1</span><span class="sxs-lookup"><span data-stu-id="91bb3-127">1</span></span>|<span data-ttu-id="91bb3-128">9</span><span class="sxs-lookup"><span data-stu-id="91bb3-128">9</span></span>|<span data-ttu-id="91bb3-129">11</span><span class="sxs-lookup"><span data-stu-id="91bb3-129">11</span></span>|<span data-ttu-id="91bb3-130">19</span><span class="sxs-lookup"><span data-stu-id="91bb3-130">19</span></span>|<span data-ttu-id="91bb3-131">21</span><span class="sxs-lookup"><span data-stu-id="91bb3-131">21</span></span>|<span data-ttu-id="91bb3-132">29</span><span class="sxs-lookup"><span data-stu-id="91bb3-132">29</span></span>|<span data-ttu-id="91bb3-133">31</span><span class="sxs-lookup"><span data-stu-id="91bb3-133">31</span></span>|<span data-ttu-id="91bb3-134">39</span><span class="sxs-lookup"><span data-stu-id="91bb3-134">39</span></span>|  
|<span data-ttu-id="91bb3-135">状態</span><span class="sxs-lookup"><span data-stu-id="91bb3-135">State</span></span>|<span data-ttu-id="91bb3-136">アクティブ</span><span class="sxs-lookup"><span data-stu-id="91bb3-136">Active</span></span>|<span data-ttu-id="91bb3-137">いっぱいになります。</span><span class="sxs-lookup"><span data-stu-id="91bb3-137">Filling</span></span>|<span data-ttu-id="91bb3-138">アクティブ</span><span class="sxs-lookup"><span data-stu-id="91bb3-138">Active</span></span>|<span data-ttu-id="91bb3-139">停止</span><span class="sxs-lookup"><span data-stu-id="91bb3-139">Stopped</span></span>|<span data-ttu-id="91bb3-140">アクティブ</span><span class="sxs-lookup"><span data-stu-id="91bb3-140">Active</span></span>|<span data-ttu-id="91bb3-141">いっぱいになります。</span><span class="sxs-lookup"><span data-stu-id="91bb3-141">Filling</span></span>|<span data-ttu-id="91bb3-142">アクティブ</span><span class="sxs-lookup"><span data-stu-id="91bb3-142">Active</span></span>|<span data-ttu-id="91bb3-143">停止</span><span class="sxs-lookup"><span data-stu-id="91bb3-143">Stopped</span></span>|  
  
 <span data-ttu-id="91bb3-144">注意*Animation1*の<xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>場合でも、その状態のまま、10 秒間にイベントが発生した<xref:System.Windows.Media.Animation.ClockState.Active>します。</span><span class="sxs-lookup"><span data-stu-id="91bb3-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="91bb3-145">変更が、10 秒で状態が変更されたためにです<xref:System.Windows.Media.Animation.ClockState.Active>に<xref:System.Windows.Media.Animation.ClockState.Filling>に戻ると<xref:System.Windows.Media.Animation.ClockState.Active>同じティックでします。</span><span class="sxs-lookup"><span data-stu-id="91bb3-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
