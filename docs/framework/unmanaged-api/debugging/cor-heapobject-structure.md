---
title: COR_HEAPOBJECT 構造体
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
ms.openlocfilehash: 270360a8950197eca14e02a60554659e5ac7b91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099079"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="d5ecc-102">COR_HEAPOBJECT 構造体</span><span class="sxs-lookup"><span data-stu-id="d5ecc-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="d5ecc-103">マネージド ヒープ上のオブジェクトに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5ecc-104">構文</span><span class="sxs-lookup"><span data-stu-id="d5ecc-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="d5ecc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d5ecc-105">Members</span></span>  
  
|<span data-ttu-id="d5ecc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d5ecc-106">Member</span></span>|<span data-ttu-id="d5ecc-107">説明</span><span class="sxs-lookup"><span data-stu-id="d5ecc-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="d5ecc-108">メモリ内のオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="d5ecc-109">オブジェクトの合計サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="d5ecc-110">オブジェクトの型を表す[COR_TYPEID](cor-typeid-structure.md)トークンです。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5ecc-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5ecc-111">Remarks</span></span>  
 <span data-ttu-id="d5ecc-112">`COR_HEAPOBJECT` インスタンスは、 [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md)メソッドを呼び出すことによって設定された、表示されていない[heapenum](icordebugheapenum-interface.md)インターフェイスオブジェクトを列挙することによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="d5ecc-113">`COR_HEAPOBJECT` インスタンスは、マネージヒープ上のライブオブジェクトに関する情報、またはオブジェクトではなく、ガベージコレクターによってまだ収集されていないオブジェクトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="d5ecc-114">パフォーマンスを向上させるために、`COR_HEAPOBJECT.address` フィールドは、デバッグ API の多くで使用される ICorDebugValue インターフェイス値ではなく `CORDB_ADDRESS` 値です。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="d5ecc-115">指定されたオブジェクトアドレスの ICorDebugValue オブジェクトを取得するには、`CORDB_ADDRESS` 値を[ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md)メソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="d5ecc-116">パフォーマンスを向上させるために、`COR_HEAPOBJECT.type` フィールドは、デバッグ API の多くで使用されているのではなく、`COR_TYPEID` 値です。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="d5ecc-117">指定された型 ID の ICorDebugProcess5 型オブジェクトを取得するには、その値を[:: GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md)メソッドに `COR_TYPEID` 渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="d5ecc-118">`COR_HEAPOBJECT` 構造体には、参照カウントの COM インターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="d5ecc-119">[次](icordebugheapenum-next-method.md)のメソッドを呼び出して列挙子から `COR_HEAPOBJECT` インスタンスを取得する場合は、その後で参照を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5ecc-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="d5ecc-120">Requirements</span></span>  
 <span data-ttu-id="d5ecc-121">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ecc-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5ecc-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5ecc-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5ecc-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5ecc-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5ecc-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5ecc-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ecc-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5ecc-125">See also</span></span>

- [<span data-ttu-id="d5ecc-126">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="d5ecc-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="d5ecc-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d5ecc-127">Debugging</span></span>](index.md)
