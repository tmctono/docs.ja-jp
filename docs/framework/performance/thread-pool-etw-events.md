---
title: スレッド プール ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: 249d0607ddd280bcb4e9cf3ef34b28ff8ada3b04
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240494"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="eb949-102">スレッド プール ETW イベント</span><span class="sxs-lookup"><span data-stu-id="eb949-102">Thread Pool ETW Events</span></span>
<span data-ttu-id="eb949-103">これらのイベントは、ワーカー スレッドと I/O スレッドに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="eb949-103">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="eb949-104">スレッド プール イベントには 2 つのグループがあります。</span><span class="sxs-lookup"><span data-stu-id="eb949-104">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="eb949-105">[ワーカー スレッド プール イベント](#worker-thread-pool-events)は、アプリケーションがどのようにスレッド プールを使用するかに関する情報と、コンカレンシー制御におけるワークロードの効果に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb949-105">[Worker thread pool events](#worker-thread-pool-events), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="eb949-106">[I/O スレッド プール イベント](#io-thread-events)は、スレッド プールで作成、無効化、無効化解除、または終了した I/O スレッドに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb949-106">[I/O thread pool events](#io-thread-events), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  

## <a name="worker-thread-pool-events"></a><span data-ttu-id="eb949-107">ワーカー スレッド プール イベント</span><span class="sxs-lookup"><span data-stu-id="eb949-107">Worker Thread Pool Events</span></span>
 <span data-ttu-id="eb949-108">これらのイベントは、ランタイムのワーカー スレッドのプールに関連付けられており、スレッド イベントに関する通知 (スレッドが作成されたり停止されたりした場合など) を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb949-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="eb949-109">ワーカー スレッド プールは、スレッドの数が計測されたスループットに基づいて計算されるアダプティブ アルゴリズムを使用して、コンカレンシー制御を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb949-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="eb949-110">ワーカー スレッド プール イベントを使用すると、アプリケーションで使用されるスレッド プールの様子や特定のワークロードがコンカレンシー制御に与える影響などを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="eb949-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="eb949-111">ThreadPoolWorkerThreadStart および ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="eb949-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="eb949-112">次の表に、これらのイベントのキーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="eb949-113">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="eb949-113">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="eb949-114">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="eb949-114">Keyword for raising the event</span></span>|<span data-ttu-id="eb949-115">Level</span><span class="sxs-lookup"><span data-stu-id="eb949-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb949-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eb949-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eb949-117">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="eb949-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="eb949-118">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb949-119">Event</span><span class="sxs-lookup"><span data-stu-id="eb949-119">Event</span></span>|<span data-ttu-id="eb949-120">イベント ID</span><span class="sxs-lookup"><span data-stu-id="eb949-120">Event ID</span></span>|<span data-ttu-id="eb949-121">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="eb949-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="eb949-122">50</span><span class="sxs-lookup"><span data-stu-id="eb949-122">50</span></span>|<span data-ttu-id="eb949-123">ワーカー スレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="eb949-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="eb949-124">51</span><span class="sxs-lookup"><span data-stu-id="eb949-124">51</span></span>|<span data-ttu-id="eb949-125">ワーカー スレッドが停止された。</span><span class="sxs-lookup"><span data-stu-id="eb949-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="eb949-126">52</span><span class="sxs-lookup"><span data-stu-id="eb949-126">52</span></span>|<span data-ttu-id="eb949-127">ワーカー スレッドが無効にされた。</span><span class="sxs-lookup"><span data-stu-id="eb949-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="eb949-128">53</span><span class="sxs-lookup"><span data-stu-id="eb949-128">53</span></span>|<span data-ttu-id="eb949-129">提供終了になったワーカー スレッドが再びアクティブになった。</span><span class="sxs-lookup"><span data-stu-id="eb949-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="eb949-130">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb949-131">フィールド名</span><span class="sxs-lookup"><span data-stu-id="eb949-131">Field name</span></span>|<span data-ttu-id="eb949-132">データ型</span><span class="sxs-lookup"><span data-stu-id="eb949-132">Data type</span></span>|<span data-ttu-id="eb949-133">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb949-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="eb949-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="eb949-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eb949-135">win:UInt32</span></span>|<span data-ttu-id="eb949-136">作業の処理に使用可能なワーカー スレッド (既に作業の処理中のもの含む) の数。</span><span class="sxs-lookup"><span data-stu-id="eb949-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="eb949-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="eb949-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="eb949-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eb949-138">win:UInt32</span></span>|<span data-ttu-id="eb949-139">作業の処理に使用できないものの、後にさらに多くのスレッドが必要になった場合に備えて予約されているワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="eb949-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="eb949-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb949-140">ClrInstanceID</span></span>|<span data-ttu-id="eb949-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb949-141">Win:UInt16</span></span>|<span data-ttu-id="eb949-142">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="eb949-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="eb949-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="eb949-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="eb949-144">これらのスレッド プール イベントは、スレッドの挿入 (コンカレンシー制御) アルゴリズムの動作を理解したりデバッグしたりするための情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb949-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="eb949-145">この情報は、ワーカー スレッド プールによって内部で使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb949-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="eb949-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="eb949-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="eb949-147">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eb949-148">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="eb949-148">Keyword for raising the event</span></span>|<span data-ttu-id="eb949-149">Level</span><span class="sxs-lookup"><span data-stu-id="eb949-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb949-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eb949-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eb949-151">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="eb949-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="eb949-152">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb949-153">Event</span><span class="sxs-lookup"><span data-stu-id="eb949-153">Event</span></span>|<span data-ttu-id="eb949-154">イベント ID</span><span class="sxs-lookup"><span data-stu-id="eb949-154">Event ID</span></span>|<span data-ttu-id="eb949-155">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="eb949-156">54</span><span class="sxs-lookup"><span data-stu-id="eb949-156">54</span></span>|<span data-ttu-id="eb949-157">1 つのサンプルの情報のコレクションを参照します。つまり、特定のコンカレンシー レベルの特定の時刻におけるスループットの測定値です。</span><span class="sxs-lookup"><span data-stu-id="eb949-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="eb949-158">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb949-159">フィールド名</span><span class="sxs-lookup"><span data-stu-id="eb949-159">Field name</span></span>|<span data-ttu-id="eb949-160">データ型</span><span class="sxs-lookup"><span data-stu-id="eb949-160">Data type</span></span>|<span data-ttu-id="eb949-161">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb949-162">スループット</span><span class="sxs-lookup"><span data-stu-id="eb949-162">Throughput</span></span>|<span data-ttu-id="eb949-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-163">win:Double</span></span>|<span data-ttu-id="eb949-164">時間の単位あたりの入力候補の数です。</span><span class="sxs-lookup"><span data-stu-id="eb949-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="eb949-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb949-165">ClrInstanceID</span></span>|<span data-ttu-id="eb949-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb949-166">Win:UInt16</span></span>|<span data-ttu-id="eb949-167">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="eb949-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="eb949-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="eb949-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="eb949-169">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eb949-170">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="eb949-170">Keyword for raising the event</span></span>|<span data-ttu-id="eb949-171">Level</span><span class="sxs-lookup"><span data-stu-id="eb949-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb949-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eb949-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eb949-173">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="eb949-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="eb949-174">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb949-175">Event</span><span class="sxs-lookup"><span data-stu-id="eb949-175">Event</span></span>|<span data-ttu-id="eb949-176">イベント ID</span><span class="sxs-lookup"><span data-stu-id="eb949-176">Event ID</span></span>|<span data-ttu-id="eb949-177">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="eb949-178">55</span><span class="sxs-lookup"><span data-stu-id="eb949-178">55</span></span>|<span data-ttu-id="eb949-179">スレッドの挿入 (山登り法) アルゴリズムが、コンカレンシー レベルに変更があったと判断した場合に、コントロールの変更を記録します。</span><span class="sxs-lookup"><span data-stu-id="eb949-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="eb949-180">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb949-181">フィールド名</span><span class="sxs-lookup"><span data-stu-id="eb949-181">Field name</span></span>|<span data-ttu-id="eb949-182">データ型</span><span class="sxs-lookup"><span data-stu-id="eb949-182">Data type</span></span>|<span data-ttu-id="eb949-183">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb949-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="eb949-184">AverageThroughput</span></span>|<span data-ttu-id="eb949-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-185">win:Double</span></span>|<span data-ttu-id="eb949-186">計測のサンプルの平均のスループット。</span><span class="sxs-lookup"><span data-stu-id="eb949-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="eb949-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="eb949-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="eb949-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eb949-188">win:UInt32</span></span>|<span data-ttu-id="eb949-189">新しいアクティブなワーカー スレッド数。</span><span class="sxs-lookup"><span data-stu-id="eb949-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="eb949-190">理由</span><span class="sxs-lookup"><span data-stu-id="eb949-190">Reason</span></span>|<span data-ttu-id="eb949-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eb949-191">win:UInt32</span></span>|<span data-ttu-id="eb949-192">調整の理由。</span><span class="sxs-lookup"><span data-stu-id="eb949-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="eb949-193">0x00 - ウォーム アップ。</span><span class="sxs-lookup"><span data-stu-id="eb949-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="eb949-194">0x01 - 初期化。</span><span class="sxs-lookup"><span data-stu-id="eb949-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="eb949-195">0x02 - ランダムな移動。</span><span class="sxs-lookup"><span data-stu-id="eb949-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="eb949-196">0x03 - 上昇移動。</span><span class="sxs-lookup"><span data-stu-id="eb949-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="eb949-197">0x04 - 変更点。</span><span class="sxs-lookup"><span data-stu-id="eb949-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="eb949-198">0x05 - 安定化。</span><span class="sxs-lookup"><span data-stu-id="eb949-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="eb949-199">0x06 - 不足。</span><span class="sxs-lookup"><span data-stu-id="eb949-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="eb949-200">0x07 - スレッドのタイムアウト。</span><span class="sxs-lookup"><span data-stu-id="eb949-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="eb949-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb949-201">ClrInstanceID</span></span>|<span data-ttu-id="eb949-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb949-202">Win:UInt16</span></span>|<span data-ttu-id="eb949-203">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="eb949-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="eb949-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="eb949-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="eb949-205">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eb949-206">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="eb949-206">Keyword for raising the event</span></span>|<span data-ttu-id="eb949-207">Level</span><span class="sxs-lookup"><span data-stu-id="eb949-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb949-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eb949-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eb949-209">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="eb949-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="eb949-210">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb949-211">Event</span><span class="sxs-lookup"><span data-stu-id="eb949-211">Event</span></span>|<span data-ttu-id="eb949-212">イベント ID</span><span class="sxs-lookup"><span data-stu-id="eb949-212">Event ID</span></span>|<span data-ttu-id="eb949-213">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="eb949-214">56</span><span class="sxs-lookup"><span data-stu-id="eb949-214">56</span></span>|<span data-ttu-id="eb949-215">スレッド プールに関するデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="eb949-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="eb949-216">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb949-217">フィールド名</span><span class="sxs-lookup"><span data-stu-id="eb949-217">Field name</span></span>|<span data-ttu-id="eb949-218">データ型</span><span class="sxs-lookup"><span data-stu-id="eb949-218">Data type</span></span>|<span data-ttu-id="eb949-219">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb949-220">Duration</span><span class="sxs-lookup"><span data-stu-id="eb949-220">Duration</span></span>|<span data-ttu-id="eb949-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-221">win:Double</span></span>|<span data-ttu-id="eb949-222">これらの統計情報が収集される時間数 (秒)。</span><span class="sxs-lookup"><span data-stu-id="eb949-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="eb949-223">スループット</span><span class="sxs-lookup"><span data-stu-id="eb949-223">Throughput</span></span>|<span data-ttu-id="eb949-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-224">win:Double</span></span>|<span data-ttu-id="eb949-225">この間隔中の 1 秒あたりの入力候補の平均数。</span><span class="sxs-lookup"><span data-stu-id="eb949-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="eb949-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="eb949-226">ThreadWave</span></span>|<span data-ttu-id="eb949-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-227">win:Double</span></span>|<span data-ttu-id="eb949-228">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="eb949-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="eb949-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="eb949-229">ThroughputWave</span></span>|<span data-ttu-id="eb949-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-230">win:Double</span></span>|<span data-ttu-id="eb949-231">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="eb949-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="eb949-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="eb949-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="eb949-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-233">win:Double</span></span>|<span data-ttu-id="eb949-234">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="eb949-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="eb949-235">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="eb949-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="eb949-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-236">win:Double</span></span>|<span data-ttu-id="eb949-237">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="eb949-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="eb949-238">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="eb949-238">ThroughputRatio</span></span>|<span data-ttu-id="eb949-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-239">win:Double</span></span>|<span data-ttu-id="eb949-240">この間隔中にアクティブなワーカー スレッドの数の変動によって引き起こされる、スループットの相対的な向上。</span><span class="sxs-lookup"><span data-stu-id="eb949-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="eb949-241">Confidence</span><span class="sxs-lookup"><span data-stu-id="eb949-241">Confidence</span></span>|<span data-ttu-id="eb949-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-242">win:Double</span></span>|<span data-ttu-id="eb949-243">ThroughputRatio フィールドの有効性の測定結果。</span><span class="sxs-lookup"><span data-stu-id="eb949-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="eb949-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="eb949-244">NewcontrolSetting</span></span>|<span data-ttu-id="eb949-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="eb949-245">win:Double</span></span>|<span data-ttu-id="eb949-246">アクティブなスレッド数の将来のバリエーションのベースラインとして使用するアクティブなワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="eb949-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="eb949-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="eb949-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="eb949-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb949-248">Win:UInt16</span></span>|<span data-ttu-id="eb949-249">アクティブなスレッド数の、将来のバリエーションの大きさを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb949-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="eb949-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb949-250">ClrInstanceID</span></span>|<span data-ttu-id="eb949-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb949-251">Win:UInt16</span></span>|<span data-ttu-id="eb949-252">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="eb949-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="io-thread-events"></a><span data-ttu-id="eb949-253">I/O スレッド イベント</span><span class="sxs-lookup"><span data-stu-id="eb949-253">I/O Thread Events</span></span>  
 <span data-ttu-id="eb949-254">これらのスレッド プール イベントは、I/O スレッド プール (完了ポート) にあるスレッドで発生します。これは非同期です。</span><span class="sxs-lookup"><span data-stu-id="eb949-254">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreate_v1"></a><span data-ttu-id="eb949-255">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="eb949-255">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="eb949-256">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-256">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eb949-257">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="eb949-257">Keyword for raising the event</span></span>|<span data-ttu-id="eb949-258">Level</span><span class="sxs-lookup"><span data-stu-id="eb949-258">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb949-259">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eb949-259">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eb949-260">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="eb949-260">Informational (4)</span></span>|  
  
 <span data-ttu-id="eb949-261">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-261">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb949-262">Event</span><span class="sxs-lookup"><span data-stu-id="eb949-262">Event</span></span>|<span data-ttu-id="eb949-263">イベント ID</span><span class="sxs-lookup"><span data-stu-id="eb949-263">Event ID</span></span>|<span data-ttu-id="eb949-264">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="eb949-264">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="eb949-265">44</span><span class="sxs-lookup"><span data-stu-id="eb949-265">44</span></span>|<span data-ttu-id="eb949-266">I/O スレッドがスレッド プールに作成された。</span><span class="sxs-lookup"><span data-stu-id="eb949-266">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="eb949-267">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-267">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb949-268">フィールド名</span><span class="sxs-lookup"><span data-stu-id="eb949-268">Field name</span></span>|<span data-ttu-id="eb949-269">データ型</span><span class="sxs-lookup"><span data-stu-id="eb949-269">Data type</span></span>|<span data-ttu-id="eb949-270">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-270">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb949-271">Count</span><span class="sxs-lookup"><span data-stu-id="eb949-271">Count</span></span>|<span data-ttu-id="eb949-272">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eb949-272">win:UInt64</span></span>|<span data-ttu-id="eb949-273">新しく作成されたスレッドを含む、I/O のスレッドの数です。</span><span class="sxs-lookup"><span data-stu-id="eb949-273">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="eb949-274">NumRetired</span><span class="sxs-lookup"><span data-stu-id="eb949-274">NumRetired</span></span>|<span data-ttu-id="eb949-275">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eb949-275">win:UInt64</span></span>|<span data-ttu-id="eb949-276">提供終了になったワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="eb949-276">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="eb949-277">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb949-277">ClrInstanceID</span></span>|<span data-ttu-id="eb949-278">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb949-278">Win:UInt16</span></span>|<span data-ttu-id="eb949-279">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="eb949-279">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretire_v1"></a><span data-ttu-id="eb949-280">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="eb949-280">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="eb949-281">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-281">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eb949-282">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="eb949-282">Keyword for raising the event</span></span>|<span data-ttu-id="eb949-283">Level</span><span class="sxs-lookup"><span data-stu-id="eb949-283">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb949-284">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eb949-284">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eb949-285">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="eb949-285">Informational (4)</span></span>|  
  
 <span data-ttu-id="eb949-286">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-286">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb949-287">Event</span><span class="sxs-lookup"><span data-stu-id="eb949-287">Event</span></span>|<span data-ttu-id="eb949-288">イベント ID</span><span class="sxs-lookup"><span data-stu-id="eb949-288">Event ID</span></span>|<span data-ttu-id="eb949-289">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="eb949-289">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="eb949-290">46</span><span class="sxs-lookup"><span data-stu-id="eb949-290">46</span></span>|<span data-ttu-id="eb949-291">I/O スレッドが、提供終了の候補になる。</span><span class="sxs-lookup"><span data-stu-id="eb949-291">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="eb949-292">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-292">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb949-293">フィールド名</span><span class="sxs-lookup"><span data-stu-id="eb949-293">Field name</span></span>|<span data-ttu-id="eb949-294">データ型</span><span class="sxs-lookup"><span data-stu-id="eb949-294">Data type</span></span>|<span data-ttu-id="eb949-295">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-295">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb949-296">Count</span><span class="sxs-lookup"><span data-stu-id="eb949-296">Count</span></span>|<span data-ttu-id="eb949-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eb949-297">win:UInt64</span></span>|<span data-ttu-id="eb949-298">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="eb949-298">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="eb949-299">NumRetired</span><span class="sxs-lookup"><span data-stu-id="eb949-299">NumRetired</span></span>|<span data-ttu-id="eb949-300">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eb949-300">win:UInt64</span></span>|<span data-ttu-id="eb949-301">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="eb949-301">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="eb949-302">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb949-302">ClrInstanceID</span></span>|<span data-ttu-id="eb949-303">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb949-303">Win:UInt16</span></span>|<span data-ttu-id="eb949-304">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="eb949-304">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretire_v1"></a><span data-ttu-id="eb949-305">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="eb949-305">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="eb949-306">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eb949-307">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="eb949-307">Keyword for raising the event</span></span>|<span data-ttu-id="eb949-308">Level</span><span class="sxs-lookup"><span data-stu-id="eb949-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb949-309">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eb949-309">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eb949-310">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="eb949-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="eb949-311">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb949-312">Event</span><span class="sxs-lookup"><span data-stu-id="eb949-312">Event</span></span>|<span data-ttu-id="eb949-313">イベント ID</span><span class="sxs-lookup"><span data-stu-id="eb949-313">Event ID</span></span>|<span data-ttu-id="eb949-314">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="eb949-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="eb949-315">47</span><span class="sxs-lookup"><span data-stu-id="eb949-315">47</span></span>|<span data-ttu-id="eb949-316">スレッドが提供終了の候補になってから待機期間内に I/O が到着したため I/O スレッドが提供終了解除された。</span><span class="sxs-lookup"><span data-stu-id="eb949-316">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="eb949-317">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-317">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb949-318">フィールド名</span><span class="sxs-lookup"><span data-stu-id="eb949-318">Field name</span></span>|<span data-ttu-id="eb949-319">データ型</span><span class="sxs-lookup"><span data-stu-id="eb949-319">Data type</span></span>|<span data-ttu-id="eb949-320">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-320">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb949-321">Count</span><span class="sxs-lookup"><span data-stu-id="eb949-321">Count</span></span>|<span data-ttu-id="eb949-322">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eb949-322">win:UInt64</span></span>|<span data-ttu-id="eb949-323">これを含む、スレッド プール内の I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="eb949-323">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="eb949-324">NumRetired</span><span class="sxs-lookup"><span data-stu-id="eb949-324">NumRetired</span></span>|<span data-ttu-id="eb949-325">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eb949-325">win:UInt64</span></span>|<span data-ttu-id="eb949-326">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="eb949-326">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="eb949-327">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb949-327">ClrInstanceID</span></span>|<span data-ttu-id="eb949-328">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb949-328">Win:UInt16</span></span>|<span data-ttu-id="eb949-329">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="eb949-329">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="eb949-330">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="eb949-330">IOThreadTerminate</span></span>  
 <span data-ttu-id="eb949-331">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-331">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eb949-332">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="eb949-332">Keyword for raising the event</span></span>|<span data-ttu-id="eb949-333">Level</span><span class="sxs-lookup"><span data-stu-id="eb949-333">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb949-334">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="eb949-334">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="eb949-335">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="eb949-335">Informational (4)</span></span>|  
  
 <span data-ttu-id="eb949-336">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-336">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb949-337">Event</span><span class="sxs-lookup"><span data-stu-id="eb949-337">Event</span></span>|<span data-ttu-id="eb949-338">イベント ID</span><span class="sxs-lookup"><span data-stu-id="eb949-338">Event ID</span></span>|<span data-ttu-id="eb949-339">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="eb949-339">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="eb949-340">45</span><span class="sxs-lookup"><span data-stu-id="eb949-340">45</span></span>|<span data-ttu-id="eb949-341">スレッドプールで i/o スレッドが終了します。</span><span class="sxs-lookup"><span data-stu-id="eb949-341">An I/O thread is terminated in the thread pool.</span></span>|  
  
 <span data-ttu-id="eb949-342">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="eb949-342">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb949-343">フィールド名</span><span class="sxs-lookup"><span data-stu-id="eb949-343">Field name</span></span>|<span data-ttu-id="eb949-344">データ型</span><span class="sxs-lookup"><span data-stu-id="eb949-344">Data type</span></span>|<span data-ttu-id="eb949-345">Description</span><span class="sxs-lookup"><span data-stu-id="eb949-345">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb949-346">Count</span><span class="sxs-lookup"><span data-stu-id="eb949-346">Count</span></span>|<span data-ttu-id="eb949-347">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eb949-347">win:UInt64</span></span>|<span data-ttu-id="eb949-348">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="eb949-348">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="eb949-349">NumRetired</span><span class="sxs-lookup"><span data-stu-id="eb949-349">NumRetired</span></span>|<span data-ttu-id="eb949-350">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="eb949-350">win:UInt64</span></span>|<span data-ttu-id="eb949-351">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="eb949-351">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="eb949-352">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb949-352">ClrInstanceID</span></span>|<span data-ttu-id="eb949-353">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb949-353">Win:UInt16</span></span>|<span data-ttu-id="eb949-354">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="eb949-354">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb949-355">参照</span><span class="sxs-lookup"><span data-stu-id="eb949-355">See also</span></span>

- [<span data-ttu-id="eb949-356">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="eb949-356">CLR ETW Events</span></span>](clr-etw-events.md)
