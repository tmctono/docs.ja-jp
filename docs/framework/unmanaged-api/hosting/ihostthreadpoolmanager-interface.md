---
title: IHostThreadPoolManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: 8aef78c7cf70e6b2d97af9c47d57908b86729ff7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122081"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="85cde-102">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="85cde-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="85cde-103">共通言語ランタイム (CLR) がスレッドプールを構成し、作業項目をスレッドプールにキューするようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="85cde-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85cde-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="85cde-104">Methods</span></span>  
  
|<span data-ttu-id="85cde-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="85cde-105">Method</span></span>|<span data-ttu-id="85cde-106">説明</span><span class="sxs-lookup"><span data-stu-id="85cde-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85cde-107">GetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="85cde-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="85cde-108">現在作業項目を処理していないスレッドプール内のスレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="85cde-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="85cde-109">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="85cde-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="85cde-110">ホストがスレッドプール内で同時に保持するスレッドの最大数を取得します。</span><span class="sxs-lookup"><span data-stu-id="85cde-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="85cde-111">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="85cde-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="85cde-112">要求を処理するためにホストが保持するアイドル状態のスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="85cde-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="85cde-113">QueueUserWorkItem メソッド</span><span class="sxs-lookup"><span data-stu-id="85cde-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="85cde-114">実行する関数をキューに配置し、関数によって使用されるデータを格納しているオブジェクトを提供します。</span><span class="sxs-lookup"><span data-stu-id="85cde-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="85cde-115">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="85cde-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="85cde-116">ホストがスレッドプールで保持できるスレッドの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="85cde-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="85cde-117">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="85cde-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="85cde-118">ホストが要求を見越して保持する必要があるアイドル状態のスレッドの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="85cde-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85cde-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="85cde-119">Remarks</span></span>  
 <span data-ttu-id="85cde-120">ホストは、`SetMaxThreads` および `SetMinThreads` メソッドの呼び出しで指定された値を使用してスレッドプールを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="85cde-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="85cde-121">この場合、ホストはこれらのメソッドから E_NOTIMPL の HRESULT 値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="85cde-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85cde-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="85cde-122">Requirements</span></span>  
 <span data-ttu-id="85cde-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85cde-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85cde-124">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="85cde-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85cde-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="85cde-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85cde-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85cde-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85cde-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="85cde-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="85cde-128">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="85cde-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
