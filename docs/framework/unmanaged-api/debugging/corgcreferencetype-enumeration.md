---
title: CorGCReferenceType 列挙型
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 690d556eb3991747d1627bae63b9c59ca68daaaa
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616216"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="5cc3a-102">CorGCReferenceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="5cc3a-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="5cc3a-103">ガベージ コレクトされる必要のあるオブジェクトのソースを識別します。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc3a-104">構文</span><span class="sxs-lookup"><span data-stu-id="5cc3a-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="5cc3a-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5cc3a-105">Members</span></span>  
  
|<span data-ttu-id="5cc3a-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="5cc3a-106">Member name</span></span>|<span data-ttu-id="5cc3a-107">説明</span><span class="sxs-lookup"><span data-stu-id="5cc3a-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="5cc3a-108">オブジェクト ハンドル テーブルからの強い参照へのハンドル。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="5cc3a-109">オブジェクト ハンドル テーブルから固定された強い参照へのハンドル。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="5cc3a-110">オブジェクト ハンドル テーブルからの弱い参照をへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="5cc3a-111">オブジェクト ハンドル テーブルから弱い参照カウント オブジェクトへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="5cc3a-112">オブジェクト ハンドル テーブルから参照カウント オブジェクトへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="5cc3a-113">オブジェクト ハンドル テーブルから、依存オブジェクトへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="5cc3a-114">オブジェクト ハンドル テーブルからの非同期固定オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="5cc3a-115">ガベージ コレクション時に、すべてのオブジェクトおよびオブジェクト ルートの集合的なクロージャの概算サイズを保持する強力なハンドル。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="5cc3a-116">マネージ スタックからの参照。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="5cc3a-117">ファイナライザー キューからの参照。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="5cc3a-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="5cc3a-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="5cc3a-119">ハンドル テーブルからの強い参照のみを返します。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="5cc3a-120">この値は使用、 [icordebugprocess 5::enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)メソッドのみです。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="5cc3a-121">ハンドル テーブルからの弱い参照のみを返します。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="5cc3a-122">この値は使用、 [icordebugprocess 5::enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)メソッドのみです。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="5cc3a-123">ハンドル テーブルからすべての参照を返します。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-123">Return all references from the handle table.</span></span> <span data-ttu-id="5cc3a-124">この値は使用、 [icordebugprocess 5::enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)メソッドのみです。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cc3a-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="5cc3a-125">Remarks</span></span>  
 <span data-ttu-id="5cc3a-126">`CorGCReferenceType`列挙体は次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="5cc3a-127">値として、`type`のフィールド、 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)構造の参照またはハンドルのソースを示します。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="5cc3a-128">として、`types`への引数、 [icordebugprocess 5::enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)メソッド、列挙体に含めるハンドルの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc3a-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="5cc3a-129">Requirements</span></span>  
 <span data-ttu-id="5cc3a-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cc3a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cc3a-131">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cc3a-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cc3a-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cc3a-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cc3a-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cc3a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc3a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cc3a-134">See also</span></span>

- [<span data-ttu-id="5cc3a-135">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="5cc3a-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
