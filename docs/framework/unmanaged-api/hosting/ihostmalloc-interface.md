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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2a7a29ef1dc85c2ad554995286e5137fcb104be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757639"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="10096-102">IHostMalloc インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10096-102">IHostMalloc Interface</span></span>
<span data-ttu-id="10096-103">共通言語ランタイム (CLR) にホストを通じてヒープから詳細な割り当てを要求できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="10096-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10096-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="10096-104">Methods</span></span>  
  
|<span data-ttu-id="10096-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="10096-105">Method</span></span>|<span data-ttu-id="10096-106">説明</span><span class="sxs-lookup"><span data-stu-id="10096-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10096-107">Alloc メソッド</span><span class="sxs-lookup"><span data-stu-id="10096-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="10096-108">ホストが、ヒープから要求されたメモリ量を割り当てることを要求します。</span><span class="sxs-lookup"><span data-stu-id="10096-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="10096-109">DebugAlloc メソッド</span><span class="sxs-lookup"><span data-stu-id="10096-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="10096-110">ホストは、ヒープから要求されたメモリ量を割り当てるし、さらに、メモリが割り当てられた場所の追跡を要求します。</span><span class="sxs-lookup"><span data-stu-id="10096-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="10096-111">Free メソッド</span><span class="sxs-lookup"><span data-stu-id="10096-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="10096-112">使用して割り当てられたメモリを解放、`Alloc`メソッド。</span><span class="sxs-lookup"><span data-stu-id="10096-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10096-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="10096-113">Remarks</span></span>  
 <span data-ttu-id="10096-114">CLR へのインターフェイス ポインターの取得、`IHostMalloc`インスタンスを呼び出すことによって、 [ihostmemorymanager::createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="10096-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10096-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="10096-115">Requirements</span></span>  
 <span data-ttu-id="10096-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10096-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10096-117">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10096-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10096-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="10096-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10096-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10096-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10096-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="10096-120">See also</span></span>

- [<span data-ttu-id="10096-121">IHostMemoryManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10096-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="10096-122">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="10096-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
