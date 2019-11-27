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
ms.openlocfilehash: 4f8cfd912a3d6f66f5f2586a8942c7ce9bd52a63
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445891"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="d55b7-102">ICorProfilerCallback::ObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="d55b7-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="d55b7-103">指定したオブジェクトによって参照されているメモリ内のオブジェクトに関する情報をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d55b7-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d55b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="d55b7-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d55b7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d55b7-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="d55b7-106">からオブジェクトを参照しているオブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="d55b7-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="d55b7-107">から指定したオブジェクトがインスタンスであるクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="d55b7-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="d55b7-108">から指定したオブジェクトによって参照されるオブジェクトの数 (つまり、`objectRefIds` 配列内の要素の数)。</span><span class="sxs-lookup"><span data-stu-id="d55b7-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="d55b7-109">から`objectId`によって参照されているオブジェクトの Id の配列。</span><span class="sxs-lookup"><span data-stu-id="d55b7-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d55b7-110">コメント</span><span class="sxs-lookup"><span data-stu-id="d55b7-110">Remarks</span></span>  
 <span data-ttu-id="d55b7-111">`ObjectReferences` メソッドは、ガベージコレクションが完了した後にヒープ内の残りのオブジェクトに対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d55b7-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="d55b7-112">プロファイラーがこのコールバックからエラーを返すと、プロファイリングサービスは、次のガベージコレクションまでこのコールバックの呼び出しを中止します。</span><span class="sxs-lookup"><span data-stu-id="d55b7-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="d55b7-113">`ObjectReferences` コールバックは、 [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)コールバックと組み合わせて使用して、ランタイムの完全なオブジェクト参照グラフを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d55b7-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="d55b7-114">共通言語ランタイム (CLR) では、各オブジェクト参照が `ObjectReferences` メソッドによって1回だけ報告されるようにします。</span><span class="sxs-lookup"><span data-stu-id="d55b7-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="d55b7-115">`ObjectReferences` によって返されるオブジェクト Id は、コールバック自体では無効です。これは、ガベージコレクションがオブジェクトを移動する途中である可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="d55b7-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="d55b7-116">そのため、`ObjectReferences` の呼び出し中に、プロファイラーがオブジェクトの検査を試行することはできません。</span><span class="sxs-lookup"><span data-stu-id="d55b7-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="d55b7-117">[ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)が呼び出されると、ガベージコレクションが完了し、検査を安全に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d55b7-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="d55b7-118">Null `ClassId` は、`objectId` にアンロード中の型があることを示します。</span><span class="sxs-lookup"><span data-stu-id="d55b7-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d55b7-119">要件</span><span class="sxs-lookup"><span data-stu-id="d55b7-119">Requirements</span></span>  
 <span data-ttu-id="d55b7-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d55b7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d55b7-121">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d55b7-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d55b7-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d55b7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d55b7-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d55b7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d55b7-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d55b7-124">See also</span></span>

- [<span data-ttu-id="d55b7-125">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d55b7-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
