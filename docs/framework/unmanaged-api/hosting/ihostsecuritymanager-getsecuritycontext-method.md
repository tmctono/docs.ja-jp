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
ms.openlocfilehash: 7198698edce48546c4f9a82ace18d5a6e71891ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176254"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="85352-102">IHostSecurityManager::GetSecurityContext メソッド</span><span class="sxs-lookup"><span data-stu-id="85352-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="85352-103">ホストから要求された[IHost セキュリティ コンテキスト](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)を取得します。</span><span class="sxs-lookup"><span data-stu-id="85352-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85352-104">構文</span><span class="sxs-lookup"><span data-stu-id="85352-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85352-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="85352-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="85352-106">[in]返すセキュリティ コンテキストの種類を示す[、EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="85352-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="85352-107">[アウト]のインターフェイス ポインタ`IHostSecurityContext`の`eContextType`アドレス。</span><span class="sxs-lookup"><span data-stu-id="85352-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85352-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="85352-108">Return Value</span></span>  
  
|<span data-ttu-id="85352-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85352-109">HRESULT</span></span>|<span data-ttu-id="85352-110">説明</span><span class="sxs-lookup"><span data-stu-id="85352-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85352-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="85352-111">S_OK</span></span>|<span data-ttu-id="85352-112">`GetSecurityContext`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="85352-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="85352-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85352-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85352-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="85352-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85352-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85352-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85352-116">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="85352-116">The call timed out.</span></span>|  
|<span data-ttu-id="85352-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85352-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85352-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="85352-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85352-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85352-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85352-120">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="85352-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85352-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85352-121">E_FAIL</span></span>|<span data-ttu-id="85352-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="85352-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85352-123">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="85352-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85352-124">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="85352-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85352-125">解説</span><span class="sxs-lookup"><span data-stu-id="85352-125">Remarks</span></span>  
 <span data-ttu-id="85352-126">ホストは、CLR とユーザー コードの両方で、スレッド トークンへのすべてのコード アクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="85352-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="85352-127">また、完全なセキュリティ コンテキスト情報が、コード アクセスが制限された非同期操作やコード ポイント間で確実に渡されるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="85352-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="85352-128">`IHostSecurityContext`は、CLR に対して不透明なこのセキュリティ コンテキスト情報をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="85352-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="85352-129">CLR は、この情報をキャプチャし、スレッド プールのワーカー アイテム のディスパッチ、ファイナライザの実行、およびモジュールとクラスの構築間で移動します。</span><span class="sxs-lookup"><span data-stu-id="85352-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85352-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="85352-130">Requirements</span></span>  
 <span data-ttu-id="85352-131">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85352-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85352-132">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85352-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85352-133">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="85352-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85352-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85352-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85352-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="85352-135">See also</span></span>

- [<span data-ttu-id="85352-136">EContextType 列挙型</span><span class="sxs-lookup"><span data-stu-id="85352-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="85352-137">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="85352-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="85352-138">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="85352-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
