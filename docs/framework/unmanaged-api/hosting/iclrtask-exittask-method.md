---
title: ICLRTask::ExitTask メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a55b62c7c71510435b980a4e5938c20628046f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075888"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="13673-102">ICLRTask::ExitTask メソッド</span><span class="sxs-lookup"><span data-stu-id="13673-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="13673-103">タスクが現在によって表される共通言語ランタイム (CLR) に通知[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスが終了し、タスクを正常にシャット ダウンしようとしています。</span><span class="sxs-lookup"><span data-stu-id="13673-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13673-104">構文</span><span class="sxs-lookup"><span data-stu-id="13673-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="13673-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="13673-105">Return Value</span></span>  
  
|<span data-ttu-id="13673-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13673-106">HRESULT</span></span>|<span data-ttu-id="13673-107">説明</span><span class="sxs-lookup"><span data-stu-id="13673-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13673-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="13673-108">S_OK</span></span>|<span data-ttu-id="13673-109">`ExitTask` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="13673-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="13673-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="13673-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="13673-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="13673-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="13673-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="13673-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="13673-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="13673-113">The call timed out.</span></span>|  
|<span data-ttu-id="13673-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="13673-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="13673-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="13673-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="13673-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="13673-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="13673-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="13673-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="13673-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="13673-118">E_FAIL</span></span>|<span data-ttu-id="13673-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="13673-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="13673-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="13673-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="13673-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="13673-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13673-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="13673-122">Remarks</span></span>  
 <span data-ttu-id="13673-123">`ExitTask` アンマネージ型ライブラリからスレッドをデタッチする場合と同様に、タスクのクリーン シャット ダウンを試行します。</span><span class="sxs-lookup"><span data-stu-id="13673-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13673-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="13673-124">Requirements</span></span>  
 <span data-ttu-id="13673-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13673-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13673-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13673-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13673-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="13673-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13673-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13673-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13673-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="13673-129">See also</span></span>

- [<span data-ttu-id="13673-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13673-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="13673-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13673-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="13673-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13673-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="13673-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13673-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
