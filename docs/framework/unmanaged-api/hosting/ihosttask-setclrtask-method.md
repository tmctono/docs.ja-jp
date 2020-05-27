---
title: IHostTask::SetCLRTask メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: b6eac134a4ffb1813cdc6957632ce5fb9b1a5fff
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842271"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="04cfa-102">IHostTask::SetCLRTask メソッド</span><span class="sxs-lookup"><span data-stu-id="04cfa-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="04cfa-103">インスタンスを `ICLRTask` 現在の[IHostTask](ihosttask-interface.md)インスタンスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="04cfa-103">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04cfa-104">構文</span><span class="sxs-lookup"><span data-stu-id="04cfa-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04cfa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04cfa-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="04cfa-106">から`ICLRTask`現在のインスタンスに関連付けられるインスタンスへのインターフェイスポインター `IHostTask` 。</span><span class="sxs-lookup"><span data-stu-id="04cfa-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04cfa-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="04cfa-107">Return Value</span></span>  
  
|<span data-ttu-id="04cfa-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04cfa-108">HRESULT</span></span>|<span data-ttu-id="04cfa-109">説明</span><span class="sxs-lookup"><span data-stu-id="04cfa-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04cfa-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="04cfa-110">S_OK</span></span>|<span data-ttu-id="04cfa-111">`SetCLRTask`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="04cfa-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="04cfa-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04cfa-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04cfa-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="04cfa-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04cfa-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04cfa-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04cfa-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="04cfa-115">The call timed out.</span></span>|  
|<span data-ttu-id="04cfa-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04cfa-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04cfa-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="04cfa-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04cfa-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04cfa-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04cfa-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="04cfa-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="04cfa-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04cfa-120">E_FAIL</span></span>|<span data-ttu-id="04cfa-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="04cfa-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04cfa-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="04cfa-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04cfa-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="04cfa-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04cfa-124">コメント</span><span class="sxs-lookup"><span data-stu-id="04cfa-124">Remarks</span></span>  
 <span data-ttu-id="04cfa-125">CLR は `SetCLRTask` を呼び出して、インスタンスを現在のインスタンスに関連付けます `ICLRTask` `IHostTask` 。これは[IHostTaskManager:: createtask](ihosttaskmanager-createtask-method.md)の呼び出しによって作成されたものです。</span><span class="sxs-lookup"><span data-stu-id="04cfa-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04cfa-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="04cfa-126">Requirements</span></span>  
 <span data-ttu-id="04cfa-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04cfa-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04cfa-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="04cfa-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04cfa-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="04cfa-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04cfa-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04cfa-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04cfa-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="04cfa-131">See also</span></span>

- [<span data-ttu-id="04cfa-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04cfa-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="04cfa-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04cfa-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="04cfa-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04cfa-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="04cfa-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04cfa-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
