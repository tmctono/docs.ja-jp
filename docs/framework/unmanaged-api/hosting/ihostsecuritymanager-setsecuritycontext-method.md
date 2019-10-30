---
title: IHostSecurityManager::SetSecurityContext メソッド
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: 676a1d50202333203c13fcf916dbb14a6d91fb8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121446"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="c23f4-102">IHostSecurityManager::SetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="c23f4-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="c23f4-103">現在実行中のスレッドのセキュリティコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="c23f4-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c23f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="c23f4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c23f4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c23f4-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="c23f4-106">から[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)値の1つ。共通言語ランタイム (CLR) がホストに配置しているコンテキストの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c23f4-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="c23f4-107">入出力新しい[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c23f4-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c23f4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c23f4-108">Return Value</span></span>  
  
|<span data-ttu-id="c23f4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c23f4-109">HRESULT</span></span>|<span data-ttu-id="c23f4-110">説明</span><span class="sxs-lookup"><span data-stu-id="c23f4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c23f4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c23f4-111">S_OK</span></span>|<span data-ttu-id="c23f4-112">`SetSecurityContext` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="c23f4-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="c23f4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c23f4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c23f4-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="c23f4-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c23f4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c23f4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c23f4-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="c23f4-116">The call timed out.</span></span>|  
|<span data-ttu-id="c23f4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c23f4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c23f4-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c23f4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c23f4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c23f4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c23f4-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="c23f4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c23f4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c23f4-121">E_FAIL</span></span>|<span data-ttu-id="c23f4-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c23f4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c23f4-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c23f4-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c23f4-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c23f4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c23f4-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="c23f4-125">Remarks</span></span>  
 <span data-ttu-id="c23f4-126">CLR はいくつかのシナリオで `SetSecurityContext` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c23f4-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="c23f4-127">CLR は、クラスおよびモジュールのコンストラクターとファイナライザーを実行する前に、`SetSecurityContext` を呼び出して、ホストが実行エラーから保護されるようにします。</span><span class="sxs-lookup"><span data-stu-id="c23f4-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="c23f4-128">次に、`SetSecurityContext`への別の呼び出しを使用して、コンストラクターまたはファイナライザーの実行後に、セキュリティコンテキストを元の状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="c23f4-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="c23f4-129">同様のパターンは、i/o の完了時に発生します。</span><span class="sxs-lookup"><span data-stu-id="c23f4-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="c23f4-130">ホストが[Ihostiocompletionmanager manager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)を実装している場合、CLR は、ホストが[iclriocomplete Manager:: oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)を呼び出した後に `SetSecurityContext` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c23f4-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="c23f4-131">ワーカースレッドの非同期ポイントでは、CLR は、ホストまたは CLR がスレッドプールを実装しているかどうかに応じて、<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 内または[IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)内で `SetSecurityContext` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c23f4-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c23f4-132">［要件］</span><span class="sxs-lookup"><span data-stu-id="c23f4-132">Requirements</span></span>  
 <span data-ttu-id="c23f4-133">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c23f4-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c23f4-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c23f4-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c23f4-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c23f4-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c23f4-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c23f4-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c23f4-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c23f4-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="c23f4-138">EContextType 列挙型</span><span class="sxs-lookup"><span data-stu-id="c23f4-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="c23f4-139">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c23f4-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="c23f4-140">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c23f4-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="c23f4-141">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c23f4-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c23f4-142">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c23f4-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="c23f4-143">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c23f4-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
