---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 4b13659f7c9909e9795caee1eace8da8092c5b9a
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974032"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="68ac2-102">ICorProfilerInfo10:: EnumerateObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="68ac2-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>
  
 <span data-ttu-id="68ac2-103">ObjectID、callback、および clientData を指定すると、各オブジェクト参照 (存在する場合) が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="68ac2-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="68ac2-104">構文</span><span class="sxs-lookup"><span data-stu-id="68ac2-104">Syntax</span></span>  
  
```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```  
  
#### <a name="parameters"></a><span data-ttu-id="68ac2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68ac2-105">Parameters</span></span>  

 `objectId` \
 <span data-ttu-id="68ac2-106">から参照を列挙するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="68ac2-106">[in] The object to enumerate references on.</span></span>

 `callback` \
 <span data-ttu-id="68ac2-107">からオブジェクトの参照を使用して呼び出される関数。</span><span class="sxs-lookup"><span data-stu-id="68ac2-107">[in] The function that will be called with the references for the object.</span></span>

 `clientData` \
 <span data-ttu-id="68ac2-108">から`callback`関数に渡されるプロファイラー提供のデータ。</span><span class="sxs-lookup"><span data-stu-id="68ac2-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="68ac2-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="68ac2-109">Remarks</span></span>  
 <span data-ttu-id="68ac2-110">`EnumerateObjectReferences` メソッドは [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) に似ていますが、参照を格納するために配列を事前に割り当てるのではなく、プロファイラーの要求時に参照をステップインする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="68ac2-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>  

## <a name="requirements"></a><span data-ttu-id="68ac2-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="68ac2-111">Requirements</span></span>  
 <span data-ttu-id="68ac2-112">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68ac2-112">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="68ac2-113">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="68ac2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="68ac2-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="68ac2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68ac2-115">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68ac2-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="68ac2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="68ac2-116">See also</span></span>
- [<span data-ttu-id="68ac2-117">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="68ac2-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

