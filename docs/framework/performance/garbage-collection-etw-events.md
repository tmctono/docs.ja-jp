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
ms.openlocfilehash: cd4a4699f115c5b134ea60e703607ff36c229a78
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040580"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="48b6f-102">ガベージ コレクション ETW イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="48b6f-103">これらのイベントは、ガベージ コレクションに関連する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="48b6f-104">ガベージ コレクションが実行された回数、ガベージ コレクションの間に解放されたメモリの量など、診断やデバッグに役立つ情報を入手できます。</span><span class="sxs-lookup"><span data-stu-id="48b6f-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="48b6f-105">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="48b6f-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="48b6f-106">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="48b6f-107">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="48b6f-108">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="48b6f-109">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="48b6f-110">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="48b6f-111">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="48b6f-112">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="48b6f-113">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="48b6f-114">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="48b6f-115">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="48b6f-116">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="48b6f-117">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="48b6f-118">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="48b6f-119">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="48b6f-120">GCStart_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="48b6f-121">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="48b6f-122">詳細については、「 [CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48b6f-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="48b6f-123">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-123">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-124">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-126">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-126">Informational (4)</span></span>|

<span data-ttu-id="48b6f-127">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-127">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-128">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-128">Event</span></span>|<span data-ttu-id="48b6f-129">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-129">Event ID</span></span>|<span data-ttu-id="48b6f-130">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="48b6f-131">1</span><span class="sxs-lookup"><span data-stu-id="48b6f-131">1</span></span>|<span data-ttu-id="48b6f-132">ガベージ コレクションが開始されました。</span><span class="sxs-lookup"><span data-stu-id="48b6f-132">A garbage collection has started.</span></span>|

<span data-ttu-id="48b6f-133">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-133">The following table shows the event data:</span></span>

|<span data-ttu-id="48b6f-134">フィールド名</span><span class="sxs-lookup"><span data-stu-id="48b6f-134">Field name</span></span>|<span data-ttu-id="48b6f-135">データの種類</span><span class="sxs-lookup"><span data-stu-id="48b6f-135">Data type</span></span>|<span data-ttu-id="48b6f-136">説明</span><span class="sxs-lookup"><span data-stu-id="48b6f-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="48b6f-137">カウント</span><span class="sxs-lookup"><span data-stu-id="48b6f-137">Count</span></span>|<span data-ttu-id="48b6f-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-138">win:UInt32</span></span>|<span data-ttu-id="48b6f-139">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="48b6f-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="48b6f-140">奥行</span><span class="sxs-lookup"><span data-stu-id="48b6f-140">Depth</span></span>|<span data-ttu-id="48b6f-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-141">win:UInt32</span></span>|<span data-ttu-id="48b6f-142">収集されるジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="48b6f-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="48b6f-143">理由</span><span class="sxs-lookup"><span data-stu-id="48b6f-143">Reason</span></span>|<span data-ttu-id="48b6f-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-144">win:UInt32</span></span>|<span data-ttu-id="48b6f-145">ガベージ コレクションが発生した理由:</span><span class="sxs-lookup"><span data-stu-id="48b6f-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="48b6f-146">0x0 - 小さなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="48b6f-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="48b6f-147">0x1 - 強制実行。</span><span class="sxs-lookup"><span data-stu-id="48b6f-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="48b6f-148">0x2 - メモリ不足。</span><span class="sxs-lookup"><span data-stu-id="48b6f-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="48b6f-149">0x3 - 空。</span><span class="sxs-lookup"><span data-stu-id="48b6f-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="48b6f-150">0x4 - 大きなオブジェクト ヒープの割り当て。</span><span class="sxs-lookup"><span data-stu-id="48b6f-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="48b6f-151">0x5 - 領域不足 (小さなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="48b6f-152">0x6 - 領域不足 (大きなオブジェクト ヒープが対象)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="48b6f-153">0x7 - 強制実行されるが、ブロッキングとして強制されない。</span><span class="sxs-lookup"><span data-stu-id="48b6f-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="48b6f-154">[種類]</span><span class="sxs-lookup"><span data-stu-id="48b6f-154">Type</span></span>|<span data-ttu-id="48b6f-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-155">win:UInt32</span></span>|<span data-ttu-id="48b6f-156">0x0 - バックグラウンド ガベージ コレクションの外部で発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="48b6f-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="48b6f-157">0x1 - バックグラウンド ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="48b6f-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="48b6f-158">0x2 - バックグラウンド ガベージ コレクションの実行中に発生するブロッキング ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="48b6f-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="48b6f-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="48b6f-159">ClrInstanceID</span></span>|<span data-ttu-id="48b6f-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="48b6f-160">win:UInt16</span></span>|<span data-ttu-id="48b6f-161">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="48b6f-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="48b6f-162">GCEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="48b6f-163">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-164">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-164">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-165">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-167">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-167">Informational (4)</span></span>|

