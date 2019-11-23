---
title: ICorProfilerCallback5::ConditionalWeakTableElementReferences メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ConditionalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
ms.openlocfilehash: ad721d28f6a7dc6ae0370ce10178990cb02fb9f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430051"
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a><span data-ttu-id="1fc6f-102">ICorProfilerCallback5::ConditionalWeakTableElementReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc6f-102">ICorProfilerCallback5::ConditionalWeakTableElementReferences Method</span></span>

<span data-ttu-id="1fc6f-103">直接のメンバー フィールド参照および `ConditionalWeakTable` 依存を介してこれらのルーツによって参照されるオブジェクトの推移的終了を識別します。</span><span class="sxs-lookup"><span data-stu-id="1fc6f-103">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>

## <a name="syntax"></a><span data-ttu-id="1fc6f-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fc6f-104">Syntax</span></span>

```cpp
HRESULT ConditionalWeakTableElementReferences(
     [in]                     ULONG    cRootRefs,
     [in, size_is(cRootRefs)] ObjectID keyRefIds[],
     [in, size_is(cRootRefs)] ObjectID valueRefIds[],
     [in, size_is(cRootRefs)] GCHandleID rootIds[]
);
```

## <a name="parameters"></a><span data-ttu-id="1fc6f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fc6f-105">Parameters</span></span>

`cRootRefs`\
<span data-ttu-id="1fc6f-106">[入力] `keyRefIds`、`valueRefIds` および `rootIds` 配列にある要素数。</span><span class="sxs-lookup"><span data-stu-id="1fc6f-106">[in] The number of elements in the `keyRefIds`, `valueRefIds`, and `rootIds` arrays.</span></span>

`keyRefIds`\
<span data-ttu-id="1fc6f-107">[入力] それぞれが依存ハンドル ペアのプライマリ要素の `ObjectID` を含む、オブジェクト ID の配列。</span><span class="sxs-lookup"><span data-stu-id="1fc6f-107">[in] An array of object IDs, each of which contains the `ObjectID` for the primary element in the dependent handle pair.</span></span>

`valueRefIds`\
<span data-ttu-id="1fc6f-108">[入力] それぞれが依存ハンドル ペアのセカンダリ要素の `ObjectID` を含む、オブジェクト ID の配列。</span><span class="sxs-lookup"><span data-stu-id="1fc6f-108">[in] An array of object IDs, each of which contains the `ObjectID` for the secondary element in the dependent handle pair.</span></span> <span data-ttu-id="1fc6f-109">(`keyRefIds[i]` keeps `valueRefIds[i]` alive.)</span><span class="sxs-lookup"><span data-stu-id="1fc6f-109">(`keyRefIds[i]` keeps `valueRefIds[i]` alive.)</span></span>

`rootIds`\
<span data-ttu-id="1fc6f-110">[入力] ガーベッジ コレクション ルートについての追加情報を含む整数を指し示す `GCHandleID` 値の配列</span><span class="sxs-lookup"><span data-stu-id="1fc6f-110">[in] An array of `GCHandleID` values that point to an integer that contains additional information about the garbage collection root.</span></span>

<span data-ttu-id="1fc6f-111">ガーベッジ コレクターがオブジェクトを古い場所から新しい場所へ移動中の可能性があるため、コールバックの間は `ObjectID` メソッドによって返される `ConditionalWeakTableElementReferences` 値の値は無効です。</span><span class="sxs-lookup"><span data-stu-id="1fc6f-111">None of the `ObjectID` values returned by the `ConditionalWeakTableElementReferences` method are valid during the callback itself, because the garbage collector may be in the process of moving objects from old to new locations.</span></span> <span data-ttu-id="1fc6f-112">このため、`ConditionalWeakTableElementReferences` 呼び出しの間、プロファイラーはオブジェクトを検査するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="1fc6f-112">Therefore, profilers should not attempt to inspect objects during a `ConditionalWeakTableElementReferences` call.</span></span> <span data-ttu-id="1fc6f-113">`GarbageCollectionFinished` では、全てのオブジェトが新しい場所へ移動しているので、検査を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1fc6f-113">At `GarbageCollectionFinished`, all objects have been moved to their new locations, and inspection may be done.</span></span>

## <a name="example"></a><span data-ttu-id="1fc6f-114">例</span><span class="sxs-lookup"><span data-stu-id="1fc6f-114">Example</span></span>

<span data-ttu-id="1fc6f-115">The following code example demonstrates how to implement [ICorProfilerCallback5](icorprofilercallback5-interface.md) and use this method.</span><span class="sxs-lookup"><span data-stu-id="1fc6f-115">The following code example demonstrates how to implement [ICorProfilerCallback5](icorprofilercallback5-interface.md) and use this method.</span></span>

```cpp
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(
    ULONG      cRootRefs,
    ObjectID   keyRefIds[],
    ObjectID   valueRefIds[],
    GCHandleID rootIds[])
{
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");
    for (unsigned int i = 0; i < cRootRefs; ++i)
    {
        // Save dependency to XML for later retrieval
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or store dependency to an internal map
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or add arc to object graph
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);
    }
    return S_OK;
}
```

## <a name="remarks"></a><span data-ttu-id="1fc6f-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="1fc6f-116">Remarks</span></span>

<span data-ttu-id="1fc6f-117">A profiler for the .NET Framework 4.5 or later versions implements the [ICorProfilerCallback5](icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method.</span><span class="sxs-lookup"><span data-stu-id="1fc6f-117">A profiler for the .NET Framework 4.5 or later versions implements the [ICorProfilerCallback5](icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method.</span></span> <span data-ttu-id="1fc6f-118">`ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries.</span><span class="sxs-lookup"><span data-stu-id="1fc6f-118">`ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries.</span></span> <span data-ttu-id="1fc6f-119">These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.</span><span class="sxs-lookup"><span data-stu-id="1fc6f-119">These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.</span></span>

## <a name="requirements"></a><span data-ttu-id="1fc6f-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="1fc6f-120">Requirements</span></span>

<span data-ttu-id="1fc6f-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fc6f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="1fc6f-122">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fc6f-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1fc6f-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fc6f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1fc6f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fc6f-124">See also</span></span>

- [<span data-ttu-id="1fc6f-125">ICorProfilerCallback5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fc6f-125">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)
