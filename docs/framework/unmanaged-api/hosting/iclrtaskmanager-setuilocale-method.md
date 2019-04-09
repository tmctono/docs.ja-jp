---
title: ICLRTaskManager::SetUILocale メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03c5c9d04567832951062fe1512a292f9b32a94b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155677"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="499b0-102">ICLRTaskManager::SetUILocale メソッド</span><span class="sxs-lookup"><span data-stu-id="499b0-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="499b0-103">現在実行中のタスクでは、共通言語ランタイム (CLR) ユーザー インターフェイス (UI) のロケール、またはカルチャ、ホストを変更したことを通知します。</span><span class="sxs-lookup"><span data-stu-id="499b0-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499b0-104">構文</span><span class="sxs-lookup"><span data-stu-id="499b0-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="499b0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="499b0-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="499b0-106">[in]新しく割り当てられた地理的なカルチャおよび言語のユーザー インターフェイスにマップされるロケール識別子の値。</span><span class="sxs-lookup"><span data-stu-id="499b0-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="499b0-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="499b0-107">Return Value</span></span>  
  
|<span data-ttu-id="499b0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="499b0-108">HRESULT</span></span>|<span data-ttu-id="499b0-109">説明</span><span class="sxs-lookup"><span data-stu-id="499b0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="499b0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="499b0-110">S_OK</span></span>|`SetUILocale` <span data-ttu-id="499b0-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="499b0-111">returned successfully.</span></span>|  
|<span data-ttu-id="499b0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="499b0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="499b0-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="499b0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="499b0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="499b0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="499b0-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="499b0-115">The call timed out.</span></span>|  
|<span data-ttu-id="499b0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="499b0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="499b0-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="499b0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="499b0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="499b0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="499b0-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="499b0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="499b0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="499b0-120">E_FAIL</span></span>|<span data-ttu-id="499b0-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="499b0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="499b0-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="499b0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="499b0-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="499b0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="499b0-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="499b0-124">Remarks</span></span>  
 `SetUILocale` <span data-ttu-id="499b0-125">ロケールの同期の任意の機構があればそれを実行するホストの機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="499b0-125">provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="499b0-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="499b0-126">Requirements</span></span>  
 <span data-ttu-id="499b0-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="499b0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="499b0-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="499b0-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="499b0-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="499b0-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="499b0-130">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="499b0-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="499b0-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="499b0-131">See also</span></span>

- [<span data-ttu-id="499b0-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="499b0-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="499b0-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="499b0-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="499b0-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="499b0-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="499b0-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="499b0-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
