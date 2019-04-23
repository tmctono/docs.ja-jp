---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated メソッド
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fcd7a3aa1a6c034985099c24071429384563700
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129390"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="a9740-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated メソッド</span><span class="sxs-lookup"><span data-stu-id="a9740-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="a9740-103">ガベージ コレクトされているメモリを差し引くことがなく、作成されているため、アプリケーション ドメインによって行われたすべてのメモリ割り当てのバイト単位の合計サイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9740-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9740-104">構文</span><span class="sxs-lookup"><span data-stu-id="a9740-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9740-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9740-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="a9740-106">[in]要求されたアプリケーション ドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="a9740-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="a9740-107">[out]すべてのメモリ割り当ての合計サイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a9740-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9740-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a9740-108">Return Value</span></span>  
 <span data-ttu-id="a9740-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="a9740-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a9740-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9740-110">HRESULT</span></span>|<span data-ttu-id="a9740-111">説明</span><span class="sxs-lookup"><span data-stu-id="a9740-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9740-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9740-112">S_OK</span></span>|<span data-ttu-id="a9740-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="a9740-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="a9740-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="a9740-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="a9740-115">アプリケーション ドメインがアンロードされたか、存在しません。</span><span class="sxs-lookup"><span data-stu-id="a9740-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9740-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="a9740-116">Remarks</span></span>  
 <span data-ttu-id="a9740-117">このメソッドはアンマネージと同等のマネージ<xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a9740-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9740-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="a9740-118">Requirements</span></span>  
 <span data-ttu-id="a9740-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9740-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9740-120">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a9740-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a9740-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a9740-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9740-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9740-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9740-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9740-123">See also</span></span>

- [<span data-ttu-id="a9740-124">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9740-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="a9740-125">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="a9740-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="a9740-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9740-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a9740-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="a9740-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
