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
ms.openlocfilehash: 9aadf9701444d215291b6fc19cc8cd61ca832837
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452241"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="62611-102">ICorProfilerInfo10:: EnumerateObjectReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="62611-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="62611-103">ObjectID、callback、および clientData を指定すると、各オブジェクト参照 (存在する場合) が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="62611-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="62611-104">構文</span><span class="sxs-lookup"><span data-stu-id="62611-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="62611-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62611-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="62611-106">で \[] 参照を列挙するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="62611-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="62611-107">\[] オブジェクトの参照を使用して呼び出される関数。</span><span class="sxs-lookup"><span data-stu-id="62611-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="62611-108">\[] `callback` 関数に渡すプロファイラーが提供するデータ。</span><span class="sxs-lookup"><span data-stu-id="62611-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="62611-109">コメント</span><span class="sxs-lookup"><span data-stu-id="62611-109">Remarks</span></span>

<span data-ttu-id="62611-110">`EnumerateObjectReferences` メソッドは[ObjectReferences](icorprofilercallback-objectreferences-method.md)に似ていますが、参照を格納するために配列を事前に割り当てるのではなく、プロファイラーの要求時に参照をステップインする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="62611-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="62611-111">要件</span><span class="sxs-lookup"><span data-stu-id="62611-111">Requirements</span></span>

<span data-ttu-id="62611-112">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62611-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="62611-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62611-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="62611-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62611-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="62611-115">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62611-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="62611-116">参照</span><span class="sxs-lookup"><span data-stu-id="62611-116">See also</span></span>

- [<span data-ttu-id="62611-117">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62611-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
