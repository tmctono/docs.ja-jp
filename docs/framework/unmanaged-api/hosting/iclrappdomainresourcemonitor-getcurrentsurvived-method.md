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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf285b6e1f703c8776937fa33c7ab5801f04f80f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950160"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="7e468-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived メソッド</span><span class="sxs-lookup"><span data-stu-id="7e468-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="7e468-103">最後の完全なブロッキングガベージコレクションの後に残った、現在のアプリケーションドメインによって参照されているバイト数を取得します。</span><span class="sxs-lookup"><span data-stu-id="7e468-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e468-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e468-104">Syntax</span></span>  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e468-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e468-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="7e468-106">から要求されたアプリケーションドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="7e468-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="7e468-107">入出力このアプリケーションドメインによって保持されている最後のガベージコレクションの後に残ったバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7e468-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="7e468-108">完全なコレクションの後、この数値は正確で完全になります。</span><span class="sxs-lookup"><span data-stu-id="7e468-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="7e468-109">短期コレクションの後、この数値は不完全になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e468-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="7e468-110">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="7e468-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="7e468-111">入出力最後のガベージコレクションから残された合計バイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7e468-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="7e468-112">完全なコレクションの後、この数値はマネージヒープに保持されているバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="7e468-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="7e468-113">短期コレクションの後、この数は短期のジェネレーションでライブに保持されているバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="7e468-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="7e468-114">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="7e468-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e468-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="7e468-115">Return Value</span></span>  
 <span data-ttu-id="7e468-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="7e468-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7e468-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e468-117">HRESULT</span></span>|<span data-ttu-id="7e468-118">説明</span><span class="sxs-lookup"><span data-stu-id="7e468-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e468-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e468-119">S_OK</span></span>|<span data-ttu-id="7e468-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="7e468-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="7e468-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="7e468-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="7e468-122">アプリケーションドメインがアンロードされているか、または存在しません。</span><span class="sxs-lookup"><span data-stu-id="7e468-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e468-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e468-123">Remarks</span></span>  
 <span data-ttu-id="7e468-124">統計は、完全なブロッキングガベージコレクションの後にのみ更新されます。つまり、コレクションの実行中にアプリケーションを停止する、すべてのジェネレーションを含むコレクションです。</span><span class="sxs-lookup"><span data-stu-id="7e468-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="7e468-125">たとえば、メソッドオーバーロード<xref:System.GC.Collect?displayProperty=nameWithType>は、完全なブロッキングコレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e468-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="7e468-126">同時実行ガベージコレクションはバックグラウンドで発生し、アプリケーションをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="7e468-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="7e468-127">メソッドは、マネージ<xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>プロパティに対応するアンマネージドプロパティです。 `GetCurrentSurvived`</span><span class="sxs-lookup"><span data-stu-id="7e468-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e468-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="7e468-128">Requirements</span></span>  
 <span data-ttu-id="7e468-129">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e468-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e468-130">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="7e468-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7e468-131">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7e468-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e468-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e468-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e468-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e468-133">See also</span></span>

- [<span data-ttu-id="7e468-134">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e468-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="7e468-135">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="7e468-135">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="7e468-136">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7e468-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7e468-137">ホスティング</span><span class="sxs-lookup"><span data-stu-id="7e468-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
