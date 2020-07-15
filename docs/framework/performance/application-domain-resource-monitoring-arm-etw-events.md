---
title: アプリケーション ドメインのリソース監視 (ARM) ETW イベント
description: ThreadCreated、AppDomainMemAllocated、AppDomainMemSurvived など、.NET でのアプリケーションドメインリソース監視 (ARM) ETW イベントについて説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: d118b3196b019a804df5399464cb86f7492c61b0
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309782"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="ea3c8-103">アプリケーション ドメインのリソース監視 (ARM) ETW イベント</span><span class="sxs-lookup"><span data-stu-id="ea3c8-103">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="ea3c8-104">これらのイベントは、アプリケーション ドメインの状態に関する詳細な診断の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-104">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="ea3c8-105">これらのイベントを使用することもできますが、アプリケーション ドメインのリソース監視 (ARM) の機能を使用しても同じ情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-105">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="ea3c8-106">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="ea3c8-106">ThreadCreated Event</span></span>

<span data-ttu-id="ea3c8-107">このイベントは、ランダウン プロバイダーで `ThreadDC` としても発生します  ( `AppDomainResourceManagementRundownKeyword` キーワードで発生)。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-107">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="ea3c8-108">これは、このカテゴリでランダウン プロバイダーで発生する唯一のイベントです。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-108">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="ea3c8-109">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-109">The following table shows the keyword and level.</span></span> <span data-ttu-id="ea3c8-110">詳細については、「 [CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-110">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="ea3c8-111">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="ea3c8-111">Keyword for raising the event</span></span>|<span data-ttu-id="ea3c8-112">レベル</span><span class="sxs-lookup"><span data-stu-id="ea3c8-112">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ea3c8-113">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-113">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ea3c8-114">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-114">Informational(4)</span></span>|
|<span data-ttu-id="ea3c8-115">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-115">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ea3c8-116">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-116">Informational(4)</span></span>|

<span data-ttu-id="ea3c8-117">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-117">The following table shows the event information:</span></span>

|<span data-ttu-id="ea3c8-118">Event</span><span class="sxs-lookup"><span data-stu-id="ea3c8-118">Event</span></span>|<span data-ttu-id="ea3c8-119">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-119">Event ID</span></span>|<span data-ttu-id="ea3c8-120">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="ea3c8-120">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="ea3c8-121">85</span><span class="sxs-lookup"><span data-stu-id="ea3c8-121">85</span></span>|<span data-ttu-id="ea3c8-122">アプリケーション ドメインに対してスレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-122">A thread was created for the application domain.</span></span>|

<span data-ttu-id="ea3c8-123">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-123">The following table shows the event data:</span></span>

