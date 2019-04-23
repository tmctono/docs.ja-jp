---
title: ICLRPolicyManager::SetActionOnFailure メソッド
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34d9e1a3747ecf3dffc925d7883599b773dd51f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117431"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="30c85-102">ICLRPolicyManager::SetActionOnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="30c85-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="30c85-103">共通言語ランタイム (CLR) が指定したエラーが発生したときに実行する必要がありますポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="30c85-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c85-104">構文</span><span class="sxs-lookup"><span data-stu-id="30c85-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30c85-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30c85-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="30c85-106">[in]1 つ、 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)アクションを実行する対象のエラーの種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="30c85-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="30c85-107">[in]1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)障害が発生したときに実行されるアクションを示す値。</span><span class="sxs-lookup"><span data-stu-id="30c85-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="30c85-108">サポートされている値の一覧は、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c85-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30c85-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="30c85-109">Return Value</span></span>  
  
|<span data-ttu-id="30c85-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30c85-110">HRESULT</span></span>|<span data-ttu-id="30c85-111">説明</span><span class="sxs-lookup"><span data-stu-id="30c85-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30c85-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="30c85-112">S_OK</span></span>|<span data-ttu-id="30c85-113">`SetActionOnFailure` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="30c85-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="30c85-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30c85-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30c85-115">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="30c85-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30c85-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30c85-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30c85-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="30c85-117">The call timed out.</span></span>|  
|<span data-ttu-id="30c85-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30c85-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30c85-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="30c85-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30c85-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30c85-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30c85-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="30c85-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30c85-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30c85-122">E_FAIL</span></span>|<span data-ttu-id="30c85-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="30c85-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30c85-124">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="30c85-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30c85-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="30c85-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="30c85-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="30c85-126">E_INVALIDARG</span></span>|<span data-ttu-id="30c85-127">指定された操作のポリシーのアクションを設定することはできませんまたは操作に無効なポリシー アクションが指定されました。</span><span class="sxs-lookup"><span data-stu-id="30c85-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30c85-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="30c85-128">Remarks</span></span>  
 <span data-ttu-id="30c85-129">既定では、CLR は、メモリなどのリソースの割り当てに失敗した場合に例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="30c85-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="30c85-130">`SetActionOnFailure` により、ホストは、障害発生時に実行するポリシーのアクションを指定することでこの動作をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="30c85-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="30c85-131">次の表は、組み合わせの[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)と[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)サポートされている値。</span><span class="sxs-lookup"><span data-stu-id="30c85-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="30c85-132">(から FAIL_ プレフィックスを省略すると[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)値)。</span><span class="sxs-lookup"><span data-stu-id="30c85-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="30c85-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="30c85-133">NonCriticalResource</span></span>|<span data-ttu-id="30c85-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="30c85-134">CriticalResource</span></span>|<span data-ttu-id="30c85-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="30c85-135">FatalRuntime</span></span>|<span data-ttu-id="30c85-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="30c85-136">OrphanedLock</span></span>|<span data-ttu-id="30c85-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="30c85-137">StackOverflow</span></span>|<span data-ttu-id="30c85-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="30c85-138">AccessViolation</span></span>|<span data-ttu-id="30c85-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="30c85-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="30c85-140">x</span><span class="sxs-lookup"><span data-stu-id="30c85-140">X</span></span>|<span data-ttu-id="30c85-141">x</span><span class="sxs-lookup"><span data-stu-id="30c85-141">X</span></span>||||<span data-ttu-id="30c85-142">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-142">N/A</span></span>||  
