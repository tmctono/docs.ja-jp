---
title: COR_PRF_GC_GENERATION 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
ms.openlocfilehash: d01b864be231e5b0a3fd72dc2f3636a87c8cae83
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448632"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="e8632-102">COR_PRF_GC_GENERATION 列挙型</span><span class="sxs-lookup"><span data-stu-id="e8632-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="e8632-103">ガベージコレクションの生成を識別します。</span><span class="sxs-lookup"><span data-stu-id="e8632-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8632-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8632-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="e8632-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="e8632-105">Members</span></span>  
  
|<span data-ttu-id="e8632-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="e8632-106">Member</span></span>|<span data-ttu-id="e8632-107">説明</span><span class="sxs-lookup"><span data-stu-id="e8632-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="e8632-108">オブジェクトは、ジェネレーション0として格納されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="e8632-109">オブジェクトは、ジェネレーション1として格納されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="e8632-110">オブジェクトは、ジェネレーション2として格納されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="e8632-111">オブジェクトは、ラージオブジェクトヒープに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8632-112">コメント</span><span class="sxs-lookup"><span data-stu-id="e8632-112">Remarks</span></span>  
 <span data-ttu-id="e8632-113">ガベージコレクターは、オブジェクトを経過期間に基づいてジェネレーションに分割することによって、メモリ管理のパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="e8632-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="e8632-114">現在、ガベージコレクターは、番号0、1、および2の3つのジェネレーションと、大きなオブジェクトに使用される特殊なヒープセグメントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e8632-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="e8632-115">サイズが特定の値より大きいオブジェクトは、大きなオブジェクトヒープに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="e8632-116">割り当てられた他のオブジェクトは、ジェネレーション0に属しています。</span><span class="sxs-lookup"><span data-stu-id="e8632-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="e8632-117">ジェネレーション0でガベージコレクションが発生した後に存在するすべてのオブジェクトは、ジェネレーション1に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="e8632-118">ジェネレーション1でガベージコレクションが発生した後に存在するオブジェクトは、ジェネレーション2に移動します。</span><span class="sxs-lookup"><span data-stu-id="e8632-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="e8632-119">ジェネレーションを使用することは、ガベージコレクターが、割り当てられたオブジェクトのサブセットだけを一度に処理する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e8632-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="e8632-120">`COR_PRF_GC_GENERATION` 列挙体は、 [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)構造体によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8632-121">要件</span><span class="sxs-lookup"><span data-stu-id="e8632-121">Requirements</span></span>  
 <span data-ttu-id="e8632-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8632-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8632-123">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8632-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8632-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8632-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8632-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8632-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8632-126">参照</span><span class="sxs-lookup"><span data-stu-id="e8632-126">See also</span></span>

- [<span data-ttu-id="e8632-127">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="e8632-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
