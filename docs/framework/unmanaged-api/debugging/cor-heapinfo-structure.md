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
ms.openlocfilehash: b6fd3682290c9752125aed7b9663c6704ade25de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132331"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="303ff-102">COR_HEAPINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="303ff-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="303ff-103">列挙可能かどうかなど、ガベージ コレクション ヒープに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="303ff-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="303ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="303ff-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="303ff-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="303ff-105">Members</span></span>  
  
|<span data-ttu-id="303ff-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="303ff-106">Member</span></span>|<span data-ttu-id="303ff-107">説明</span><span class="sxs-lookup"><span data-stu-id="303ff-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="303ff-108">ガベージコレクション構造が有効で、ヒープを列挙できるかどうかを `true` します。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="303ff-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="303ff-109">ターゲットアーキテクチャのポインターのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="303ff-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="303ff-110">プロセス内の論理ガベージコレクションヒープの数。</span><span class="sxs-lookup"><span data-stu-id="303ff-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="303ff-111">同時実行 (バックグラウンド) ガベージコレクションが有効になっている場合に `TRUE` します。それ以外の場合は、`FALSE`ます。</span><span class="sxs-lookup"><span data-stu-id="303ff-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="303ff-112">ガベージコレクターがワークステーションまたはサーバーのどちらで実行されているかを示す[CorDebugGCType](cordebuggctype-enumeration.md)列挙体のメンバー。</span><span class="sxs-lookup"><span data-stu-id="303ff-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="303ff-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="303ff-113">Remarks</span></span>  
 <span data-ttu-id="303ff-114">[ICorDebugProcess5:: Getg](icordebugprocess5-getgcheapinformation-method.md)メソッドを呼び出すことによって、`COR_HEAPINFO` 構造体のインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="303ff-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="303ff-115">ガベージコレクションヒープのオブジェクトを列挙する前に、必ず `areGCStructuresValid` フィールドをチェックして、ヒープが列挙可能な状態であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="303ff-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="303ff-116">詳細については、「 [ICorDebugProcess5:: Getg](icordebugprocess5-getgcheapinformation-method.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="303ff-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="303ff-117">［要件］</span><span class="sxs-lookup"><span data-stu-id="303ff-117">Requirements</span></span>  
 <span data-ttu-id="303ff-118">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="303ff-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="303ff-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="303ff-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="303ff-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="303ff-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="303ff-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="303ff-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303ff-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="303ff-122">See also</span></span>

- [<span data-ttu-id="303ff-123">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="303ff-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="303ff-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="303ff-124">Debugging</span></span>](index.md)
