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
ms.openlocfilehash: 31d26ed6249bad8a7e2fbaab01264c1b32e1ff55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194475"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="8016f-102">ICLRReferenceAssemblyEnum::Get メソッド</span><span class="sxs-lookup"><span data-stu-id="8016f-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="8016f-103">指定したインデックス位置にあるアセンブリの id を取得します。</span><span class="sxs-lookup"><span data-stu-id="8016f-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8016f-104">構文</span><span class="sxs-lookup"><span data-stu-id="8016f-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8016f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8016f-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="8016f-106">[in]アセンブリ id を返すの 0 から始まるインデックス。</span><span class="sxs-lookup"><span data-stu-id="8016f-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="8016f-107">[out]アセンブリの id データを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="8016f-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="8016f-108">[入力、出力]サイズ、`pwzBuffer`バッファー。</span><span class="sxs-lookup"><span data-stu-id="8016f-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8016f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="8016f-109">Return Value</span></span>  
  
|<span data-ttu-id="8016f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8016f-110">HRESULT</span></span>|<span data-ttu-id="8016f-111">説明</span><span class="sxs-lookup"><span data-stu-id="8016f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8016f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8016f-112">S_OK</span></span>|`Get` <span data-ttu-id="8016f-113">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="8016f-113">returned successfully.</span></span>|  
|<span data-ttu-id="8016f-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="8016f-114">ERROR_INSUFFICIENT_BUFFER</span></span>|`pwzBuffer` <span data-ttu-id="8016f-115">小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="8016f-115">is too small.</span></span>|  
|<span data-ttu-id="8016f-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="8016f-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="8016f-117">列挙には、これ以上項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8016f-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="8016f-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8016f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8016f-119">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="8016f-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8016f-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8016f-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8016f-121">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="8016f-121">The call timed out.</span></span>|  
|<span data-ttu-id="8016f-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8016f-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8016f-123">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8016f-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8016f-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8016f-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8016f-125">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="8016f-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8016f-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8016f-126">E_FAIL</span></span>|<span data-ttu-id="8016f-127">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8016f-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8016f-128">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8016f-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8016f-129">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8016f-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8016f-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="8016f-130">Remarks</span></span>  
 `Get` <span data-ttu-id="8016f-131">通常は 2 回呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8016f-131">is typically called twice.</span></span> <span data-ttu-id="8016f-132">最初の呼び出しには、null 値が指定されています`pwzBuffer`、設定と`pcchBufferSize`の適切なサイズに`pwzBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="8016f-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="8016f-133">2 つ目の呼び出しが適切なサイズ指定されています`pwzBuffer`、完了すると標準アセンブリの id データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8016f-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8016f-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="8016f-134">Requirements</span></span>  
 <span data-ttu-id="8016f-135">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8016f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8016f-136">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8016f-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8016f-137">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8016f-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8016f-138">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8016f-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8016f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="8016f-139">See also</span></span>

- [<span data-ttu-id="8016f-140">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8016f-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8016f-141">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8016f-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
