---
title: ICorProfilerInfo2::GetObjectGeneration メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ab77b3e57213bd2c697dcb9222055b8d8f49210
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782279"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="bcf91-102">ICorProfilerInfo2::GetObjectGeneration メソッド</span><span class="sxs-lookup"><span data-stu-id="bcf91-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="bcf91-103">指定したオブジェクトが含まれるヒープのセグメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="bcf91-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcf91-104">構文</span><span class="sxs-lookup"><span data-stu-id="bcf91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcf91-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcf91-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="bcf91-106">[in]オブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="bcf91-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="bcf91-107">[out]ポインターを[COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)構造体は、ガベージ コレクション ジェネレーション内のメモリの範囲 (ブロック) について説明します。</span><span class="sxs-lookup"><span data-stu-id="bcf91-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="bcf91-108">この範囲には、指定したオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bcf91-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcf91-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="bcf91-109">Remarks</span></span>  
 <span data-ttu-id="bcf91-110">`GetObjectGeneration`メソッドは、ガベージ コレクションが行われていないことの任意のプロファイラー コールバックから呼び出すことがあります。</span><span class="sxs-lookup"><span data-stu-id="bcf91-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="bcf91-111">つまりの間に発生するものを除く任意のコールバックから呼び出すことがあります[icorprofilercallback 2::garbagecollectionstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)と[icorprofilercallback 2::garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="bcf91-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcf91-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="bcf91-112">Requirements</span></span>  
 <span data-ttu-id="bcf91-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcf91-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcf91-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bcf91-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bcf91-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcf91-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcf91-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcf91-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf91-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcf91-117">See also</span></span>

- [<span data-ttu-id="bcf91-118">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcf91-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="bcf91-119">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcf91-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
