---
title: COR_PRF_FUNCTION_ARGUMENT_INFO 構造体
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293ad30ebf47ca8684d158b1ae1772ab245d7981
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775090"
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="042de-102">COR_PRF_FUNCTION_ARGUMENT_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="042de-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="042de-103">関数の引数を左から右方向で表します。</span><span class="sxs-lookup"><span data-stu-id="042de-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="042de-104">構文</span><span class="sxs-lookup"><span data-stu-id="042de-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="042de-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="042de-105">Members</span></span>  
  
|<span data-ttu-id="042de-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="042de-106">Member</span></span>|<span data-ttu-id="042de-107">説明</span><span class="sxs-lookup"><span data-stu-id="042de-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="042de-108">引数のブロックの数。</span><span class="sxs-lookup"><span data-stu-id="042de-108">The number of blocks of arguments.</span></span> <span data-ttu-id="042de-109">これは、この値が、数ある[COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)内の構造体、`ranges`配列。</span><span class="sxs-lookup"><span data-stu-id="042de-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="042de-110">すべての引数の合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="042de-110">The total size of all arguments.</span></span> <span data-ttu-id="042de-111">つまり、この値は、引数の長さの合計です。</span><span class="sxs-lookup"><span data-stu-id="042de-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="042de-112">配列の`COR_PRF_FUNCTION_ARGUMENT_RANGE`構造体、関数の引数の 1 つのブロックのそれぞれ表します。</span><span class="sxs-lookup"><span data-stu-id="042de-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="042de-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="042de-113">Remarks</span></span>  
 <span data-ttu-id="042de-114">関数は、多くの引数があります。</span><span class="sxs-lookup"><span data-stu-id="042de-114">A function may have many arguments.</span></span> <span data-ttu-id="042de-115">これらの引数は可能性がありますメモリ内で連続して格納されません。</span><span class="sxs-lookup"><span data-stu-id="042de-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="042de-116">3 つの引数を 1 か所でのブロック、別の場所に 2 つの引数のブロック、および別の場所に 1 つの引数の最後のブロックするがあります。</span><span class="sxs-lookup"><span data-stu-id="042de-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="042de-117">これらの引数はすべて、同じ関数のさまざまな場所にだけ格納されます。</span><span class="sxs-lookup"><span data-stu-id="042de-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="042de-118">`COR_PRF_FUNCTION_ARGUMENT_INFO`構造体が 1 つの関数のすべての引数を表します。</span><span class="sxs-lookup"><span data-stu-id="042de-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="042de-119">関数の引数のすべてのブロックを参照するのに配列を使用します。</span><span class="sxs-lookup"><span data-stu-id="042de-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="042de-120">そのために、1 つのある 1 つの関数`COR_PRF_FUNCTION_ARGUMENT_INFO`構造体は、複数の参照`COR_PRF_FUNCTION_ARGUMENT_RANGE`構造体、1 つまたは複数の関数の引数を参照します。</span><span class="sxs-lookup"><span data-stu-id="042de-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="042de-121">レジスタに格納されている引数は、構造を構築するメモリに書き込まれました。</span><span class="sxs-lookup"><span data-stu-id="042de-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="042de-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="042de-122">Requirements</span></span>  
 <span data-ttu-id="042de-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="042de-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="042de-124">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="042de-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="042de-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="042de-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="042de-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="042de-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="042de-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="042de-127">See also</span></span>

- [<span data-ttu-id="042de-128">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="042de-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
