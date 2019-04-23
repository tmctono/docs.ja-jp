---
title: スレッド プール ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: caacee591c4df8389cea241916618f50da56b22b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119133"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="e7364-102">スレッド プール ETW イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-102">Thread Pool ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="e7364-103">これらのイベントは、ワーカー スレッドと I/O スレッドに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="e7364-103">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="e7364-104">スレッド プール イベントには 2 つのグループがあります。</span><span class="sxs-lookup"><span data-stu-id="e7364-104">There are two groups of thread pool events:</span></span>  
  
-   <span data-ttu-id="e7364-105">[ワーカー スレッド プール イベント](#worker)は、アプリケーションがどのようにスレッド プールを使用するかに関する情報と、コンカレンシー制御におけるワークロードの効果に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e7364-105">[Worker thread pool events](#worker), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
-   <span data-ttu-id="e7364-106">[I/O スレッド プール イベント](#io)は、スレッド プールで作成、無効化、無効化解除、または終了した I/O スレッドに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e7364-106">[I/O thread pool events](#io), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  
  
<a name="worker"></a>   
## <a name="worker-thread-pool-events"></a><span data-ttu-id="e7364-107">ワーカー スレッド プール イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-107">Worker Thread Pool Events</span></span>  
 <span data-ttu-id="e7364-108">これらのイベントは、ランタイムのワーカー スレッドのプールに関連付けられており、スレッド イベントに関する通知 (スレッドが作成されたり停止されたりした場合など) を提供します。</span><span class="sxs-lookup"><span data-stu-id="e7364-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="e7364-109">ワーカー スレッド プールは、スレッドの数が計測されたスループットに基づいて計算されるアダプティブ アルゴリズムを使用して、コンカレンシー制御を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7364-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="e7364-110">ワーカー スレッド プール イベントを使用すると、アプリケーションで使用されるスレッド プールの様子や特定のワークロードがコンカレンシー制御に与える影響などを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="e7364-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="e7364-111">ThreadPoolWorkerThreadStart および ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="e7364-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="e7364-112">次の表に、これらのイベントのキーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="e7364-113">(詳細については、「 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e7364-113">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="e7364-114">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e7364-114">Keyword for raising the event</span></span>|<span data-ttu-id="e7364-115">レベル</span><span class="sxs-lookup"><span data-stu-id="e7364-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e7364-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e7364-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e7364-117">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="e7364-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="e7364-118">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e7364-119">イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-119">Event</span></span>|<span data-ttu-id="e7364-120">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7364-120">Event ID</span></span>|<span data-ttu-id="e7364-121">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e7364-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="e7364-122">50</span><span class="sxs-lookup"><span data-stu-id="e7364-122">50</span></span>|<span data-ttu-id="e7364-123">ワーカー スレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="e7364-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="e7364-124">51</span><span class="sxs-lookup"><span data-stu-id="e7364-124">51</span></span>|<span data-ttu-id="e7364-125">ワーカー スレッドが停止された。</span><span class="sxs-lookup"><span data-stu-id="e7364-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="e7364-126">52</span><span class="sxs-lookup"><span data-stu-id="e7364-126">52</span></span>|<span data-ttu-id="e7364-127">ワーカー スレッドが無効にされた。</span><span class="sxs-lookup"><span data-stu-id="e7364-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="e7364-128">53</span><span class="sxs-lookup"><span data-stu-id="e7364-128">53</span></span>|<span data-ttu-id="e7364-129">提供終了になったワーカー スレッドが再びアクティブになった。</span><span class="sxs-lookup"><span data-stu-id="e7364-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="e7364-130">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e7364-131">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e7364-131">Field name</span></span>|<span data-ttu-id="e7364-132">データ型</span><span class="sxs-lookup"><span data-stu-id="e7364-132">Data type</span></span>|<span data-ttu-id="e7364-133">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e7364-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="e7364-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="e7364-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e7364-135">win:UInt32</span></span>|<span data-ttu-id="e7364-136">作業の処理に使用可能なワーカー スレッド (既に作業の処理中のもの含む) の数。</span><span class="sxs-lookup"><span data-stu-id="e7364-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="e7364-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="e7364-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="e7364-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e7364-138">win:UInt32</span></span>|<span data-ttu-id="e7364-139">作業の処理に使用できないものの、後にさらに多くのスレッドが必要になった場合に備えて予約されているワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="e7364-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="e7364-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e7364-140">ClrInstanceID</span></span>|<span data-ttu-id="e7364-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e7364-141">Win:UInt16</span></span>|<span data-ttu-id="e7364-142">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e7364-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="e7364-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="e7364-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="e7364-144">これらのスレッド プール イベントは、スレッドの挿入 (コンカレンシー制御) アルゴリズムの動作を理解したりデバッグしたりするための情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e7364-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="e7364-145">この情報は、ワーカー スレッド プールによって内部で使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7364-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="e7364-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="e7364-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="e7364-147">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e7364-148">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e7364-148">Keyword for raising the event</span></span>|<span data-ttu-id="e7364-149">レベル</span><span class="sxs-lookup"><span data-stu-id="e7364-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e7364-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e7364-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e7364-151">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="e7364-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="e7364-152">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e7364-153">イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-153">Event</span></span>|<span data-ttu-id="e7364-154">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7364-154">Event ID</span></span>|<span data-ttu-id="e7364-155">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="e7364-156">54</span><span class="sxs-lookup"><span data-stu-id="e7364-156">54</span></span>|<span data-ttu-id="e7364-157">1 つのサンプルの情報のコレクションを参照します。つまり、特定のコンカレンシー レベルの特定の時刻におけるスループットの測定値です。</span><span class="sxs-lookup"><span data-stu-id="e7364-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="e7364-158">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e7364-159">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e7364-159">Field name</span></span>|<span data-ttu-id="e7364-160">データ型</span><span class="sxs-lookup"><span data-stu-id="e7364-160">Data type</span></span>|<span data-ttu-id="e7364-161">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e7364-162">スループット</span><span class="sxs-lookup"><span data-stu-id="e7364-162">Throughput</span></span>|<span data-ttu-id="e7364-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-163">win:Double</span></span>|<span data-ttu-id="e7364-164">時間の単位あたりの入力候補の数です。</span><span class="sxs-lookup"><span data-stu-id="e7364-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="e7364-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e7364-165">ClrInstanceID</span></span>|<span data-ttu-id="e7364-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e7364-166">Win:UInt16</span></span>|<span data-ttu-id="e7364-167">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e7364-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="e7364-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="e7364-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="e7364-169">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e7364-170">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e7364-170">Keyword for raising the event</span></span>|<span data-ttu-id="e7364-171">レベル</span><span class="sxs-lookup"><span data-stu-id="e7364-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e7364-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e7364-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e7364-173">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="e7364-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="e7364-174">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e7364-175">イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-175">Event</span></span>|<span data-ttu-id="e7364-176">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7364-176">Event ID</span></span>|<span data-ttu-id="e7364-177">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="e7364-178">55</span><span class="sxs-lookup"><span data-stu-id="e7364-178">55</span></span>|<span data-ttu-id="e7364-179">スレッドの挿入 (山登り法) アルゴリズムが、コンカレンシー レベルに変更があったと判断した場合に、コントロールの変更を記録します。</span><span class="sxs-lookup"><span data-stu-id="e7364-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="e7364-180">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e7364-181">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e7364-181">Field name</span></span>|<span data-ttu-id="e7364-182">データ型</span><span class="sxs-lookup"><span data-stu-id="e7364-182">Data type</span></span>|<span data-ttu-id="e7364-183">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e7364-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="e7364-184">AverageThroughput</span></span>|<span data-ttu-id="e7364-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-185">win:Double</span></span>|<span data-ttu-id="e7364-186">計測のサンプルの平均のスループット。</span><span class="sxs-lookup"><span data-stu-id="e7364-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="e7364-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="e7364-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="e7364-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e7364-188">win:UInt32</span></span>|<span data-ttu-id="e7364-189">新しいアクティブなワーカー スレッド数。</span><span class="sxs-lookup"><span data-stu-id="e7364-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="e7364-190">理由</span><span class="sxs-lookup"><span data-stu-id="e7364-190">Reason</span></span>|<span data-ttu-id="e7364-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e7364-191">win:UInt32</span></span>|<span data-ttu-id="e7364-192">調整の理由。</span><span class="sxs-lookup"><span data-stu-id="e7364-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="e7364-193">0x00 - ウォーム アップ。</span><span class="sxs-lookup"><span data-stu-id="e7364-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="e7364-194">0x01 - 初期化。</span><span class="sxs-lookup"><span data-stu-id="e7364-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="e7364-195">0x02 - ランダムな移動。</span><span class="sxs-lookup"><span data-stu-id="e7364-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="e7364-196">0x03 - 上昇移動。</span><span class="sxs-lookup"><span data-stu-id="e7364-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="e7364-197">0x04 - 変更点。</span><span class="sxs-lookup"><span data-stu-id="e7364-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="e7364-198">0x05 - 安定化。</span><span class="sxs-lookup"><span data-stu-id="e7364-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="e7364-199">0x06 - 不足。</span><span class="sxs-lookup"><span data-stu-id="e7364-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="e7364-200">0x07 - スレッドのタイムアウト。</span><span class="sxs-lookup"><span data-stu-id="e7364-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="e7364-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e7364-201">ClrInstanceID</span></span>|<span data-ttu-id="e7364-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e7364-202">Win:UInt16</span></span>|<span data-ttu-id="e7364-203">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e7364-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="e7364-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="e7364-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="e7364-205">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e7364-206">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e7364-206">Keyword for raising the event</span></span>|<span data-ttu-id="e7364-207">レベル</span><span class="sxs-lookup"><span data-stu-id="e7364-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e7364-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e7364-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e7364-209">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="e7364-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="e7364-210">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e7364-211">イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-211">Event</span></span>|<span data-ttu-id="e7364-212">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7364-212">Event ID</span></span>|<span data-ttu-id="e7364-213">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="e7364-214">56</span><span class="sxs-lookup"><span data-stu-id="e7364-214">56</span></span>|<span data-ttu-id="e7364-215">スレッド プールに関するデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="e7364-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="e7364-216">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e7364-217">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e7364-217">Field name</span></span>|<span data-ttu-id="e7364-218">データ型</span><span class="sxs-lookup"><span data-stu-id="e7364-218">Data type</span></span>|<span data-ttu-id="e7364-219">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e7364-220">期間</span><span class="sxs-lookup"><span data-stu-id="e7364-220">Duration</span></span>|<span data-ttu-id="e7364-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-221">win:Double</span></span>|<span data-ttu-id="e7364-222">これらの統計情報が収集される時間数 (秒)。</span><span class="sxs-lookup"><span data-stu-id="e7364-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="e7364-223">スループット</span><span class="sxs-lookup"><span data-stu-id="e7364-223">Throughput</span></span>|<span data-ttu-id="e7364-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-224">win:Double</span></span>|<span data-ttu-id="e7364-225">この間隔中の 1 秒あたりの入力候補の平均数。</span><span class="sxs-lookup"><span data-stu-id="e7364-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="e7364-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="e7364-226">ThreadWave</span></span>|<span data-ttu-id="e7364-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-227">win:Double</span></span>|<span data-ttu-id="e7364-228">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="e7364-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="e7364-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="e7364-229">ThroughputWave</span></span>|<span data-ttu-id="e7364-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-230">win:Double</span></span>|<span data-ttu-id="e7364-231">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="e7364-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="e7364-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="e7364-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="e7364-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-233">win:Double</span></span>|<span data-ttu-id="e7364-234">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="e7364-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="e7364-235">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="e7364-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="e7364-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-236">win:Double</span></span>|<span data-ttu-id="e7364-237">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="e7364-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="e7364-238">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="e7364-238">ThroughputRatio</span></span>|<span data-ttu-id="e7364-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-239">win:Double</span></span>|<span data-ttu-id="e7364-240">この間隔中にアクティブなワーカー スレッドの数の変動によって引き起こされる、スループットの相対的な向上。</span><span class="sxs-lookup"><span data-stu-id="e7364-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="e7364-241">信頼度</span><span class="sxs-lookup"><span data-stu-id="e7364-241">Confidence</span></span>|<span data-ttu-id="e7364-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-242">win:Double</span></span>|<span data-ttu-id="e7364-243">ThroughputRatio フィールドの有効性の測定結果。</span><span class="sxs-lookup"><span data-stu-id="e7364-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="e7364-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="e7364-244">NewcontrolSetting</span></span>|<span data-ttu-id="e7364-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="e7364-245">win:Double</span></span>|<span data-ttu-id="e7364-246">アクティブなスレッド数の将来のバリエーションのベースラインとして使用するアクティブなワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="e7364-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="e7364-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="e7364-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="e7364-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e7364-248">Win:UInt16</span></span>|<span data-ttu-id="e7364-249">アクティブなスレッド数の、将来のバリエーションの大きさを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7364-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="e7364-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e7364-250">ClrInstanceID</span></span>|<span data-ttu-id="e7364-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e7364-251">Win:UInt16</span></span>|<span data-ttu-id="e7364-252">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e7364-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e7364-253">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="e7364-253">Back to top</span></span>](#top)  
  
<a name="io"></a>   
## <a name="io-thread-events"></a><span data-ttu-id="e7364-254">I/O スレッド イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-254">I/O Thread Events</span></span>  
 <span data-ttu-id="e7364-255">これらのスレッド プール イベントは、I/O スレッド プール (完了ポート) にあるスレッドで発生します。これは非同期です。</span><span class="sxs-lookup"><span data-stu-id="e7364-255">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreatev1"></a><span data-ttu-id="e7364-256">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="e7364-256">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="e7364-257">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-257">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e7364-258">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e7364-258">Keyword for raising the event</span></span>|<span data-ttu-id="e7364-259">レベル</span><span class="sxs-lookup"><span data-stu-id="e7364-259">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e7364-260">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e7364-260">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e7364-261">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="e7364-261">Informational (4)</span></span>|  
  
 <span data-ttu-id="e7364-262">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-262">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e7364-263">イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-263">Event</span></span>|<span data-ttu-id="e7364-264">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7364-264">Event ID</span></span>|<span data-ttu-id="e7364-265">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e7364-265">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="e7364-266">44</span><span class="sxs-lookup"><span data-stu-id="e7364-266">44</span></span>|<span data-ttu-id="e7364-267">I/O スレッドがスレッド プールに作成された。</span><span class="sxs-lookup"><span data-stu-id="e7364-267">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="e7364-268">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-268">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e7364-269">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e7364-269">Field name</span></span>|<span data-ttu-id="e7364-270">データ型</span><span class="sxs-lookup"><span data-stu-id="e7364-270">Data type</span></span>|<span data-ttu-id="e7364-271">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-271">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e7364-272">カウント</span><span class="sxs-lookup"><span data-stu-id="e7364-272">Count</span></span>|<span data-ttu-id="e7364-273">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e7364-273">win:UInt64</span></span>|<span data-ttu-id="e7364-274">新しく作成されたスレッドを含む、I/O のスレッドの数です。</span><span class="sxs-lookup"><span data-stu-id="e7364-274">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="e7364-275">NumRetired</span><span class="sxs-lookup"><span data-stu-id="e7364-275">NumRetired</span></span>|<span data-ttu-id="e7364-276">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e7364-276">win:UInt64</span></span>|<span data-ttu-id="e7364-277">提供終了になったワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="e7364-277">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="e7364-278">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e7364-278">ClrInstanceID</span></span>|<span data-ttu-id="e7364-279">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e7364-279">Win:UInt16</span></span>|<span data-ttu-id="e7364-280">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e7364-280">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretirev1"></a><span data-ttu-id="e7364-281">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="e7364-281">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="e7364-282">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-282">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e7364-283">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e7364-283">Keyword for raising the event</span></span>|<span data-ttu-id="e7364-284">レベル</span><span class="sxs-lookup"><span data-stu-id="e7364-284">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e7364-285">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e7364-285">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e7364-286">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="e7364-286">Informational (4)</span></span>|  
  
 <span data-ttu-id="e7364-287">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-287">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e7364-288">イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-288">Event</span></span>|<span data-ttu-id="e7364-289">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7364-289">Event ID</span></span>|<span data-ttu-id="e7364-290">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e7364-290">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="e7364-291">46</span><span class="sxs-lookup"><span data-stu-id="e7364-291">46</span></span>|<span data-ttu-id="e7364-292">I/O スレッドが、提供終了の候補になる。</span><span class="sxs-lookup"><span data-stu-id="e7364-292">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="e7364-293">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-293">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e7364-294">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e7364-294">Field name</span></span>|<span data-ttu-id="e7364-295">データ型</span><span class="sxs-lookup"><span data-stu-id="e7364-295">Data type</span></span>|<span data-ttu-id="e7364-296">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-296">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e7364-297">カウント</span><span class="sxs-lookup"><span data-stu-id="e7364-297">Count</span></span>|<span data-ttu-id="e7364-298">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e7364-298">win:UInt64</span></span>|<span data-ttu-id="e7364-299">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="e7364-299">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="e7364-300">NumRetired</span><span class="sxs-lookup"><span data-stu-id="e7364-300">NumRetired</span></span>|<span data-ttu-id="e7364-301">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e7364-301">win:UInt64</span></span>|<span data-ttu-id="e7364-302">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="e7364-302">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="e7364-303">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e7364-303">ClrInstanceID</span></span>|<span data-ttu-id="e7364-304">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e7364-304">Win:UInt16</span></span>|<span data-ttu-id="e7364-305">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e7364-305">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretirev1"></a><span data-ttu-id="e7364-306">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="e7364-306">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="e7364-307">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-307">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e7364-308">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e7364-308">Keyword for raising the event</span></span>|<span data-ttu-id="e7364-309">レベル</span><span class="sxs-lookup"><span data-stu-id="e7364-309">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e7364-310">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e7364-310">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e7364-311">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="e7364-311">Informational (4)</span></span>|  
  
 <span data-ttu-id="e7364-312">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-312">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e7364-313">イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-313">Event</span></span>|<span data-ttu-id="e7364-314">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7364-314">Event ID</span></span>|<span data-ttu-id="e7364-315">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e7364-315">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="e7364-316">47</span><span class="sxs-lookup"><span data-stu-id="e7364-316">47</span></span>|<span data-ttu-id="e7364-317">スレッドが提供終了の候補になってから待機期間内に I/O が到着したため I/O スレッドが提供終了解除された。</span><span class="sxs-lookup"><span data-stu-id="e7364-317">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="e7364-318">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-318">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e7364-319">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e7364-319">Field name</span></span>|<span data-ttu-id="e7364-320">データ型</span><span class="sxs-lookup"><span data-stu-id="e7364-320">Data type</span></span>|<span data-ttu-id="e7364-321">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-321">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e7364-322">カウント</span><span class="sxs-lookup"><span data-stu-id="e7364-322">Count</span></span>|<span data-ttu-id="e7364-323">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e7364-323">win:UInt64</span></span>|<span data-ttu-id="e7364-324">これを含む、スレッド プール内の I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="e7364-324">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="e7364-325">NumRetired</span><span class="sxs-lookup"><span data-stu-id="e7364-325">NumRetired</span></span>|<span data-ttu-id="e7364-326">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e7364-326">win:UInt64</span></span>|<span data-ttu-id="e7364-327">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="e7364-327">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="e7364-328">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e7364-328">ClrInstanceID</span></span>|<span data-ttu-id="e7364-329">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e7364-329">Win:UInt16</span></span>|<span data-ttu-id="e7364-330">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e7364-330">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="e7364-331">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="e7364-331">IOThreadTerminate</span></span>  
 <span data-ttu-id="e7364-332">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-332">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e7364-333">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e7364-333">Keyword for raising the event</span></span>|<span data-ttu-id="e7364-334">レベル</span><span class="sxs-lookup"><span data-stu-id="e7364-334">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="e7364-335">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="e7364-335">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="e7364-336">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="e7364-336">Informational (4)</span></span>|  
  
 <span data-ttu-id="e7364-337">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-337">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e7364-338">イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-338">Event</span></span>|<span data-ttu-id="e7364-339">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7364-339">Event ID</span></span>|<span data-ttu-id="e7364-340">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e7364-340">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="e7364-341">45</span><span class="sxs-lookup"><span data-stu-id="e7364-341">45</span></span>|<span data-ttu-id="e7364-342">I/O スレッドがスレッド プールに作成された。</span><span class="sxs-lookup"><span data-stu-id="e7364-342">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="e7364-343">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e7364-343">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e7364-344">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e7364-344">Field name</span></span>|<span data-ttu-id="e7364-345">データ型</span><span class="sxs-lookup"><span data-stu-id="e7364-345">Data type</span></span>|<span data-ttu-id="e7364-346">説明</span><span class="sxs-lookup"><span data-stu-id="e7364-346">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e7364-347">カウント</span><span class="sxs-lookup"><span data-stu-id="e7364-347">Count</span></span>|<span data-ttu-id="e7364-348">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e7364-348">win:UInt64</span></span>|<span data-ttu-id="e7364-349">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="e7364-349">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="e7364-350">NumRetired</span><span class="sxs-lookup"><span data-stu-id="e7364-350">NumRetired</span></span>|<span data-ttu-id="e7364-351">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e7364-351">win:UInt64</span></span>|<span data-ttu-id="e7364-352">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="e7364-352">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="e7364-353">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e7364-353">ClrInstanceID</span></span>|<span data-ttu-id="e7364-354">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e7364-354">Win:UInt16</span></span>|<span data-ttu-id="e7364-355">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e7364-355">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7364-356">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7364-356">See also</span></span>

- [<span data-ttu-id="e7364-357">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="e7364-357">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
