---
title: ガベージ コレクション ETW イベント
description: ガベージコレクション ETW イベントに関する詳細情報を表示します。 説明されているイベントには、GCStart_V1、GCEnd_V1、GCHeapStats_V1、GCCreateSegment_V1 などがあります。
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 2e1e0fda5c1a80627c8dde7f49954a867b9a2b66
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720138"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="4c190-104">ガベージ コレクション ETW イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-104">Garbage Collection ETW Events</span></span>

<span data-ttu-id="4c190-105">これらのイベントは、ガベージ コレクションに関連する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="4c190-105">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="4c190-106">ガベージ コレクションが実行された回数、ガベージ コレクションの間に解放されたメモリの量など、診断やデバッグに役立つ情報を入手できます。</span><span class="sxs-lookup"><span data-stu-id="4c190-106">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="4c190-107">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4c190-107">This category consists of the following events:</span></span>

- [<span data-ttu-id="4c190-108">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-108">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="4c190-109">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-109">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="4c190-110">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-110">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="4c190-111">GCHeapStats_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-111">GCHeapStats_V2 Event</span></span>](#gcheapstats_v2-event)
- [<span data-ttu-id="4c190-112">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-112">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="4c190-113">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-113">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="4c190-114">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-114">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="4c190-115">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-115">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="4c190-116">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-116">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="4c190-117">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-117">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="4c190-118">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-118">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="4c190-119">GCAllocationTick_V3 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-119">GCAllocationTick_V3 Event</span></span>](#gcallocationtick_v3-event)
- [<span data-ttu-id="4c190-120">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-120">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="4c190-121">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-121">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="4c190-122">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-122">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="4c190-123">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-123">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="4c190-124">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-124">GCStart_V1 Event</span></span>  

<span data-ttu-id="4c190-125">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-125">The following table shows the keyword and level.</span></span> <span data-ttu-id="4c190-126">詳細については、「 [CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c190-126">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="4c190-127">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-127">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-128">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-128">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-129">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-129">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-130">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-130">Informational (4)</span></span>|

<span data-ttu-id="4c190-131">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-131">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-132">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-132">Event</span></span>|<span data-ttu-id="4c190-133">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-133">Event ID</span></span>|<span data-ttu-id="4c190-134">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-134">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="4c190-135">1</span><span class="sxs-lookup"><span data-stu-id="4c190-135">1</span></span>|<span data-ttu-id="4c190-136">ガベージ コレクションが開始されました。</span><span class="sxs-lookup"><span data-stu-id="4c190-136">A garbage collection has started.</span></span>|

<span data-ttu-id="4c190-137">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-137">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-138">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-138">Field name</span></span>|<span data-ttu-id="4c190-139">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-139">Data type</span></span>|<span data-ttu-id="4c190-140">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-140">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-141">Count</span><span class="sxs-lookup"><span data-stu-id="4c190-141">Count</span></span>|<span data-ttu-id="4c190-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-142">win:UInt32</span></span>|<span data-ttu-id="4c190-143">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="4c190-143">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="4c190-144">奥行</span><span class="sxs-lookup"><span data-stu-id="4c190-144">Depth</span></span>|<span data-ttu-id="4c190-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-145">win:UInt32</span></span>|<span data-ttu-id="4c190-146">収集されるジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="4c190-146">The generation that is being collected.</span></span>|
|<span data-ttu-id="4c190-147">理由</span><span class="sxs-lookup"><span data-stu-id="4c190-147">Reason</span></span>|<span data-ttu-id="4c190-148">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-148">win:UInt32</span></span>|<span data-ttu-id="4c190-149">ガベージ コレクションが発生した理由:</span><span class="sxs-lookup"><span data-stu-id="4c190-149">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="4c190-150">0x0 - 小さなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="4c190-150">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="4c190-151">0x1 - 強制実行。</span><span class="sxs-lookup"><span data-stu-id="4c190-151">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="4c190-152">0x2 - メモリ不足。</span><span class="sxs-lookup"><span data-stu-id="4c190-152">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="4c190-153">0x3 - 空。</span><span class="sxs-lookup"><span data-stu-id="4c190-153">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="4c190-154">0x4 - 大きなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="4c190-154">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="4c190-155">0x5 - 領域不足 (小さなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="4c190-155">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="4c190-156">0x6 - 領域不足 (大きなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="4c190-156">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="4c190-157">0x7 - 強制実行されるが、ブロッキングとして強制されない。</span><span class="sxs-lookup"><span data-stu-id="4c190-157">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="4c190-158">Type</span><span class="sxs-lookup"><span data-stu-id="4c190-158">Type</span></span>|<span data-ttu-id="4c190-159">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-159">win:UInt32</span></span>|<span data-ttu-id="4c190-160">0x0 - バックグラウンド ガベージ コレクションの外部で発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="4c190-160">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="4c190-161">0x1 - バックグラウンド ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="4c190-161">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="4c190-162">0x2 - バックグラウンド ガベージ コレクションの実行中に発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="4c190-162">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="4c190-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-163">ClrInstanceID</span></span>|<span data-ttu-id="4c190-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-164">win:UInt16</span></span>|<span data-ttu-id="4c190-165">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="4c190-166">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-166">GCEnd_V1 Event</span></span>

<span data-ttu-id="4c190-167">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-167">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-168">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-168">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-169">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-169">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-170">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-170">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-171">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-171">Informational (4)</span></span>|

<span data-ttu-id="4c190-172">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-172">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-173">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-173">Event</span></span>|<span data-ttu-id="4c190-174">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-174">Event ID</span></span>|<span data-ttu-id="4c190-175">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-175">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="4c190-176">2</span><span class="sxs-lookup"><span data-stu-id="4c190-176">2</span></span>|<span data-ttu-id="4c190-177">ガベージ コレクションが終了しました。</span><span class="sxs-lookup"><span data-stu-id="4c190-177">The garbage collection has ended.</span></span>|

<span data-ttu-id="4c190-178">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-178">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-179">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-179">Field name</span></span>|<span data-ttu-id="4c190-180">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-180">Data type</span></span>|<span data-ttu-id="4c190-181">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-181">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-182">Count</span><span class="sxs-lookup"><span data-stu-id="4c190-182">Count</span></span>|<span data-ttu-id="4c190-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-183">win:UInt32</span></span>|<span data-ttu-id="4c190-184">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="4c190-184">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="4c190-185">奥行</span><span class="sxs-lookup"><span data-stu-id="4c190-185">Depth</span></span>|<span data-ttu-id="4c190-186">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-186">win:UInt32</span></span>|<span data-ttu-id="4c190-187">収集されたジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="4c190-187">The generation that was collected.</span></span>|
|<span data-ttu-id="4c190-188">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-188">ClrInstanceID</span></span>|<span data-ttu-id="4c190-189">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-189">win:UInt16</span></span>|<span data-ttu-id="4c190-190">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-190">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="4c190-191">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-191">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="4c190-192">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-192">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-193">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-193">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-194">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-194">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-195">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-195">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-196">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-196">Informational (4)</span></span>|

<span data-ttu-id="4c190-197">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-197">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-198">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-198">Event</span></span>|<span data-ttu-id="4c190-199">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-199">Event ID</span></span>|<span data-ttu-id="4c190-200">[説明]</span><span class="sxs-lookup"><span data-stu-id="4c190-200">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="4c190-201">4</span><span class="sxs-lookup"><span data-stu-id="4c190-201">4</span></span>|<span data-ttu-id="4c190-202">各ガベージ コレクション終了時のヒープの統計情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-202">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="4c190-203">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-203">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-204">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-204">Field name</span></span>|<span data-ttu-id="4c190-205">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-205">Data type</span></span>|<span data-ttu-id="4c190-206">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-206">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-207">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="4c190-207">GenerationSize0</span></span>|<span data-ttu-id="4c190-208">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-208">win:UInt64</span></span>|<span data-ttu-id="4c190-209">ジェネレーション 0 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-209">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="4c190-210">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="4c190-210">TotalPromotedSize0</span></span>|<span data-ttu-id="4c190-211">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-211">win:UInt64</span></span>|<span data-ttu-id="4c190-212">ジェネレーション 0 からジェネレーション 1 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="4c190-212">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="4c190-213">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="4c190-213">GenerationSize1</span></span>|<span data-ttu-id="4c190-214">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-214">win:UInt64</span></span>|<span data-ttu-id="4c190-215">ジェネレーション 1 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-215">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="4c190-216">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="4c190-216">TotalPromotedSize1</span></span>|<span data-ttu-id="4c190-217">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-217">win:UInt64</span></span>|<span data-ttu-id="4c190-218">ジェネレーション 1 からジェネレーション 2 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="4c190-218">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="4c190-219">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="4c190-219">GenerationSize2</span></span>|<span data-ttu-id="4c190-220">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-220">win:UInt64</span></span>|<span data-ttu-id="4c190-221">ジェネレーション 2 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-221">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="4c190-222">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="4c190-222">TotalPromotedSize2</span></span>|<span data-ttu-id="4c190-223">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-223">win:UInt64</span></span>|<span data-ttu-id="4c190-224">最後のガベージ コレクションの後にジェネレーション 2 に残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="4c190-224">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="4c190-225">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="4c190-225">GenerationSize3</span></span>|<span data-ttu-id="4c190-226">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-226">win:UInt64</span></span>|<span data-ttu-id="4c190-227">大きなオブジェクト ヒープのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-227">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="4c190-228">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="4c190-228">TotalPromotedSize3</span></span>|<span data-ttu-id="4c190-229">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-229">win:UInt64</span></span>|<span data-ttu-id="4c190-230">最後のガベージ コレクションの後に大きなオブジェクト ヒープに残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="4c190-230">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="4c190-231">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="4c190-231">FinalizationPromotedSize</span></span>|<span data-ttu-id="4c190-232">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-232">win:UInt64</span></span>|<span data-ttu-id="4c190-233">終了準備が完了しているオブジェクトの合計サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-233">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="4c190-234">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="4c190-234">FinalizationPromotedCount</span></span>|<span data-ttu-id="4c190-235">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-235">win:UInt64</span></span>|<span data-ttu-id="4c190-236">終了準備が完了しているオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="4c190-236">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="4c190-237">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="4c190-237">PinnedObjectCount</span></span>|<span data-ttu-id="4c190-238">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-238">win:UInt32</span></span>|<span data-ttu-id="4c190-239">ピン止めオブジェクト (移動できないオブジェクト) の数。</span><span class="sxs-lookup"><span data-stu-id="4c190-239">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="4c190-240">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="4c190-240">SinkBlockCount</span></span>|<span data-ttu-id="4c190-241">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-241">win:UInt32</span></span>|<span data-ttu-id="4c190-242">使用中の同期ブロックの数。</span><span class="sxs-lookup"><span data-stu-id="4c190-242">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="4c190-243">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="4c190-243">GCHandleCount</span></span>|<span data-ttu-id="4c190-244">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-244">win:UInt32</span></span>|<span data-ttu-id="4c190-245">使用中のガベージ コレクション ハンドルの数。</span><span class="sxs-lookup"><span data-stu-id="4c190-245">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="4c190-246">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-246">ClrInstanceID</span></span>|<span data-ttu-id="4c190-247">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-247">win:UInt16</span></span>|<span data-ttu-id="4c190-248">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-248">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gcheapstats_v2-event"></a><span data-ttu-id="4c190-249">GCHeapStats_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-249">GCHeapStats_V2 Event</span></span>

<span data-ttu-id="4c190-250">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-250">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-251">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-251">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-252">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-252">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-253">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-253">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-254">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-254">Informational (4)</span></span>|

<span data-ttu-id="4c190-255">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-255">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-256">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-256">Event</span></span>|<span data-ttu-id="4c190-257">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-257">Event ID</span></span>|<span data-ttu-id="4c190-258">[説明]</span><span class="sxs-lookup"><span data-stu-id="4c190-258">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V2`|<span data-ttu-id="4c190-259">4</span><span class="sxs-lookup"><span data-stu-id="4c190-259">4</span></span>|<span data-ttu-id="4c190-260">各ガベージ コレクション終了時のヒープの統計情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-260">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="4c190-261">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-261">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-262">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-262">Field name</span></span>|<span data-ttu-id="4c190-263">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-263">Data type</span></span>|<span data-ttu-id="4c190-264">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-264">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-265">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="4c190-265">GenerationSize0</span></span>|<span data-ttu-id="4c190-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-266">win:UInt64</span></span>|<span data-ttu-id="4c190-267">ジェネレーション 0 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-267">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="4c190-268">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="4c190-268">TotalPromotedSize0</span></span>|<span data-ttu-id="4c190-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-269">win:UInt64</span></span>|<span data-ttu-id="4c190-270">ジェネレーション 0 からジェネレーション 1 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="4c190-270">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="4c190-271">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="4c190-271">GenerationSize1</span></span>|<span data-ttu-id="4c190-272">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-272">win:UInt64</span></span>|<span data-ttu-id="4c190-273">ジェネレーション 1 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-273">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="4c190-274">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="4c190-274">TotalPromotedSize1</span></span>|<span data-ttu-id="4c190-275">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-275">win:UInt64</span></span>|<span data-ttu-id="4c190-276">ジェネレーション 1 からジェネレーション 2 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="4c190-276">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="4c190-277">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="4c190-277">GenerationSize2</span></span>|<span data-ttu-id="4c190-278">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-278">win:UInt64</span></span>|<span data-ttu-id="4c190-279">ジェネレーション 2 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-279">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="4c190-280">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="4c190-280">TotalPromotedSize2</span></span>|<span data-ttu-id="4c190-281">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-281">win:UInt64</span></span>|<span data-ttu-id="4c190-282">最後のガベージ コレクションの後にジェネレーション 2 に残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="4c190-282">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="4c190-283">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="4c190-283">GenerationSize3</span></span>|<span data-ttu-id="4c190-284">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-284">win:UInt64</span></span>|<span data-ttu-id="4c190-285">大きなオブジェクト ヒープのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-285">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="4c190-286">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="4c190-286">TotalPromotedSize3</span></span>|<span data-ttu-id="4c190-287">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-287">win:UInt64</span></span>|<span data-ttu-id="4c190-288">最後のガベージ コレクションの後に大きなオブジェクト ヒープに残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="4c190-288">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="4c190-289">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="4c190-289">FinalizationPromotedSize</span></span>|<span data-ttu-id="4c190-290">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-290">win:UInt64</span></span>|<span data-ttu-id="4c190-291">終了準備が完了しているオブジェクトの合計サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-291">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="4c190-292">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="4c190-292">FinalizationPromotedCount</span></span>|<span data-ttu-id="4c190-293">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-293">win:UInt64</span></span>|<span data-ttu-id="4c190-294">終了準備が完了しているオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="4c190-294">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="4c190-295">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="4c190-295">PinnedObjectCount</span></span>|<span data-ttu-id="4c190-296">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-296">win:UInt32</span></span>|<span data-ttu-id="4c190-297">ピン止めオブジェクト (移動できないオブジェクト) の数。</span><span class="sxs-lookup"><span data-stu-id="4c190-297">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="4c190-298">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="4c190-298">SinkBlockCount</span></span>|<span data-ttu-id="4c190-299">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-299">win:UInt32</span></span>|<span data-ttu-id="4c190-300">使用中の同期ブロックの数。</span><span class="sxs-lookup"><span data-stu-id="4c190-300">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="4c190-301">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="4c190-301">GCHandleCount</span></span>|<span data-ttu-id="4c190-302">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-302">win:UInt32</span></span>|<span data-ttu-id="4c190-303">使用中のガベージ コレクション ハンドルの数。</span><span class="sxs-lookup"><span data-stu-id="4c190-303">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="4c190-304">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-304">ClrInstanceID</span></span>|<span data-ttu-id="4c190-305">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-305">win:UInt16</span></span>|<span data-ttu-id="4c190-306">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-306">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="4c190-307">GenerationSize4</span><span class="sxs-lookup"><span data-stu-id="4c190-307">GenerationSize4</span></span>|<span data-ttu-id="4c190-308">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-308">win:UInt64</span></span>|<span data-ttu-id="4c190-309">固定されたオブジェクトヒープのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-309">The size, in bytes, of the pinned object heap.</span></span>|
|<span data-ttu-id="4c190-310">TotalPromotedSize4</span><span class="sxs-lookup"><span data-stu-id="4c190-310">TotalPromotedSize4</span></span>|<span data-ttu-id="4c190-311">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-311">win:UInt64</span></span>|<span data-ttu-id="4c190-312">最後のコレクションの後に固定されたオブジェクトヒープに残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="4c190-312">The number of bytes that survived in the pinned object heap after the last collection.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="4c190-313">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-313">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="4c190-314">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-315">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-315">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-316">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-318">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-318">Informational (4)</span></span>|

<span data-ttu-id="4c190-319">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-319">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-320">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-320">Event</span></span>|<span data-ttu-id="4c190-321">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-321">Event ID</span></span>|<span data-ttu-id="4c190-322">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="4c190-323">5</span><span class="sxs-lookup"><span data-stu-id="4c190-323">5</span></span>|<span data-ttu-id="4c190-324">新しいガベージ コレクション セグメントが作成されました。</span><span class="sxs-lookup"><span data-stu-id="4c190-324">A new garbage collection segment has been created.</span></span> <span data-ttu-id="4c190-325">既に実行されているプロセスでトレースを有効にした場合は、このイベントが各既存セグメントについて発生します。</span><span class="sxs-lookup"><span data-stu-id="4c190-325">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="4c190-326">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-326">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-327">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-327">Field name</span></span>|<span data-ttu-id="4c190-328">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-328">Data type</span></span>|<span data-ttu-id="4c190-329">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-329">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-330">Address</span><span class="sxs-lookup"><span data-stu-id="4c190-330">Address</span></span>|<span data-ttu-id="4c190-331">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-331">win:UInt64</span></span>|<span data-ttu-id="4c190-332">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="4c190-332">The address of the segment.</span></span>|
|<span data-ttu-id="4c190-333">サイズ</span><span class="sxs-lookup"><span data-stu-id="4c190-333">Size</span></span>|<span data-ttu-id="4c190-334">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-334">win:UInt64</span></span>|<span data-ttu-id="4c190-335">セグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="4c190-335">The size of the segment.</span></span>|
|<span data-ttu-id="4c190-336">Type</span><span class="sxs-lookup"><span data-stu-id="4c190-336">Type</span></span>|<span data-ttu-id="4c190-337">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-337">win:UInt32</span></span>|<span data-ttu-id="4c190-338">0x0 - 小さなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="4c190-338">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="4c190-339">0x1 - 大きなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="4c190-339">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="4c190-340">0x2 - 読み取り専用ヒープ。</span><span class="sxs-lookup"><span data-stu-id="4c190-340">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="4c190-341">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-341">ClrInstanceID</span></span>|<span data-ttu-id="4c190-342">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-342">win:UInt16</span></span>|<span data-ttu-id="4c190-343">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-343">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="4c190-344">ガベージ コレクターによって割り当てられるセグメントのサイズは実装に固有であり、定期的な更新プログラムによる場合を含め、いつでも変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4c190-344">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="4c190-345">アプリでは、セグメント サイズを推測することや、特定のセグメント サイズに依存することを絶対に避けてください。また、セグメントの割り当てに使用可能なメモリの量を構成しようとしてもなりません。</span><span class="sxs-lookup"><span data-stu-id="4c190-345">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="4c190-346">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-346">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="4c190-347">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-347">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-348">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-348">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-349">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-349">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-350">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-350">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-351">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-351">Informational (4)</span></span>|

<span data-ttu-id="4c190-352">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-352">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-353">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-353">Event</span></span>|<span data-ttu-id="4c190-354">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-354">Event ID</span></span>|<span data-ttu-id="4c190-355">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-355">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="4c190-356">6</span><span class="sxs-lookup"><span data-stu-id="4c190-356">6</span></span>|<span data-ttu-id="4c190-357">ガベージ コレクション セグメントが解放されました。</span><span class="sxs-lookup"><span data-stu-id="4c190-357">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="4c190-358">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-358">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-359">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-359">Field name</span></span>|<span data-ttu-id="4c190-360">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-360">Data type</span></span>|<span data-ttu-id="4c190-361">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-361">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-362">Address</span><span class="sxs-lookup"><span data-stu-id="4c190-362">Address</span></span>|<span data-ttu-id="4c190-363">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-363">win:UInt64</span></span>|<span data-ttu-id="4c190-364">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="4c190-364">The address of the segment.</span></span>|
|<span data-ttu-id="4c190-365">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-365">ClrInstanceID</span></span>|<span data-ttu-id="4c190-366">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-366">win:UInt16</span></span>|<span data-ttu-id="4c190-367">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-367">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="4c190-368">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-368">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="4c190-369">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-369">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-370">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-370">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-371">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-371">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-372">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-372">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-373">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-373">Informational (4)</span></span>|

<span data-ttu-id="4c190-374">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-374">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-375">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-375">Event</span></span>|<span data-ttu-id="4c190-376">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-376">Event ID</span></span>|<span data-ttu-id="4c190-377">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-377">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="4c190-378">7</span><span class="sxs-lookup"><span data-stu-id="4c190-378">7</span></span>|<span data-ttu-id="4c190-379">共通言語ランタイムの中断からの再開が開始されました。</span><span class="sxs-lookup"><span data-stu-id="4c190-379">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="4c190-380">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="4c190-380">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="4c190-381">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-381">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="4c190-382">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-382">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-383">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-383">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-384">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-384">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-385">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-385">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-386">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-386">Informational (4)</span></span>|

<span data-ttu-id="4c190-387">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-387">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-388">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-388">Event</span></span>|<span data-ttu-id="4c190-389">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-389">Event Id</span></span>|<span data-ttu-id="4c190-390">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-390">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="4c190-391">3</span><span class="sxs-lookup"><span data-stu-id="4c190-391">3</span></span>|<span data-ttu-id="4c190-392">共通言語ランタイムの中断からの再開が終了しました。</span><span class="sxs-lookup"><span data-stu-id="4c190-392">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="4c190-393">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="4c190-393">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="4c190-394">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-394">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="4c190-395">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-395">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-396">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-396">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-397">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-397">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-398">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-398">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-399">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-399">Informational (4)</span></span>|

<span data-ttu-id="4c190-400">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-400">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-401">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-401">Event</span></span>|<span data-ttu-id="4c190-402">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-402">Event ID</span></span>|<span data-ttu-id="4c190-403">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-403">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="4c190-404">9</span><span class="sxs-lookup"><span data-stu-id="4c190-404">9</span></span>|<span data-ttu-id="4c190-405">ガベージ コレクションのための実行エンジンの中断の開始。</span><span class="sxs-lookup"><span data-stu-id="4c190-405">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="4c190-406">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-406">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-407">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-407">Field name</span></span>|<span data-ttu-id="4c190-408">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-408">Data type</span></span>|<span data-ttu-id="4c190-409">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-409">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-410">原因</span><span class="sxs-lookup"><span data-stu-id="4c190-410">Reason</span></span>|<span data-ttu-id="4c190-411">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-411">win:UInt16</span></span>|<span data-ttu-id="4c190-412">0x0 - その他。</span><span class="sxs-lookup"><span data-stu-id="4c190-412">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="4c190-413">0x1 - ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="4c190-413">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="4c190-414">0x2 - アプリケーション ドメインのシャットダウン。</span><span class="sxs-lookup"><span data-stu-id="4c190-414">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="4c190-415">0x3 - コード ピッチ。</span><span class="sxs-lookup"><span data-stu-id="4c190-415">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="4c190-416">0x4 - シャットダウン。</span><span class="sxs-lookup"><span data-stu-id="4c190-416">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="4c190-417">0x5 - デバッガー。</span><span class="sxs-lookup"><span data-stu-id="4c190-417">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="4c190-418">0x6 - ガベージ コレクションの準備。</span><span class="sxs-lookup"><span data-stu-id="4c190-418">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="4c190-419">データの個数</span><span class="sxs-lookup"><span data-stu-id="4c190-419">Count</span></span>|<span data-ttu-id="4c190-420">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-420">win:UInt32</span></span>|<span data-ttu-id="4c190-421">その時点の GC カウント。</span><span class="sxs-lookup"><span data-stu-id="4c190-421">The GC count at the time.</span></span> <span data-ttu-id="4c190-422">通常、この後に後続の GC 開始イベントが表示され、そのカウントは、ガベージ コレクション中に、GC インデックスが増えるため、このカウント + 1 になります。</span><span class="sxs-lookup"><span data-stu-id="4c190-422">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="4c190-423">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-423">ClrInstanceID</span></span>|<span data-ttu-id="4c190-424">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-424">win:UInt16</span></span>|<span data-ttu-id="4c190-425">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-425">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="4c190-426">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-426">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="4c190-427">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-427">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-428">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-428">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-429">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-429">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-431">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-431">Informational (4)</span></span>|

<span data-ttu-id="4c190-432">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-432">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-433">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-433">Event</span></span>|<span data-ttu-id="4c190-434">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-434">Event ID</span></span>|<span data-ttu-id="4c190-435">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-435">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="4c190-436">8</span><span class="sxs-lookup"><span data-stu-id="4c190-436">8</span></span>|<span data-ttu-id="4c190-437">ガベージ コレクションのための実行エンジンの中断の終了。</span><span class="sxs-lookup"><span data-stu-id="4c190-437">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="4c190-438">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="4c190-438">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="4c190-439">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-439">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="4c190-440">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-440">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-441">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-441">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-442">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-442">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-443">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-443">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-444">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-444">Informational (4)</span></span>|

<span data-ttu-id="4c190-445">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-445">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-446">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-446">Event</span></span>|<span data-ttu-id="4c190-447">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-447">Event ID</span></span>|<span data-ttu-id="4c190-448">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-448">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="4c190-449">10</span><span class="sxs-lookup"><span data-stu-id="4c190-449">10</span></span>|<span data-ttu-id="4c190-450">約 100 KB が割り当てられるたび。</span><span class="sxs-lookup"><span data-stu-id="4c190-450">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="4c190-451">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-451">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-452">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-452">Field name</span></span>|<span data-ttu-id="4c190-453">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-453">Data type</span></span>|<span data-ttu-id="4c190-454">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-454">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-455">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="4c190-455">AllocationAmount</span></span>|<span data-ttu-id="4c190-456">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-456">win:UInt32</span></span>|<span data-ttu-id="4c190-457">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-457">The allocation size, in bytes.</span></span> <span data-ttu-id="4c190-458">この値は、ULONG (4,294,967,295 バイト) の長さより短い割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="4c190-458">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="4c190-459">割り当てがこれを超える場合、このフィールドには切り捨てられた値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c190-459">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="4c190-460">非常に大きな割り当てには `AllocationAmount64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c190-460">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="4c190-461">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="4c190-461">AllocationKind</span></span>|<span data-ttu-id="4c190-462">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-462">win:UInt32</span></span>|<span data-ttu-id="4c190-463">0x0 - 小さなオブジェクトの割り当て (小さなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="4c190-463">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="4c190-464">0x1 - 大きなオブジェクトの割り当て (大きなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="4c190-464">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="4c190-465">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-465">ClrInstanceID</span></span>|<span data-ttu-id="4c190-466">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-466">win:UInt16</span></span>|<span data-ttu-id="4c190-467">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-467">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="4c190-468">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="4c190-468">AllocationAmount64</span></span>|<span data-ttu-id="4c190-469">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-469">win:UInt64</span></span>|<span data-ttu-id="4c190-470">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-470">The allocation size, in bytes.</span></span> <span data-ttu-id="4c190-471">この値は非常に大きな割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="4c190-471">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="4c190-472">TypeId</span><span class="sxs-lookup"><span data-stu-id="4c190-472">TypeId</span></span>|<span data-ttu-id="4c190-473">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="4c190-473">win:Pointer</span></span>|<span data-ttu-id="4c190-474">MethodTable のアドレス。</span><span class="sxs-lookup"><span data-stu-id="4c190-474">The address of the MethodTable.</span></span> <span data-ttu-id="4c190-475">このイベント中に複数の型のオブジェクトが割り当てられた場合、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) に対応する MethodTable のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="4c190-475">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="4c190-476">TypeName</span><span class="sxs-lookup"><span data-stu-id="4c190-476">TypeName</span></span>|<span data-ttu-id="4c190-477">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4c190-477">win:UnicodeString</span></span>|<span data-ttu-id="4c190-478">割り当てられた型の名前。</span><span class="sxs-lookup"><span data-stu-id="4c190-478">The name of the type that was allocated.</span></span> <span data-ttu-id="4c190-479">このイベント中に複数の型のオブジェクトが割り当てられた場合は、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) の型です。</span><span class="sxs-lookup"><span data-stu-id="4c190-479">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="4c190-480">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="4c190-480">HeapIndex</span></span>|<span data-ttu-id="4c190-481">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-481">win:UInt32</span></span>|<span data-ttu-id="4c190-482">オブジェクトが割り当てられたヒープ。</span><span class="sxs-lookup"><span data-stu-id="4c190-482">The heap where the object was allocated.</span></span> <span data-ttu-id="4c190-483">ワークステーションのガベージ コレクションと共に実行する場合、この値は 0 (ゼロ) になります。</span><span class="sxs-lookup"><span data-stu-id="4c190-483">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcallocationtick_v3-event"></a><span data-ttu-id="4c190-484">GCAllocationTick_V3 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-484">GCAllocationTick_V3 Event</span></span>

<span data-ttu-id="4c190-485">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-485">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-486">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-486">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-487">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-487">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-488">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-488">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-489">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-489">Informational (4)</span></span>|

<span data-ttu-id="4c190-490">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-490">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-491">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-491">Event</span></span>|<span data-ttu-id="4c190-492">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-492">Event ID</span></span>|<span data-ttu-id="4c190-493">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-493">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V3`|<span data-ttu-id="4c190-494">10</span><span class="sxs-lookup"><span data-stu-id="4c190-494">10</span></span>|<span data-ttu-id="4c190-495">約 100 KB が割り当てられるたび。</span><span class="sxs-lookup"><span data-stu-id="4c190-495">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="4c190-496">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-496">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-497">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-497">Field name</span></span>|<span data-ttu-id="4c190-498">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-498">Data type</span></span>|<span data-ttu-id="4c190-499">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-499">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-500">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="4c190-500">AllocationAmount</span></span>|<span data-ttu-id="4c190-501">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-501">win:UInt32</span></span>|<span data-ttu-id="4c190-502">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-502">The allocation size, in bytes.</span></span> <span data-ttu-id="4c190-503">この値は、ULONG (4,294,967,295 バイト) の長さより短い割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="4c190-503">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="4c190-504">割り当てがこれを超える場合、このフィールドには切り捨てられた値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4c190-504">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="4c190-505">非常に大きな割り当てには `AllocationAmount64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c190-505">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="4c190-506">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="4c190-506">AllocationKind</span></span>|<span data-ttu-id="4c190-507">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-507">win:UInt32</span></span>|<span data-ttu-id="4c190-508">0x0 - 小さなオブジェクトの割り当て (小さなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="4c190-508">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="4c190-509">0x1 - 大きなオブジェクトの割り当て (大きなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="4c190-509">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="4c190-510">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-510">ClrInstanceID</span></span>|<span data-ttu-id="4c190-511">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-511">win:UInt16</span></span>|<span data-ttu-id="4c190-512">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-512">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="4c190-513">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="4c190-513">AllocationAmount64</span></span>|<span data-ttu-id="4c190-514">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4c190-514">win:UInt64</span></span>|<span data-ttu-id="4c190-515">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="4c190-515">The allocation size, in bytes.</span></span> <span data-ttu-id="4c190-516">この値は非常に大きな割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="4c190-516">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="4c190-517">TypeId</span><span class="sxs-lookup"><span data-stu-id="4c190-517">TypeId</span></span>|<span data-ttu-id="4c190-518">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="4c190-518">win:Pointer</span></span>|<span data-ttu-id="4c190-519">MethodTable のアドレス。</span><span class="sxs-lookup"><span data-stu-id="4c190-519">The address of the MethodTable.</span></span> <span data-ttu-id="4c190-520">このイベント中に複数の型のオブジェクトが割り当てられた場合、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) に対応する MethodTable のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="4c190-520">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="4c190-521">TypeName</span><span class="sxs-lookup"><span data-stu-id="4c190-521">TypeName</span></span>|<span data-ttu-id="4c190-522">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4c190-522">win:UnicodeString</span></span>|<span data-ttu-id="4c190-523">割り当てられた型の名前。</span><span class="sxs-lookup"><span data-stu-id="4c190-523">The name of the type that was allocated.</span></span> <span data-ttu-id="4c190-524">このイベント中に複数の型のオブジェクトが割り当てられた場合は、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) の型です。</span><span class="sxs-lookup"><span data-stu-id="4c190-524">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="4c190-525">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="4c190-525">HeapIndex</span></span>|<span data-ttu-id="4c190-526">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-526">win:UInt32</span></span>|<span data-ttu-id="4c190-527">オブジェクトが割り当てられたヒープ。</span><span class="sxs-lookup"><span data-stu-id="4c190-527">The heap where the object was allocated.</span></span> <span data-ttu-id="4c190-528">ワークステーションのガベージ コレクションと共に実行する場合、この値は 0 (ゼロ) になります。</span><span class="sxs-lookup"><span data-stu-id="4c190-528">This value is 0 (zero) when running with workstation garbage collection.</span></span>|
|<span data-ttu-id="4c190-529">Address</span><span class="sxs-lookup"><span data-stu-id="4c190-529">Address</span></span>|<span data-ttu-id="4c190-530">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="4c190-530">win:Pointer</span></span>|<span data-ttu-id="4c190-531">最後に割り当てられたオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="4c190-531">The address of the last allocated object.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="4c190-532">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-532">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="4c190-533">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-533">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-534">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-534">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-535">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-535">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-536">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-536">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-537">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-537">Informational (4)</span></span>|

<span data-ttu-id="4c190-538">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-538">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-539">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-539">Event</span></span>|<span data-ttu-id="4c190-540">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-540">Event ID</span></span>|<span data-ttu-id="4c190-541">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-541">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="4c190-542">14</span><span class="sxs-lookup"><span data-stu-id="4c190-542">14</span></span>|<span data-ttu-id="4c190-543">ファイナライザーの実行の開始。</span><span class="sxs-lookup"><span data-stu-id="4c190-543">The start of running finalizers.</span></span>|

<span data-ttu-id="4c190-544">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="4c190-544">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="4c190-545">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-545">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="4c190-546">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-546">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-547">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-547">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-548">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-548">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-549">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-549">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-550">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-550">Informational (4)</span></span>|

<span data-ttu-id="4c190-551">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-551">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-552">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-552">Event</span></span>|<span data-ttu-id="4c190-553">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-553">Event ID</span></span>|<span data-ttu-id="4c190-554">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-554">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="4c190-555">13</span><span class="sxs-lookup"><span data-stu-id="4c190-555">13</span></span>|<span data-ttu-id="4c190-556">ファイナライザーの実行の終了。</span><span class="sxs-lookup"><span data-stu-id="4c190-556">The end of running finalizers.</span></span>|

<span data-ttu-id="4c190-557">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-557">The following table shows the event data:</span></span>

|<span data-ttu-id="4c190-558">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c190-558">Field name</span></span>|<span data-ttu-id="4c190-559">データ型</span><span class="sxs-lookup"><span data-stu-id="4c190-559">Data type</span></span>|<span data-ttu-id="4c190-560">説明</span><span class="sxs-lookup"><span data-stu-id="4c190-560">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4c190-561">Count</span><span class="sxs-lookup"><span data-stu-id="4c190-561">Count</span></span>|<span data-ttu-id="4c190-562">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4c190-562">win:UInt32</span></span>|<span data-ttu-id="4c190-563">実行されたファイナライザーの数。</span><span class="sxs-lookup"><span data-stu-id="4c190-563">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="4c190-564">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4c190-564">ClrInstanceID</span></span>|<span data-ttu-id="4c190-565">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4c190-565">win:UInt16</span></span>|<span data-ttu-id="4c190-566">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="4c190-566">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="4c190-567">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-567">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="4c190-568">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-568">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-569">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-569">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-570">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-570">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-571">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-571">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-572">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-572">Informational (4)</span></span>|
|<span data-ttu-id="4c190-573">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4c190-573">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4c190-574">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-574">Informational (4)</span></span>|

<span data-ttu-id="4c190-575">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-575">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-576">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-576">Event</span></span>|<span data-ttu-id="4c190-577">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-577">Event ID</span></span>|<span data-ttu-id="4c190-578">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-578">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="4c190-579">11</span><span class="sxs-lookup"><span data-stu-id="4c190-579">11</span></span>|<span data-ttu-id="4c190-580">同時実行ガベージ コレクション スレッドが作成されました。</span><span class="sxs-lookup"><span data-stu-id="4c190-580">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="4c190-581">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="4c190-581">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="4c190-582">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-582">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="4c190-583">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-583">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4c190-584">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="4c190-584">Keyword for raising the event</span></span>|<span data-ttu-id="4c190-585">Level</span><span class="sxs-lookup"><span data-stu-id="4c190-585">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4c190-586">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4c190-586">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4c190-587">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-587">Informational (4)</span></span>|
|<span data-ttu-id="4c190-588">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4c190-588">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4c190-589">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="4c190-589">Informational (4)</span></span>|

<span data-ttu-id="4c190-590">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4c190-590">The following table shows the event information:</span></span>

|<span data-ttu-id="4c190-591">Event</span><span class="sxs-lookup"><span data-stu-id="4c190-591">Event</span></span>|<span data-ttu-id="4c190-592">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c190-592">Event ID</span></span>|<span data-ttu-id="4c190-593">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="4c190-593">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="4c190-594">12</span><span class="sxs-lookup"><span data-stu-id="4c190-594">12</span></span>|<span data-ttu-id="4c190-595">同時実行ガベージ コレクションスレッドが終了しました。</span><span class="sxs-lookup"><span data-stu-id="4c190-595">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="4c190-596">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="4c190-596">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c190-597">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c190-597">See also</span></span>

- [<span data-ttu-id="4c190-598">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="4c190-598">CLR ETW Events</span></span>](clr-etw-events.md)
