---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived メソッド
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
ms.openlocfilehash: 62fcdb60b83c88738ebe2e39455b8eae60fb705e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126777"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="dd262-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived メソッド</span><span class="sxs-lookup"><span data-stu-id="dd262-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="dd262-103">最後の完全なブロッキングガベージコレクションの後に残った、現在のアプリケーションドメインによって参照されているバイト数を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd262-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd262-104">構文</span><span class="sxs-lookup"><span data-stu-id="dd262-104">Syntax</span></span>  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd262-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd262-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="dd262-106">から要求されたアプリケーションドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="dd262-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="dd262-107">入出力このアプリケーションドメインによって保持されている最後のガベージコレクションの後に残ったバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dd262-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="dd262-108">完全なコレクションの後、この数値は正確で完全になります。</span><span class="sxs-lookup"><span data-stu-id="dd262-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="dd262-109">短期コレクションの後、この数値は不完全になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd262-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="dd262-110">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="dd262-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="dd262-111">入出力最後のガベージコレクションから残された合計バイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dd262-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="dd262-112">完全なコレクションの後、この数値はマネージヒープに保持されているバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="dd262-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="dd262-113">短期コレクションの後、この数は短期のジェネレーションでライブに保持されているバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="dd262-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="dd262-114">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="dd262-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd262-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="dd262-115">Return Value</span></span>  
 <span data-ttu-id="dd262-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="dd262-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dd262-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd262-117">HRESULT</span></span>|<span data-ttu-id="dd262-118">説明</span><span class="sxs-lookup"><span data-stu-id="dd262-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd262-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd262-119">S_OK</span></span>|<span data-ttu-id="dd262-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="dd262-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="dd262-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="dd262-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="dd262-122">アプリケーションドメインがアンロードされているか、または存在しません。</span><span class="sxs-lookup"><span data-stu-id="dd262-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd262-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="dd262-123">Remarks</span></span>  
 <span data-ttu-id="dd262-124">統計は、完全なブロッキングガベージコレクションの後にのみ更新されます。つまり、コレクションの実行中にアプリケーションを停止する、すべてのジェネレーションを含むコレクションです。</span><span class="sxs-lookup"><span data-stu-id="dd262-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="dd262-125">たとえば、<xref:System.GC.Collect?displayProperty=nameWithType> メソッドのオーバーロードは、完全なブロッキングコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd262-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="dd262-126">同時実行ガベージコレクションはバックグラウンドで発生し、アプリケーションをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="dd262-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="dd262-127">`GetCurrentSurvived` メソッドは、マネージ <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> プロパティと同等のアンマネージドです。</span><span class="sxs-lookup"><span data-stu-id="dd262-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd262-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="dd262-128">Requirements</span></span>  
 <span data-ttu-id="dd262-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd262-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd262-130">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="dd262-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dd262-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="dd262-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd262-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd262-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd262-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd262-133">See also</span></span>

- [<span data-ttu-id="dd262-134">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd262-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="dd262-135">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="dd262-135">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="dd262-136">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd262-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="dd262-137">ホスティング</span><span class="sxs-lookup"><span data-stu-id="dd262-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
