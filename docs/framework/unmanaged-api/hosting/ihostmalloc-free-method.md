---
title: IHostMAlloc::Free メソッド
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
ms.openlocfilehash: 1dd5ed4c556a5a4d4425a9c0730cebf22ff1785b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804618"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="b229f-102">IHostMAlloc::Free メソッド</span><span class="sxs-lookup"><span data-stu-id="b229f-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="b229f-103">[Alloc](ihostmalloc-alloc-method.md)関数を使用して割り当てられたメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="b229f-103">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b229f-104">構文</span><span class="sxs-lookup"><span data-stu-id="b229f-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b229f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b229f-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="b229f-106">から解放するメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b229f-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b229f-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b229f-107">Return Value</span></span>  
  
|<span data-ttu-id="b229f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b229f-108">HRESULT</span></span>|<span data-ttu-id="b229f-109">説明</span><span class="sxs-lookup"><span data-stu-id="b229f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b229f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b229f-110">S_OK</span></span>|<span data-ttu-id="b229f-111">`Free`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b229f-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="b229f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b229f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b229f-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b229f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b229f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b229f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b229f-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b229f-115">The call timed out.</span></span>|  
|<span data-ttu-id="b229f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b229f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b229f-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b229f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b229f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b229f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b229f-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b229f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b229f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b229f-120">E_FAIL</span></span>|<span data-ttu-id="b229f-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b229f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b229f-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b229f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b229f-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b229f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b229f-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="b229f-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="b229f-125">ホストを通じて割り当てられていないメモリを解放しようとしました。</span><span class="sxs-lookup"><span data-stu-id="b229f-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b229f-126">解説</span><span class="sxs-lookup"><span data-stu-id="b229f-126">Remarks</span></span>  
 <span data-ttu-id="b229f-127">パラメーターが、 `pMem` の呼び出しを使用して割り当てられていないメモリ領域を参照している場合 `Alloc` 、ホストは HOST_E_INVALIDOPERATION を返します。</span><span class="sxs-lookup"><span data-stu-id="b229f-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b229f-128">要件</span><span class="sxs-lookup"><span data-stu-id="b229f-128">Requirements</span></span>  
 <span data-ttu-id="b229f-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b229f-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b229f-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b229f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b229f-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b229f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b229f-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b229f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b229f-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b229f-133">See also</span></span>

- [<span data-ttu-id="b229f-134">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b229f-134">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="b229f-135">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b229f-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