<span data-ttu-id="48b6f-168">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-168">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-169">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-169">Event</span></span>|<span data-ttu-id="48b6f-170">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-170">Event ID</span></span>|<span data-ttu-id="48b6f-171">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="48b6f-172">2</span><span class="sxs-lookup"><span data-stu-id="48b6f-172">2</span></span>|<span data-ttu-id="48b6f-173">ガベージ コレクションが終了しました。</span><span class="sxs-lookup"><span data-stu-id="48b6f-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="48b6f-174">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-174">The following table shows the event data:</span></span>

|<span data-ttu-id="48b6f-175">フィールド名</span><span class="sxs-lookup"><span data-stu-id="48b6f-175">Field name</span></span>|<span data-ttu-id="48b6f-176">データの種類</span><span class="sxs-lookup"><span data-stu-id="48b6f-176">Data type</span></span>|<span data-ttu-id="48b6f-177">説明</span><span class="sxs-lookup"><span data-stu-id="48b6f-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="48b6f-178">カウント</span><span class="sxs-lookup"><span data-stu-id="48b6f-178">Count</span></span>|<span data-ttu-id="48b6f-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-179">win:UInt32</span></span>|<span data-ttu-id="48b6f-180">*n*回めのガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="48b6f-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="48b6f-181">奥行</span><span class="sxs-lookup"><span data-stu-id="48b6f-181">Depth</span></span>|<span data-ttu-id="48b6f-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-182">win:UInt32</span></span>|<span data-ttu-id="48b6f-183">収集されたジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="48b6f-183">The generation that was collected.</span></span>|
|<span data-ttu-id="48b6f-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="48b6f-184">ClrInstanceID</span></span>|<span data-ttu-id="48b6f-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="48b6f-185">win:UInt16</span></span>|<span data-ttu-id="48b6f-186">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="48b6f-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="48b6f-187">GCHeapStats_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="48b6f-188">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-189">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-189">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-190">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-192">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-192">Informational (4)</span></span>|

<span data-ttu-id="48b6f-193">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-193">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-194">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-194">Event</span></span>|<span data-ttu-id="48b6f-195">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-195">Event ID</span></span>|<span data-ttu-id="48b6f-196">説明</span><span class="sxs-lookup"><span data-stu-id="48b6f-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="48b6f-197">4</span><span class="sxs-lookup"><span data-stu-id="48b6f-197">4</span></span>|<span data-ttu-id="48b6f-198">各ガベージ コレクション終了時のヒープの統計情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="48b6f-199">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-199">The following table shows the event data:</span></span>

