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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3187a72d4b05be8d7b5b49df149366c4beb11d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779600"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="da8c6-102">IHostPolicyManager::OnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="da8c6-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="da8c6-103">共通言語ランタイム (CLR) はへの呼び出しで指定されたアクションを実行するホストに通知します、 [iclrpolicymanager::setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)メソッドでは、リソース割り当てまたは解放の失敗に応答します。</span><span class="sxs-lookup"><span data-stu-id="da8c6-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da8c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="da8c6-104">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da8c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da8c6-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="da8c6-106">[in]1 つ、 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) CLR が応答してエラーの種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="da8c6-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="da8c6-107">[in]1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)への応答が、CLR の操作を示す値、かかって`failure`します。</span><span class="sxs-lookup"><span data-stu-id="da8c6-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da8c6-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="da8c6-108">Return Value</span></span>  
  
|<span data-ttu-id="da8c6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da8c6-109">HRESULT</span></span>|<span data-ttu-id="da8c6-110">説明</span><span class="sxs-lookup"><span data-stu-id="da8c6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da8c6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="da8c6-111">S_OK</span></span>|<span data-ttu-id="da8c6-112">`OnFailure` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="da8c6-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="da8c6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="da8c6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="da8c6-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="da8c6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="da8c6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="da8c6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="da8c6-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="da8c6-116">The call timed out.</span></span>|  
|<span data-ttu-id="da8c6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="da8c6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="da8c6-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="da8c6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="da8c6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="da8c6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="da8c6-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="da8c6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="da8c6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="da8c6-121">E_FAIL</span></span>|<span data-ttu-id="da8c6-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="da8c6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="da8c6-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="da8c6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="da8c6-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="da8c6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da8c6-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="da8c6-125">Requirements</span></span>  
 <span data-ttu-id="da8c6-126">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="da8c6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da8c6-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="da8c6-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da8c6-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="da8c6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da8c6-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da8c6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da8c6-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="da8c6-130">See also</span></span>

- [<span data-ttu-id="da8c6-131">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="da8c6-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="da8c6-132">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="da8c6-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="da8c6-133">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da8c6-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="da8c6-134">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da8c6-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
