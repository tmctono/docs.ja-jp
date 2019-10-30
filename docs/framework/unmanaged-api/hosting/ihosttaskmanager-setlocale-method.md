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
ms.openlocfilehash: e560d08d3e10db1b5978d1bd7be53dfed9ca3268
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132980"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="b7bfc-102">IHostTaskManager::SetLocale メソッド</span><span class="sxs-lookup"><span data-stu-id="b7bfc-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="b7bfc-103">共通言語ランタイム (CLR) によって、現在実行中のタスクのロケール (カルチャ) が変更されたことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7bfc-104">構文</span><span class="sxs-lookup"><span data-stu-id="b7bfc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7bfc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b7bfc-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="b7bfc-106">から新しく割り当てられた地理的カルチャおよび言語にマップされるロケール識別子の値。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7bfc-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b7bfc-107">Return Value</span></span>  
  
|<span data-ttu-id="b7bfc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7bfc-108">HRESULT</span></span>|<span data-ttu-id="b7bfc-109">説明</span><span class="sxs-lookup"><span data-stu-id="b7bfc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7bfc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7bfc-110">S_OK</span></span>|<span data-ttu-id="b7bfc-111">`SetLocale` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="b7bfc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b7bfc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b7bfc-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b7bfc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b7bfc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b7bfc-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-115">The call timed out.</span></span>|  
|<span data-ttu-id="b7bfc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b7bfc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b7bfc-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b7bfc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b7bfc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b7bfc-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b7bfc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7bfc-120">E_FAIL</span></span>|<span data-ttu-id="b7bfc-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b7bfc-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b7bfc-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b7bfc-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b7bfc-124">E_NOTIMPL</span></span>|<span data-ttu-id="b7bfc-125">ホストでは、マネージユーザーコードでロケールを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7bfc-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7bfc-126">Remarks</span></span>  
 <span data-ttu-id="b7bfc-127">ランタイムは、<xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> プロパティの値がマネージコードによって変更された場合に `SetLocale` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="b7bfc-128">この方法を使用すると、ホストはロケールの同期に必要なメカニズムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="b7bfc-129">ホストでロケールをマネージコードから変更できない場合、またはロケールを同期する機構を実装していない場合は、このメソッドから E_NOTIMPL が返されます。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7bfc-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="b7bfc-130">Requirements</span></span>  
 <span data-ttu-id="b7bfc-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7bfc-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7bfc-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b7bfc-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7bfc-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b7bfc-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7bfc-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7bfc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bfc-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7bfc-135">See also</span></span>

- [<span data-ttu-id="b7bfc-136">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7bfc-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b7bfc-137">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7bfc-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b7bfc-138">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7bfc-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b7bfc-139">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7bfc-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="b7bfc-140">SetUILocale メソッド</span><span class="sxs-lookup"><span data-stu-id="b7bfc-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
