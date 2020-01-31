---
title: CorGCReferenceType 列挙体
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
ms.openlocfilehash: 17d47b6242bb12ff5ca3cfbde3e4ec183b9c19fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793874"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="2c982-102">CorGCReferenceType 列挙体</span><span class="sxs-lookup"><span data-stu-id="2c982-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="2c982-103">ガベージ コレクトされる必要のあるオブジェクトのソースを識別します。</span><span class="sxs-lookup"><span data-stu-id="2c982-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c982-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c982-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="2c982-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="2c982-105">Members</span></span>  
  
|<span data-ttu-id="2c982-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="2c982-106">Member name</span></span>|<span data-ttu-id="2c982-107">説明</span><span class="sxs-lookup"><span data-stu-id="2c982-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="2c982-108">オブジェクト ハンドル テーブルからの強い参照へのハンドル。</span><span class="sxs-lookup"><span data-stu-id="2c982-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="2c982-109">オブジェクトハンドルテーブルからの固定された強い参照へのハンドル。</span><span class="sxs-lookup"><span data-stu-id="2c982-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="2c982-110">オブジェクトハンドルテーブルからの弱い参照へのハンドル。</span><span class="sxs-lookup"><span data-stu-id="2c982-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="2c982-111">オブジェクトハンドルテーブルからの弱い参照カウントオブジェクトへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="2c982-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="2c982-112">オブジェクトハンドルテーブルからの参照カウントオブジェクトへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="2c982-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="2c982-113">オブジェクトハンドルテーブルからの依存オブジェクトへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="2c982-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="2c982-114">オブジェクト ハンドル テーブルからの非同期固定オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2c982-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="2c982-115">ガベージ コレクション時に、すべてのオブジェクトおよびオブジェクト ルートの集合的なクロージャの概算サイズを保持する強力なハンドル。</span><span class="sxs-lookup"><span data-stu-id="2c982-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="2c982-116">マネージスタックからの参照。</span><span class="sxs-lookup"><span data-stu-id="2c982-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="2c982-117">ファイナライザーキューからの参照。</span><span class="sxs-lookup"><span data-stu-id="2c982-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="2c982-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="2c982-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="2c982-119">ハンドルテーブルからの強い参照だけを返します。</span><span class="sxs-lookup"><span data-stu-id="2c982-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="2c982-120">この値は、 [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)メソッドによってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c982-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="2c982-121">ハンドルテーブルからの弱い参照だけを返します。</span><span class="sxs-lookup"><span data-stu-id="2c982-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="2c982-122">この値は、 [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)メソッドによってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c982-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="2c982-123">Handle テーブルからすべての参照を返します。</span><span class="sxs-lookup"><span data-stu-id="2c982-123">Return all references from the handle table.</span></span> <span data-ttu-id="2c982-124">この値は、 [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)メソッドによってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c982-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c982-125">コメント</span><span class="sxs-lookup"><span data-stu-id="2c982-125">Remarks</span></span>  
 <span data-ttu-id="2c982-126">`CorGCReferenceType` 列挙体は次のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c982-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="2c982-127">[COR_GC_REFERENCE](cor-gc-reference-structure.md)構造体の `type` フィールドの値として、参照またはハンドルのソースを示します。</span><span class="sxs-lookup"><span data-stu-id="2c982-127">As the value of the `type` field of the [COR_GC_REFERENCE](cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="2c982-128">[ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)メソッドの `types` 引数として、列挙体に含めるハンドルの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c982-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c982-129">要件</span><span class="sxs-lookup"><span data-stu-id="2c982-129">Requirements</span></span>  
 <span data-ttu-id="2c982-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c982-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c982-131">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c982-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c982-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c982-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c982-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c982-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c982-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c982-134">See also</span></span>

- [<span data-ttu-id="2c982-135">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="2c982-135">Debugging Enumerations</span></span>](debugging-enumerations.md)
