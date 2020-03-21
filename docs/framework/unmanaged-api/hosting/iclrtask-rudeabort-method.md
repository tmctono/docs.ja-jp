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
ms.openlocfilehash: aacf9de36dc39b63ed36b672e31f40704413d608
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176332"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="87c20-102">ICLRTask::RudeAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="87c20-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="87c20-103">共通言語ランタイム (CLR) に、現在の[ICLRTask インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスによって表されるタスクを直ちに無条件に中止するように指示します。</span><span class="sxs-lookup"><span data-stu-id="87c20-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c20-104">構文</span><span class="sxs-lookup"><span data-stu-id="87c20-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="87c20-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="87c20-105">Return Value</span></span>  
  
|<span data-ttu-id="87c20-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87c20-106">HRESULT</span></span>|<span data-ttu-id="87c20-107">説明</span><span class="sxs-lookup"><span data-stu-id="87c20-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87c20-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="87c20-108">S_OK</span></span>|<span data-ttu-id="87c20-109">`RudeAbort`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="87c20-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="87c20-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87c20-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87c20-111">CLR がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="87c20-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87c20-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87c20-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87c20-113">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="87c20-113">The call timed out.</span></span>|  
|<span data-ttu-id="87c20-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87c20-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87c20-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="87c20-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87c20-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87c20-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87c20-117">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="87c20-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87c20-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87c20-118">E_FAIL</span></span>|<span data-ttu-id="87c20-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="87c20-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87c20-120">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="87c20-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87c20-121">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="87c20-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87c20-122">解説</span><span class="sxs-lookup"><span data-stu-id="87c20-122">Remarks</span></span>  
 <span data-ttu-id="87c20-123">ホストは、`RudeAbort`タスクをただちに中止する呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="87c20-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="87c20-124">ファイナライザーと例外処理ルーチンは、実行される保証はありません。</span><span class="sxs-lookup"><span data-stu-id="87c20-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87c20-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="87c20-125">Requirements</span></span>  
 <span data-ttu-id="87c20-126">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87c20-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87c20-127">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="87c20-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87c20-128">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="87c20-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87c20-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87c20-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c20-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="87c20-130">See also</span></span>

- [<span data-ttu-id="87c20-131">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87c20-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="87c20-132">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87c20-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="87c20-133">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87c20-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="87c20-134">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87c20-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
