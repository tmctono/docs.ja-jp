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
ms.openlocfilehash: 101bcac4ad25a0e1c0a5971aad639b0fb05378b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779968"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="c3aac-102">ICLRTaskManager::SetUILocale メソッド</span><span class="sxs-lookup"><span data-stu-id="c3aac-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="c3aac-103">現在実行中のタスクでは、共通言語ランタイム (CLR) ユーザー インターフェイス (UI) のロケール、またはカルチャ、ホストを変更したことを通知します。</span><span class="sxs-lookup"><span data-stu-id="c3aac-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3aac-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3aac-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3aac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3aac-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="c3aac-106">[in]新しく割り当てられた地理的なカルチャおよび言語のユーザー インターフェイスにマップされるロケール識別子の値。</span><span class="sxs-lookup"><span data-stu-id="c3aac-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3aac-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="c3aac-107">Return Value</span></span>  
  
|<span data-ttu-id="c3aac-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3aac-108">HRESULT</span></span>|<span data-ttu-id="c3aac-109">説明</span><span class="sxs-lookup"><span data-stu-id="c3aac-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3aac-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3aac-110">S_OK</span></span>|<span data-ttu-id="c3aac-111">`SetUILocale` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="c3aac-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="c3aac-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3aac-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c3aac-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="c3aac-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c3aac-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c3aac-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c3aac-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="c3aac-115">The call timed out.</span></span>|  
|<span data-ttu-id="c3aac-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c3aac-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c3aac-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c3aac-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c3aac-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c3aac-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c3aac-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="c3aac-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c3aac-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c3aac-120">E_FAIL</span></span>|<span data-ttu-id="c3aac-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c3aac-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c3aac-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c3aac-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c3aac-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c3aac-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3aac-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="c3aac-124">Remarks</span></span>  
 <span data-ttu-id="c3aac-125">`SetUILocale` ロケールの同期の任意の機構があればそれを実行するホストの機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="c3aac-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3aac-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="c3aac-126">Requirements</span></span>  
 <span data-ttu-id="c3aac-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3aac-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3aac-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c3aac-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3aac-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c3aac-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3aac-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3aac-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3aac-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3aac-131">See also</span></span>

- [<span data-ttu-id="c3aac-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3aac-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c3aac-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3aac-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c3aac-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3aac-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c3aac-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3aac-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
