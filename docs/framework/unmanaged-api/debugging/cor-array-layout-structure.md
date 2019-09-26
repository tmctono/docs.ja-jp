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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec9c4f3afb8f3b7e75e22874996d57d29ce8cf16
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274214"
---
# <a name="cor_array_layout-structure"></a><span data-ttu-id="226ad-102">COR_ARRAY_LAYOUT 構造体</span><span class="sxs-lookup"><span data-stu-id="226ad-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="226ad-103">メモリ内の配列オブジェクトのレイアウトに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="226ad-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="226ad-104">構文</span><span class="sxs-lookup"><span data-stu-id="226ad-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="226ad-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="226ad-105">Members</span></span>  
  
|<span data-ttu-id="226ad-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="226ad-106">Member</span></span>|<span data-ttu-id="226ad-107">説明</span><span class="sxs-lookup"><span data-stu-id="226ad-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="226ad-108">配列に格納されているオブジェクトの型の識別子。</span><span class="sxs-lookup"><span data-stu-id="226ad-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="226ad-109">コンポーネントがガベージコレクション参照、値クラス、またはプリミティブであるかどうかを示す CorElementType 列挙値。</span><span class="sxs-lookup"><span data-stu-id="226ad-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="226ad-110">配列内の最初の要素へのオフセット。</span><span class="sxs-lookup"><span data-stu-id="226ad-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="226ad-111">各要素のサイズ。</span><span class="sxs-lookup"><span data-stu-id="226ad-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="226ad-112">配列内の要素の数へのオフセット。</span><span class="sxs-lookup"><span data-stu-id="226ad-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="226ad-113">ランクのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="226ad-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="226ad-114">配列内のランクの数。</span><span class="sxs-lookup"><span data-stu-id="226ad-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="226ad-115">ランクの開始位置を示すオフセット。</span><span class="sxs-lookup"><span data-stu-id="226ad-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="226ad-116">コメント</span><span class="sxs-lookup"><span data-stu-id="226ad-116">Remarks</span></span>  
 <span data-ttu-id="226ad-117">この`rankSize`フィールドは、多次元配列内のランクのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="226ad-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="226ad-118">これは、1次元配列に対しても正確です。</span><span class="sxs-lookup"><span data-stu-id="226ad-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="226ad-119">の`numRanks`値は、1次元`N`配列の場合は1、次元の`N`多次元配列の場合は1になります。</span><span class="sxs-lookup"><span data-stu-id="226ad-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="226ad-120">要件</span><span class="sxs-lookup"><span data-stu-id="226ad-120">Requirements</span></span>  
 <span data-ttu-id="226ad-121">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="226ad-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="226ad-122">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="226ad-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="226ad-123">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="226ad-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="226ad-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="226ad-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="226ad-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="226ad-125">See also</span></span>

- [<span data-ttu-id="226ad-126">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="226ad-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="226ad-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="226ad-127">Debugging</span></span>](index.md)
