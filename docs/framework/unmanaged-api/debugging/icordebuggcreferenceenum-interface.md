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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f09a8974dc1e8cb20185975c42c1cb3ad86a5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647156"
---
# <a name="icordebuggcreferenceenum-interface"></a><span data-ttu-id="35f7f-102">ICorDebugGCReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35f7f-102">ICorDebugGCReferenceEnum Interface</span></span>
<span data-ttu-id="35f7f-103">ガベージ コレクトされるオブジェクトの列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="35f7f-103">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35f7f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="35f7f-104">Methods</span></span>  
  
|<span data-ttu-id="35f7f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="35f7f-105">Method</span></span>|<span data-ttu-id="35f7f-106">説明</span><span class="sxs-lookup"><span data-stu-id="35f7f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35f7f-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="35f7f-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|<span data-ttu-id="35f7f-108">指定した数を取得[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)ガベージ コレクトされるオブジェクトに関する情報が含まれているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="35f7f-108">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35f7f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="35f7f-109">Remarks</span></span>  
 <span data-ttu-id="35f7f-110">`ICorDebugGCReferenceEnum` "ICorDebugEnum"インターフェイスを実装するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="35f7f-110">The `ICorDebugGCReferenceEnum` interface implements the "ICorDebugEnum" interface.</span></span>  
  
 <span data-ttu-id="35f7f-111">`ICorDebugGCReferenceEnum`インスタンスには、 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)インスタンスを呼び出すことによって、 [icordebugprocess 5::enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="35f7f-111">An `ICorDebugGCReferenceEnum` instance is populated with [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances by calling the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method.</span></span> <span data-ttu-id="35f7f-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)オブジェクトを呼び出すことによって列挙できる、 [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="35f7f-112">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects can be enumerated by calling the [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="35f7f-113">[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)このメソッドによって設定されます。 コレクション内のオブジェクトは、3 種類のオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="35f7f-113">The [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects in the collection populated by this method represent three kinds of objects:</span></span>  
  
- <span data-ttu-id="35f7f-114">すべてのマネージ スタックからオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="35f7f-114">Objects from all managed stacks.</span></span> <span data-ttu-id="35f7f-115">これには、マネージ コードだけではなく、共通言語ランタイムによって作成されたオブジェクトでのライブ参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="35f7f-115">This includes live references in managed code as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="35f7f-116">オブジェクト ハンドル テーブルをします。</span><span class="sxs-lookup"><span data-stu-id="35f7f-116">Objects from the handle table.</span></span> <span data-ttu-id="35f7f-117">強い参照が含まれます (`HNDTYPE_STRONG`と`HNDTYPE_REFCOUNT`) とモジュールの静的変数。</span><span class="sxs-lookup"><span data-stu-id="35f7f-117">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="35f7f-118">ファイナライザー キューからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="35f7f-118">Objects from the finalizer queue.</span></span> <span data-ttu-id="35f7f-119">ファイナライザー キューでは、ファイナライザーが実行されるまでオブジェクトがルートします。</span><span class="sxs-lookup"><span data-stu-id="35f7f-119">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35f7f-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="35f7f-120">Requirements</span></span>  
 <span data-ttu-id="35f7f-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35f7f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35f7f-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35f7f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35f7f-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35f7f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35f7f-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35f7f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f7f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="35f7f-125">See also</span></span>

- [<span data-ttu-id="35f7f-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35f7f-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
