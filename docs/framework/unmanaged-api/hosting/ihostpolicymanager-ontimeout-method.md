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
ms.openlocfilehash: d5b5fa5198ae2c0bba30ae0f8d6d3834f2891672
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178007"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="12b6e-102">IHostPolicyManager::OnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="12b6e-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="12b6e-103">共通言語ランタイム (CLR) がタイムアウトに応答して[メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)の呼び出しによって指定されたアクションを実行しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="12b6e-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b6e-104">構文</span><span class="sxs-lookup"><span data-stu-id="12b6e-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12b6e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12b6e-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="12b6e-106">[in]タイムアウトした操作の種類を示す[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="12b6e-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="12b6e-107">[in]タイムアウトに応答して CLR が実行しているアクションを示す[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="12b6e-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12b6e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="12b6e-108">Return Value</span></span>  
  
|<span data-ttu-id="12b6e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12b6e-109">HRESULT</span></span>|<span data-ttu-id="12b6e-110">説明</span><span class="sxs-lookup"><span data-stu-id="12b6e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12b6e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="12b6e-111">S_OK</span></span>|<span data-ttu-id="12b6e-112">`OnTimeout`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="12b6e-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="12b6e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="12b6e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="12b6e-114">CLR がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="12b6e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="12b6e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="12b6e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="12b6e-116">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="12b6e-116">The call timed out.</span></span>|  
|<span data-ttu-id="12b6e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="12b6e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="12b6e-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="12b6e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="12b6e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="12b6e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="12b6e-120">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="12b6e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="12b6e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="12b6e-121">E_FAIL</span></span>|<span data-ttu-id="12b6e-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="12b6e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="12b6e-123">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="12b6e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="12b6e-124">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="12b6e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12b6e-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="12b6e-125">Requirements</span></span>  
 <span data-ttu-id="12b6e-126">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12b6e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12b6e-127">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="12b6e-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12b6e-128">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="12b6e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12b6e-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12b6e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b6e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="12b6e-130">See also</span></span>

- [<span data-ttu-id="12b6e-131">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="12b6e-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="12b6e-132">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="12b6e-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="12b6e-133">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12b6e-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="12b6e-134">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12b6e-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