|<span data-ttu-id="48b6f-200">フィールド名</span><span class="sxs-lookup"><span data-stu-id="48b6f-200">Field name</span></span>|<span data-ttu-id="48b6f-201">データの種類</span><span class="sxs-lookup"><span data-stu-id="48b6f-201">Data type</span></span>|<span data-ttu-id="48b6f-202">説明</span><span class="sxs-lookup"><span data-stu-id="48b6f-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="48b6f-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="48b6f-203">GenerationSize0</span></span>|<span data-ttu-id="48b6f-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-204">win:UInt64</span></span>|<span data-ttu-id="48b6f-205">ジェネレーション 0 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="48b6f-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="48b6f-206">TotalPromotedSize0</span></span>|<span data-ttu-id="48b6f-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-207">win:UInt64</span></span>|<span data-ttu-id="48b6f-208">ジェネレーション 0 からジェネレーション 1 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="48b6f-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="48b6f-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="48b6f-209">GenerationSize1</span></span>|<span data-ttu-id="48b6f-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-210">win:UInt64</span></span>|<span data-ttu-id="48b6f-211">ジェネレーション 1 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="48b6f-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="48b6f-212">TotalPromotedSize1</span></span>|<span data-ttu-id="48b6f-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-213">win:UInt64</span></span>|<span data-ttu-id="48b6f-214">ジェネレーション 1 からジェネレーション 2 に移されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="48b6f-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="48b6f-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="48b6f-215">GenerationSize2</span></span>|<span data-ttu-id="48b6f-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-216">win:UInt64</span></span>|<span data-ttu-id="48b6f-217">ジェネレーション 2 メモリのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="48b6f-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="48b6f-218">TotalPromotedSize2</span></span>|<span data-ttu-id="48b6f-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-219">win:UInt64</span></span>|<span data-ttu-id="48b6f-220">最後のガベージ コレクションの後にジェネレーション 2 に残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="48b6f-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="48b6f-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="48b6f-221">GenerationSize3</span></span>|<span data-ttu-id="48b6f-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-222">win:UInt64</span></span>|<span data-ttu-id="48b6f-223">大きなオブジェクト ヒープのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="48b6f-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="48b6f-224">TotalPromotedSize3</span></span>|<span data-ttu-id="48b6f-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-225">win:UInt64</span></span>|<span data-ttu-id="48b6f-226">最後のガベージ コレクションの後に大きなオブジェクト ヒープに残ったバイト数。</span><span class="sxs-lookup"><span data-stu-id="48b6f-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="48b6f-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="48b6f-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="48b6f-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-228">win:UInt64</span></span>|<span data-ttu-id="48b6f-229">終了準備が完了しているオブジェクトの合計サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="48b6f-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="48b6f-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="48b6f-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-231">win:UInt64</span></span>|<span data-ttu-id="48b6f-232">終了準備が完了しているオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="48b6f-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="48b6f-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="48b6f-233">PinnedObjectCount</span></span>|<span data-ttu-id="48b6f-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-234">win:UInt32</span></span>|<span data-ttu-id="48b6f-235">ピン止めオブジェクト (移動できないオブジェクト) の数。</span><span class="sxs-lookup"><span data-stu-id="48b6f-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="48b6f-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="48b6f-236">SinkBlockCount</span></span>|<span data-ttu-id="48b6f-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-237">win:UInt32</span></span>|<span data-ttu-id="48b6f-238">使用中の同期ブロックの数。</span><span class="sxs-lookup"><span data-stu-id="48b6f-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="48b6f-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="48b6f-239">GCHandleCount</span></span>|<span data-ttu-id="48b6f-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-240">win:UInt32</span></span>|<span data-ttu-id="48b6f-241">使用中のガベージ コレクション ハンドルの数。</span><span class="sxs-lookup"><span data-stu-id="48b6f-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="48b6f-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="48b6f-242">ClrInstanceID</span></span>|<span data-ttu-id="48b6f-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="48b6f-243">win:UInt16</span></span>|<span data-ttu-id="48b6f-244">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="48b6f-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="48b6f-245">GCCreateSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="48b6f-246">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-247">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-247">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-248">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-250">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-250">Informational (4)</span></span>|

