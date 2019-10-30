---
title: IHostSecurityManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: 9b7cc41848e41976f388e38bf22c9ea0f90abbae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121476"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="4ff4a-102">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ff4a-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="4ff4a-103">現在実行中のスレッドのセキュリティコンテキストに対するアクセスと制御を許可するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ff4a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4ff4a-104">Methods</span></span>  
  
|<span data-ttu-id="4ff4a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4ff4a-105">Method</span></span>|<span data-ttu-id="4ff4a-106">説明</span><span class="sxs-lookup"><span data-stu-id="4ff4a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4ff4a-107">GetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="4ff4a-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="4ff4a-108">ホストから要求された[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)を取得します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="4ff4a-109">ImpersonateLoggedOnUser メソッド</span><span class="sxs-lookup"><span data-stu-id="4ff4a-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="4ff4a-110">現在のユーザー id の資格情報を使用して、コードの実行を要求します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="4ff4a-111">OpenThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="4ff4a-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="4ff4a-112">現在のスレッドに関連付けられている随意アクセストークンを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="4ff4a-113">RevertToSelf メソッド</span><span class="sxs-lookup"><span data-stu-id="4ff4a-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="4ff4a-114">現在のユーザー id の偽装を終了し、元のスレッドトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="4ff4a-115">SetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="4ff4a-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="4ff4a-116">現在実行中のスレッドのセキュリティコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="4ff4a-117">SetThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="4ff4a-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="4ff4a-118">現在実行中のスレッドのハンドルを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ff4a-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ff4a-119">Remarks</span></span>  
 <span data-ttu-id="4ff4a-120">ホストは、共通言語ランタイム (CLR) とユーザーコードの両方によって、スレッドトークンへのすべてのコードアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="4ff4a-121">また、完全なセキュリティコンテキスト情報が、制限されたコードアクセスで非同期操作またはコードポイント全体に渡されるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="4ff4a-122">`IHostSecurityContext` は、CLR に対して非透過的なこのセキュリティコンテキスト情報をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="4ff4a-123">CLR は、マネージスレッドコンテキストを内部で処理します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="4ff4a-124">次のような場合に、プロセス固有の `IHostSecurityManager` に対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="4ff4a-125">ファイナライザーの実行中に発生します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="4ff4a-126">クラスおよびモジュールコンストラクターの実行中。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="4ff4a-127">ワーカースレッドの非同期ポイントで、 [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="4ff4a-128">I/o 完了ポートのサービス。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ff4a-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="4ff4a-129">Requirements</span></span>  
 <span data-ttu-id="4ff4a-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ff4a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ff4a-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4ff4a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ff4a-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4ff4a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ff4a-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ff4a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff4a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ff4a-134">See also</span></span>

- [<span data-ttu-id="4ff4a-135">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ff4a-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="4ff4a-136">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ff4a-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
