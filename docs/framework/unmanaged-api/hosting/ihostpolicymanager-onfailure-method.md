---
title: IHostPolicyManager::OnFailure メソッド
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
ms.openlocfilehash: 3bb65d747d7cdc81bd534108f6189eb1c94e3b15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128544"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="40e40-102">IHostPolicyManager::OnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="40e40-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="40e40-103">リソース割り当てまたは再利用の失敗に応じて、 [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)メソッドの呼び出しによって指定されたアクションを共通言語ランタイム (CLR) が実行しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="40e40-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e40-104">構文</span><span class="sxs-lookup"><span data-stu-id="40e40-104">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40e40-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40e40-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="40e40-106">から[Eclrfailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)値の1つ。 CLR が応答しているエラーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="40e40-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="40e40-107">から`failure`に応答して CLR が実行しているアクションを示す[Epolicyaction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値の1つ。</span><span class="sxs-lookup"><span data-stu-id="40e40-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40e40-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="40e40-108">Return Value</span></span>  
  
|<span data-ttu-id="40e40-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40e40-109">HRESULT</span></span>|<span data-ttu-id="40e40-110">説明</span><span class="sxs-lookup"><span data-stu-id="40e40-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40e40-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="40e40-111">S_OK</span></span>|<span data-ttu-id="40e40-112">`OnFailure` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="40e40-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="40e40-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40e40-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40e40-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="40e40-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40e40-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40e40-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40e40-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="40e40-116">The call timed out.</span></span>|  
|<span data-ttu-id="40e40-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40e40-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40e40-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="40e40-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40e40-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40e40-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40e40-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="40e40-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40e40-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40e40-121">E_FAIL</span></span>|<span data-ttu-id="40e40-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="40e40-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40e40-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="40e40-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40e40-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="40e40-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40e40-125">［要件］</span><span class="sxs-lookup"><span data-stu-id="40e40-125">Requirements</span></span>  
 <span data-ttu-id="40e40-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40e40-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e40-127">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="40e40-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40e40-128">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="40e40-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40e40-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e40-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e40-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="40e40-130">See also</span></span>

- [<span data-ttu-id="40e40-131">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="40e40-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="40e40-132">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="40e40-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="40e40-133">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40e40-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="40e40-134">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40e40-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
