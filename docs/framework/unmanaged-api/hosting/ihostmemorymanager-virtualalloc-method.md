---
title: IHostMemoryManager::VirtualAlloc メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5407a9d23833d73b2d6ef0038454f56f01d56867
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760208"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="216c1-102">IHostMemoryManager::VirtualAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="216c1-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="216c1-103">対応する Win32 関数の論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="216c1-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="216c1-104">Win32 実装`VirtualAlloc`予約または呼び出し元のプロセス仮想アドレス空間内のページの領域をコミットします。</span><span class="sxs-lookup"><span data-stu-id="216c1-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="216c1-105">構文</span><span class="sxs-lookup"><span data-stu-id="216c1-105">Syntax</span></span>  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="216c1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="216c1-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="216c1-107">[in]割り当てる領域の開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="216c1-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="216c1-108">[in]リージョンのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="216c1-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="216c1-109">[in]メモリ割り当ての種類。</span><span class="sxs-lookup"><span data-stu-id="216c1-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="216c1-110">[in]割り当てられるページの領域のメモリ保護します。</span><span class="sxs-lookup"><span data-stu-id="216c1-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="216c1-111">[in][EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)割り当てエラーの影響を示す値。</span><span class="sxs-lookup"><span data-stu-id="216c1-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="216c1-112">[out]割り当てられたメモリは、または要求を処理できなかった場合は null の開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="216c1-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="216c1-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="216c1-113">Return Value</span></span>  
  
|<span data-ttu-id="216c1-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="216c1-114">HRESULT</span></span>|<span data-ttu-id="216c1-115">説明</span><span class="sxs-lookup"><span data-stu-id="216c1-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="216c1-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="216c1-116">S_OK</span></span>|<span data-ttu-id="216c1-117">`VirtualAlloc` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="216c1-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="216c1-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="216c1-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="216c1-119">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="216c1-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="216c1-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="216c1-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="216c1-121">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="216c1-121">The call timed out.</span></span>|  
|<span data-ttu-id="216c1-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="216c1-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="216c1-123">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="216c1-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="216c1-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="216c1-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="216c1-125">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="216c1-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="216c1-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="216c1-126">E_FAIL</span></span>|<span data-ttu-id="216c1-127">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="216c1-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="216c1-128">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="216c1-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="216c1-129">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="216c1-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="216c1-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="216c1-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="216c1-131">十分なメモリが割り当て要求を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="216c1-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="216c1-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="216c1-132">Remarks</span></span>  
 <span data-ttu-id="216c1-133">呼び出すことによって、プロセスのアドレス空間で領域を予約する`VirtualAlloc`します。</span><span class="sxs-lookup"><span data-stu-id="216c1-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="216c1-134">`pAddress`パラメーターにするメモリ ブロックの開始アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="216c1-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="216c1-135">このパラメーターの設定は、通常 null にします。</span><span class="sxs-lookup"><span data-stu-id="216c1-135">This parameter is typically set to null.</span></span> <span data-ttu-id="216c1-136">オペレーティング システムをプロセスに使用可能な無料のアドレス範囲のレコードを保持します。</span><span class="sxs-lookup"><span data-stu-id="216c1-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="216c1-137">A`pAddress`値は null ですが、システムに最適と思われる任意の場所に領域を予約するように指示します。</span><span class="sxs-lookup"><span data-stu-id="216c1-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="216c1-138">また、メモリ ブロックの特定の開始アドレスを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="216c1-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="216c1-139">どちらの場合も、出力パラメーター`ppMem`が割り当てられたメモリへのポインターとして返されます。</span><span class="sxs-lookup"><span data-stu-id="216c1-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="216c1-140">関数自体では、HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="216c1-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="216c1-141">Win32`VirtualAlloc`関数はありません、`ppMem`パラメーターと、代わりに、割り当てられたメモリへのポインターを返します。</span><span class="sxs-lookup"><span data-stu-id="216c1-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="216c1-142">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="216c1-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="216c1-143">必要条件</span><span class="sxs-lookup"><span data-stu-id="216c1-143">Requirements</span></span>  
 <span data-ttu-id="216c1-144">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="216c1-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="216c1-145">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="216c1-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="216c1-146">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="216c1-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="216c1-147">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="216c1-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216c1-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="216c1-148">See also</span></span>

- [<span data-ttu-id="216c1-149">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="216c1-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
