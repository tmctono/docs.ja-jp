---
title: ガベージ コレクション ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f9bf0e309ec8c77d4b1d6afbf111e7eeae629ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149735"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="0ff02-102">ガベージ コレクション ETW イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="0ff02-103">これらのイベントは、ガベージ コレクションに関連する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="0ff02-104">ガベージ コレクションが実行された回数、ガベージ コレクションの間に解放されたメモリの量など、診断やデバッグに役立つ情報を入手できます。</span><span class="sxs-lookup"><span data-stu-id="0ff02-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="0ff02-105">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="0ff02-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="0ff02-106">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="0ff02-107">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="0ff02-108">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="0ff02-109">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="0ff02-110">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="0ff02-111">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="0ff02-112">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="0ff02-113">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="0ff02-114">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="0ff02-115">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="0ff02-116">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="0ff02-117">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="0ff02-118">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="0ff02-119">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="0ff02-120">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="0ff02-121">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="0ff02-122">(詳細については、「 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="0ff02-123">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-123">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-124">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-124">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-125">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-125">(0x1)</span></span>|<span data-ttu-id="0ff02-126">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-127">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-128">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-128">Event</span></span>|<span data-ttu-id="0ff02-129">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-129">Event ID</span></span>|<span data-ttu-id="0ff02-130">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="0ff02-131">1</span><span class="sxs-lookup"><span data-stu-id="0ff02-131">1</span></span>|<span data-ttu-id="0ff02-132">ガベージ コレクションが開始されました。</span><span class="sxs-lookup"><span data-stu-id="0ff02-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="0ff02-133">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0ff02-134">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0ff02-134">Field name</span></span>|<span data-ttu-id="0ff02-135">データ型</span><span class="sxs-lookup"><span data-stu-id="0ff02-135">Data type</span></span>|<span data-ttu-id="0ff02-136">説明</span><span class="sxs-lookup"><span data-stu-id="0ff02-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0ff02-137">カウント</span><span class="sxs-lookup"><span data-stu-id="0ff02-137">Count</span></span>|<span data-ttu-id="0ff02-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-138">win:UInt32</span></span>|<span data-ttu-id="0ff02-139">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="0ff02-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="0ff02-140">奥行</span><span class="sxs-lookup"><span data-stu-id="0ff02-140">Depth</span></span>|<span data-ttu-id="0ff02-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-141">win:UInt32</span></span>|<span data-ttu-id="0ff02-142">収集されるジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="0ff02-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="0ff02-143">理由</span><span class="sxs-lookup"><span data-stu-id="0ff02-143">Reason</span></span>|<span data-ttu-id="0ff02-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-144">win:UInt32</span></span>|<span data-ttu-id="0ff02-145">ガベージ コレクションが発生した理由:</span><span class="sxs-lookup"><span data-stu-id="0ff02-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="0ff02-146">0x0 - 小さなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="0ff02-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="0ff02-147">0x1 - 強制実行。</span><span class="sxs-lookup"><span data-stu-id="0ff02-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="0ff02-148">0x2 - メモリ不足。</span><span class="sxs-lookup"><span data-stu-id="0ff02-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="0ff02-149">0x3 - 空。</span><span class="sxs-lookup"><span data-stu-id="0ff02-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="0ff02-150">0x4 - 大きなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="0ff02-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="0ff02-151">0x5 - 領域不足 (小さなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="0ff02-152">0x6 - 領域不足 (大きなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="0ff02-153">0x7 - 強制実行されるが、ブロッキングとして強制されない。</span><span class="sxs-lookup"><span data-stu-id="0ff02-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="0ff02-154">型</span><span class="sxs-lookup"><span data-stu-id="0ff02-154">Type</span></span>|<span data-ttu-id="0ff02-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-155">win:UInt32</span></span>|<span data-ttu-id="0ff02-156">0x0 - バックグラウンド ガベージ コレクションの外部で発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="0ff02-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="0ff02-157">0x1 - バックグラウンド ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="0ff02-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="0ff02-158">0x2 - バックグラウンド ガベージ コレクションの実行中に発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="0ff02-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="0ff02-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0ff02-159">ClrInstanceID</span></span>|<span data-ttu-id="0ff02-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0ff02-160">win:UInt16</span></span>|<span data-ttu-id="0ff02-161">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0ff02-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0ff02-162">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="0ff02-163">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="0ff02-164">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-165">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-165">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-166">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-166">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-167">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-167">(0x1)</span></span>|<span data-ttu-id="0ff02-168">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-169">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-170">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-170">Event</span></span>|<span data-ttu-id="0ff02-171">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-171">Event ID</span></span>|<span data-ttu-id="0ff02-172">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="0ff02-173">2</span><span class="sxs-lookup"><span data-stu-id="0ff02-173">2</span></span>|<span data-ttu-id="0ff02-174">ガベージ コレクションが終了しました。</span><span class="sxs-lookup"><span data-stu-id="0ff02-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="0ff02-175">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0ff02-176">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0ff02-176">Field name</span></span>|<span data-ttu-id="0ff02-177">データ型</span><span class="sxs-lookup"><span data-stu-id="0ff02-177">Data type</span></span>|<span data-ttu-id="0ff02-178">説明</span><span class="sxs-lookup"><span data-stu-id="0ff02-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0ff02-179">カウント</span><span class="sxs-lookup"><span data-stu-id="0ff02-179">Count</span></span>|<span data-ttu-id="0ff02-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-180">win:UInt32</span></span>|<span data-ttu-id="0ff02-181">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="0ff02-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="0ff02-182">奥行</span><span class="sxs-lookup"><span data-stu-id="0ff02-182">Depth</span></span>|<span data-ttu-id="0ff02-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-183">win:UInt32</span></span>|<span data-ttu-id="0ff02-184">収集されたジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="0ff02-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="0ff02-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0ff02-185">ClrInstanceID</span></span>|<span data-ttu-id="0ff02-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0ff02-186">win:UInt16</span></span>|<span data-ttu-id="0ff02-187">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0ff02-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0ff02-188">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="0ff02-189">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="0ff02-190">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-191">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-191">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-192">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-192">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-193">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-193">(0x1)</span></span>|<span data-ttu-id="0ff02-194">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-195">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-196">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-196">Event</span></span>|<span data-ttu-id="0ff02-197">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-197">Event ID</span></span>|<span data-ttu-id="0ff02-198">説明</span><span class="sxs-lookup"><span data-stu-id="0ff02-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="0ff02-199">4</span><span class="sxs-lookup"><span data-stu-id="0ff02-199">4</span></span>|<span data-ttu-id="0ff02-200">各ガベージ コレクション終了時のヒープの統計情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="0ff02-201">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0ff02-202">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0ff02-202">Field name</span></span>|<span data-ttu-id="0ff02-203">データ型</span><span class="sxs-lookup"><span data-stu-id="0ff02-203">Data type</span></span>|<span data-ttu-id="0ff02-204">説明</span><span class="sxs-lookup"><span data-stu-id="0ff02-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0ff02-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="0ff02-205">GenerationSize0</span></span>|<span data-ttu-id="0ff02-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-206">win:UInt64</span></span>|<span data-ttu-id="0ff02-207">ジェネレーション 0 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="0ff02-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="0ff02-208">TotalPromotedSize0</span></span>|<span data-ttu-id="0ff02-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-209">win:UInt64</span></span>|<span data-ttu-id="0ff02-210">ジェネレーション 0 からジェネレーション 1 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="0ff02-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="0ff02-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="0ff02-211">GenerationSize1</span></span>|<span data-ttu-id="0ff02-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-212">win:UInt64</span></span>|<span data-ttu-id="0ff02-213">ジェネレーション 1 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="0ff02-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="0ff02-214">TotalPromotedSize1</span></span>|<span data-ttu-id="0ff02-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-215">win:UInt64</span></span>|<span data-ttu-id="0ff02-216">ジェネレーション 1 からジェネレーション 2 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="0ff02-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="0ff02-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="0ff02-217">GenerationSize2</span></span>|<span data-ttu-id="0ff02-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-218">win:UInt64</span></span>|<span data-ttu-id="0ff02-219">ジェネレーション 2 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="0ff02-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="0ff02-220">TotalPromotedSize2</span></span>|<span data-ttu-id="0ff02-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-221">win:UInt64</span></span>|<span data-ttu-id="0ff02-222">最後のガベージ コレクションの後にジェネレーション 2 に残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="0ff02-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="0ff02-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="0ff02-223">GenerationSize3</span></span>|<span data-ttu-id="0ff02-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-224">win:UInt64</span></span>|<span data-ttu-id="0ff02-225">大きなオブジェクト ヒープのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="0ff02-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="0ff02-226">TotalPromotedSize3</span></span>|<span data-ttu-id="0ff02-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-227">win:UInt64</span></span>|<span data-ttu-id="0ff02-228">最後のガベージ コレクションの後に大きなオブジェクト ヒープに残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="0ff02-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="0ff02-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="0ff02-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="0ff02-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-230">win:UInt64</span></span>|<span data-ttu-id="0ff02-231">終了準備が完了しているオブジェクトの合計サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="0ff02-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="0ff02-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="0ff02-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-233">win:UInt64</span></span>|<span data-ttu-id="0ff02-234">終了準備が完了しているオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="0ff02-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="0ff02-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="0ff02-235">PinnedObjectCount</span></span>|<span data-ttu-id="0ff02-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-236">win:UInt32</span></span>|<span data-ttu-id="0ff02-237">ピン止めオブジェクト (移動できないオブジェクト) の数。</span><span class="sxs-lookup"><span data-stu-id="0ff02-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="0ff02-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="0ff02-238">SinkBlockCount</span></span>|<span data-ttu-id="0ff02-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-239">win:UInt32</span></span>|<span data-ttu-id="0ff02-240">使用中の同期ブロックの数。</span><span class="sxs-lookup"><span data-stu-id="0ff02-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="0ff02-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="0ff02-241">GCHandleCount</span></span>|<span data-ttu-id="0ff02-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-242">win:UInt32</span></span>|<span data-ttu-id="0ff02-243">使用中のガベージ コレクション ハンドルの数。</span><span class="sxs-lookup"><span data-stu-id="0ff02-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="0ff02-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0ff02-244">ClrInstanceID</span></span>|<span data-ttu-id="0ff02-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0ff02-245">win:UInt16</span></span>|<span data-ttu-id="0ff02-246">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0ff02-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0ff02-247">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="0ff02-248">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="0ff02-249">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-250">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-250">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-251">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-251">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-252">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-252">(0x1)</span></span>|<span data-ttu-id="0ff02-253">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-254">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-255">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-255">Event</span></span>|<span data-ttu-id="0ff02-256">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-256">Event ID</span></span>|<span data-ttu-id="0ff02-257">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="0ff02-258">5</span><span class="sxs-lookup"><span data-stu-id="0ff02-258">5</span></span>|<span data-ttu-id="0ff02-259">新しいガベージ コレクション セグメントが作成されました。</span><span class="sxs-lookup"><span data-stu-id="0ff02-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="0ff02-260">既に実行されているプロセスでトレースを有効にした場合は、このイベントが各既存セグメントについて発生します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="0ff02-261">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0ff02-262">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0ff02-262">Field name</span></span>|<span data-ttu-id="0ff02-263">データ型</span><span class="sxs-lookup"><span data-stu-id="0ff02-263">Data type</span></span>|<span data-ttu-id="0ff02-264">説明</span><span class="sxs-lookup"><span data-stu-id="0ff02-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0ff02-265">アドレス</span><span class="sxs-lookup"><span data-stu-id="0ff02-265">Address</span></span>|<span data-ttu-id="0ff02-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-266">win:UInt64</span></span>|<span data-ttu-id="0ff02-267">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="0ff02-267">The address of the segment.</span></span>|  
|<span data-ttu-id="0ff02-268">サイズ</span><span class="sxs-lookup"><span data-stu-id="0ff02-268">Size</span></span>|<span data-ttu-id="0ff02-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-269">win:UInt64</span></span>|<span data-ttu-id="0ff02-270">セグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="0ff02-270">The size of the segment.</span></span>|  
|<span data-ttu-id="0ff02-271">型</span><span class="sxs-lookup"><span data-stu-id="0ff02-271">Type</span></span>|<span data-ttu-id="0ff02-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-272">win:UInt32</span></span>|<span data-ttu-id="0ff02-273">0x0 - 小さなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="0ff02-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="0ff02-274">0x1 - 大きなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="0ff02-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="0ff02-275">0x2 - 読み取り専用ヒープ。</span><span class="sxs-lookup"><span data-stu-id="0ff02-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="0ff02-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0ff02-276">ClrInstanceID</span></span>|<span data-ttu-id="0ff02-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0ff02-277">win:UInt16</span></span>|<span data-ttu-id="0ff02-278">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0ff02-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="0ff02-279">ガベージ コレクターによって割り当てられるセグメントのサイズは実装に固有であり、定期的な更新プログラムによる場合を含め、いつでも変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0ff02-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="0ff02-280">アプリでは、セグメント サイズを推測することや、特定のセグメント サイズに依存することを絶対に避けてください。また、セグメントの割り当てに使用可能なメモリの量を構成しようとしてもなりません。</span><span class="sxs-lookup"><span data-stu-id="0ff02-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="0ff02-281">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="0ff02-282">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="0ff02-283">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-284">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-284">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-285">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-285">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-286">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-286">(0x1)</span></span>|<span data-ttu-id="0ff02-287">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-288">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-289">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-289">Event</span></span>|<span data-ttu-id="0ff02-290">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-290">Event ID</span></span>|<span data-ttu-id="0ff02-291">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="0ff02-292">6</span><span class="sxs-lookup"><span data-stu-id="0ff02-292">6</span></span>|<span data-ttu-id="0ff02-293">ガベージ コレクション セグメントが解放されました。</span><span class="sxs-lookup"><span data-stu-id="0ff02-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="0ff02-294">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0ff02-295">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0ff02-295">Field name</span></span>|<span data-ttu-id="0ff02-296">データ型</span><span class="sxs-lookup"><span data-stu-id="0ff02-296">Data type</span></span>|<span data-ttu-id="0ff02-297">説明</span><span class="sxs-lookup"><span data-stu-id="0ff02-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0ff02-298">アドレス</span><span class="sxs-lookup"><span data-stu-id="0ff02-298">Address</span></span>|<span data-ttu-id="0ff02-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-299">win:UInt64</span></span>|<span data-ttu-id="0ff02-300">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="0ff02-300">The address of the segment.</span></span>|  
|<span data-ttu-id="0ff02-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0ff02-301">ClrInstanceID</span></span>|<span data-ttu-id="0ff02-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0ff02-302">win:UInt16</span></span>|<span data-ttu-id="0ff02-303">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0ff02-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0ff02-304">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="0ff02-305">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="0ff02-306">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-307">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-307">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-308">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-308">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-309">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-309">(0x1)</span></span>|<span data-ttu-id="0ff02-310">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-311">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-312">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-312">Event</span></span>|<span data-ttu-id="0ff02-313">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-313">Event ID</span></span>|<span data-ttu-id="0ff02-314">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="0ff02-315">7</span><span class="sxs-lookup"><span data-stu-id="0ff02-315">7</span></span>|<span data-ttu-id="0ff02-316">共通言語ランタイムの中断からの再開が開始されました。</span><span class="sxs-lookup"><span data-stu-id="0ff02-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="0ff02-317">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="0ff02-317">No event data.</span></span>  
  
 [<span data-ttu-id="0ff02-318">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="0ff02-319">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="0ff02-320">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-321">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-321">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-322">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-322">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-323">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-323">(0x1)</span></span>|<span data-ttu-id="0ff02-324">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-325">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-326">event</span><span class="sxs-lookup"><span data-stu-id="0ff02-326">Event</span></span>|<span data-ttu-id="0ff02-327">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-327">Event Id</span></span>|<span data-ttu-id="0ff02-328">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="0ff02-329">3</span><span class="sxs-lookup"><span data-stu-id="0ff02-329">3</span></span>|<span data-ttu-id="0ff02-330">共通言語ランタイムの中断からの再開が終了しました。</span><span class="sxs-lookup"><span data-stu-id="0ff02-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="0ff02-331">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="0ff02-331">No event data.</span></span>  
  
 [<span data-ttu-id="0ff02-332">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="0ff02-333">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="0ff02-334">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-335">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-335">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-336">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-336">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-337">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-337">(0x1)</span></span>|<span data-ttu-id="0ff02-338">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-339">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-340">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-340">Event</span></span>|<span data-ttu-id="0ff02-341">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-341">Event ID</span></span>|<span data-ttu-id="0ff02-342">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="0ff02-343">9</span><span class="sxs-lookup"><span data-stu-id="0ff02-343">9</span></span>|<span data-ttu-id="0ff02-344">ガベージ コレクションのための実行エンジンの中断の開始。</span><span class="sxs-lookup"><span data-stu-id="0ff02-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="0ff02-345">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0ff02-346">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0ff02-346">Field name</span></span>|<span data-ttu-id="0ff02-347">データ型</span><span class="sxs-lookup"><span data-stu-id="0ff02-347">Data type</span></span>|<span data-ttu-id="0ff02-348">説明</span><span class="sxs-lookup"><span data-stu-id="0ff02-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0ff02-349">理由</span><span class="sxs-lookup"><span data-stu-id="0ff02-349">Reason</span></span>|<span data-ttu-id="0ff02-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0ff02-350">win:UInt16</span></span>|<span data-ttu-id="0ff02-351">0x0 - その他。</span><span class="sxs-lookup"><span data-stu-id="0ff02-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="0ff02-352">0x1 - ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="0ff02-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="0ff02-353">0x2 - アプリケーション ドメインのシャットダウン。</span><span class="sxs-lookup"><span data-stu-id="0ff02-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="0ff02-354">0x3 - コード ピッチ。</span><span class="sxs-lookup"><span data-stu-id="0ff02-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="0ff02-355">0x4 - シャットダウン。</span><span class="sxs-lookup"><span data-stu-id="0ff02-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="0ff02-356">0x5 - デバッガー。</span><span class="sxs-lookup"><span data-stu-id="0ff02-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="0ff02-357">0x6 - ガベージ コレクションの準備。</span><span class="sxs-lookup"><span data-stu-id="0ff02-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="0ff02-358">カウント</span><span class="sxs-lookup"><span data-stu-id="0ff02-358">Count</span></span>|<span data-ttu-id="0ff02-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-359">win:UInt32</span></span>|<span data-ttu-id="0ff02-360">その時点の GC カウント。</span><span class="sxs-lookup"><span data-stu-id="0ff02-360">The GC count at the time.</span></span> <span data-ttu-id="0ff02-361">通常、この後に後続の GC 開始イベントが表示され、そのカウントは、ガベージ コレクション中に、GC インデックスが増えるため、このカウント + 1 になります。</span><span class="sxs-lookup"><span data-stu-id="0ff02-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="0ff02-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0ff02-362">ClrInstanceID</span></span>|<span data-ttu-id="0ff02-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0ff02-363">win:UInt16</span></span>|<span data-ttu-id="0ff02-364">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0ff02-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0ff02-365">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="0ff02-366">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="0ff02-367">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="0ff02-368">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-368">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-369">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-369">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-370">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-370">(0x1)</span></span>|<span data-ttu-id="0ff02-371">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-372">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="0ff02-373">event</span><span class="sxs-lookup"><span data-stu-id="0ff02-373">Event</span></span>|<span data-ttu-id="0ff02-374">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-374">Event ID</span></span>|<span data-ttu-id="0ff02-375">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="0ff02-376">8</span><span class="sxs-lookup"><span data-stu-id="0ff02-376">8</span></span>|<span data-ttu-id="0ff02-377">ガベージ コレクションのための実行エンジンの中断の終了。</span><span class="sxs-lookup"><span data-stu-id="0ff02-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="0ff02-378">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="0ff02-378">No event data.</span></span>  
  
 [<span data-ttu-id="0ff02-379">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="0ff02-380">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="0ff02-381">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-382">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-382">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-383">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-383">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-384">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-384">(0x1)</span></span>|<span data-ttu-id="0ff02-385">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-386">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-387">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-387">Event</span></span>|<span data-ttu-id="0ff02-388">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-388">Event ID</span></span>|<span data-ttu-id="0ff02-389">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="0ff02-390">10</span><span class="sxs-lookup"><span data-stu-id="0ff02-390">10</span></span>|<span data-ttu-id="0ff02-391">約 100 KB が割り当てられるたび。</span><span class="sxs-lookup"><span data-stu-id="0ff02-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="0ff02-392">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0ff02-393">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0ff02-393">Field name</span></span>|<span data-ttu-id="0ff02-394">データ型</span><span class="sxs-lookup"><span data-stu-id="0ff02-394">Data type</span></span>|<span data-ttu-id="0ff02-395">説明</span><span class="sxs-lookup"><span data-stu-id="0ff02-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0ff02-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="0ff02-396">AllocationAmount</span></span>|<span data-ttu-id="0ff02-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-397">win:UInt32</span></span>|<span data-ttu-id="0ff02-398">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-398">The allocation size, in bytes.</span></span> <span data-ttu-id="0ff02-399">この値は、ULONG (4,294,967,295 バイト) の長さより短い割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="0ff02-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="0ff02-400">割り当てがこれを超える場合、このフィールドには切り捨てられた値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ff02-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="0ff02-401">非常に大きな割り当てには `AllocationAmount64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="0ff02-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="0ff02-402">AllocationKind</span></span>|<span data-ttu-id="0ff02-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-403">win:UInt32</span></span>|<span data-ttu-id="0ff02-404">0x0 - 小さなオブジェクトの割り当て (小さなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="0ff02-405">0x1 - 大きなオブジェクトの割り当て (大きなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="0ff02-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0ff02-406">ClrInstanceID</span></span>|<span data-ttu-id="0ff02-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0ff02-407">win:UInt16</span></span>|<span data-ttu-id="0ff02-408">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0ff02-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="0ff02-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="0ff02-409">AllocationAmount64</span></span>|<span data-ttu-id="0ff02-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0ff02-410">win:UInt64</span></span>|<span data-ttu-id="0ff02-411">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="0ff02-411">The allocation size, in bytes.</span></span> <span data-ttu-id="0ff02-412">この値は非常に大きな割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="0ff02-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="0ff02-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="0ff02-413">TypeId</span></span>|<span data-ttu-id="0ff02-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="0ff02-414">win:Pointer</span></span>|<span data-ttu-id="0ff02-415">MethodTable のアドレス。</span><span class="sxs-lookup"><span data-stu-id="0ff02-415">The address of the MethodTable.</span></span> <span data-ttu-id="0ff02-416">このイベント中に複数の型のオブジェクトが割り当てられた場合、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) に対応する MethodTable のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="0ff02-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="0ff02-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="0ff02-417">TypeName</span></span>|<span data-ttu-id="0ff02-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="0ff02-418">win:UnicodeString</span></span>|<span data-ttu-id="0ff02-419">割り当てられた型の名前。</span><span class="sxs-lookup"><span data-stu-id="0ff02-419">The name of the type that was allocated.</span></span> <span data-ttu-id="0ff02-420">このイベント中に複数の型のオブジェクトが割り当てられた場合は、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) の型です。</span><span class="sxs-lookup"><span data-stu-id="0ff02-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="0ff02-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="0ff02-421">HeapIndex</span></span>|<span data-ttu-id="0ff02-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-422">win:UInt32</span></span>|<span data-ttu-id="0ff02-423">オブジェクトが割り当てられたヒープ。</span><span class="sxs-lookup"><span data-stu-id="0ff02-423">The heap where the object was allocated.</span></span> <span data-ttu-id="0ff02-424">ワークステーションのガベージ コレクションと共に実行する場合、この値は 0 (ゼロ) になります。</span><span class="sxs-lookup"><span data-stu-id="0ff02-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="0ff02-425">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="0ff02-426">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="0ff02-427">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-428">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-428">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-429">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-429">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-430">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-430">(0x1)</span></span>|<span data-ttu-id="0ff02-431">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-432">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-433">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-433">Event</span></span>|<span data-ttu-id="0ff02-434">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-434">Event ID</span></span>|<span data-ttu-id="0ff02-435">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="0ff02-436">14</span><span class="sxs-lookup"><span data-stu-id="0ff02-436">14</span></span>|<span data-ttu-id="0ff02-437">ファイナライザーの実行の開始。</span><span class="sxs-lookup"><span data-stu-id="0ff02-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="0ff02-438">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="0ff02-438">No event data.</span></span>  
  
 [<span data-ttu-id="0ff02-439">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="0ff02-440">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="0ff02-441">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-442">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-442">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-443">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-443">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-444">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-444">(0x1)</span></span>|<span data-ttu-id="0ff02-445">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-446">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-447">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-447">Event</span></span>|<span data-ttu-id="0ff02-448">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-448">Event ID</span></span>|<span data-ttu-id="0ff02-449">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="0ff02-450">13</span><span class="sxs-lookup"><span data-stu-id="0ff02-450">13</span></span>|<span data-ttu-id="0ff02-451">ファイナライザーの実行の終了。</span><span class="sxs-lookup"><span data-stu-id="0ff02-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="0ff02-452">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0ff02-453">フィールド名</span><span class="sxs-lookup"><span data-stu-id="0ff02-453">Field name</span></span>|<span data-ttu-id="0ff02-454">データ型</span><span class="sxs-lookup"><span data-stu-id="0ff02-454">Data type</span></span>|<span data-ttu-id="0ff02-455">説明</span><span class="sxs-lookup"><span data-stu-id="0ff02-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0ff02-456">カウント</span><span class="sxs-lookup"><span data-stu-id="0ff02-456">Count</span></span>|<span data-ttu-id="0ff02-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0ff02-457">win:UInt32</span></span>|<span data-ttu-id="0ff02-458">実行されたファイナライザーの数。</span><span class="sxs-lookup"><span data-stu-id="0ff02-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="0ff02-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0ff02-459">ClrInstanceID</span></span>|<span data-ttu-id="0ff02-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0ff02-460">win:UInt16</span></span>|<span data-ttu-id="0ff02-461">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0ff02-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0ff02-462">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="0ff02-463">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="0ff02-464">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-465">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-465">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-466">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-466">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-467">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-467">(0x1)</span></span>|<span data-ttu-id="0ff02-468">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-468">Informational (4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="0ff02-469">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="0ff02-469">(0x10000)</span></span>|<span data-ttu-id="0ff02-470">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-471">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-472">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-472">Event</span></span>|<span data-ttu-id="0ff02-473">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-473">Event ID</span></span>|<span data-ttu-id="0ff02-474">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="0ff02-475">11</span><span class="sxs-lookup"><span data-stu-id="0ff02-475">11</span></span>|<span data-ttu-id="0ff02-476">同時実行ガベージ コレクション スレッドが作成されました。</span><span class="sxs-lookup"><span data-stu-id="0ff02-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="0ff02-477">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="0ff02-477">No event data.</span></span>  
  
 [<span data-ttu-id="0ff02-478">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="0ff02-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="0ff02-479">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="0ff02-480">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0ff02-481">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="0ff02-481">Keyword for raising the event</span></span>|<span data-ttu-id="0ff02-482">レベル</span><span class="sxs-lookup"><span data-stu-id="0ff02-482">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="0ff02-483">(0x1)</span><span class="sxs-lookup"><span data-stu-id="0ff02-483">(0x1)</span></span>|<span data-ttu-id="0ff02-484">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-484">Informational (4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="0ff02-485">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="0ff02-485">(0x10000)</span></span>|<span data-ttu-id="0ff02-486">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="0ff02-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="0ff02-487">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0ff02-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0ff02-488">イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-488">Event</span></span>|<span data-ttu-id="0ff02-489">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ff02-489">Event ID</span></span>|<span data-ttu-id="0ff02-490">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="0ff02-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="0ff02-491">12</span><span class="sxs-lookup"><span data-stu-id="0ff02-491">12</span></span>|<span data-ttu-id="0ff02-492">同時実行ガベージ コレクションスレッドが終了しました。</span><span class="sxs-lookup"><span data-stu-id="0ff02-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="0ff02-493">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="0ff02-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ff02-494">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ff02-494">See also</span></span>

- [<span data-ttu-id="0ff02-495">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="0ff02-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
