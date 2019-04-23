---
title: ICorDebugHeapEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79ef77e52e14fede9949121e7ec4575d10b820c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135851"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="8c216-102">ICorDebugHeapEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c216-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="8c216-103">マネージド ヒープのオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="8c216-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="8c216-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="8c216-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c216-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8c216-105">Methods</span></span>  
  
|<span data-ttu-id="8c216-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="8c216-106">Method</span></span>|<span data-ttu-id="8c216-107">説明</span><span class="sxs-lookup"><span data-stu-id="8c216-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8c216-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="8c216-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="8c216-109">指定した数を取得[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)マネージ ヒープ上のオブジェクトに関する情報が含まれているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="8c216-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c216-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c216-110">Remarks</span></span>  
 <span data-ttu-id="8c216-111">`ICorDebugHeapEnum` ICorDebugEnum インターフェイスを実装するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="8c216-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="8c216-112">`ICorDebugHeapEnum`インスタンスには、 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)インスタンスを呼び出すことによって、 [icordebugprocess 5::enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="8c216-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="8c216-113">各[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)コレクション内のインスタンスが、ヒープ上のライブ オブジェクトまたはオブジェクトでルートがありませんが、ガベージ コレクターによって収集されていないオブジェクトのいずれかを表します。</span><span class="sxs-lookup"><span data-stu-id="8c216-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="8c216-114">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)呼び出すことによって、コレクション内のオブジェクトを列挙することができます、 [icordebugheapenum::next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="8c216-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c216-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c216-115">Requirements</span></span>  
 <span data-ttu-id="8c216-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c216-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c216-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c216-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c216-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c216-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c216-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c216-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c216-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c216-120">See also</span></span>

- [<span data-ttu-id="8c216-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c216-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
