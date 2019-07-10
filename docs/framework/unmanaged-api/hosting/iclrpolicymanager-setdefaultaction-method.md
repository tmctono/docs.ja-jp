---
title: ICLRPolicyManager::SetDefaultAction メソッド
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63398902071b4cfa1964f77b5641baa6e6239eb5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757358"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="01e7c-102">ICLRPolicyManager::SetDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="01e7c-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="01e7c-103">共通言語ランタイム (CLR) が、指定された操作が発生したときに実行する必要がありますポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="01e7c-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01e7c-104">構文</span><span class="sxs-lookup"><span data-stu-id="01e7c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01e7c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="01e7c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="01e7c-106">[in]1 つ、 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) CLR の動作をカスタマイズする必要がありますの操作を示す値。</span><span class="sxs-lookup"><span data-stu-id="01e7c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="01e7c-107">[in]1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)ポリシー アクション、CLR には、ときに実行する必要がありますを示す値`operation`に発生します。</span><span class="sxs-lookup"><span data-stu-id="01e7c-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01e7c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="01e7c-108">Return Value</span></span>  
  
|<span data-ttu-id="01e7c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01e7c-109">HRESULT</span></span>|<span data-ttu-id="01e7c-110">説明</span><span class="sxs-lookup"><span data-stu-id="01e7c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01e7c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="01e7c-111">S_OK</span></span>|<span data-ttu-id="01e7c-112">`SetDefaultAction` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="01e7c-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="01e7c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01e7c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01e7c-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="01e7c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01e7c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01e7c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01e7c-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="01e7c-116">The call timed out.</span></span>|  
|<span data-ttu-id="01e7c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01e7c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01e7c-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="01e7c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01e7c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01e7c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01e7c-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="01e7c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01e7c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01e7c-121">E_FAIL</span></span>|<span data-ttu-id="01e7c-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="01e7c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01e7c-123">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="01e7c-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01e7c-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="01e7c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="01e7c-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01e7c-125">E_INVALIDARG</span></span>|<span data-ttu-id="01e7c-126">無効な`action`が指定されました、`operation`の無効な値が指定されているまたは`operation`します。</span><span class="sxs-lookup"><span data-stu-id="01e7c-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01e7c-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="01e7c-127">Remarks</span></span>  
 <span data-ttu-id="01e7c-128">すべてのポリシーのアクション値は、CLR 操作では既定の動作として指定できます。</span><span class="sxs-lookup"><span data-stu-id="01e7c-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="01e7c-129">`SetDefaultAction` エスカレーションの動作だけに通常使用できます。</span><span class="sxs-lookup"><span data-stu-id="01e7c-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="01e7c-130">たとえば、ホストにルード スレッドの中止するになっていることを指定することができますが、スレッドの中止、その逆を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="01e7c-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="01e7c-131">次の表は、有効な説明`action`可能性のある各値`operation`値。</span><span class="sxs-lookup"><span data-stu-id="01e7c-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="01e7c-132">値 `operation`</span><span class="sxs-lookup"><span data-stu-id="01e7c-132">Value for `operation`</span></span>|<span data-ttu-id="01e7c-133">有効な値 `action`</span><span class="sxs-lookup"><span data-stu-id="01e7c-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="01e7c-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="01e7c-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="01e7c-135">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="01e7c-135">-   eAbortThread</span></span><br /><span data-ttu-id="01e7c-136">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="01e7c-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="01e7c-137">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01e7c-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="01e7c-138">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01e7c-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01e7c-139">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-139">-   eExitProcess</span></span><br /><span data-ttu-id="01e7c-140">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="01e7c-141">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01e7c-142">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01e7c-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01e7c-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="01e7c-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="01e7c-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="01e7c-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="01e7c-145">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="01e7c-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="01e7c-146">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01e7c-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="01e7c-147">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01e7c-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01e7c-148">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-148">-   eExitProcess</span></span><br /><span data-ttu-id="01e7c-149">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="01e7c-150">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01e7c-151">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01e7c-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01e7c-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="01e7c-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="01e7c-153">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01e7c-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="01e7c-154">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01e7c-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01e7c-155">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-155">-   eExitProcess</span></span><br /><span data-ttu-id="01e7c-156">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="01e7c-157">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01e7c-158">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01e7c-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01e7c-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="01e7c-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="01e7c-160">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01e7c-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01e7c-161">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-161">-   eExitProcess</span></span><br /><span data-ttu-id="01e7c-162">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="01e7c-163">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01e7c-164">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01e7c-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01e7c-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="01e7c-165">OPR_ProcessExit</span></span>|<span data-ttu-id="01e7c-166">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-166">-   eExitProcess</span></span><br /><span data-ttu-id="01e7c-167">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="01e7c-168">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01e7c-169">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01e7c-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="01e7c-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="01e7c-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="01e7c-171">-eNoAction</span><span class="sxs-lookup"><span data-stu-id="01e7c-171">-   eNoAction</span></span><br /><span data-ttu-id="01e7c-172">-   eAbortThread</span><span class="sxs-lookup"><span data-stu-id="01e7c-172">-   eAbortThread</span></span><br /><span data-ttu-id="01e7c-173">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="01e7c-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="01e7c-174">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01e7c-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="01e7c-175">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="01e7c-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="01e7c-176">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-176">-   eExitProcess</span></span><br /><span data-ttu-id="01e7c-177">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="01e7c-178">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="01e7c-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="01e7c-179">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="01e7c-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01e7c-180">必要条件</span><span class="sxs-lookup"><span data-stu-id="01e7c-180">Requirements</span></span>  
 <span data-ttu-id="01e7c-181">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01e7c-181">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01e7c-182">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01e7c-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01e7c-183">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="01e7c-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01e7c-184">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01e7c-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e7c-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="01e7c-185">See also</span></span>

- [<span data-ttu-id="01e7c-186">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="01e7c-186">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="01e7c-187">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="01e7c-187">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="01e7c-188">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01e7c-188">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
