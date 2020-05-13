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
ms.openlocfilehash: 5650a7e6e6cb0108f0d043914ea94debe2b703bf
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213102"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="2e9d9-102">ICorDebugGCReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e9d9-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="2e9d9-103">ガベージ コレクトされるオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e9d9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2e9d9-104">Methods</span></span>  
  
|<span data-ttu-id="2e9d9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2e9d9-105">Method</span></span>|<span data-ttu-id="2e9d9-106">説明</span><span class="sxs-lookup"><span data-stu-id="2e9d9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e9d9-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="2e9d9-107">Next Method</span></span>](icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="2e9d9-108">ガベージコレクトされるオブジェクトに関する情報を格納している、指定した数の[COR_GC_REFERENCE](cor-gc-reference-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-108">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e9d9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e9d9-109">Remarks</span></span>  
 <span data-ttu-id="2e9d9-110">`ICorDebugGCReferenceEnum`インターフェイスは、"ICorDebugEnum" インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="2e9d9-111">`ICorDebugGCReferenceEnum`インスタンスには、 [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md)メソッドを呼び出すことによって[COR_GC_REFERENCE](cor-gc-reference-structure.md)インスタンスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="2e9d9-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md)オブジェクトは、 [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md)メソッドを呼び出すことによって列挙できます。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-112">[COR_GC_REFERENCE](cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="2e9d9-113">このメソッドによって設定されるコレクション内の[COR_GC_REFERENCE](cor-gc-reference-structure.md)オブジェクトは、次の3種類のオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-113">The [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="2e9d9-114">すべてのマネージスタックからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-114">Objects from all managed stacks.</span></span> <span data-ttu-id="2e9d9-115">これには、マネージコードのライブ参照や、共通言語ランタイムによって作成されたオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="2e9d9-116">ハンドルテーブルのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-116">Objects from the handle table.</span></span> <span data-ttu-id="2e9d9-117">これには、モジュール内の厳密な参照 ( `HNDTYPE_STRONG` および `HNDTYPE_REFCOUNT` ) と静的変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="2e9d9-118">ファイナライザーキューからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="2e9d9-119">ファイナライザーが実行されるまで、ファイナライザーはオブジェクトをキューに置いています。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e9d9-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="2e9d9-120">Requirements</span></span>  
 <span data-ttu-id="2e9d9-121">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e9d9-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e9d9-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e9d9-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e9d9-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e9d9-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e9d9-124">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e9d9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9d9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e9d9-125">See also</span></span>

- [<span data-ttu-id="2e9d9-126">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e9d9-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
