---
title: スレッド プール ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: e1deb17dfdfea4c8b66eb8d836a10bf888727e1a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715900"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="c6ae8-102">スレッド プール ETW イベント</span><span class="sxs-lookup"><span data-stu-id="c6ae8-102">Thread Pool ETW Events</span></span>
<span data-ttu-id="c6ae8-103">これらのイベントは、ワーカー スレッドと I/O スレッドに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-103">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="c6ae8-104">スレッド プール イベントには 2 つのグループがあります。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-104">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="c6ae8-105">[ワーカー スレッド プール イベント](#worker-thread-pool-events)は、アプリケーションがどのようにスレッド プールを使用するかに関する情報と、コンカレンシー制御におけるワークロードの効果に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-105">[Worker thread pool events](#worker-thread-pool-events), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="c6ae8-106">[I/O スレッド プール イベント](#io-thread-events)は、スレッド プールで作成、無効化、無効化解除、または終了した I/O スレッドに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-106">[I/O thread pool events](#io-thread-events), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  

## <a name="worker-thread-pool-events"></a><span data-ttu-id="c6ae8-107">ワーカー スレッド プール イベント</span><span class="sxs-lookup"><span data-stu-id="c6ae8-107">Worker Thread Pool Events</span></span>
 <span data-ttu-id="c6ae8-108">これらのイベントは、ランタイムのワーカー スレッドのプールに関連付けられており、スレッド イベントに関する通知 (スレッドが作成されたり停止されたりした場合など) を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="c6ae8-109">ワーカー スレッド プールは、スレッドの数が計測されたスループットに基づいて計算されるアダプティブ アルゴリズムを使用して、コンカレンシー制御を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="c6ae8-110">ワーカー スレッド プール イベントを使用すると、アプリケーションで使用されるスレッド プールの様子や特定のワークロードがコンカレンシー制御に与える影響などを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="c6ae8-111">ThreadPoolWorkerThreadStart および ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="c6ae8-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="c6ae8-112">次の表に、これらのイベントのキーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="c6ae8-113">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-113">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="c6ae8-114">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c6ae8-114">Keyword for raising the event</span></span>|<span data-ttu-id="c6ae8-115">レベル</span><span class="sxs-lookup"><span data-stu-id="c6ae8-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c6ae8-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c6ae8-117">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="c6ae8-118">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c6ae8-119">Event</span><span class="sxs-lookup"><span data-stu-id="c6ae8-119">Event</span></span>|<span data-ttu-id="c6ae8-120">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-120">Event ID</span></span>|<span data-ttu-id="c6ae8-121">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="c6ae8-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="c6ae8-122">50</span><span class="sxs-lookup"><span data-stu-id="c6ae8-122">50</span></span>|<span data-ttu-id="c6ae8-123">ワーカー スレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="c6ae8-124">51</span><span class="sxs-lookup"><span data-stu-id="c6ae8-124">51</span></span>|<span data-ttu-id="c6ae8-125">ワーカー スレッドが停止された。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="c6ae8-126">52</span><span class="sxs-lookup"><span data-stu-id="c6ae8-126">52</span></span>|<span data-ttu-id="c6ae8-127">ワーカー スレッドが無効にされた。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="c6ae8-128">53</span><span class="sxs-lookup"><span data-stu-id="c6ae8-128">53</span></span>|<span data-ttu-id="c6ae8-129">提供終了になったワーカー スレッドが再びアクティブになった。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="c6ae8-130">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c6ae8-131">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c6ae8-131">Field name</span></span>|<span data-ttu-id="c6ae8-132">[データ型]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-132">Data type</span></span>|<span data-ttu-id="c6ae8-133">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c6ae8-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="c6ae8-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="c6ae8-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c6ae8-135">win:UInt32</span></span>|<span data-ttu-id="c6ae8-136">作業の処理に使用可能なワーカー スレッド (既に作業の処理中のもの含む) の数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="c6ae8-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="c6ae8-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="c6ae8-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c6ae8-138">win:UInt32</span></span>|<span data-ttu-id="c6ae8-139">作業の処理に使用できないものの、後にさらに多くのスレッドが必要になった場合に備えて予約されているワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="c6ae8-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-140">ClrInstanceID</span></span>|<span data-ttu-id="c6ae8-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c6ae8-141">Win:UInt16</span></span>|<span data-ttu-id="c6ae8-142">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="c6ae8-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="c6ae8-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="c6ae8-144">これらのスレッド プール イベントは、スレッドの挿入 (コンカレンシー制御) アルゴリズムの動作を理解したりデバッグしたりするための情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="c6ae8-145">この情報は、ワーカー スレッド プールによって内部で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="c6ae8-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="c6ae8-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="c6ae8-147">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c6ae8-148">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c6ae8-148">Keyword for raising the event</span></span>|<span data-ttu-id="c6ae8-149">レベル</span><span class="sxs-lookup"><span data-stu-id="c6ae8-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c6ae8-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c6ae8-151">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="c6ae8-152">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c6ae8-153">Event</span><span class="sxs-lookup"><span data-stu-id="c6ae8-153">Event</span></span>|<span data-ttu-id="c6ae8-154">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-154">Event ID</span></span>|<span data-ttu-id="c6ae8-155">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="c6ae8-156">54</span><span class="sxs-lookup"><span data-stu-id="c6ae8-156">54</span></span>|<span data-ttu-id="c6ae8-157">1 つのサンプルの情報のコレクションを参照します。つまり、特定のコンカレンシー レベルの特定の時刻におけるスループットの測定値です。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="c6ae8-158">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c6ae8-159">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c6ae8-159">Field name</span></span>|<span data-ttu-id="c6ae8-160">[データ型]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-160">Data type</span></span>|<span data-ttu-id="c6ae8-161">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c6ae8-162">スループット</span><span class="sxs-lookup"><span data-stu-id="c6ae8-162">Throughput</span></span>|<span data-ttu-id="c6ae8-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-163">win:Double</span></span>|<span data-ttu-id="c6ae8-164">時間の単位あたりの入力候補の数です。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="c6ae8-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-165">ClrInstanceID</span></span>|<span data-ttu-id="c6ae8-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c6ae8-166">Win:UInt16</span></span>|<span data-ttu-id="c6ae8-167">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="c6ae8-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="c6ae8-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="c6ae8-169">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c6ae8-170">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c6ae8-170">Keyword for raising the event</span></span>|<span data-ttu-id="c6ae8-171">レベル</span><span class="sxs-lookup"><span data-stu-id="c6ae8-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c6ae8-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c6ae8-173">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="c6ae8-174">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c6ae8-175">Event</span><span class="sxs-lookup"><span data-stu-id="c6ae8-175">Event</span></span>|<span data-ttu-id="c6ae8-176">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-176">Event ID</span></span>|<span data-ttu-id="c6ae8-177">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="c6ae8-178">55</span><span class="sxs-lookup"><span data-stu-id="c6ae8-178">55</span></span>|<span data-ttu-id="c6ae8-179">スレッドの挿入 (山登り法) アルゴリズムが、コンカレンシー レベルに変更があったと判断した場合に、コントロールの変更を記録します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="c6ae8-180">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c6ae8-181">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c6ae8-181">Field name</span></span>|<span data-ttu-id="c6ae8-182">[データ型]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-182">Data type</span></span>|<span data-ttu-id="c6ae8-183">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c6ae8-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="c6ae8-184">AverageThroughput</span></span>|<span data-ttu-id="c6ae8-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-185">win:Double</span></span>|<span data-ttu-id="c6ae8-186">計測のサンプルの平均のスループット。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="c6ae8-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="c6ae8-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="c6ae8-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c6ae8-188">win:UInt32</span></span>|<span data-ttu-id="c6ae8-189">新しいアクティブなワーカー スレッド数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="c6ae8-190">理由</span><span class="sxs-lookup"><span data-stu-id="c6ae8-190">Reason</span></span>|<span data-ttu-id="c6ae8-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c6ae8-191">win:UInt32</span></span>|<span data-ttu-id="c6ae8-192">調整の理由。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="c6ae8-193">0x00 - ウォーム アップ。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="c6ae8-194">0x01 - 初期化。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="c6ae8-195">0x02 - ランダムな移動。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="c6ae8-196">0x03 - 上昇移動。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="c6ae8-197">0x04 - 変更点。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="c6ae8-198">0x05 - 安定化。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="c6ae8-199">0x06 - 不足。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="c6ae8-200">0x07 - スレッドのタイムアウト。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="c6ae8-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-201">ClrInstanceID</span></span>|<span data-ttu-id="c6ae8-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c6ae8-202">Win:UInt16</span></span>|<span data-ttu-id="c6ae8-203">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="c6ae8-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="c6ae8-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="c6ae8-205">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c6ae8-206">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c6ae8-206">Keyword for raising the event</span></span>|<span data-ttu-id="c6ae8-207">レベル</span><span class="sxs-lookup"><span data-stu-id="c6ae8-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c6ae8-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c6ae8-209">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="c6ae8-210">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c6ae8-211">Event</span><span class="sxs-lookup"><span data-stu-id="c6ae8-211">Event</span></span>|<span data-ttu-id="c6ae8-212">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-212">Event ID</span></span>|<span data-ttu-id="c6ae8-213">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="c6ae8-214">56</span><span class="sxs-lookup"><span data-stu-id="c6ae8-214">56</span></span>|<span data-ttu-id="c6ae8-215">スレッド プールに関するデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="c6ae8-216">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c6ae8-217">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c6ae8-217">Field name</span></span>|<span data-ttu-id="c6ae8-218">[データ型]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-218">Data type</span></span>|<span data-ttu-id="c6ae8-219">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c6ae8-220">継続期間</span><span class="sxs-lookup"><span data-stu-id="c6ae8-220">Duration</span></span>|<span data-ttu-id="c6ae8-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-221">win:Double</span></span>|<span data-ttu-id="c6ae8-222">これらの統計情報が収集される時間数 (秒)。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="c6ae8-223">スループット</span><span class="sxs-lookup"><span data-stu-id="c6ae8-223">Throughput</span></span>|<span data-ttu-id="c6ae8-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-224">win:Double</span></span>|<span data-ttu-id="c6ae8-225">この間隔中の 1 秒あたりの入力候補の平均数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="c6ae8-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="c6ae8-226">ThreadWave</span></span>|<span data-ttu-id="c6ae8-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-227">win:Double</span></span>|<span data-ttu-id="c6ae8-228">内部使用のために予約済みです。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="c6ae8-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="c6ae8-229">ThroughputWave</span></span>|<span data-ttu-id="c6ae8-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-230">win:Double</span></span>|<span data-ttu-id="c6ae8-231">内部使用のために予約済みです。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="c6ae8-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="c6ae8-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="c6ae8-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-233">win:Double</span></span>|<span data-ttu-id="c6ae8-234">内部使用のために予約済みです。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="c6ae8-235">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="c6ae8-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="c6ae8-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-236">win:Double</span></span>|<span data-ttu-id="c6ae8-237">内部使用のために予約済みです。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="c6ae8-238">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="c6ae8-238">ThroughputRatio</span></span>|<span data-ttu-id="c6ae8-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-239">win:Double</span></span>|<span data-ttu-id="c6ae8-240">この間隔中にアクティブなワーカー スレッドの数の変動によって引き起こされる、スループットの相対的な向上。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="c6ae8-241">信頼度</span><span class="sxs-lookup"><span data-stu-id="c6ae8-241">Confidence</span></span>|<span data-ttu-id="c6ae8-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-242">win:Double</span></span>|<span data-ttu-id="c6ae8-243">ThroughputRatio フィールドの有効性の測定結果。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="c6ae8-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="c6ae8-244">NewcontrolSetting</span></span>|<span data-ttu-id="c6ae8-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="c6ae8-245">win:Double</span></span>|<span data-ttu-id="c6ae8-246">アクティブなスレッド数の将来のバリエーションのベースラインとして使用するアクティブなワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="c6ae8-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="c6ae8-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="c6ae8-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c6ae8-248">Win:UInt16</span></span>|<span data-ttu-id="c6ae8-249">アクティブなスレッド数の、将来のバリエーションの大きさを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="c6ae8-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-250">ClrInstanceID</span></span>|<span data-ttu-id="c6ae8-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c6ae8-251">Win:UInt16</span></span>|<span data-ttu-id="c6ae8-252">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="io-thread-events"></a><span data-ttu-id="c6ae8-253">I/O スレッド イベント</span><span class="sxs-lookup"><span data-stu-id="c6ae8-253">I/O Thread Events</span></span>  
 <span data-ttu-id="c6ae8-254">これらのスレッド プール イベントは、I/O スレッド プール (完了ポート) にあるスレッドで発生します。これは非同期です。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-254">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreate_v1"></a><span data-ttu-id="c6ae8-255">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="c6ae8-255">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="c6ae8-256">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-256">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c6ae8-257">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c6ae8-257">Keyword for raising the event</span></span>|<span data-ttu-id="c6ae8-258">レベル</span><span class="sxs-lookup"><span data-stu-id="c6ae8-258">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c6ae8-259">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-259">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c6ae8-260">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-260">Informational (4)</span></span>|  
  
 <span data-ttu-id="c6ae8-261">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-261">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c6ae8-262">Event</span><span class="sxs-lookup"><span data-stu-id="c6ae8-262">Event</span></span>|<span data-ttu-id="c6ae8-263">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-263">Event ID</span></span>|<span data-ttu-id="c6ae8-264">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="c6ae8-264">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="c6ae8-265">44</span><span class="sxs-lookup"><span data-stu-id="c6ae8-265">44</span></span>|<span data-ttu-id="c6ae8-266">I/O スレッドがスレッド プールに作成された。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-266">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="c6ae8-267">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-267">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c6ae8-268">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c6ae8-268">Field name</span></span>|<span data-ttu-id="c6ae8-269">[データ型]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-269">Data type</span></span>|<span data-ttu-id="c6ae8-270">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-270">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c6ae8-271">[カウント]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-271">Count</span></span>|<span data-ttu-id="c6ae8-272">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c6ae8-272">win:UInt64</span></span>|<span data-ttu-id="c6ae8-273">新しく作成されたスレッドを含む、I/O のスレッドの数です。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-273">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="c6ae8-274">NumRetired</span><span class="sxs-lookup"><span data-stu-id="c6ae8-274">NumRetired</span></span>|<span data-ttu-id="c6ae8-275">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c6ae8-275">win:UInt64</span></span>|<span data-ttu-id="c6ae8-276">提供終了になったワーカー スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-276">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="c6ae8-277">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-277">ClrInstanceID</span></span>|<span data-ttu-id="c6ae8-278">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c6ae8-278">Win:UInt16</span></span>|<span data-ttu-id="c6ae8-279">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-279">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretire_v1"></a><span data-ttu-id="c6ae8-280">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="c6ae8-280">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="c6ae8-281">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-281">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c6ae8-282">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c6ae8-282">Keyword for raising the event</span></span>|<span data-ttu-id="c6ae8-283">レベル</span><span class="sxs-lookup"><span data-stu-id="c6ae8-283">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c6ae8-284">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-284">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c6ae8-285">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-285">Informational (4)</span></span>|  
  
 <span data-ttu-id="c6ae8-286">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-286">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c6ae8-287">Event</span><span class="sxs-lookup"><span data-stu-id="c6ae8-287">Event</span></span>|<span data-ttu-id="c6ae8-288">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-288">Event ID</span></span>|<span data-ttu-id="c6ae8-289">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="c6ae8-289">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="c6ae8-290">46</span><span class="sxs-lookup"><span data-stu-id="c6ae8-290">46</span></span>|<span data-ttu-id="c6ae8-291">I/O スレッドが、提供終了の候補になる。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-291">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="c6ae8-292">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-292">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c6ae8-293">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c6ae8-293">Field name</span></span>|<span data-ttu-id="c6ae8-294">[データ型]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-294">Data type</span></span>|<span data-ttu-id="c6ae8-295">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-295">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c6ae8-296">[カウント]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-296">Count</span></span>|<span data-ttu-id="c6ae8-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c6ae8-297">win:UInt64</span></span>|<span data-ttu-id="c6ae8-298">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-298">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="c6ae8-299">NumRetired</span><span class="sxs-lookup"><span data-stu-id="c6ae8-299">NumRetired</span></span>|<span data-ttu-id="c6ae8-300">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c6ae8-300">win:UInt64</span></span>|<span data-ttu-id="c6ae8-301">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-301">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="c6ae8-302">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-302">ClrInstanceID</span></span>|<span data-ttu-id="c6ae8-303">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c6ae8-303">Win:UInt16</span></span>|<span data-ttu-id="c6ae8-304">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-304">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretire_v1"></a><span data-ttu-id="c6ae8-305">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="c6ae8-305">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="c6ae8-306">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c6ae8-307">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c6ae8-307">Keyword for raising the event</span></span>|<span data-ttu-id="c6ae8-308">レベル</span><span class="sxs-lookup"><span data-stu-id="c6ae8-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c6ae8-309">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-309">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c6ae8-310">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="c6ae8-311">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c6ae8-312">Event</span><span class="sxs-lookup"><span data-stu-id="c6ae8-312">Event</span></span>|<span data-ttu-id="c6ae8-313">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-313">Event ID</span></span>|<span data-ttu-id="c6ae8-314">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="c6ae8-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="c6ae8-315">47</span><span class="sxs-lookup"><span data-stu-id="c6ae8-315">47</span></span>|<span data-ttu-id="c6ae8-316">スレッドが提供終了の候補になってから待機期間内に I/O が到着したため I/O スレッドが提供終了解除された。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-316">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="c6ae8-317">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-317">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c6ae8-318">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c6ae8-318">Field name</span></span>|<span data-ttu-id="c6ae8-319">[データ型]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-319">Data type</span></span>|<span data-ttu-id="c6ae8-320">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-320">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c6ae8-321">[カウント]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-321">Count</span></span>|<span data-ttu-id="c6ae8-322">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c6ae8-322">win:UInt64</span></span>|<span data-ttu-id="c6ae8-323">これを含む、スレッド プール内の I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-323">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="c6ae8-324">NumRetired</span><span class="sxs-lookup"><span data-stu-id="c6ae8-324">NumRetired</span></span>|<span data-ttu-id="c6ae8-325">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c6ae8-325">win:UInt64</span></span>|<span data-ttu-id="c6ae8-326">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-326">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="c6ae8-327">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-327">ClrInstanceID</span></span>|<span data-ttu-id="c6ae8-328">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c6ae8-328">Win:UInt16</span></span>|<span data-ttu-id="c6ae8-329">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-329">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="c6ae8-330">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="c6ae8-330">IOThreadTerminate</span></span>  
 <span data-ttu-id="c6ae8-331">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-331">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c6ae8-332">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="c6ae8-332">Keyword for raising the event</span></span>|<span data-ttu-id="c6ae8-333">レベル</span><span class="sxs-lookup"><span data-stu-id="c6ae8-333">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c6ae8-334">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-334">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c6ae8-335">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="c6ae8-335">Informational (4)</span></span>|  
  
 <span data-ttu-id="c6ae8-336">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-336">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c6ae8-337">Event</span><span class="sxs-lookup"><span data-stu-id="c6ae8-337">Event</span></span>|<span data-ttu-id="c6ae8-338">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-338">Event ID</span></span>|<span data-ttu-id="c6ae8-339">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="c6ae8-339">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="c6ae8-340">45</span><span class="sxs-lookup"><span data-stu-id="c6ae8-340">45</span></span>|<span data-ttu-id="c6ae8-341">I/O スレッドがスレッド プールに作成された。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-341">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="c6ae8-342">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-342">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c6ae8-343">フィールド名</span><span class="sxs-lookup"><span data-stu-id="c6ae8-343">Field name</span></span>|<span data-ttu-id="c6ae8-344">[データ型]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-344">Data type</span></span>|<span data-ttu-id="c6ae8-345">説明</span><span class="sxs-lookup"><span data-stu-id="c6ae8-345">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c6ae8-346">[カウント]</span><span class="sxs-lookup"><span data-stu-id="c6ae8-346">Count</span></span>|<span data-ttu-id="c6ae8-347">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c6ae8-347">win:UInt64</span></span>|<span data-ttu-id="c6ae8-348">スレッド プールに残っている I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-348">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="c6ae8-349">NumRetired</span><span class="sxs-lookup"><span data-stu-id="c6ae8-349">NumRetired</span></span>|<span data-ttu-id="c6ae8-350">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c6ae8-350">win:UInt64</span></span>|<span data-ttu-id="c6ae8-351">提供終了になった I/O スレッドの数。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-351">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="c6ae8-352">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c6ae8-352">ClrInstanceID</span></span>|<span data-ttu-id="c6ae8-353">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c6ae8-353">Win:UInt16</span></span>|<span data-ttu-id="c6ae8-354">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c6ae8-354">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6ae8-355">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6ae8-355">See also</span></span>

- [<span data-ttu-id="c6ae8-356">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="c6ae8-356">CLR ETW Events</span></span>](clr-etw-events.md)
