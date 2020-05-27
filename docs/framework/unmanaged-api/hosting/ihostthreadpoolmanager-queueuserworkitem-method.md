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
ms.openlocfilehash: b3d77e30cd48310c392d38dc29f62fab565c8b42
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842466"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="4435c-102">IHostThreadPoolManager::QueueUserWorkItem メソッド</span><span class="sxs-lookup"><span data-stu-id="4435c-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="4435c-103">実行する関数をキューに配置し、その関数によって使用されるデータを格納しているオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4435c-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="4435c-104">関数は、スレッドが使用可能になったときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="4435c-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4435c-105">構文</span><span class="sxs-lookup"><span data-stu-id="4435c-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4435c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4435c-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="4435c-107">から実行する関数を表す関数ポインター。</span><span class="sxs-lookup"><span data-stu-id="4435c-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="4435c-108">からによって使用されるデータを格納しているオブジェクト `Function` 。</span><span class="sxs-lookup"><span data-stu-id="4435c-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="4435c-109">からWin32 メソッドに対して定義されている、実行を制御するフラグ値の1つ `QueueUserWorkItem` 。</span><span class="sxs-lookup"><span data-stu-id="4435c-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4435c-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="4435c-110">Return Value</span></span>  
  
|<span data-ttu-id="4435c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4435c-111">HRESULT</span></span>|<span data-ttu-id="4435c-112">説明</span><span class="sxs-lookup"><span data-stu-id="4435c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4435c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="4435c-113">S_OK</span></span>|<span data-ttu-id="4435c-114">`QueueUserWorkItem`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4435c-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="4435c-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4435c-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4435c-116">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="4435c-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4435c-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4435c-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4435c-118">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="4435c-118">The call timed out.</span></span>|  
|<span data-ttu-id="4435c-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4435c-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4435c-120">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4435c-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4435c-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4435c-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4435c-122">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="4435c-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4435c-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4435c-123">E_FAIL</span></span>|<span data-ttu-id="4435c-124">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4435c-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4435c-125">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4435c-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4435c-126">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4435c-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4435c-127">コメント</span><span class="sxs-lookup"><span data-stu-id="4435c-127">Remarks</span></span>  
 <span data-ttu-id="4435c-128">`QueueUserWorkItem`スレッドプール内のワーカースレッドに作業項目をキューします。</span><span class="sxs-lookup"><span data-stu-id="4435c-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="4435c-129">そのシグネチャとパラメーターの型は、同じ名前を持つ対応する Win32 関数と同じです。</span><span class="sxs-lookup"><span data-stu-id="4435c-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="4435c-130">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4435c-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4435c-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="4435c-131">Requirements</span></span>  
 <span data-ttu-id="4435c-132">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4435c-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4435c-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4435c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4435c-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4435c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4435c-135">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4435c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4435c-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4435c-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="4435c-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4435c-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
