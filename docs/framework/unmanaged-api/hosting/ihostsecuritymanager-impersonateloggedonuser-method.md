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
ms.openlocfilehash: ada12a35691e0897a44f4f00e2e439fc08ef18af
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803903"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="1f6a3-102">IHostSecurityManager::ImpersonateLoggedOnUser メソッド</span><span class="sxs-lookup"><span data-stu-id="1f6a3-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="1f6a3-103">現在のユーザー id の資格情報を使用して、コードの実行を要求します。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f6a3-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f6a3-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f6a3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f6a3-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="1f6a3-106">から権限を借用するユーザーの資格情報を表すトークン。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f6a3-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="1f6a3-107">Return Value</span></span>  
  
|<span data-ttu-id="1f6a3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f6a3-108">HRESULT</span></span>|<span data-ttu-id="1f6a3-109">説明</span><span class="sxs-lookup"><span data-stu-id="1f6a3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f6a3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f6a3-110">S_OK</span></span>|<span data-ttu-id="1f6a3-111">`ImpersonateLoggedOnUser`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="1f6a3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1f6a3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1f6a3-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1f6a3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1f6a3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1f6a3-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-115">The call timed out.</span></span>|  
|<span data-ttu-id="1f6a3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1f6a3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1f6a3-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1f6a3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1f6a3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1f6a3-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1f6a3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1f6a3-120">E_FAIL</span></span>|<span data-ttu-id="1f6a3-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1f6a3-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1f6a3-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f6a3-124">解説</span><span class="sxs-lookup"><span data-stu-id="1f6a3-124">Remarks</span></span>  
 <span data-ttu-id="1f6a3-125">を呼び出す `LogonUser` か、または関連する Win32 関数を呼び出して、現在のユーザー id の資格情報を識別するハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="1f6a3-126">`HANDLE`この型は COM に準拠していません。つまり、そのサイズはオペレーティングシステムに固有であり、カスタムマーシャリングが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="1f6a3-127">したがって、このトークンは、CLR とホストの間でプロセス内でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f6a3-128">要件</span><span class="sxs-lookup"><span data-stu-id="1f6a3-128">Requirements</span></span>  
 <span data-ttu-id="1f6a3-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f6a3-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f6a3-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1f6a3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f6a3-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1f6a3-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f6a3-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f6a3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f6a3-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f6a3-133">See also</span></span>

- [<span data-ttu-id="1f6a3-134">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f6a3-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="1f6a3-135">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f6a3-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="1f6a3-136">RevertToSelf メソッド</span><span class="sxs-lookup"><span data-stu-id="1f6a3-136">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)
