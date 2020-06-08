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
ms.openlocfilehash: 6a6b4d0351e22026dc873aad8281d0259d871a14
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501483"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="abc41-102">IHostSecurityManager::SetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="abc41-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="abc41-103">現在実行中のスレッドのセキュリティコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="abc41-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abc41-104">構文</span><span class="sxs-lookup"><span data-stu-id="abc41-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abc41-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="abc41-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="abc41-106">から[EContextType](econtexttype-enumeration.md)値の1つ。共通言語ランタイム (CLR) がホストに配置しているコンテキストの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="abc41-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="abc41-107">入出力新しい[IHostSecurityContext](ihostsecuritycontext-interface.md)オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="abc41-107">[out] A pointer to the address of a new [IHostSecurityContext](ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abc41-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="abc41-108">Return Value</span></span>  
  
|<span data-ttu-id="abc41-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="abc41-109">HRESULT</span></span>|<span data-ttu-id="abc41-110">説明</span><span class="sxs-lookup"><span data-stu-id="abc41-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="abc41-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="abc41-111">S_OK</span></span>|<span data-ttu-id="abc41-112">`SetSecurityContext`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="abc41-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="abc41-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="abc41-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="abc41-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="abc41-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="abc41-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="abc41-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="abc41-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="abc41-116">The call timed out.</span></span>|  
|<span data-ttu-id="abc41-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="abc41-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="abc41-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="abc41-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="abc41-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="abc41-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="abc41-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="abc41-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="abc41-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="abc41-121">E_FAIL</span></span>|<span data-ttu-id="abc41-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="abc41-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="abc41-123">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="abc41-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="abc41-124">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="abc41-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abc41-125">解説</span><span class="sxs-lookup"><span data-stu-id="abc41-125">Remarks</span></span>  
 <span data-ttu-id="abc41-126">CLR は `SetSecurityContext` いくつかのシナリオでを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="abc41-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="abc41-127">CLR は、クラスコンストラクターとモジュールコンストラクター、およびファイナライザーを実行する前にを呼び出して、 `SetSecurityContext` ホストが実行エラーから保護されるようにします。</span><span class="sxs-lookup"><span data-stu-id="abc41-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="abc41-128">次に、への別の呼び出しを使用して、コンストラクターまたはファイナライザーの実行後に、セキュリティコンテキストを元の状態にリセットし `SetSecurityContext` ます。</span><span class="sxs-lookup"><span data-stu-id="abc41-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="abc41-129">同様のパターンは、i/o の完了時に発生します。</span><span class="sxs-lookup"><span data-stu-id="abc41-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="abc41-130">ホストが[Ihostiocompletionmanager manager](ihostiocompletionmanager-interface.md)を実装している場合、CLR は `SetSecurityContext` ホストが[Iclriocomplete Manager:: oncomplete](iclriocompletionmanager-oncomplete-method.md)を呼び出した後にを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="abc41-130">If the host implements [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="abc41-131">ワーカースレッドの非同期ポイントでは、CLR は `SetSecurityContext` 、 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> ホストまたは clr がスレッドプールを実装しているかどうかに応じて、 [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)内または内でを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="abc41-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abc41-132">要件</span><span class="sxs-lookup"><span data-stu-id="abc41-132">Requirements</span></span>  
 <span data-ttu-id="abc41-133">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abc41-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abc41-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="abc41-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abc41-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="abc41-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abc41-136">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abc41-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abc41-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="abc41-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="abc41-138">EContextType 列挙型</span><span class="sxs-lookup"><span data-stu-id="abc41-138">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="abc41-139">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abc41-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="abc41-140">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abc41-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="abc41-141">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abc41-141">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="abc41-142">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abc41-142">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="abc41-143">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abc41-143">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
