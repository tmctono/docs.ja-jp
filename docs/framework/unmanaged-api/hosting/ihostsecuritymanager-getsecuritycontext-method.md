---
title: IHostSecurityManager::GetSecurityContext メソッド
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
ms.openlocfilehash: 66aab8081a5cce8c5ba986470bc91eb0604781a5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121513"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="c2272-102">IHostSecurityManager::GetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="c2272-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="c2272-103">ホストから要求された[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2272-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2272-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2272-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2272-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2272-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="c2272-106">から[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)値の1つ。返されるセキュリティコンテキストの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c2272-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="c2272-107">入出力`eContextType`の `IHostSecurityContext` へのインターフェイスポインターのアドレス。</span><span class="sxs-lookup"><span data-stu-id="c2272-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2272-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c2272-108">Return Value</span></span>  
  
|<span data-ttu-id="c2272-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2272-109">HRESULT</span></span>|<span data-ttu-id="c2272-110">説明</span><span class="sxs-lookup"><span data-stu-id="c2272-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2272-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2272-111">S_OK</span></span>|<span data-ttu-id="c2272-112">`GetSecurityContext` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="c2272-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="c2272-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2272-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2272-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="c2272-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2272-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2272-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2272-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="c2272-116">The call timed out.</span></span>|  
|<span data-ttu-id="c2272-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2272-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2272-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c2272-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2272-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2272-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2272-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="c2272-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2272-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2272-121">E_FAIL</span></span>|<span data-ttu-id="c2272-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c2272-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2272-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c2272-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2272-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c2272-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2272-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2272-125">Remarks</span></span>  
 <span data-ttu-id="c2272-126">ホストは、CLR とユーザーコードの両方によって、スレッドトークンへのすべてのコードアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c2272-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="c2272-127">また、完全なセキュリティコンテキスト情報が、制限されたコードアクセスで非同期操作またはコードポイント全体に渡されるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c2272-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="c2272-128">`IHostSecurityContext` は、CLR に対して非透過的なこのセキュリティコンテキスト情報をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="c2272-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="c2272-129">CLR は、この情報をキャプチャし、スレッドプールのワーカー項目のディスパッチ、ファイナライザーの実行、およびモジュールとクラスの構築の間で移動します。</span><span class="sxs-lookup"><span data-stu-id="c2272-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2272-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="c2272-130">Requirements</span></span>  
 <span data-ttu-id="c2272-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2272-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2272-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c2272-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2272-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c2272-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2272-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2272-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2272-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2272-135">See also</span></span>

- [<span data-ttu-id="c2272-136">EContextType 列挙型</span><span class="sxs-lookup"><span data-stu-id="c2272-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="c2272-137">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2272-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c2272-138">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2272-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
