---
title: アプリケーション ドメインのリソース監視 (ARM) ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bb2b0dd95877fc6492f6d23a19c14688cd78f7c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788064"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="d5edd-102">アプリケーション ドメインのリソース監視 (ARM) ETW イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="d5edd-103">これらのイベントは、アプリケーション ドメインの状態に関する詳細な診断の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="d5edd-104">これらのイベントを使用することもできますが、アプリケーション ドメインのリソース監視 (ARM) の機能を使用しても同じ情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="d5edd-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="d5edd-105">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d5edd-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="d5edd-106">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="d5edd-107">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="d5edd-108">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="d5edd-109">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="d5edd-110">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="d5edd-111">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="d5edd-112">このイベントは、ランダウン プロバイダーで `ThreadDC` としても発生します  ( `AppDomainResourceManagementRundownKeyword` キーワードで発生)。</span><span class="sxs-lookup"><span data-stu-id="d5edd-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="d5edd-113">これは、このカテゴリでランダウン プロバイダーで発生する唯一のイベントです。</span><span class="sxs-lookup"><span data-stu-id="d5edd-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="d5edd-114">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="d5edd-115">(詳細については、「 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d5edd-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="d5edd-116">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="d5edd-116">Keyword for raising the event</span></span>|<span data-ttu-id="d5edd-117">レベル</span><span class="sxs-lookup"><span data-stu-id="d5edd-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d5edd-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="d5edd-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="d5edd-119">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="d5edd-119">Informational(4)</span></span>|  
|<span data-ttu-id="d5edd-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d5edd-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d5edd-121">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="d5edd-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="d5edd-122">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d5edd-123">イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-123">Event</span></span>|<span data-ttu-id="d5edd-124">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5edd-124">Event ID</span></span>|<span data-ttu-id="d5edd-125">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="d5edd-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="d5edd-126">85</span><span class="sxs-lookup"><span data-stu-id="d5edd-126">85</span></span>|<span data-ttu-id="d5edd-127">アプリケーション ドメインに対してスレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="d5edd-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="d5edd-128">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d5edd-129">フィールド名</span><span class="sxs-lookup"><span data-stu-id="d5edd-129">Field name</span></span>|<span data-ttu-id="d5edd-130">データ型</span><span class="sxs-lookup"><span data-stu-id="d5edd-130">Data type</span></span>|<span data-ttu-id="d5edd-131">説明</span><span class="sxs-lookup"><span data-stu-id="d5edd-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d5edd-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="d5edd-132">ThreadID</span></span>|<span data-ttu-id="d5edd-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-133">win:UInt64</span></span>|<span data-ttu-id="d5edd-134">作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="d5edd-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="d5edd-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="d5edd-135">AppDomainID</span></span>|<span data-ttu-id="d5edd-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-136">win:UInt64</span></span>|<span data-ttu-id="d5edd-137">スレッドのアクティビティの報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="d5edd-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="d5edd-138">フラグ</span><span class="sxs-lookup"><span data-stu-id="d5edd-138">Flags</span></span>|<span data-ttu-id="d5edd-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d5edd-139">win:UInt32</span></span>|<span data-ttu-id="d5edd-140">スレッドの作成フラグ</span><span class="sxs-lookup"><span data-stu-id="d5edd-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="d5edd-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="d5edd-141">ManagedThreadIndex</span></span>|<span data-ttu-id="d5edd-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d5edd-142">win:UInt32</span></span>|<span data-ttu-id="d5edd-143">作成されたスレッドのマネージド インデックス。</span><span class="sxs-lookup"><span data-stu-id="d5edd-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="d5edd-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="d5edd-144">OSThreadID</span></span>|<span data-ttu-id="d5edd-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d5edd-145">win:UInt32</span></span>|<span data-ttu-id="d5edd-146">作成されたスレッドのオペレーティング システム ID。</span><span class="sxs-lookup"><span data-stu-id="d5edd-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="d5edd-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d5edd-147">ClrInstanceID</span></span>|<span data-ttu-id="d5edd-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d5edd-148">win:UInt16</span></span>|<span data-ttu-id="d5edd-149">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="d5edd-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d5edd-150">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="d5edd-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="d5edd-151">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="d5edd-152">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="d5edd-153">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="d5edd-153">Keyword for raising the event</span></span>|<span data-ttu-id="d5edd-154">レベル</span><span class="sxs-lookup"><span data-stu-id="d5edd-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d5edd-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="d5edd-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="d5edd-156">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="d5edd-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="d5edd-157">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d5edd-158">イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-158">Event</span></span>|<span data-ttu-id="d5edd-159">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5edd-159">Event ID</span></span>|<span data-ttu-id="d5edd-160">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="d5edd-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="d5edd-161">83</span><span class="sxs-lookup"><span data-stu-id="d5edd-161">83</span></span>|<span data-ttu-id="d5edd-162">アプリケーション ドメインに 4 MB ずつのメモリ (概算) が割り当てられる。</span><span class="sxs-lookup"><span data-stu-id="d5edd-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="d5edd-163">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d5edd-164">フィールド名</span><span class="sxs-lookup"><span data-stu-id="d5edd-164">Field name</span></span>|<span data-ttu-id="d5edd-165">データ型</span><span class="sxs-lookup"><span data-stu-id="d5edd-165">Data type</span></span>|<span data-ttu-id="d5edd-166">説明</span><span class="sxs-lookup"><span data-stu-id="d5edd-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d5edd-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="d5edd-167">AppDomainID</span></span>|<span data-ttu-id="d5edd-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-168">win:UInt64</span></span>|<span data-ttu-id="d5edd-169">リソースの使用状況の報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="d5edd-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="d5edd-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="d5edd-170">Allocated</span></span>|<span data-ttu-id="d5edd-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-171">win:UInt64</span></span>|<span data-ttu-id="d5edd-172">アプリケーション ドメインが作成されてから、このアプリケーション ドメインに割り当てられたバイトの合計数 (解放されたメモリの量は引かれない)。</span><span class="sxs-lookup"><span data-stu-id="d5edd-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="d5edd-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d5edd-173">ClrInstanceID</span></span>|<span data-ttu-id="d5edd-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d5edd-174">win:UInt16</span></span>|<span data-ttu-id="d5edd-175">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="d5edd-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d5edd-176">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="d5edd-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="d5edd-177">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="d5edd-178">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="d5edd-179">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="d5edd-179">Keyword for raising the event</span></span>|<span data-ttu-id="d5edd-180">レベル</span><span class="sxs-lookup"><span data-stu-id="d5edd-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d5edd-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="d5edd-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="d5edd-182">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="d5edd-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="d5edd-183">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d5edd-184">イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-184">Event</span></span>|<span data-ttu-id="d5edd-185">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5edd-185">Event ID</span></span>|<span data-ttu-id="d5edd-186">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="d5edd-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="d5edd-187">84</span><span class="sxs-lookup"><span data-stu-id="d5edd-187">84</span></span>|<span data-ttu-id="d5edd-188">各ガベージ コレクションが終了した。</span><span class="sxs-lookup"><span data-stu-id="d5edd-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="d5edd-189">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d5edd-190">フィールド名</span><span class="sxs-lookup"><span data-stu-id="d5edd-190">Field name</span></span>|<span data-ttu-id="d5edd-191">データ型</span><span class="sxs-lookup"><span data-stu-id="d5edd-191">Data type</span></span>|<span data-ttu-id="d5edd-192">説明</span><span class="sxs-lookup"><span data-stu-id="d5edd-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d5edd-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="d5edd-193">AppDomainID</span></span>|<span data-ttu-id="d5edd-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-194">win:UInt64</span></span>|<span data-ttu-id="d5edd-195">リソースの使用状況の報告対象のドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="d5edd-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="d5edd-196">Survived</span><span class="sxs-lookup"><span data-stu-id="d5edd-196">Survived</span></span>|<span data-ttu-id="d5edd-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-197">win:UInt64</span></span>|<span data-ttu-id="d5edd-198">最後のコレクションの実行後に残され、このアプリケーション ドメインによって保持されることが判明しているバイト数。</span><span class="sxs-lookup"><span data-stu-id="d5edd-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="d5edd-199">この数は、完全なコレクションの後では正確で完全ですが、短期コレクションの後では完全ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5edd-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="d5edd-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="d5edd-200">ProcessSurvived</span></span>|<span data-ttu-id="d5edd-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-201">win:UInt64</span></span>|<span data-ttu-id="d5edd-202">最後のコレクション後に残った合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="d5edd-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="d5edd-203">完全なコレクションの後では、この数はマネージド ヒープにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="d5edd-204">短期コレクションの後では、この数は短期のジェネレーションにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="d5edd-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d5edd-205">ClrInstanceID</span></span>|<span data-ttu-id="d5edd-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d5edd-206">win:UInt16</span></span>|<span data-ttu-id="d5edd-207">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="d5edd-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d5edd-208">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="d5edd-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="d5edd-209">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="d5edd-210">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="d5edd-211">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="d5edd-211">Keyword for raising the event</span></span>|<span data-ttu-id="d5edd-212">レベル</span><span class="sxs-lookup"><span data-stu-id="d5edd-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d5edd-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="d5edd-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="d5edd-214">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="d5edd-214">Informational(4)</span></span>|  
|<span data-ttu-id="d5edd-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d5edd-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d5edd-216">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="d5edd-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="d5edd-217">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d5edd-218">イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-218">Event</span></span>|<span data-ttu-id="d5edd-219">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5edd-219">Event ID</span></span>|<span data-ttu-id="d5edd-220">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="d5edd-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="d5edd-221">87</span><span class="sxs-lookup"><span data-stu-id="d5edd-221">87</span></span>|<span data-ttu-id="d5edd-222">アプリケーション ドメインにスレッドが入力される。</span><span class="sxs-lookup"><span data-stu-id="d5edd-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="d5edd-223">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d5edd-224">フィールド名</span><span class="sxs-lookup"><span data-stu-id="d5edd-224">Field name</span></span>|<span data-ttu-id="d5edd-225">データ型</span><span class="sxs-lookup"><span data-stu-id="d5edd-225">Data type</span></span>|<span data-ttu-id="d5edd-226">説明</span><span class="sxs-lookup"><span data-stu-id="d5edd-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d5edd-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="d5edd-227">ThreadID</span></span>|<span data-ttu-id="d5edd-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-228">win:UInt64</span></span>|<span data-ttu-id="d5edd-229">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="d5edd-229">The thread identifier.</span></span>|  
|<span data-ttu-id="d5edd-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="d5edd-230">AppDomainID</span></span>|<span data-ttu-id="d5edd-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-231">win:UInt64</span></span>|<span data-ttu-id="d5edd-232">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="d5edd-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="d5edd-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d5edd-233">ClrInstanceID</span></span>|<span data-ttu-id="d5edd-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d5edd-234">win:UInt16</span></span>|<span data-ttu-id="d5edd-235">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="d5edd-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d5edd-236">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="d5edd-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="d5edd-237">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="d5edd-238">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="d5edd-239">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="d5edd-239">Keyword for raising the event</span></span>|<span data-ttu-id="d5edd-240">レベル</span><span class="sxs-lookup"><span data-stu-id="d5edd-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d5edd-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="d5edd-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="d5edd-242">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="d5edd-242">Informational(4)</span></span>|  
|<span data-ttu-id="d5edd-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d5edd-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d5edd-244">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="d5edd-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="d5edd-245">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d5edd-246">イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-246">Event</span></span>|<span data-ttu-id="d5edd-247">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5edd-247">Event ID</span></span>|<span data-ttu-id="d5edd-248">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="d5edd-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="d5edd-249">86</span><span class="sxs-lookup"><span data-stu-id="d5edd-249">86</span></span>|<span data-ttu-id="d5edd-250">スレッドが終了する。</span><span class="sxs-lookup"><span data-stu-id="d5edd-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="d5edd-251">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="d5edd-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="d5edd-252">フィールド名</span><span class="sxs-lookup"><span data-stu-id="d5edd-252">Field name</span></span>|<span data-ttu-id="d5edd-253">データ型</span><span class="sxs-lookup"><span data-stu-id="d5edd-253">Data type</span></span>|<span data-ttu-id="d5edd-254">説明</span><span class="sxs-lookup"><span data-stu-id="d5edd-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d5edd-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="d5edd-255">ThreadID</span></span>|<span data-ttu-id="d5edd-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-256">win:UInt64</span></span>|<span data-ttu-id="d5edd-257">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="d5edd-257">The thread identifier.</span></span>|  
|<span data-ttu-id="d5edd-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="d5edd-258">AppDomainID</span></span>|<span data-ttu-id="d5edd-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d5edd-259">win:UInt64</span></span>|<span data-ttu-id="d5edd-260">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="d5edd-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="d5edd-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d5edd-261">ClrInstanceID</span></span>|<span data-ttu-id="d5edd-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d5edd-262">win:UInt16</span></span>|<span data-ttu-id="d5edd-263">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="d5edd-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5edd-264">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5edd-264">See also</span></span>

- [<span data-ttu-id="d5edd-265">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="d5edd-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
