---
title: COR_HEAPINFO 構造体
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7b340a73aa9eaebca9c0d78563ae298557039b8
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274192"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="68f3d-102">COR_HEAPINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="68f3d-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="68f3d-103">列挙可能かどうかなど、ガベージ コレクション ヒープに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="68f3d-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68f3d-104">構文</span><span class="sxs-lookup"><span data-stu-id="68f3d-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="68f3d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="68f3d-105">Members</span></span>  
  
|<span data-ttu-id="68f3d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="68f3d-106">Member</span></span>|<span data-ttu-id="68f3d-107">説明</span><span class="sxs-lookup"><span data-stu-id="68f3d-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="68f3d-108">`true`ガベージコレクション構造体が有効で、ヒープを列挙できる場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="68f3d-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="68f3d-109">ターゲットアーキテクチャのポインターのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="68f3d-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="68f3d-110">プロセス内の論理ガベージコレクションヒープの数。</span><span class="sxs-lookup"><span data-stu-id="68f3d-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="68f3d-111">`TRUE`同時実行 (バックグラウンド) ガベージコレクションが有効な場合は。それ以外`FALSE`の場合は。</span><span class="sxs-lookup"><span data-stu-id="68f3d-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="68f3d-112">ガベージコレクターがワークステーションまたはサーバーのどちらで実行されているかを示す[CorDebugGCType](cordebuggctype-enumeration.md)列挙体のメンバー。</span><span class="sxs-lookup"><span data-stu-id="68f3d-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68f3d-113">コメント</span><span class="sxs-lookup"><span data-stu-id="68f3d-113">Remarks</span></span>  
 <span data-ttu-id="68f3d-114">`COR_HEAPINFO`構造体のインスタンスは、 [ICorDebugProcess5:: getg apinformation](icordebugprocess5-getgcheapinformation-method.md)メソッドを呼び出すことによって返されます。</span><span class="sxs-lookup"><span data-stu-id="68f3d-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="68f3d-115">ガベージコレクションヒープ上のオブジェクトを列挙する前に、必ずフィールド`areGCStructuresValid`をチェックして、ヒープが列挙可能な状態であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68f3d-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="68f3d-116">詳細については、「 [ICorDebugProcess5:: Getg](icordebugprocess5-getgcheapinformation-method.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68f3d-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68f3d-117">要件</span><span class="sxs-lookup"><span data-stu-id="68f3d-117">Requirements</span></span>  
 <span data-ttu-id="68f3d-118">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68f3d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68f3d-119">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="68f3d-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68f3d-120">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="68f3d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68f3d-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68f3d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f3d-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="68f3d-122">See also</span></span>

- [<span data-ttu-id="68f3d-123">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="68f3d-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="68f3d-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="68f3d-124">Debugging</span></span>](index.md)