<span data-ttu-id="48b6f-251">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-251">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-252">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-252">Event</span></span>|<span data-ttu-id="48b6f-253">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-253">Event ID</span></span>|<span data-ttu-id="48b6f-254">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="48b6f-255">5</span><span class="sxs-lookup"><span data-stu-id="48b6f-255">5</span></span>|<span data-ttu-id="48b6f-256">新しいガベージ コレクション セグメントが作成されました。</span><span class="sxs-lookup"><span data-stu-id="48b6f-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="48b6f-257">既に実行されているプロセスでトレースを有効にした場合は、このイベントが各既存セグメントについて発生します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="48b6f-258">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-258">The following table shows the event data:</span></span>

|<span data-ttu-id="48b6f-259">フィールド名</span><span class="sxs-lookup"><span data-stu-id="48b6f-259">Field name</span></span>|<span data-ttu-id="48b6f-260">データの種類</span><span class="sxs-lookup"><span data-stu-id="48b6f-260">Data type</span></span>|<span data-ttu-id="48b6f-261">説明</span><span class="sxs-lookup"><span data-stu-id="48b6f-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="48b6f-262">アドレス</span><span class="sxs-lookup"><span data-stu-id="48b6f-262">Address</span></span>|<span data-ttu-id="48b6f-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-263">win:UInt64</span></span>|<span data-ttu-id="48b6f-264">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="48b6f-264">The address of the segment.</span></span>|
|<span data-ttu-id="48b6f-265">サイズ</span><span class="sxs-lookup"><span data-stu-id="48b6f-265">Size</span></span>|<span data-ttu-id="48b6f-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-266">win:UInt64</span></span>|<span data-ttu-id="48b6f-267">セグメントのサイズ。</span><span class="sxs-lookup"><span data-stu-id="48b6f-267">The size of the segment.</span></span>|
|<span data-ttu-id="48b6f-268">[種類]</span><span class="sxs-lookup"><span data-stu-id="48b6f-268">Type</span></span>|<span data-ttu-id="48b6f-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-269">win:UInt32</span></span>|<span data-ttu-id="48b6f-270">0x0 - 小さなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="48b6f-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="48b6f-271">0x1 - 大きなオブジェクト ヒープ。</span><span class="sxs-lookup"><span data-stu-id="48b6f-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="48b6f-272">0x2 - 読み取り専用ヒープ。</span><span class="sxs-lookup"><span data-stu-id="48b6f-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="48b6f-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="48b6f-273">ClrInstanceID</span></span>|<span data-ttu-id="48b6f-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="48b6f-274">win:UInt16</span></span>|<span data-ttu-id="48b6f-275">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="48b6f-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="48b6f-276">ガベージ コレクターによって割り当てられるセグメントのサイズは実装に固有であり、定期的な更新プログラムによる場合を含め、いつでも変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="48b6f-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="48b6f-277">アプリでは、セグメント サイズを推測することや、特定のセグメント サイズに依存することを絶対に避けてください。また、セグメントの割り当てに使用可能なメモリの量を構成しようとしてもなりません。</span><span class="sxs-lookup"><span data-stu-id="48b6f-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="48b6f-278">GCFreeSegment_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="48b6f-279">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-280">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-280">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-281">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-283">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-283">Informational (4)</span></span>|

<span data-ttu-id="48b6f-284">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-284">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-285">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-285">Event</span></span>|<span data-ttu-id="48b6f-286">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-286">Event ID</span></span>|<span data-ttu-id="48b6f-287">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="48b6f-288">6</span><span class="sxs-lookup"><span data-stu-id="48b6f-288">6</span></span>|<span data-ttu-id="48b6f-289">ガベージ コレクション セグメントが解放されました。</span><span class="sxs-lookup"><span data-stu-id="48b6f-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="48b6f-290">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-290">The following table shows the event data:</span></span>

