---
title: ICLRReferenceAssemblyEnum::Get メソッド
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a69e32d418478071f9b99a391e6bef9095d6f4ad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749921"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="fad82-102">ICLRReferenceAssemblyEnum::Get メソッド</span><span class="sxs-lookup"><span data-stu-id="fad82-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="fad82-103">指定したインデックス位置にあるアセンブリの id を取得します。</span><span class="sxs-lookup"><span data-stu-id="fad82-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fad82-104">構文</span><span class="sxs-lookup"><span data-stu-id="fad82-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fad82-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fad82-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="fad82-106">[in]アセンブリ id を返すの 0 から始まるインデックス。</span><span class="sxs-lookup"><span data-stu-id="fad82-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="fad82-107">[out]アセンブリの id データを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="fad82-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="fad82-108">[入力、出力]サイズ、`pwzBuffer`バッファー。</span><span class="sxs-lookup"><span data-stu-id="fad82-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fad82-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="fad82-109">Return Value</span></span>  
  
|<span data-ttu-id="fad82-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fad82-110">HRESULT</span></span>|<span data-ttu-id="fad82-111">説明</span><span class="sxs-lookup"><span data-stu-id="fad82-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fad82-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fad82-112">S_OK</span></span>|<span data-ttu-id="fad82-113">`Get` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="fad82-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="fad82-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="fad82-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="fad82-115">`pwzBuffer` が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="fad82-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="fad82-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="fad82-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="fad82-117">列挙には、これ以上項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fad82-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="fad82-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fad82-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fad82-119">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="fad82-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fad82-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fad82-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fad82-121">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="fad82-121">The call timed out.</span></span>|  
|<span data-ttu-id="fad82-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fad82-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fad82-123">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="fad82-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fad82-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fad82-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fad82-125">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="fad82-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fad82-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fad82-126">E_FAIL</span></span>|<span data-ttu-id="fad82-127">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fad82-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fad82-128">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fad82-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fad82-129">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fad82-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fad82-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="fad82-130">Remarks</span></span>  
 <span data-ttu-id="fad82-131">`Get` 通常は 2 回呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fad82-131">`Get` is typically called twice.</span></span> <span data-ttu-id="fad82-132">最初の呼び出しには、null 値が指定されています`pwzBuffer`、設定と`pcchBufferSize`の適切なサイズに`pwzBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="fad82-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="fad82-133">2 つ目の呼び出しが適切なサイズ指定されています`pwzBuffer`、完了すると標準アセンブリの id データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fad82-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fad82-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="fad82-134">Requirements</span></span>  
 <span data-ttu-id="fad82-135">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fad82-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fad82-136">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fad82-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fad82-137">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fad82-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fad82-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fad82-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad82-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="fad82-139">See also</span></span>

- [<span data-ttu-id="fad82-140">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fad82-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="fad82-141">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fad82-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
