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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b16cc6a899b1ad5c814c29a93c6125250ca8186d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133576"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="5170f-102">ICLRPolicyManager::SetTimeout メソッド</span><span class="sxs-lookup"><span data-stu-id="5170f-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="5170f-103">指定された操作のタイムアウト値を設定します。</span><span class="sxs-lookup"><span data-stu-id="5170f-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5170f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5170f-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5170f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5170f-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="5170f-106">[in]1 つ、 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)タイムアウトを設定する対象の共通言語ランタイム (CLR) 操作を示す値。</span><span class="sxs-lookup"><span data-stu-id="5170f-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="5170f-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5170f-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="5170f-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="5170f-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="5170f-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="5170f-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="5170f-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="5170f-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="5170f-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="5170f-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="5170f-112">[in]新しいタイムアウト値 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="5170f-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="5170f-113">無限の値により、操作がタイムアウトすることはありません。</span><span class="sxs-lookup"><span data-stu-id="5170f-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5170f-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="5170f-114">Return Value</span></span>  
  
|<span data-ttu-id="5170f-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5170f-115">HRESULT</span></span>|<span data-ttu-id="5170f-116">説明</span><span class="sxs-lookup"><span data-stu-id="5170f-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5170f-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="5170f-117">S_OK</span></span>|`SetTimeout` <span data-ttu-id="5170f-118">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="5170f-118">returned successfully.</span></span>|  
|<span data-ttu-id="5170f-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5170f-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5170f-120">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="5170f-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5170f-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5170f-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5170f-122">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="5170f-122">The call timed out.</span></span>|  
|<span data-ttu-id="5170f-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5170f-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5170f-124">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5170f-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5170f-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5170f-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5170f-126">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="5170f-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5170f-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5170f-127">E_FAIL</span></span>|<span data-ttu-id="5170f-128">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5170f-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5170f-129">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5170f-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5170f-130">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5170f-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5170f-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5170f-131">E_INVALIDARG</span></span>|<span data-ttu-id="5170f-132">タイムアウトを設定することはできません、指定された`operation`の無効な値が指定されているまたは`operation`します。</span><span class="sxs-lookup"><span data-stu-id="5170f-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5170f-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="5170f-133">Requirements</span></span>  
 <span data-ttu-id="5170f-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5170f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5170f-135">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5170f-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5170f-136">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5170f-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5170f-137">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="5170f-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5170f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="5170f-138">See also</span></span>

- [<span data-ttu-id="5170f-139">EClrOperation 列挙型</span><span class="sxs-lookup"><span data-stu-id="5170f-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="5170f-140">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5170f-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5170f-141">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5170f-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
