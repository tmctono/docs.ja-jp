---
title: ICLRTaskManager::SetLocale メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae097320ad7cd6e7c840122bf3f315812e9b2acd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763348"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="8eb29-102">ICLRTaskManager::SetLocale メソッド</span><span class="sxs-lookup"><span data-stu-id="8eb29-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="8eb29-103">ホストが現在実行中のタスクのロケール識別子 (これは、地理的なカルチャおよび言語にマップする) の値を変更したことを共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="8eb29-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eb29-104">構文</span><span class="sxs-lookup"><span data-stu-id="8eb29-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eb29-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8eb29-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="8eb29-106">[in]新しく割り当てられた地理的なカルチャおよび言語に対応するロケール識別子の値。</span><span class="sxs-lookup"><span data-stu-id="8eb29-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8eb29-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="8eb29-107">Return Value</span></span>  
  
|<span data-ttu-id="8eb29-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8eb29-108">HRESULT</span></span>|<span data-ttu-id="8eb29-109">説明</span><span class="sxs-lookup"><span data-stu-id="8eb29-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8eb29-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8eb29-110">S_OK</span></span>|<span data-ttu-id="8eb29-111">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="8eb29-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="8eb29-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8eb29-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8eb29-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="8eb29-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8eb29-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8eb29-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8eb29-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="8eb29-115">The call timed out.</span></span>|  
|<span data-ttu-id="8eb29-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8eb29-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8eb29-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8eb29-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8eb29-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8eb29-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8eb29-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="8eb29-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8eb29-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8eb29-120">E_FAIL</span></span>|<span data-ttu-id="8eb29-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8eb29-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8eb29-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8eb29-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8eb29-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8eb29-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8eb29-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="8eb29-124">Remarks</span></span>  
 <span data-ttu-id="8eb29-125">`SetLocale` ホストのロケールの同期が与えられているメカニズムを実行する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="8eb29-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eb29-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="8eb29-126">Requirements</span></span>  
 <span data-ttu-id="8eb29-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eb29-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eb29-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8eb29-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8eb29-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8eb29-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8eb29-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eb29-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb29-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="8eb29-131">See also</span></span>

- [<span data-ttu-id="8eb29-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8eb29-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8eb29-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8eb29-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8eb29-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8eb29-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8eb29-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8eb29-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
