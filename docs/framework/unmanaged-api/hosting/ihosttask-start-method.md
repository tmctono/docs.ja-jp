---
title: IHostTask::Start メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: fe93a3bab267ccca941974b734c86329ad0f4d03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121338"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="499de-102">IHostTask::Start メソッド</span><span class="sxs-lookup"><span data-stu-id="499de-102">IHostTask::Start Method</span></span>
<span data-ttu-id="499de-103">現在の[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスによって表されているタスクを、中断されているからライブ状態 (コードを実行できる) に移動するようホストに要求します。</span><span class="sxs-lookup"><span data-stu-id="499de-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499de-104">構文</span><span class="sxs-lookup"><span data-stu-id="499de-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="499de-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="499de-105">Return Value</span></span>  
  
|<span data-ttu-id="499de-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="499de-106">HRESULT</span></span>|<span data-ttu-id="499de-107">説明</span><span class="sxs-lookup"><span data-stu-id="499de-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="499de-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="499de-108">S_OK</span></span>|<span data-ttu-id="499de-109">Start が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="499de-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="499de-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="499de-110">E_FAIL</span></span>|<span data-ttu-id="499de-111">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="499de-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="499de-112">メソッドから E_FAIL が返された場合、そのプロセス内で共通言語ランタイム (CLR) は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="499de-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="499de-113">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="499de-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="499de-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="499de-114">Remarks</span></span>  
 <span data-ttu-id="499de-115">`Start` は常に HRESULT の HRESULT 値を返しますが、重大なエラーが発生した場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="499de-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="499de-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="499de-116">Requirements</span></span>  
 <span data-ttu-id="499de-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="499de-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="499de-118">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="499de-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="499de-119">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="499de-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="499de-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="499de-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499de-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="499de-121">See also</span></span>

- [<span data-ttu-id="499de-122">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="499de-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="499de-123">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="499de-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="499de-124">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="499de-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="499de-125">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="499de-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
