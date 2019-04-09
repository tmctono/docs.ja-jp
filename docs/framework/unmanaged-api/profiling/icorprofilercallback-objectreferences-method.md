---
title: ICorProfilerCallback::ObjectReferences メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1142b33f029708d93cc3b808dc6be2b2df5b0ee3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119250"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="d4e43-102">ICorProfilerCallback::ObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="d4e43-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="d4e43-103">指定したオブジェクトによって参照されているメモリ内のオブジェクトをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d4e43-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e43-104">構文</span><span class="sxs-lookup"><span data-stu-id="d4e43-104">Syntax</span></span>  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4e43-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d4e43-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="d4e43-106">[in]オブジェクトを参照しているオブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="d4e43-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="d4e43-107">[in]指定したオブジェクトのインスタンスでは、クラスの ID。</span><span class="sxs-lookup"><span data-stu-id="d4e43-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="d4e43-108">[in]指定したオブジェクトによって参照されるオブジェクトの数 (つまり、内の要素の数、`objectRefIds`配列)。</span><span class="sxs-lookup"><span data-stu-id="d4e43-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="d4e43-109">[in]によって参照されるオブジェクトの Id の配列`objectId`します。</span><span class="sxs-lookup"><span data-stu-id="d4e43-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4e43-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d4e43-110">Remarks</span></span>  
 <span data-ttu-id="d4e43-111">`ObjectReferences`ガベージ コレクションが完了した後のヒープの残りの各オブジェクトのメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d4e43-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="d4e43-112">プロファイラーがこのコールバックからエラーを返した場合、プロファイリング サービスは、次のガベージ コレクションされるまでこのコールバックの呼び出しを中止します。</span><span class="sxs-lookup"><span data-stu-id="d4e43-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="d4e43-113">`ObjectReferences`コールバックを組み合わせて使用することができます、 [icorprofilercallback::rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)ランタイムの完全なオブジェクト参照グラフを作成するコールバック。</span><span class="sxs-lookup"><span data-stu-id="d4e43-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="d4e43-114">共通言語ランタイム (CLR) により、それぞれのオブジェクト参照を一度だけ報告、`ObjectReferences`メソッド。</span><span class="sxs-lookup"><span data-stu-id="d4e43-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="d4e43-115">によって返されるオブジェクト Id`ObjectReferences`コールバック自体の中に無効なため、オブジェクトを移動中にガベージ コレクションがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d4e43-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="d4e43-116">そのため、プロファイラーは、中にオブジェクトを検査する試行する必要がありますいないを`ObjectReferences`呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d4e43-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="d4e43-117">ときに[icorprofilercallback 2::garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)を呼び出すと、ガベージ コレクションが完了し、検査を安全に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d4e43-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="d4e43-118">Null`ClassId`ことを示します`objectId`型をアンロードしていますがあります。</span><span class="sxs-lookup"><span data-stu-id="d4e43-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4e43-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="d4e43-119">Requirements</span></span>  
 <span data-ttu-id="d4e43-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4e43-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4e43-121">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d4e43-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d4e43-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4e43-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d4e43-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d4e43-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d4e43-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4e43-124">See also</span></span>

- [<span data-ttu-id="d4e43-125">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4e43-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