|<span data-ttu-id="ea3c8-124">フィールド名</span><span class="sxs-lookup"><span data-stu-id="ea3c8-124">Field name</span></span>|<span data-ttu-id="ea3c8-125">データ型</span><span class="sxs-lookup"><span data-stu-id="ea3c8-125">Data type</span></span>|<span data-ttu-id="ea3c8-126">説明</span><span class="sxs-lookup"><span data-stu-id="ea3c8-126">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ea3c8-127">ThreadID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-127">ThreadID</span></span>|<span data-ttu-id="ea3c8-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-128">win:UInt64</span></span>|<span data-ttu-id="ea3c8-129">作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-129">ID of the thread that was created.</span></span>|
|<span data-ttu-id="ea3c8-130">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-130">AppDomainID</span></span>|<span data-ttu-id="ea3c8-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-131">win:UInt64</span></span>|<span data-ttu-id="ea3c8-132">スレッドのアクティビティの報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-132">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="ea3c8-133">Flags</span><span class="sxs-lookup"><span data-stu-id="ea3c8-133">Flags</span></span>|<span data-ttu-id="ea3c8-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea3c8-134">win:UInt32</span></span>|<span data-ttu-id="ea3c8-135">スレッドの作成フラグ</span><span class="sxs-lookup"><span data-stu-id="ea3c8-135">Thread creation flags.</span></span>|
|<span data-ttu-id="ea3c8-136">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="ea3c8-136">ManagedThreadIndex</span></span>|<span data-ttu-id="ea3c8-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea3c8-137">win:UInt32</span></span>|<span data-ttu-id="ea3c8-138">作成されたスレッドのマネージド インデックス。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-138">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="ea3c8-139">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-139">OSThreadID</span></span>|<span data-ttu-id="ea3c8-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea3c8-140">win:UInt32</span></span>|<span data-ttu-id="ea3c8-141">作成されたスレッドのオペレーティング システム ID。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-141">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="ea3c8-142">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-142">ClrInstanceID</span></span>|<span data-ttu-id="ea3c8-143">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea3c8-143">win:UInt16</span></span>|<span data-ttu-id="ea3c8-144">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="ea3c8-145">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="ea3c8-145">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="ea3c8-146">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-146">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ea3c8-147">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="ea3c8-147">Keyword for raising the event</span></span>|<span data-ttu-id="ea3c8-148">レベル</span><span class="sxs-lookup"><span data-stu-id="ea3c8-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ea3c8-149">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-149">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ea3c8-150">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-150">Informational(4)</span></span>|

<span data-ttu-id="ea3c8-151">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-151">The following table shows the event information:</span></span>

|<span data-ttu-id="ea3c8-152">Event</span><span class="sxs-lookup"><span data-stu-id="ea3c8-152">Event</span></span>|<span data-ttu-id="ea3c8-153">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-153">Event ID</span></span>|<span data-ttu-id="ea3c8-154">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="ea3c8-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="ea3c8-155">83</span><span class="sxs-lookup"><span data-stu-id="ea3c8-155">83</span></span>|<span data-ttu-id="ea3c8-156">アプリケーション ドメインに 4 MB ずつのメモリ (概算) が割り当てられる。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-156">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="ea3c8-157">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-157">The following table shows the event data:</span></span>

|<span data-ttu-id="ea3c8-158">フィールド名</span><span class="sxs-lookup"><span data-stu-id="ea3c8-158">Field name</span></span>|<span data-ttu-id="ea3c8-159">データ型</span><span class="sxs-lookup"><span data-stu-id="ea3c8-159">Data type</span></span>|<span data-ttu-id="ea3c8-160">説明</span><span class="sxs-lookup"><span data-stu-id="ea3c8-160">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ea3c8-161">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-161">AppDomainID</span></span>|<span data-ttu-id="ea3c8-162">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-162">win:UInt64</span></span>|<span data-ttu-id="ea3c8-163">リソースの使用状況の報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-163">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="ea3c8-164">Allocated</span><span class="sxs-lookup"><span data-stu-id="ea3c8-164">Allocated</span></span>|<span data-ttu-id="ea3c8-165">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-165">win:UInt64</span></span>|<span data-ttu-id="ea3c8-166">アプリケーション ドメインが作成されてから、このアプリケーション ドメインに割り当てられたバイトの合計数 (解放されたメモリの量は引かれない)。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-166">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="ea3c8-167">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-167">ClrInstanceID</span></span>|<span data-ttu-id="ea3c8-168">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea3c8-168">win:UInt16</span></span>|<span data-ttu-id="ea3c8-169">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-169">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="ea3c8-170">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="ea3c8-170">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="ea3c8-171">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-171">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ea3c8-172">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="ea3c8-172">Keyword for raising the event</span></span>|<span data-ttu-id="ea3c8-173">レベル</span><span class="sxs-lookup"><span data-stu-id="ea3c8-173">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ea3c8-174">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-174">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ea3c8-175">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-175">Informational(4)</span></span>|

<span data-ttu-id="ea3c8-176">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-176">The following table shows the event information:</span></span>

