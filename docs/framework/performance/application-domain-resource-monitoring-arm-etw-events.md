---
title: アプリケーション ドメインのリソース監視 (ARM) ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e4002ae248022a9e4380c79174109494b5e4ca
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046769"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="31bbf-102">アプリケーション ドメインのリソース監視 (ARM) ETW イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="31bbf-103">これらのイベントは、アプリケーション ドメインの状態に関する詳細な診断の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="31bbf-104">これらのイベントを使用することもできますが、アプリケーション ドメインのリソース監視 (ARM) の機能を使用しても同じ情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="31bbf-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="31bbf-105">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="31bbf-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="31bbf-106">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="31bbf-107">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="31bbf-108">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="31bbf-109">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="31bbf-110">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="31bbf-111">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="31bbf-112">このイベントは、ランダウン プロバイダーで `ThreadDC` としても発生します  ( `AppDomainResourceManagementRundownKeyword` キーワードで発生)。</span><span class="sxs-lookup"><span data-stu-id="31bbf-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="31bbf-113">これは、このカテゴリでランダウン プロバイダーで発生する唯一のイベントです。</span><span class="sxs-lookup"><span data-stu-id="31bbf-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="31bbf-114">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="31bbf-115">(詳細については、「 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="31bbf-115">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="31bbf-116">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="31bbf-116">Keyword for raising the event</span></span>|<span data-ttu-id="31bbf-117">レベル</span><span class="sxs-lookup"><span data-stu-id="31bbf-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="31bbf-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="31bbf-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="31bbf-119">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="31bbf-119">Informational(4)</span></span>|  
|<span data-ttu-id="31bbf-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="31bbf-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="31bbf-121">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="31bbf-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="31bbf-122">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="31bbf-123">イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-123">Event</span></span>|<span data-ttu-id="31bbf-124">イベント ID</span><span class="sxs-lookup"><span data-stu-id="31bbf-124">Event ID</span></span>|<span data-ttu-id="31bbf-125">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="31bbf-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="31bbf-126">85</span><span class="sxs-lookup"><span data-stu-id="31bbf-126">85</span></span>|<span data-ttu-id="31bbf-127">アプリケーション ドメインに対してスレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="31bbf-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="31bbf-128">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="31bbf-129">フィールド名</span><span class="sxs-lookup"><span data-stu-id="31bbf-129">Field name</span></span>|<span data-ttu-id="31bbf-130">データ型</span><span class="sxs-lookup"><span data-stu-id="31bbf-130">Data type</span></span>|<span data-ttu-id="31bbf-131">説明</span><span class="sxs-lookup"><span data-stu-id="31bbf-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="31bbf-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="31bbf-132">ThreadID</span></span>|<span data-ttu-id="31bbf-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-133">win:UInt64</span></span>|<span data-ttu-id="31bbf-134">作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="31bbf-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="31bbf-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="31bbf-135">AppDomainID</span></span>|<span data-ttu-id="31bbf-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-136">win:UInt64</span></span>|<span data-ttu-id="31bbf-137">スレッドのアクティビティの報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="31bbf-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="31bbf-138">フラグ</span><span class="sxs-lookup"><span data-stu-id="31bbf-138">Flags</span></span>|<span data-ttu-id="31bbf-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="31bbf-139">win:UInt32</span></span>|<span data-ttu-id="31bbf-140">スレッドの作成フラグ</span><span class="sxs-lookup"><span data-stu-id="31bbf-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="31bbf-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="31bbf-141">ManagedThreadIndex</span></span>|<span data-ttu-id="31bbf-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="31bbf-142">win:UInt32</span></span>|<span data-ttu-id="31bbf-143">作成されたスレッドのマネージド インデックス。</span><span class="sxs-lookup"><span data-stu-id="31bbf-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="31bbf-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="31bbf-144">OSThreadID</span></span>|<span data-ttu-id="31bbf-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="31bbf-145">win:UInt32</span></span>|<span data-ttu-id="31bbf-146">作成されたスレッドのオペレーティング システム ID。</span><span class="sxs-lookup"><span data-stu-id="31bbf-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="31bbf-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="31bbf-147">ClrInstanceID</span></span>|<span data-ttu-id="31bbf-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="31bbf-148">win:UInt16</span></span>|<span data-ttu-id="31bbf-149">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="31bbf-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="31bbf-150">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="31bbf-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="31bbf-151">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="31bbf-152">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="31bbf-153">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="31bbf-153">Keyword for raising the event</span></span>|<span data-ttu-id="31bbf-154">レベル</span><span class="sxs-lookup"><span data-stu-id="31bbf-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="31bbf-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="31bbf-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="31bbf-156">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="31bbf-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="31bbf-157">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="31bbf-158">イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-158">Event</span></span>|<span data-ttu-id="31bbf-159">イベント ID</span><span class="sxs-lookup"><span data-stu-id="31bbf-159">Event ID</span></span>|<span data-ttu-id="31bbf-160">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="31bbf-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="31bbf-161">83</span><span class="sxs-lookup"><span data-stu-id="31bbf-161">83</span></span>|<span data-ttu-id="31bbf-162">アプリケーション ドメインに 4 MB ずつのメモリ (概算) が割り当てられる。</span><span class="sxs-lookup"><span data-stu-id="31bbf-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="31bbf-163">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="31bbf-164">フィールド名</span><span class="sxs-lookup"><span data-stu-id="31bbf-164">Field name</span></span>|<span data-ttu-id="31bbf-165">データ型</span><span class="sxs-lookup"><span data-stu-id="31bbf-165">Data type</span></span>|<span data-ttu-id="31bbf-166">説明</span><span class="sxs-lookup"><span data-stu-id="31bbf-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="31bbf-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="31bbf-167">AppDomainID</span></span>|<span data-ttu-id="31bbf-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-168">win:UInt64</span></span>|<span data-ttu-id="31bbf-169">リソースの使用状況の報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="31bbf-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="31bbf-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="31bbf-170">Allocated</span></span>|<span data-ttu-id="31bbf-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-171">win:UInt64</span></span>|<span data-ttu-id="31bbf-172">アプリケーション ドメインが作成されてから、このアプリケーション ドメインに割り当てられたバイトの合計数 (解放されたメモリの量は引かれない)。</span><span class="sxs-lookup"><span data-stu-id="31bbf-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="31bbf-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="31bbf-173">ClrInstanceID</span></span>|<span data-ttu-id="31bbf-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="31bbf-174">win:UInt16</span></span>|<span data-ttu-id="31bbf-175">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="31bbf-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="31bbf-176">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="31bbf-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="31bbf-177">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="31bbf-178">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="31bbf-179">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="31bbf-179">Keyword for raising the event</span></span>|<span data-ttu-id="31bbf-180">レベル</span><span class="sxs-lookup"><span data-stu-id="31bbf-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="31bbf-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="31bbf-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="31bbf-182">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="31bbf-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="31bbf-183">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="31bbf-184">イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-184">Event</span></span>|<span data-ttu-id="31bbf-185">イベント ID</span><span class="sxs-lookup"><span data-stu-id="31bbf-185">Event ID</span></span>|<span data-ttu-id="31bbf-186">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="31bbf-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="31bbf-187">84</span><span class="sxs-lookup"><span data-stu-id="31bbf-187">84</span></span>|<span data-ttu-id="31bbf-188">各ガベージ コレクションが終了した。</span><span class="sxs-lookup"><span data-stu-id="31bbf-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="31bbf-189">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="31bbf-190">フィールド名</span><span class="sxs-lookup"><span data-stu-id="31bbf-190">Field name</span></span>|<span data-ttu-id="31bbf-191">データ型</span><span class="sxs-lookup"><span data-stu-id="31bbf-191">Data type</span></span>|<span data-ttu-id="31bbf-192">説明</span><span class="sxs-lookup"><span data-stu-id="31bbf-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="31bbf-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="31bbf-193">AppDomainID</span></span>|<span data-ttu-id="31bbf-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-194">win:UInt64</span></span>|<span data-ttu-id="31bbf-195">リソースの使用状況の報告対象のドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="31bbf-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="31bbf-196">Survived</span><span class="sxs-lookup"><span data-stu-id="31bbf-196">Survived</span></span>|<span data-ttu-id="31bbf-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-197">win:UInt64</span></span>|<span data-ttu-id="31bbf-198">最後のコレクションの実行後に残され、このアプリケーション ドメインによって保持されることが判明しているバイト数。</span><span class="sxs-lookup"><span data-stu-id="31bbf-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="31bbf-199">この数は、完全なコレクションの後では正確で完全ですが、短期コレクションの後では完全ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31bbf-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="31bbf-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="31bbf-200">ProcessSurvived</span></span>|<span data-ttu-id="31bbf-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-201">win:UInt64</span></span>|<span data-ttu-id="31bbf-202">最後のコレクション後に残った合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="31bbf-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="31bbf-203">完全なコレクションの後では、この数はマネージド ヒープにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="31bbf-204">短期コレクションの後では、この数は短期のジェネレーションにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="31bbf-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="31bbf-205">ClrInstanceID</span></span>|<span data-ttu-id="31bbf-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="31bbf-206">win:UInt16</span></span>|<span data-ttu-id="31bbf-207">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="31bbf-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="31bbf-208">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="31bbf-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="31bbf-209">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="31bbf-210">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="31bbf-211">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="31bbf-211">Keyword for raising the event</span></span>|<span data-ttu-id="31bbf-212">レベル</span><span class="sxs-lookup"><span data-stu-id="31bbf-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="31bbf-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="31bbf-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="31bbf-214">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="31bbf-214">Informational(4)</span></span>|  
|<span data-ttu-id="31bbf-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="31bbf-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="31bbf-216">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="31bbf-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="31bbf-217">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="31bbf-218">イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-218">Event</span></span>|<span data-ttu-id="31bbf-219">イベント ID</span><span class="sxs-lookup"><span data-stu-id="31bbf-219">Event ID</span></span>|<span data-ttu-id="31bbf-220">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="31bbf-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="31bbf-221">87</span><span class="sxs-lookup"><span data-stu-id="31bbf-221">87</span></span>|<span data-ttu-id="31bbf-222">アプリケーション ドメインにスレッドが入力される。</span><span class="sxs-lookup"><span data-stu-id="31bbf-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="31bbf-223">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="31bbf-224">フィールド名</span><span class="sxs-lookup"><span data-stu-id="31bbf-224">Field name</span></span>|<span data-ttu-id="31bbf-225">データ型</span><span class="sxs-lookup"><span data-stu-id="31bbf-225">Data type</span></span>|<span data-ttu-id="31bbf-226">説明</span><span class="sxs-lookup"><span data-stu-id="31bbf-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="31bbf-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="31bbf-227">ThreadID</span></span>|<span data-ttu-id="31bbf-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-228">win:UInt64</span></span>|<span data-ttu-id="31bbf-229">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="31bbf-229">The thread identifier.</span></span>|  
|<span data-ttu-id="31bbf-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="31bbf-230">AppDomainID</span></span>|<span data-ttu-id="31bbf-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-231">win:UInt64</span></span>|<span data-ttu-id="31bbf-232">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="31bbf-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="31bbf-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="31bbf-233">ClrInstanceID</span></span>|<span data-ttu-id="31bbf-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="31bbf-234">win:UInt16</span></span>|<span data-ttu-id="31bbf-235">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="31bbf-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="31bbf-236">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="31bbf-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="31bbf-237">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="31bbf-238">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="31bbf-239">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="31bbf-239">Keyword for raising the event</span></span>|<span data-ttu-id="31bbf-240">レベル</span><span class="sxs-lookup"><span data-stu-id="31bbf-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="31bbf-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="31bbf-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="31bbf-242">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="31bbf-242">Informational(4)</span></span>|  
|<span data-ttu-id="31bbf-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="31bbf-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="31bbf-244">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="31bbf-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="31bbf-245">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="31bbf-246">イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-246">Event</span></span>|<span data-ttu-id="31bbf-247">イベント ID</span><span class="sxs-lookup"><span data-stu-id="31bbf-247">Event ID</span></span>|<span data-ttu-id="31bbf-248">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="31bbf-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="31bbf-249">86</span><span class="sxs-lookup"><span data-stu-id="31bbf-249">86</span></span>|<span data-ttu-id="31bbf-250">スレッドが終了する。</span><span class="sxs-lookup"><span data-stu-id="31bbf-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="31bbf-251">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="31bbf-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="31bbf-252">フィールド名</span><span class="sxs-lookup"><span data-stu-id="31bbf-252">Field name</span></span>|<span data-ttu-id="31bbf-253">データ型</span><span class="sxs-lookup"><span data-stu-id="31bbf-253">Data type</span></span>|<span data-ttu-id="31bbf-254">説明</span><span class="sxs-lookup"><span data-stu-id="31bbf-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="31bbf-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="31bbf-255">ThreadID</span></span>|<span data-ttu-id="31bbf-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-256">win:UInt64</span></span>|<span data-ttu-id="31bbf-257">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="31bbf-257">The thread identifier.</span></span>|  
|<span data-ttu-id="31bbf-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="31bbf-258">AppDomainID</span></span>|<span data-ttu-id="31bbf-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="31bbf-259">win:UInt64</span></span>|<span data-ttu-id="31bbf-260">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="31bbf-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="31bbf-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="31bbf-261">ClrInstanceID</span></span>|<span data-ttu-id="31bbf-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="31bbf-262">win:UInt16</span></span>|<span data-ttu-id="31bbf-263">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="31bbf-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31bbf-264">関連項目</span><span class="sxs-lookup"><span data-stu-id="31bbf-264">See also</span></span>

- [<span data-ttu-id="31bbf-265">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="31bbf-265">CLR ETW Events</span></span>](clr-etw-events.md)
