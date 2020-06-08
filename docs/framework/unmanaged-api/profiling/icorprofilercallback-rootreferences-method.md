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
ms.openlocfilehash: b587f30a01623c6e9806bcd9d01058a0880be239
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499910"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="f945a-102">ICorProfilerCallback::RootReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="f945a-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="f945a-103">ガベージコレクション後のルート参照に関する情報をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f945a-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f945a-104">構文</span><span class="sxs-lookup"><span data-stu-id="f945a-104">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f945a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f945a-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="f945a-106">から配列内の参照の数 `rootRefIds` 。</span><span class="sxs-lookup"><span data-stu-id="f945a-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="f945a-107">から静的オブジェクトまたはスタック上のオブジェクトのいずれかを参照するオブジェクト Id の配列。</span><span class="sxs-lookup"><span data-stu-id="f945a-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f945a-108">解説</span><span class="sxs-lookup"><span data-stu-id="f945a-108">Remarks</span></span>  
 <span data-ttu-id="f945a-109">`RootReferences`と[ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md)の両方が呼び出され、プロファイラーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="f945a-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="f945a-110">通常、プロファイラーはどちらか一方を実装しますが、渡され `RootReferences2` た情報は渡されたのスーパーセットであるため、両方ではありません `RootReferences` 。</span><span class="sxs-lookup"><span data-stu-id="f945a-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="f945a-111">`rootRefIds`配列に null オブジェクトが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f945a-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="f945a-112">たとえば、スタックで宣言されたすべてのオブジェクト参照は、ガベージコレクターによってルートとして扱われ、常に報告されます。</span><span class="sxs-lookup"><span data-stu-id="f945a-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="f945a-113">によって返されるオブジェクト Id `RootReferences` は、コールバック自体では無効です。これは、ガベージコレクションが古いアドレスから新しいアドレスにオブジェクトを移動する途中にある可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="f945a-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="f945a-114">そのため、呼び出し中にプロファイラーがオブジェクトの検査を試行することはできません `RootReferences` 。</span><span class="sxs-lookup"><span data-stu-id="f945a-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="f945a-115">[ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)が呼び出されると、すべてのオブジェクトが新しい場所に移動され、安全に検査できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f945a-115">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f945a-116">要件</span><span class="sxs-lookup"><span data-stu-id="f945a-116">Requirements</span></span>  
 <span data-ttu-id="f945a-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f945a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f945a-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f945a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f945a-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f945a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f945a-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f945a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f945a-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f945a-121">See also</span></span>

- [<span data-ttu-id="f945a-122">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f945a-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
