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
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="078de-102">アプリケーション ドメインのリソース監視 (ARM) ETW イベント</span><span class="sxs-lookup"><span data-stu-id="078de-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="078de-103">これらのイベントは、アプリケーション ドメインの状態に関する詳細な診断の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="078de-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="078de-104">これらのイベントを使用することもできますが、アプリケーション ドメインのリソース監視 (ARM) の機能を使用しても同じ情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="078de-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="078de-105">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="078de-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="078de-106">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="078de-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="078de-107">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="078de-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="078de-108">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="078de-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="078de-109">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="078de-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="078de-110">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="078de-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="078de-111">ThreadCreated イベント</span><span class="sxs-lookup"><span data-stu-id="078de-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="078de-112">このイベントは、ランダウン プロバイダーで `ThreadDC` としても発生します  ( `AppDomainResourceManagementRundownKeyword` キーワードで発生)。</span><span class="sxs-lookup"><span data-stu-id="078de-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="078de-113">これは、このカテゴリでランダウン プロバイダーで発生する唯一のイベントです。</span><span class="sxs-lookup"><span data-stu-id="078de-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="078de-114">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="078de-115">(詳細については、「 [CLR ETW キーワードおよびレベル](clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="078de-115">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="078de-116">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="078de-116">Keyword for raising the event</span></span>|<span data-ttu-id="078de-117">レベル</span><span class="sxs-lookup"><span data-stu-id="078de-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="078de-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="078de-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="078de-119">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="078de-119">Informational(4)</span></span>|  
|<span data-ttu-id="078de-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="078de-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="078de-121">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="078de-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="078de-122">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="078de-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="078de-123">イベント</span><span class="sxs-lookup"><span data-stu-id="078de-123">Event</span></span>|<span data-ttu-id="078de-124">イベント ID</span><span class="sxs-lookup"><span data-stu-id="078de-124">Event ID</span></span>|<span data-ttu-id="078de-125">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="078de-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="078de-126">85</span><span class="sxs-lookup"><span data-stu-id="078de-126">85</span></span>|<span data-ttu-id="078de-127">アプリケーション ドメインに対してスレッドが作成された。</span><span class="sxs-lookup"><span data-stu-id="078de-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="078de-128">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="078de-129">フィールド名</span><span class="sxs-lookup"><span data-stu-id="078de-129">Field name</span></span>|<span data-ttu-id="078de-130">データ型</span><span class="sxs-lookup"><span data-stu-id="078de-130">Data type</span></span>|<span data-ttu-id="078de-131">説明</span><span class="sxs-lookup"><span data-stu-id="078de-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="078de-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="078de-132">ThreadID</span></span>|<span data-ttu-id="078de-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-133">win:UInt64</span></span>|<span data-ttu-id="078de-134">作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="078de-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="078de-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="078de-135">AppDomainID</span></span>|<span data-ttu-id="078de-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-136">win:UInt64</span></span>|<span data-ttu-id="078de-137">スレッドのアクティビティの報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="078de-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="078de-138">フラグ</span><span class="sxs-lookup"><span data-stu-id="078de-138">Flags</span></span>|<span data-ttu-id="078de-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="078de-139">win:UInt32</span></span>|<span data-ttu-id="078de-140">スレッドの作成フラグ</span><span class="sxs-lookup"><span data-stu-id="078de-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="078de-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="078de-141">ManagedThreadIndex</span></span>|<span data-ttu-id="078de-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="078de-142">win:UInt32</span></span>|<span data-ttu-id="078de-143">作成されたスレッドのマネージド インデックス。</span><span class="sxs-lookup"><span data-stu-id="078de-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="078de-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="078de-144">OSThreadID</span></span>|<span data-ttu-id="078de-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="078de-145">win:UInt32</span></span>|<span data-ttu-id="078de-146">作成されたスレッドのオペレーティング システム ID。</span><span class="sxs-lookup"><span data-stu-id="078de-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="078de-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="078de-147">ClrInstanceID</span></span>|<span data-ttu-id="078de-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="078de-148">win:UInt16</span></span>|<span data-ttu-id="078de-149">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="078de-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="078de-150">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="078de-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="078de-151">AppDomainMemAllocated イベント</span><span class="sxs-lookup"><span data-stu-id="078de-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="078de-152">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="078de-153">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="078de-153">Keyword for raising the event</span></span>|<span data-ttu-id="078de-154">レベル</span><span class="sxs-lookup"><span data-stu-id="078de-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="078de-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="078de-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="078de-156">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="078de-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="078de-157">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="078de-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="078de-158">イベント</span><span class="sxs-lookup"><span data-stu-id="078de-158">Event</span></span>|<span data-ttu-id="078de-159">イベント ID</span><span class="sxs-lookup"><span data-stu-id="078de-159">Event ID</span></span>|<span data-ttu-id="078de-160">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="078de-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="078de-161">83</span><span class="sxs-lookup"><span data-stu-id="078de-161">83</span></span>|<span data-ttu-id="078de-162">アプリケーション ドメインに 4 MB ずつのメモリ (概算) が割り当てられる。</span><span class="sxs-lookup"><span data-stu-id="078de-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="078de-163">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="078de-164">フィールド名</span><span class="sxs-lookup"><span data-stu-id="078de-164">Field name</span></span>|<span data-ttu-id="078de-165">データ型</span><span class="sxs-lookup"><span data-stu-id="078de-165">Data type</span></span>|<span data-ttu-id="078de-166">説明</span><span class="sxs-lookup"><span data-stu-id="078de-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="078de-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="078de-167">AppDomainID</span></span>|<span data-ttu-id="078de-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-168">win:UInt64</span></span>|<span data-ttu-id="078de-169">リソースの使用状況の報告対象のアプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="078de-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="078de-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="078de-170">Allocated</span></span>|<span data-ttu-id="078de-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-171">win:UInt64</span></span>|<span data-ttu-id="078de-172">アプリケーション ドメインが作成されてから、このアプリケーション ドメインに割り当てられたバイトの合計数 (解放されたメモリの量は引かれない)。</span><span class="sxs-lookup"><span data-stu-id="078de-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="078de-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="078de-173">ClrInstanceID</span></span>|<span data-ttu-id="078de-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="078de-174">win:UInt16</span></span>|<span data-ttu-id="078de-175">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="078de-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="078de-176">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="078de-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="078de-177">AppDomainMemSurvived イベント</span><span class="sxs-lookup"><span data-stu-id="078de-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="078de-178">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="078de-179">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="078de-179">Keyword for raising the event</span></span>|<span data-ttu-id="078de-180">レベル</span><span class="sxs-lookup"><span data-stu-id="078de-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="078de-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="078de-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="078de-182">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="078de-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="078de-183">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="078de-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="078de-184">イベント</span><span class="sxs-lookup"><span data-stu-id="078de-184">Event</span></span>|<span data-ttu-id="078de-185">イベント ID</span><span class="sxs-lookup"><span data-stu-id="078de-185">Event ID</span></span>|<span data-ttu-id="078de-186">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="078de-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="078de-187">84</span><span class="sxs-lookup"><span data-stu-id="078de-187">84</span></span>|<span data-ttu-id="078de-188">各ガベージ コレクションが終了した。</span><span class="sxs-lookup"><span data-stu-id="078de-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="078de-189">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="078de-190">フィールド名</span><span class="sxs-lookup"><span data-stu-id="078de-190">Field name</span></span>|<span data-ttu-id="078de-191">データ型</span><span class="sxs-lookup"><span data-stu-id="078de-191">Data type</span></span>|<span data-ttu-id="078de-192">説明</span><span class="sxs-lookup"><span data-stu-id="078de-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="078de-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="078de-193">AppDomainID</span></span>|<span data-ttu-id="078de-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-194">win:UInt64</span></span>|<span data-ttu-id="078de-195">リソースの使用状況の報告対象のドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="078de-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="078de-196">Survived</span><span class="sxs-lookup"><span data-stu-id="078de-196">Survived</span></span>|<span data-ttu-id="078de-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-197">win:UInt64</span></span>|<span data-ttu-id="078de-198">最後のコレクションの実行後に残され、このアプリケーション ドメインによって保持されることが判明しているバイト数。</span><span class="sxs-lookup"><span data-stu-id="078de-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="078de-199">この数は、完全なコレクションの後では正確で完全ですが、短期コレクションの後では完全ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="078de-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="078de-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="078de-200">ProcessSurvived</span></span>|<span data-ttu-id="078de-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-201">win:UInt64</span></span>|<span data-ttu-id="078de-202">最後のコレクション後に残った合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="078de-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="078de-203">完全なコレクションの後では、この数はマネージド ヒープにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="078de-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="078de-204">短期コレクションの後では、この数は短期のジェネレーションにライブで保持されるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="078de-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="078de-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="078de-205">ClrInstanceID</span></span>|<span data-ttu-id="078de-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="078de-206">win:UInt16</span></span>|<span data-ttu-id="078de-207">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="078de-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="078de-208">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="078de-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="078de-209">ThreadAppDomainEnter イベント</span><span class="sxs-lookup"><span data-stu-id="078de-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="078de-210">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="078de-211">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="078de-211">Keyword for raising the event</span></span>|<span data-ttu-id="078de-212">レベル</span><span class="sxs-lookup"><span data-stu-id="078de-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="078de-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="078de-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="078de-214">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="078de-214">Informational(4)</span></span>|  
|<span data-ttu-id="078de-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="078de-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="078de-216">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="078de-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="078de-217">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="078de-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="078de-218">イベント</span><span class="sxs-lookup"><span data-stu-id="078de-218">Event</span></span>|<span data-ttu-id="078de-219">イベント ID</span><span class="sxs-lookup"><span data-stu-id="078de-219">Event ID</span></span>|<span data-ttu-id="078de-220">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="078de-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="078de-221">87</span><span class="sxs-lookup"><span data-stu-id="078de-221">87</span></span>|<span data-ttu-id="078de-222">アプリケーション ドメインにスレッドが入力される。</span><span class="sxs-lookup"><span data-stu-id="078de-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="078de-223">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="078de-224">フィールド名</span><span class="sxs-lookup"><span data-stu-id="078de-224">Field name</span></span>|<span data-ttu-id="078de-225">データ型</span><span class="sxs-lookup"><span data-stu-id="078de-225">Data type</span></span>|<span data-ttu-id="078de-226">説明</span><span class="sxs-lookup"><span data-stu-id="078de-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="078de-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="078de-227">ThreadID</span></span>|<span data-ttu-id="078de-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-228">win:UInt64</span></span>|<span data-ttu-id="078de-229">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="078de-229">The thread identifier.</span></span>|  
|<span data-ttu-id="078de-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="078de-230">AppDomainID</span></span>|<span data-ttu-id="078de-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-231">win:UInt64</span></span>|<span data-ttu-id="078de-232">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="078de-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="078de-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="078de-233">ClrInstanceID</span></span>|<span data-ttu-id="078de-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="078de-234">win:UInt16</span></span>|<span data-ttu-id="078de-235">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="078de-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="078de-236">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="078de-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="078de-237">ThreadTerminated イベント</span><span class="sxs-lookup"><span data-stu-id="078de-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="078de-238">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="078de-239">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="078de-239">Keyword for raising the event</span></span>|<span data-ttu-id="078de-240">レベル</span><span class="sxs-lookup"><span data-stu-id="078de-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="078de-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="078de-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="078de-242">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="078de-242">Informational(4)</span></span>|  
|<span data-ttu-id="078de-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="078de-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="078de-244">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="078de-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="078de-245">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="078de-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="078de-246">イベント</span><span class="sxs-lookup"><span data-stu-id="078de-246">Event</span></span>|<span data-ttu-id="078de-247">イベント ID</span><span class="sxs-lookup"><span data-stu-id="078de-247">Event ID</span></span>|<span data-ttu-id="078de-248">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="078de-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="078de-249">86</span><span class="sxs-lookup"><span data-stu-id="078de-249">86</span></span>|<span data-ttu-id="078de-250">スレッドが終了する。</span><span class="sxs-lookup"><span data-stu-id="078de-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="078de-251">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="078de-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="078de-252">フィールド名</span><span class="sxs-lookup"><span data-stu-id="078de-252">Field name</span></span>|<span data-ttu-id="078de-253">データ型</span><span class="sxs-lookup"><span data-stu-id="078de-253">Data type</span></span>|<span data-ttu-id="078de-254">説明</span><span class="sxs-lookup"><span data-stu-id="078de-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="078de-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="078de-255">ThreadID</span></span>|<span data-ttu-id="078de-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-256">win:UInt64</span></span>|<span data-ttu-id="078de-257">スレッド ID です</span><span class="sxs-lookup"><span data-stu-id="078de-257">The thread identifier.</span></span>|  
|<span data-ttu-id="078de-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="078de-258">AppDomainID</span></span>|<span data-ttu-id="078de-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="078de-259">win:UInt64</span></span>|<span data-ttu-id="078de-260">アプリケーション ドメインの識別子。</span><span class="sxs-lookup"><span data-stu-id="078de-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="078de-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="078de-261">ClrInstanceID</span></span>|<span data-ttu-id="078de-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="078de-262">win:UInt16</span></span>|<span data-ttu-id="078de-263">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="078de-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="078de-264">関連項目</span><span class="sxs-lookup"><span data-stu-id="078de-264">See also</span></span>

- [<span data-ttu-id="078de-265">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="078de-265">CLR ETW Events</span></span>](clr-etw-events.md)
