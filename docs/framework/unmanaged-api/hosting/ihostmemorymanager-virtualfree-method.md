---
title: IHostMemoryManager::VirtualFree メソッド
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
ms.openlocfilehash: b53c0bb38922ae8de048c131807eb32f97423d6c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128592"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="f0a89-102">IHostMemoryManager::VirtualFree メソッド</span><span class="sxs-lookup"><span data-stu-id="f0a89-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="f0a89-103">対応する Win32 関数の論理ラッパーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="f0a89-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="f0a89-104">`VirtualFree` リリース、デ、またはリリースの Win32 実装では、呼び出しプロセスの仮想アドレス空間内のページの領域をデします。</span><span class="sxs-lookup"><span data-stu-id="f0a89-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a89-105">構文</span><span class="sxs-lookup"><span data-stu-id="f0a89-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0a89-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0a89-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="f0a89-107">から解放される仮想メモリページのベースアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0a89-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="f0a89-108">から解放する領域のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="f0a89-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="f0a89-109">から解放操作の種類。</span><span class="sxs-lookup"><span data-stu-id="f0a89-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0a89-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="f0a89-110">Return Value</span></span>  
  
|<span data-ttu-id="f0a89-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0a89-111">HRESULT</span></span>|<span data-ttu-id="f0a89-112">説明</span><span class="sxs-lookup"><span data-stu-id="f0a89-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0a89-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0a89-113">S_OK</span></span>|<span data-ttu-id="f0a89-114">`VirtualFree` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="f0a89-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="f0a89-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f0a89-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f0a89-116">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="f0a89-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f0a89-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f0a89-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f0a89-118">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="f0a89-118">The call timed out.</span></span>|  
|<span data-ttu-id="f0a89-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f0a89-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f0a89-120">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f0a89-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f0a89-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f0a89-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f0a89-122">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="f0a89-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f0a89-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f0a89-123">E_FAIL</span></span>|<span data-ttu-id="f0a89-124">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f0a89-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f0a89-125">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f0a89-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f0a89-126">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f0a89-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f0a89-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="f0a89-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="f0a89-128">ホストを通じて割り当てられていないメモリを解放しようとしました。</span><span class="sxs-lookup"><span data-stu-id="f0a89-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0a89-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0a89-129">Remarks</span></span>  
 <span data-ttu-id="f0a89-130">`VirtualFree` は、 [IHostMemoryManager:: VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)関数の以前の呼び出しによって、`lpAddress` パラメーターに関連付けられた仮想メモリページを解放します。</span><span class="sxs-lookup"><span data-stu-id="f0a89-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="f0a89-131">ホストを通じて割り当てられていないメモリを解放しようとすると、HOST_E_INVALIDOPERATION が返されます。</span><span class="sxs-lookup"><span data-stu-id="f0a89-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="f0a89-132">セマンティクスは、`VirtualFree`の Win32 実装と同じです。</span><span class="sxs-lookup"><span data-stu-id="f0a89-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="f0a89-133">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0a89-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a89-134">［要件］</span><span class="sxs-lookup"><span data-stu-id="f0a89-134">Requirements</span></span>  
 <span data-ttu-id="f0a89-135">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0a89-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a89-136">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f0a89-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0a89-137">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f0a89-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0a89-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0a89-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a89-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0a89-139">See also</span></span>

- [<span data-ttu-id="f0a89-140">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0a89-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="f0a89-141">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0a89-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
