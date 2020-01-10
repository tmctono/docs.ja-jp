---
title: アプリケーション ドメインのリソース監視 (ARM) ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: 0e453b2bafffd9e07a1bdddd97282c5b97f5483d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716225"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="aeed6-102">アプリケーション ドメインのリソース監視 (ARM) ETW イベント</span><span class="sxs-lookup"><span data-stu-id="aeed6-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="aeed6-103">これらのイベントは、アプリケーション ドメインの状態に関する詳細な診断の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="aeed6-104">これらのイベントを使用することもできますが、アプリケーション ドメインのリソース監視 (ARM) の機能を使用しても同じ情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="aeed6-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="aeed6-105">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="aeed6-105">ThreadCreated Event</span></span>

<span data-ttu-id="aeed6-106">このイベントは、ランダウン プロバイダーで `ThreadDC` としても発生します  ( `AppDomainResourceManagementRundownKeyword` キーワードで発生)。</span><span class="sxs-lookup"><span data-stu-id="aeed6-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="aeed6-107">これは、このカテゴリでランダウン プロバイダーで発生する唯一のイベントです。</span><span class="sxs-lookup"><span data-stu-id="aeed6-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="aeed6-108">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="aeed6-109">詳細については、「 [CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeed6-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="aeed6-110">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="aeed6-110">Keyword for raising the event</span></span>|<span data-ttu-id="aeed6-111">レベル</span><span class="sxs-lookup"><span data-stu-id="aeed6-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="aeed6-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="aeed6-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="aeed6-113">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="aeed6-113">Informational(4)</span></span>|
|<span data-ttu-id="aeed6-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="aeed6-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="aeed6-115">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="aeed6-115">Informational(4)</span></span>|

<span data-ttu-id="aeed6-116">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-116">The following table shows the event information:</span></span>

|<span data-ttu-id="aeed6-117">Event</span><span class="sxs-lookup"><span data-stu-id="aeed6-117">Event</span></span>|<span data-ttu-id="aeed6-118">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aeed6-118">Event ID</span></span>|<span data-ttu-id="aeed6-119">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="aeed6-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="aeed6-120">85</span><span class="sxs-lookup"><span data-stu-id="aeed6-120">85</span></span>|<span data-ttu-id="aeed6-121">アプリケーション ドメインに対してスレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="aeed6-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="aeed6-122">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-122">The following table shows the event data:</span></span>

|<span data-ttu-id="aeed6-123">フィールド名</span><span class="sxs-lookup"><span data-stu-id="aeed6-123">Field name</span></span>|<span data-ttu-id="aeed6-124">[データ型]</span><span class="sxs-lookup"><span data-stu-id="aeed6-124">Data type</span></span>|<span data-ttu-id="aeed6-125">説明</span><span class="sxs-lookup"><span data-stu-id="aeed6-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="aeed6-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="aeed6-126">ThreadID</span></span>|<span data-ttu-id="aeed6-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-127">win:UInt64</span></span>|<span data-ttu-id="aeed6-128">作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="aeed6-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="aeed6-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="aeed6-129">AppDomainID</span></span>|<span data-ttu-id="aeed6-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-130">win:UInt64</span></span>|<span data-ttu-id="aeed6-131">スレッドのアクティビティの報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="aeed6-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="aeed6-132">フラグ</span><span class="sxs-lookup"><span data-stu-id="aeed6-132">Flags</span></span>|<span data-ttu-id="aeed6-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="aeed6-133">win:UInt32</span></span>|<span data-ttu-id="aeed6-134">スレッドの作成フラグ</span><span class="sxs-lookup"><span data-stu-id="aeed6-134">Thread creation flags.</span></span>|
|<span data-ttu-id="aeed6-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="aeed6-135">ManagedThreadIndex</span></span>|<span data-ttu-id="aeed6-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="aeed6-136">win:UInt32</span></span>|<span data-ttu-id="aeed6-137">作成されたスレッドのマネージド インデックス。</span><span class="sxs-lookup"><span data-stu-id="aeed6-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="aeed6-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="aeed6-138">OSThreadID</span></span>|<span data-ttu-id="aeed6-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="aeed6-139">win:UInt32</span></span>|<span data-ttu-id="aeed6-140">作成されたスレッドのオペレーティング システム ID。</span><span class="sxs-lookup"><span data-stu-id="aeed6-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="aeed6-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="aeed6-141">ClrInstanceID</span></span>|<span data-ttu-id="aeed6-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="aeed6-142">win:UInt16</span></span>|<span data-ttu-id="aeed6-143">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="aeed6-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="aeed6-144">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="aeed6-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="aeed6-145">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="aeed6-146">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="aeed6-146">Keyword for raising the event</span></span>|<span data-ttu-id="aeed6-147">レベル</span><span class="sxs-lookup"><span data-stu-id="aeed6-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="aeed6-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="aeed6-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="aeed6-149">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="aeed6-149">Informational(4)</span></span>|

<span data-ttu-id="aeed6-150">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-150">The following table shows the event information:</span></span>

|<span data-ttu-id="aeed6-151">Event</span><span class="sxs-lookup"><span data-stu-id="aeed6-151">Event</span></span>|<span data-ttu-id="aeed6-152">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aeed6-152">Event ID</span></span>|<span data-ttu-id="aeed6-153">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="aeed6-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="aeed6-154">83</span><span class="sxs-lookup"><span data-stu-id="aeed6-154">83</span></span>|<span data-ttu-id="aeed6-155">アプリケーション ドメインに 4 MB ずつのメモリ (概算) が割り当てられる。</span><span class="sxs-lookup"><span data-stu-id="aeed6-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="aeed6-156">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-156">The following table shows the event data:</span></span>

|<span data-ttu-id="aeed6-157">フィールド名</span><span class="sxs-lookup"><span data-stu-id="aeed6-157">Field name</span></span>|<span data-ttu-id="aeed6-158">[データ型]</span><span class="sxs-lookup"><span data-stu-id="aeed6-158">Data type</span></span>|<span data-ttu-id="aeed6-159">説明</span><span class="sxs-lookup"><span data-stu-id="aeed6-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="aeed6-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="aeed6-160">AppDomainID</span></span>|<span data-ttu-id="aeed6-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-161">win:UInt64</span></span>|<span data-ttu-id="aeed6-162">リソースの使用状況の報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="aeed6-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="aeed6-163">Allocated</span><span class="sxs-lookup"><span data-stu-id="aeed6-163">Allocated</span></span>|<span data-ttu-id="aeed6-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-164">win:UInt64</span></span>|<span data-ttu-id="aeed6-165">アプリケーション ドメインが作成されてから、このアプリケーション ドメインに割り当てられたバイトの合計数 (解放されたメモリの量は引かれない)。</span><span class="sxs-lookup"><span data-stu-id="aeed6-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="aeed6-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="aeed6-166">ClrInstanceID</span></span>|<span data-ttu-id="aeed6-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="aeed6-167">win:UInt16</span></span>|<span data-ttu-id="aeed6-168">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="aeed6-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="aeed6-169">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="aeed6-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="aeed6-170">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="aeed6-171">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="aeed6-171">Keyword for raising the event</span></span>|<span data-ttu-id="aeed6-172">レベル</span><span class="sxs-lookup"><span data-stu-id="aeed6-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="aeed6-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="aeed6-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="aeed6-174">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="aeed6-174">Informational(4)</span></span>|

<span data-ttu-id="aeed6-175">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-175">The following table shows the event information:</span></span>

|<span data-ttu-id="aeed6-176">Event</span><span class="sxs-lookup"><span data-stu-id="aeed6-176">Event</span></span>|<span data-ttu-id="aeed6-177">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aeed6-177">Event ID</span></span>|<span data-ttu-id="aeed6-178">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="aeed6-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="aeed6-179">84</span><span class="sxs-lookup"><span data-stu-id="aeed6-179">84</span></span>|<span data-ttu-id="aeed6-180">各ガベージ コレクションが終了した。</span><span class="sxs-lookup"><span data-stu-id="aeed6-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="aeed6-181">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-181">The following table shows the event data:</span></span>

|<span data-ttu-id="aeed6-182">フィールド名</span><span class="sxs-lookup"><span data-stu-id="aeed6-182">Field name</span></span>|<span data-ttu-id="aeed6-183">[データ型]</span><span class="sxs-lookup"><span data-stu-id="aeed6-183">Data type</span></span>|<span data-ttu-id="aeed6-184">説明</span><span class="sxs-lookup"><span data-stu-id="aeed6-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="aeed6-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="aeed6-185">AppDomainID</span></span>|<span data-ttu-id="aeed6-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-186">win:UInt64</span></span>|<span data-ttu-id="aeed6-187">リソースの使用状況の報告対象のドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="aeed6-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="aeed6-188">Survived</span><span class="sxs-lookup"><span data-stu-id="aeed6-188">Survived</span></span>|<span data-ttu-id="aeed6-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-189">win:UInt64</span></span>|<span data-ttu-id="aeed6-190">最後のコレクションの実行後に残され、このアプリケーション ドメインによって保持されることが判明しているバイト数。</span><span class="sxs-lookup"><span data-stu-id="aeed6-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="aeed6-191">この数は、完全なコレクションの後では正確で完全ですが、短期コレクションの後では完全ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aeed6-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="aeed6-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="aeed6-192">ProcessSurvived</span></span>|<span data-ttu-id="aeed6-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-193">win:UInt64</span></span>|<span data-ttu-id="aeed6-194">最後のコレクション後に残った合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="aeed6-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="aeed6-195">完全なコレクションの後では、この数はマネージド ヒープにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="aeed6-196">短期コレクションの後では、この数は短期のジェネレーションにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="aeed6-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="aeed6-197">ClrInstanceID</span></span>|<span data-ttu-id="aeed6-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="aeed6-198">win:UInt16</span></span>|<span data-ttu-id="aeed6-199">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="aeed6-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="aeed6-200">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="aeed6-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="aeed6-201">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="aeed6-202">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="aeed6-202">Keyword for raising the event</span></span>|<span data-ttu-id="aeed6-203">レベル</span><span class="sxs-lookup"><span data-stu-id="aeed6-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="aeed6-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="aeed6-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="aeed6-205">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="aeed6-205">Informational(4)</span></span>|
|<span data-ttu-id="aeed6-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="aeed6-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="aeed6-207">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="aeed6-207">Informational(4)</span></span>|

<span data-ttu-id="aeed6-208">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-208">The following table shows the event information:</span></span>

|<span data-ttu-id="aeed6-209">Event</span><span class="sxs-lookup"><span data-stu-id="aeed6-209">Event</span></span>|<span data-ttu-id="aeed6-210">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aeed6-210">Event ID</span></span>|<span data-ttu-id="aeed6-211">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="aeed6-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="aeed6-212">87</span><span class="sxs-lookup"><span data-stu-id="aeed6-212">87</span></span>|<span data-ttu-id="aeed6-213">アプリケーション ドメインにスレッドが入力される。</span><span class="sxs-lookup"><span data-stu-id="aeed6-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="aeed6-214">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-214">The following table shows the event data:</span></span>

|<span data-ttu-id="aeed6-215">フィールド名</span><span class="sxs-lookup"><span data-stu-id="aeed6-215">Field name</span></span>|<span data-ttu-id="aeed6-216">[データ型]</span><span class="sxs-lookup"><span data-stu-id="aeed6-216">Data type</span></span>|<span data-ttu-id="aeed6-217">説明</span><span class="sxs-lookup"><span data-stu-id="aeed6-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="aeed6-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="aeed6-218">ThreadID</span></span>|<span data-ttu-id="aeed6-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-219">win:UInt64</span></span>|<span data-ttu-id="aeed6-220">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="aeed6-220">The thread identifier.</span></span>|
|<span data-ttu-id="aeed6-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="aeed6-221">AppDomainID</span></span>|<span data-ttu-id="aeed6-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-222">win:UInt64</span></span>|<span data-ttu-id="aeed6-223">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="aeed6-223">The application domain identifier.</span></span>|
|<span data-ttu-id="aeed6-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="aeed6-224">ClrInstanceID</span></span>|<span data-ttu-id="aeed6-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="aeed6-225">win:UInt16</span></span>|<span data-ttu-id="aeed6-226">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="aeed6-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="aeed6-227">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="aeed6-227">ThreadTerminated Event</span></span>

<span data-ttu-id="aeed6-228">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="aeed6-229">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="aeed6-229">Keyword for raising the event</span></span>|<span data-ttu-id="aeed6-230">レベル</span><span class="sxs-lookup"><span data-stu-id="aeed6-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="aeed6-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="aeed6-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="aeed6-232">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="aeed6-232">Informational(4)</span></span>|
|<span data-ttu-id="aeed6-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="aeed6-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="aeed6-234">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="aeed6-234">Informational(4)</span></span>|

<span data-ttu-id="aeed6-235">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-235">The following table shows the event information:</span></span>

|<span data-ttu-id="aeed6-236">Event</span><span class="sxs-lookup"><span data-stu-id="aeed6-236">Event</span></span>|<span data-ttu-id="aeed6-237">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aeed6-237">Event ID</span></span>|<span data-ttu-id="aeed6-238">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="aeed6-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="aeed6-239">86</span><span class="sxs-lookup"><span data-stu-id="aeed6-239">86</span></span>|<span data-ttu-id="aeed6-240">スレッドが終了する。</span><span class="sxs-lookup"><span data-stu-id="aeed6-240">A thread terminates.</span></span>|

<span data-ttu-id="aeed6-241">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="aeed6-241">The following table shows the event data:</span></span>

|<span data-ttu-id="aeed6-242">フィールド名</span><span class="sxs-lookup"><span data-stu-id="aeed6-242">Field name</span></span>|<span data-ttu-id="aeed6-243">[データ型]</span><span class="sxs-lookup"><span data-stu-id="aeed6-243">Data type</span></span>|<span data-ttu-id="aeed6-244">説明</span><span class="sxs-lookup"><span data-stu-id="aeed6-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="aeed6-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="aeed6-245">ThreadID</span></span>|<span data-ttu-id="aeed6-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-246">win:UInt64</span></span>|<span data-ttu-id="aeed6-247">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="aeed6-247">The thread identifier.</span></span>|
|<span data-ttu-id="aeed6-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="aeed6-248">AppDomainID</span></span>|<span data-ttu-id="aeed6-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="aeed6-249">win:UInt64</span></span>|<span data-ttu-id="aeed6-250">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="aeed6-250">The application domain identifier.</span></span>|
|<span data-ttu-id="aeed6-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="aeed6-251">ClrInstanceID</span></span>|<span data-ttu-id="aeed6-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="aeed6-252">win:UInt16</span></span>|<span data-ttu-id="aeed6-253">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="aeed6-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="aeed6-254">関連項目</span><span class="sxs-lookup"><span data-stu-id="aeed6-254">See also</span></span>

- [<span data-ttu-id="aeed6-255">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="aeed6-255">CLR ETW Events</span></span>](clr-etw-events.md)
