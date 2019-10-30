---
title: IHostSecurityManager::RevertToSelf メソッド
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
ms.openlocfilehash: b896c5509cc4862a6416381f89bc04a28959e091
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121450"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="5e88f-102">IHostSecurityManager::RevertToSelf メソッド</span><span class="sxs-lookup"><span data-stu-id="5e88f-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="5e88f-103">現在のユーザー id の偽装を終了し、元のスレッドトークンを返します。</span><span class="sxs-lookup"><span data-stu-id="5e88f-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e88f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e88f-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5e88f-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="5e88f-105">Return Value</span></span>  
  
|<span data-ttu-id="5e88f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e88f-106">HRESULT</span></span>|<span data-ttu-id="5e88f-107">説明</span><span class="sxs-lookup"><span data-stu-id="5e88f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e88f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e88f-108">S_OK</span></span>|<span data-ttu-id="5e88f-109">`RevertToSelf` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="5e88f-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="5e88f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e88f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e88f-111">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="5e88f-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e88f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e88f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e88f-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="5e88f-113">The call timed out.</span></span>|  
|<span data-ttu-id="5e88f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e88f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e88f-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5e88f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e88f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e88f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e88f-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5e88f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e88f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e88f-118">E_FAIL</span></span>|<span data-ttu-id="5e88f-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5e88f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e88f-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5e88f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e88f-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5e88f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e88f-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e88f-122">Remarks</span></span>  
 <span data-ttu-id="5e88f-123">[ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)メソッドを以前に呼び出した後、元のスレッドトークンに戻るために `RevertToSelf` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5e88f-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e88f-124">［要件］</span><span class="sxs-lookup"><span data-stu-id="5e88f-124">Requirements</span></span>  
 <span data-ttu-id="5e88f-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e88f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e88f-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5e88f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e88f-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5e88f-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e88f-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e88f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e88f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e88f-129">See also</span></span>

- [<span data-ttu-id="5e88f-130">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e88f-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="5e88f-131">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e88f-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="5e88f-132">ImpersonateLoggedOnUser メソッド</span><span class="sxs-lookup"><span data-stu-id="5e88f-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
