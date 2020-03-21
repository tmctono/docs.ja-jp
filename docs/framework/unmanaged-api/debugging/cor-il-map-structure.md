---
title: COR_IL_MAP 構造体
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179294"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="4d61a-102">COR_IL_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="4d61a-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="4d61a-103">機能の相対オフセットでの変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d61a-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d61a-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d61a-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="4d61a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4d61a-105">Members</span></span>  
  
|<span data-ttu-id="4d61a-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4d61a-106">Member</span></span>|<span data-ttu-id="4d61a-107">説明</span><span class="sxs-lookup"><span data-stu-id="4d61a-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="4d61a-108">関数の先頭を基準とした、古い Microsoft 中間言語 (MSIL) オフセット。</span><span class="sxs-lookup"><span data-stu-id="4d61a-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="4d61a-109">関数の先頭を基準とした新しい MSIL オフセット。</span><span class="sxs-lookup"><span data-stu-id="4d61a-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="4d61a-110">`true`マッピングが正確であることがわかっている場合。それ以外`false`の場合は、 .</span><span class="sxs-lookup"><span data-stu-id="4d61a-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d61a-111">解説</span><span class="sxs-lookup"><span data-stu-id="4d61a-111">Remarks</span></span>  
 <span data-ttu-id="4d61a-112">マップの形式は次のとおりです: デバッガーは、元の変更されていない`oldOffset`MSIL コード内の MSIL オフセットを参照することを想定します。</span><span class="sxs-lookup"><span data-stu-id="4d61a-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="4d61a-113">パラメーター`newOffset`は、新しいインストルメント化されたコード内の対応する MSIL オフセットを参照します。</span><span class="sxs-lookup"><span data-stu-id="4d61a-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="4d61a-114">ステップが正しく機能するためには、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d61a-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="4d61a-115">マップは昇順で並べ替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d61a-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="4d61a-116">インストルメント化された MSIL コードは並べ替えできません。</span><span class="sxs-lookup"><span data-stu-id="4d61a-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="4d61a-117">元の MSIL コードは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="4d61a-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="4d61a-118">マップには、プログラム データベース (PDB) ファイルからのすべてのシーケンス ポイントをマップするエントリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d61a-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="4d61a-119">マップは、欠落しているエントリを補間しません。</span><span class="sxs-lookup"><span data-stu-id="4d61a-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="4d61a-120">次の例は、マップとその結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="4d61a-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="4d61a-121">マップ：</span><span class="sxs-lookup"><span data-stu-id="4d61a-121">Map:</span></span>  
  
- <span data-ttu-id="4d61a-122">0 古いオフセット、0 新しいオフセット</span><span class="sxs-lookup"><span data-stu-id="4d61a-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="4d61a-123">5 古いオフセット、10 の新しいオフセット</span><span class="sxs-lookup"><span data-stu-id="4d61a-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="4d61a-124">9 古いオフセット、20 の新しいオフセット</span><span class="sxs-lookup"><span data-stu-id="4d61a-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="4d61a-125">結果:</span><span class="sxs-lookup"><span data-stu-id="4d61a-125">Results:</span></span>  
  
- <span data-ttu-id="4d61a-126">古いオフセットが 0、1、2、3、または 4 の場合は、新しいオフセット 0 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="4d61a-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="4d61a-127">古いオフセットが 5、6、7、または 8 の場合は、新しいオフセット 10 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="4d61a-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="4d61a-128">9 以上の古いオフセットは、新しいオフセット 20 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="4d61a-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="4d61a-129">新しいオフセット 0、1、2、3、4、5、6、7、8、または 9 は、古いオフセット 0 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="4d61a-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="4d61a-130">10、11、12、13、14、15、16、17、18、または 19 の新しいオフセットは、古いオフセット 5 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="4d61a-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="4d61a-131">20 以上の新しいオフセットは、古いオフセット 9 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="4d61a-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d61a-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="4d61a-132">Requirements</span></span>  
 <span data-ttu-id="4d61a-133">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d61a-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d61a-134">**ヘッダー:** コルデバッグ.idl、コルプロフ.idl</span><span class="sxs-lookup"><span data-stu-id="4d61a-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="4d61a-135">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d61a-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d61a-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d61a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d61a-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d61a-137">See also</span></span>

- [<span data-ttu-id="4d61a-138">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="4d61a-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="4d61a-139">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4d61a-139">Debugging</span></span>](index.md)
