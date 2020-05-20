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
ms.openlocfilehash: c0d8b66c8b85710b0365bfc410188c81431720ff
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703440"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="2d3fa-102">ICLRPolicyManager::SetDefaultAction メソッド</span><span class="sxs-lookup"><span data-stu-id="2d3fa-102">ICLRPolicyManager::SetDefaultAction Method</span></span>
<span data-ttu-id="2d3fa-103">指定された操作が発生したときに共通言語ランタイム (CLR) が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d3fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d3fa-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d3fa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d3fa-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="2d3fa-106">から[EClrOperation](eclroperation-enumeration.md)値の1つ。 CLR 動作をカスタマイズする必要があるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="2d3fa-107">から[Epolicyaction](epolicyaction-enumeration.md)値の1つ。 CLR が発生したときに実行するポリシーアクションを示し `operation` ます。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d3fa-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2d3fa-108">Return Value</span></span>  
  
|<span data-ttu-id="2d3fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d3fa-109">HRESULT</span></span>|<span data-ttu-id="2d3fa-110">説明</span><span class="sxs-lookup"><span data-stu-id="2d3fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d3fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d3fa-111">S_OK</span></span>|<span data-ttu-id="2d3fa-112">`SetDefaultAction`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="2d3fa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d3fa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d3fa-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d3fa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d3fa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d3fa-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-116">The call timed out.</span></span>|  
|<span data-ttu-id="2d3fa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d3fa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d3fa-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d3fa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d3fa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d3fa-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d3fa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d3fa-121">E_FAIL</span></span>|<span data-ttu-id="2d3fa-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d3fa-123">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d3fa-124">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2d3fa-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2d3fa-125">E_INVALIDARG</span></span>|<span data-ttu-id="2d3fa-126">に対して無効なが指定された `action` `operation` か、またはに無効な値が指定されました `operation` 。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d3fa-127">解説</span><span class="sxs-lookup"><span data-stu-id="2d3fa-127">Remarks</span></span>  
 <span data-ttu-id="2d3fa-128">すべてのポリシーアクション値を、CLR 操作の既定の動作として指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="2d3fa-129">`SetDefaultAction`通常は、動作をエスカレートするためにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="2d3fa-130">たとえば、ホストは、スレッドの中止をルースレッドの中止に変換するように指定できますが、逆のを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="2d3fa-131">次の表は、 `action` 使用可能な各値の有効な値を示して `operation` います。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="2d3fa-132">の値`operation`</span><span class="sxs-lookup"><span data-stu-id="2d3fa-132">Value for `operation`</span></span>|<span data-ttu-id="2d3fa-133">`action` の有効な値</span><span class="sxs-lookup"><span data-stu-id="2d3fa-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="2d3fa-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="2d3fa-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="2d3fa-135">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="2d3fa-135">-   eAbortThread</span></span><br /><span data-ttu-id="2d3fa-136">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="2d3fa-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="2d3fa-137">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3fa-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="2d3fa-138">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3fa-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="2d3fa-139">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-139">-   eExitProcess</span></span><br /><span data-ttu-id="2d3fa-140">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="2d3fa-141">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="2d3fa-142">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="2d3fa-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="2d3fa-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="2d3fa-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="2d3fa-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="2d3fa-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="2d3fa-145">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="2d3fa-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="2d3fa-146">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3fa-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="2d3fa-147">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3fa-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="2d3fa-148">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-148">-   eExitProcess</span></span><br /><span data-ttu-id="2d3fa-149">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="2d3fa-150">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="2d3fa-151">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="2d3fa-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="2d3fa-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="2d3fa-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="2d3fa-153">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3fa-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="2d3fa-154">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3fa-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="2d3fa-155">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-155">-   eExitProcess</span></span><br /><span data-ttu-id="2d3fa-156">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="2d3fa-157">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="2d3fa-158">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="2d3fa-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="2d3fa-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="2d3fa-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="2d3fa-160">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3fa-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="2d3fa-161">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-161">-   eExitProcess</span></span><br /><span data-ttu-id="2d3fa-162">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="2d3fa-163">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="2d3fa-164">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="2d3fa-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="2d3fa-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="2d3fa-165">OPR_ProcessExit</span></span>|<span data-ttu-id="2d3fa-166">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-166">-   eExitProcess</span></span><br /><span data-ttu-id="2d3fa-167">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="2d3fa-168">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="2d3fa-169">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="2d3fa-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="2d3fa-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="2d3fa-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="2d3fa-171">-"-" アクション</span><span class="sxs-lookup"><span data-stu-id="2d3fa-171">-   eNoAction</span></span><br /><span data-ttu-id="2d3fa-172">-eAbortThread</span><span class="sxs-lookup"><span data-stu-id="2d3fa-172">-   eAbortThread</span></span><br /><span data-ttu-id="2d3fa-173">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="2d3fa-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="2d3fa-174">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3fa-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="2d3fa-175">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2d3fa-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="2d3fa-176">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-176">-   eExitProcess</span></span><br /><span data-ttu-id="2d3fa-177">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="2d3fa-178">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="2d3fa-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="2d3fa-179">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="2d3fa-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d3fa-180">要件</span><span class="sxs-lookup"><span data-stu-id="2d3fa-180">Requirements</span></span>  
 <span data-ttu-id="2d3fa-181">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d3fa-181">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d3fa-182">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2d3fa-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d3fa-183">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2d3fa-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d3fa-184">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d3fa-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3fa-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d3fa-185">See also</span></span>

- [<span data-ttu-id="2d3fa-186">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="2d3fa-186">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="2d3fa-187">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="2d3fa-187">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="2d3fa-188">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d3fa-188">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
