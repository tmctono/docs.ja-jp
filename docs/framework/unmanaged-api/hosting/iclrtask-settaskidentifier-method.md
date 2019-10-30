---
title: ICLRTask::SetTaskIdentifier メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: cf6d84e483188ea7ed3376ba9b28906a38913fd4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124622"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="be4bf-102">ICLRTask::SetTaskIdentifier メソッド</span><span class="sxs-lookup"><span data-stu-id="be4bf-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="be4bf-103">共通言語ランタイム (CLR) に対して、指定された識別子の値を現在の[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスによって表されるタスクに関連付けるように指示します。</span><span class="sxs-lookup"><span data-stu-id="be4bf-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be4bf-104">構文</span><span class="sxs-lookup"><span data-stu-id="be4bf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be4bf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be4bf-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="be4bf-106">から現在の `ICLRTask` インスタンスによって表されるタスクに関連付ける共通言語ランタイムの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="be4bf-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be4bf-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="be4bf-107">Return Value</span></span>  
  
|<span data-ttu-id="be4bf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be4bf-108">HRESULT</span></span>|<span data-ttu-id="be4bf-109">説明</span><span class="sxs-lookup"><span data-stu-id="be4bf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be4bf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="be4bf-110">S_OK</span></span>|<span data-ttu-id="be4bf-111">`SetTaskIdentifier` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="be4bf-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="be4bf-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="be4bf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="be4bf-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="be4bf-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="be4bf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="be4bf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="be4bf-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="be4bf-115">The call timed out.</span></span>|  
|<span data-ttu-id="be4bf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="be4bf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="be4bf-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="be4bf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="be4bf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="be4bf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="be4bf-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="be4bf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="be4bf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be4bf-120">E_FAIL</span></span>|<span data-ttu-id="be4bf-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="be4bf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="be4bf-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="be4bf-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="be4bf-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="be4bf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be4bf-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="be4bf-124">Remarks</span></span>  
 <span data-ttu-id="be4bf-125">ホストは、デバッグ環境で CLR とホストを統合できるように、識別子をタスクに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="be4bf-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="be4bf-126">この識別子は、CLR には意味がありません。</span><span class="sxs-lookup"><span data-stu-id="be4bf-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="be4bf-127">CLR はこれをデバッガーアプリケーションに渡します。</span><span class="sxs-lookup"><span data-stu-id="be4bf-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="be4bf-128">デバッガーはこの識別子を使用して、CLR 呼び出し履歴をホストの呼び出し履歴に関連付けて、デバッガーのユーザーインターフェイスに表示されたときに、それぞれのトレース情報を統合できるようにします。</span><span class="sxs-lookup"><span data-stu-id="be4bf-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be4bf-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="be4bf-129">Requirements</span></span>  
 <span data-ttu-id="be4bf-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be4bf-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be4bf-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="be4bf-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be4bf-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="be4bf-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be4bf-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be4bf-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4bf-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="be4bf-134">See also</span></span>

- [<span data-ttu-id="be4bf-135">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="be4bf-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="be4bf-136">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="be4bf-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="be4bf-137">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="be4bf-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="be4bf-138">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="be4bf-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
