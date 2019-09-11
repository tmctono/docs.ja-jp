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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b379bb2a9512cd1bd3344ed7f5130f96c0ccfa87
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855582"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="b97f3-102">IHostSecurityManager::GetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="b97f3-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="b97f3-103">ホストから要求された[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)を取得します。</span><span class="sxs-lookup"><span data-stu-id="b97f3-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b97f3-104">構文</span><span class="sxs-lookup"><span data-stu-id="b97f3-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b97f3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b97f3-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="b97f3-106">から[EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)値の1つ。返されるセキュリティコンテキストの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="b97f3-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="b97f3-107">入出力`IHostSecurityContext`のへの`eContextType`インターフェイスポインターのアドレス。</span><span class="sxs-lookup"><span data-stu-id="b97f3-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b97f3-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="b97f3-108">Return Value</span></span>  
  
|<span data-ttu-id="b97f3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b97f3-109">HRESULT</span></span>|<span data-ttu-id="b97f3-110">説明</span><span class="sxs-lookup"><span data-stu-id="b97f3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b97f3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b97f3-111">S_OK</span></span>|<span data-ttu-id="b97f3-112">`GetSecurityContext`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b97f3-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="b97f3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b97f3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b97f3-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b97f3-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b97f3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b97f3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b97f3-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b97f3-116">The call timed out.</span></span>|  
|<span data-ttu-id="b97f3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b97f3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b97f3-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b97f3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b97f3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b97f3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b97f3-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b97f3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b97f3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b97f3-121">E_FAIL</span></span>|<span data-ttu-id="b97f3-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b97f3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b97f3-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b97f3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b97f3-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b97f3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b97f3-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="b97f3-125">Remarks</span></span>  
 <span data-ttu-id="b97f3-126">ホストは、CLR とユーザーコードの両方によって、スレッドトークンへのすべてのコードアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b97f3-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="b97f3-127">また、完全なセキュリティコンテキスト情報が、制限されたコードアクセスで非同期操作またはコードポイント全体に渡されるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b97f3-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="b97f3-128">`IHostSecurityContext`CLR に対して非透過的なこのセキュリティコンテキスト情報をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="b97f3-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="b97f3-129">CLR は、この情報をキャプチャし、スレッドプールのワーカー項目のディスパッチ、ファイナライザーの実行、およびモジュールとクラスの構築の間で移動します。</span><span class="sxs-lookup"><span data-stu-id="b97f3-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b97f3-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="b97f3-130">Requirements</span></span>  
 <span data-ttu-id="b97f3-131">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b97f3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b97f3-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b97f3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b97f3-133">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b97f3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b97f3-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b97f3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b97f3-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b97f3-135">See also</span></span>

- [<span data-ttu-id="b97f3-136">EContextType 列挙型</span><span class="sxs-lookup"><span data-stu-id="b97f3-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="b97f3-137">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b97f3-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="b97f3-138">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b97f3-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
