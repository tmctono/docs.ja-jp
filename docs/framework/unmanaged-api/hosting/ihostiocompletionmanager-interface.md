---
title: IHostIoCompletionManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 51d79c398c94ec355528140325da2c25422cbad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133846"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="ff15f-102">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff15f-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="ff15f-103">共通言語ランタイム (CLR) がホストによって提供される i/o 完了ポートと対話できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff15f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-104">Methods</span></span>  
  
|<span data-ttu-id="ff15f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-105">Method</span></span>|<span data-ttu-id="ff15f-106">説明</span><span class="sxs-lookup"><span data-stu-id="ff15f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff15f-107">Bind メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="ff15f-108">I/o 完了ポートにハンドルをバインドします。</span><span class="sxs-lookup"><span data-stu-id="ff15f-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="ff15f-109">CloseIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="ff15f-110">以前の `CreateIoCompletionPort`の呼び出しで作成されたポートを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ff15f-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="ff15f-111">CreateIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="ff15f-112">ホストが新しい i/o 完了ポートを作成することを要求します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="ff15f-113">GetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="ff15f-114">現在要求を処理していない i/o 完了スレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="ff15f-115">GetHostOverlappedSize メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="ff15f-116">ホストが i/o 要求に追加しようとしているカスタムデータのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="ff15f-117">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="ff15f-118">ホストがサービス i/o 要求に割り当てることができるスレッドの最大数を取得します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="ff15f-119">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="ff15f-120">ホストが i/o 要求を処理するために提供するスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="ff15f-121">InitializeHostOverlapped メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="ff15f-122">I/o 要求に関するカスタムデータを初期化する機会をホストに提供します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="ff15f-123">SetCLRIoCompletionManager メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="ff15f-124">CLR によって実装されている[Iclrio提供マネージャー](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)インスタンスへのインターフェイスポインターをホストに提供します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="ff15f-125">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="ff15f-126">ホストが大量の i/o 要求を処理するスレッドの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="ff15f-127">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="ff15f-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="ff15f-128">ホストが i/o 完了に割り当てる必要があるスレッドの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff15f-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff15f-129">Remarks</span></span>  
 <span data-ttu-id="ff15f-130">`IHostIoCompletionManager` は、CLR によって実装される `ICLRIoCompletionManager` インターフェイスに対応します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="ff15f-131">CLR は、`IHostIoCompletionManager` のメソッドを呼び出して、ホストが提供するポートにハンドルをバインドします。また、ホストは、`ICLRIoCompletionManager` のメソッドを呼び出して、i/o 要求の完了を報告します。</span><span class="sxs-lookup"><span data-stu-id="ff15f-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff15f-132">［要件］</span><span class="sxs-lookup"><span data-stu-id="ff15f-132">Requirements</span></span>  
 <span data-ttu-id="ff15f-133">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff15f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff15f-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ff15f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff15f-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ff15f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff15f-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff15f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff15f-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff15f-137">See also</span></span>

- [<span data-ttu-id="ff15f-138">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff15f-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
