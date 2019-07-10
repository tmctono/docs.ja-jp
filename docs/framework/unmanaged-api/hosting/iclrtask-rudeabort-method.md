---
title: ICLRTask::RudeAbort メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7750d50b772ff17cf9dcd05de2e2f34556714e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770482"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="02d8a-102">ICLRTask::RudeAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="02d8a-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="02d8a-103">共通言語ランタイム (CLR) が現在によって表されるタスクを中止するように指示します[ICLRTask インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)直ちに無条件でインスタンスします。</span><span class="sxs-lookup"><span data-stu-id="02d8a-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d8a-104">構文</span><span class="sxs-lookup"><span data-stu-id="02d8a-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="02d8a-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="02d8a-105">Return Value</span></span>  
  
|<span data-ttu-id="02d8a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02d8a-106">HRESULT</span></span>|<span data-ttu-id="02d8a-107">説明</span><span class="sxs-lookup"><span data-stu-id="02d8a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02d8a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="02d8a-108">S_OK</span></span>|<span data-ttu-id="02d8a-109">`RudeAbort` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="02d8a-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="02d8a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02d8a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02d8a-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="02d8a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02d8a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02d8a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02d8a-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="02d8a-113">The call timed out.</span></span>|  
|<span data-ttu-id="02d8a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02d8a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02d8a-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="02d8a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02d8a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02d8a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02d8a-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="02d8a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02d8a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02d8a-118">E_FAIL</span></span>|<span data-ttu-id="02d8a-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="02d8a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02d8a-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="02d8a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02d8a-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="02d8a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02d8a-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="02d8a-122">Remarks</span></span>  
 <span data-ttu-id="02d8a-123">ホストは`RudeAbort`をすぐにタスクを中止します。</span><span class="sxs-lookup"><span data-stu-id="02d8a-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="02d8a-124">ファイナライザーおよび例外処理ルーチンが実行される保証はありません。</span><span class="sxs-lookup"><span data-stu-id="02d8a-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d8a-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="02d8a-125">Requirements</span></span>  
 <span data-ttu-id="02d8a-126">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02d8a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d8a-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="02d8a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02d8a-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="02d8a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02d8a-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d8a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d8a-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="02d8a-130">See also</span></span>

- [<span data-ttu-id="02d8a-131">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02d8a-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="02d8a-132">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02d8a-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="02d8a-133">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02d8a-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="02d8a-134">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02d8a-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
