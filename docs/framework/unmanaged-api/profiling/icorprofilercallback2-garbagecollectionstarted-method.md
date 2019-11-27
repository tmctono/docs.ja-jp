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
ms.openlocfilehash: ed2553f2d971deefd85f731dd39f383cd096c5b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439817"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="176fa-102">ICorProfilerCallback2::GarbageCollectionStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="176fa-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="176fa-103">ガベージコレクションが開始されたことをコードプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="176fa-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="176fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="176fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="176fa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="176fa-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="176fa-106">から`generationCollected` 配列内のエントリの合計数。</span><span class="sxs-lookup"><span data-stu-id="176fa-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="176fa-107">からブール値の配列。配列インデックスに対応する世代がこのガベージコレクションによって収集されている場合に `true` ます。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="176fa-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="176fa-108">配列は、生成を示す[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)列挙体の値によってインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="176fa-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="176fa-109">からガベージコレクションが発生した理由を示す[COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="176fa-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="176fa-110">コメント</span><span class="sxs-lookup"><span data-stu-id="176fa-110">Remarks</span></span>  
 <span data-ttu-id="176fa-111">このガベージコレクションに関連するすべてのコールバックは、`GarbageCollectionStarted` コールバックと、対応する[ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)コールバックの間で発生します。</span><span class="sxs-lookup"><span data-stu-id="176fa-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="176fa-112">これらのコールバックは、同じスレッドでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="176fa-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="176fa-113">`GarbageCollectionStarted` コールバック中に、プロファイラーが元の場所のオブジェクトを検査するのは安全です。</span><span class="sxs-lookup"><span data-stu-id="176fa-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="176fa-114">`GarbageCollectionStarted`から戻った後、ガベージコレクターがオブジェクトの移動を開始します。</span><span class="sxs-lookup"><span data-stu-id="176fa-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="176fa-115">プロファイラーは、このコールバックから返された後、`ICorProfilerCallback2::GarbageCollectionFinished` コールバックを受け取るまで、すべてのオブジェクト Id が無効であると見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="176fa-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="176fa-116">要件</span><span class="sxs-lookup"><span data-stu-id="176fa-116">Requirements</span></span>  
 <span data-ttu-id="176fa-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="176fa-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="176fa-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="176fa-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="176fa-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="176fa-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="176fa-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="176fa-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176fa-121">参照</span><span class="sxs-lookup"><span data-stu-id="176fa-121">See also</span></span>

- [<span data-ttu-id="176fa-122">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="176fa-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="176fa-123">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="176fa-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
