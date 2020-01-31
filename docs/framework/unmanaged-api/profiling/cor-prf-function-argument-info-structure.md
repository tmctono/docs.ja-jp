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
ms.openlocfilehash: c92ee580caed9f1fb87a31b676747769ad31a0e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867253"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="ed5c1-102">COR_PRF_FUNCTION_ARGUMENT_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="ed5c1-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="ed5c1-103">関数の引数を左から右方向で表します。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed5c1-104">構文</span><span class="sxs-lookup"><span data-stu-id="ed5c1-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="ed5c1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ed5c1-105">Members</span></span>  
  
|<span data-ttu-id="ed5c1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ed5c1-106">Member</span></span>|<span data-ttu-id="ed5c1-107">説明</span><span class="sxs-lookup"><span data-stu-id="ed5c1-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="ed5c1-108">引数のブロックの数。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-108">The number of blocks of arguments.</span></span> <span data-ttu-id="ed5c1-109">つまり、この値は、`ranges` 配列内の[COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md)構造体の数です。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="ed5c1-110">すべての引数の合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-110">The total size of all arguments.</span></span> <span data-ttu-id="ed5c1-111">言い換えると、この値は引数の長さの合計になります。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="ed5c1-112">`COR_PRF_FUNCTION_ARGUMENT_RANGE` 構造体の配列。それぞれが関数の引数の1つのブロックを表します。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed5c1-113">コメント</span><span class="sxs-lookup"><span data-stu-id="ed5c1-113">Remarks</span></span>  
 <span data-ttu-id="ed5c1-114">関数には、多くの引数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-114">A function may have many arguments.</span></span> <span data-ttu-id="ed5c1-115">これらの引数は、連続してメモリに格納されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="ed5c1-116">1つの場所に3つの引数のブロック、別の場所に2つの引数のブロック、および別の場所にある1つの引数の最後のブロックがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="ed5c1-117">これらの引数はすべて同じ関数に対して使用されます。これらは、さまざまな場所に格納されています。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="ed5c1-118">`COR_PRF_FUNCTION_ARGUMENT_INFO` 構造体は、1つの関数のすべての引数を表します。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="ed5c1-119">配列を使用して、関数の引数のすべてのブロックを参照します。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="ed5c1-120">そのため、1つの関数に対して、1つの `COR_PRF_FUNCTION_ARGUMENT_INFO` 構造体を使用して、それぞれが1つ以上の関数引数を指し示す複数の `COR_PRF_FUNCTION_ARGUMENT_RANGE` 構造体を参照します。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="ed5c1-121">レジスタに格納されている引数は、構造体を構築するためにメモリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed5c1-122">要件</span><span class="sxs-lookup"><span data-stu-id="ed5c1-122">Requirements</span></span>  
 <span data-ttu-id="ed5c1-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed5c1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed5c1-124">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="ed5c1-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ed5c1-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed5c1-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed5c1-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed5c1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5c1-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed5c1-127">See also</span></span>

- [<span data-ttu-id="ed5c1-128">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="ed5c1-128">Profiling Structures</span></span>](profiling-structures.md)
