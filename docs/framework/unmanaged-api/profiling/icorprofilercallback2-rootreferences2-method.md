---
title: ICorProfilerCallback2::RootReferences2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
ms.openlocfilehash: dffd4365669da61f7b321110ad663c131ce591e6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439670"
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="82cbe-102">ICorProfilerCallback2::RootReferences2 メソッド</span><span class="sxs-lookup"><span data-stu-id="82cbe-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="82cbe-103">ガベージコレクションが発生した後のルート参照をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="82cbe-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="82cbe-104">このメソッドは、 [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)メソッドの拡張です。</span><span class="sxs-lookup"><span data-stu-id="82cbe-104">This method is an extension of the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82cbe-105">構文</span><span class="sxs-lookup"><span data-stu-id="82cbe-105">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82cbe-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82cbe-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="82cbe-107">から`rootRefIds`、`rootKinds`、`rootFlags`、および `rootIds` の各配列内の要素の数。</span><span class="sxs-lookup"><span data-stu-id="82cbe-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="82cbe-108">からオブジェクト Id の配列。それぞれが静的オブジェクトまたはスタック上のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="82cbe-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="82cbe-109">`rootKinds` 配列内の要素は、`rootRefIds` 配列内の対応する要素を分類するための情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="82cbe-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="82cbe-110">からガベージコレクションのルートの型を示す[COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)値の配列。</span><span class="sxs-lookup"><span data-stu-id="82cbe-110">[in] An array of [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="82cbe-111">からガベージコレクションのルートのプロパティを記述する[COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)値の配列。</span><span class="sxs-lookup"><span data-stu-id="82cbe-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="82cbe-112">から`rootKinds` パラメーターの値に応じて、ガベージコレクションのルートに関する追加情報を格納している整数を指す UINT_PTR 値の配列。</span><span class="sxs-lookup"><span data-stu-id="82cbe-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="82cbe-113">ルートの型がスタックの場合、ルート ID は変数を含む関数を示します。</span><span class="sxs-lookup"><span data-stu-id="82cbe-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="82cbe-114">そのルート ID が0の場合、関数は CLR の内部にある名前のない関数です。</span><span class="sxs-lookup"><span data-stu-id="82cbe-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="82cbe-115">ルートの型がハンドルの場合、ルート ID はガベージコレクションハンドル用です。</span><span class="sxs-lookup"><span data-stu-id="82cbe-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="82cbe-116">その他のルート型では、ID は不透明な値であるため、無視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82cbe-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82cbe-117">コメント</span><span class="sxs-lookup"><span data-stu-id="82cbe-117">Remarks</span></span>  
 <span data-ttu-id="82cbe-118">`rootRefIds`、`rootKinds`、`rootFlags`、および `rootIds` 配列は並列配列です。</span><span class="sxs-lookup"><span data-stu-id="82cbe-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="82cbe-119">つまり、`rootRefIds[i]`、`rootKinds[i]`、`rootFlags[i]`、および `rootIds[i]` はすべて同じルートに関係しています。</span><span class="sxs-lookup"><span data-stu-id="82cbe-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="82cbe-120">`RootReferences` と `RootReferences2` の両方が、プロファイラーに通知するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="82cbe-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="82cbe-121">通常、プロファイラーは1つのメソッドを実装しますが、両方は実装しません。 `RootReferences2` 渡される情報は `RootReferences`で渡されるのスーパーセットであるためです。</span><span class="sxs-lookup"><span data-stu-id="82cbe-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="82cbe-122">`rootRefIds` のエントリをゼロにすることができます。これは、対応するルート参照が null で、マネージヒープ上のオブジェクトを参照しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="82cbe-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="82cbe-123">`RootReferences2` によって返されるオブジェクト Id は、コールバック自体では無効です。これは、ガベージコレクションが古いアドレスから新しいアドレスにオブジェクトを移動する途中である可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="82cbe-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="82cbe-124">このため、`RootReferences2` 呼び出しの間、プロファイラーはオブジェクトを検査するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="82cbe-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="82cbe-125">[ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)が呼び出されると、すべてのオブジェクトが新しい場所に移動され、安全に検査できるようになります。</span><span class="sxs-lookup"><span data-stu-id="82cbe-125">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82cbe-126">要件</span><span class="sxs-lookup"><span data-stu-id="82cbe-126">Requirements</span></span>  
 <span data-ttu-id="82cbe-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82cbe-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82cbe-128">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82cbe-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82cbe-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82cbe-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82cbe-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82cbe-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82cbe-131">参照</span><span class="sxs-lookup"><span data-stu-id="82cbe-131">See also</span></span>

- [<span data-ttu-id="82cbe-132">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82cbe-132">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="82cbe-133">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82cbe-133">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
