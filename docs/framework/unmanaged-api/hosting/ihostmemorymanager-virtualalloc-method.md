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
ms.openlocfilehash: dd588fa85ff8aaa396a8d0e52a738ada46c2a9b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128612"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="e32d1-102">IHostMemoryManager::VirtualAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="e32d1-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="e32d1-103">対応する Win32 関数の論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="e32d1-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="e32d1-104">`VirtualAlloc` の Win32 実装は、呼び出し元プロセスの仮想アドレス空間内のページの領域を予約またはコミットします。</span><span class="sxs-lookup"><span data-stu-id="e32d1-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32d1-105">構文</span><span class="sxs-lookup"><span data-stu-id="e32d1-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e32d1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e32d1-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="e32d1-107">から割り当てる領域の開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e32d1-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="e32d1-108">から領域のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="e32d1-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="e32d1-109">からメモリ割り当ての種類。</span><span class="sxs-lookup"><span data-stu-id="e32d1-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="e32d1-110">から割り当てられるページの領域のメモリ保護。</span><span class="sxs-lookup"><span data-stu-id="e32d1-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="e32d1-111">から割り当てエラーの影響を示す[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)値です。</span><span class="sxs-lookup"><span data-stu-id="e32d1-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="e32d1-112">入出力割り当てられたメモリの開始アドレスへのポインター。要求を満たすことができなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="e32d1-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e32d1-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="e32d1-113">Return Value</span></span>  
  
|<span data-ttu-id="e32d1-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e32d1-114">HRESULT</span></span>|<span data-ttu-id="e32d1-115">説明</span><span class="sxs-lookup"><span data-stu-id="e32d1-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e32d1-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="e32d1-116">S_OK</span></span>|<span data-ttu-id="e32d1-117">`VirtualAlloc` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e32d1-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="e32d1-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e32d1-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e32d1-119">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="e32d1-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e32d1-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e32d1-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e32d1-121">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="e32d1-121">The call timed out.</span></span>|  
|<span data-ttu-id="e32d1-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e32d1-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e32d1-123">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e32d1-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e32d1-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e32d1-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e32d1-125">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="e32d1-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e32d1-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e32d1-126">E_FAIL</span></span>|<span data-ttu-id="e32d1-127">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e32d1-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e32d1-128">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e32d1-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e32d1-129">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e32d1-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e32d1-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e32d1-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e32d1-131">割り当て要求を完了するのに十分なメモリがありませんでした</span><span class="sxs-lookup"><span data-stu-id="e32d1-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e32d1-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="e32d1-132">Remarks</span></span>  
 <span data-ttu-id="e32d1-133">`VirtualAlloc`を呼び出すことによって、プロセスのアドレス空間にリージョンを予約します。</span><span class="sxs-lookup"><span data-stu-id="e32d1-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="e32d1-134">`pAddress` パラメーターには、必要なメモリブロックの開始アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e32d1-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="e32d1-135">通常、このパラメーターは null に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e32d1-135">This parameter is typically set to null.</span></span> <span data-ttu-id="e32d1-136">オペレーティングシステムは、プロセスで使用可能な空きアドレス範囲の記録を保持します。</span><span class="sxs-lookup"><span data-stu-id="e32d1-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="e32d1-137">`pAddress` 値が null の場合は、必要に応じて領域を予約するようにシステムに指示します。</span><span class="sxs-lookup"><span data-stu-id="e32d1-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="e32d1-138">または、メモリブロックの特定の開始アドレスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e32d1-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="e32d1-139">どちらの場合も、出力パラメーター `ppMem` は、割り当てられたメモリへのポインターとして返されます。</span><span class="sxs-lookup"><span data-stu-id="e32d1-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="e32d1-140">関数自体は HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="e32d1-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="e32d1-141">Win32 `VirtualAlloc` 関数には `ppMem` パラメーターがないため、代わりに割り当てられたメモリへのポインターを返します。</span><span class="sxs-lookup"><span data-stu-id="e32d1-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="e32d1-142">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e32d1-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e32d1-143">［要件］</span><span class="sxs-lookup"><span data-stu-id="e32d1-143">Requirements</span></span>  
 <span data-ttu-id="e32d1-144">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e32d1-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e32d1-145">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e32d1-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e32d1-146">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e32d1-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e32d1-147">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e32d1-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32d1-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="e32d1-148">See also</span></span>

- [<span data-ttu-id="e32d1-149">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e32d1-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
