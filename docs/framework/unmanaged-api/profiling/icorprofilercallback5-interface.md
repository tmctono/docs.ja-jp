---
title: ICorProfilerCallback5 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 114d97e02b0a6b80c46f971ed74a24dc3c397f1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072650"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="d376c-102">ICorProfilerCallback5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d376c-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="d376c-103">プロファイラーがいずれかを使用すると、ライブ オブジェクトの完全なクロージャーを識別する補足情報、 [icorprofilercallback::rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)または[icorprofilercallback 2::rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)メソッドと組み合わせて、 [icorprofilercallback::objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)と[ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d376c-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 `ICorProfilerCallback5` <span data-ttu-id="d376c-104">通知に関連する依存ハンドルを購読するマネージ メモリ プロファイラーによって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d376c-104">must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d376c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="d376c-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d376c-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="d376c-106">Methods</span></span>  
  
|<span data-ttu-id="d376c-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="d376c-107">Method</span></span>|<span data-ttu-id="d376c-108">説明</span><span class="sxs-lookup"><span data-stu-id="d376c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d376c-109">ConditionalWeakTableElementReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="d376c-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="d376c-110">直接のメンバー フィールド参照および `ConditionalWeakTable` 依存を介してこれらのルーツによって参照されるオブジェクトの推移的終了を識別します。</span><span class="sxs-lookup"><span data-stu-id="d376c-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d376c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d376c-111">Requirements</span></span>  
 <span data-ttu-id="d376c-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d376c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d376c-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d376c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="d376c-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d376c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d376c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d376c-115">See also</span></span>

- [<span data-ttu-id="d376c-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d376c-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d376c-117">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d376c-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
