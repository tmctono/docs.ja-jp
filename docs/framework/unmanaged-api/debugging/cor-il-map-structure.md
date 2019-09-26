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
ms.openlocfilehash: 5ae4c5743b01c4a9087323678d315473631cb32f
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274049"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="79053-102">COR_IL_MAP 構造体</span><span class="sxs-lookup"><span data-stu-id="79053-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="79053-103">機能の相対オフセットでの変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="79053-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79053-104">構文</span><span class="sxs-lookup"><span data-stu-id="79053-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="79053-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="79053-105">Members</span></span>  
  
|<span data-ttu-id="79053-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="79053-106">Member</span></span>|<span data-ttu-id="79053-107">説明</span><span class="sxs-lookup"><span data-stu-id="79053-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="79053-108">関数の先頭を基準とした、以前の Microsoft 中間言語 (MSIL) オフセット。</span><span class="sxs-lookup"><span data-stu-id="79053-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="79053-109">関数の先頭を基準とする新しい MSIL オフセット。</span><span class="sxs-lookup"><span data-stu-id="79053-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="79053-110">`true`マッピングが正確であることがわかっている場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="79053-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79053-111">コメント</span><span class="sxs-lookup"><span data-stu-id="79053-111">Remarks</span></span>  
 <span data-ttu-id="79053-112">マップの形式は次のとおりです。デバッガーは、が元`oldOffset`の変更されていない msil コード内の msil オフセットを参照することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="79053-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="79053-113">パラメーター `newOffset`は、新しいインストルメント化されたコード内で、対応する MSIL オフセットを参照します。</span><span class="sxs-lookup"><span data-stu-id="79053-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="79053-114">ステップ実行を正常に行うには、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79053-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="79053-115">マップは昇順に並べ替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="79053-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="79053-116">インストルメント化された MSIL コードを並べ替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="79053-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="79053-117">元の MSIL コードは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="79053-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="79053-118">マップには、プログラムデータベース (PDB) ファイルのすべてのシーケンスポイントをマップするためのエントリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79053-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="79053-119">マップでは、不足しているエントリは補間されません。</span><span class="sxs-lookup"><span data-stu-id="79053-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="79053-120">次の例は、マップとその結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="79053-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="79053-121">付け</span><span class="sxs-lookup"><span data-stu-id="79053-121">Map:</span></span>  
  
- <span data-ttu-id="79053-122">0個の古いオフセット、0個の新しいオフセット</span><span class="sxs-lookup"><span data-stu-id="79053-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="79053-123">5個の古いオフセット、10個の新しいオフセット</span><span class="sxs-lookup"><span data-stu-id="79053-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="79053-124">9個の古いオフセット、20個の新しいオフセット</span><span class="sxs-lookup"><span data-stu-id="79053-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="79053-125">生じ</span><span class="sxs-lookup"><span data-stu-id="79053-125">Results:</span></span>  
  
- <span data-ttu-id="79053-126">0、1、2、3、または4の古いオフセットは、新しいオフセット0にマップされます。</span><span class="sxs-lookup"><span data-stu-id="79053-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="79053-127">古いオフセット5、6、7、または8は、新しいオフセット10にマップされます。</span><span class="sxs-lookup"><span data-stu-id="79053-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="79053-128">9以上の古いオフセットは、新しいオフセット20にマップされます。</span><span class="sxs-lookup"><span data-stu-id="79053-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="79053-129">新しいオフセット0、1、2、3、4、5、6、7、8、または9が古いオフセット0にマップされます。</span><span class="sxs-lookup"><span data-stu-id="79053-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="79053-130">新しいオフセット10、11、12、13、14、15、16、17、18、19は、古いオフセット5にマップされます。</span><span class="sxs-lookup"><span data-stu-id="79053-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="79053-131">20以上の新しいオフセットは、古いオフセット9にマップされます。</span><span class="sxs-lookup"><span data-stu-id="79053-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79053-132">要件</span><span class="sxs-lookup"><span data-stu-id="79053-132">Requirements</span></span>  
 <span data-ttu-id="79053-133">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79053-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79053-134">**ヘッダー:** CorDebug .idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="79053-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="79053-135">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="79053-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79053-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79053-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79053-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="79053-137">See also</span></span>

- [<span data-ttu-id="79053-138">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="79053-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="79053-139">デバッグ</span><span class="sxs-lookup"><span data-stu-id="79053-139">Debugging</span></span>](index.md)
