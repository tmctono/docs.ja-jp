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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32499e74e8af9a865347bd800d3db4c303a7344c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796735"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="876a7-102">IHostMAlloc::Alloc メソッド</span><span class="sxs-lookup"><span data-stu-id="876a7-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="876a7-103">ホストが、ヒープから指定されたメモリ量を割り当てることを要求します。</span><span class="sxs-lookup"><span data-stu-id="876a7-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="876a7-104">構文</span><span class="sxs-lookup"><span data-stu-id="876a7-104">Syntax</span></span>  
  
```  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="876a7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="876a7-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="876a7-106">[in]現在のメモリ割り当て要求のバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="876a7-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="876a7-107">[in]1 つ、 [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)割り当てエラーの影響を示す値。</span><span class="sxs-lookup"><span data-stu-id="876a7-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="876a7-108">[out]割り当てられたメモリは、または null の場合は、要求を完了できませんでしたへのポインター。</span><span class="sxs-lookup"><span data-stu-id="876a7-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="876a7-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="876a7-109">Return Value</span></span>  
  
|<span data-ttu-id="876a7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="876a7-110">HRESULT</span></span>|<span data-ttu-id="876a7-111">説明</span><span class="sxs-lookup"><span data-stu-id="876a7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="876a7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="876a7-112">S_OK</span></span>|<span data-ttu-id="876a7-113">`Alloc` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="876a7-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="876a7-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="876a7-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="876a7-115">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="876a7-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="876a7-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="876a7-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="876a7-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="876a7-117">The call timed out.</span></span>|  
|<span data-ttu-id="876a7-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="876a7-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="876a7-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="876a7-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="876a7-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="876a7-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="876a7-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="876a7-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="876a7-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="876a7-122">E_FAIL</span></span>|<span data-ttu-id="876a7-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="876a7-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="876a7-124">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="876a7-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="876a7-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="876a7-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="876a7-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="876a7-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="876a7-127">十分なメモリ割り当て要求を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="876a7-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="876a7-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="876a7-128">Remarks</span></span>  
 <span data-ttu-id="876a7-129">CLR へのインターフェイス ポインターの取得、`IHostMalloc`インスタンスを呼び出すことによって、 [ihostmemorymanager::createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="876a7-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="876a7-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="876a7-130">Requirements</span></span>  
 <span data-ttu-id="876a7-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="876a7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="876a7-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="876a7-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="876a7-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="876a7-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="876a7-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="876a7-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="876a7-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="876a7-135">See also</span></span>

- [<span data-ttu-id="876a7-136">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="876a7-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="876a7-137">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="876a7-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
