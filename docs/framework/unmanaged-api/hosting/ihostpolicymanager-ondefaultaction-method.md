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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45167a2b358b9a7a39390c07f552aa3f3dabce4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760143"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="ac2b3-102">IHostPolicyManager::OnDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="ac2b3-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="ac2b3-103">呼び出しによって設定された既定のアクションに共通言語ランタイム (CLR) であるホストに通知します、 [iclrpolicymanager::setdefaultaction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)スレッドの中止への応答でメソッドまたは<xref:System.AppDomain>をアンロードします。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac2b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="ac2b3-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac2b3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac2b3-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="ac2b3-106">[in]1 つ、 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) CLR が応答してイベントの種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="ac2b3-107">[in]1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)イベントへの応答で、CLR がかかっている操作を示す値。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac2b3-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ac2b3-108">Return Value</span></span>  
  
|<span data-ttu-id="ac2b3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac2b3-109">HRESULT</span></span>|<span data-ttu-id="ac2b3-110">説明</span><span class="sxs-lookup"><span data-stu-id="ac2b3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac2b3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac2b3-111">S_OK</span></span>|<span data-ttu-id="ac2b3-112">`OnDefaultAction` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="ac2b3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac2b3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac2b3-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しの処理にことはできません。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="ac2b3-115">正常に</span><span class="sxs-lookup"><span data-stu-id="ac2b3-115">successfully</span></span>|  
|<span data-ttu-id="ac2b3-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac2b3-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac2b3-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-117">The call timed out.</span></span>|  
|<span data-ttu-id="ac2b3-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac2b3-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac2b3-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac2b3-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac2b3-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac2b3-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac2b3-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac2b3-122">E_FAIL</span></span>|<span data-ttu-id="ac2b3-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac2b3-124">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac2b3-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac2b3-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="ac2b3-126">Requirements</span></span>  
 <span data-ttu-id="ac2b3-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac2b3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac2b3-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac2b3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac2b3-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ac2b3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac2b3-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac2b3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2b3-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac2b3-131">See also</span></span>

- [<span data-ttu-id="ac2b3-132">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="ac2b3-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="ac2b3-133">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="ac2b3-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="ac2b3-134">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac2b3-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="ac2b3-135">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac2b3-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
