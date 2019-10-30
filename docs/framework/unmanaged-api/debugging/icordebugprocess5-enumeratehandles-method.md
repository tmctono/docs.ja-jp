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
ms.openlocfilehash: e0e68dba1f4d9ac5fa618aa842b823dcc046e70e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129676"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="c0d92-102">ICorDebugProcess5::EnumerateHandles メソッド</span><span class="sxs-lookup"><span data-stu-id="c0d92-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="c0d92-103">プロセス内のオブジェクトハンドルの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0d92-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d92-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0d92-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0d92-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0d92-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="c0d92-106">からコレクションに含めるハンドルの種類を指定する[Corgcreの](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="c0d92-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="c0d92-107">入出力ガベージコレクションの対象となるオブジェクトの列挙子[である、](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)ツールのアドレスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="c0d92-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0d92-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0d92-108">Remarks</span></span>  
 <span data-ttu-id="c0d92-109">`EnumerateHandles` は、ハンドルテーブルの検査をサポートするヘルパー関数です。</span><span class="sxs-lookup"><span data-stu-id="c0d92-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="c0d92-110">これは[ICorDebugProcess5:: EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)メソッドに似ていますが、すべてのオブジェクトがガベージコレクトされるよう[に、すべて](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)のオブジェクトを使用してすべてのオブジェクトを作成するのではなく、からハンドルを持つオブジェクトのみを含むようにする点が異なります。ハンドルテーブル。</span><span class="sxs-lookup"><span data-stu-id="c0d92-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="c0d92-111">`types` パラメーターは、コレクションに含めるハンドルの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0d92-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="c0d92-112">`types`、次の3つのメンバーのいずれかを[Corgcreの型](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)の列挙体にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c0d92-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="c0d92-113">`CorHandleStrongOnly` (厳密な参照へのハンドルのみ)。</span><span class="sxs-lookup"><span data-stu-id="c0d92-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="c0d92-114">`CorHandleWeakOnly` (弱参照のみを処理します)。</span><span class="sxs-lookup"><span data-stu-id="c0d92-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="c0d92-115">`CorHandleAll` (すべてのハンドル)。</span><span class="sxs-lookup"><span data-stu-id="c0d92-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0d92-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="c0d92-116">Requirements</span></span>  
 <span data-ttu-id="c0d92-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d92-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0d92-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0d92-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0d92-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0d92-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0d92-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0d92-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d92-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0d92-121">See also</span></span>

- [<span data-ttu-id="c0d92-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="c0d92-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="c0d92-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c0d92-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
