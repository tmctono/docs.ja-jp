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
ms.openlocfilehash: b2c334c7a757c2f4044d08787bdae93ffc2804e4
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803894"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="d3aa5-102">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3aa5-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="d3aa5-103">現在実行中のスレッドのセキュリティコンテキストに対するアクセスと制御を許可するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3aa5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d3aa5-104">Methods</span></span>  
  
|<span data-ttu-id="d3aa5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d3aa5-105">Method</span></span>|<span data-ttu-id="d3aa5-106">説明</span><span class="sxs-lookup"><span data-stu-id="d3aa5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3aa5-107">GetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="d3aa5-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="d3aa5-108">ホストから要求された[IHostSecurityContext](ihostsecuritycontext-interface.md)を取得します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-108">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="d3aa5-109">ImpersonateLoggedOnUser メソッド</span><span class="sxs-lookup"><span data-stu-id="d3aa5-109">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="d3aa5-110">現在のユーザー id の資格情報を使用して、コードの実行を要求します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="d3aa5-111">OpenThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="d3aa5-111">OpenThreadToken Method</span></span>](ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="d3aa5-112">現在のスレッドに関連付けられている随意アクセストークンを開きます。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="d3aa5-113">RevertToSelf メソッド</span><span class="sxs-lookup"><span data-stu-id="d3aa5-113">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="d3aa5-114">現在のユーザー id の偽装を終了し、元のスレッドトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="d3aa5-115">SetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="d3aa5-115">SetSecurityContext Method</span></span>](ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="d3aa5-116">現在実行中のスレッドのセキュリティコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="d3aa5-117">SetThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="d3aa5-117">SetThreadToken Method</span></span>](ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="d3aa5-118">現在実行中のスレッドのハンドルを設定します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3aa5-119">解説</span><span class="sxs-lookup"><span data-stu-id="d3aa5-119">Remarks</span></span>  
 <span data-ttu-id="d3aa5-120">ホストは、共通言語ランタイム (CLR) とユーザーコードの両方によって、スレッドトークンへのすべてのコードアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="d3aa5-121">また、完全なセキュリティコンテキスト情報が、制限されたコードアクセスで非同期操作またはコードポイント全体に渡されるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="d3aa5-122">`IHostSecurityContext`CLR に対して非透過的なこのセキュリティコンテキスト情報をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="d3aa5-123">CLR は、マネージスレッドコンテキストを内部で処理します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="d3aa5-124">次のような状況で、プロセス固有のクエリが実行され `IHostSecurityManager` ます。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="d3aa5-125">ファイナライザーの実行中に発生します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="d3aa5-126">クラスおよびモジュールコンストラクターの実行中。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="d3aa5-127">ワーカースレッドの非同期ポイントで、 [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="d3aa5-128">I/o 完了ポートのサービス。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3aa5-129">要件</span><span class="sxs-lookup"><span data-stu-id="d3aa5-129">Requirements</span></span>  
 <span data-ttu-id="d3aa5-130">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3aa5-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3aa5-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d3aa5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3aa5-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d3aa5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3aa5-133">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3aa5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3aa5-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3aa5-134">See also</span></span>

- [<span data-ttu-id="d3aa5-135">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3aa5-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="d3aa5-136">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3aa5-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
