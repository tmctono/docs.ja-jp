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
ms.openlocfilehash: 33c790bf2721f09b263494e845356ef6b6712f99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177139"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="a6351-102">ICLRControl::GetCLRManager メソッド</span><span class="sxs-lookup"><span data-stu-id="a6351-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="a6351-103">ホストは、共通言語ランタイム (CLR) の構成に使用できる、マネージャーの種類のいずれかのインスタンスへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6351-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6351-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6351-104">Syntax</span></span>  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6351-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6351-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="a6351-106">[in]`IID`のマネージャーの種類を返します。</span><span class="sxs-lookup"><span data-stu-id="a6351-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="a6351-107">次`IID`値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a6351-107">The following `IID` values are supported.</span></span>  
  
-   <span data-ttu-id="a6351-108">IID_ICLRDebugManager:指定します`ppObject`型[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6351-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="a6351-109">IID_ICLRErrorReportingManager:指定します`ppObject`型[ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6351-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="a6351-110">IID_ICLRGCManager:指定します`ppObject`型[ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6351-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="a6351-111">IID_ICLRHostProtectionManager:指定します`ppObject`型[ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6351-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="a6351-112">IID_ICLROnEventManager:指定します`ppObject`型[ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6351-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="a6351-113">IID_ICLRPolicyManager:指定します`ppObject`型[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6351-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
-   <span data-ttu-id="a6351-114">IID_ICLRTaskManager: speciries を`ppObject`型[ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6351-114">IID_ICLRTaskManager: speciries that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="a6351-115">[out]要求マネージャーは、または null の場合、無効なマネージャーの種類が要求された場合にインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="a6351-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6351-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="a6351-116">Return Value</span></span>  
  
|<span data-ttu-id="a6351-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6351-117">HRESULT</span></span>|<span data-ttu-id="a6351-118">説明</span><span class="sxs-lookup"><span data-stu-id="a6351-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a6351-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6351-119">S_OK</span></span>|<span data-ttu-id="a6351-120">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="a6351-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="a6351-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a6351-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a6351-122">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="a6351-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a6351-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a6351-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a6351-124">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="a6351-124">The call timed out.</span></span>|  
|<span data-ttu-id="a6351-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a6351-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a6351-126">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="a6351-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a6351-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a6351-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a6351-128">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="a6351-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a6351-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a6351-129">E_FAIL</span></span>|<span data-ttu-id="a6351-130">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a6351-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a6351-131">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a6351-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a6351-132">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="a6351-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a6351-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="a6351-133">E_NOINTERFACE</span></span>|<span data-ttu-id="a6351-134">インターフェイスの種類がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a6351-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6351-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6351-135">Requirements</span></span>  
 <span data-ttu-id="a6351-136">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6351-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6351-137">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a6351-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6351-138">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a6351-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6351-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6351-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6351-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6351-140">See also</span></span>

- [<span data-ttu-id="a6351-141">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6351-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a6351-142">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6351-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
