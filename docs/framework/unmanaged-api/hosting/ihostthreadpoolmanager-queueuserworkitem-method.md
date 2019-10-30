---
title: IHostThreadPoolManager::QueueUserWorkItem メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
ms.openlocfilehash: 39c35884d0fb53baefafbf86391a349e141418a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141316"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="f08be-102">IHostThreadPoolManager::QueueUserWorkItem メソッド</span><span class="sxs-lookup"><span data-stu-id="f08be-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="f08be-103">実行する関数をキューに配置し、その関数によって使用されるデータを格納しているオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f08be-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="f08be-104">関数は、スレッドが使用可能になったときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="f08be-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f08be-105">構文</span><span class="sxs-lookup"><span data-stu-id="f08be-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f08be-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f08be-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="f08be-107">から実行する関数を表す関数ポインター。</span><span class="sxs-lookup"><span data-stu-id="f08be-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="f08be-108">から`Function`によって使用されるデータを格納しているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f08be-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="f08be-109">からWin32 `QueueUserWorkItem` メソッドに対して定義されているフラグ値の1つ。実行を制御します。</span><span class="sxs-lookup"><span data-stu-id="f08be-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f08be-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="f08be-110">Return Value</span></span>  
  
|<span data-ttu-id="f08be-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f08be-111">HRESULT</span></span>|<span data-ttu-id="f08be-112">説明</span><span class="sxs-lookup"><span data-stu-id="f08be-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f08be-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f08be-113">S_OK</span></span>|<span data-ttu-id="f08be-114">`QueueUserWorkItem` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="f08be-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="f08be-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f08be-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f08be-116">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="f08be-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f08be-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f08be-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f08be-118">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="f08be-118">The call timed out.</span></span>|  
|<span data-ttu-id="f08be-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f08be-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f08be-120">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f08be-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f08be-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f08be-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f08be-122">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="f08be-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f08be-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f08be-123">E_FAIL</span></span>|<span data-ttu-id="f08be-124">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f08be-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f08be-125">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f08be-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f08be-126">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f08be-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f08be-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="f08be-127">Remarks</span></span>  
 <span data-ttu-id="f08be-128">`QueueUserWorkItem`、スレッドプール内のワーカースレッドに作業項目をキューに置いています。</span><span class="sxs-lookup"><span data-stu-id="f08be-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="f08be-129">そのシグネチャとパラメーターの型は、同じ名前を持つ対応する Win32 関数と同じです。</span><span class="sxs-lookup"><span data-stu-id="f08be-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="f08be-130">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f08be-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f08be-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="f08be-131">Requirements</span></span>  
 <span data-ttu-id="f08be-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f08be-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f08be-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f08be-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f08be-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f08be-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f08be-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f08be-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f08be-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="f08be-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="f08be-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f08be-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
