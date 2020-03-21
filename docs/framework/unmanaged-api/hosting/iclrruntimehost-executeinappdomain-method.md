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
ms.openlocfilehash: c012e4e2b5e41737f7bbe6a0fb887693b0ba22c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176423"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="b9540-102">ICLRRuntimeHost::ExecuteInAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="b9540-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="b9540-103">指定した<xref:System.AppDomain>マネージ コードを実行する対象を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9540-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9540-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9540-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9540-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9540-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="b9540-106">[in]指定したメソッドを<xref:System.AppDomain>実行する対象の数値 ID。</span><span class="sxs-lookup"><span data-stu-id="b9540-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="b9540-107">[in]指定した<xref:System.AppDomain>内で実行する関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="b9540-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="b9540-108">[in]呼び出し元が割り当てたメモリを不透明にするポインター。</span><span class="sxs-lookup"><span data-stu-id="b9540-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="b9540-109">このパラメーターは、共通言語ランタイム (CLR) によってドメイン コールバックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b9540-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="b9540-110">ランタイム管理ヒープメモリではありません。このメモリの割り当てと有効期間の両方が呼び出し元によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="b9540-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9540-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="b9540-111">Return Value</span></span>  
  
|<span data-ttu-id="b9540-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9540-112">HRESULT</span></span>|<span data-ttu-id="b9540-113">説明</span><span class="sxs-lookup"><span data-stu-id="b9540-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9540-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9540-114">S_OK</span></span>|<span data-ttu-id="b9540-115">`ExecuteInAppDomain`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b9540-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="b9540-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9540-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9540-117">CLR がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="b9540-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9540-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9540-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9540-119">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b9540-119">The call timed out.</span></span>|  
|<span data-ttu-id="b9540-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9540-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9540-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b9540-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9540-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9540-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9540-123">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="b9540-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9540-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9540-124">E_FAIL</span></span>|<span data-ttu-id="b9540-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b9540-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9540-126">メソッドがE_FAILを返した場合、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b9540-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9540-127">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="b9540-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9540-128">解説</span><span class="sxs-lookup"><span data-stu-id="b9540-128">Remarks</span></span>  
 <span data-ttu-id="b9540-129">`ExecuteInAppDomain`ホストは、指定されたマネージ<xref:System.AppDomain>メソッドを実行するマネージを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b9540-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="b9540-130">[GetCurrentAppDomainId メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)を呼び出すことによって、プロパティの値に対応するアプリケーション<xref:System.AppDomain.Id%2A>ドメインの識別子の値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b9540-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9540-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9540-131">Requirements</span></span>  
 <span data-ttu-id="b9540-132">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9540-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9540-133">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9540-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9540-134">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="b9540-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9540-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9540-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9540-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9540-136">See also</span></span>

- [<span data-ttu-id="b9540-137">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9540-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
