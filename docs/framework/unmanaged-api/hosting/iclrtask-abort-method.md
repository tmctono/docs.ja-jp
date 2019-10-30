---
title: ICLRTask::Abort メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
ms.openlocfilehash: 026d4c14abed030b80e8e1b3f8363fbd59ac05e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124915"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="0cee7-102">ICLRTask::Abort メソッド</span><span class="sxs-lookup"><span data-stu-id="0cee7-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="0cee7-103">現在の[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスが表すタスクを共通言語ランタイム (CLR) が中止することを要求します。</span><span class="sxs-lookup"><span data-stu-id="0cee7-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cee7-104">構文</span><span class="sxs-lookup"><span data-stu-id="0cee7-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0cee7-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="0cee7-105">Return Value</span></span>  
  
|<span data-ttu-id="0cee7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0cee7-106">HRESULT</span></span>|<span data-ttu-id="0cee7-107">説明</span><span class="sxs-lookup"><span data-stu-id="0cee7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0cee7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0cee7-108">S_OK</span></span>|<span data-ttu-id="0cee7-109">`Abort` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="0cee7-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="0cee7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0cee7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0cee7-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="0cee7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0cee7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0cee7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0cee7-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="0cee7-113">The call timed out.</span></span>|  
|<span data-ttu-id="0cee7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0cee7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0cee7-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0cee7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0cee7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0cee7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0cee7-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="0cee7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0cee7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0cee7-118">E_FAIL</span></span>|<span data-ttu-id="0cee7-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0cee7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0cee7-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0cee7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0cee7-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0cee7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cee7-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="0cee7-122">Remarks</span></span>  
 <span data-ttu-id="0cee7-123">ホストが `Abort`を呼び出すと、CLR によって <xref:System.Threading.ThreadAbortException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="0cee7-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="0cee7-124">ファイナライザーや例外処理機構などのユーザーコードが実行されるのを待たずに、例外情報が初期化された直後に制御が戻ります。</span><span class="sxs-lookup"><span data-stu-id="0cee7-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="0cee7-125">`Abort` を呼び出すと、すぐにが返されます。</span><span class="sxs-lookup"><span data-stu-id="0cee7-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cee7-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="0cee7-126">Requirements</span></span>  
 <span data-ttu-id="0cee7-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cee7-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cee7-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0cee7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0cee7-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0cee7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cee7-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cee7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cee7-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cee7-131">See also</span></span>

- [<span data-ttu-id="0cee7-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0cee7-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0cee7-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0cee7-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0cee7-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0cee7-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0cee7-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0cee7-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
