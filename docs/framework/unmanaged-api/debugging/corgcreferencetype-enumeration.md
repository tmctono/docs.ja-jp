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
ms.openlocfilehash: 8a673c98b11fbca5f66e9e1ae61f224448c20797
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207150"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="deeb5-102">CorGCReferenceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="deeb5-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="deeb5-103">ガベージ コレクトされる必要のあるオブジェクトのソースを識別します。</span><span class="sxs-lookup"><span data-stu-id="deeb5-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deeb5-104">構文</span><span class="sxs-lookup"><span data-stu-id="deeb5-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="deeb5-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="deeb5-105">Members</span></span>  
  
|<span data-ttu-id="deeb5-106">メンバー名</span><span class="sxs-lookup"><span data-stu-id="deeb5-106">Member name</span></span>|<span data-ttu-id="deeb5-107">説明</span><span class="sxs-lookup"><span data-stu-id="deeb5-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="deeb5-108">オブジェクト ハンドル テーブルからの強い参照へのハンドル。</span><span class="sxs-lookup"><span data-stu-id="deeb5-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="deeb5-109">オブジェクト ハンドル テーブルから固定された強い参照へのハンドル。</span><span class="sxs-lookup"><span data-stu-id="deeb5-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="deeb5-110">オブジェクト ハンドル テーブルからの弱い参照をへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="deeb5-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="deeb5-111">オブジェクト ハンドル テーブルから弱い参照カウント オブジェクトへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="deeb5-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="deeb5-112">オブジェクト ハンドル テーブルから参照カウント オブジェクトへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="deeb5-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="deeb5-113">オブジェクト ハンドル テーブルから、依存オブジェクトへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="deeb5-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="deeb5-114">オブジェクト ハンドル テーブルからの非同期固定オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="deeb5-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="deeb5-115">ガベージ コレクション時に、すべてのオブジェクトおよびオブジェクト ルートの集合的なクロージャの概算サイズを保持する強力なハンドル。</span><span class="sxs-lookup"><span data-stu-id="deeb5-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="deeb5-116">マネージ スタックからの参照。</span><span class="sxs-lookup"><span data-stu-id="deeb5-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="deeb5-117">ファイナライザー キューからの参照。</span><span class="sxs-lookup"><span data-stu-id="deeb5-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="deeb5-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="deeb5-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="deeb5-119">ハンドル テーブルからの強い参照のみを返します。</span><span class="sxs-lookup"><span data-stu-id="deeb5-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="deeb5-120">この値は使用、 [icordebugprocess 5::enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)メソッドのみです。</span><span class="sxs-lookup"><span data-stu-id="deeb5-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="deeb5-121">ハンドル テーブルからの弱い参照のみを返します。</span><span class="sxs-lookup"><span data-stu-id="deeb5-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="deeb5-122">この値は使用、 [icordebugprocess 5::enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)メソッドのみです。</span><span class="sxs-lookup"><span data-stu-id="deeb5-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="deeb5-123">ハンドル テーブルからすべての参照を返します。</span><span class="sxs-lookup"><span data-stu-id="deeb5-123">Return all references from the handle table.</span></span> <span data-ttu-id="deeb5-124">この値は使用、 [icordebugprocess 5::enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)メソッドのみです。</span><span class="sxs-lookup"><span data-stu-id="deeb5-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="deeb5-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="deeb5-125">Remarks</span></span>  
 <span data-ttu-id="deeb5-126">`CorGCReferenceType`列挙体は次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="deeb5-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="deeb5-127">値として、`type`のフィールド、 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)構造の参照またはハンドルのソースを示します。</span><span class="sxs-lookup"><span data-stu-id="deeb5-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="deeb5-128">として、`types`への引数、 [icordebugprocess 5::enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)メソッド、列挙体に含めるハンドルの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="deeb5-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deeb5-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="deeb5-129">Requirements</span></span>  
 <span data-ttu-id="deeb5-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="deeb5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deeb5-131">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="deeb5-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="deeb5-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="deeb5-132">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="deeb5-133">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="deeb5-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="deeb5-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="deeb5-134">See also</span></span>

- [<span data-ttu-id="deeb5-135">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="deeb5-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
