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
ms.openlocfilehash: a276ecfe65ed9752f39ed68a36e8e17a24255508
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558317"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="39430-102">ICorProfilerInfo10:: EnumerateObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="39430-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="39430-103">ObjectID、callback、および clientData を指定すると、各オブジェクト参照 (存在する場合) が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="39430-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="39430-104">構文</span><span class="sxs-lookup"><span data-stu-id="39430-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="39430-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39430-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="39430-106">\[in) 参照を列挙するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="39430-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="39430-107">\[では、オブジェクトの参照を使用して呼び出される関数。</span><span class="sxs-lookup"><span data-stu-id="39430-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="39430-108">\[in) 関数に渡すプロファイラーが提供するデータ `callback` 。</span><span class="sxs-lookup"><span data-stu-id="39430-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="39430-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="39430-109">Remarks</span></span>

<span data-ttu-id="39430-110">`EnumerateObjectReferences`メソッドは[ObjectReferences](icorprofilercallback-objectreferences-method.md)に似ていますが、参照を格納するために配列を事前に割り当てるのではなく、プロファイラーの要求時に参照をステップインする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="39430-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="39430-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="39430-111">Requirements</span></span>

<span data-ttu-id="39430-112">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/windows.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39430-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="39430-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39430-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="39430-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39430-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="39430-115">**.Net のバージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39430-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="39430-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="39430-116">See also</span></span>

- [<span data-ttu-id="39430-117">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39430-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
