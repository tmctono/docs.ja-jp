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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2c71f32dfd190e188bb28aad5d51c72160eb4bc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603213"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="a2ff5-102">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2ff5-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="a2ff5-103">アクセスと、現在実行中のスレッドのセキュリティ コンテキストに対する制御を許可するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2ff5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a2ff5-104">Methods</span></span>  
  
|<span data-ttu-id="a2ff5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a2ff5-105">Method</span></span>|<span data-ttu-id="a2ff5-106">説明</span><span class="sxs-lookup"><span data-stu-id="a2ff5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2ff5-107">GetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="a2ff5-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="a2ff5-108">要求された取得[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)ホストから。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="a2ff5-109">ImpersonateLoggedOnUser メソッド</span><span class="sxs-lookup"><span data-stu-id="a2ff5-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="a2ff5-110">要求の現在のユーザー id の資格情報を使用してコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="a2ff5-111">OpenThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="a2ff5-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="a2ff5-112">現在のスレッドに関連付けられた随意アクセス トークンを開きます。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="a2ff5-113">RevertToSelf メソッド</span><span class="sxs-lookup"><span data-stu-id="a2ff5-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="a2ff5-114">現在のユーザー id の権限の借用を終了し、元のスレッド トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="a2ff5-115">SetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="a2ff5-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="a2ff5-116">現在実行中のスレッドのセキュリティ コンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="a2ff5-117">SetThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="a2ff5-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="a2ff5-118">現在実行中のスレッドのハンドルを設定します。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2ff5-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2ff5-119">Remarks</span></span>  
 <span data-ttu-id="a2ff5-120">ホストは、共通言語ランタイム (CLR) とユーザー コードの両方で、スレッド トークンへのすべてのコード アクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="a2ff5-121">その完全なセキュリティを確保できますも非同期操作または制限付きのコード アクセス権を持つコード ポイントの間で渡されるコンテキスト情報。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="a2ff5-122">`IHostSecurityContext` CLR に非透過的であるこのセキュリティ コンテキスト情報をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="a2ff5-123">CLR では、マネージ スレッドのコンテキストを内部的に処理します。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="a2ff5-124">プロセス固有のクエリを実行`IHostSecurityManager`次の状況で。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="a2ff5-125">ファイナライザー スレッド、ファイナライザーの実行中です。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="a2ff5-126">実行中にクラスとモジュールのコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="a2ff5-127">呼び出しで、ワーカー スレッドで非同期の時点で、 [ihostthreadpoolmanager::queueuserworkitem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="a2ff5-128">I/O 完了ポートの使用中です。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2ff5-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2ff5-129">Requirements</span></span>  
 <span data-ttu-id="a2ff5-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2ff5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2ff5-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2ff5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2ff5-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a2ff5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2ff5-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2ff5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ff5-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2ff5-134">See also</span></span>

- [<span data-ttu-id="a2ff5-135">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2ff5-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="a2ff5-136">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2ff5-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
