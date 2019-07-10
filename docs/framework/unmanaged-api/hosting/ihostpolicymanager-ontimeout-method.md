---
title: IHostPolicyManager::OnTimeout メソッド
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75e6ff3b2b7c8f4b8611630092203aace0ce3136
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781016"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="e38da-102">IHostPolicyManager::OnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="e38da-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="e38da-103">共通言語ランタイム (CLR) はへの呼び出しで指定されたアクションを実行するホストに通知します、 [iclrpolicymanager::setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)タイムアウトへの応答方法。</span><span class="sxs-lookup"><span data-stu-id="e38da-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e38da-104">構文</span><span class="sxs-lookup"><span data-stu-id="e38da-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e38da-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e38da-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="e38da-106">[in]1 つ、 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)タイムアウトした操作の種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="e38da-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="e38da-107">[in]1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値は、タイムアウトへの応答時間が、CLR の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="e38da-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e38da-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e38da-108">Return Value</span></span>  
  
|<span data-ttu-id="e38da-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e38da-109">HRESULT</span></span>|<span data-ttu-id="e38da-110">説明</span><span class="sxs-lookup"><span data-stu-id="e38da-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e38da-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e38da-111">S_OK</span></span>|<span data-ttu-id="e38da-112">`OnTimeout` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e38da-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="e38da-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e38da-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e38da-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="e38da-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e38da-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e38da-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e38da-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="e38da-116">The call timed out.</span></span>|  
|<span data-ttu-id="e38da-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e38da-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e38da-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e38da-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e38da-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e38da-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e38da-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="e38da-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e38da-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e38da-121">E_FAIL</span></span>|<span data-ttu-id="e38da-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e38da-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e38da-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e38da-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e38da-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e38da-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e38da-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="e38da-125">Requirements</span></span>  
 <span data-ttu-id="e38da-126">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e38da-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e38da-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e38da-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e38da-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e38da-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e38da-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e38da-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e38da-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="e38da-130">See also</span></span>

- [<span data-ttu-id="e38da-131">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="e38da-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="e38da-132">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="e38da-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="e38da-133">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e38da-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="e38da-134">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e38da-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