|<span data-ttu-id="ea3c8-177">Event</span><span class="sxs-lookup"><span data-stu-id="ea3c8-177">Event</span></span>|<span data-ttu-id="ea3c8-178">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-178">Event ID</span></span>|<span data-ttu-id="ea3c8-179">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="ea3c8-179">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="ea3c8-180">84</span><span class="sxs-lookup"><span data-stu-id="ea3c8-180">84</span></span>|<span data-ttu-id="ea3c8-181">各ガベージ コレクションが終了した。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-181">Each garbage collection has ended.</span></span>|

<span data-ttu-id="ea3c8-182">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-182">The following table shows the event data:</span></span>

|<span data-ttu-id="ea3c8-183">フィールド名</span><span class="sxs-lookup"><span data-stu-id="ea3c8-183">Field name</span></span>|<span data-ttu-id="ea3c8-184">データ型</span><span class="sxs-lookup"><span data-stu-id="ea3c8-184">Data type</span></span>|<span data-ttu-id="ea3c8-185">説明</span><span class="sxs-lookup"><span data-stu-id="ea3c8-185">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ea3c8-186">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-186">AppDomainID</span></span>|<span data-ttu-id="ea3c8-187">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-187">win:UInt64</span></span>|<span data-ttu-id="ea3c8-188">リソースの使用状況の報告対象のドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-188">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="ea3c8-189">Survived</span><span class="sxs-lookup"><span data-stu-id="ea3c8-189">Survived</span></span>|<span data-ttu-id="ea3c8-190">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-190">win:UInt64</span></span>|<span data-ttu-id="ea3c8-191">最後のコレクションの実行後に残され、このアプリケーション ドメインによって保持されることが判明しているバイト数。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-191">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="ea3c8-192">この数は、完全なコレクションの後では正確で完全ですが、短期コレクションの後では完全ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-192">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="ea3c8-193">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="ea3c8-193">ProcessSurvived</span></span>|<span data-ttu-id="ea3c8-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-194">win:UInt64</span></span>|<span data-ttu-id="ea3c8-195">最後のコレクション後に残った合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-195">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="ea3c8-196">完全なコレクションの後では、この数はマネージド ヒープにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-196">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="ea3c8-197">短期コレクションの後では、この数は短期のジェネレーションにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-197">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="ea3c8-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-198">ClrInstanceID</span></span>|<span data-ttu-id="ea3c8-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea3c8-199">win:UInt16</span></span>|<span data-ttu-id="ea3c8-200">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="ea3c8-201">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="ea3c8-201">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="ea3c8-202">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-202">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ea3c8-203">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="ea3c8-203">Keyword for raising the event</span></span>|<span data-ttu-id="ea3c8-204">レベル</span><span class="sxs-lookup"><span data-stu-id="ea3c8-204">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ea3c8-205">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-205">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ea3c8-206">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-206">Informational(4)</span></span>|
|<span data-ttu-id="ea3c8-207">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-207">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ea3c8-208">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-208">Informational(4)</span></span>|

<span data-ttu-id="ea3c8-209">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-209">The following table shows the event information:</span></span>

|<span data-ttu-id="ea3c8-210">Event</span><span class="sxs-lookup"><span data-stu-id="ea3c8-210">Event</span></span>|<span data-ttu-id="ea3c8-211">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-211">Event ID</span></span>|<span data-ttu-id="ea3c8-212">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="ea3c8-212">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="ea3c8-213">87</span><span class="sxs-lookup"><span data-stu-id="ea3c8-213">87</span></span>|<span data-ttu-id="ea3c8-214">アプリケーション ドメインにスレッドが入力される。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-214">A thread enters an application domain.</span></span>|

<span data-ttu-id="ea3c8-215">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-215">The following table shows the event data:</span></span>

