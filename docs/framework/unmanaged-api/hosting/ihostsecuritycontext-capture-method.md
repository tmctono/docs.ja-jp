---
title: IHostSecurityContext::Capture メソッド
ms.date: 03/30/2017
api_name:
- IHostSecurityContext.Capture
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type:
- apiref
ms.openlocfilehash: e1df31ed8b652837a33b360b1378f99e6800cbea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501522"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="d511b-102">IHostSecurityContext::Capture メソッド</span><span class="sxs-lookup"><span data-stu-id="d511b-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="d511b-103">[IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md)への呼び出しから返された[IHostSecurityContext](ihostsecuritycontext-interface.md)インスタンスの複製を取得します。</span><span class="sxs-lookup"><span data-stu-id="d511b-103">Gets a clone of the [IHostSecurityContext](ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d511b-104">構文</span><span class="sxs-lookup"><span data-stu-id="d511b-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d511b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d511b-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="d511b-106">入出力キャプチャするオブジェクトの複製のアドレスへのポインター `IHostSecurityContext` 。</span><span class="sxs-lookup"><span data-stu-id="d511b-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d511b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d511b-107">Return Value</span></span>  
  
|<span data-ttu-id="d511b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d511b-108">HRESULT</span></span>|<span data-ttu-id="d511b-109">説明</span><span class="sxs-lookup"><span data-stu-id="d511b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d511b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d511b-110">S_OK</span></span>|<span data-ttu-id="d511b-111">`Capture`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="d511b-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="d511b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d511b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d511b-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="d511b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d511b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d511b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d511b-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="d511b-115">The call timed out.</span></span>|  
|<span data-ttu-id="d511b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d511b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d511b-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d511b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d511b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d511b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d511b-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="d511b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d511b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d511b-120">E_FAIL</span></span>|<span data-ttu-id="d511b-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d511b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d511b-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d511b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d511b-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d511b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d511b-124">解説</span><span class="sxs-lookup"><span data-stu-id="d511b-124">Remarks</span></span>  
 <span data-ttu-id="d511b-125">から返されるインターフェイスポインター `Capture` は、キャプチャされたコンテキストの複製です。</span><span class="sxs-lookup"><span data-stu-id="d511b-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="d511b-126">この情報が非同期コードポイント間で移動されると、その有効期間は、呼び出しが行われたポインターとは分離されます。</span><span class="sxs-lookup"><span data-stu-id="d511b-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="d511b-127">したがって、元のポインターは解放できます。</span><span class="sxs-lookup"><span data-stu-id="d511b-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d511b-128">要件</span><span class="sxs-lookup"><span data-stu-id="d511b-128">Requirements</span></span>  
 <span data-ttu-id="d511b-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d511b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d511b-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d511b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d511b-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d511b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d511b-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d511b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d511b-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d511b-133">See also</span></span>

- [<span data-ttu-id="d511b-134">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d511b-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="d511b-135">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d511b-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
