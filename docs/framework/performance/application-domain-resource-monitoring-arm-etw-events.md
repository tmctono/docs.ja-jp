---
title: アプリケーション ドメインのリソース監視 (ARM) ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e1c2a38be6f2c15a118b35925570119b474f096
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040565"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="613c1-102">アプリケーション ドメインのリソース監視 (ARM) ETW イベント</span><span class="sxs-lookup"><span data-stu-id="613c1-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="613c1-103">これらのイベントは、アプリケーション ドメインの状態に関する詳細な診断の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="613c1-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="613c1-104">これらのイベントを使用することもできますが、アプリケーション ドメインのリソース監視 (ARM) の機能を使用しても同じ情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="613c1-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="613c1-105">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="613c1-105">ThreadCreated Event</span></span>

<span data-ttu-id="613c1-106">このイベントは、ランダウン プロバイダーで `ThreadDC` としても発生します  ( `AppDomainResourceManagementRundownKeyword` キーワードで発生)。</span><span class="sxs-lookup"><span data-stu-id="613c1-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="613c1-107">これは、このカテゴリでランダウン プロバイダーで発生する唯一のイベントです。</span><span class="sxs-lookup"><span data-stu-id="613c1-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="613c1-108">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="613c1-109">詳細については、「 [CLR ETW のキーワードとレベル](clr-etw-keywords-and-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="613c1-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="613c1-110">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="613c1-110">Keyword for raising the event</span></span>|<span data-ttu-id="613c1-111">レベル</span><span class="sxs-lookup"><span data-stu-id="613c1-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="613c1-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="613c1-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="613c1-113">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="613c1-113">Informational(4)</span></span>|
|<span data-ttu-id="613c1-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="613c1-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="613c1-115">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="613c1-115">Informational(4)</span></span>|

<span data-ttu-id="613c1-116">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-116">The following table shows the event information:</span></span>

|<span data-ttu-id="613c1-117">event</span><span class="sxs-lookup"><span data-stu-id="613c1-117">Event</span></span>|<span data-ttu-id="613c1-118">イベント ID</span><span class="sxs-lookup"><span data-stu-id="613c1-118">Event ID</span></span>|<span data-ttu-id="613c1-119">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="613c1-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="613c1-120">85</span><span class="sxs-lookup"><span data-stu-id="613c1-120">85</span></span>|<span data-ttu-id="613c1-121">アプリケーション ドメインに対してスレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="613c1-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="613c1-122">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-122">The following table shows the event data:</span></span>

|<span data-ttu-id="613c1-123">フィールド名</span><span class="sxs-lookup"><span data-stu-id="613c1-123">Field name</span></span>|<span data-ttu-id="613c1-124">データの種類</span><span class="sxs-lookup"><span data-stu-id="613c1-124">Data type</span></span>|<span data-ttu-id="613c1-125">説明</span><span class="sxs-lookup"><span data-stu-id="613c1-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="613c1-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="613c1-126">ThreadID</span></span>|<span data-ttu-id="613c1-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-127">win:UInt64</span></span>|<span data-ttu-id="613c1-128">作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="613c1-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="613c1-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="613c1-129">AppDomainID</span></span>|<span data-ttu-id="613c1-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-130">win:UInt64</span></span>|<span data-ttu-id="613c1-131">スレッドのアクティビティの報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="613c1-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="613c1-132">フラグ</span><span class="sxs-lookup"><span data-stu-id="613c1-132">Flags</span></span>|<span data-ttu-id="613c1-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="613c1-133">win:UInt32</span></span>|<span data-ttu-id="613c1-134">スレッドの作成フラグ</span><span class="sxs-lookup"><span data-stu-id="613c1-134">Thread creation flags.</span></span>|
|<span data-ttu-id="613c1-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="613c1-135">ManagedThreadIndex</span></span>|<span data-ttu-id="613c1-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="613c1-136">win:UInt32</span></span>|<span data-ttu-id="613c1-137">作成されたスレッドのマネージド インデックス。</span><span class="sxs-lookup"><span data-stu-id="613c1-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="613c1-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="613c1-138">OSThreadID</span></span>|<span data-ttu-id="613c1-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="613c1-139">win:UInt32</span></span>|<span data-ttu-id="613c1-140">作成されたスレッドのオペレーティング システム ID。</span><span class="sxs-lookup"><span data-stu-id="613c1-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="613c1-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="613c1-141">ClrInstanceID</span></span>|<span data-ttu-id="613c1-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="613c1-142">win:UInt16</span></span>|<span data-ttu-id="613c1-143">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="613c1-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="613c1-144">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="613c1-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="613c1-145">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="613c1-146">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="613c1-146">Keyword for raising the event</span></span>|<span data-ttu-id="613c1-147">レベル</span><span class="sxs-lookup"><span data-stu-id="613c1-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="613c1-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="613c1-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="613c1-149">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="613c1-149">Informational(4)</span></span>|

<span data-ttu-id="613c1-150">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-150">The following table shows the event information:</span></span>

|<span data-ttu-id="613c1-151">event</span><span class="sxs-lookup"><span data-stu-id="613c1-151">Event</span></span>|<span data-ttu-id="613c1-152">イベント ID</span><span class="sxs-lookup"><span data-stu-id="613c1-152">Event ID</span></span>|<span data-ttu-id="613c1-153">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="613c1-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="613c1-154">83</span><span class="sxs-lookup"><span data-stu-id="613c1-154">83</span></span>|<span data-ttu-id="613c1-155">アプリケーション ドメインに 4 MB ずつのメモリ (概算) が割り当てられる。</span><span class="sxs-lookup"><span data-stu-id="613c1-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="613c1-156">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-156">The following table shows the event data:</span></span>

|<span data-ttu-id="613c1-157">フィールド名</span><span class="sxs-lookup"><span data-stu-id="613c1-157">Field name</span></span>|<span data-ttu-id="613c1-158">データの種類</span><span class="sxs-lookup"><span data-stu-id="613c1-158">Data type</span></span>|<span data-ttu-id="613c1-159">説明</span><span class="sxs-lookup"><span data-stu-id="613c1-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="613c1-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="613c1-160">AppDomainID</span></span>|<span data-ttu-id="613c1-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-161">win:UInt64</span></span>|<span data-ttu-id="613c1-162">リソースの使用状況の報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="613c1-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="613c1-163">Allocated</span><span class="sxs-lookup"><span data-stu-id="613c1-163">Allocated</span></span>|<span data-ttu-id="613c1-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-164">win:UInt64</span></span>|<span data-ttu-id="613c1-165">アプリケーション ドメインが作成されてから、このアプリケーション ドメインに割り当てられたバイトの合計数 (解放されたメモリの量は引かれない)。</span><span class="sxs-lookup"><span data-stu-id="613c1-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="613c1-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="613c1-166">ClrInstanceID</span></span>|<span data-ttu-id="613c1-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="613c1-167">win:UInt16</span></span>|<span data-ttu-id="613c1-168">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="613c1-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="613c1-169">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="613c1-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="613c1-170">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="613c1-171">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="613c1-171">Keyword for raising the event</span></span>|<span data-ttu-id="613c1-172">レベル</span><span class="sxs-lookup"><span data-stu-id="613c1-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="613c1-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="613c1-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="613c1-174">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="613c1-174">Informational(4)</span></span>|

<span data-ttu-id="613c1-175">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-175">The following table shows the event information:</span></span>

|<span data-ttu-id="613c1-176">event</span><span class="sxs-lookup"><span data-stu-id="613c1-176">Event</span></span>|<span data-ttu-id="613c1-177">イベント ID</span><span class="sxs-lookup"><span data-stu-id="613c1-177">Event ID</span></span>|<span data-ttu-id="613c1-178">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="613c1-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="613c1-179">84</span><span class="sxs-lookup"><span data-stu-id="613c1-179">84</span></span>|<span data-ttu-id="613c1-180">各ガベージ コレクションが終了した。</span><span class="sxs-lookup"><span data-stu-id="613c1-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="613c1-181">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-181">The following table shows the event data:</span></span>

|<span data-ttu-id="613c1-182">フィールド名</span><span class="sxs-lookup"><span data-stu-id="613c1-182">Field name</span></span>|<span data-ttu-id="613c1-183">データの種類</span><span class="sxs-lookup"><span data-stu-id="613c1-183">Data type</span></span>|<span data-ttu-id="613c1-184">説明</span><span class="sxs-lookup"><span data-stu-id="613c1-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="613c1-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="613c1-185">AppDomainID</span></span>|<span data-ttu-id="613c1-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-186">win:UInt64</span></span>|<span data-ttu-id="613c1-187">リソースの使用状況の報告対象のドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="613c1-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="613c1-188">Survived</span><span class="sxs-lookup"><span data-stu-id="613c1-188">Survived</span></span>|<span data-ttu-id="613c1-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-189">win:UInt64</span></span>|<span data-ttu-id="613c1-190">最後のコレクションの実行後に残され、このアプリケーション ドメインによって保持されることが判明しているバイト数。</span><span class="sxs-lookup"><span data-stu-id="613c1-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="613c1-191">この数は、完全なコレクションの後では正確で完全ですが、短期コレクションの後では完全ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="613c1-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="613c1-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="613c1-192">ProcessSurvived</span></span>|<span data-ttu-id="613c1-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-193">win:UInt64</span></span>|<span data-ttu-id="613c1-194">最後のコレクション後に残った合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="613c1-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="613c1-195">完全なコレクションの後では、この数はマネージド ヒープにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="613c1-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="613c1-196">短期コレクションの後では、この数は短期のジェネレーションにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="613c1-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="613c1-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="613c1-197">ClrInstanceID</span></span>|<span data-ttu-id="613c1-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="613c1-198">win:UInt16</span></span>|<span data-ttu-id="613c1-199">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="613c1-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="613c1-200">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="613c1-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="613c1-201">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="613c1-202">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="613c1-202">Keyword for raising the event</span></span>|<span data-ttu-id="613c1-203">レベル</span><span class="sxs-lookup"><span data-stu-id="613c1-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="613c1-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="613c1-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="613c1-205">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="613c1-205">Informational(4)</span></span>|
|<span data-ttu-id="613c1-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="613c1-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="613c1-207">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="613c1-207">Informational(4)</span></span>|

<span data-ttu-id="613c1-208">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-208">The following table shows the event information:</span></span>

|<span data-ttu-id="613c1-209">event</span><span class="sxs-lookup"><span data-stu-id="613c1-209">Event</span></span>|<span data-ttu-id="613c1-210">イベント ID</span><span class="sxs-lookup"><span data-stu-id="613c1-210">Event ID</span></span>|<span data-ttu-id="613c1-211">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="613c1-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="613c1-212">87</span><span class="sxs-lookup"><span data-stu-id="613c1-212">87</span></span>|<span data-ttu-id="613c1-213">アプリケーション ドメインにスレッドが入力される。</span><span class="sxs-lookup"><span data-stu-id="613c1-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="613c1-214">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-214">The following table shows the event data:</span></span>

|<span data-ttu-id="613c1-215">フィールド名</span><span class="sxs-lookup"><span data-stu-id="613c1-215">Field name</span></span>|<span data-ttu-id="613c1-216">データの種類</span><span class="sxs-lookup"><span data-stu-id="613c1-216">Data type</span></span>|<span data-ttu-id="613c1-217">説明</span><span class="sxs-lookup"><span data-stu-id="613c1-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="613c1-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="613c1-218">ThreadID</span></span>|<span data-ttu-id="613c1-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-219">win:UInt64</span></span>|<span data-ttu-id="613c1-220">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="613c1-220">The thread identifier.</span></span>|
|<span data-ttu-id="613c1-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="613c1-221">AppDomainID</span></span>|<span data-ttu-id="613c1-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-222">win:UInt64</span></span>|<span data-ttu-id="613c1-223">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="613c1-223">The application domain identifier.</span></span>|
|<span data-ttu-id="613c1-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="613c1-224">ClrInstanceID</span></span>|<span data-ttu-id="613c1-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="613c1-225">win:UInt16</span></span>|<span data-ttu-id="613c1-226">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="613c1-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="613c1-227">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="613c1-227">ThreadTerminated Event</span></span>

<span data-ttu-id="613c1-228">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="613c1-229">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="613c1-229">Keyword for raising the event</span></span>|<span data-ttu-id="613c1-230">レベル</span><span class="sxs-lookup"><span data-stu-id="613c1-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="613c1-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="613c1-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="613c1-232">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="613c1-232">Informational(4)</span></span>|
|<span data-ttu-id="613c1-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="613c1-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="613c1-234">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="613c1-234">Informational(4)</span></span>|

<span data-ttu-id="613c1-235">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-235">The following table shows the event information:</span></span>

|<span data-ttu-id="613c1-236">event</span><span class="sxs-lookup"><span data-stu-id="613c1-236">Event</span></span>|<span data-ttu-id="613c1-237">イベント ID</span><span class="sxs-lookup"><span data-stu-id="613c1-237">Event ID</span></span>|<span data-ttu-id="613c1-238">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="613c1-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="613c1-239">86</span><span class="sxs-lookup"><span data-stu-id="613c1-239">86</span></span>|<span data-ttu-id="613c1-240">スレッドが終了する。</span><span class="sxs-lookup"><span data-stu-id="613c1-240">A thread terminates.</span></span>|

<span data-ttu-id="613c1-241">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="613c1-241">The following table shows the event data:</span></span>

|<span data-ttu-id="613c1-242">フィールド名</span><span class="sxs-lookup"><span data-stu-id="613c1-242">Field name</span></span>|<span data-ttu-id="613c1-243">データの種類</span><span class="sxs-lookup"><span data-stu-id="613c1-243">Data type</span></span>|<span data-ttu-id="613c1-244">説明</span><span class="sxs-lookup"><span data-stu-id="613c1-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="613c1-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="613c1-245">ThreadID</span></span>|<span data-ttu-id="613c1-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-246">win:UInt64</span></span>|<span data-ttu-id="613c1-247">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="613c1-247">The thread identifier.</span></span>|
|<span data-ttu-id="613c1-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="613c1-248">AppDomainID</span></span>|<span data-ttu-id="613c1-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="613c1-249">win:UInt64</span></span>|<span data-ttu-id="613c1-250">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="613c1-250">The application domain identifier.</span></span>|
|<span data-ttu-id="613c1-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="613c1-251">ClrInstanceID</span></span>|<span data-ttu-id="613c1-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="613c1-252">win:UInt16</span></span>|<span data-ttu-id="613c1-253">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="613c1-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="613c1-254">関連項目</span><span class="sxs-lookup"><span data-stu-id="613c1-254">See also</span></span>

- [<span data-ttu-id="613c1-255">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="613c1-255">CLR ETW Events</span></span>](clr-etw-events.md)
