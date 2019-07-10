---
title: ICLRRuntimeHost::UnloadAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e1a2358590b95b39b6495b74078f079c5b34876
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765678"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="0153b-102">ICLRRuntimeHost::UnloadAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="0153b-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="0153b-103">マネージ アンロード<xref:System.AppDomain>指定した数値識別子に対応します。</span><span class="sxs-lookup"><span data-stu-id="0153b-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0153b-104">構文</span><span class="sxs-lookup"><span data-stu-id="0153b-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0153b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0153b-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="0153b-106">[in]アンロードするアプリケーション ドメインの数値識別子。</span><span class="sxs-lookup"><span data-stu-id="0153b-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="0153b-107">[in]`true`を共通言語ランタイム (CLR) がアプリケーション ドメインをアンロードする前に、アプリケーションの現在のスレッドの実行が完了するまで待機する必要があるかを示します。</span><span class="sxs-lookup"><span data-stu-id="0153b-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0153b-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0153b-108">Return Value</span></span>  
  
|<span data-ttu-id="0153b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0153b-109">HRESULT</span></span>|<span data-ttu-id="0153b-110">説明</span><span class="sxs-lookup"><span data-stu-id="0153b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0153b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0153b-111">S_OK</span></span>|<span data-ttu-id="0153b-112">`UnloadAppDomain` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="0153b-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="0153b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0153b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0153b-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="0153b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0153b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0153b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0153b-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="0153b-116">The call timed out.</span></span>|  
|<span data-ttu-id="0153b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0153b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0153b-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0153b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0153b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0153b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0153b-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="0153b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0153b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0153b-121">E_FAIL</span></span>|<span data-ttu-id="0153b-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0153b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0153b-123">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0153b-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0153b-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0153b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0153b-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="0153b-125">Remarks</span></span>  
 <span data-ttu-id="0153b-126">呼び出すことによって、現在のスレッドを実行しているアプリケーション ドメインの数値識別子を取得する[GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="0153b-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="0153b-127">この識別子に対応する、<xref:System.AppDomain.Id%2A>マネージ プロパティ<xref:System.AppDomain>型。</span><span class="sxs-lookup"><span data-stu-id="0153b-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0153b-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="0153b-128">Requirements</span></span>  
 <span data-ttu-id="0153b-129">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0153b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0153b-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0153b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0153b-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0153b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0153b-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0153b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0153b-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="0153b-133">See also</span></span>

- [<span data-ttu-id="0153b-134">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0153b-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
