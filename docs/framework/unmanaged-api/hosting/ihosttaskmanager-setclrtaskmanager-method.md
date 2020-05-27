---
title: IHostTaskManager::SetCLRTaskManager メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: 0e030a33a0a3368f35c82fad33f1ea2ce32446af
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841829"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="b3fc7-102">IHostTaskManager::SetCLRTaskManager メソッド</span><span class="sxs-lookup"><span data-stu-id="b3fc7-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="b3fc7-103">共通言語ランタイム (CLR) によって実装された[ICLRTaskManager](iclrtaskmanager-interface.md)インスタンスへのインターフェイスポインターをホストに提供します。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-103">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3fc7-104">構文</span><span class="sxs-lookup"><span data-stu-id="b3fc7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3fc7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3fc7-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="b3fc7-106">から`ICLRTaskManager`共通言語ランタイムによって実装されたインスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3fc7-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b3fc7-107">Return Value</span></span>  
  
|<span data-ttu-id="b3fc7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3fc7-108">HRESULT</span></span>|<span data-ttu-id="b3fc7-109">説明</span><span class="sxs-lookup"><span data-stu-id="b3fc7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3fc7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3fc7-110">S_OK</span></span>|<span data-ttu-id="b3fc7-111">`SetCLRTaskManager`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="b3fc7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3fc7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3fc7-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3fc7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3fc7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3fc7-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-115">The call timed out.</span></span>|  
|<span data-ttu-id="b3fc7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3fc7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3fc7-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3fc7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3fc7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3fc7-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3fc7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3fc7-120">E_FAIL</span></span>|<span data-ttu-id="b3fc7-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3fc7-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3fc7-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3fc7-124">コメント</span><span class="sxs-lookup"><span data-stu-id="b3fc7-124">Remarks</span></span>  
 <span data-ttu-id="b3fc7-125">ランタイムはを呼び出して、 `SetCLRTaskManager` ホストにインスタンスへのインターフェイスポインターを提供し `ICLRTaskManager` ます。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3fc7-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="b3fc7-126">Requirements</span></span>  
 <span data-ttu-id="b3fc7-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3fc7-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3fc7-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b3fc7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3fc7-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b3fc7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3fc7-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3fc7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3fc7-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3fc7-131">See also</span></span>

- [<span data-ttu-id="b3fc7-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3fc7-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b3fc7-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3fc7-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b3fc7-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3fc7-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b3fc7-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3fc7-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
