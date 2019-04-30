---
title: ICorProfilerCallback::RootReferences メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b616017745d7cc33d57b1626b6c27c59a0a60a32
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992291"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="091bb-102">ICorProfilerCallback::RootReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="091bb-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="091bb-103">ガベージ コレクション後のルート参照に関する情報をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="091bb-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="091bb-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="091bb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="091bb-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="091bb-106">[in]参照の数、`rootRefIds`配列。</span><span class="sxs-lookup"><span data-stu-id="091bb-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="091bb-107">[in]静的オブジェクトまたはスタック上のオブジェクトのいずれかを参照するオブジェクト Id の配列。</span><span class="sxs-lookup"><span data-stu-id="091bb-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="091bb-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="091bb-108">Remarks</span></span>  
 <span data-ttu-id="091bb-109">両方`RootReferences`と[icorprofilercallback 2::rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)をプロファイラーに通知と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="091bb-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="091bb-110">プロファイラーは、どちらかを実装通常しますが、どちらで情報が渡されるため`RootReferences2`渡さのスーパー セット`RootReferences`します。</span><span class="sxs-lookup"><span data-stu-id="091bb-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="091bb-111">可能性があります、 `rootRefIds` null オブジェクトを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="091bb-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="091bb-112">たとえば、スタックで宣言されているすべてのオブジェクト参照は、ガベージ コレクターによってルートとして扱われますは常に報告されます。</span><span class="sxs-lookup"><span data-stu-id="091bb-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="091bb-113">によって返されるオブジェクト Id`RootReferences`コールバック自体の中に無効なため、古いアドレスから新しいアドレスにオブジェクトを移動中にガベージ コレクションがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="091bb-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="091bb-114">そのため、プロファイラーは、中にオブジェクトを検査する試行する必要がありますいないを`RootReferences`呼び出します。</span><span class="sxs-lookup"><span data-stu-id="091bb-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="091bb-115">ときに[icorprofilercallback 2::garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)が呼び出されると、すべてのオブジェクトの新しい場所に移動されているし、安全に検査することができます。</span><span class="sxs-lookup"><span data-stu-id="091bb-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="091bb-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="091bb-116">Requirements</span></span>  
 <span data-ttu-id="091bb-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="091bb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="091bb-118">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="091bb-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="091bb-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="091bb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="091bb-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="091bb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091bb-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="091bb-121">See also</span></span>

- [<span data-ttu-id="091bb-122">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="091bb-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
