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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117431"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="0da21-102">ICLRPolicyManager::SetActionOnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="0da21-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="0da21-103">共通言語ランタイム (CLR) が指定したエラーが発生したときに実行する必要がありますポリシーのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="0da21-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da21-104">構文</span><span class="sxs-lookup"><span data-stu-id="0da21-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da21-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0da21-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="0da21-106">[in]1 つ、 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)アクションを実行する対象のエラーの種類を示す値。</span><span class="sxs-lookup"><span data-stu-id="0da21-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="0da21-107">[in]1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)障害が発生したときに実行されるアクションを示す値。</span><span class="sxs-lookup"><span data-stu-id="0da21-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="0da21-108">サポートされている値の一覧は、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0da21-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0da21-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="0da21-109">Return Value</span></span>  
  
|<span data-ttu-id="0da21-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0da21-110">HRESULT</span></span>|<span data-ttu-id="0da21-111">説明</span><span class="sxs-lookup"><span data-stu-id="0da21-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0da21-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0da21-112">S_OK</span></span>|`SetActionOnFailure` <span data-ttu-id="0da21-113">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="0da21-113">returned successfully.</span></span>|  
|<span data-ttu-id="0da21-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0da21-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0da21-115">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="0da21-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0da21-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0da21-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0da21-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="0da21-117">The call timed out.</span></span>|  
|<span data-ttu-id="0da21-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0da21-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0da21-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0da21-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0da21-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0da21-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0da21-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="0da21-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0da21-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0da21-122">E_FAIL</span></span>|<span data-ttu-id="0da21-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0da21-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0da21-124">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0da21-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0da21-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0da21-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0da21-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0da21-126">E_INVALIDARG</span></span>|<span data-ttu-id="0da21-127">指定された操作のポリシーのアクションを設定することはできませんまたは操作に無効なポリシー アクションが指定されました。</span><span class="sxs-lookup"><span data-stu-id="0da21-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0da21-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="0da21-128">Remarks</span></span>  
 <span data-ttu-id="0da21-129">既定では、CLR は、メモリなどのリソースの割り当てに失敗した場合に例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="0da21-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> `SetActionOnFailure` <span data-ttu-id="0da21-130">により、ホストは、障害発生時に実行するポリシーのアクションを指定することでこの動作をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="0da21-130">allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="0da21-131">次の表は、組み合わせの[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)と[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)サポートされている値。</span><span class="sxs-lookup"><span data-stu-id="0da21-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="0da21-132">(から FAIL_ プレフィックスを省略すると[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)値)。</span><span class="sxs-lookup"><span data-stu-id="0da21-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="0da21-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="0da21-133">NonCriticalResource</span></span>|<span data-ttu-id="0da21-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="0da21-134">CriticalResource</span></span>|<span data-ttu-id="0da21-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="0da21-135">FatalRuntime</span></span>|<span data-ttu-id="0da21-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="0da21-136">OrphanedLock</span></span>|<span data-ttu-id="0da21-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="0da21-137">StackOverflow</span></span>|<span data-ttu-id="0da21-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="0da21-138">AccessViolation</span></span>|<span data-ttu-id="0da21-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="0da21-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="0da21-140">x</span><span class="sxs-lookup"><span data-stu-id="0da21-140">X</span></span>|<span data-ttu-id="0da21-141">x</span><span class="sxs-lookup"><span data-stu-id="0da21-141">X</span></span>||||<span data-ttu-id="0da21-142">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-142">N/A</span></span>||  
