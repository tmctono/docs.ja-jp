---
title: ICorDebugProcess5::EnumerateHandles メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3cc158c48e8bb9f833429bbddaa74ed459f1b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930274"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="55932-102">ICorDebugProcess5::EnumerateHandles メソッド</span><span class="sxs-lookup"><span data-stu-id="55932-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="55932-103">プロセスでオブジェクト ハンドルの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="55932-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55932-104">構文</span><span class="sxs-lookup"><span data-stu-id="55932-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55932-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55932-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="55932-106">[in]ビットごとの組み合わせ[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)コレクションに含めるへのハンドルの種類を指定する値。</span><span class="sxs-lookup"><span data-stu-id="55932-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="55932-107">[out]アドレスへのポインター、 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)ガベージ コレクトされる列挙子は、オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="55932-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55932-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="55932-108">Remarks</span></span>  
 <span data-ttu-id="55932-109">`EnumerateHandles` ハンドル テーブルの検査をサポートするヘルパー関数です。</span><span class="sxs-lookup"><span data-stu-id="55932-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="55932-110">似ています、 [icordebugprocess 5::enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)点を除いて、メソッドの設定ではなく、 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)ガベージ コレクトされるすべてのオブジェクトを使用して、コレクション、ハンドル テーブルからのハンドルを持つオブジェクトのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="55932-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="55932-111">`types`パラメーターがコレクションに含めるハンドルの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="55932-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="55932-112">`types` 次の 3 つのメンバーのいずれか、 [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="55932-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="55932-113">`CorHandleStrongOnly` (ハンドルを強力な参照のみ)。</span><span class="sxs-lookup"><span data-stu-id="55932-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="55932-114">`CorHandleWeakOnly` (弱い参照のみへのハンドル)。</span><span class="sxs-lookup"><span data-stu-id="55932-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="55932-115">`CorHandleAll` (すべてのハンドル)。</span><span class="sxs-lookup"><span data-stu-id="55932-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55932-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="55932-116">Requirements</span></span>  
 <span data-ttu-id="55932-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55932-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55932-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55932-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55932-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55932-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55932-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55932-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55932-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="55932-121">See also</span></span>

- [<span data-ttu-id="55932-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="55932-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="55932-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="55932-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
