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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0f6ae812b64080a2c4d236a2be02ad81c4a11b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193305"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="146bd-102">IHostSecurityContext::Capture メソッド</span><span class="sxs-lookup"><span data-stu-id="146bd-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="146bd-103">複製を取得、 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)への呼び出しから返されるインスタンス[ihostsecuritymanager::getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="146bd-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="146bd-104">構文</span><span class="sxs-lookup"><span data-stu-id="146bd-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="146bd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="146bd-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="146bd-106">[out]複製のアドレスへのポインター、`IHostSecurityContext`キャプチャするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="146bd-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="146bd-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="146bd-107">Return Value</span></span>  
  
|<span data-ttu-id="146bd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="146bd-108">HRESULT</span></span>|<span data-ttu-id="146bd-109">説明</span><span class="sxs-lookup"><span data-stu-id="146bd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="146bd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="146bd-110">S_OK</span></span>|<span data-ttu-id="146bd-111">`Capture` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="146bd-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="146bd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="146bd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="146bd-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="146bd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="146bd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="146bd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="146bd-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="146bd-115">The call timed out.</span></span>|  
|<span data-ttu-id="146bd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="146bd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="146bd-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="146bd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="146bd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="146bd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="146bd-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="146bd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="146bd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="146bd-120">E_FAIL</span></span>|<span data-ttu-id="146bd-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="146bd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="146bd-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="146bd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="146bd-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="146bd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="146bd-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="146bd-124">Remarks</span></span>  
 <span data-ttu-id="146bd-125">返されるインターフェイス ポインター`Capture`はキャプチャされたコンテキストのクローンであります。</span><span class="sxs-lookup"><span data-stu-id="146bd-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="146bd-126">この情報は、非同期のコード ポイント間で移動が、ときに呼び出しが行われたポインターをその有効期間が区切られます。</span><span class="sxs-lookup"><span data-stu-id="146bd-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="146bd-127">元のポインターを解放できることができます。</span><span class="sxs-lookup"><span data-stu-id="146bd-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="146bd-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="146bd-128">Requirements</span></span>  
 <span data-ttu-id="146bd-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="146bd-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="146bd-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="146bd-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="146bd-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="146bd-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="146bd-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="146bd-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="146bd-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="146bd-133">See also</span></span>

- [<span data-ttu-id="146bd-134">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="146bd-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="146bd-135">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="146bd-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
