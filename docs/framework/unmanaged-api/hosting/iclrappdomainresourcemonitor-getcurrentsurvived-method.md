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
ms.openlocfilehash: 408ef5419fbc2081d25ad442986ec8155bcb4c62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985193"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="c5558-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived メソッド</span><span class="sxs-lookup"><span data-stu-id="c5558-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="c5558-103">最後の完全なブロッキング ガベージ コレクション後に残っていると、現在のアプリケーション ドメインによって参照されるバイト数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c5558-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5558-104">構文</span><span class="sxs-lookup"><span data-stu-id="c5558-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5558-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5558-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="c5558-106">[in]要求されたアプリケーション ドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="c5558-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="c5558-107">[out]このアプリケーション ドメインによって保持されている最後のガベージ コレクションの後に残ったバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c5558-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="c5558-108">完全なコレクションの後は、この番号は正確で完全なは。</span><span class="sxs-lookup"><span data-stu-id="c5558-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="c5558-109">短期コレクションの後にこの数は完全な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c5558-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="c5558-110">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c5558-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="c5558-111">[out]最後のガベージ コレクションの後に残っているバイトの総数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c5558-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="c5558-112">完全なコレクションの後は、この数は、マネージ ヒープに保持されているバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="c5558-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="c5558-113">短期コレクションの後は、この数は、短期のジェネレーションにライブで保持されているバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="c5558-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="c5558-114">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c5558-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5558-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="c5558-115">Return Value</span></span>  
 <span data-ttu-id="c5558-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="c5558-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c5558-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5558-117">HRESULT</span></span>|<span data-ttu-id="c5558-118">説明</span><span class="sxs-lookup"><span data-stu-id="c5558-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5558-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5558-119">S_OK</span></span>|<span data-ttu-id="c5558-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="c5558-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="c5558-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="c5558-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="c5558-122">アプリケーション ドメインがアンロードされたか、存在しません。</span><span class="sxs-lookup"><span data-stu-id="c5558-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5558-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5558-123">Remarks</span></span>  
 <span data-ttu-id="c5558-124">統計がフル ブロッキング ガベージ コレクション後にのみ更新されます。つまり、コレクションの中に、アプリケーションが停止するを含むすべてのジェネレーションのコレクションが発生します。</span><span class="sxs-lookup"><span data-stu-id="c5558-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="c5558-125">たとえば、<xref:System.GC.Collect?displayProperty=nameWithType>メソッドのオーバー ロードは、完全なブロッキング コレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5558-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="c5558-126">同時実行ガベージ コレクションでは、バック グラウンドで行われ、アプリケーションはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="c5558-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="c5558-127">`GetCurrentSurvived`メソッドはアンマネージと同等のマネージ<xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c5558-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5558-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="c5558-128">Requirements</span></span>  
 <span data-ttu-id="c5558-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5558-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5558-130">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c5558-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c5558-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c5558-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5558-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5558-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5558-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5558-133">See also</span></span>

- [<span data-ttu-id="c5558-134">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5558-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="c5558-135">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="c5558-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="c5558-136">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5558-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c5558-137">ホスティング</span><span class="sxs-lookup"><span data-stu-id="c5558-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
