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
ms.openlocfilehash: 208d567aa5c19ddcf8bf9b13b452cb4fc48c976f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126766"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="96994-102">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96994-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="96994-103">アプリケーションドメインのメモリおよび CPU 使用率を検査するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="96994-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96994-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="96994-104">Methods</span></span>  
  
|<span data-ttu-id="96994-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="96994-105">Method</span></span>|<span data-ttu-id="96994-106">説明</span><span class="sxs-lookup"><span data-stu-id="96994-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96994-107">GetCurrentAllocated メソッド</span><span class="sxs-lookup"><span data-stu-id="96994-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="96994-108">アプリケーションドメインが作成されてからアプリケーションドメインによって行われたすべてのメモリ割り当ての合計サイズ (バイト単位) を取得します。ガベージコレクトされたメモリは減算されません。</span><span class="sxs-lookup"><span data-stu-id="96994-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="96994-109">GetCurrentSurvived メソッド</span><span class="sxs-lookup"><span data-stu-id="96994-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="96994-110">最後の完全なブロッキングガベージコレクションの後に残った、現在のアプリケーションドメインによって参照されているバイト数を取得します。</span><span class="sxs-lookup"><span data-stu-id="96994-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="96994-111">GetCurrentCpuTime メソッド</span><span class="sxs-lookup"><span data-stu-id="96994-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="96994-112">アプリケーションドメインが作成されてから、現在のアプリケーションドメインでの実行中にすべてのスレッドによって使用された合計プロセッサ時間を取得します。</span><span class="sxs-lookup"><span data-stu-id="96994-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96994-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="96994-113">Remarks</span></span>  
 <span data-ttu-id="96994-114">`ICLRAppDomainResourceMonitor` インターフェイスには、次のマネージプロパティと同様の機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="96994-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="96994-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="96994-115">Requirements</span></span>  
 <span data-ttu-id="96994-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96994-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96994-117">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="96994-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="96994-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="96994-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96994-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96994-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96994-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="96994-120">See also</span></span>

- [<span data-ttu-id="96994-121">\<appDomainResourceMonitoring > 要素</span><span class="sxs-lookup"><span data-stu-id="96994-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="96994-122">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="96994-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="96994-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96994-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="96994-124">ホスティング</span><span class="sxs-lookup"><span data-stu-id="96994-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
