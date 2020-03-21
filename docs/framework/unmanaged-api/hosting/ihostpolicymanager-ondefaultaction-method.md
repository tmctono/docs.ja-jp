---
title: IHostPolicyManager::OnDefaultAction メソッド
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
ms.openlocfilehash: 8d987614c1a5a2c90ccb3faa11c605767ae5cfda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178018"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="8d77a-102">IHostPolicyManager::OnDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="8d77a-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="8d77a-103">共通言語ランタイム (CLR) が、スレッドの中止または<xref:System.AppDomain>アンロードに応答して[ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)メソッドの呼び出しによって設定された既定のアクションを実行しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="8d77a-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d77a-104">構文</span><span class="sxs-lookup"><span data-stu-id="8d77a-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d77a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8d77a-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="8d77a-106">[in]CLR が応答するイベントの種類を示す[、EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="8d77a-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="8d77a-107">[in]イベントに応答して CLR が実行しているアクションを示す[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="8d77a-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d77a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="8d77a-108">Return Value</span></span>  
  
|<span data-ttu-id="8d77a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d77a-109">HRESULT</span></span>|<span data-ttu-id="8d77a-110">説明</span><span class="sxs-lookup"><span data-stu-id="8d77a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d77a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d77a-111">S_OK</span></span>|<span data-ttu-id="8d77a-112">`OnDefaultAction`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="8d77a-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="8d77a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8d77a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8d77a-114">CLR がプロセスに読み込まれていないか、CLR がマネージ コードを実行したり呼び出しを処理できない状態にしています。</span><span class="sxs-lookup"><span data-stu-id="8d77a-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="8d77a-115">正しく</span><span class="sxs-lookup"><span data-stu-id="8d77a-115">successfully</span></span>|  
|<span data-ttu-id="8d77a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8d77a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8d77a-117">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="8d77a-117">The call timed out.</span></span>|  
|<span data-ttu-id="8d77a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8d77a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8d77a-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8d77a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8d77a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8d77a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8d77a-121">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="8d77a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8d77a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d77a-122">E_FAIL</span></span>|<span data-ttu-id="8d77a-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8d77a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8d77a-124">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8d77a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8d77a-125">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="8d77a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d77a-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="8d77a-126">Requirements</span></span>  
 <span data-ttu-id="8d77a-127">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d77a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d77a-128">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d77a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d77a-129">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="8d77a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d77a-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d77a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d77a-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d77a-131">See also</span></span>

- [<span data-ttu-id="8d77a-132">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="8d77a-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="8d77a-133">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="8d77a-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="8d77a-134">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d77a-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="8d77a-135">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d77a-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
