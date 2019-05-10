---
title: ICLRPolicyManager::SetActionOnTimeout メソッド
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8d99f4f0615e7d25991b37030b7cb609985192f
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910664"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="dc216-102">ICLRPolicyManager::SetActionOnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="dc216-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="dc216-103">共通言語ランタイム (CLR) が、指定された操作がタイムアウトしたときに実行するポリシー アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc216-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc216-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc216-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc216-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc216-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="dc216-106">[in]1 つ、 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)タイムアウト時の動作を指定するための操作を示す値。</span><span class="sxs-lookup"><span data-stu-id="dc216-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="dc216-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dc216-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="dc216-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="dc216-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="dc216-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="dc216-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="dc216-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="dc216-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="dc216-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="dc216-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="dc216-112">[in]1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)操作がタイムアウトになるときに実行されるポリシーのアクションを示す値。</span><span class="sxs-lookup"><span data-stu-id="dc216-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc216-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="dc216-113">Return Value</span></span>  
  
|<span data-ttu-id="dc216-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc216-114">HRESULT</span></span>|<span data-ttu-id="dc216-115">説明</span><span class="sxs-lookup"><span data-stu-id="dc216-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc216-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc216-116">S_OK</span></span>|<span data-ttu-id="dc216-117">`SetActionOnTimeout` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="dc216-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="dc216-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc216-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc216-119">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="dc216-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc216-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc216-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc216-121">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="dc216-121">The call timed out.</span></span>|  
|<span data-ttu-id="dc216-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc216-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc216-123">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="dc216-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc216-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc216-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc216-125">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="dc216-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc216-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc216-126">E_FAIL</span></span>|<span data-ttu-id="dc216-127">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="dc216-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc216-128">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dc216-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc216-129">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="dc216-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dc216-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dc216-130">E_INVALIDARG</span></span>|<span data-ttu-id="dc216-131">タイムアウトを設定することはできません、指定された`operation`の無効な値が指定されているまたは`operation`します。</span><span class="sxs-lookup"><span data-stu-id="dc216-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc216-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc216-132">Remarks</span></span>  
 <span data-ttu-id="dc216-133">タイムアウト値は、設定、CLR によって既定のタイムアウトまたはへの呼び出しで host で指定した値のいずれかを指定できます、 [iclrpolicymanager::settimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="dc216-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="dc216-134">すべてのポリシーのアクション値は、CLR 操作ではタイムアウトの動作として指定できます。</span><span class="sxs-lookup"><span data-stu-id="dc216-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="dc216-135">`SetActionOnTimeout` 通常の動作をエスカレートする場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc216-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="dc216-136">たとえば、ホストにルード スレッドの中止するになっていることを指定することができますが、スレッドの中止、その逆を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc216-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="dc216-137">次の表は、有効な説明`action`の値が有効な`operation`値。</span><span class="sxs-lookup"><span data-stu-id="dc216-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="dc216-138">値 `operation`</span><span class="sxs-lookup"><span data-stu-id="dc216-138">Value for `operation`</span></span>|<span data-ttu-id="dc216-139">有効な値 `action`</span><span class="sxs-lookup"><span data-stu-id="dc216-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="dc216-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="dc216-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="dc216-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="dc216-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="dc216-142">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="dc216-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="dc216-143">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dc216-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="dc216-144">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dc216-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="dc216-145">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="dc216-145">-   eExitProcess</span></span><br /><span data-ttu-id="dc216-146">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dc216-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="dc216-147">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="dc216-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="dc216-148">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="dc216-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="dc216-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="dc216-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="dc216-150">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dc216-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="dc216-151">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="dc216-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="dc216-152">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="dc216-152">-   eExitProcess</span></span><br /><span data-ttu-id="dc216-153">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dc216-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="dc216-154">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="dc216-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="dc216-155">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="dc216-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="dc216-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="dc216-156">OPR_ProcessExit</span></span>|<span data-ttu-id="dc216-157">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="dc216-157">-   eExitProcess</span></span><br /><span data-ttu-id="dc216-158">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="dc216-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="dc216-159">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="dc216-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="dc216-160">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="dc216-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dc216-161">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc216-161">Requirements</span></span>  
 <span data-ttu-id="dc216-162">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc216-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc216-163">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dc216-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc216-164">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="dc216-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc216-165">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc216-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc216-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc216-166">See also</span></span>

- [<span data-ttu-id="dc216-167">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="dc216-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="dc216-168">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="dc216-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="dc216-169">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc216-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="dc216-170">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc216-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
