---
title: IHostMalloc インターフェイス
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136771"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="67d74-102">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67d74-102">IHostMalloc Interface</span></span>
<span data-ttu-id="67d74-103">共通言語ランタイム (CLR) がホストを介してヒープから細かい割り当てを要求できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="67d74-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67d74-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="67d74-104">Methods</span></span>  
  
|<span data-ttu-id="67d74-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="67d74-105">Method</span></span>|<span data-ttu-id="67d74-106">説明</span><span class="sxs-lookup"><span data-stu-id="67d74-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67d74-107">Alloc メソッド</span><span class="sxs-lookup"><span data-stu-id="67d74-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="67d74-108">ホストがヒープから要求された量のメモリを割り当てることを要求します。</span><span class="sxs-lookup"><span data-stu-id="67d74-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="67d74-109">DebugAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="67d74-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="67d74-110">は、要求されたメモリ量をヒープから割り当て、さらにメモリが割り当てられた場所を追跡することをホストに要求します。</span><span class="sxs-lookup"><span data-stu-id="67d74-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="67d74-111">Free メソッド</span><span class="sxs-lookup"><span data-stu-id="67d74-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="67d74-112">`Alloc` メソッドを使用して割り当てられたメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="67d74-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67d74-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="67d74-113">Remarks</span></span>  
 <span data-ttu-id="67d74-114">CLR は、 [IHostMemoryManager:: CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)メソッドを呼び出すことによって、`IHostMalloc` インスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="67d74-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67d74-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="67d74-115">Requirements</span></span>  
 <span data-ttu-id="67d74-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67d74-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67d74-117">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="67d74-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67d74-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="67d74-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67d74-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67d74-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d74-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="67d74-120">See also</span></span>

- [<span data-ttu-id="67d74-121">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67d74-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="67d74-122">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67d74-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
