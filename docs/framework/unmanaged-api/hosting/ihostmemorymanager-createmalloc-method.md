---
title: IHostMemoryManager::CreateMAlloc メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba380babe1c84cca632babdd041b5e59ce575d23
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748766"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="83981-102">IHostMemoryManager::CreateMAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="83981-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="83981-103">インターフェイス ポインターを取得、 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)ホストによって作成されたヒープから割り当て要求を作成するために使用するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="83981-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83981-104">構文</span><span class="sxs-lookup"><span data-stu-id="83981-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83981-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83981-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="83981-106">[in]組み合わせた[MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md)割り当てられるメモリの特性を指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="83981-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="83981-107">[out]アドレスへのポインター、`IHostMAlloc`ホストによって提供されるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="83981-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83981-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="83981-108">Return Value</span></span>  
  
|<span data-ttu-id="83981-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83981-109">HRESULT</span></span>|<span data-ttu-id="83981-110">説明</span><span class="sxs-lookup"><span data-stu-id="83981-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83981-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="83981-111">S_OK</span></span>|<span data-ttu-id="83981-112">`CreateMAlloc` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="83981-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="83981-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="83981-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="83981-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="83981-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="83981-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="83981-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="83981-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="83981-116">The call timed out.</span></span>|  
|<span data-ttu-id="83981-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="83981-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="83981-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="83981-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="83981-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="83981-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="83981-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="83981-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="83981-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="83981-121">E_FAIL</span></span>|<span data-ttu-id="83981-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="83981-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="83981-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="83981-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="83981-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="83981-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="83981-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="83981-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="83981-126">物理メモリが不足は、割り当て要求を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="83981-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83981-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="83981-127">Remarks</span></span>  
 <span data-ttu-id="83981-128">`CreateMAlloc` 標準の Win32 関数を使用する代わりに、ホストを通じて割り当て要求を行う CLR をできるようにするオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="83981-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83981-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="83981-129">Requirements</span></span>  
 <span data-ttu-id="83981-130">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="83981-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83981-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83981-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83981-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="83981-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83981-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83981-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83981-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="83981-134">See also</span></span>

- [<span data-ttu-id="83981-135">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83981-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="83981-136">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83981-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
