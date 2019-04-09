---
title: IHostSecurityManager::ImpersonateLoggedOnUser メソッド
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ebf9ad72f7a1b0dd7ac54afa104089182f122ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109890"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="7bf99-102">IHostSecurityManager::ImpersonateLoggedOnUser メソッド</span><span class="sxs-lookup"><span data-stu-id="7bf99-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="7bf99-103">要求の現在のユーザー id の資格情報を使用してコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bf99-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf99-104">構文</span><span class="sxs-lookup"><span data-stu-id="7bf99-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bf99-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7bf99-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="7bf99-106">[in]権限を借用するユーザーの資格情報を表すトークンです。</span><span class="sxs-lookup"><span data-stu-id="7bf99-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bf99-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7bf99-107">Return Value</span></span>  
  
|<span data-ttu-id="7bf99-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7bf99-108">HRESULT</span></span>|<span data-ttu-id="7bf99-109">説明</span><span class="sxs-lookup"><span data-stu-id="7bf99-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7bf99-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7bf99-110">S_OK</span></span>|`ImpersonateLoggedOnUser` <span data-ttu-id="7bf99-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="7bf99-111">returned successfully.</span></span>|  
|<span data-ttu-id="7bf99-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7bf99-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7bf99-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="7bf99-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7bf99-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7bf99-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7bf99-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="7bf99-115">The call timed out.</span></span>|  
|<span data-ttu-id="7bf99-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7bf99-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7bf99-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7bf99-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7bf99-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7bf99-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7bf99-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="7bf99-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7bf99-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7bf99-120">E_FAIL</span></span>|<span data-ttu-id="7bf99-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7bf99-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7bf99-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7bf99-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7bf99-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7bf99-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bf99-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="7bf99-124">Remarks</span></span>  
 <span data-ttu-id="7bf99-125">呼び出す`LogonUser`または関連する Win32 関数を現在のユーザー id の資格情報を識別するハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="7bf99-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="7bf99-126">`HANDLE`型は COM に準拠していない、つまり、そのサイズは、オペレーティング システムに固有およびカスタム マーシャ リングが必要です。</span><span class="sxs-lookup"><span data-stu-id="7bf99-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="7bf99-127">したがって、このトークンは、CLR とホスト間、プロセス内でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="7bf99-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bf99-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="7bf99-128">Requirements</span></span>  
 <span data-ttu-id="7bf99-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bf99-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bf99-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7bf99-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7bf99-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7bf99-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7bf99-132">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="7bf99-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7bf99-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bf99-133">See also</span></span>

- [<span data-ttu-id="7bf99-134">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7bf99-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="7bf99-135">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7bf99-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="7bf99-136">RevertToSelf メソッド</span><span class="sxs-lookup"><span data-stu-id="7bf99-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
