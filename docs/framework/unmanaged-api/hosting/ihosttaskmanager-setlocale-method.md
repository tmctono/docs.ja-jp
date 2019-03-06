---
title: IHostTaskManager::SetLocale メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77f0196e667e2d7bb148c07218a7e39f52a37809
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474317"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="2236e-102">IHostTaskManager::SetLocale メソッド</span><span class="sxs-lookup"><span data-stu-id="2236e-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="2236e-103">ロケール、またはカルチャは、現在実行中のタスクに共通言語ランタイム (CLR) が変更されたことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="2236e-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2236e-104">構文</span><span class="sxs-lookup"><span data-stu-id="2236e-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2236e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2236e-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="2236e-106">[in]新しく割り当てられた地理的なカルチャおよび言語に対応するロケール識別子の値。</span><span class="sxs-lookup"><span data-stu-id="2236e-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2236e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2236e-107">Return Value</span></span>  
  
|<span data-ttu-id="2236e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2236e-108">HRESULT</span></span>|<span data-ttu-id="2236e-109">説明</span><span class="sxs-lookup"><span data-stu-id="2236e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2236e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2236e-110">S_OK</span></span>|<span data-ttu-id="2236e-111">`SetLocale` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="2236e-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="2236e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2236e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2236e-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="2236e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2236e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2236e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2236e-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="2236e-115">The call timed out.</span></span>|  
|<span data-ttu-id="2236e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2236e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2236e-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2236e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2236e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2236e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2236e-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="2236e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2236e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2236e-120">E_FAIL</span></span>|<span data-ttu-id="2236e-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2236e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2236e-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2236e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2236e-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2236e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2236e-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2236e-124">E_NOTIMPL</span></span>|<span data-ttu-id="2236e-125">ホストには、ロケールを変更するマネージ ユーザー コードはできません。</span><span class="sxs-lookup"><span data-stu-id="2236e-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2236e-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="2236e-126">Remarks</span></span>  
 <span data-ttu-id="2236e-127">ランタイム呼び出し`SetLocale`ときの値、<xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>マネージ コードでプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="2236e-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="2236e-128">このメソッドは、ロケールの同期のための機構があればそれを実行するホストの機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="2236e-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="2236e-129">ホストは、ロケールのマネージ コードから変更を許可しないまたはロケールを同期するためのメカニズムを実装していませんの場合は、E_NOTIMPL をこのメソッドから返します。</span><span class="sxs-lookup"><span data-stu-id="2236e-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2236e-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="2236e-130">Requirements</span></span>  
 <span data-ttu-id="2236e-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2236e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2236e-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2236e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2236e-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2236e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2236e-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2236e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2236e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="2236e-135">See also</span></span>
- [<span data-ttu-id="2236e-136">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2236e-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2236e-137">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2236e-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2236e-138">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2236e-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2236e-139">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2236e-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="2236e-140">SetUILocale メソッド</span><span class="sxs-lookup"><span data-stu-id="2236e-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