|<span data-ttu-id="48b6f-291">フィールド名</span><span class="sxs-lookup"><span data-stu-id="48b6f-291">Field name</span></span>|<span data-ttu-id="48b6f-292">データの種類</span><span class="sxs-lookup"><span data-stu-id="48b6f-292">Data type</span></span>|<span data-ttu-id="48b6f-293">説明</span><span class="sxs-lookup"><span data-stu-id="48b6f-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="48b6f-294">アドレス</span><span class="sxs-lookup"><span data-stu-id="48b6f-294">Address</span></span>|<span data-ttu-id="48b6f-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-295">win:UInt64</span></span>|<span data-ttu-id="48b6f-296">セグメントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="48b6f-296">The address of the segment.</span></span>|
|<span data-ttu-id="48b6f-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="48b6f-297">ClrInstanceID</span></span>|<span data-ttu-id="48b6f-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="48b6f-298">win:UInt16</span></span>|<span data-ttu-id="48b6f-299">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="48b6f-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="48b6f-300">GCRestartEEBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="48b6f-301">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-302">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-302">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-303">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-305">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-305">Informational (4)</span></span>|

<span data-ttu-id="48b6f-306">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-306">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-307">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-307">Event</span></span>|<span data-ttu-id="48b6f-308">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-308">Event ID</span></span>|<span data-ttu-id="48b6f-309">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="48b6f-310">7</span><span class="sxs-lookup"><span data-stu-id="48b6f-310">7</span></span>|<span data-ttu-id="48b6f-311">共通言語ランタイムの中断からの再開が開始されました。</span><span class="sxs-lookup"><span data-stu-id="48b6f-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="48b6f-312">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="48b6f-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="48b6f-313">GCRestartEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="48b6f-314">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-315">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-315">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-316">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-318">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-318">Informational (4)</span></span>|

<span data-ttu-id="48b6f-319">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-319">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-320">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-320">Event</span></span>|<span data-ttu-id="48b6f-321">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-321">Event Id</span></span>|<span data-ttu-id="48b6f-322">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="48b6f-323">3</span><span class="sxs-lookup"><span data-stu-id="48b6f-323">3</span></span>|<span data-ttu-id="48b6f-324">共通言語ランタイムの中断からの再開が終了しました。</span><span class="sxs-lookup"><span data-stu-id="48b6f-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="48b6f-325">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="48b6f-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="48b6f-326">GCSuspendEE_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="48b6f-327">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-328">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-328">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-329">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-331">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-331">Informational (4)</span></span>|

<span data-ttu-id="48b6f-332">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-332">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-333">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-333">Event</span></span>|<span data-ttu-id="48b6f-334">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-334">Event ID</span></span>|<span data-ttu-id="48b6f-335">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="48b6f-336">9</span><span class="sxs-lookup"><span data-stu-id="48b6f-336">9</span></span>|<span data-ttu-id="48b6f-337">ガベージ コレクションのための実行エンジンの中断の開始。</span><span class="sxs-lookup"><span data-stu-id="48b6f-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="48b6f-338">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-338">The following table shows the event data:</span></span>

