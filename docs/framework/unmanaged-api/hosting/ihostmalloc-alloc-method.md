---
title: IHostMAlloc::Alloc メソッド
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
ms.openlocfilehash: dded37fdef02963f60883b289462aa6a96693b3d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176306"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="67561-102">IHostMAlloc::Alloc メソッド</span><span class="sxs-lookup"><span data-stu-id="67561-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="67561-103">ホストに、ヒープから指定された量のメモリを割り当てすることを要求します。</span><span class="sxs-lookup"><span data-stu-id="67561-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67561-104">構文</span><span class="sxs-lookup"><span data-stu-id="67561-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67561-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67561-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="67561-106">[in]現在のメモリ割り当て要求のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="67561-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="67561-107">[in]割り当てエラーの影響を示す[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="67561-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="67561-108">[アウト]割り当てられたメモリへのポインター、または null 要求を完了できなかった場合。</span><span class="sxs-lookup"><span data-stu-id="67561-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67561-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="67561-109">Return Value</span></span>  
  
|<span data-ttu-id="67561-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67561-110">HRESULT</span></span>|<span data-ttu-id="67561-111">説明</span><span class="sxs-lookup"><span data-stu-id="67561-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67561-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="67561-112">S_OK</span></span>|<span data-ttu-id="67561-113">`Alloc`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="67561-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="67561-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67561-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67561-115">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="67561-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67561-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67561-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67561-117">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="67561-117">The call timed out.</span></span>|  
|<span data-ttu-id="67561-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67561-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67561-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="67561-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67561-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67561-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67561-121">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="67561-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67561-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67561-122">E_FAIL</span></span>|<span data-ttu-id="67561-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="67561-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67561-124">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="67561-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67561-125">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="67561-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="67561-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="67561-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="67561-127">メモリ不足で、割り当て要求を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="67561-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67561-128">解説</span><span class="sxs-lookup"><span data-stu-id="67561-128">Remarks</span></span>  
 <span data-ttu-id="67561-129">CLR は、メソッドを`IHostMalloc`呼び出すことによって、インスタンスへのインターフェイス ポインター[を](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)取得します。</span><span class="sxs-lookup"><span data-stu-id="67561-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67561-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="67561-130">Requirements</span></span>  
 <span data-ttu-id="67561-131">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67561-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67561-132">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67561-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67561-133">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="67561-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67561-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67561-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67561-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="67561-135">See also</span></span>

- [<span data-ttu-id="67561-136">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67561-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="67561-137">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67561-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
