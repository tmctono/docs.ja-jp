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
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178038"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="e122c-102">IHostMAlloc::DebugAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="e122c-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="e122c-103">ホストに、ヒープから指定された量のメモリを割り当て、さらにメモリが割り当てられた場所を追跡することを要求します。</span><span class="sxs-lookup"><span data-stu-id="e122c-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e122c-104">構文</span><span class="sxs-lookup"><span data-stu-id="e122c-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e122c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e122c-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="e122c-106">[in]現在のメモリ割り当て要求のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="e122c-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="e122c-107">[in]割り当てエラーの影響を示す[EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="e122c-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="e122c-108">[in]デバッグ中の実行可能ファイルのコード ファイル。</span><span class="sxs-lookup"><span data-stu-id="e122c-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="e122c-109">[in]割り当て`pszFileName`が要求された行番号。</span><span class="sxs-lookup"><span data-stu-id="e122c-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="e122c-110">[アウト]割り当てられたメモリへのポインター、または null 要求を完了できなかった場合。</span><span class="sxs-lookup"><span data-stu-id="e122c-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e122c-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="e122c-111">Return Value</span></span>  
  
|<span data-ttu-id="e122c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e122c-112">HRESULT</span></span>|<span data-ttu-id="e122c-113">説明</span><span class="sxs-lookup"><span data-stu-id="e122c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e122c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e122c-114">S_OK</span></span>|<span data-ttu-id="e122c-115">`DebugAlloc`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e122c-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="e122c-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e122c-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e122c-117">CLR がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="e122c-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e122c-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e122c-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e122c-119">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="e122c-119">The call timed out.</span></span>|  
|<span data-ttu-id="e122c-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e122c-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e122c-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e122c-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e122c-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e122c-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e122c-123">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="e122c-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e122c-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e122c-124">E_FAIL</span></span>|<span data-ttu-id="e122c-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e122c-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e122c-126">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e122c-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e122c-127">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="e122c-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e122c-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e122c-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e122c-129">メモリ不足で、割り当て要求を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="e122c-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e122c-130">解説</span><span class="sxs-lookup"><span data-stu-id="e122c-130">Remarks</span></span>  
 <span data-ttu-id="e122c-131">CLR は、メソッドを呼び出すことによって[、IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)インスタンスへのインターフェイス ポインター[を](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)取得します。</span><span class="sxs-lookup"><span data-stu-id="e122c-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="e122c-132">`DebugAlloc`ランタイムは、デバッグ中に使用するコード ファイル情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e122c-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e122c-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="e122c-133">Requirements</span></span>  
 <span data-ttu-id="e122c-134">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e122c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e122c-135">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e122c-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e122c-136">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="e122c-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e122c-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e122c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e122c-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="e122c-138">See also</span></span>

- [<span data-ttu-id="e122c-139">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e122c-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="e122c-140">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e122c-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
