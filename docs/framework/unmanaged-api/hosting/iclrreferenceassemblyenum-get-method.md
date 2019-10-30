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
ms.openlocfilehash: 8f479443e168c3fc7c627c3227e59f1e8b54f0e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120501"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="4ca40-102">ICLRReferenceAssemblyEnum::Get メソッド</span><span class="sxs-lookup"><span data-stu-id="4ca40-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="4ca40-103">指定されたインデックス位置にあるアセンブリ id を取得します。</span><span class="sxs-lookup"><span data-stu-id="4ca40-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca40-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ca40-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ca40-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ca40-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="4ca40-106">から返されるアセンブリ id の0から始まるインデックス。</span><span class="sxs-lookup"><span data-stu-id="4ca40-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="4ca40-107">入出力アセンブリ id データを格納しているバッファー。</span><span class="sxs-lookup"><span data-stu-id="4ca40-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="4ca40-108">[入力、出力]`pwzBuffer` バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="4ca40-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ca40-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4ca40-109">Return Value</span></span>  
  
|<span data-ttu-id="4ca40-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ca40-110">HRESULT</span></span>|<span data-ttu-id="4ca40-111">説明</span><span class="sxs-lookup"><span data-stu-id="4ca40-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ca40-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ca40-112">S_OK</span></span>|<span data-ttu-id="4ca40-113">`Get` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4ca40-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="4ca40-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4ca40-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4ca40-115">`pwzBuffer` が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="4ca40-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="4ca40-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="4ca40-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="4ca40-117">列挙には、これ以上項目が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="4ca40-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="4ca40-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4ca40-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4ca40-119">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="4ca40-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4ca40-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4ca40-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4ca40-121">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="4ca40-121">The call timed out.</span></span>|  
|<span data-ttu-id="4ca40-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4ca40-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4ca40-123">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4ca40-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4ca40-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4ca40-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4ca40-125">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="4ca40-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4ca40-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ca40-126">E_FAIL</span></span>|<span data-ttu-id="4ca40-127">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4ca40-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4ca40-128">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4ca40-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4ca40-129">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4ca40-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ca40-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ca40-130">Remarks</span></span>  
 <span data-ttu-id="4ca40-131">通常、`Get` は2回呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4ca40-131">`Get` is typically called twice.</span></span> <span data-ttu-id="4ca40-132">最初の呼び出しでは `pwzBuffer`に null 値を指定し、`pcchBufferSize` を `pwzBuffer`に適したサイズに設定します。</span><span class="sxs-lookup"><span data-stu-id="4ca40-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="4ca40-133">2番目の呼び出しでは、適切にサイズ設定された `pwzBuffer`を渡し、完了時に正規のアセンブリ id データを格納します。</span><span class="sxs-lookup"><span data-stu-id="4ca40-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ca40-134">［要件］</span><span class="sxs-lookup"><span data-stu-id="4ca40-134">Requirements</span></span>  
 <span data-ttu-id="4ca40-135">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ca40-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ca40-136">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4ca40-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ca40-137">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4ca40-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ca40-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ca40-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca40-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ca40-139">See also</span></span>

- [<span data-ttu-id="4ca40-140">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ca40-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4ca40-141">ICLRReferenceAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ca40-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
