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
ms.openlocfilehash: 051bd5cb846eb4e6e3390e17b3011a1c5b50bc45
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127877"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="a3824-102">ICLRTaskManager::SetUILocale メソッド</span><span class="sxs-lookup"><span data-stu-id="a3824-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="a3824-103">現在実行中のタスクのユーザーインターフェイス (UI) ロケール (カルチャ) がホストによって変更されたことを、共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="a3824-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3824-104">構文</span><span class="sxs-lookup"><span data-stu-id="a3824-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3824-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3824-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="a3824-106">から新しく割り当てられた地理的カルチャとユーザーインターフェイスの言語にマップされるロケール識別子の値。</span><span class="sxs-lookup"><span data-stu-id="a3824-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3824-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="a3824-107">Return Value</span></span>  
  
|<span data-ttu-id="a3824-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3824-108">HRESULT</span></span>|<span data-ttu-id="a3824-109">説明</span><span class="sxs-lookup"><span data-stu-id="a3824-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3824-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3824-110">S_OK</span></span>|<span data-ttu-id="a3824-111">`SetUILocale` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="a3824-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="a3824-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3824-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3824-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="a3824-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a3824-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3824-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a3824-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="a3824-115">The call timed out.</span></span>|  
|<span data-ttu-id="a3824-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a3824-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a3824-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="a3824-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a3824-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a3824-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a3824-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="a3824-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a3824-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3824-120">E_FAIL</span></span>|<span data-ttu-id="a3824-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a3824-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a3824-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a3824-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a3824-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="a3824-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3824-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="a3824-124">Remarks</span></span>  
 <span data-ttu-id="a3824-125">`SetUILocale` を使用すると、ホストはロケールの同期に必要なメカニズムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a3824-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3824-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="a3824-126">Requirements</span></span>  
 <span data-ttu-id="a3824-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3824-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3824-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a3824-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3824-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a3824-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3824-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3824-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3824-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3824-131">See also</span></span>

- [<span data-ttu-id="a3824-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3824-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a3824-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3824-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a3824-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3824-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a3824-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3824-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
