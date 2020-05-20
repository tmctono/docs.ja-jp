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
ms.openlocfilehash: efd30ef04c148d5e098110efcb37e50f143884e4
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703427"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="fe40c-102">ICLRPolicyManager::SetTimeoutAndAction メソッド</span><span class="sxs-lookup"><span data-stu-id="fe40c-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="fe40c-103">指定された操作のタイムアウト値を設定し、操作が発生したときに共通言語ランタイム (CLR) が実行するポリシーアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe40c-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe40c-104">構文</span><span class="sxs-lookup"><span data-stu-id="fe40c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe40c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe40c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="fe40c-106">からタイムアウトとポリシーを設定する操作を示す[EClrOperation](eclroperation-enumeration.md)値の1つ `action` 。</span><span class="sxs-lookup"><span data-stu-id="fe40c-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="fe40c-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fe40c-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="fe40c-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="fe40c-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="fe40c-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="fe40c-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="fe40c-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="fe40c-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="fe40c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="fe40c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="fe40c-112">から新しいタイムアウト値 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="fe40c-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="fe40c-113">値が無限であると、 `operation` タイムアウトしません。</span><span class="sxs-lookup"><span data-stu-id="fe40c-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="fe40c-114">から[Epolicyaction](epolicyaction-enumeration.md)値の1つ。 CLR が発生したときに実行するポリシーアクションを示し `operation` ます。</span><span class="sxs-lookup"><span data-stu-id="fe40c-114">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe40c-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="fe40c-115">Return Value</span></span>  
  
|<span data-ttu-id="fe40c-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe40c-116">HRESULT</span></span>|<span data-ttu-id="fe40c-117">説明</span><span class="sxs-lookup"><span data-stu-id="fe40c-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe40c-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe40c-118">S_OK</span></span>|<span data-ttu-id="fe40c-119">`SetTimeoutAndAction`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="fe40c-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="fe40c-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe40c-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe40c-121">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="fe40c-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe40c-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe40c-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe40c-123">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="fe40c-123">The call timed out.</span></span>|  
|<span data-ttu-id="fe40c-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe40c-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe40c-125">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="fe40c-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe40c-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe40c-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe40c-127">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="fe40c-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe40c-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe40c-128">E_FAIL</span></span>|<span data-ttu-id="fe40c-129">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fe40c-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe40c-130">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="fe40c-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe40c-131">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fe40c-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fe40c-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fe40c-132">E_INVALIDARG</span></span>|<span data-ttu-id="fe40c-133">指定されたに対してタイムアウトを設定できない `operation` か、に無効な値が指定されました `action` 。</span><span class="sxs-lookup"><span data-stu-id="fe40c-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe40c-134">解説</span><span class="sxs-lookup"><span data-stu-id="fe40c-134">Remarks</span></span>  
 <span data-ttu-id="fe40c-135">`SetTimeoutAndAction`[ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)メソッドと[ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md)メソッドの機能をカプセル化し、これら2つのメソッドの順次呼び出しの代わりに呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fe40c-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fe40c-136">すべてのポリシーアクション値は、CLR 操作のタイムアウト動作として指定できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fe40c-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="fe40c-137">有効な値については、これら2つの方法に関するトピックの「解説」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe40c-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe40c-138">要件</span><span class="sxs-lookup"><span data-stu-id="fe40c-138">Requirements</span></span>  
 <span data-ttu-id="fe40c-139">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe40c-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe40c-140">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fe40c-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe40c-141">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="fe40c-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe40c-142">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe40c-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe40c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe40c-143">See also</span></span>

- [<span data-ttu-id="fe40c-144">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="fe40c-144">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="fe40c-145">EPolicyAction 列挙型</span><span class="sxs-lookup"><span data-stu-id="fe40c-145">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="fe40c-146">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe40c-146">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="fe40c-147">SetActionOnTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="fe40c-147">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="fe40c-148">ICLRPolicyManager:: SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="fe40c-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](iclrpolicymanager-settimeoutandaction-method.md)
