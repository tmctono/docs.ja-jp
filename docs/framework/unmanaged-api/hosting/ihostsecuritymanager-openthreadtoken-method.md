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
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176267"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="2ffee-102">IHostSecurityManager::OpenThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="2ffee-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="2ffee-103">現在実行中のスレッドに関連付けられている任意のアクセス トークンを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ffee-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ffee-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ffee-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ffee-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ffee-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="2ffee-106">[in]スレッド トークンへのアクセスの要求された種類を指定するアクセス値のマスク。</span><span class="sxs-lookup"><span data-stu-id="2ffee-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="2ffee-107">これらの値は Win32`OpenThreadToken`関数で定義されます。</span><span class="sxs-lookup"><span data-stu-id="2ffee-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="2ffee-108">要求されたアクセスの種類は、トークンの随意アクセス制御リスト (DACL) に対して調整され、許可または拒否するアクセスの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="2ffee-109">[in]`true`呼び出し元スレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを行うことを指定します。`false`呼び出し元スレッド自体のセキュリティ コンテキストを使用してアクセス チェックを実行するように指定します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="2ffee-110">スレッドがクライアントを偽装している場合、セキュリティ コンテキストはクライアント プロセスのコンテキストにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2ffee-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="2ffee-111">[アウト]新しく開いたアクセス トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2ffee-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ffee-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="2ffee-112">Return Value</span></span>  
  
|<span data-ttu-id="2ffee-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ffee-113">HRESULT</span></span>|<span data-ttu-id="2ffee-114">説明</span><span class="sxs-lookup"><span data-stu-id="2ffee-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ffee-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ffee-115">S_OK</span></span>|<span data-ttu-id="2ffee-116">`OpenThreadToken`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="2ffee-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="2ffee-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ffee-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ffee-118">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ffee-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2ffee-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2ffee-120">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="2ffee-120">The call timed out.</span></span>|  
|<span data-ttu-id="2ffee-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2ffee-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2ffee-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2ffee-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2ffee-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2ffee-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2ffee-124">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="2ffee-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2ffee-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ffee-125">E_FAIL</span></span>|<span data-ttu-id="2ffee-126">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2ffee-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ffee-127">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2ffee-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ffee-128">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ffee-129">解説</span><span class="sxs-lookup"><span data-stu-id="2ffee-129">Remarks</span></span>  
 <span data-ttu-id="2ffee-130">`IHostSecurityManager::OpenThreadToken`Win32 関数では、呼び出し元が任意のスレッドにハンドルを渡し、呼び出し元スレッドに関連付けられたトークンのみを`IHostSecurityManager::OpenThreadToken`開くことを許可する点を除いて、同じ名前の対応する Win32 関数と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="2ffee-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="2ffee-131">型`HANDLE`は COM に準拠していない、つまり、そのサイズはオペレーティング システムに固有であり、カスタム マーシャリングが必要です。</span><span class="sxs-lookup"><span data-stu-id="2ffee-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="2ffee-132">したがって、このトークンは、プロセス内で、CLR とホストの間でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ffee-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ffee-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="2ffee-133">Requirements</span></span>  
 <span data-ttu-id="2ffee-134">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ffee-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ffee-135">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ffee-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ffee-136">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="2ffee-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ffee-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ffee-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ffee-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ffee-138">See also</span></span>

- [<span data-ttu-id="2ffee-139">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ffee-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="2ffee-140">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ffee-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
