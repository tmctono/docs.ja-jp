---
title: COR_ARRAY_LAYOUT 構造体
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
ms.openlocfilehash: ca2d00611a7530dfb0d1c2a27123947bdf69820d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179350"
---
# <a name="cor_array_layout-structure"></a><span data-ttu-id="54504-102">COR_ARRAY_LAYOUT 構造体</span><span class="sxs-lookup"><span data-stu-id="54504-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="54504-103">メモリ内の配列オブジェクトのレイアウトに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="54504-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54504-104">構文</span><span class="sxs-lookup"><span data-stu-id="54504-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;
    ULONG32 rankSize;
    ULONG32 numRanks;
    ULONG32 rankOffset;
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="54504-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="54504-105">Members</span></span>  
  
|<span data-ttu-id="54504-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="54504-106">Member</span></span>|<span data-ttu-id="54504-107">説明</span><span class="sxs-lookup"><span data-stu-id="54504-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="54504-108">配列に含まれるオブジェクトの型の識別子。</span><span class="sxs-lookup"><span data-stu-id="54504-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="54504-109">コンポーネントがガベージ コレクション参照、値クラス、またはプリミティブであるかどうかを示す CorElementType 列挙値。</span><span class="sxs-lookup"><span data-stu-id="54504-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="54504-110">配列の最初の要素へのオフセット。</span><span class="sxs-lookup"><span data-stu-id="54504-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="54504-111">各要素のサイズ。</span><span class="sxs-lookup"><span data-stu-id="54504-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="54504-112">配列内の要素数のオフセット。</span><span class="sxs-lookup"><span data-stu-id="54504-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="54504-113">ランクのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="54504-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="54504-114">配列内のランクの数。</span><span class="sxs-lookup"><span data-stu-id="54504-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="54504-115">ランクの開始位置のオフセット。</span><span class="sxs-lookup"><span data-stu-id="54504-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54504-116">解説</span><span class="sxs-lookup"><span data-stu-id="54504-116">Remarks</span></span>  
 <span data-ttu-id="54504-117">この`rankSize`フィールドは、多次元配列のランクのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="54504-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="54504-118">これは、単一次元配列でも正確です。</span><span class="sxs-lookup"><span data-stu-id="54504-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="54504-119">1 次元`numRanks`配列の場合は 1、次元`N`の多次元配列の`N`場合は、値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="54504-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54504-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="54504-120">Requirements</span></span>  
 <span data-ttu-id="54504-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54504-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54504-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54504-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54504-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54504-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54504-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54504-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54504-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="54504-125">See also</span></span>

- [<span data-ttu-id="54504-126">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="54504-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="54504-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="54504-127">Debugging</span></span>](index.md)
