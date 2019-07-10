---
title: ICLRRuntimeHost::ExecuteInAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 314ffb143e99f9490bcd4a6489f2afed314b7c2c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768763"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="2a110-102">ICLRRuntimeHost::ExecuteInAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="2a110-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="2a110-103">指定します、<xref:System.AppDomain>指定したマネージ コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="2a110-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a110-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a110-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a110-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a110-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="2a110-106">[in]数値 ID、<xref:System.AppDomain>指定されたメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2a110-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="2a110-107">[in]指定した中で実行する関数へのポインター<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="2a110-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="2a110-108">[in]非透過の呼び出し元が割り当てたメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2a110-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="2a110-109">このパラメーターは、共通言語ランタイム (CLR) でドメインのコールバックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="2a110-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="2a110-110">ランタイムで管理されたヒープ メモリではありません。このメモリの有効期間と割り当ては、呼び出し元によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="2a110-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a110-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="2a110-111">Return Value</span></span>  
  
|<span data-ttu-id="2a110-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a110-112">HRESULT</span></span>|<span data-ttu-id="2a110-113">説明</span><span class="sxs-lookup"><span data-stu-id="2a110-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a110-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a110-114">S_OK</span></span>|<span data-ttu-id="2a110-115">`ExecuteInAppDomain` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="2a110-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="2a110-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a110-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a110-117">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="2a110-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a110-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a110-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a110-119">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="2a110-119">The call timed out.</span></span>|  
|<span data-ttu-id="2a110-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a110-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a110-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2a110-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a110-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a110-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a110-123">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="2a110-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a110-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a110-124">E_FAIL</span></span>|<span data-ttu-id="2a110-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2a110-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a110-126">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2a110-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a110-127">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2a110-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a110-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a110-128">Remarks</span></span>  
 <span data-ttu-id="2a110-129">`ExecuteInAppDomain` コントロールを練習をホストできるように管理 over<xref:System.AppDomain>で指定したマネージ メソッドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a110-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="2a110-130">値に対応するアプリケーション ドメインの識別子の値を取得することができます、<xref:System.AppDomain.Id%2A>プロパティを呼び出すことによって[GetCurrentAppDomainId メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="2a110-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a110-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="2a110-131">Requirements</span></span>  
 <span data-ttu-id="2a110-132">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a110-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a110-133">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a110-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a110-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2a110-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a110-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a110-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a110-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a110-136">See also</span></span>

- [<span data-ttu-id="2a110-137">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a110-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
