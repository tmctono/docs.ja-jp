---
title: ICLRPolicyManager::SetTimeout メソッド
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
ms.openlocfilehash: 516ba1325404e757af8e38de239864b21b1640f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140747"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="071d1-102">ICLRPolicyManager::SetTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="071d1-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="071d1-103">指定された操作のタイムアウト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="071d1-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="071d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="071d1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="071d1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="071d1-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="071d1-106">からタイムアウトを設定する共通言語ランタイム (CLR) 操作を示す[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)値の1つ。</span><span class="sxs-lookup"><span data-stu-id="071d1-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="071d1-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="071d1-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="071d1-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="071d1-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="071d1-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="071d1-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="071d1-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="071d1-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="071d1-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="071d1-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="071d1-112">から新しいタイムアウト値 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="071d1-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="071d1-113">値を無限にすると、操作はタイムアウトしません。</span><span class="sxs-lookup"><span data-stu-id="071d1-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="071d1-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="071d1-114">Return Value</span></span>  
  
|<span data-ttu-id="071d1-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="071d1-115">HRESULT</span></span>|<span data-ttu-id="071d1-116">説明</span><span class="sxs-lookup"><span data-stu-id="071d1-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="071d1-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="071d1-117">S_OK</span></span>|<span data-ttu-id="071d1-118">`SetTimeout` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="071d1-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="071d1-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="071d1-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="071d1-120">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="071d1-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="071d1-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="071d1-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="071d1-122">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="071d1-122">The call timed out.</span></span>|  
|<span data-ttu-id="071d1-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="071d1-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="071d1-124">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="071d1-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="071d1-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="071d1-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="071d1-126">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="071d1-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="071d1-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="071d1-127">E_FAIL</span></span>|<span data-ttu-id="071d1-128">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="071d1-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="071d1-129">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="071d1-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="071d1-130">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="071d1-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="071d1-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="071d1-131">E_INVALIDARG</span></span>|<span data-ttu-id="071d1-132">指定された `operation`にタイムアウトを設定できないか、`operation`に無効な値が指定されました。</span><span class="sxs-lookup"><span data-stu-id="071d1-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="071d1-133">［要件］</span><span class="sxs-lookup"><span data-stu-id="071d1-133">Requirements</span></span>  
 <span data-ttu-id="071d1-134">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="071d1-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="071d1-135">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="071d1-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="071d1-136">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="071d1-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="071d1-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="071d1-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="071d1-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="071d1-138">See also</span></span>

- [<span data-ttu-id="071d1-139">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="071d1-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="071d1-140">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="071d1-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="071d1-141">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="071d1-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
