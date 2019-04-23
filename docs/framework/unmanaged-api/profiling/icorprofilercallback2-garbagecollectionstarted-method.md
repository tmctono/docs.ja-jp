---
title: ICorProfilerCallback2::GarbageCollectionStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5f9104dded44540c47c955c15354d8d76a27650
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183073"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="8bc3d-102">ICorProfilerCallback2::GarbageCollectionStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="8bc3d-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="8bc3d-103">ガベージ コレクションが開始されたことをコード プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc3d-104">構文</span><span class="sxs-lookup"><span data-stu-id="8bc3d-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bc3d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8bc3d-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="8bc3d-106">[in]内のエントリの合計数、`generationCollected`配列。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="8bc3d-107">[in]ブール値の配列`true`このガベージ コレクションによって収集されます。 それ以外の場合、配列のインデックスに対応する生成されている場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="8bc3d-108">値によって、配列のインデックスが、 [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)列挙体は、ジェネレーションを示します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="8bc3d-109">[in]値、 [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)ガベージ コレクション理由を示す列挙体が発生しました。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bc3d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8bc3d-110">Remarks</span></span>  
 <span data-ttu-id="8bc3d-111">このガベージ コレクションに関連するすべてのコールバック間で発生する、`GarbageCollectionStarted`コールバックと、対応する[icorprofilercallback 2::garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="8bc3d-112">これらのコールバックは、同じスレッドでは発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="8bc3d-113">プロファイラーが中に元の場所にオブジェクトを検査するは安全では、`GarbageCollectionStarted`コールバック。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="8bc3d-114">ガベージ コレクターが移動オブジェクトからの戻り値の後に開始されます`GarbageCollectionStarted`します。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="8bc3d-115">プロファイラーがこのコールバックから戻ると後、プロファイラーが受信するまで無効にするすべてのオブジェクト Id を検討してください、`ICorProfilerCallback2::GarbageCollectionFinished`コールバック。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bc3d-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="8bc3d-116">Requirements</span></span>  
 <span data-ttu-id="8bc3d-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bc3d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bc3d-118">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8bc3d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8bc3d-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bc3d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bc3d-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bc3d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc3d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bc3d-121">See also</span></span>

- [<span data-ttu-id="8bc3d-122">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc3d-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8bc3d-123">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bc3d-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