|<span data-ttu-id="ea3c8-216">フィールド名</span><span class="sxs-lookup"><span data-stu-id="ea3c8-216">Field name</span></span>|<span data-ttu-id="ea3c8-217">データ型</span><span class="sxs-lookup"><span data-stu-id="ea3c8-217">Data type</span></span>|<span data-ttu-id="ea3c8-218">説明</span><span class="sxs-lookup"><span data-stu-id="ea3c8-218">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ea3c8-219">ThreadID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-219">ThreadID</span></span>|<span data-ttu-id="ea3c8-220">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-220">win:UInt64</span></span>|<span data-ttu-id="ea3c8-221">スレッド識別子です。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-221">The thread identifier.</span></span>|
|<span data-ttu-id="ea3c8-222">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-222">AppDomainID</span></span>|<span data-ttu-id="ea3c8-223">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-223">win:UInt64</span></span>|<span data-ttu-id="ea3c8-224">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-224">The application domain identifier.</span></span>|
|<span data-ttu-id="ea3c8-225">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-225">ClrInstanceID</span></span>|<span data-ttu-id="ea3c8-226">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea3c8-226">win:UInt16</span></span>|<span data-ttu-id="ea3c8-227">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-227">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="ea3c8-228">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="ea3c8-228">ThreadTerminated Event</span></span>

<span data-ttu-id="ea3c8-229">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-229">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ea3c8-230">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="ea3c8-230">Keyword for raising the event</span></span>|<span data-ttu-id="ea3c8-231">レベル</span><span class="sxs-lookup"><span data-stu-id="ea3c8-231">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ea3c8-232">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-232">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ea3c8-233">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-233">Informational(4)</span></span>|
|<span data-ttu-id="ea3c8-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ea3c8-235">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="ea3c8-235">Informational(4)</span></span>|

<span data-ttu-id="ea3c8-236">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-236">The following table shows the event information:</span></span>

|<span data-ttu-id="ea3c8-237">Event</span><span class="sxs-lookup"><span data-stu-id="ea3c8-237">Event</span></span>|<span data-ttu-id="ea3c8-238">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-238">Event ID</span></span>|<span data-ttu-id="ea3c8-239">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="ea3c8-239">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="ea3c8-240">86</span><span class="sxs-lookup"><span data-stu-id="ea3c8-240">86</span></span>|<span data-ttu-id="ea3c8-241">スレッドが終了する。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-241">A thread terminates.</span></span>|

<span data-ttu-id="ea3c8-242">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-242">The following table shows the event data:</span></span>

|<span data-ttu-id="ea3c8-243">フィールド名</span><span class="sxs-lookup"><span data-stu-id="ea3c8-243">Field name</span></span>|<span data-ttu-id="ea3c8-244">データ型</span><span class="sxs-lookup"><span data-stu-id="ea3c8-244">Data type</span></span>|<span data-ttu-id="ea3c8-245">説明</span><span class="sxs-lookup"><span data-stu-id="ea3c8-245">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ea3c8-246">ThreadID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-246">ThreadID</span></span>|<span data-ttu-id="ea3c8-247">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-247">win:UInt64</span></span>|<span data-ttu-id="ea3c8-248">スレッド識別子です。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-248">The thread identifier.</span></span>|
|<span data-ttu-id="ea3c8-249">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-249">AppDomainID</span></span>|<span data-ttu-id="ea3c8-250">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea3c8-250">win:UInt64</span></span>|<span data-ttu-id="ea3c8-251">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-251">The application domain identifier.</span></span>|
|<span data-ttu-id="ea3c8-252">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea3c8-252">ClrInstanceID</span></span>|<span data-ttu-id="ea3c8-253">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea3c8-253">win:UInt16</span></span>|<span data-ttu-id="ea3c8-254">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ea3c8-254">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ea3c8-255">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea3c8-255">See also</span></span>

- [<span data-ttu-id="ea3c8-256">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="ea3c8-256">CLR ETW Events</span></span>](clr-etw-events.md)
