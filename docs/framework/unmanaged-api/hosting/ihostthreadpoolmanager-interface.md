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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e7976740a79efda8e5ab569f2efb55444012c5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220371"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="8f94f-102">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f94f-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="8f94f-103">共通言語ランタイム (CLR) スレッド プールを構成し、スレッド プールに作業項目をキューに登録を有効にする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f94f-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f94f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8f94f-104">Methods</span></span>  
  
|<span data-ttu-id="8f94f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8f94f-105">Method</span></span>|<span data-ttu-id="8f94f-106">説明</span><span class="sxs-lookup"><span data-stu-id="8f94f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f94f-107">GetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="8f94f-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="8f94f-108">作業項目を現在処理していないスレッド プールのスレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f94f-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="8f94f-109">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="8f94f-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="8f94f-110">スレッド プールに同時にホストで管理されるスレッドの最大数を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f94f-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="8f94f-111">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="8f94f-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="8f94f-112">要求に応じるためには、ホストで管理されるアイドル状態のスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f94f-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="8f94f-113">QueueUserWorkItem メソッド</span><span class="sxs-lookup"><span data-stu-id="8f94f-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="8f94f-114">キューに入れ、実行するための関数および関数によって使用されるデータを格納しているオブジェクトを提供します。</span><span class="sxs-lookup"><span data-stu-id="8f94f-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="8f94f-115">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="8f94f-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="8f94f-116">ホストは、スレッド プールで保持できるスレッドの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="8f94f-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="8f94f-117">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="8f94f-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="8f94f-118">要求に応じるため、ホストを管理する必要があるアイドル状態のスレッドの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="8f94f-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f94f-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="8f94f-119">Remarks</span></span>  
 <span data-ttu-id="8f94f-120">ホストがへの呼び出しで指定された値を使用して、スレッド プールを構成する必要はありません、`SetMaxThreads`と`SetMinThreads`メソッド。</span><span class="sxs-lookup"><span data-stu-id="8f94f-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="8f94f-121">この場合、ホストは、これらのメソッドから HRESULT 値 E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f94f-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f94f-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f94f-122">Requirements</span></span>  
 <span data-ttu-id="8f94f-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f94f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f94f-124">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8f94f-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f94f-125">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8f94f-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8f94f-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8f94f-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f94f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f94f-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="8f94f-128">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f94f-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
