---
title: contextSwitchDeadlock MDA
description: COM コンテキストの遷移中にデッドロックが検出されたときにアクティブ化される、.NET での contextSwitchDeadlock ロックマネージデバッグアシスタント (MDA) について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
ms.openlocfilehash: 52db4f2c88bac4e8cac621cca989fa10acb43f94
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416019"
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="eef30-103">contextSwitchDeadlock MDA</span><span class="sxs-lookup"><span data-stu-id="eef30-103">contextSwitchDeadlock MDA</span></span>

<span data-ttu-id="eef30-104">`contextSwitchDeadlock` マネージド デバッグ アシスタント (MDA) は、COM コンテキストの遷移の試行中にデッドロックが検出されるとアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="eef30-104">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>

## <a name="symptoms"></a><span data-ttu-id="eef30-105">現象</span><span class="sxs-lookup"><span data-stu-id="eef30-105">Symptoms</span></span>

<span data-ttu-id="eef30-106">最も一般的な症状は、マネージド コードから実行されたアンマネージド COM コンポーネントの呼び出しから戻らないことです。</span><span class="sxs-lookup"><span data-stu-id="eef30-106">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="eef30-107">別の症状として、メモリの使用量が時間と共に増加する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="eef30-107">Another symptom is memory usage increasing over time.</span></span>

## <a name="cause"></a><span data-ttu-id="eef30-108">原因</span><span class="sxs-lookup"><span data-stu-id="eef30-108">Cause</span></span>

<span data-ttu-id="eef30-109">最も考えられる原因として、シングルスレッド アパートメント (STA) スレッドがメッセージ ポンプを行っていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="eef30-109">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="eef30-110">STA スレッドが、メッセージ ポンプを行わずに待機しているか、または時間のかかる操作を実行していて、メッセージ キューのポンプを許可していません。</span><span class="sxs-lookup"><span data-stu-id="eef30-110">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>

<span data-ttu-id="eef30-111">メモリ使用量が時間の経過と共に増加する症状は、ファイナライザー スレッドがアンマネージ COM コンポーネント上の `Release` を呼び出そうとして、そのコンポーネントが戻らない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="eef30-111">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="eef30-112">このため、ファイナライザーは他のオブジェクトを再利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="eef30-112">This prevents the finalizer from reclaiming other objects.</span></span>

<span data-ttu-id="eef30-113">既定では、Visual Basic コンソール アプリケーションのメイン スレッドのスレッド処理モデルは STA です。</span><span class="sxs-lookup"><span data-stu-id="eef30-113">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="eef30-114">STA スレッドが共通言語ランタイムまたはサードパーティ コントロールを通じて COM 相互運用性を直接または間接的に使用する場合、この MDA がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="eef30-114">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="eef30-115">Visual Basic コンソール アプリケーションでこの MDA がアクティブ化されるのを防ぐには、メイン メソッドに <xref:System.MTAThreadAttribute> 属性を適用するか、またはメッセージをポンプするようにアプリケーションを変更します。</span><span class="sxs-lookup"><span data-stu-id="eef30-115">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>

<span data-ttu-id="eef30-116">次のすべての条件が満たされる場合、この MDA が誤ってアクティブ化される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eef30-116">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>

- <span data-ttu-id="eef30-117">アプリケーションがライブラリを通じて直接または間接的に STA スレッドから COM コンポーネントを作成する。</span><span class="sxs-lookup"><span data-stu-id="eef30-117">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>

- <span data-ttu-id="eef30-118">デバッガーでアプリケーションが中断され、ユーザーがアプリケーションを続行したか、またはステップ操作を実行した。</span><span class="sxs-lookup"><span data-stu-id="eef30-118">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>

- <span data-ttu-id="eef30-119">アンマネージ デバッグが有効になっていない。</span><span class="sxs-lookup"><span data-stu-id="eef30-119">Unmanaged debugging is not enabled.</span></span>

<span data-ttu-id="eef30-120">MDA が誤ってアクティブ化されたかどうかを判断するには、すべてのブレークポイントを無効にし、アプリケーションを再び実行して、中断なしで実行させます。</span><span class="sxs-lookup"><span data-stu-id="eef30-120">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="eef30-121">MDA がアクティブ化されない場合は、最初のアクティブ化は誤りだった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eef30-121">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="eef30-122">その場合は、MDA を無効にして、デバッグ セッションとの干渉を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="eef30-122">In this case, disable the MDA to avoid interference with the debugging session.</span></span>

> [!NOTE]
> <span data-ttu-id="eef30-123">この MDA は、Visual Studio の既定のセットに含まれています。</span><span class="sxs-lookup"><span data-stu-id="eef30-123">This MDA is in the default set for Visual Studio.</span></span> <span data-ttu-id="eef30-124">Mda を無効にする方法の詳細については、「[マネージデバッグアシスタントによるエラーの診断](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eef30-124">For information about how to disable MDAs, see [Diagnosing Errors with Managed Debugging Assistants](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span></span>

## <a name="resolution"></a><span data-ttu-id="eef30-125">解決策</span><span class="sxs-lookup"><span data-stu-id="eef30-125">Resolution</span></span>

<span data-ttu-id="eef30-126">STA メッセージ ポンプに関する COM 規則に従います。</span><span class="sxs-lookup"><span data-stu-id="eef30-126">Follow COM rules regarding STA message pumping.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="eef30-127">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="eef30-127">Effect on the Runtime</span></span>

<span data-ttu-id="eef30-128">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="eef30-128">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="eef30-129">COM コンテキストに関するデータを報告するだけです。</span><span class="sxs-lookup"><span data-stu-id="eef30-129">It only reports data about COM contexts.</span></span>

## <a name="output"></a><span data-ttu-id="eef30-130">出力</span><span class="sxs-lookup"><span data-stu-id="eef30-130">Output</span></span>

<span data-ttu-id="eef30-131">現在のコンテキストおよびターゲット コンテキストを説明するメッセージです。</span><span class="sxs-lookup"><span data-stu-id="eef30-131">A message describing the current context and the target context.</span></span>

## <a name="configuration"></a><span data-ttu-id="eef30-132">構成</span><span class="sxs-lookup"><span data-stu-id="eef30-132">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <contextSwitchDeadlock />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="eef30-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="eef30-133">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="eef30-134">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="eef30-134">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="eef30-135">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="eef30-135">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
