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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133823"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="e6dd7-102">アプリケーション ドメインのリソース監視 (ARM) ETW イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="e6dd7-103">これらのイベントは、アプリケーション ドメインの状態に関する詳細な診断の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="e6dd7-104">これらのイベントを使用することもできますが、アプリケーション ドメインのリソース監視 (ARM) の機能を使用しても同じ情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="e6dd7-105">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="e6dd7-106">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="e6dd7-107">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="e6dd7-108">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="e6dd7-109">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="e6dd7-110">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="e6dd7-111">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="e6dd7-112">このイベントは、ランダウン プロバイダーで `ThreadDC` としても発生します  ( `AppDomainResourceManagementRundownKeyword` キーワードで発生)。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="e6dd7-113">これは、このカテゴリでランダウン プロバイダーで発生する唯一のイベントです。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="e6dd7-114">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="e6dd7-115">(詳細については、「 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="e6dd7-116">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e6dd7-116">Keyword for raising the event</span></span>|<span data-ttu-id="e6dd7-117">レベル</span><span class="sxs-lookup"><span data-stu-id="e6dd7-117">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="e6dd7-118">(0x800)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-118">(0x800)</span></span>|<span data-ttu-id="e6dd7-119">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-119">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="e6dd7-120">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-120">(0x10000)</span></span>|<span data-ttu-id="e6dd7-121">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="e6dd7-122">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6dd7-123">イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-123">Event</span></span>|<span data-ttu-id="e6dd7-124">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-124">Event ID</span></span>|<span data-ttu-id="e6dd7-125">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e6dd7-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="e6dd7-126">85</span><span class="sxs-lookup"><span data-stu-id="e6dd7-126">85</span></span>|<span data-ttu-id="e6dd7-127">アプリケーション ドメインに対してスレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="e6dd7-128">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6dd7-129">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e6dd7-129">Field name</span></span>|<span data-ttu-id="e6dd7-130">データ型</span><span class="sxs-lookup"><span data-stu-id="e6dd7-130">Data type</span></span>|<span data-ttu-id="e6dd7-131">説明</span><span class="sxs-lookup"><span data-stu-id="e6dd7-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6dd7-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-132">ThreadID</span></span>|<span data-ttu-id="e6dd7-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-133">win:UInt64</span></span>|<span data-ttu-id="e6dd7-134">作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="e6dd7-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-135">AppDomainID</span></span>|<span data-ttu-id="e6dd7-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-136">win:UInt64</span></span>|<span data-ttu-id="e6dd7-137">スレッドのアクティビティの報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="e6dd7-138">フラグ</span><span class="sxs-lookup"><span data-stu-id="e6dd7-138">Flags</span></span>|<span data-ttu-id="e6dd7-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6dd7-139">win:UInt32</span></span>|<span data-ttu-id="e6dd7-140">スレッドの作成フラグ</span><span class="sxs-lookup"><span data-stu-id="e6dd7-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="e6dd7-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="e6dd7-141">ManagedThreadIndex</span></span>|<span data-ttu-id="e6dd7-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6dd7-142">win:UInt32</span></span>|<span data-ttu-id="e6dd7-143">作成されたスレッドのマネージド インデックス。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="e6dd7-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-144">OSThreadID</span></span>|<span data-ttu-id="e6dd7-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="e6dd7-145">win:UInt32</span></span>|<span data-ttu-id="e6dd7-146">作成されたスレッドのオペレーティング システム ID。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="e6dd7-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-147">ClrInstanceID</span></span>|<span data-ttu-id="e6dd7-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6dd7-148">win:UInt16</span></span>|<span data-ttu-id="e6dd7-149">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6dd7-150">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="e6dd7-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="e6dd7-151">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="e6dd7-152">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6dd7-153">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e6dd7-153">Keyword for raising the event</span></span>|<span data-ttu-id="e6dd7-154">レベル</span><span class="sxs-lookup"><span data-stu-id="e6dd7-154">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="e6dd7-155">(0x800)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-155">(0x800)</span></span>|<span data-ttu-id="e6dd7-156">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="e6dd7-157">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6dd7-158">イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-158">Event</span></span>|<span data-ttu-id="e6dd7-159">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-159">Event ID</span></span>|<span data-ttu-id="e6dd7-160">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e6dd7-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="e6dd7-161">83</span><span class="sxs-lookup"><span data-stu-id="e6dd7-161">83</span></span>|<span data-ttu-id="e6dd7-162">アプリケーション ドメインに 4 MB ずつのメモリ (概算) が割り当てられる。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="e6dd7-163">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6dd7-164">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e6dd7-164">Field name</span></span>|<span data-ttu-id="e6dd7-165">データ型</span><span class="sxs-lookup"><span data-stu-id="e6dd7-165">Data type</span></span>|<span data-ttu-id="e6dd7-166">説明</span><span class="sxs-lookup"><span data-stu-id="e6dd7-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6dd7-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-167">AppDomainID</span></span>|<span data-ttu-id="e6dd7-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-168">win:UInt64</span></span>|<span data-ttu-id="e6dd7-169">リソースの使用状況の報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="e6dd7-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="e6dd7-170">Allocated</span></span>|<span data-ttu-id="e6dd7-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-171">win:UInt64</span></span>|<span data-ttu-id="e6dd7-172">アプリケーション ドメインが作成されてから、このアプリケーション ドメインに割り当てられたバイトの合計数 (解放されたメモリの量は引かれない)。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="e6dd7-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-173">ClrInstanceID</span></span>|<span data-ttu-id="e6dd7-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6dd7-174">win:UInt16</span></span>|<span data-ttu-id="e6dd7-175">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6dd7-176">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="e6dd7-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="e6dd7-177">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="e6dd7-178">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6dd7-179">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e6dd7-179">Keyword for raising the event</span></span>|<span data-ttu-id="e6dd7-180">レベル</span><span class="sxs-lookup"><span data-stu-id="e6dd7-180">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="e6dd7-181">(0x800)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-181">(0x800)</span></span>|<span data-ttu-id="e6dd7-182">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="e6dd7-183">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6dd7-184">イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-184">Event</span></span>|<span data-ttu-id="e6dd7-185">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-185">Event ID</span></span>|<span data-ttu-id="e6dd7-186">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e6dd7-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="e6dd7-187">84</span><span class="sxs-lookup"><span data-stu-id="e6dd7-187">84</span></span>|<span data-ttu-id="e6dd7-188">各ガベージ コレクションが終了した。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="e6dd7-189">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6dd7-190">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e6dd7-190">Field name</span></span>|<span data-ttu-id="e6dd7-191">データ型</span><span class="sxs-lookup"><span data-stu-id="e6dd7-191">Data type</span></span>|<span data-ttu-id="e6dd7-192">説明</span><span class="sxs-lookup"><span data-stu-id="e6dd7-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6dd7-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-193">AppDomainID</span></span>|<span data-ttu-id="e6dd7-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-194">win:UInt64</span></span>|<span data-ttu-id="e6dd7-195">リソースの使用状況の報告対象のドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="e6dd7-196">Survived</span><span class="sxs-lookup"><span data-stu-id="e6dd7-196">Survived</span></span>|<span data-ttu-id="e6dd7-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-197">win:UInt64</span></span>|<span data-ttu-id="e6dd7-198">最後のコレクションの実行後に残され、このアプリケーション ドメインによって保持されることが判明しているバイト数。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="e6dd7-199">この数は、完全なコレクションの後では正確で完全ですが、短期コレクションの後では完全ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="e6dd7-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="e6dd7-200">ProcessSurvived</span></span>|<span data-ttu-id="e6dd7-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-201">win:UInt64</span></span>|<span data-ttu-id="e6dd7-202">最後のコレクション後に残った合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="e6dd7-203">完全なコレクションの後では、この数はマネージド ヒープにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="e6dd7-204">短期コレクションの後では、この数は短期のジェネレーションにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="e6dd7-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-205">ClrInstanceID</span></span>|<span data-ttu-id="e6dd7-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6dd7-206">win:UInt16</span></span>|<span data-ttu-id="e6dd7-207">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6dd7-208">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="e6dd7-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="e6dd7-209">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="e6dd7-210">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6dd7-211">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e6dd7-211">Keyword for raising the event</span></span>|<span data-ttu-id="e6dd7-212">レベル</span><span class="sxs-lookup"><span data-stu-id="e6dd7-212">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="e6dd7-213">(0x800)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-213">(0x800)</span></span>|<span data-ttu-id="e6dd7-214">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-214">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="e6dd7-215">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-215">(0x10000)</span></span>|<span data-ttu-id="e6dd7-216">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="e6dd7-217">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6dd7-218">イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-218">Event</span></span>|<span data-ttu-id="e6dd7-219">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-219">Event ID</span></span>|<span data-ttu-id="e6dd7-220">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e6dd7-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="e6dd7-221">87</span><span class="sxs-lookup"><span data-stu-id="e6dd7-221">87</span></span>|<span data-ttu-id="e6dd7-222">アプリケーション ドメインにスレッドが入力される。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="e6dd7-223">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="e6dd7-224">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e6dd7-224">Field name</span></span>|<span data-ttu-id="e6dd7-225">データ型</span><span class="sxs-lookup"><span data-stu-id="e6dd7-225">Data type</span></span>|<span data-ttu-id="e6dd7-226">説明</span><span class="sxs-lookup"><span data-stu-id="e6dd7-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6dd7-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-227">ThreadID</span></span>|<span data-ttu-id="e6dd7-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-228">win:UInt64</span></span>|<span data-ttu-id="e6dd7-229">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="e6dd7-229">The thread identifier.</span></span>|  
|<span data-ttu-id="e6dd7-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-230">AppDomainID</span></span>|<span data-ttu-id="e6dd7-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-231">win:UInt64</span></span>|<span data-ttu-id="e6dd7-232">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="e6dd7-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-233">ClrInstanceID</span></span>|<span data-ttu-id="e6dd7-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6dd7-234">win:UInt16</span></span>|<span data-ttu-id="e6dd7-235">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="e6dd7-236">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="e6dd7-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="e6dd7-237">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="e6dd7-238">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="e6dd7-239">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="e6dd7-239">Keyword for raising the event</span></span>|<span data-ttu-id="e6dd7-240">レベル</span><span class="sxs-lookup"><span data-stu-id="e6dd7-240">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="e6dd7-241">(0x800)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-241">(0x800)</span></span>|<span data-ttu-id="e6dd7-242">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-242">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="e6dd7-243">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-243">(0x10000)</span></span>|<span data-ttu-id="e6dd7-244">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="e6dd7-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="e6dd7-245">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="e6dd7-246">イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-246">Event</span></span>|<span data-ttu-id="e6dd7-247">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-247">Event ID</span></span>|<span data-ttu-id="e6dd7-248">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="e6dd7-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="e6dd7-249">86</span><span class="sxs-lookup"><span data-stu-id="e6dd7-249">86</span></span>|<span data-ttu-id="e6dd7-250">スレッドが終了する。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="e6dd7-251">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="e6dd7-252">フィールド名</span><span class="sxs-lookup"><span data-stu-id="e6dd7-252">Field name</span></span>|<span data-ttu-id="e6dd7-253">データ型</span><span class="sxs-lookup"><span data-stu-id="e6dd7-253">Data type</span></span>|<span data-ttu-id="e6dd7-254">説明</span><span class="sxs-lookup"><span data-stu-id="e6dd7-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="e6dd7-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-255">ThreadID</span></span>|<span data-ttu-id="e6dd7-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-256">win:UInt64</span></span>|<span data-ttu-id="e6dd7-257">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="e6dd7-257">The thread identifier.</span></span>|  
|<span data-ttu-id="e6dd7-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-258">AppDomainID</span></span>|<span data-ttu-id="e6dd7-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="e6dd7-259">win:UInt64</span></span>|<span data-ttu-id="e6dd7-260">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="e6dd7-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="e6dd7-261">ClrInstanceID</span></span>|<span data-ttu-id="e6dd7-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="e6dd7-262">win:UInt16</span></span>|<span data-ttu-id="e6dd7-263">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e6dd7-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6dd7-264">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6dd7-264">See also</span></span>

- [<span data-ttu-id="e6dd7-265">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="e6dd7-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