|<span data-ttu-id="30c85-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="30c85-143">eThrowException</span></span>|<span data-ttu-id="30c85-144">x</span><span class="sxs-lookup"><span data-stu-id="30c85-144">X</span></span>|<span data-ttu-id="30c85-145">x</span><span class="sxs-lookup"><span data-stu-id="30c85-145">X</span></span>||||<span data-ttu-id="30c85-146">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="30c85-147">x</span><span class="sxs-lookup"><span data-stu-id="30c85-147">X</span></span>|<span data-ttu-id="30c85-148">x</span><span class="sxs-lookup"><span data-stu-id="30c85-148">X</span></span>||||<span data-ttu-id="30c85-149">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-149">N/A</span></span>|<span data-ttu-id="30c85-150">x</span><span class="sxs-lookup"><span data-stu-id="30c85-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="30c85-151">x</span><span class="sxs-lookup"><span data-stu-id="30c85-151">X</span></span>|<span data-ttu-id="30c85-152">x</span><span class="sxs-lookup"><span data-stu-id="30c85-152">X</span></span>||||<span data-ttu-id="30c85-153">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-153">N/A</span></span>|<span data-ttu-id="30c85-154">x</span><span class="sxs-lookup"><span data-stu-id="30c85-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="30c85-155">x</span><span class="sxs-lookup"><span data-stu-id="30c85-155">X</span></span>|<span data-ttu-id="30c85-156">x</span><span class="sxs-lookup"><span data-stu-id="30c85-156">X</span></span>||<span data-ttu-id="30c85-157">x</span><span class="sxs-lookup"><span data-stu-id="30c85-157">X</span></span>||<span data-ttu-id="30c85-158">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-158">N/A</span></span>|<span data-ttu-id="30c85-159">x</span><span class="sxs-lookup"><span data-stu-id="30c85-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="30c85-160">x</span><span class="sxs-lookup"><span data-stu-id="30c85-160">X</span></span>|<span data-ttu-id="30c85-161">x</span><span class="sxs-lookup"><span data-stu-id="30c85-161">X</span></span>||<span data-ttu-id="30c85-162">x</span><span class="sxs-lookup"><span data-stu-id="30c85-162">X</span></span>|<span data-ttu-id="30c85-163">x</span><span class="sxs-lookup"><span data-stu-id="30c85-163">X</span></span>|<span data-ttu-id="30c85-164">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-164">N/A</span></span>|<span data-ttu-id="30c85-165">x</span><span class="sxs-lookup"><span data-stu-id="30c85-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="30c85-166">x</span><span class="sxs-lookup"><span data-stu-id="30c85-166">X</span></span>|<span data-ttu-id="30c85-167">x</span><span class="sxs-lookup"><span data-stu-id="30c85-167">X</span></span>||<span data-ttu-id="30c85-168">x</span><span class="sxs-lookup"><span data-stu-id="30c85-168">X</span></span>|<span data-ttu-id="30c85-169">x</span><span class="sxs-lookup"><span data-stu-id="30c85-169">X</span></span>|<span data-ttu-id="30c85-170">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-170">N/A</span></span>|<span data-ttu-id="30c85-171">x</span><span class="sxs-lookup"><span data-stu-id="30c85-171">X</span></span>|  
|<span data-ttu-id="30c85-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="30c85-172">eFastExitProcess</span></span>|<span data-ttu-id="30c85-173">x</span><span class="sxs-lookup"><span data-stu-id="30c85-173">X</span></span>|<span data-ttu-id="30c85-174">x</span><span class="sxs-lookup"><span data-stu-id="30c85-174">X</span></span>||<span data-ttu-id="30c85-175">x</span><span class="sxs-lookup"><span data-stu-id="30c85-175">X</span></span>|<span data-ttu-id="30c85-176">x</span><span class="sxs-lookup"><span data-stu-id="30c85-176">X</span></span>|<span data-ttu-id="30c85-177">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="30c85-178">x</span><span class="sxs-lookup"><span data-stu-id="30c85-178">X</span></span>|<span data-ttu-id="30c85-179">x</span><span class="sxs-lookup"><span data-stu-id="30c85-179">X</span></span>|<span data-ttu-id="30c85-180">x</span><span class="sxs-lookup"><span data-stu-id="30c85-180">X</span></span>|<span data-ttu-id="30c85-181">x</span><span class="sxs-lookup"><span data-stu-id="30c85-181">X</span></span>|<span data-ttu-id="30c85-182">x</span><span class="sxs-lookup"><span data-stu-id="30c85-182">X</span></span>|<span data-ttu-id="30c85-183">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="30c85-184">x</span><span class="sxs-lookup"><span data-stu-id="30c85-184">X</span></span>|<span data-ttu-id="30c85-185">x</span><span class="sxs-lookup"><span data-stu-id="30c85-185">X</span></span>|<span data-ttu-id="30c85-186">x</span><span class="sxs-lookup"><span data-stu-id="30c85-186">X</span></span>|<span data-ttu-id="30c85-187">x</span><span class="sxs-lookup"><span data-stu-id="30c85-187">X</span></span>|<span data-ttu-id="30c85-188">x</span><span class="sxs-lookup"><span data-stu-id="30c85-188">X</span></span>|<span data-ttu-id="30c85-189">N/A</span><span class="sxs-lookup"><span data-stu-id="30c85-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="30c85-190">必要条件</span><span class="sxs-lookup"><span data-stu-id="30c85-190">Requirements</span></span>  
 <span data-ttu-id="30c85-191">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c85-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30c85-192">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30c85-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30c85-193">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="30c85-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30c85-194">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30c85-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c85-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="30c85-195">See also</span></span>

- [<span data-ttu-id="30c85-196">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="30c85-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="30c85-197">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="30c85-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="30c85-198">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30c85-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="30c85-199">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30c85-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
