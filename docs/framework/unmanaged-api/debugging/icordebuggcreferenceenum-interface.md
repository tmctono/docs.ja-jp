---
title: ICorDebugGCReferenceEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: 49f89f7d36e74b1fa5921230d7dc6d271d4c0883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134629"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="b3ca9-102">ICorDebugGCReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3ca9-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="b3ca9-103">ガベージ コレクトされるオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3ca9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b3ca9-104">Methods</span></span>  
  
|<span data-ttu-id="b3ca9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b3ca9-105">Method</span></span>|<span data-ttu-id="b3ca9-106">説明</span><span class="sxs-lookup"><span data-stu-id="b3ca9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3ca9-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="b3ca9-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="b3ca9-108">ガベージコレクトされるオブジェクトに関する情報を格納している、指定した数の[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3ca9-109">コメント</span><span class="sxs-lookup"><span data-stu-id="b3ca9-109">Remarks</span></span>  
 <span data-ttu-id="b3ca9-110">`ICorDebugGCReferenceEnum` インターフェイスは、"ICorDebugEnum" インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="b3ca9-111">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) インスタンスには、 [ICorDebugProcess5:: EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)メソッドを呼び出すことによって、 インスタンスが設定されます。 `ICorDebugGCReferenceEnum`</span><span class="sxs-lookup"><span data-stu-id="b3ca9-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="b3ca9-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)オブジェクトは、 [ICorDebugGCReference:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)メソッドを呼び出すことによって列挙できます。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="b3ca9-113">このメソッドによって設定されるコレクション内の[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)オブジェクトは、次の3種類のオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="b3ca9-114">すべてのマネージスタックからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-114">Objects from all managed stacks.</span></span> <span data-ttu-id="b3ca9-115">これには、マネージコードのライブ参照や、共通言語ランタイムによって作成されたオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="b3ca9-116">ハンドルテーブルのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-116">Objects from the handle table.</span></span> <span data-ttu-id="b3ca9-117">これには、厳密な参照 (`HNDTYPE_STRONG` と `HNDTYPE_REFCOUNT`) と、モジュール内の静的変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="b3ca9-118">ファイナライザーキューからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="b3ca9-119">ファイナライザーが実行されるまで、ファイナライザーはオブジェクトをキューに置いています。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3ca9-120">要件</span><span class="sxs-lookup"><span data-stu-id="b3ca9-120">Requirements</span></span>  
 <span data-ttu-id="b3ca9-121">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ca9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3ca9-122">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b3ca9-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3ca9-123">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="b3ca9-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3ca9-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3ca9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ca9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3ca9-125">See also</span></span>

- [<span data-ttu-id="b3ca9-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3ca9-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