|<span data-ttu-id="48b6f-339">フィールド名</span><span class="sxs-lookup"><span data-stu-id="48b6f-339">Field name</span></span>|<span data-ttu-id="48b6f-340">データの種類</span><span class="sxs-lookup"><span data-stu-id="48b6f-340">Data type</span></span>|<span data-ttu-id="48b6f-341">説明</span><span class="sxs-lookup"><span data-stu-id="48b6f-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="48b6f-342">理由</span><span class="sxs-lookup"><span data-stu-id="48b6f-342">Reason</span></span>|<span data-ttu-id="48b6f-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="48b6f-343">win:UInt16</span></span>|<span data-ttu-id="48b6f-344">0x0 - その他。</span><span class="sxs-lookup"><span data-stu-id="48b6f-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="48b6f-345">0x1 - ガベージ コレクション。</span><span class="sxs-lookup"><span data-stu-id="48b6f-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="48b6f-346">0x2 - アプリケーション ドメインのシャットダウン。</span><span class="sxs-lookup"><span data-stu-id="48b6f-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="48b6f-347">0x3 - コード ピッチ。</span><span class="sxs-lookup"><span data-stu-id="48b6f-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="48b6f-348">0x4 - シャットダウン。</span><span class="sxs-lookup"><span data-stu-id="48b6f-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="48b6f-349">0x5 - デバッガー。</span><span class="sxs-lookup"><span data-stu-id="48b6f-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="48b6f-350">0x6 - ガベージ コレクションの準備。</span><span class="sxs-lookup"><span data-stu-id="48b6f-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="48b6f-351">カウント</span><span class="sxs-lookup"><span data-stu-id="48b6f-351">Count</span></span>|<span data-ttu-id="48b6f-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-352">win:UInt32</span></span>|<span data-ttu-id="48b6f-353">その時点の GC カウント。</span><span class="sxs-lookup"><span data-stu-id="48b6f-353">The GC count at the time.</span></span> <span data-ttu-id="48b6f-354">通常、この後に後続の GC 開始イベントが表示され、そのカウントは、ガベージ コレクション中に、GC インデックスが増えるため、このカウント + 1 になります。</span><span class="sxs-lookup"><span data-stu-id="48b6f-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="48b6f-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="48b6f-355">ClrInstanceID</span></span>|<span data-ttu-id="48b6f-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="48b6f-356">win:UInt16</span></span>|<span data-ttu-id="48b6f-357">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="48b6f-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="48b6f-358">GCSuspendEEEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="48b6f-359">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-360">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-360">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-361">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-363">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-363">Informational (4)</span></span>|

<span data-ttu-id="48b6f-364">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-364">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-365">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-365">Event</span></span>|<span data-ttu-id="48b6f-366">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-366">Event ID</span></span>|<span data-ttu-id="48b6f-367">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="48b6f-368">8</span><span class="sxs-lookup"><span data-stu-id="48b6f-368">8</span></span>|<span data-ttu-id="48b6f-369">ガベージ コレクションのための実行エンジンの中断の終了。</span><span class="sxs-lookup"><span data-stu-id="48b6f-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="48b6f-370">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="48b6f-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="48b6f-371">GCAllocationTick_V2 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="48b6f-372">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-373">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-373">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-374">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-376">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-376">Informational (4)</span></span>|

<span data-ttu-id="48b6f-377">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-377">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-378">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-378">Event</span></span>|<span data-ttu-id="48b6f-379">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-379">Event ID</span></span>|<span data-ttu-id="48b6f-380">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="48b6f-381">10</span><span class="sxs-lookup"><span data-stu-id="48b6f-381">10</span></span>|<span data-ttu-id="48b6f-382">約 100 KB が割り当てられるたび。</span><span class="sxs-lookup"><span data-stu-id="48b6f-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="48b6f-383">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-383">The following table shows the event data:</span></span>

