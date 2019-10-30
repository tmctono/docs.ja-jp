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
ms.openlocfilehash: f19ac39737d08c10c23ce0bde03131f52b660cac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126816"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="5faa9-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated メソッド</span><span class="sxs-lookup"><span data-stu-id="5faa9-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="5faa9-103">アプリケーションドメインが作成されてからアプリケーションドメインによって行われたすべてのメモリ割り当ての合計サイズ (バイト単位) を取得します。ガベージコレクトされたメモリは減算されません。</span><span class="sxs-lookup"><span data-stu-id="5faa9-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5faa9-104">構文</span><span class="sxs-lookup"><span data-stu-id="5faa9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5faa9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5faa9-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="5faa9-106">から要求されたアプリケーションドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="5faa9-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="5faa9-107">入出力すべてのメモリ割り当ての合計サイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5faa9-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5faa9-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5faa9-108">Return Value</span></span>  
 <span data-ttu-id="5faa9-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="5faa9-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5faa9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5faa9-110">HRESULT</span></span>|<span data-ttu-id="5faa9-111">説明</span><span class="sxs-lookup"><span data-stu-id="5faa9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5faa9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5faa9-112">S_OK</span></span>|<span data-ttu-id="5faa9-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="5faa9-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="5faa9-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="5faa9-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="5faa9-115">アプリケーションドメインがアンロードされているか、または存在しません。</span><span class="sxs-lookup"><span data-stu-id="5faa9-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5faa9-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="5faa9-116">Remarks</span></span>  
 <span data-ttu-id="5faa9-117">このメソッドは、マネージ <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> プロパティに対応するアンマネージドです。</span><span class="sxs-lookup"><span data-stu-id="5faa9-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5faa9-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="5faa9-118">Requirements</span></span>  
 <span data-ttu-id="5faa9-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5faa9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5faa9-120">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="5faa9-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5faa9-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5faa9-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5faa9-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5faa9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5faa9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="5faa9-123">See also</span></span>

- [<span data-ttu-id="5faa9-124">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5faa9-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="5faa9-125">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="5faa9-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="5faa9-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5faa9-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5faa9-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="5faa9-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
