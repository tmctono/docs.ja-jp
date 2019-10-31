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
ms.openlocfilehash: 9837e4e3428a0293c8e689b3f3e081aa07f055b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192076"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="27629-102">IHostMAlloc::Alloc メソッド</span><span class="sxs-lookup"><span data-stu-id="27629-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="27629-103">ホストが指定された量のメモリをヒープから割り当てることを要求します。</span><span class="sxs-lookup"><span data-stu-id="27629-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27629-104">構文</span><span class="sxs-lookup"><span data-stu-id="27629-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27629-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27629-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="27629-106">から現在のメモリ割り当て要求のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="27629-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="27629-107">から割り当てエラーの影響を示す[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)値の1つ。</span><span class="sxs-lookup"><span data-stu-id="27629-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="27629-108">入出力割り当てられたメモリへのポインター。要求を完了できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="27629-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27629-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="27629-109">Return Value</span></span>  
  
|<span data-ttu-id="27629-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27629-110">HRESULT</span></span>|<span data-ttu-id="27629-111">説明</span><span class="sxs-lookup"><span data-stu-id="27629-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27629-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="27629-112">S_OK</span></span>|<span data-ttu-id="27629-113">`Alloc` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="27629-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="27629-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27629-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27629-115">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="27629-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27629-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27629-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27629-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="27629-117">The call timed out.</span></span>|  
|<span data-ttu-id="27629-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27629-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27629-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="27629-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27629-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27629-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27629-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="27629-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27629-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27629-122">E_FAIL</span></span>|<span data-ttu-id="27629-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="27629-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27629-124">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="27629-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27629-125">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="27629-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="27629-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="27629-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="27629-127">割り当て要求を完了するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="27629-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27629-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="27629-128">Remarks</span></span>  
 <span data-ttu-id="27629-129">CLR は、 [IHostMemoryManager:: CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)メソッドを呼び出すことによって、`IHostMalloc` インスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="27629-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27629-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="27629-130">Requirements</span></span>  
 <span data-ttu-id="27629-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27629-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27629-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="27629-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27629-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="27629-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27629-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27629-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27629-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="27629-135">See also</span></span>

- [<span data-ttu-id="27629-136">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27629-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="27629-137">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27629-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
