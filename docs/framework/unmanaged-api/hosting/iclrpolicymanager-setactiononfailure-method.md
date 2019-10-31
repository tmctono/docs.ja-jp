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
ms.openlocfilehash: 143052febe136e969987c35bc06f6c3b3356aedf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140779"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="7cf13-102">ICLRPolicyManager::SetActionOnFailure メソッド</span><span class="sxs-lookup"><span data-stu-id="7cf13-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="7cf13-103">指定したエラーが発生したときに共通言語ランタイム (CLR) が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7cf13-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf13-104">構文</span><span class="sxs-lookup"><span data-stu-id="7cf13-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cf13-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7cf13-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="7cf13-106">から[Eclrfailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)値の1つで、アクションを実行するエラーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="7cf13-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="7cf13-107">から[Epolicyaction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値の1つ。エラーが発生したときに実行するアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="7cf13-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="7cf13-108">サポートされている値の一覧については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cf13-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cf13-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7cf13-109">Return Value</span></span>  
  
|<span data-ttu-id="7cf13-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cf13-110">HRESULT</span></span>|<span data-ttu-id="7cf13-111">説明</span><span class="sxs-lookup"><span data-stu-id="7cf13-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7cf13-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cf13-112">S_OK</span></span>|<span data-ttu-id="7cf13-113">`SetActionOnFailure` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7cf13-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="7cf13-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7cf13-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7cf13-115">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="7cf13-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7cf13-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7cf13-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7cf13-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="7cf13-117">The call timed out.</span></span>|  
|<span data-ttu-id="7cf13-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7cf13-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7cf13-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7cf13-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7cf13-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7cf13-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7cf13-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="7cf13-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7cf13-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7cf13-122">E_FAIL</span></span>|<span data-ttu-id="7cf13-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7cf13-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7cf13-124">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7cf13-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7cf13-125">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7cf13-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7cf13-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7cf13-126">E_INVALIDARG</span></span>|<span data-ttu-id="7cf13-127">指定された操作に対してポリシーアクションを設定できないか、操作に無効なポリシーアクションが指定されました。</span><span class="sxs-lookup"><span data-stu-id="7cf13-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cf13-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="7cf13-128">Remarks</span></span>  
 <span data-ttu-id="7cf13-129">既定では、メモリなどのリソースの割り当てに失敗した場合、CLR は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="7cf13-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="7cf13-130">`SetActionOnFailure` では、エラー発生時に実行するポリシーアクションを指定することにより、ホストはこの動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="7cf13-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="7cf13-131">次の表は、サポートされている[Eclrfailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)値と[epolicyaction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値の組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="7cf13-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="7cf13-132">(FAIL_ プレフィックスは[Eclrfailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)値から省略されています)。</span><span class="sxs-lookup"><span data-stu-id="7cf13-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="7cf13-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="7cf13-133">NonCriticalResource</span></span>|<span data-ttu-id="7cf13-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="7cf13-134">CriticalResource</span></span>|<span data-ttu-id="7cf13-135">Fat (Alruntime)</span><span class="sxs-lookup"><span data-stu-id="7cf13-135">FatalRuntime</span></span>|<span data-ttu-id="7cf13-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="7cf13-136">OrphanedLock</span></span>|<span data-ttu-id="7cf13-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="7cf13-137">StackOverflow</span></span>|<span data-ttu-id="7cf13-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="7cf13-138">AccessViolation</span></span>|<span data-ttu-id="7cf13-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="7cf13-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="7cf13-140">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-140">X</span></span>|<span data-ttu-id="7cf13-141">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-141">X</span></span>||||<span data-ttu-id="7cf13-142">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-142">N/A</span></span>||  
|<span data-ttu-id="7cf13-143">の例外</span><span class="sxs-lookup"><span data-stu-id="7cf13-143">eThrowException</span></span>|<span data-ttu-id="7cf13-144">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-144">X</span></span>|<span data-ttu-id="7cf13-145">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-145">X</span></span>||||<span data-ttu-id="7cf13-146">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="7cf13-147">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-147">X</span></span>|<span data-ttu-id="7cf13-148">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-148">X</span></span>||||<span data-ttu-id="7cf13-149">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-149">N/A</span></span>|<span data-ttu-id="7cf13-150">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="7cf13-151">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-151">X</span></span>|<span data-ttu-id="7cf13-152">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-152">X</span></span>||||<span data-ttu-id="7cf13-153">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-153">N/A</span></span>|<span data-ttu-id="7cf13-154">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="7cf13-155">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-155">X</span></span>|<span data-ttu-id="7cf13-156">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-156">X</span></span>||<span data-ttu-id="7cf13-157">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-157">X</span></span>||<span data-ttu-id="7cf13-158">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-158">N/A</span></span>|<span data-ttu-id="7cf13-159">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="7cf13-160">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-160">X</span></span>|<span data-ttu-id="7cf13-161">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-161">X</span></span>||<span data-ttu-id="7cf13-162">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-162">X</span></span>|<span data-ttu-id="7cf13-163">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-163">X</span></span>|<span data-ttu-id="7cf13-164">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-164">N/A</span></span>|<span data-ttu-id="7cf13-165">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="7cf13-166">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-166">X</span></span>|<span data-ttu-id="7cf13-167">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-167">X</span></span>||<span data-ttu-id="7cf13-168">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-168">X</span></span>|<span data-ttu-id="7cf13-169">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-169">X</span></span>|<span data-ttu-id="7cf13-170">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-170">N/A</span></span>|<span data-ttu-id="7cf13-171">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-171">X</span></span>|  
|<span data-ttu-id="7cf13-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="7cf13-172">eFastExitProcess</span></span>|<span data-ttu-id="7cf13-173">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-173">X</span></span>|<span data-ttu-id="7cf13-174">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-174">X</span></span>||<span data-ttu-id="7cf13-175">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-175">X</span></span>|<span data-ttu-id="7cf13-176">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-176">X</span></span>|<span data-ttu-id="7cf13-177">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="7cf13-178">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-178">X</span></span>|<span data-ttu-id="7cf13-179">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-179">X</span></span>|<span data-ttu-id="7cf13-180">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-180">X</span></span>|<span data-ttu-id="7cf13-181">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-181">X</span></span>|<span data-ttu-id="7cf13-182">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-182">X</span></span>|<span data-ttu-id="7cf13-183">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="7cf13-184">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-184">X</span></span>|<span data-ttu-id="7cf13-185">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-185">X</span></span>|<span data-ttu-id="7cf13-186">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-186">X</span></span>|<span data-ttu-id="7cf13-187">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-187">X</span></span>|<span data-ttu-id="7cf13-188">x</span><span class="sxs-lookup"><span data-stu-id="7cf13-188">X</span></span>|<span data-ttu-id="7cf13-189">N/A</span><span class="sxs-lookup"><span data-stu-id="7cf13-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="7cf13-190">［要件］</span><span class="sxs-lookup"><span data-stu-id="7cf13-190">Requirements</span></span>  
 <span data-ttu-id="7cf13-191">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cf13-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf13-192">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7cf13-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7cf13-193">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7cf13-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cf13-194">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cf13-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf13-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cf13-195">See also</span></span>

- [<span data-ttu-id="7cf13-196">EClrFailure 列挙型</span><span class="sxs-lookup"><span data-stu-id="7cf13-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="7cf13-197">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="7cf13-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="7cf13-198">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7cf13-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="7cf13-199">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7cf13-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
