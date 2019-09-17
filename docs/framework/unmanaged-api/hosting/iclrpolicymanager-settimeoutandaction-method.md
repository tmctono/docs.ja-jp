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
ms.openlocfilehash: 120dbfdc463a7441cce8ca7d87561998a8e28eda
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916961"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="5e60c-102">ICLRPolicyManager::SetTimeoutAndAction メソッド</span><span class="sxs-lookup"><span data-stu-id="5e60c-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="5e60c-103">指定された操作のタイムアウト値を設定し、操作が発生したときに共通言語ランタイム (CLR) が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e60c-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e60c-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e60c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e60c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e60c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="5e60c-106">からタイムアウトとポリシー `action`を設定する操作を示す [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 値の1つ。</span><span class="sxs-lookup"><span data-stu-id="5e60c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="5e60c-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5e60c-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="5e60c-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="5e60c-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="5e60c-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="5e60c-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="5e60c-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="5e60c-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="5e60c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="5e60c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="5e60c-112">から新しいタイムアウト値 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="5e60c-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="5e60c-113">値が無限である`operation`と、タイムアウトしません。</span><span class="sxs-lookup"><span data-stu-id="5e60c-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="5e60c-114">から[Epolicyaction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)値の1つ。 CLR が発生したとき`operation`に実行するポリシーアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="5e60c-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e60c-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="5e60c-115">Return Value</span></span>  
  
|<span data-ttu-id="5e60c-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e60c-116">HRESULT</span></span>|<span data-ttu-id="5e60c-117">説明</span><span class="sxs-lookup"><span data-stu-id="5e60c-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e60c-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e60c-118">S_OK</span></span>|<span data-ttu-id="5e60c-119">`SetTimeoutAndAction`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="5e60c-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="5e60c-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e60c-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e60c-121">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="5e60c-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e60c-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e60c-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e60c-123">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="5e60c-123">The call timed out.</span></span>|  
|<span data-ttu-id="5e60c-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e60c-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e60c-125">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5e60c-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e60c-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e60c-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e60c-127">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5e60c-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e60c-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e60c-128">E_FAIL</span></span>|<span data-ttu-id="5e60c-129">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5e60c-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e60c-130">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5e60c-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e60c-131">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5e60c-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5e60c-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5e60c-132">E_INVALIDARG</span></span>|<span data-ttu-id="5e60c-133">指定され`operation`たに対してタイムアウトを設定できないか、に`action`無効な値が指定されました。</span><span class="sxs-lookup"><span data-stu-id="5e60c-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e60c-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e60c-134">Remarks</span></span>  
 <span data-ttu-id="5e60c-135">`SetTimeoutAndAction`[ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)メソッドと[ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)メソッドの機能をカプセル化し、これら2つのメソッドの順次呼び出しの代わりに呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5e60c-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5e60c-136">すべてのポリシーアクション値は、CLR 操作のタイムアウト動作として指定できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5e60c-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="5e60c-137">有効な値については、これら2つの方法に関するトピックの「解説」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e60c-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e60c-138">必要条件</span><span class="sxs-lookup"><span data-stu-id="5e60c-138">Requirements</span></span>  
 <span data-ttu-id="5e60c-139">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e60c-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e60c-140">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5e60c-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e60c-141">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5e60c-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e60c-142">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e60c-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e60c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e60c-143">See also</span></span>

- [<span data-ttu-id="5e60c-144">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="5e60c-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="5e60c-145">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="5e60c-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="5e60c-146">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e60c-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="5e60c-147">SetActionOnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="5e60c-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="5e60c-148">ICLRPolicyManager:: SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="5e60c-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
