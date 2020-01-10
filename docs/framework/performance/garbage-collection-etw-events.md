---
title: ガベージ コレクション ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 5ff214314b92796f4a4a89ddd33a976d8b1f21d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716066"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="7eb30-102">ガベージ コレクション ETW イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="7eb30-103">これらのイベントは、ガベージ コレクションに関連する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="7eb30-104">ガベージ コレクションが実行された回数、ガベージ コレクションの間に解放されたメモリの量など、診断やデバッグに役立つ情報を入手できます。</span><span class="sxs-lookup"><span data-stu-id="7eb30-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="7eb30-105">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7eb30-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="7eb30-106">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="7eb30-107">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="7eb30-108">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="7eb30-109">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="7eb30-110">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="7eb30-111">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="7eb30-112">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="7eb30-113">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="7eb30-114">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="7eb30-115">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="7eb30-116">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="7eb30-117">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="7eb30-118">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="7eb30-119">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="7eb30-120">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="7eb30-121">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="7eb30-122">詳細については、「 [CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eb30-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="7eb30-123">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-123">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-124">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-126">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-126">Informational (4)</span></span>|

<span data-ttu-id="7eb30-127">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-127">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-128">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-128">Event</span></span>|<span data-ttu-id="7eb30-129">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-129">Event ID</span></span>|<span data-ttu-id="7eb30-130">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="7eb30-131">1</span><span class="sxs-lookup"><span data-stu-id="7eb30-131">1</span></span>|<span data-ttu-id="7eb30-132">ガベージ コレクションが開始されました。</span><span class="sxs-lookup"><span data-stu-id="7eb30-132">A garbage collection has started.</span></span>|

<span data-ttu-id="7eb30-133">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-133">The following table shows the event data:</span></span>

|<span data-ttu-id="7eb30-134">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7eb30-134">Field name</span></span>|<span data-ttu-id="7eb30-135">[データ型]</span><span class="sxs-lookup"><span data-stu-id="7eb30-135">Data type</span></span>|<span data-ttu-id="7eb30-136">説明</span><span class="sxs-lookup"><span data-stu-id="7eb30-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7eb30-137">[カウント]</span><span class="sxs-lookup"><span data-stu-id="7eb30-137">Count</span></span>|<span data-ttu-id="7eb30-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-138">win:UInt32</span></span>|<span data-ttu-id="7eb30-139">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="7eb30-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="7eb30-140">奥行</span><span class="sxs-lookup"><span data-stu-id="7eb30-140">Depth</span></span>|<span data-ttu-id="7eb30-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-141">win:UInt32</span></span>|<span data-ttu-id="7eb30-142">収集されるジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="7eb30-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="7eb30-143">理由</span><span class="sxs-lookup"><span data-stu-id="7eb30-143">Reason</span></span>|<span data-ttu-id="7eb30-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-144">win:UInt32</span></span>|<span data-ttu-id="7eb30-145">ガベージ コレクションが発生した理由:</span><span class="sxs-lookup"><span data-stu-id="7eb30-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="7eb30-146">0x0 - 小さなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="7eb30-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="7eb30-147">0x1 - 強制実行。</span><span class="sxs-lookup"><span data-stu-id="7eb30-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="7eb30-148">0x2 - メモリ不足。</span><span class="sxs-lookup"><span data-stu-id="7eb30-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="7eb30-149">0x3 - 空。</span><span class="sxs-lookup"><span data-stu-id="7eb30-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="7eb30-150">0x4 - 大きなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="7eb30-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="7eb30-151">0x5 - 領域不足 (小さなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="7eb30-152">0x6 - 領域不足 (大きなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="7eb30-153">0x7 - 強制実行されるが、ブロッキングとして強制されない。</span><span class="sxs-lookup"><span data-stu-id="7eb30-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="7eb30-154">の型</span><span class="sxs-lookup"><span data-stu-id="7eb30-154">Type</span></span>|<span data-ttu-id="7eb30-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-155">win:UInt32</span></span>|<span data-ttu-id="7eb30-156">0x0 - バックグラウンド ガベージ コレクションの外部で発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="7eb30-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="7eb30-157">0x1 - バックグラウンド ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="7eb30-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="7eb30-158">0x2 - バックグラウンド ガベージ コレクションの実行中に発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="7eb30-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="7eb30-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7eb30-159">ClrInstanceID</span></span>|<span data-ttu-id="7eb30-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7eb30-160">win:UInt16</span></span>|<span data-ttu-id="7eb30-161">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7eb30-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="7eb30-162">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="7eb30-163">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-164">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-164">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-165">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-167">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-167">Informational (4)</span></span>|

<span data-ttu-id="7eb30-168">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-168">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-169">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-169">Event</span></span>|<span data-ttu-id="7eb30-170">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-170">Event ID</span></span>|<span data-ttu-id="7eb30-171">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="7eb30-172">2</span><span class="sxs-lookup"><span data-stu-id="7eb30-172">2</span></span>|<span data-ttu-id="7eb30-173">ガベージ コレクションが終了しました。</span><span class="sxs-lookup"><span data-stu-id="7eb30-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="7eb30-174">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-174">The following table shows the event data:</span></span>

|<span data-ttu-id="7eb30-175">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7eb30-175">Field name</span></span>|<span data-ttu-id="7eb30-176">[データ型]</span><span class="sxs-lookup"><span data-stu-id="7eb30-176">Data type</span></span>|<span data-ttu-id="7eb30-177">説明</span><span class="sxs-lookup"><span data-stu-id="7eb30-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7eb30-178">[カウント]</span><span class="sxs-lookup"><span data-stu-id="7eb30-178">Count</span></span>|<span data-ttu-id="7eb30-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-179">win:UInt32</span></span>|<span data-ttu-id="7eb30-180">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="7eb30-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="7eb30-181">奥行</span><span class="sxs-lookup"><span data-stu-id="7eb30-181">Depth</span></span>|<span data-ttu-id="7eb30-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-182">win:UInt32</span></span>|<span data-ttu-id="7eb30-183">収集されたジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="7eb30-183">The generation that was collected.</span></span>|
|<span data-ttu-id="7eb30-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7eb30-184">ClrInstanceID</span></span>|<span data-ttu-id="7eb30-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7eb30-185">win:UInt16</span></span>|<span data-ttu-id="7eb30-186">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7eb30-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="7eb30-187">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="7eb30-188">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-189">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-189">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-190">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-192">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-192">Informational (4)</span></span>|

<span data-ttu-id="7eb30-193">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-193">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-194">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-194">Event</span></span>|<span data-ttu-id="7eb30-195">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-195">Event ID</span></span>|<span data-ttu-id="7eb30-196">説明</span><span class="sxs-lookup"><span data-stu-id="7eb30-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="7eb30-197">4</span><span class="sxs-lookup"><span data-stu-id="7eb30-197">4</span></span>|<span data-ttu-id="7eb30-198">各ガベージ コレクション終了時のヒープの統計情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="7eb30-199">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-199">The following table shows the event data:</span></span>

|<span data-ttu-id="7eb30-200">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7eb30-200">Field name</span></span>|<span data-ttu-id="7eb30-201">[データ型]</span><span class="sxs-lookup"><span data-stu-id="7eb30-201">Data type</span></span>|<span data-ttu-id="7eb30-202">説明</span><span class="sxs-lookup"><span data-stu-id="7eb30-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7eb30-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="7eb30-203">GenerationSize0</span></span>|<span data-ttu-id="7eb30-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-204">win:UInt64</span></span>|<span data-ttu-id="7eb30-205">ジェネレーション 0 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="7eb30-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="7eb30-206">TotalPromotedSize0</span></span>|<span data-ttu-id="7eb30-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-207">win:UInt64</span></span>|<span data-ttu-id="7eb30-208">ジェネレーション 0 からジェネレーション 1 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="7eb30-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="7eb30-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="7eb30-209">GenerationSize1</span></span>|<span data-ttu-id="7eb30-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-210">win:UInt64</span></span>|<span data-ttu-id="7eb30-211">ジェネレーション 1 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="7eb30-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="7eb30-212">TotalPromotedSize1</span></span>|<span data-ttu-id="7eb30-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-213">win:UInt64</span></span>|<span data-ttu-id="7eb30-214">ジェネレーション 1 からジェネレーション 2 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="7eb30-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="7eb30-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="7eb30-215">GenerationSize2</span></span>|<span data-ttu-id="7eb30-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-216">win:UInt64</span></span>|<span data-ttu-id="7eb30-217">ジェネレーション 2 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="7eb30-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="7eb30-218">TotalPromotedSize2</span></span>|<span data-ttu-id="7eb30-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-219">win:UInt64</span></span>|<span data-ttu-id="7eb30-220">最後のガベージ コレクションの後にジェネレーション 2 に残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="7eb30-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="7eb30-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="7eb30-221">GenerationSize3</span></span>|<span data-ttu-id="7eb30-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-222">win:UInt64</span></span>|<span data-ttu-id="7eb30-223">大きなオブジェクト ヒープのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="7eb30-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="7eb30-224">TotalPromotedSize3</span></span>|<span data-ttu-id="7eb30-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-225">win:UInt64</span></span>|<span data-ttu-id="7eb30-226">最後のガベージ コレクションの後に大きなオブジェクト ヒープに残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="7eb30-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="7eb30-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="7eb30-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="7eb30-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-228">win:UInt64</span></span>|<span data-ttu-id="7eb30-229">終了準備が完了しているオブジェクトの合計サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="7eb30-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="7eb30-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="7eb30-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-231">win:UInt64</span></span>|<span data-ttu-id="7eb30-232">終了準備が完了しているオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="7eb30-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="7eb30-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="7eb30-233">PinnedObjectCount</span></span>|<span data-ttu-id="7eb30-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-234">win:UInt32</span></span>|<span data-ttu-id="7eb30-235">ピン止めオブジェクト (移動できないオブジェクト) の数。</span><span class="sxs-lookup"><span data-stu-id="7eb30-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="7eb30-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="7eb30-236">SinkBlockCount</span></span>|<span data-ttu-id="7eb30-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-237">win:UInt32</span></span>|<span data-ttu-id="7eb30-238">使用中の同期ブロックの数。</span><span class="sxs-lookup"><span data-stu-id="7eb30-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="7eb30-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="7eb30-239">GCHandleCount</span></span>|<span data-ttu-id="7eb30-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-240">win:UInt32</span></span>|<span data-ttu-id="7eb30-241">使用中のガベージ コレクション ハンドルの数。</span><span class="sxs-lookup"><span data-stu-id="7eb30-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="7eb30-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7eb30-242">ClrInstanceID</span></span>|<span data-ttu-id="7eb30-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7eb30-243">win:UInt16</span></span>|<span data-ttu-id="7eb30-244">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7eb30-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="7eb30-245">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="7eb30-246">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-247">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-247">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-248">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-250">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-250">Informational (4)</span></span>|

<span data-ttu-id="7eb30-251">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-251">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-252">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-252">Event</span></span>|<span data-ttu-id="7eb30-253">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-253">Event ID</span></span>|<span data-ttu-id="7eb30-254">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="7eb30-255">5</span><span class="sxs-lookup"><span data-stu-id="7eb30-255">5</span></span>|<span data-ttu-id="7eb30-256">新しいガベージ コレクション セグメントが作成されました。</span><span class="sxs-lookup"><span data-stu-id="7eb30-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="7eb30-257">既に実行されているプロセスでトレースを有効にした場合は、このイベントが各既存セグメントについて発生します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="7eb30-258">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-258">The following table shows the event data:</span></span>

|<span data-ttu-id="7eb30-259">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7eb30-259">Field name</span></span>|<span data-ttu-id="7eb30-260">[データ型]</span><span class="sxs-lookup"><span data-stu-id="7eb30-260">Data type</span></span>|<span data-ttu-id="7eb30-261">説明</span><span class="sxs-lookup"><span data-stu-id="7eb30-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7eb30-262">Address</span><span class="sxs-lookup"><span data-stu-id="7eb30-262">Address</span></span>|<span data-ttu-id="7eb30-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-263">win:UInt64</span></span>|<span data-ttu-id="7eb30-264">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="7eb30-264">The address of the segment.</span></span>|
|<span data-ttu-id="7eb30-265">サイズ</span><span class="sxs-lookup"><span data-stu-id="7eb30-265">Size</span></span>|<span data-ttu-id="7eb30-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-266">win:UInt64</span></span>|<span data-ttu-id="7eb30-267">セグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="7eb30-267">The size of the segment.</span></span>|
|<span data-ttu-id="7eb30-268">の型</span><span class="sxs-lookup"><span data-stu-id="7eb30-268">Type</span></span>|<span data-ttu-id="7eb30-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-269">win:UInt32</span></span>|<span data-ttu-id="7eb30-270">0x0 - 小さなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="7eb30-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="7eb30-271">0x1 - 大きなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="7eb30-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="7eb30-272">0x2 - 読み取り専用ヒープ。</span><span class="sxs-lookup"><span data-stu-id="7eb30-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="7eb30-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7eb30-273">ClrInstanceID</span></span>|<span data-ttu-id="7eb30-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7eb30-274">win:UInt16</span></span>|<span data-ttu-id="7eb30-275">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7eb30-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="7eb30-276">ガベージ コレクターによって割り当てられるセグメントのサイズは実装に固有であり、定期的な更新プログラムによる場合を含め、いつでも変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7eb30-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="7eb30-277">アプリでは、セグメント サイズを推測することや、特定のセグメント サイズに依存することを絶対に避けてください。また、セグメントの割り当てに使用可能なメモリの量を構成しようとしてもなりません。</span><span class="sxs-lookup"><span data-stu-id="7eb30-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="7eb30-278">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="7eb30-279">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-280">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-280">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-281">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-283">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-283">Informational (4)</span></span>|

<span data-ttu-id="7eb30-284">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-284">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-285">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-285">Event</span></span>|<span data-ttu-id="7eb30-286">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-286">Event ID</span></span>|<span data-ttu-id="7eb30-287">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="7eb30-288">6</span><span class="sxs-lookup"><span data-stu-id="7eb30-288">6</span></span>|<span data-ttu-id="7eb30-289">ガベージ コレクション セグメントが解放されました。</span><span class="sxs-lookup"><span data-stu-id="7eb30-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="7eb30-290">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-290">The following table shows the event data:</span></span>

|<span data-ttu-id="7eb30-291">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7eb30-291">Field name</span></span>|<span data-ttu-id="7eb30-292">[データ型]</span><span class="sxs-lookup"><span data-stu-id="7eb30-292">Data type</span></span>|<span data-ttu-id="7eb30-293">説明</span><span class="sxs-lookup"><span data-stu-id="7eb30-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7eb30-294">Address</span><span class="sxs-lookup"><span data-stu-id="7eb30-294">Address</span></span>|<span data-ttu-id="7eb30-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-295">win:UInt64</span></span>|<span data-ttu-id="7eb30-296">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="7eb30-296">The address of the segment.</span></span>|
|<span data-ttu-id="7eb30-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7eb30-297">ClrInstanceID</span></span>|<span data-ttu-id="7eb30-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7eb30-298">win:UInt16</span></span>|<span data-ttu-id="7eb30-299">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7eb30-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="7eb30-300">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="7eb30-301">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-302">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-302">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-303">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-305">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-305">Informational (4)</span></span>|

<span data-ttu-id="7eb30-306">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-306">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-307">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-307">Event</span></span>|<span data-ttu-id="7eb30-308">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-308">Event ID</span></span>|<span data-ttu-id="7eb30-309">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="7eb30-310">7</span><span class="sxs-lookup"><span data-stu-id="7eb30-310">7</span></span>|<span data-ttu-id="7eb30-311">共通言語ランタイムの中断からの再開が開始されました。</span><span class="sxs-lookup"><span data-stu-id="7eb30-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="7eb30-312">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="7eb30-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="7eb30-313">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="7eb30-314">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-315">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-315">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-316">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-318">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-318">Informational (4)</span></span>|

<span data-ttu-id="7eb30-319">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-319">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-320">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-320">Event</span></span>|<span data-ttu-id="7eb30-321">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-321">Event Id</span></span>|<span data-ttu-id="7eb30-322">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="7eb30-323">3</span><span class="sxs-lookup"><span data-stu-id="7eb30-323">3</span></span>|<span data-ttu-id="7eb30-324">共通言語ランタイムの中断からの再開が終了しました。</span><span class="sxs-lookup"><span data-stu-id="7eb30-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="7eb30-325">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="7eb30-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="7eb30-326">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="7eb30-327">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-328">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-328">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-329">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-331">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-331">Informational (4)</span></span>|

<span data-ttu-id="7eb30-332">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-332">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-333">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-333">Event</span></span>|<span data-ttu-id="7eb30-334">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-334">Event ID</span></span>|<span data-ttu-id="7eb30-335">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="7eb30-336">9</span><span class="sxs-lookup"><span data-stu-id="7eb30-336">9</span></span>|<span data-ttu-id="7eb30-337">ガベージ コレクションのための実行エンジンの中断の開始。</span><span class="sxs-lookup"><span data-stu-id="7eb30-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="7eb30-338">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-338">The following table shows the event data:</span></span>

|<span data-ttu-id="7eb30-339">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7eb30-339">Field name</span></span>|<span data-ttu-id="7eb30-340">[データ型]</span><span class="sxs-lookup"><span data-stu-id="7eb30-340">Data type</span></span>|<span data-ttu-id="7eb30-341">説明</span><span class="sxs-lookup"><span data-stu-id="7eb30-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7eb30-342">理由</span><span class="sxs-lookup"><span data-stu-id="7eb30-342">Reason</span></span>|<span data-ttu-id="7eb30-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7eb30-343">win:UInt16</span></span>|<span data-ttu-id="7eb30-344">0x0 - その他。</span><span class="sxs-lookup"><span data-stu-id="7eb30-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="7eb30-345">0x1 - ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="7eb30-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="7eb30-346">0x2 - アプリケーション ドメインのシャットダウン。</span><span class="sxs-lookup"><span data-stu-id="7eb30-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="7eb30-347">0x3 - コード ピッチ。</span><span class="sxs-lookup"><span data-stu-id="7eb30-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="7eb30-348">0x4 - シャットダウン。</span><span class="sxs-lookup"><span data-stu-id="7eb30-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="7eb30-349">0x5 - デバッガー。</span><span class="sxs-lookup"><span data-stu-id="7eb30-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="7eb30-350">0x6 - ガベージ コレクションの準備。</span><span class="sxs-lookup"><span data-stu-id="7eb30-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="7eb30-351">[カウント]</span><span class="sxs-lookup"><span data-stu-id="7eb30-351">Count</span></span>|<span data-ttu-id="7eb30-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-352">win:UInt32</span></span>|<span data-ttu-id="7eb30-353">その時点の GC カウント。</span><span class="sxs-lookup"><span data-stu-id="7eb30-353">The GC count at the time.</span></span> <span data-ttu-id="7eb30-354">通常、この後に後続の GC 開始イベントが表示され、そのカウントは、ガベージ コレクション中に、GC インデックスが増えるため、このカウント + 1 になります。</span><span class="sxs-lookup"><span data-stu-id="7eb30-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="7eb30-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7eb30-355">ClrInstanceID</span></span>|<span data-ttu-id="7eb30-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7eb30-356">win:UInt16</span></span>|<span data-ttu-id="7eb30-357">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7eb30-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="7eb30-358">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="7eb30-359">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-360">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-360">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-361">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-363">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-363">Informational (4)</span></span>|

<span data-ttu-id="7eb30-364">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-364">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-365">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-365">Event</span></span>|<span data-ttu-id="7eb30-366">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-366">Event ID</span></span>|<span data-ttu-id="7eb30-367">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="7eb30-368">8</span><span class="sxs-lookup"><span data-stu-id="7eb30-368">8</span></span>|<span data-ttu-id="7eb30-369">ガベージ コレクションのための実行エンジンの中断の終了。</span><span class="sxs-lookup"><span data-stu-id="7eb30-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="7eb30-370">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="7eb30-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="7eb30-371">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="7eb30-372">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-373">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-373">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-374">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-376">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-376">Informational (4)</span></span>|

<span data-ttu-id="7eb30-377">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-377">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-378">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-378">Event</span></span>|<span data-ttu-id="7eb30-379">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-379">Event ID</span></span>|<span data-ttu-id="7eb30-380">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="7eb30-381">10</span><span class="sxs-lookup"><span data-stu-id="7eb30-381">10</span></span>|<span data-ttu-id="7eb30-382">約 100 KB が割り当てられるたび。</span><span class="sxs-lookup"><span data-stu-id="7eb30-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="7eb30-383">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-383">The following table shows the event data:</span></span>

|<span data-ttu-id="7eb30-384">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7eb30-384">Field name</span></span>|<span data-ttu-id="7eb30-385">[データ型]</span><span class="sxs-lookup"><span data-stu-id="7eb30-385">Data type</span></span>|<span data-ttu-id="7eb30-386">説明</span><span class="sxs-lookup"><span data-stu-id="7eb30-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7eb30-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="7eb30-387">AllocationAmount</span></span>|<span data-ttu-id="7eb30-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-388">win:UInt32</span></span>|<span data-ttu-id="7eb30-389">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-389">The allocation size, in bytes.</span></span> <span data-ttu-id="7eb30-390">この値は、ULONG (4,294,967,295 バイト) の長さより短い割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="7eb30-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="7eb30-391">割り当てがこれを超える場合、このフィールドには切り捨てられた値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7eb30-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="7eb30-392">非常に大きな割り当てには `AllocationAmount64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="7eb30-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="7eb30-393">AllocationKind</span></span>|<span data-ttu-id="7eb30-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-394">win:UInt32</span></span>|<span data-ttu-id="7eb30-395">0x0 - 小さなオブジェクトの割り当て (小さなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="7eb30-396">0x1 - 大きなオブジェクトの割り当て (大きなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="7eb30-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7eb30-397">ClrInstanceID</span></span>|<span data-ttu-id="7eb30-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7eb30-398">win:UInt16</span></span>|<span data-ttu-id="7eb30-399">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7eb30-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="7eb30-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="7eb30-400">AllocationAmount64</span></span>|<span data-ttu-id="7eb30-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7eb30-401">win:UInt64</span></span>|<span data-ttu-id="7eb30-402">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7eb30-402">The allocation size, in bytes.</span></span> <span data-ttu-id="7eb30-403">この値は非常に大きな割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="7eb30-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="7eb30-404">タイプ ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-404">TypeId</span></span>|<span data-ttu-id="7eb30-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="7eb30-405">win:Pointer</span></span>|<span data-ttu-id="7eb30-406">MethodTable のアドレス。</span><span class="sxs-lookup"><span data-stu-id="7eb30-406">The address of the MethodTable.</span></span> <span data-ttu-id="7eb30-407">このイベント中に複数の型のオブジェクトが割り当てられた場合、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) に対応する MethodTable のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="7eb30-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="7eb30-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="7eb30-408">TypeName</span></span>|<span data-ttu-id="7eb30-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7eb30-409">win:UnicodeString</span></span>|<span data-ttu-id="7eb30-410">割り当てられた型の名前。</span><span class="sxs-lookup"><span data-stu-id="7eb30-410">The name of the type that was allocated.</span></span> <span data-ttu-id="7eb30-411">このイベント中に複数の型のオブジェクトが割り当てられた場合は、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) の型です。</span><span class="sxs-lookup"><span data-stu-id="7eb30-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="7eb30-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="7eb30-412">HeapIndex</span></span>|<span data-ttu-id="7eb30-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-413">win:UInt32</span></span>|<span data-ttu-id="7eb30-414">オブジェクトが割り当てられたヒープ。</span><span class="sxs-lookup"><span data-stu-id="7eb30-414">The heap where the object was allocated.</span></span> <span data-ttu-id="7eb30-415">ワークステーションのガベージ コレクションと共に実行する場合、この値は 0 (ゼロ) になります。</span><span class="sxs-lookup"><span data-stu-id="7eb30-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="7eb30-416">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="7eb30-417">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-418">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-418">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-419">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-421">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-421">Informational (4)</span></span>|

<span data-ttu-id="7eb30-422">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-422">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-423">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-423">Event</span></span>|<span data-ttu-id="7eb30-424">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-424">Event ID</span></span>|<span data-ttu-id="7eb30-425">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="7eb30-426">14</span><span class="sxs-lookup"><span data-stu-id="7eb30-426">14</span></span>|<span data-ttu-id="7eb30-427">ファイナライザーの実行の開始。</span><span class="sxs-lookup"><span data-stu-id="7eb30-427">The start of running finalizers.</span></span>|

<span data-ttu-id="7eb30-428">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="7eb30-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="7eb30-429">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="7eb30-430">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-431">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-431">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-432">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-434">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-434">Informational (4)</span></span>|

<span data-ttu-id="7eb30-435">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-435">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-436">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-436">Event</span></span>|<span data-ttu-id="7eb30-437">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-437">Event ID</span></span>|<span data-ttu-id="7eb30-438">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="7eb30-439">13</span><span class="sxs-lookup"><span data-stu-id="7eb30-439">13</span></span>|<span data-ttu-id="7eb30-440">ファイナライザーの実行の終了。</span><span class="sxs-lookup"><span data-stu-id="7eb30-440">The end of running finalizers.</span></span>|

<span data-ttu-id="7eb30-441">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-441">The following table shows the event data:</span></span>

|<span data-ttu-id="7eb30-442">フィールド名</span><span class="sxs-lookup"><span data-stu-id="7eb30-442">Field name</span></span>|<span data-ttu-id="7eb30-443">[データ型]</span><span class="sxs-lookup"><span data-stu-id="7eb30-443">Data type</span></span>|<span data-ttu-id="7eb30-444">説明</span><span class="sxs-lookup"><span data-stu-id="7eb30-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="7eb30-445">[カウント]</span><span class="sxs-lookup"><span data-stu-id="7eb30-445">Count</span></span>|<span data-ttu-id="7eb30-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7eb30-446">win:UInt32</span></span>|<span data-ttu-id="7eb30-447">実行されたファイナライザーの数。</span><span class="sxs-lookup"><span data-stu-id="7eb30-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="7eb30-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7eb30-448">ClrInstanceID</span></span>|<span data-ttu-id="7eb30-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7eb30-449">win:UInt16</span></span>|<span data-ttu-id="7eb30-450">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="7eb30-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="7eb30-451">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="7eb30-452">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-453">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-453">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-454">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-456">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-456">Informational (4)</span></span>|
|<span data-ttu-id="7eb30-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="7eb30-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="7eb30-458">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-458">Informational (4)</span></span>|

<span data-ttu-id="7eb30-459">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-459">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-460">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-460">Event</span></span>|<span data-ttu-id="7eb30-461">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-461">Event ID</span></span>|<span data-ttu-id="7eb30-462">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="7eb30-463">11</span><span class="sxs-lookup"><span data-stu-id="7eb30-463">11</span></span>|<span data-ttu-id="7eb30-464">同時実行ガベージ コレクション スレッドが作成されました。</span><span class="sxs-lookup"><span data-stu-id="7eb30-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="7eb30-465">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="7eb30-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="7eb30-466">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="7eb30-467">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="7eb30-468">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="7eb30-468">Keyword for raising the event</span></span>|<span data-ttu-id="7eb30-469">レベル</span><span class="sxs-lookup"><span data-stu-id="7eb30-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="7eb30-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="7eb30-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="7eb30-471">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-471">Informational (4)</span></span>|
|<span data-ttu-id="7eb30-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="7eb30-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="7eb30-473">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="7eb30-473">Informational (4)</span></span>|

<span data-ttu-id="7eb30-474">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="7eb30-474">The following table shows the event information:</span></span>

|<span data-ttu-id="7eb30-475">Event</span><span class="sxs-lookup"><span data-stu-id="7eb30-475">Event</span></span>|<span data-ttu-id="7eb30-476">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7eb30-476">Event ID</span></span>|<span data-ttu-id="7eb30-477">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="7eb30-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="7eb30-478">12</span><span class="sxs-lookup"><span data-stu-id="7eb30-478">12</span></span>|<span data-ttu-id="7eb30-479">同時実行ガベージ コレクションスレッドが終了しました。</span><span class="sxs-lookup"><span data-stu-id="7eb30-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="7eb30-480">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="7eb30-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="7eb30-481">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eb30-481">See also</span></span>

- [<span data-ttu-id="7eb30-482">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="7eb30-482">CLR ETW Events</span></span>](clr-etw-events.md)
