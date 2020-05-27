---
title: IHostTask::GetPriority メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: e41fcf2f03b024c1b4ae0032c0ff025d6e2aa1c3
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842505"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="f428b-102">IHostTask::GetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="f428b-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="f428b-103">現在の[IHostTask](ihosttask-interface.md)インスタンスによって表されるタスクのスレッド優先度レベルを取得します。</span><span class="sxs-lookup"><span data-stu-id="f428b-103">Gets the thread priority level of the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f428b-104">構文</span><span class="sxs-lookup"><span data-stu-id="f428b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f428b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f428b-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="f428b-106">入出力現在のインスタンスによって表されるタスクのスレッド優先度レベルを示す整数を指すポインターです `IHostTask` 。</span><span class="sxs-lookup"><span data-stu-id="f428b-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f428b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="f428b-107">Return Value</span></span>  
  
|<span data-ttu-id="f428b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f428b-108">HRESULT</span></span>|<span data-ttu-id="f428b-109">説明</span><span class="sxs-lookup"><span data-stu-id="f428b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f428b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f428b-110">S_OK</span></span>|<span data-ttu-id="f428b-111">`GetPriority`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="f428b-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="f428b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f428b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f428b-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="f428b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f428b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f428b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f428b-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="f428b-115">The call timed out.</span></span>|  
|<span data-ttu-id="f428b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f428b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f428b-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f428b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f428b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f428b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f428b-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="f428b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f428b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f428b-120">E_FAIL</span></span>|<span data-ttu-id="f428b-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f428b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f428b-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f428b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f428b-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f428b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f428b-124">コメント</span><span class="sxs-lookup"><span data-stu-id="f428b-124">Remarks</span></span>  
 <span data-ttu-id="f428b-125">スレッドの優先度レベルの値は、Win32 関数によって定義され `SetThreadPriority` ます。</span><span class="sxs-lookup"><span data-stu-id="f428b-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f428b-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="f428b-126">Requirements</span></span>  
 <span data-ttu-id="f428b-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f428b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f428b-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f428b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f428b-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f428b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f428b-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f428b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f428b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="f428b-131">See also</span></span>

- [<span data-ttu-id="f428b-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f428b-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f428b-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f428b-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f428b-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f428b-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="f428b-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f428b-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
