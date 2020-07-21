---
title: スレッド プール ETW イベント
description: スレッドプールの ETW イベントを確認します。これは、.NET のスレッドに関する情報を収集します。 スレッドプールイベントは、ワーカースレッドプールイベントまたは i/o スレッドプールイベントです。
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: d3059cec5007c24d41a4a779939d4990f19305ca
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475204"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="77298-104">スレッド プール ETW イベント</span><span class="sxs-lookup"><span data-stu-id="77298-104">Thread Pool ETW Events</span></span>
<span data-ttu-id="77298-105">これらのイベントは、ワーカー スレッドと I/O スレッドに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="77298-105">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="77298-106">スレッド プール イベントには 2 つのグループがあります。</span><span class="sxs-lookup"><span data-stu-id="77298-106">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="77298-107">[ワーカー スレッド プール イベント](#worker-thread-pool-events)は、アプリケーションがどのようにスレッド プールを使用するかに関する情報と、コンカレンシー制御におけるワークロードの効果に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="77298-107">[Worker thread pool events](#worker-thread-pool-events), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="77298-108">[I/O スレッド プール イベント](#io-thread-events)は、スレッド プールで作成、無効化、無効化解除、または終了した I/O スレッドに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="77298-108">[I/O thread pool events](#io-thread-events), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  

## <a name="worker-thread-pool-events"></a><span data-ttu-id="77298-109">ワーカー スレッド プール イベント</span><span class="sxs-lookup"><span data-stu-id="77298-109">Worker Thread Pool Events</span></span>
 <span data-ttu-id="77298-110">これらのイベントは、ランタイムのワーカー スレッドのプールに関連付けられており、スレッド イベントに関する通知 (スレッドが作成されたり停止されたりした場合など) を提供します。</span><span class="sxs-lookup"><span data-stu-id="77298-110">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="77298-111">ワーカー スレッド プールは、スレッドの数が計測されたスループットに基づいて計算されるアダプティブ アルゴリズムを使用して、コンカレンシー制御を実行します。</span><span class="sxs-lookup"><span data-stu-id="77298-111">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="77298-112">ワーカー スレッド プール イベントを使用すると、アプリケーションで使用されるスレッド プールの様子や特定のワークロードがコンカレンシー制御に与える影響などを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="77298-112">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="77298-113">ThreadPoolWorkerThreadStart および ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="77298-113">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="77298-114">次の表に、これらのイベントのキーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-114">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="77298-115">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="77298-115">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="77298-116">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="77298-116">Keyword for raising the event</span></span>|<span data-ttu-id="77298-117">Level</span><span class="sxs-lookup"><span data-stu-id="77298-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="77298-118">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="77298-118">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="77298-119">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="77298-119">Informational (4)</span></span>|  
  
 <span data-ttu-id="77298-120">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="77298-120">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77298-121">Event</span><span class="sxs-lookup"><span data-stu-id="77298-121">Event</span></span>|<span data-ttu-id="77298-122">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77298-122">Event ID</span></span>|<span data-ttu-id="77298-123">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="77298-123">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="77298-124">50</span><span class="sxs-lookup"><span data-stu-id="77298-124">50</span></span>|<span data-ttu-id="77298-125">ワーカー スレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="77298-125">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="77298-126">51</span><span class="sxs-lookup"><span data-stu-id="77298-126">51</span></span>|<span data-ttu-id="77298-127">ワーカー スレッドが停止された。</span><span class="sxs-lookup"><span data-stu-id="77298-127">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="77298-128">52</span><span class="sxs-lookup"><span data-stu-id="77298-128">52</span></span>|<span data-ttu-id="77298-129">ワーカー スレッドが無効にされた。</span><span class="sxs-lookup"><span data-stu-id="77298-129">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="77298-130">53</span><span class="sxs-lookup"><span data-stu-id="77298-130">53</span></span>|<span data-ttu-id="77298-131">提供終了になったワーカー スレッドが再びアクティブになった。</span><span class="sxs-lookup"><span data-stu-id="77298-131">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="77298-132">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-132">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77298-133">フィールド名</span><span class="sxs-lookup"><span data-stu-id="77298-133">Field name</span></span>|<span data-ttu-id="77298-134">データ型</span><span class="sxs-lookup"><span data-stu-id="77298-134">Data type</span></span>|<span data-ttu-id="77298-135">説明</span><span class="sxs-lookup"><span data-stu-id="77298-135">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77298-136">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="77298-136">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="77298-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77298-137">win:UInt32</span></span>|<span data-ttu-id="77298-138">作業の処理に使用可能なワーカー スレッド (既に作業の処理中のもの含む) の数。</span><span class="sxs-lookup"><span data-stu-id="77298-138">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="77298-139">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="77298-139">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="77298-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77298-140">win:UInt32</span></span>|<span data-ttu-id="77298-141">作業の処理に使用できないものの、後にさらに多くのスレッドが必要になった場合に備えて予約されているワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="77298-141">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="77298-142">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77298-142">ClrInstanceID</span></span>|<span data-ttu-id="77298-143">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77298-143">Win:UInt16</span></span>|<span data-ttu-id="77298-144">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="77298-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="77298-145">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="77298-145">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="77298-146">これらのスレッド プール イベントは、スレッドの挿入 (コンカレンシー制御) アルゴリズムの動作を理解したりデバッグしたりするための情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="77298-146">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="77298-147">この情報は、ワーカー スレッド プールによって内部で使用されます。</span><span class="sxs-lookup"><span data-stu-id="77298-147">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="77298-148">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="77298-148">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="77298-149">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-149">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77298-150">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="77298-150">Keyword for raising the event</span></span>|<span data-ttu-id="77298-151">Level</span><span class="sxs-lookup"><span data-stu-id="77298-151">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="77298-152">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="77298-152">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="77298-153">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="77298-153">Informational (4)</span></span>|  
  
 <span data-ttu-id="77298-154">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="77298-154">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77298-155">Event</span><span class="sxs-lookup"><span data-stu-id="77298-155">Event</span></span>|<span data-ttu-id="77298-156">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77298-156">Event ID</span></span>|<span data-ttu-id="77298-157">説明</span><span class="sxs-lookup"><span data-stu-id="77298-157">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="77298-158">54</span><span class="sxs-lookup"><span data-stu-id="77298-158">54</span></span>|<span data-ttu-id="77298-159">1 つのサンプルの情報のコレクションを参照します。つまり、特定のコンカレンシー レベルの特定の時刻におけるスループットの測定値です。</span><span class="sxs-lookup"><span data-stu-id="77298-159">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="77298-160">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-160">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77298-161">フィールド名</span><span class="sxs-lookup"><span data-stu-id="77298-161">Field name</span></span>|<span data-ttu-id="77298-162">データ型</span><span class="sxs-lookup"><span data-stu-id="77298-162">Data type</span></span>|<span data-ttu-id="77298-163">説明</span><span class="sxs-lookup"><span data-stu-id="77298-163">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77298-164">スループット</span><span class="sxs-lookup"><span data-stu-id="77298-164">Throughput</span></span>|<span data-ttu-id="77298-165">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-165">win:Double</span></span>|<span data-ttu-id="77298-166">時間の単位あたりの入力候補の数です。</span><span class="sxs-lookup"><span data-stu-id="77298-166">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="77298-167">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77298-167">ClrInstanceID</span></span>|<span data-ttu-id="77298-168">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77298-168">Win:UInt16</span></span>|<span data-ttu-id="77298-169">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="77298-169">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="77298-170">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="77298-170">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="77298-171">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-171">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77298-172">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="77298-172">Keyword for raising the event</span></span>|<span data-ttu-id="77298-173">Level</span><span class="sxs-lookup"><span data-stu-id="77298-173">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="77298-174">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="77298-174">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="77298-175">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="77298-175">Informational (4)</span></span>|  
  
 <span data-ttu-id="77298-176">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="77298-176">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77298-177">Event</span><span class="sxs-lookup"><span data-stu-id="77298-177">Event</span></span>|<span data-ttu-id="77298-178">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77298-178">Event ID</span></span>|<span data-ttu-id="77298-179">説明</span><span class="sxs-lookup"><span data-stu-id="77298-179">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="77298-180">55</span><span class="sxs-lookup"><span data-stu-id="77298-180">55</span></span>|<span data-ttu-id="77298-181">スレッドの挿入 (山登り法) アルゴリズムが、コンカレンシー レベルに変更があったと判断した場合に、コントロールの変更を記録します。</span><span class="sxs-lookup"><span data-stu-id="77298-181">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="77298-182">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-182">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77298-183">フィールド名</span><span class="sxs-lookup"><span data-stu-id="77298-183">Field name</span></span>|<span data-ttu-id="77298-184">データ型</span><span class="sxs-lookup"><span data-stu-id="77298-184">Data type</span></span>|<span data-ttu-id="77298-185">説明</span><span class="sxs-lookup"><span data-stu-id="77298-185">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77298-186">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="77298-186">AverageThroughput</span></span>|<span data-ttu-id="77298-187">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-187">win:Double</span></span>|<span data-ttu-id="77298-188">計測のサンプルの平均のスループット。</span><span class="sxs-lookup"><span data-stu-id="77298-188">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="77298-189">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="77298-189">NewWorkerThreadCount</span></span>|<span data-ttu-id="77298-190">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77298-190">win:UInt32</span></span>|<span data-ttu-id="77298-191">新しいアクティブなワーカー スレッド数。</span><span class="sxs-lookup"><span data-stu-id="77298-191">New number of active worker threads.</span></span>|  
|<span data-ttu-id="77298-192">理由</span><span class="sxs-lookup"><span data-stu-id="77298-192">Reason</span></span>|<span data-ttu-id="77298-193">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="77298-193">win:UInt32</span></span>|<span data-ttu-id="77298-194">調整の理由。</span><span class="sxs-lookup"><span data-stu-id="77298-194">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="77298-195">0x00 - ウォーム アップ。</span><span class="sxs-lookup"><span data-stu-id="77298-195">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="77298-196">0x01 - 初期化。</span><span class="sxs-lookup"><span data-stu-id="77298-196">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="77298-197">0x02 - ランダムな移動。</span><span class="sxs-lookup"><span data-stu-id="77298-197">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="77298-198">0x03 - 上昇移動。</span><span class="sxs-lookup"><span data-stu-id="77298-198">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="77298-199">0x04 - 変更点。</span><span class="sxs-lookup"><span data-stu-id="77298-199">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="77298-200">0x05 - 安定化。</span><span class="sxs-lookup"><span data-stu-id="77298-200">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="77298-201">0x06 - 不足。</span><span class="sxs-lookup"><span data-stu-id="77298-201">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="77298-202">0x07 - スレッドのタイムアウト。</span><span class="sxs-lookup"><span data-stu-id="77298-202">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="77298-203">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77298-203">ClrInstanceID</span></span>|<span data-ttu-id="77298-204">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77298-204">Win:UInt16</span></span>|<span data-ttu-id="77298-205">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="77298-205">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="77298-206">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="77298-206">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="77298-207">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-207">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77298-208">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="77298-208">Keyword for raising the event</span></span>|<span data-ttu-id="77298-209">Level</span><span class="sxs-lookup"><span data-stu-id="77298-209">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="77298-210">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="77298-210">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="77298-211">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="77298-211">Informational (4)</span></span>|  
  
 <span data-ttu-id="77298-212">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="77298-212">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77298-213">Event</span><span class="sxs-lookup"><span data-stu-id="77298-213">Event</span></span>|<span data-ttu-id="77298-214">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77298-214">Event ID</span></span>|<span data-ttu-id="77298-215">説明</span><span class="sxs-lookup"><span data-stu-id="77298-215">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="77298-216">56</span><span class="sxs-lookup"><span data-stu-id="77298-216">56</span></span>|<span data-ttu-id="77298-217">スレッド プールに関するデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="77298-217">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="77298-218">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-218">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77298-219">フィールド名</span><span class="sxs-lookup"><span data-stu-id="77298-219">Field name</span></span>|<span data-ttu-id="77298-220">データ型</span><span class="sxs-lookup"><span data-stu-id="77298-220">Data type</span></span>|<span data-ttu-id="77298-221">説明</span><span class="sxs-lookup"><span data-stu-id="77298-221">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77298-222">Duration</span><span class="sxs-lookup"><span data-stu-id="77298-222">Duration</span></span>|<span data-ttu-id="77298-223">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-223">win:Double</span></span>|<span data-ttu-id="77298-224">これらの統計情報が収集される時間数 (秒)。</span><span class="sxs-lookup"><span data-stu-id="77298-224">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="77298-225">スループット</span><span class="sxs-lookup"><span data-stu-id="77298-225">Throughput</span></span>|<span data-ttu-id="77298-226">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-226">win:Double</span></span>|<span data-ttu-id="77298-227">この間隔中の 1 秒あたりの入力候補の平均数。</span><span class="sxs-lookup"><span data-stu-id="77298-227">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="77298-228">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="77298-228">ThreadWave</span></span>|<span data-ttu-id="77298-229">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-229">win:Double</span></span>|<span data-ttu-id="77298-230">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="77298-230">Reserved for internal use.</span></span>|  
|<span data-ttu-id="77298-231">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="77298-231">ThroughputWave</span></span>|<span data-ttu-id="77298-232">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-232">win:Double</span></span>|<span data-ttu-id="77298-233">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="77298-233">Reserved for internal use.</span></span>|  
|<span data-ttu-id="77298-234">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="77298-234">ThroughputErrorEstimate</span></span>|<span data-ttu-id="77298-235">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-235">win:Double</span></span>|<span data-ttu-id="77298-236">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="77298-236">Reserved for internal use.</span></span>|  
|<span data-ttu-id="77298-237">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="77298-237">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="77298-238">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-238">win:Double</span></span>|<span data-ttu-id="77298-239">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="77298-239">Reserved for internal use.</span></span>|  
|<span data-ttu-id="77298-240">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="77298-240">ThroughputRatio</span></span>|<span data-ttu-id="77298-241">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-241">win:Double</span></span>|<span data-ttu-id="77298-242">この間隔中にアクティブなワーカー スレッドの数の変動によって引き起こされる、スループットの相対的な向上。</span><span class="sxs-lookup"><span data-stu-id="77298-242">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="77298-243">Confidence</span><span class="sxs-lookup"><span data-stu-id="77298-243">Confidence</span></span>|<span data-ttu-id="77298-244">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-244">win:Double</span></span>|<span data-ttu-id="77298-245">ThroughputRatio フィールドの有効性の測定結果。</span><span class="sxs-lookup"><span data-stu-id="77298-245">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="77298-246">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="77298-246">NewcontrolSetting</span></span>|<span data-ttu-id="77298-247">win:Double</span><span class="sxs-lookup"><span data-stu-id="77298-247">win:Double</span></span>|<span data-ttu-id="77298-248">アクティブなスレッド数の将来のバリエーションのベースラインとして使用するアクティブなワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="77298-248">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="77298-249">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="77298-249">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="77298-250">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77298-250">Win:UInt16</span></span>|<span data-ttu-id="77298-251">アクティブなスレッド数の、将来のバリエーションの大きさを指定します。</span><span class="sxs-lookup"><span data-stu-id="77298-251">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="77298-252">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77298-252">ClrInstanceID</span></span>|<span data-ttu-id="77298-253">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77298-253">Win:UInt16</span></span>|<span data-ttu-id="77298-254">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="77298-254">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="io-thread-events"></a><span data-ttu-id="77298-255">I/O スレッド イベント</span><span class="sxs-lookup"><span data-stu-id="77298-255">I/O Thread Events</span></span>  
 <span data-ttu-id="77298-256">これらのスレッド プール イベントは、I/O スレッド プール (完了ポート) にあるスレッドで発生します。これは非同期です。</span><span class="sxs-lookup"><span data-stu-id="77298-256">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreate_v1"></a><span data-ttu-id="77298-257">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="77298-257">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="77298-258">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-258">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77298-259">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="77298-259">Keyword for raising the event</span></span>|<span data-ttu-id="77298-260">Level</span><span class="sxs-lookup"><span data-stu-id="77298-260">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="77298-261">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="77298-261">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="77298-262">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="77298-262">Informational (4)</span></span>|  
  
 <span data-ttu-id="77298-263">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="77298-263">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77298-264">Event</span><span class="sxs-lookup"><span data-stu-id="77298-264">Event</span></span>|<span data-ttu-id="77298-265">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77298-265">Event ID</span></span>|<span data-ttu-id="77298-266">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="77298-266">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="77298-267">44</span><span class="sxs-lookup"><span data-stu-id="77298-267">44</span></span>|<span data-ttu-id="77298-268">I/O スレッドがスレッド プールに作成された。</span><span class="sxs-lookup"><span data-stu-id="77298-268">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="77298-269">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-269">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77298-270">フィールド名</span><span class="sxs-lookup"><span data-stu-id="77298-270">Field name</span></span>|<span data-ttu-id="77298-271">データ型</span><span class="sxs-lookup"><span data-stu-id="77298-271">Data type</span></span>|<span data-ttu-id="77298-272">説明</span><span class="sxs-lookup"><span data-stu-id="77298-272">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77298-273">Count</span><span class="sxs-lookup"><span data-stu-id="77298-273">Count</span></span>|<span data-ttu-id="77298-274">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77298-274">win:UInt64</span></span>|<span data-ttu-id="77298-275">新しく作成されたスレッドを含む、I/O のスレッドの数です。</span><span class="sxs-lookup"><span data-stu-id="77298-275">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="77298-276">NumRetired</span><span class="sxs-lookup"><span data-stu-id="77298-276">NumRetired</span></span>|<span data-ttu-id="77298-277">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77298-277">win:UInt64</span></span>|<span data-ttu-id="77298-278">提供終了になったワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="77298-278">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="77298-279">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77298-279">ClrInstanceID</span></span>|<span data-ttu-id="77298-280">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77298-280">Win:UInt16</span></span>|<span data-ttu-id="77298-281">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="77298-281">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretire_v1"></a><span data-ttu-id="77298-282">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="77298-282">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="77298-283">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77298-284">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="77298-284">Keyword for raising the event</span></span>|<span data-ttu-id="77298-285">Level</span><span class="sxs-lookup"><span data-stu-id="77298-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="77298-286">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="77298-286">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="77298-287">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="77298-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="77298-288">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="77298-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77298-289">Event</span><span class="sxs-lookup"><span data-stu-id="77298-289">Event</span></span>|<span data-ttu-id="77298-290">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77298-290">Event ID</span></span>|<span data-ttu-id="77298-291">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="77298-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="77298-292">46</span><span class="sxs-lookup"><span data-stu-id="77298-292">46</span></span>|<span data-ttu-id="77298-293">I/O スレッドが、提供終了の候補になる。</span><span class="sxs-lookup"><span data-stu-id="77298-293">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="77298-294">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77298-295">フィールド名</span><span class="sxs-lookup"><span data-stu-id="77298-295">Field name</span></span>|<span data-ttu-id="77298-296">データ型</span><span class="sxs-lookup"><span data-stu-id="77298-296">Data type</span></span>|<span data-ttu-id="77298-297">説明</span><span class="sxs-lookup"><span data-stu-id="77298-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77298-298">Count</span><span class="sxs-lookup"><span data-stu-id="77298-298">Count</span></span>|<span data-ttu-id="77298-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77298-299">win:UInt64</span></span>|<span data-ttu-id="77298-300">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="77298-300">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="77298-301">NumRetired</span><span class="sxs-lookup"><span data-stu-id="77298-301">NumRetired</span></span>|<span data-ttu-id="77298-302">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77298-302">win:UInt64</span></span>|<span data-ttu-id="77298-303">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="77298-303">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="77298-304">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77298-304">ClrInstanceID</span></span>|<span data-ttu-id="77298-305">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77298-305">Win:UInt16</span></span>|<span data-ttu-id="77298-306">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="77298-306">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretire_v1"></a><span data-ttu-id="77298-307">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="77298-307">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="77298-308">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-308">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77298-309">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="77298-309">Keyword for raising the event</span></span>|<span data-ttu-id="77298-310">Level</span><span class="sxs-lookup"><span data-stu-id="77298-310">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="77298-311">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="77298-311">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="77298-312">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="77298-312">Informational (4)</span></span>|  
  
 <span data-ttu-id="77298-313">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="77298-313">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77298-314">Event</span><span class="sxs-lookup"><span data-stu-id="77298-314">Event</span></span>|<span data-ttu-id="77298-315">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77298-315">Event ID</span></span>|<span data-ttu-id="77298-316">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="77298-316">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="77298-317">47</span><span class="sxs-lookup"><span data-stu-id="77298-317">47</span></span>|<span data-ttu-id="77298-318">スレッドが提供終了の候補になってから待機期間内に I/O が到着したため I/O スレッドが提供終了解除された。</span><span class="sxs-lookup"><span data-stu-id="77298-318">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="77298-319">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-319">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77298-320">フィールド名</span><span class="sxs-lookup"><span data-stu-id="77298-320">Field name</span></span>|<span data-ttu-id="77298-321">データ型</span><span class="sxs-lookup"><span data-stu-id="77298-321">Data type</span></span>|<span data-ttu-id="77298-322">説明</span><span class="sxs-lookup"><span data-stu-id="77298-322">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77298-323">Count</span><span class="sxs-lookup"><span data-stu-id="77298-323">Count</span></span>|<span data-ttu-id="77298-324">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77298-324">win:UInt64</span></span>|<span data-ttu-id="77298-325">これを含む、スレッド プール内の I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="77298-325">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="77298-326">NumRetired</span><span class="sxs-lookup"><span data-stu-id="77298-326">NumRetired</span></span>|<span data-ttu-id="77298-327">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77298-327">win:UInt64</span></span>|<span data-ttu-id="77298-328">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="77298-328">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="77298-329">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77298-329">ClrInstanceID</span></span>|<span data-ttu-id="77298-330">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77298-330">Win:UInt16</span></span>|<span data-ttu-id="77298-331">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="77298-331">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="77298-332">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="77298-332">IOThreadTerminate</span></span>  
 <span data-ttu-id="77298-333">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-333">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="77298-334">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="77298-334">Keyword for raising the event</span></span>|<span data-ttu-id="77298-335">Level</span><span class="sxs-lookup"><span data-stu-id="77298-335">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="77298-336">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="77298-336">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="77298-337">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="77298-337">Informational (4)</span></span>|  
  
 <span data-ttu-id="77298-338">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="77298-338">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="77298-339">Event</span><span class="sxs-lookup"><span data-stu-id="77298-339">Event</span></span>|<span data-ttu-id="77298-340">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77298-340">Event ID</span></span>|<span data-ttu-id="77298-341">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="77298-341">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="77298-342">45</span><span class="sxs-lookup"><span data-stu-id="77298-342">45</span></span>|<span data-ttu-id="77298-343">スレッドプールで i/o スレッドが終了します。</span><span class="sxs-lookup"><span data-stu-id="77298-343">An I/O thread is terminated in the thread pool.</span></span>|  
  
 <span data-ttu-id="77298-344">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="77298-344">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="77298-345">フィールド名</span><span class="sxs-lookup"><span data-stu-id="77298-345">Field name</span></span>|<span data-ttu-id="77298-346">データ型</span><span class="sxs-lookup"><span data-stu-id="77298-346">Data type</span></span>|<span data-ttu-id="77298-347">説明</span><span class="sxs-lookup"><span data-stu-id="77298-347">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="77298-348">Count</span><span class="sxs-lookup"><span data-stu-id="77298-348">Count</span></span>|<span data-ttu-id="77298-349">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77298-349">win:UInt64</span></span>|<span data-ttu-id="77298-350">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="77298-350">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="77298-351">NumRetired</span><span class="sxs-lookup"><span data-stu-id="77298-351">NumRetired</span></span>|<span data-ttu-id="77298-352">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="77298-352">win:UInt64</span></span>|<span data-ttu-id="77298-353">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="77298-353">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="77298-354">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="77298-354">ClrInstanceID</span></span>|<span data-ttu-id="77298-355">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="77298-355">Win:UInt16</span></span>|<span data-ttu-id="77298-356">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="77298-356">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77298-357">関連項目</span><span class="sxs-lookup"><span data-stu-id="77298-357">See also</span></span>

- [<span data-ttu-id="77298-358">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="77298-358">CLR ETW Events</span></span>](clr-etw-events.md)