|<span data-ttu-id="48b6f-384">フィールド名</span><span class="sxs-lookup"><span data-stu-id="48b6f-384">Field name</span></span>|<span data-ttu-id="48b6f-385">データの種類</span><span class="sxs-lookup"><span data-stu-id="48b6f-385">Data type</span></span>|<span data-ttu-id="48b6f-386">説明</span><span class="sxs-lookup"><span data-stu-id="48b6f-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="48b6f-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="48b6f-387">AllocationAmount</span></span>|<span data-ttu-id="48b6f-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-388">win:UInt32</span></span>|<span data-ttu-id="48b6f-389">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-389">The allocation size, in bytes.</span></span> <span data-ttu-id="48b6f-390">この値は、ULONG (4,294,967,295 バイト) の長さより短い割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="48b6f-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="48b6f-391">割り当てがこれを超える場合、このフィールドには切り捨てられた値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48b6f-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="48b6f-392">非常に大きな割り当てには `AllocationAmount64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="48b6f-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="48b6f-393">AllocationKind</span></span>|<span data-ttu-id="48b6f-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-394">win:UInt32</span></span>|<span data-ttu-id="48b6f-395">0x0 - 小さなオブジェクトの割り当て (小さなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="48b6f-396">0x1 - 大きなオブジェクトの割り当て (大きなオブジェクト ヒープへの割り当て)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="48b6f-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="48b6f-397">ClrInstanceID</span></span>|<span data-ttu-id="48b6f-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="48b6f-398">win:UInt16</span></span>|<span data-ttu-id="48b6f-399">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="48b6f-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="48b6f-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="48b6f-400">AllocationAmount64</span></span>|<span data-ttu-id="48b6f-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="48b6f-401">win:UInt64</span></span>|<span data-ttu-id="48b6f-402">割り当てサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="48b6f-402">The allocation size, in bytes.</span></span> <span data-ttu-id="48b6f-403">この値は非常に大きな割り当ての場合に正確です。</span><span class="sxs-lookup"><span data-stu-id="48b6f-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="48b6f-404">TypeId</span><span class="sxs-lookup"><span data-stu-id="48b6f-404">TypeId</span></span>|<span data-ttu-id="48b6f-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="48b6f-405">win:Pointer</span></span>|<span data-ttu-id="48b6f-406">MethodTable のアドレス。</span><span class="sxs-lookup"><span data-stu-id="48b6f-406">The address of the MethodTable.</span></span> <span data-ttu-id="48b6f-407">このイベント中に複数の型のオブジェクトが割り当てられた場合、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) に対応する MethodTable のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="48b6f-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="48b6f-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="48b6f-408">TypeName</span></span>|<span data-ttu-id="48b6f-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="48b6f-409">win:UnicodeString</span></span>|<span data-ttu-id="48b6f-410">割り当てられた型の名前。</span><span class="sxs-lookup"><span data-stu-id="48b6f-410">The name of the type that was allocated.</span></span> <span data-ttu-id="48b6f-411">このイベント中に複数の型のオブジェクトが割り当てられた場合は、これは最後に割り当てられたオブジェクト (100 KB のしきい値を超えたオブジェクト) の型です。</span><span class="sxs-lookup"><span data-stu-id="48b6f-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="48b6f-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="48b6f-412">HeapIndex</span></span>|<span data-ttu-id="48b6f-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-413">win:UInt32</span></span>|<span data-ttu-id="48b6f-414">オブジェクトが割り当てられたヒープ。</span><span class="sxs-lookup"><span data-stu-id="48b6f-414">The heap where the object was allocated.</span></span> <span data-ttu-id="48b6f-415">ワークステーションのガベージ コレクションと共に実行する場合、この値は 0 (ゼロ) になります。</span><span class="sxs-lookup"><span data-stu-id="48b6f-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="48b6f-416">GCFinalizersBegin_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="48b6f-417">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-418">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-418">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-419">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-421">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-421">Informational (4)</span></span>|

<span data-ttu-id="48b6f-422">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-422">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-423">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-423">Event</span></span>|<span data-ttu-id="48b6f-424">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-424">Event ID</span></span>|<span data-ttu-id="48b6f-425">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="48b6f-426">14</span><span class="sxs-lookup"><span data-stu-id="48b6f-426">14</span></span>|<span data-ttu-id="48b6f-427">ファイナライザーの実行の開始。</span><span class="sxs-lookup"><span data-stu-id="48b6f-427">The start of running finalizers.</span></span>|

<span data-ttu-id="48b6f-428">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="48b6f-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="48b6f-429">GCFinalizersEnd_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="48b6f-430">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-431">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-431">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-432">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-434">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-434">Informational (4)</span></span>|

<span data-ttu-id="48b6f-435">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-435">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-436">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-436">Event</span></span>|<span data-ttu-id="48b6f-437">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-437">Event ID</span></span>|<span data-ttu-id="48b6f-438">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="48b6f-439">13</span><span class="sxs-lookup"><span data-stu-id="48b6f-439">13</span></span>|<span data-ttu-id="48b6f-440">ファイナライザーの実行の終了。</span><span class="sxs-lookup"><span data-stu-id="48b6f-440">The end of running finalizers.</span></span>|

<span data-ttu-id="48b6f-441">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-441">The following table shows the event data:</span></span>

|<span data-ttu-id="48b6f-442">フィールド名</span><span class="sxs-lookup"><span data-stu-id="48b6f-442">Field name</span></span>|<span data-ttu-id="48b6f-443">データの種類</span><span class="sxs-lookup"><span data-stu-id="48b6f-443">Data type</span></span>|<span data-ttu-id="48b6f-444">説明</span><span class="sxs-lookup"><span data-stu-id="48b6f-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="48b6f-445">カウント</span><span class="sxs-lookup"><span data-stu-id="48b6f-445">Count</span></span>|<span data-ttu-id="48b6f-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="48b6f-446">win:UInt32</span></span>|<span data-ttu-id="48b6f-447">実行されたファイナライザーの数。</span><span class="sxs-lookup"><span data-stu-id="48b6f-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="48b6f-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="48b6f-448">ClrInstanceID</span></span>|<span data-ttu-id="48b6f-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="48b6f-449">win:UInt16</span></span>|<span data-ttu-id="48b6f-450">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="48b6f-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="48b6f-451">GCCreateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="48b6f-452">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-453">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-453">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-454">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-456">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-456">Informational (4)</span></span>|
|<span data-ttu-id="48b6f-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48b6f-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48b6f-458">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-458">Informational (4)</span></span>|

<span data-ttu-id="48b6f-459">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-459">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-460">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-460">Event</span></span>|<span data-ttu-id="48b6f-461">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-461">Event ID</span></span>|<span data-ttu-id="48b6f-462">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="48b6f-463">11</span><span class="sxs-lookup"><span data-stu-id="48b6f-463">11</span></span>|<span data-ttu-id="48b6f-464">同時実行ガベージ コレクション スレッドが作成されました。</span><span class="sxs-lookup"><span data-stu-id="48b6f-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="48b6f-465">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="48b6f-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="48b6f-466">GCTerminateConcurrentThread_V1 イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="48b6f-467">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="48b6f-468">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="48b6f-468">Keyword for raising the event</span></span>|<span data-ttu-id="48b6f-469">レベル</span><span class="sxs-lookup"><span data-stu-id="48b6f-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="48b6f-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="48b6f-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="48b6f-471">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-471">Informational (4)</span></span>|
|<span data-ttu-id="48b6f-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="48b6f-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="48b6f-473">情報提供 (4)</span><span class="sxs-lookup"><span data-stu-id="48b6f-473">Informational (4)</span></span>|

<span data-ttu-id="48b6f-474">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="48b6f-474">The following table shows the event information:</span></span>

|<span data-ttu-id="48b6f-475">event</span><span class="sxs-lookup"><span data-stu-id="48b6f-475">Event</span></span>|<span data-ttu-id="48b6f-476">イベント ID</span><span class="sxs-lookup"><span data-stu-id="48b6f-476">Event ID</span></span>|<span data-ttu-id="48b6f-477">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="48b6f-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="48b6f-478">12</span><span class="sxs-lookup"><span data-stu-id="48b6f-478">12</span></span>|<span data-ttu-id="48b6f-479">同時実行ガベージ コレクションスレッドが終了しました。</span><span class="sxs-lookup"><span data-stu-id="48b6f-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="48b6f-480">イベント データはありません。</span><span class="sxs-lookup"><span data-stu-id="48b6f-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="48b6f-481">関連項目</span><span class="sxs-lookup"><span data-stu-id="48b6f-481">See also</span></span>

- [<span data-ttu-id="48b6f-482">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="48b6f-482">CLR ETW Events</span></span>](clr-etw-events.md)
