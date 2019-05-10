---
title: ICLRAppDomainResourceMonitor インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f336ac45e4bf5894c667412ff89acde4b9524c80
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666068"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="6f3cb-102">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f3cb-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="6f3cb-103">アプリケーション ドメインのメモリと CPU 使用率を確認するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="6f3cb-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f3cb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6f3cb-104">Methods</span></span>  
  
|<span data-ttu-id="6f3cb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6f3cb-105">Method</span></span>|<span data-ttu-id="6f3cb-106">説明</span><span class="sxs-lookup"><span data-stu-id="6f3cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f3cb-107">GetCurrentAllocated メソッド</span><span class="sxs-lookup"><span data-stu-id="6f3cb-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="6f3cb-108">ガベージ コレクトされているメモリを差し引くことがなく、作成されているため、アプリケーション ドメインによって行われたすべてのメモリ割り当てのバイト単位の合計サイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="6f3cb-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="6f3cb-109">GetCurrentSurvived メソッド</span><span class="sxs-lookup"><span data-stu-id="6f3cb-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="6f3cb-110">最後の完全なブロッキング ガベージ コレクション後に残っていると、現在のアプリケーション ドメインによって参照されるバイト数を取得します。</span><span class="sxs-lookup"><span data-stu-id="6f3cb-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="6f3cb-111">GetCurrentCpuTime メソッド</span><span class="sxs-lookup"><span data-stu-id="6f3cb-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="6f3cb-112">アプリケーション ドメインが作成されたために、現在のアプリケーション ドメインで実行中にすべてのスレッドによって使用されているプロセッサの合計時間を取得します。</span><span class="sxs-lookup"><span data-stu-id="6f3cb-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f3cb-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f3cb-113">Remarks</span></span>  
 <span data-ttu-id="6f3cb-114">`ICLRAppDomainResourceMonitor`インターフェイスは、次のマネージ プロパティを次のような機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6f3cb-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="6f3cb-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="6f3cb-115">Requirements</span></span>  
 <span data-ttu-id="6f3cb-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f3cb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f3cb-117">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6f3cb-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6f3cb-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6f3cb-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f3cb-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f3cb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f3cb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f3cb-120">See also</span></span>

- [<span data-ttu-id="6f3cb-121">\<appDomainResourceMonitoring > 要素</span><span class="sxs-lookup"><span data-stu-id="6f3cb-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="6f3cb-122">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="6f3cb-122">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="6f3cb-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f3cb-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="6f3cb-124">ホスティング</span><span class="sxs-lookup"><span data-stu-id="6f3cb-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
