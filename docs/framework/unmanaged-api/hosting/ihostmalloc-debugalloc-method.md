---
title: IHostMAlloc::DebugAlloc メソッド
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: a2a752f23ed64795f9208b9101c21bc585d5f431
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136815"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="6729f-102">IHostMAlloc::DebugAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="6729f-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="6729f-103">ホストがヒープから指定された量のメモリを割り当て、さらにメモリが割り当てられた場所を追跡するように要求します。</span><span class="sxs-lookup"><span data-stu-id="6729f-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6729f-104">構文</span><span class="sxs-lookup"><span data-stu-id="6729f-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6729f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6729f-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="6729f-106">から現在のメモリ割り当て要求のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="6729f-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="6729f-107">から割り当てエラーの影響を示す[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)値の1つ。</span><span class="sxs-lookup"><span data-stu-id="6729f-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="6729f-108">からデバッグ中の実行可能ファイルのコードファイル。</span><span class="sxs-lookup"><span data-stu-id="6729f-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="6729f-109">から割り当てが要求された `pszFileName` 内の行番号。</span><span class="sxs-lookup"><span data-stu-id="6729f-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="6729f-110">入出力割り当てられたメモリへのポインター。要求を完了できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="6729f-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6729f-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="6729f-111">Return Value</span></span>  
  
|<span data-ttu-id="6729f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6729f-112">HRESULT</span></span>|<span data-ttu-id="6729f-113">説明</span><span class="sxs-lookup"><span data-stu-id="6729f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6729f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6729f-114">S_OK</span></span>|<span data-ttu-id="6729f-115">`DebugAlloc` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="6729f-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="6729f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6729f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6729f-117">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="6729f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6729f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6729f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6729f-119">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="6729f-119">The call timed out.</span></span>|  
|<span data-ttu-id="6729f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6729f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6729f-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6729f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6729f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6729f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6729f-123">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="6729f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6729f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6729f-124">E_FAIL</span></span>|<span data-ttu-id="6729f-125">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6729f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6729f-126">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6729f-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6729f-127">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6729f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6729f-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6729f-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6729f-129">割り当て要求を完了するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="6729f-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6729f-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="6729f-130">Remarks</span></span>  
 <span data-ttu-id="6729f-131">CLR は、 [IHostMemoryManager:: CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)メソッドを呼び出すことによって、 [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)インスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6729f-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="6729f-132">`DebugAlloc` を使用すると、ランタイムはデバッグ時に使用するコードファイルの情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6729f-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6729f-133">［要件］</span><span class="sxs-lookup"><span data-stu-id="6729f-133">Requirements</span></span>  
 <span data-ttu-id="6729f-134">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6729f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6729f-135">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6729f-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6729f-136">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6729f-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6729f-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6729f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6729f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6729f-138">See also</span></span>

- [<span data-ttu-id="6729f-139">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6729f-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="6729f-140">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6729f-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