|<span data-ttu-id="0da21-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="0da21-143">eThrowException</span></span>|<span data-ttu-id="0da21-144">x</span><span class="sxs-lookup"><span data-stu-id="0da21-144">X</span></span>|<span data-ttu-id="0da21-145">x</span><span class="sxs-lookup"><span data-stu-id="0da21-145">X</span></span>||||<span data-ttu-id="0da21-146">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="0da21-147">x</span><span class="sxs-lookup"><span data-stu-id="0da21-147">X</span></span>|<span data-ttu-id="0da21-148">x</span><span class="sxs-lookup"><span data-stu-id="0da21-148">X</span></span>||||<span data-ttu-id="0da21-149">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-149">N/A</span></span>|<span data-ttu-id="0da21-150">x</span><span class="sxs-lookup"><span data-stu-id="0da21-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="0da21-151">x</span><span class="sxs-lookup"><span data-stu-id="0da21-151">X</span></span>|<span data-ttu-id="0da21-152">x</span><span class="sxs-lookup"><span data-stu-id="0da21-152">X</span></span>||||<span data-ttu-id="0da21-153">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-153">N/A</span></span>|<span data-ttu-id="0da21-154">x</span><span class="sxs-lookup"><span data-stu-id="0da21-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="0da21-155">x</span><span class="sxs-lookup"><span data-stu-id="0da21-155">X</span></span>|<span data-ttu-id="0da21-156">x</span><span class="sxs-lookup"><span data-stu-id="0da21-156">X</span></span>||<span data-ttu-id="0da21-157">x</span><span class="sxs-lookup"><span data-stu-id="0da21-157">X</span></span>||<span data-ttu-id="0da21-158">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-158">N/A</span></span>|<span data-ttu-id="0da21-159">x</span><span class="sxs-lookup"><span data-stu-id="0da21-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="0da21-160">x</span><span class="sxs-lookup"><span data-stu-id="0da21-160">X</span></span>|<span data-ttu-id="0da21-161">x</span><span class="sxs-lookup"><span data-stu-id="0da21-161">X</span></span>||<span data-ttu-id="0da21-162">x</span><span class="sxs-lookup"><span data-stu-id="0da21-162">X</span></span>|<span data-ttu-id="0da21-163">x</span><span class="sxs-lookup"><span data-stu-id="0da21-163">X</span></span>|<span data-ttu-id="0da21-164">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-164">N/A</span></span>|<span data-ttu-id="0da21-165">x</span><span class="sxs-lookup"><span data-stu-id="0da21-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="0da21-166">x</span><span class="sxs-lookup"><span data-stu-id="0da21-166">X</span></span>|<span data-ttu-id="0da21-167">x</span><span class="sxs-lookup"><span data-stu-id="0da21-167">X</span></span>||<span data-ttu-id="0da21-168">x</span><span class="sxs-lookup"><span data-stu-id="0da21-168">X</span></span>|<span data-ttu-id="0da21-169">x</span><span class="sxs-lookup"><span data-stu-id="0da21-169">X</span></span>|<span data-ttu-id="0da21-170">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-170">N/A</span></span>|<span data-ttu-id="0da21-171">x</span><span class="sxs-lookup"><span data-stu-id="0da21-171">X</span></span>|  
|<span data-ttu-id="0da21-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="0da21-172">eFastExitProcess</span></span>|<span data-ttu-id="0da21-173">x</span><span class="sxs-lookup"><span data-stu-id="0da21-173">X</span></span>|<span data-ttu-id="0da21-174">x</span><span class="sxs-lookup"><span data-stu-id="0da21-174">X</span></span>||<span data-ttu-id="0da21-175">x</span><span class="sxs-lookup"><span data-stu-id="0da21-175">X</span></span>|<span data-ttu-id="0da21-176">x</span><span class="sxs-lookup"><span data-stu-id="0da21-176">X</span></span>|<span data-ttu-id="0da21-177">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="0da21-178">x</span><span class="sxs-lookup"><span data-stu-id="0da21-178">X</span></span>|<span data-ttu-id="0da21-179">x</span><span class="sxs-lookup"><span data-stu-id="0da21-179">X</span></span>|<span data-ttu-id="0da21-180">x</span><span class="sxs-lookup"><span data-stu-id="0da21-180">X</span></span>|<span data-ttu-id="0da21-181">x</span><span class="sxs-lookup"><span data-stu-id="0da21-181">X</span></span>|<span data-ttu-id="0da21-182">x</span><span class="sxs-lookup"><span data-stu-id="0da21-182">X</span></span>|<span data-ttu-id="0da21-183">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="0da21-184">x</span><span class="sxs-lookup"><span data-stu-id="0da21-184">X</span></span>|<span data-ttu-id="0da21-185">x</span><span class="sxs-lookup"><span data-stu-id="0da21-185">X</span></span>|<span data-ttu-id="0da21-186">x</span><span class="sxs-lookup"><span data-stu-id="0da21-186">X</span></span>|<span data-ttu-id="0da21-187">x</span><span class="sxs-lookup"><span data-stu-id="0da21-187">X</span></span>|<span data-ttu-id="0da21-188">x</span><span class="sxs-lookup"><span data-stu-id="0da21-188">X</span></span>|<span data-ttu-id="0da21-189">N/A</span><span class="sxs-lookup"><span data-stu-id="0da21-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="0da21-190">必要条件</span><span class="sxs-lookup"><span data-stu-id="0da21-190">Requirements</span></span>  
 <span data-ttu-id="0da21-191">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0da21-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da21-192">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0da21-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0da21-193">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0da21-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0da21-194">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0da21-194">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0da21-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="0da21-195">See also</span></span>

- [<span data-ttu-id="0da21-196">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="0da21-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="0da21-197">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="0da21-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="0da21-198">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0da21-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0da21-199">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0da21-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
