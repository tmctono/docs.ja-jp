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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6d8023c7ac6d917c9df40fb18316ddc12df5ec1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609419"
---
# <a name="corilmap-structure"></a><span data-ttu-id="2397c-102">COR_IL_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="2397c-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="2397c-103">機能の相対オフセットでの変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="2397c-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2397c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2397c-104">Syntax</span></span>  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="2397c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="2397c-105">Members</span></span>  
  
|<span data-ttu-id="2397c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="2397c-106">Member</span></span>|<span data-ttu-id="2397c-107">説明</span><span class="sxs-lookup"><span data-stu-id="2397c-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="2397c-108">古い Microsoft intermediate language (MSIL) 関数の先頭からの相対オフセットします。</span><span class="sxs-lookup"><span data-stu-id="2397c-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="2397c-109">関数の先頭を基準とした新しい MSIL オフセット。</span><span class="sxs-lookup"><span data-stu-id="2397c-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="2397c-110">`true` 正確であるマッピングがわかっている場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="2397c-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2397c-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="2397c-111">Remarks</span></span>  
 <span data-ttu-id="2397c-112">マップの形式は次のとおりです。デバッガーは仮定`oldOffset`、変更されていない元の MSIL コード内で MSIL オフセットを示します。</span><span class="sxs-lookup"><span data-stu-id="2397c-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="2397c-113">`newOffset`パラメーターは、新しい、インストルメント化されたコード内で、対応する MSIL のオフセットを表します。</span><span class="sxs-lookup"><span data-stu-id="2397c-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="2397c-114">適切に機能するステップの場合は、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="2397c-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="2397c-115">マップは、昇順で並べ替えする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2397c-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="2397c-116">インストルメント化された MSIL コードは並べ替えないでください。</span><span class="sxs-lookup"><span data-stu-id="2397c-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="2397c-117">元の MSIL コードを削除しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="2397c-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="2397c-118">マップには、プログラム データベース (PDB) ファイルからのすべてのシーケンス ポイントをマップするエントリを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2397c-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="2397c-119">マップに存在しないエントリが補間されません。</span><span class="sxs-lookup"><span data-stu-id="2397c-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="2397c-120">次の例では、マップとその結果を示します。</span><span class="sxs-lookup"><span data-stu-id="2397c-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="2397c-121">マップ:</span><span class="sxs-lookup"><span data-stu-id="2397c-121">Map:</span></span>  
  
- <span data-ttu-id="2397c-122">以前のオフセットは 0、0 の新しいオフセット</span><span class="sxs-lookup"><span data-stu-id="2397c-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="2397c-123">以前のオフセットが 5、10 の新しいオフセット</span><span class="sxs-lookup"><span data-stu-id="2397c-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="2397c-124">以前のオフセットを 9、20 の新しいオフセット</span><span class="sxs-lookup"><span data-stu-id="2397c-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="2397c-125">結果:</span><span class="sxs-lookup"><span data-stu-id="2397c-125">Results:</span></span>  
  
- <span data-ttu-id="2397c-126">0、1、2、3、または 4 の以前のオフセットは、新しいオフセットは 0 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2397c-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="2397c-127">5、6、7、または 8 の以前のオフセットは、10 の新しいオフセットにマップされます。</span><span class="sxs-lookup"><span data-stu-id="2397c-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="2397c-128">9 以降の以前のオフセットは、20 の新しいオフセットにマップされます。</span><span class="sxs-lookup"><span data-stu-id="2397c-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="2397c-129">0、1、2、3、4、5、6、7、8、または 9 の新しいオフセットは、以前のオフセット 0 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2397c-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="2397c-130">10、11、12、13、14、15、16、17、18 または 19 の新しいオフセットは、以前のオフセット 5 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2397c-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="2397c-131">20 以上の新しいオフセットは、以前のオフセット 9 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2397c-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2397c-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="2397c-132">Requirements</span></span>  
 <span data-ttu-id="2397c-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2397c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2397c-134">**ヘッダー:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="2397c-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="2397c-135">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2397c-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2397c-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2397c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2397c-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="2397c-137">See also</span></span>

- [<span data-ttu-id="2397c-138">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="2397c-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="2397c-139">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2397c-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
