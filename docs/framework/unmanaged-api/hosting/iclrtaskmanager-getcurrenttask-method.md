---
title: ICLRTaskManager::GetCurrentTask メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: 9cb97d9f383b7b54b431457042c4c4a7fc9cd876
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762833"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="65d90-102">ICLRTaskManager::GetCurrentTask メソッド</span><span class="sxs-lookup"><span data-stu-id="65d90-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="65d90-103">メソッドの呼び出し元のオペレーティングシステムスレッドで現在実行されている[ICLRTask](iclrtask-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="65d90-103">Gets the [ICLRTask](iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65d90-104">構文</span><span class="sxs-lookup"><span data-stu-id="65d90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65d90-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="65d90-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="65d90-106">入出力`ICLRTask`呼び出しを開始したオペレーティングシステムスレッドで現在実行されているインスタンスのアドレスへのポインター。このスレッドで現在実行中のタスクがない場合は null。</span><span class="sxs-lookup"><span data-stu-id="65d90-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65d90-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="65d90-107">Return Value</span></span>  
  
|<span data-ttu-id="65d90-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65d90-108">HRESULT</span></span>|<span data-ttu-id="65d90-109">説明</span><span class="sxs-lookup"><span data-stu-id="65d90-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65d90-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="65d90-110">S_OK</span></span>|<span data-ttu-id="65d90-111">メソッドから正常に値が返されました。</span><span class="sxs-lookup"><span data-stu-id="65d90-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="65d90-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65d90-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65d90-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="65d90-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65d90-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65d90-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65d90-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="65d90-115">The call timed out.</span></span>|  
|<span data-ttu-id="65d90-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65d90-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65d90-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="65d90-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65d90-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65d90-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65d90-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="65d90-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65d90-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65d90-120">E_FAIL</span></span>|<span data-ttu-id="65d90-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="65d90-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65d90-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="65d90-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65d90-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="65d90-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65d90-124">解説</span><span class="sxs-lookup"><span data-stu-id="65d90-124">Remarks</span></span>  
 <span data-ttu-id="65d90-125">`ICLRTask`パラメーターが指すインスタンスは、 `ppTask` CLR に対して現在実行中のタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="65d90-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="65d90-126">`ICLRTask`インスタンスは、ホストのタスクを表す、対応する[IHostTask](ihosttask-interface.md)インスタンスに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="65d90-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65d90-127">要件</span><span class="sxs-lookup"><span data-stu-id="65d90-127">Requirements</span></span>  
 <span data-ttu-id="65d90-128">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65d90-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65d90-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="65d90-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65d90-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="65d90-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65d90-131">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65d90-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d90-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="65d90-132">See also</span></span>

- [<span data-ttu-id="65d90-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65d90-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="65d90-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65d90-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="65d90-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65d90-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="65d90-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65d90-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
