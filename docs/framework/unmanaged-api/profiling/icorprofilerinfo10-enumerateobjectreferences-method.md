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
ms.openlocfilehash: 7fd62e0d3d9173f3b75882131e57126075c0677f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863310"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="1fa90-102">ICorProfilerInfo10:: EnumerateObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="1fa90-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="1fa90-103">ObjectID、callback、および clientData を指定すると、各オブジェクト参照 (存在する場合) が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="1fa90-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="1fa90-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fa90-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="1fa90-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fa90-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="1fa90-106">で \[] 参照を列挙するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1fa90-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="1fa90-107">\[] オブジェクトの参照を使用して呼び出される関数。</span><span class="sxs-lookup"><span data-stu-id="1fa90-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="1fa90-108">\[] `callback` 関数に渡すプロファイラーが提供するデータ。</span><span class="sxs-lookup"><span data-stu-id="1fa90-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fa90-109">コメント</span><span class="sxs-lookup"><span data-stu-id="1fa90-109">Remarks</span></span>

<span data-ttu-id="1fa90-110">`EnumerateObjectReferences` メソッドは [ObjectReferences](icorprofilercallback-objectreferences-method.md) に似ていますが、参照を格納するために配列を事前に割り当てるのではなく、プロファイラーの要求時に参照をステップインする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="1fa90-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="1fa90-111">要件</span><span class="sxs-lookup"><span data-stu-id="1fa90-111">Requirements</span></span>

<span data-ttu-id="1fa90-112">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fa90-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="1fa90-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fa90-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1fa90-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fa90-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1fa90-115">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fa90-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1fa90-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fa90-116">See also</span></span>

- [<span data-ttu-id="1fa90-117">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fa90-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
