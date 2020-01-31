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
ms.openlocfilehash: 2a1653055a3834ce1bed0e7de7877b255bea0c38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792426"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="b98db-102">ICorDebugProcess5::EnumerateHandles メソッド</span><span class="sxs-lookup"><span data-stu-id="b98db-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="b98db-103">プロセス内のオブジェクトハンドルの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="b98db-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b98db-104">構文</span><span class="sxs-lookup"><span data-stu-id="b98db-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b98db-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b98db-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="b98db-106">からコレクションに含めるハンドルの種類を指定する[Corgcreの](corgcreferencetype-enumeration.md)値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="b98db-106">[in] A bitwise combination of [CorGCReferenceType](corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="b98db-107">入出力ガベージコレクションの対象となるオブジェクトの列挙子[である、](icordebuggcreferenceenum-interface.md)ツールのアドレスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="b98db-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b98db-108">コメント</span><span class="sxs-lookup"><span data-stu-id="b98db-108">Remarks</span></span>  
 <span data-ttu-id="b98db-109">`EnumerateHandles` は、ハンドルテーブルの検査をサポートするヘルパー関数です。</span><span class="sxs-lookup"><span data-stu-id="b98db-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="b98db-110">これは[ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md)メソッドに似ていますが、すべてのオブジェクトがガベージコレクトされるよう[に、すべて](icordebuggcreferenceenum-interface.md)のオブジェクトを使用してすべてのオブジェクトを作成するのではなく、handle テーブルからハンドルを持つオブジェクトのみが含まれる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="b98db-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="b98db-111">`types` パラメーターは、コレクションに含めるハンドルの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="b98db-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="b98db-112">`types`、次の3つのメンバーのいずれかを[Corgcreの型](corgcreferencetype-enumeration.md)の列挙体にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b98db-112">`types` can be any of the following three members of the [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="b98db-113">`CorHandleStrongOnly` (厳密な参照へのハンドルのみ)。</span><span class="sxs-lookup"><span data-stu-id="b98db-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="b98db-114">`CorHandleWeakOnly` (弱参照のみを処理します)。</span><span class="sxs-lookup"><span data-stu-id="b98db-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="b98db-115">`CorHandleAll` (すべてのハンドル)。</span><span class="sxs-lookup"><span data-stu-id="b98db-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b98db-116">要件</span><span class="sxs-lookup"><span data-stu-id="b98db-116">Requirements</span></span>  
 <span data-ttu-id="b98db-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b98db-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b98db-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b98db-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b98db-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b98db-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b98db-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b98db-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98db-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b98db-121">See also</span></span>

- [<span data-ttu-id="b98db-122">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="b98db-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b98db-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b98db-123">Debugging</span></span>](index.md)
