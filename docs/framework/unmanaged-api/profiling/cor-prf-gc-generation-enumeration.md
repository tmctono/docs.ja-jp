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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74e70f58600205d44a9ba052981b2cc67b3a44ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753810"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="63ea8-102">COR_PRF_GC_GENERATION 列挙型</span><span class="sxs-lookup"><span data-stu-id="63ea8-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="63ea8-103">ガベージ コレクション ジェネレーションを識別します。</span><span class="sxs-lookup"><span data-stu-id="63ea8-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ea8-104">構文</span><span class="sxs-lookup"><span data-stu-id="63ea8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="63ea8-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="63ea8-105">Members</span></span>  
  
|<span data-ttu-id="63ea8-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="63ea8-106">Member</span></span>|<span data-ttu-id="63ea8-107">説明</span><span class="sxs-lookup"><span data-stu-id="63ea8-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="63ea8-108">オブジェクトは、ジェネレーション 0 として格納されます。</span><span class="sxs-lookup"><span data-stu-id="63ea8-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="63ea8-109">オブジェクトは、第 1 世代として格納されます。</span><span class="sxs-lookup"><span data-stu-id="63ea8-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="63ea8-110">オブジェクトは、第 2 世代として格納されます。</span><span class="sxs-lookup"><span data-stu-id="63ea8-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="63ea8-111">オブジェクトは、大きなオブジェクト ヒープに格納されます。</span><span class="sxs-lookup"><span data-stu-id="63ea8-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63ea8-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="63ea8-112">Remarks</span></span>  
 <span data-ttu-id="63ea8-113">ガベージ コレクターには、年齢に基づいてジェネレーションに分割オブジェクトによってメモリ管理のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="63ea8-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="63ea8-114">現在、ガベージ コレクターは、0、1、2、およびラージ オブジェクトに使用される特殊なヒープ セグメントの番号、3 つの世代を使用します。</span><span class="sxs-lookup"><span data-stu-id="63ea8-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="63ea8-115">サイズが特定の値より大きいオブジェクトは、大きなオブジェクト ヒープに格納されます。</span><span class="sxs-lookup"><span data-stu-id="63ea8-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="63ea8-116">割り当てられたその他のオブジェクトをジェネレーション 0 に属するを起動します。</span><span class="sxs-lookup"><span data-stu-id="63ea8-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="63ea8-117">ジェネレーション 0 ガベージ コレクションが行われた後に存在するすべてのオブジェクトは、第 1 世代に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="63ea8-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="63ea8-118">ジェネレーション 1 のガベージ コレクションが行われた後に存在するオブジェクトは、ジェネレーション 2 に移動します。</span><span class="sxs-lookup"><span data-stu-id="63ea8-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="63ea8-119">生成結果の使用は、ガベージ コレクターはいつでも割り当てられたオブジェクトのサブセットのみを使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="63ea8-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="63ea8-120">`COR_PRF_GC_GENERATION`列挙型を使用して、 [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="63ea8-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63ea8-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="63ea8-121">Requirements</span></span>  
 <span data-ttu-id="63ea8-122">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63ea8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ea8-123">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63ea8-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63ea8-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63ea8-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63ea8-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ea8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ea8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="63ea8-126">See also</span></span>

- [<span data-ttu-id="63ea8-127">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="63ea8-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
