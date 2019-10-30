---
title: IHostSecurityManager::OpenThreadToken メソッド
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 2ced153798355aff882f0244f3dd946c39dea2bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121469"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="b9d04-102">IHostSecurityManager::OpenThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="b9d04-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="b9d04-103">現在実行中のスレッドに関連付けられている随意アクセストークンを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9d04-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9d04-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9d04-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9d04-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9d04-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="b9d04-106">からスレッドトークンへの要求されたアクセスの種類を指定するアクセス値のマスク。</span><span class="sxs-lookup"><span data-stu-id="b9d04-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="b9d04-107">これらの値は、Win32 `OpenThreadToken` 関数で定義されています。</span><span class="sxs-lookup"><span data-stu-id="b9d04-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="b9d04-108">要求されたアクセスの種類は、付与または拒否するアクセスの種類を決定するために、トークンの随意アクセス制御リスト (DACL) に対して調整されます。</span><span class="sxs-lookup"><span data-stu-id="b9d04-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="b9d04-109">[in] 呼び出し元スレッドのプロセスのセキュリティコンテキストを使用してアクセスチェックを行うように指定するには `true` ます。`false`、呼び出し元のスレッド自体のセキュリティコンテキストを使用してアクセスチェックを実行するように指定します。</span><span class="sxs-lookup"><span data-stu-id="b9d04-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="b9d04-110">スレッドがクライアントを偽装している場合は、クライアントプロセスのセキュリティコンテキストになります。</span><span class="sxs-lookup"><span data-stu-id="b9d04-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="b9d04-111">入出力新しく開かれたアクセストークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b9d04-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9d04-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="b9d04-112">Return Value</span></span>  
  
|<span data-ttu-id="b9d04-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9d04-113">HRESULT</span></span>|<span data-ttu-id="b9d04-114">説明</span><span class="sxs-lookup"><span data-stu-id="b9d04-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9d04-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9d04-115">S_OK</span></span>|<span data-ttu-id="b9d04-116">`OpenThreadToken` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b9d04-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="b9d04-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9d04-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9d04-118">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b9d04-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9d04-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9d04-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9d04-120">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b9d04-120">The call timed out.</span></span>|  
|<span data-ttu-id="b9d04-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9d04-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9d04-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b9d04-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9d04-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9d04-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9d04-124">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b9d04-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9d04-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9d04-125">E_FAIL</span></span>|<span data-ttu-id="b9d04-126">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b9d04-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9d04-127">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b9d04-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9d04-128">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b9d04-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9d04-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9d04-129">Remarks</span></span>  
 <span data-ttu-id="b9d04-130">`IHostSecurityManager::OpenThreadToken` は、同じ名前の対応する Win32 関数と同じように動作します。ただし、Win32 関数では、呼び出し元が任意のスレッドへのハンドルを渡すことを許可し、`IHostSecurityManager::OpenThreadToken` は呼び出し元のスレッドに関連付けられているトークンのみを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="b9d04-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="b9d04-131">`HANDLE` 型は COM に準拠していません。つまり、そのサイズはオペレーティングシステムに固有であり、カスタムマーシャリングが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9d04-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="b9d04-132">したがって、このトークンは、CLR とホストの間でプロセス内でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9d04-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9d04-133">［要件］</span><span class="sxs-lookup"><span data-stu-id="b9d04-133">Requirements</span></span>  
 <span data-ttu-id="b9d04-134">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9d04-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9d04-135">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b9d04-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9d04-136">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b9d04-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9d04-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9d04-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d04-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9d04-138">See also</span></span>

- [<span data-ttu-id="b9d04-139">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9d04-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="b9d04-140">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9d04-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
