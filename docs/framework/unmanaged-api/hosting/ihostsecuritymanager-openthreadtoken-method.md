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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68ebfdcd0ef34edec724a044791d05dd48580b12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697486"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="fbf77-102">IHostSecurityManager::OpenThreadToken メソッド</span><span class="sxs-lookup"><span data-stu-id="fbf77-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="fbf77-103">現在実行中のスレッドに関連付けられた随意アクセス トークンを開きます。</span><span class="sxs-lookup"><span data-stu-id="fbf77-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf77-104">構文</span><span class="sxs-lookup"><span data-stu-id="fbf77-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbf77-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbf77-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="fbf77-106">[in]スレッド トークンへのアクセスの要求の種類を指定するアクセスの値のマスク。</span><span class="sxs-lookup"><span data-stu-id="fbf77-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="fbf77-107">これらの値は、Win32 で定義されている`OpenThreadToken`関数。</span><span class="sxs-lookup"><span data-stu-id="fbf77-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="fbf77-108">要求されたアクセス タイプは、トークンの随意アクセス制御リスト (DACL) へのアクセスを許可または拒否の種類を決定するに対して調整します。</span><span class="sxs-lookup"><span data-stu-id="fbf77-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="fbf77-109">[in]`true`呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用して、アクセス チェックが行われることを指定するには`false`自体、呼び出し元スレッドのセキュリティ コンテキストを使用して、アクセス チェックを実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbf77-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="fbf77-110">スレッドは、クライアントを偽装する場合のクライアント プロセスをセキュリティ コンテキストにできます。</span><span class="sxs-lookup"><span data-stu-id="fbf77-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="fbf77-111">[out]新しく開かれたアクセス トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fbf77-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbf77-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="fbf77-112">Return Value</span></span>  
  
|<span data-ttu-id="fbf77-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbf77-113">HRESULT</span></span>|<span data-ttu-id="fbf77-114">説明</span><span class="sxs-lookup"><span data-stu-id="fbf77-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbf77-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbf77-115">S_OK</span></span>|<span data-ttu-id="fbf77-116">`OpenThreadToken` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="fbf77-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="fbf77-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fbf77-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fbf77-118">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="fbf77-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fbf77-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fbf77-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fbf77-120">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="fbf77-120">The call timed out.</span></span>|  
|<span data-ttu-id="fbf77-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fbf77-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fbf77-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="fbf77-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fbf77-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fbf77-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fbf77-124">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="fbf77-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fbf77-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fbf77-125">E_FAIL</span></span>|<span data-ttu-id="fbf77-126">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fbf77-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fbf77-127">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fbf77-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fbf77-128">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fbf77-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbf77-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="fbf77-129">Remarks</span></span>  
 <span data-ttu-id="fbf77-130">`IHostSecurityManager::OpenThreadToken` 動作は同様に、同じ名前の対応する Win32 関数に点を除いて、呼び出し元に渡す任意のスレッドのハンドルで Win32 関数は、中にされた`IHostSecurityManager::OpenThreadToken`呼び出し元のスレッドに関連付けられているトークンのみを開きます。</span><span class="sxs-lookup"><span data-stu-id="fbf77-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="fbf77-131">`HANDLE`型は COM に準拠していない、つまり、そのサイズは、オペレーティング システムに固有およびカスタム マーシャ リングが必要です。</span><span class="sxs-lookup"><span data-stu-id="fbf77-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="fbf77-132">したがって、このトークンは、CLR とホスト間、プロセス内でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="fbf77-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbf77-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="fbf77-133">Requirements</span></span>  
 <span data-ttu-id="fbf77-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbf77-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbf77-135">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fbf77-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbf77-136">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fbf77-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbf77-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbf77-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf77-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbf77-138">See also</span></span>

- [<span data-ttu-id="fbf77-139">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbf77-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="fbf77-140">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fbf77-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
