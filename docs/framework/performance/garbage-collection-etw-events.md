---
title: ガベージ コレクション ETW イベント
description: ガベージコレクション ETW イベントに関する詳細情報を表示します。 説明されているイベントには、GCStart_V1、GCEnd_V1、GCHeapStats_V1、GCCreateSegment_V1 などがあります。
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 58ad874ef6a12c18c404640aa66577c391573534
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309743"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="36032-104">ガベージ コレクション ETW イベント</span><span class="sxs-lookup"><span data-stu-id="36032-104">Garbage Collection ETW Events</span></span>

<span data-ttu-id="36032-105">これらのイベントは、ガベージ コレクションに関連する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="36032-105">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="36032-106">ガベージ コレクションが実行された回数、ガベージ コレクションの間に解放されたメモリの量など、診断やデバッグに役立つ情報を入手できます。</span><span class="sxs-lookup"><span data-stu-id="36032-106">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="36032-107">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="36032-107">This category consists of the following events:</span></span>

- [<span data-ttu-id="36032-108">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-108">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="36032-109">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-109">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="36032-110">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-110">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="36032-111">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-111">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="36032-112">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-112">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="36032-113">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-113">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="36032-114">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-114">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="36032-115">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-115">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="36032-116">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-116">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="36032-117">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-117">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="36032-118">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-118">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="36032-119">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-119">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="36032-120">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-120">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="36032-121">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-121">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="36032-122">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-122">GCStart_V1 Event</span></span>  

<span data-ttu-id="36032-123">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-123">The following table shows the keyword and level.</span></span> <span data-ttu-id="36032-124">詳細については、「 [CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36032-124">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="36032-125">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-125">Keyword for raising the event</span></span>|<span data-ttu-id="36032-126">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-126">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-127">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-127">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-128">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-128">Informational (4)</span></span>|

<span data-ttu-id="36032-129">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-129">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-130">Event</span><span class="sxs-lookup"><span data-stu-id="36032-130">Event</span></span>|<span data-ttu-id="36032-131">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-131">Event ID</span></span>|<span data-ttu-id="36032-132">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-132">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="36032-133">1</span><span class="sxs-lookup"><span data-stu-id="36032-133">1</span></span>|<span data-ttu-id="36032-134">ガベージ コレクションが開始されました。</span><span class="sxs-lookup"><span data-stu-id="36032-134">A garbage collection has started.</span></span>|

<span data-ttu-id="36032-135">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-135">The following table shows the event data:</span></span>

|<span data-ttu-id="36032-136">フィールド名</span><span class="sxs-lookup"><span data-stu-id="36032-136">Field name</span></span>|<span data-ttu-id="36032-137">データ型</span><span class="sxs-lookup"><span data-stu-id="36032-137">Data type</span></span>|<span data-ttu-id="36032-138">説明</span><span class="sxs-lookup"><span data-stu-id="36032-138">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="36032-139">Count</span><span class="sxs-lookup"><span data-stu-id="36032-139">Count</span></span>|<span data-ttu-id="36032-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-140">win:UInt32</span></span>|<span data-ttu-id="36032-141">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="36032-141">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="36032-142">奥行き</span><span class="sxs-lookup"><span data-stu-id="36032-142">Depth</span></span>|<span data-ttu-id="36032-143">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-143">win:UInt32</span></span>|<span data-ttu-id="36032-144">収集されるジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="36032-144">The generation that is being collected.</span></span>|
|<span data-ttu-id="36032-145">理由</span><span class="sxs-lookup"><span data-stu-id="36032-145">Reason</span></span>|<span data-ttu-id="36032-146">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-146">win:UInt32</span></span>|<span data-ttu-id="36032-147">ガベージ コレクションが発生した理由:</span><span class="sxs-lookup"><span data-stu-id="36032-147">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="36032-148">0x0 - 小さなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="36032-148">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="36032-149">0x1 - 強制実行。</span><span class="sxs-lookup"><span data-stu-id="36032-149">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="36032-150">0x2 - メモリ不足。</span><span class="sxs-lookup"><span data-stu-id="36032-150">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="36032-151">0x3 - 空。</span><span class="sxs-lookup"><span data-stu-id="36032-151">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="36032-152">0x4 - 大きなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="36032-152">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="36032-153">0x5 - 領域不足 (小さなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="36032-153">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="36032-154">0x6 - 領域不足 (大きなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="36032-154">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="36032-155">0x7 - 強制実行されるが、ブロッキングとして強制されない。</span><span class="sxs-lookup"><span data-stu-id="36032-155">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="36032-156">Type</span><span class="sxs-lookup"><span data-stu-id="36032-156">Type</span></span>|<span data-ttu-id="36032-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-157">win:UInt32</span></span>|<span data-ttu-id="36032-158">0x0 - バックグラウンド ガベージ コレクションの外部で発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="36032-158">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="36032-159">0x1 - バックグラウンド ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="36032-159">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="36032-160">0x2 - バックグラウンド ガベージ コレクションの実行中に発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="36032-160">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="36032-161">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="36032-161">ClrInstanceID</span></span>|<span data-ttu-id="36032-162">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="36032-162">win:UInt16</span></span>|<span data-ttu-id="36032-163">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="36032-163">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="36032-164">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-164">GCEnd_V1 Event</span></span>

<span data-ttu-id="36032-165">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-165">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-166">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-166">Keyword for raising the event</span></span>|<span data-ttu-id="36032-167">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-167">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-168">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-168">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-169">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-169">Informational (4)</span></span>|

<span data-ttu-id="36032-170">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-170">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-171">Event</span><span class="sxs-lookup"><span data-stu-id="36032-171">Event</span></span>|<span data-ttu-id="36032-172">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-172">Event ID</span></span>|<span data-ttu-id="36032-173">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-173">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="36032-174">2</span><span class="sxs-lookup"><span data-stu-id="36032-174">2</span></span>|<span data-ttu-id="36032-175">ガベージ コレクションが終了しました。</span><span class="sxs-lookup"><span data-stu-id="36032-175">The garbage collection has ended.</span></span>|

<span data-ttu-id="36032-176">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-176">The following table shows the event data:</span></span>

|<span data-ttu-id="36032-177">フィールド名</span><span class="sxs-lookup"><span data-stu-id="36032-177">Field name</span></span>|<span data-ttu-id="36032-178">データ型</span><span class="sxs-lookup"><span data-stu-id="36032-178">Data type</span></span>|<span data-ttu-id="36032-179">説明</span><span class="sxs-lookup"><span data-stu-id="36032-179">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="36032-180">Count</span><span class="sxs-lookup"><span data-stu-id="36032-180">Count</span></span>|<span data-ttu-id="36032-181">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-181">win:UInt32</span></span>|<span data-ttu-id="36032-182">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="36032-182">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="36032-183">奥行き</span><span class="sxs-lookup"><span data-stu-id="36032-183">Depth</span></span>|<span data-ttu-id="36032-184">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-184">win:UInt32</span></span>|<span data-ttu-id="36032-185">収集されたジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="36032-185">The generation that was collected.</span></span>|
|<span data-ttu-id="36032-186">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="36032-186">ClrInstanceID</span></span>|<span data-ttu-id="36032-187">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="36032-187">win:UInt16</span></span>|<span data-ttu-id="36032-188">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="36032-188">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="36032-189">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-189">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="36032-190">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-190">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-191">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-191">Keyword for raising the event</span></span>|<span data-ttu-id="36032-192">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-192">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-194">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-194">Informational (4)</span></span>|

<span data-ttu-id="36032-195">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-195">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-196">Event</span><span class="sxs-lookup"><span data-stu-id="36032-196">Event</span></span>|<span data-ttu-id="36032-197">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-197">Event ID</span></span>|<span data-ttu-id="36032-198">説明</span><span class="sxs-lookup"><span data-stu-id="36032-198">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="36032-199">4</span><span class="sxs-lookup"><span data-stu-id="36032-199">4</span></span>|<span data-ttu-id="36032-200">各ガベージ コレクション終了時のヒープの統計情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-200">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="36032-201">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-201">The following table shows the event data:</span></span>

|<span data-ttu-id="36032-202">フィールド名</span><span class="sxs-lookup"><span data-stu-id="36032-202">Field name</span></span>|<span data-ttu-id="36032-203">データ型</span><span class="sxs-lookup"><span data-stu-id="36032-203">Data type</span></span>|<span data-ttu-id="36032-204">説明</span><span class="sxs-lookup"><span data-stu-id="36032-204">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="36032-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="36032-205">GenerationSize0</span></span>|<span data-ttu-id="36032-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-206">win:UInt64</span></span>|<span data-ttu-id="36032-207">ジェネレーション 0 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="36032-207">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="36032-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="36032-208">TotalPromotedSize0</span></span>|<span data-ttu-id="36032-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-209">win:UInt64</span></span>|<span data-ttu-id="36032-210">ジェネレーション 0 からジェネレーション 1 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="36032-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="36032-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="36032-211">GenerationSize1</span></span>|<span data-ttu-id="36032-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-212">win:UInt64</span></span>|<span data-ttu-id="36032-213">ジェネレーション 1 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="36032-213">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="36032-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="36032-214">TotalPromotedSize1</span></span>|<span data-ttu-id="36032-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-215">win:UInt64</span></span>|<span data-ttu-id="36032-216">ジェネレーション 1 からジェネレーション 2 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="36032-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="36032-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="36032-217">GenerationSize2</span></span>|<span data-ttu-id="36032-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-218">win:UInt64</span></span>|<span data-ttu-id="36032-219">ジェネレーション 2 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="36032-219">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="36032-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="36032-220">TotalPromotedSize2</span></span>|<span data-ttu-id="36032-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-221">win:UInt64</span></span>|<span data-ttu-id="36032-222">最後のガベージ コレクションの後にジェネレーション 2 に残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="36032-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="36032-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="36032-223">GenerationSize3</span></span>|<span data-ttu-id="36032-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-224">win:UInt64</span></span>|<span data-ttu-id="36032-225">大きなオブジェクト ヒープのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="36032-225">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="36032-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="36032-226">TotalPromotedSize3</span></span>|<span data-ttu-id="36032-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-227">win:UInt64</span></span>|<span data-ttu-id="36032-228">最後のガベージ コレクションの後に大きなオブジェクト ヒープに残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="36032-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="36032-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="36032-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="36032-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-230">win:UInt64</span></span>|<span data-ttu-id="36032-231">終了準備が完了しているオブジェクトの合計サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="36032-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="36032-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="36032-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="36032-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-233">win:UInt64</span></span>|<span data-ttu-id="36032-234">終了準備が完了しているオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="36032-234">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="36032-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="36032-235">PinnedObjectCount</span></span>|<span data-ttu-id="36032-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-236">win:UInt32</span></span>|<span data-ttu-id="36032-237">ピン止めオブジェクト (移動できないオブジェクト) の数。</span><span class="sxs-lookup"><span data-stu-id="36032-237">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="36032-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="36032-238">SinkBlockCount</span></span>|<span data-ttu-id="36032-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-239">win:UInt32</span></span>|<span data-ttu-id="36032-240">使用中の同期ブロックの数。</span><span class="sxs-lookup"><span data-stu-id="36032-240">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="36032-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="36032-241">GCHandleCount</span></span>|<span data-ttu-id="36032-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-242">win:UInt32</span></span>|<span data-ttu-id="36032-243">使用中のガベージ コレクション ハンドルの数。</span><span class="sxs-lookup"><span data-stu-id="36032-243">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="36032-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="36032-244">ClrInstanceID</span></span>|<span data-ttu-id="36032-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="36032-245">win:UInt16</span></span>|<span data-ttu-id="36032-246">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="36032-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="36032-247">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-247">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="36032-248">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-248">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-249">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-249">Keyword for raising the event</span></span>|<span data-ttu-id="36032-250">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-250">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-251">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-251">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-252">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-252">Informational (4)</span></span>|

<span data-ttu-id="36032-253">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-253">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-254">Event</span><span class="sxs-lookup"><span data-stu-id="36032-254">Event</span></span>|<span data-ttu-id="36032-255">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-255">Event ID</span></span>|<span data-ttu-id="36032-256">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-256">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="36032-257">5</span><span class="sxs-lookup"><span data-stu-id="36032-257">5</span></span>|<span data-ttu-id="36032-258">新しいガベージ コレクション セグメントが作成されました。</span><span class="sxs-lookup"><span data-stu-id="36032-258">A new garbage collection segment has been created.</span></span> <span data-ttu-id="36032-259">既に実行されているプロセスでトレースを有効にした場合は、このイベントが各既存セグメントについて発生します。</span><span class="sxs-lookup"><span data-stu-id="36032-259">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="36032-260">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-260">The following table shows the event data:</span></span>

|<span data-ttu-id="36032-261">フィールド名</span><span class="sxs-lookup"><span data-stu-id="36032-261">Field name</span></span>|<span data-ttu-id="36032-262">データ型</span><span class="sxs-lookup"><span data-stu-id="36032-262">Data type</span></span>|<span data-ttu-id="36032-263">説明</span><span class="sxs-lookup"><span data-stu-id="36032-263">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="36032-264">Address</span><span class="sxs-lookup"><span data-stu-id="36032-264">Address</span></span>|<span data-ttu-id="36032-265">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-265">win:UInt64</span></span>|<span data-ttu-id="36032-266">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="36032-266">The address of the segment.</span></span>|
|<span data-ttu-id="36032-267">サイズ</span><span class="sxs-lookup"><span data-stu-id="36032-267">Size</span></span>|<span data-ttu-id="36032-268">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-268">win:UInt64</span></span>|<span data-ttu-id="36032-269">セグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="36032-269">The size of the segment.</span></span>|
|<span data-ttu-id="36032-270">Type</span><span class="sxs-lookup"><span data-stu-id="36032-270">Type</span></span>|<span data-ttu-id="36032-271">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-271">win:UInt32</span></span>|<span data-ttu-id="36032-272">0x0 - 小さなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="36032-272">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="36032-273">0x1 - 大きなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="36032-273">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="36032-274">0x2 - 読み取り専用ヒープ。</span><span class="sxs-lookup"><span data-stu-id="36032-274">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="36032-275">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="36032-275">ClrInstanceID</span></span>|<span data-ttu-id="36032-276">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="36032-276">win:UInt16</span></span>|<span data-ttu-id="36032-277">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="36032-277">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="36032-278">ガベージ コレクターによって割り当てられるセグメントのサイズは実装に固有であり、定期的な更新プログラムによる場合を含め、いつでも変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="36032-278">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="36032-279">アプリでは、セグメント サイズを推測することや、特定のセグメント サイズに依存することを絶対に避けてください。また、セグメントの割り当てに使用可能なメモリの量を構成しようとしてもなりません。</span><span class="sxs-lookup"><span data-stu-id="36032-279">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="36032-280">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-280">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="36032-281">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-281">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-282">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-282">Keyword for raising the event</span></span>|<span data-ttu-id="36032-283">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-283">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-284">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-284">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-285">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-285">Informational (4)</span></span>|

<span data-ttu-id="36032-286">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-286">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-287">Event</span><span class="sxs-lookup"><span data-stu-id="36032-287">Event</span></span>|<span data-ttu-id="36032-288">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-288">Event ID</span></span>|<span data-ttu-id="36032-289">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-289">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="36032-290">6</span><span class="sxs-lookup"><span data-stu-id="36032-290">6</span></span>|<span data-ttu-id="36032-291">ガベージ コレクション セグメントが解放されました。</span><span class="sxs-lookup"><span data-stu-id="36032-291">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="36032-292">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-292">The following table shows the event data:</span></span>

|<span data-ttu-id="36032-293">フィールド名</span><span class="sxs-lookup"><span data-stu-id="36032-293">Field name</span></span>|<span data-ttu-id="36032-294">データ型</span><span class="sxs-lookup"><span data-stu-id="36032-294">Data type</span></span>|<span data-ttu-id="36032-295">説明</span><span class="sxs-lookup"><span data-stu-id="36032-295">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="36032-296">Address</span><span class="sxs-lookup"><span data-stu-id="36032-296">Address</span></span>|<span data-ttu-id="36032-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-297">win:UInt64</span></span>|<span data-ttu-id="36032-298">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="36032-298">The address of the segment.</span></span>|
|<span data-ttu-id="36032-299">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="36032-299">ClrInstanceID</span></span>|<span data-ttu-id="36032-300">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="36032-300">win:UInt16</span></span>|<span data-ttu-id="36032-301">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="36032-301">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="36032-302">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-302">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="36032-303">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-303">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-304">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-304">Keyword for raising the event</span></span>|<span data-ttu-id="36032-305">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-305">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-306">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-306">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-307">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-307">Informational (4)</span></span>|

<span data-ttu-id="36032-308">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-308">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-309">Event</span><span class="sxs-lookup"><span data-stu-id="36032-309">Event</span></span>|<span data-ttu-id="36032-310">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-310">Event ID</span></span>|<span data-ttu-id="36032-311">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-311">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="36032-312">7</span><span class="sxs-lookup"><span data-stu-id="36032-312">7</span></span>|<span data-ttu-id="36032-313">共通言語ランタイムの中断からの再開が開始されました。</span><span class="sxs-lookup"><span data-stu-id="36032-313">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="36032-314">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="36032-314">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="36032-315">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-315">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="36032-316">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-316">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-317">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-317">Keyword for raising the event</span></span>|<span data-ttu-id="36032-318">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-318">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-319">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-319">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-320">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-320">Informational (4)</span></span>|

<span data-ttu-id="36032-321">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-321">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-322">Event</span><span class="sxs-lookup"><span data-stu-id="36032-322">Event</span></span>|<span data-ttu-id="36032-323">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-323">Event Id</span></span>|<span data-ttu-id="36032-324">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-324">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="36032-325">3</span><span class="sxs-lookup"><span data-stu-id="36032-325">3</span></span>|<span data-ttu-id="36032-326">共通言語ランタイムの中断からの再開が終了しました。</span><span class="sxs-lookup"><span data-stu-id="36032-326">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="36032-327">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="36032-327">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="36032-328">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-328">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="36032-329">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-329">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-330">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-330">Keyword for raising the event</span></span>|<span data-ttu-id="36032-331">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-331">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-332">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-332">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-333">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-333">Informational (4)</span></span>|

<span data-ttu-id="36032-334">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-334">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-335">Event</span><span class="sxs-lookup"><span data-stu-id="36032-335">Event</span></span>|<span data-ttu-id="36032-336">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-336">Event ID</span></span>|<span data-ttu-id="36032-337">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-337">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="36032-338">9</span><span class="sxs-lookup"><span data-stu-id="36032-338">9</span></span>|<span data-ttu-id="36032-339">ガベージ コレクションのための実行エンジンの中断の開始。</span><span class="sxs-lookup"><span data-stu-id="36032-339">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="36032-340">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-340">The following table shows the event data:</span></span>

|<span data-ttu-id="36032-341">フィールド名</span><span class="sxs-lookup"><span data-stu-id="36032-341">Field name</span></span>|<span data-ttu-id="36032-342">データ型</span><span class="sxs-lookup"><span data-stu-id="36032-342">Data type</span></span>|<span data-ttu-id="36032-343">説明</span><span class="sxs-lookup"><span data-stu-id="36032-343">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="36032-344">原因</span><span class="sxs-lookup"><span data-stu-id="36032-344">Reason</span></span>|<span data-ttu-id="36032-345">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="36032-345">win:UInt16</span></span>|<span data-ttu-id="36032-346">0x0 - その他。</span><span class="sxs-lookup"><span data-stu-id="36032-346">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="36032-347">0x1 - ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="36032-347">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="36032-348">0x2 - アプリケーション ドメインのシャットダウン。</span><span class="sxs-lookup"><span data-stu-id="36032-348">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="36032-349">0x3 - コード ピッチ。</span><span class="sxs-lookup"><span data-stu-id="36032-349">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="36032-350">0x4 - シャットダウン。</span><span class="sxs-lookup"><span data-stu-id="36032-350">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="36032-351">0x5 - デバッガー。</span><span class="sxs-lookup"><span data-stu-id="36032-351">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="36032-352">0x6 - ガベージ コレクションの準備。</span><span class="sxs-lookup"><span data-stu-id="36032-352">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="36032-353">Count</span><span class="sxs-lookup"><span data-stu-id="36032-353">Count</span></span>|<span data-ttu-id="36032-354">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-354">win:UInt32</span></span>|<span data-ttu-id="36032-355">その時点の GC カウント。</span><span class="sxs-lookup"><span data-stu-id="36032-355">The GC count at the time.</span></span> <span data-ttu-id="36032-356">通常、この後に後続の GC 開始イベントが表示され、そのカウントは、ガベージ コレクション中に、GC インデックスが増えるため、このカウント + 1 になります。</span><span class="sxs-lookup"><span data-stu-id="36032-356">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="36032-357">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="36032-357">ClrInstanceID</span></span>|<span data-ttu-id="36032-358">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="36032-358">win:UInt16</span></span>|<span data-ttu-id="36032-359">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="36032-359">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="36032-360">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-360">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="36032-361">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-361">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-362">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-362">Keyword for raising the event</span></span>|<span data-ttu-id="36032-363">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-363">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-364">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-364">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-365">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-365">Informational (4)</span></span>|

<span data-ttu-id="36032-366">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-366">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-367">Event</span><span class="sxs-lookup"><span data-stu-id="36032-367">Event</span></span>|<span data-ttu-id="36032-368">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-368">Event ID</span></span>|<span data-ttu-id="36032-369">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-369">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="36032-370">8</span><span class="sxs-lookup"><span data-stu-id="36032-370">8</span></span>|<span data-ttu-id="36032-371">ガベージ コレクションのための実行エンジンの中断の終了。</span><span class="sxs-lookup"><span data-stu-id="36032-371">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="36032-372">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="36032-372">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="36032-373">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-373">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="36032-374">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-374">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-375">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-375">Keyword for raising the event</span></span>|<span data-ttu-id="36032-376">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-376">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-377">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-377">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-378">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-378">Informational (4)</span></span>|

<span data-ttu-id="36032-379">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-379">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-380">Event</span><span class="sxs-lookup"><span data-stu-id="36032-380">Event</span></span>|<span data-ttu-id="36032-381">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-381">Event ID</span></span>|<span data-ttu-id="36032-382">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-382">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="36032-383">10</span><span class="sxs-lookup"><span data-stu-id="36032-383">10</span></span>|<span data-ttu-id="36032-384">約 100 KB が割り当てられるたび。</span><span class="sxs-lookup"><span data-stu-id="36032-384">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="36032-385">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-385">The following table shows the event data:</span></span>

|<span data-ttu-id="36032-386">フィールド名</span><span class="sxs-lookup"><span data-stu-id="36032-386">Field name</span></span>|<span data-ttu-id="36032-387">データ型</span><span class="sxs-lookup"><span data-stu-id="36032-387">Data type</span></span>|<span data-ttu-id="36032-388">説明</span><span class="sxs-lookup"><span data-stu-id="36032-388">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="36032-389">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="36032-389">AllocationAmount</span></span>|<span data-ttu-id="36032-390">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-390">win:UInt32</span></span>|<span data-ttu-id="36032-391">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="36032-391">The allocation size, in bytes.</span></span> <span data-ttu-id="36032-392">この値は、ULONG (4,294,967,295 バイト) の長さより短い割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="36032-392">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="36032-393">割り当てがこれを超える場合、このフィールドには切り捨てられた値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36032-393">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="36032-394">非常に大きな割り当てには `AllocationAmount64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="36032-394">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="36032-395">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="36032-395">AllocationKind</span></span>|<span data-ttu-id="36032-396">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-396">win:UInt32</span></span>|<span data-ttu-id="36032-397">0x0 - 小さなオブジェクトの割り当て (小さなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="36032-397">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="36032-398">0x1 - 大きなオブジェクトの割り当て (大きなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="36032-398">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="36032-399">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="36032-399">ClrInstanceID</span></span>|<span data-ttu-id="36032-400">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="36032-400">win:UInt16</span></span>|<span data-ttu-id="36032-401">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="36032-401">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="36032-402">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="36032-402">AllocationAmount64</span></span>|<span data-ttu-id="36032-403">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="36032-403">win:UInt64</span></span>|<span data-ttu-id="36032-404">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="36032-404">The allocation size, in bytes.</span></span> <span data-ttu-id="36032-405">この値は非常に大きな割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="36032-405">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="36032-406">TypeId</span><span class="sxs-lookup"><span data-stu-id="36032-406">TypeId</span></span>|<span data-ttu-id="36032-407">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="36032-407">win:Pointer</span></span>|<span data-ttu-id="36032-408">MethodTable のアドレス。</span><span class="sxs-lookup"><span data-stu-id="36032-408">The address of the MethodTable.</span></span> <span data-ttu-id="36032-409">このイベント中に複数の型のオブジェクトが割り当てられた場合、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) に対応する MethodTable のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="36032-409">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="36032-410">TypeName</span><span class="sxs-lookup"><span data-stu-id="36032-410">TypeName</span></span>|<span data-ttu-id="36032-411">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="36032-411">win:UnicodeString</span></span>|<span data-ttu-id="36032-412">割り当てられた型の名前。</span><span class="sxs-lookup"><span data-stu-id="36032-412">The name of the type that was allocated.</span></span> <span data-ttu-id="36032-413">このイベント中に複数の型のオブジェクトが割り当てられた場合は、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) の型です。</span><span class="sxs-lookup"><span data-stu-id="36032-413">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="36032-414">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="36032-414">HeapIndex</span></span>|<span data-ttu-id="36032-415">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-415">win:UInt32</span></span>|<span data-ttu-id="36032-416">オブジェクトが割り当てられたヒープ。</span><span class="sxs-lookup"><span data-stu-id="36032-416">The heap where the object was allocated.</span></span> <span data-ttu-id="36032-417">ワークステーションのガベージ コレクションと共に実行する場合、この値は 0 (ゼロ) になります。</span><span class="sxs-lookup"><span data-stu-id="36032-417">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="36032-418">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-418">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="36032-419">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-419">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-420">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-420">Keyword for raising the event</span></span>|<span data-ttu-id="36032-421">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-421">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-422">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-422">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-423">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-423">Informational (4)</span></span>|

<span data-ttu-id="36032-424">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-424">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-425">Event</span><span class="sxs-lookup"><span data-stu-id="36032-425">Event</span></span>|<span data-ttu-id="36032-426">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-426">Event ID</span></span>|<span data-ttu-id="36032-427">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-427">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="36032-428">14</span><span class="sxs-lookup"><span data-stu-id="36032-428">14</span></span>|<span data-ttu-id="36032-429">ファイナライザーの実行の開始。</span><span class="sxs-lookup"><span data-stu-id="36032-429">The start of running finalizers.</span></span>|

<span data-ttu-id="36032-430">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="36032-430">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="36032-431">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-431">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="36032-432">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-432">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-433">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-433">Keyword for raising the event</span></span>|<span data-ttu-id="36032-434">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-434">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-435">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-435">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-436">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-436">Informational (4)</span></span>|

<span data-ttu-id="36032-437">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-437">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-438">Event</span><span class="sxs-lookup"><span data-stu-id="36032-438">Event</span></span>|<span data-ttu-id="36032-439">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-439">Event ID</span></span>|<span data-ttu-id="36032-440">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-440">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="36032-441">13</span><span class="sxs-lookup"><span data-stu-id="36032-441">13</span></span>|<span data-ttu-id="36032-442">ファイナライザーの実行の終了。</span><span class="sxs-lookup"><span data-stu-id="36032-442">The end of running finalizers.</span></span>|

<span data-ttu-id="36032-443">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-443">The following table shows the event data:</span></span>

|<span data-ttu-id="36032-444">フィールド名</span><span class="sxs-lookup"><span data-stu-id="36032-444">Field name</span></span>|<span data-ttu-id="36032-445">データ型</span><span class="sxs-lookup"><span data-stu-id="36032-445">Data type</span></span>|<span data-ttu-id="36032-446">説明</span><span class="sxs-lookup"><span data-stu-id="36032-446">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="36032-447">Count</span><span class="sxs-lookup"><span data-stu-id="36032-447">Count</span></span>|<span data-ttu-id="36032-448">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="36032-448">win:UInt32</span></span>|<span data-ttu-id="36032-449">実行されたファイナライザーの数。</span><span class="sxs-lookup"><span data-stu-id="36032-449">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="36032-450">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="36032-450">ClrInstanceID</span></span>|<span data-ttu-id="36032-451">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="36032-451">win:UInt16</span></span>|<span data-ttu-id="36032-452">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="36032-452">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="36032-453">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-453">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="36032-454">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-454">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-455">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-455">Keyword for raising the event</span></span>|<span data-ttu-id="36032-456">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-456">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-457">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-457">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-458">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-458">Informational (4)</span></span>|
|<span data-ttu-id="36032-459">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="36032-459">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="36032-460">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-460">Informational (4)</span></span>|

<span data-ttu-id="36032-461">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-461">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-462">Event</span><span class="sxs-lookup"><span data-stu-id="36032-462">Event</span></span>|<span data-ttu-id="36032-463">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-463">Event ID</span></span>|<span data-ttu-id="36032-464">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-464">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="36032-465">11</span><span class="sxs-lookup"><span data-stu-id="36032-465">11</span></span>|<span data-ttu-id="36032-466">同時実行ガベージ コレクション スレッドが作成されました。</span><span class="sxs-lookup"><span data-stu-id="36032-466">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="36032-467">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="36032-467">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="36032-468">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="36032-468">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="36032-469">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="36032-469">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="36032-470">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="36032-470">Keyword for raising the event</span></span>|<span data-ttu-id="36032-471">レベル</span><span class="sxs-lookup"><span data-stu-id="36032-471">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="36032-472">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="36032-472">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="36032-473">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-473">Informational (4)</span></span>|
|<span data-ttu-id="36032-474">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="36032-474">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="36032-475">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="36032-475">Informational (4)</span></span>|

<span data-ttu-id="36032-476">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="36032-476">The following table shows the event information:</span></span>

|<span data-ttu-id="36032-477">Event</span><span class="sxs-lookup"><span data-stu-id="36032-477">Event</span></span>|<span data-ttu-id="36032-478">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36032-478">Event ID</span></span>|<span data-ttu-id="36032-479">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="36032-479">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="36032-480">12</span><span class="sxs-lookup"><span data-stu-id="36032-480">12</span></span>|<span data-ttu-id="36032-481">同時実行ガベージ コレクションスレッドが終了しました。</span><span class="sxs-lookup"><span data-stu-id="36032-481">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="36032-482">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="36032-482">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="36032-483">関連項目</span><span class="sxs-lookup"><span data-stu-id="36032-483">See also</span></span>

- [<span data-ttu-id="36032-484">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="36032-484">CLR ETW Events</span></span>](clr-etw-events.md)
