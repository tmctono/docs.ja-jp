---
title: ICLRControl::GetCLRManager メソッド
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d97d75eb5fab396530a6f48314e96c8d47d06439
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64656481"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="e9c26-102">ICLRControl::GetCLRManager メソッド</span><span class="sxs-lookup"><span data-stu-id="e9c26-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="e9c26-103">ホストは、共通言語ランタイム (CLR) の構成に使用できる、マネージャーの種類のいずれかのインスタンスへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e9c26-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c26-104">構文</span><span class="sxs-lookup"><span data-stu-id="e9c26-104">Syntax</span></span>  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9c26-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9c26-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="e9c26-106">[in]`IID`のマネージャーの種類を返します。</span><span class="sxs-lookup"><span data-stu-id="e9c26-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="e9c26-107">次`IID`値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e9c26-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="e9c26-108">IID_ICLRDebugManager:指定します`ppObject`型[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9c26-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="e9c26-109">IID_ICLRErrorReportingManager:指定します`ppObject`型[ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9c26-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="e9c26-110">IID_ICLRGCManager:指定します`ppObject`型[ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9c26-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="e9c26-111">IID_ICLRHostProtectionManager:指定します`ppObject`型[ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9c26-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="e9c26-112">IID_ICLROnEventManager:指定します`ppObject`型[ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9c26-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="e9c26-113">IID_ICLRPolicyManager:指定します`ppObject`型[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9c26-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="e9c26-114">IID_ICLRTaskManager:指定します`ppObject`型[ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9c26-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="e9c26-115">[out]要求マネージャーは、または null の場合、無効なマネージャーの種類が要求された場合にインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="e9c26-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9c26-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="e9c26-116">Return Value</span></span>  
  
|<span data-ttu-id="e9c26-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9c26-117">HRESULT</span></span>|<span data-ttu-id="e9c26-118">説明</span><span class="sxs-lookup"><span data-stu-id="e9c26-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9c26-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9c26-119">S_OK</span></span>|<span data-ttu-id="e9c26-120">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e9c26-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="e9c26-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e9c26-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e9c26-122">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="e9c26-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e9c26-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e9c26-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e9c26-124">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="e9c26-124">The call timed out.</span></span>|  
|<span data-ttu-id="e9c26-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e9c26-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e9c26-126">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e9c26-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e9c26-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e9c26-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e9c26-128">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="e9c26-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e9c26-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e9c26-129">E_FAIL</span></span>|<span data-ttu-id="e9c26-130">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e9c26-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e9c26-131">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e9c26-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e9c26-132">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e9c26-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e9c26-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="e9c26-133">E_NOINTERFACE</span></span>|<span data-ttu-id="e9c26-134">インターフェイスの種類がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e9c26-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9c26-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="e9c26-135">Requirements</span></span>  
 <span data-ttu-id="e9c26-136">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9c26-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9c26-137">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9c26-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9c26-138">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e9c26-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9c26-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9c26-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c26-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9c26-140">See also</span></span>

- [<span data-ttu-id="e9c26-141">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e9c26-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e9c26-142">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e9c26-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
