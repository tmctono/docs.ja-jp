---
title: ICLRPolicyManager::SetTimeoutAndAction メソッド
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb5db23db752cc82b04d97cb2bc81a3155d465be
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627174"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="2fbe0-102">ICLRPolicyManager::SetTimeoutAndAction メソッド</span><span class="sxs-lookup"><span data-stu-id="2fbe0-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="2fbe0-103">指定された操作のタイムアウト値を設定し、共通言語ランタイム (CLR) が、操作が発生したときに実行する必要がありますポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fbe0-104">構文</span><span class="sxs-lookup"><span data-stu-id="2fbe0-104">Syntax</span></span>  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fbe0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fbe0-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="2fbe0-106">[in]1 つ、 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)値、タイムアウトとポリシーを設定する対象の操作を示す`action`します。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="2fbe0-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="2fbe0-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="2fbe0-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="2fbe0-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="2fbe0-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="2fbe0-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="2fbe0-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="2fbe0-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="2fbe0-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="2fbe0-112">[in]新しいタイムアウト値 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="2fbe0-113">値が無限の原因の`operation`がタイムアウトすることはありません。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="2fbe0-114">[in]1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 、CLR がときに実行するポリシーのアクションを示す値`operation`に発生します。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fbe0-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="2fbe0-115">Return Value</span></span>  
  
|<span data-ttu-id="2fbe0-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fbe0-116">HRESULT</span></span>|<span data-ttu-id="2fbe0-117">説明</span><span class="sxs-lookup"><span data-stu-id="2fbe0-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fbe0-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fbe0-118">S_OK</span></span>|<span data-ttu-id="2fbe0-119">`SetTimeoutAndAction` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="2fbe0-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2fbe0-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2fbe0-121">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2fbe0-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2fbe0-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2fbe0-123">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-123">The call timed out.</span></span>|  
|<span data-ttu-id="2fbe0-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2fbe0-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2fbe0-125">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2fbe0-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2fbe0-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2fbe0-127">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2fbe0-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2fbe0-128">E_FAIL</span></span>|<span data-ttu-id="2fbe0-129">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2fbe0-130">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2fbe0-131">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2fbe0-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2fbe0-132">E_INVALIDARG</span></span>|<span data-ttu-id="2fbe0-133">タイムアウトを設定することはできません、指定された`operation`の無効な値が指定されているまたは`action`します。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fbe0-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="2fbe0-134">Remarks</span></span>  
 <span data-ttu-id="2fbe0-135">`SetTimeoutAndAction` 機能をカプセル化、 [iclrpolicymanager::settimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)と[iclrpolicymanager::setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)メソッド、順次これら 2 つのメソッド呼び出しの代わりに呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2fbe0-136">すべてのポリシーのアクション値は、CLR 操作ではタイムアウトの動作として指定できます。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="2fbe0-137">有効な値の 2 つのメソッドは、トピックの「解説」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fbe0-138">必要条件</span><span class="sxs-lookup"><span data-stu-id="2fbe0-138">Requirements</span></span>  
 <span data-ttu-id="2fbe0-139">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fbe0-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fbe0-140">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fbe0-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fbe0-141">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2fbe0-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fbe0-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fbe0-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fbe0-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fbe0-143">See also</span></span>

- [<span data-ttu-id="2fbe0-144">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="2fbe0-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="2fbe0-145">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="2fbe0-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="2fbe0-146">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2fbe0-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="2fbe0-147">SetActionOnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="2fbe0-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="2fbe0-148">ICLRPolicyManager::SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="2fbe0-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
