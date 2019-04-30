---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod メソッド
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67ae413ae8944757fc90bcde752b9a5fe53cc68f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948526"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="e0718-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="e0718-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="e0718-103">特定の NGen モジュールと特定のメソッドをインラインで定義されているすべてのメソッドには、列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="e0718-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0718-104">構文</span><span class="sxs-lookup"><span data-stu-id="e0718-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="e0718-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0718-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="e0718-106">[in]NGen モジュールの識別子です。</span><span class="sxs-lookup"><span data-stu-id="e0718-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="e0718-107">[in]定義するモジュールの識別子`inlineeMethodId`します。</span><span class="sxs-lookup"><span data-stu-id="e0718-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="e0718-108">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0718-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="e0718-109">[in]インライン メソッドの識別子です。</span><span class="sxs-lookup"><span data-stu-id="e0718-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="e0718-110">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0718-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="e0718-111">[out]フラグを示すかどうか`ppEnum`特定のメソッドにはインライン展開のすべてのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0718-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="e0718-112">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0718-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="e0718-113">[out]列挙子のアドレスへのポインター</span><span class="sxs-lookup"><span data-stu-id="e0718-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="e0718-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="e0718-114">Remarks</span></span>

<span data-ttu-id="e0718-115">`inlineeModuleId` `inlineeMethodId`インライン化されるメソッドの完全な識別子を形成します。</span><span class="sxs-lookup"><span data-stu-id="e0718-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="e0718-116">たとえば、モジュール`A`メソッドを定義します`Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="e0718-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="e0718-117">B のモジュールを定義および`Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="e0718-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="e0718-118">あることができます。`Fancy.AddTwice`インライン呼び出しに`SimpleAdd`します。</span><span class="sxs-lookup"><span data-stu-id="e0718-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="e0718-119">プロファイラーは、この列挙子を使用してモジュール B がインラインで定義されたすべてのメソッドを検索する可能性があります`Simple.Add`は、結果の列挙と`AddTwice`します。</span><span class="sxs-lookup"><span data-stu-id="e0718-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="e0718-120">`inlineeModuleId` モジュールの識別子は、 `A`、および`inlineeMethodId`の識別子は、`Simple.Add(int a, int b)`します。</span><span class="sxs-lookup"><span data-stu-id="e0718-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="e0718-121">場合`incompleteData`関数の後に、列挙子は、すべてのメソッドがインライン展開の特定のメソッドを含んでいませんを返します。</span><span class="sxs-lookup"><span data-stu-id="e0718-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="e0718-122">これは、1 つの場合に発生することができますかより直接的または間接的な依存関係のインライン モジュールがまだ読み込まれていません。</span><span class="sxs-lookup"><span data-stu-id="e0718-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="e0718-123">プロファイラーは、データの正確性を必要とする場合は、複数のモジュールが読み込まれるときに、可能であれば 各モジュールの読み込み後に再試行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0718-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="e0718-124">`EnumNgenModuleMethodsInliningThisMethod`メソッドを使用して、上の制限を回避する ReJIT のインライン化します。</span><span class="sxs-lookup"><span data-stu-id="e0718-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="e0718-125">ReJIT では、プロファイラーは、メソッドの実装を変更して、実行時にその新しいコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e0718-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="e0718-126">たとえば、変更`Simple.Add`次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e0718-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="e0718-127">ただしため`Fancy.AddTwice`が既にインライン`Simple.Add`、以前と同じ動作を続行します。</span><span class="sxs-lookup"><span data-stu-id="e0718-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="e0718-128">呼び出し元がすべてのモジュールでインラインのすべてのメソッドを検索するがその制限を回避する`Simple.Add`を使用して、`ICorProfilerInfo5::RequestRejit`これらのメソッドの各します。</span><span class="sxs-lookup"><span data-stu-id="e0718-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="e0718-129">新しい動作が、メソッドは、再コンパイル、`Simple.Add`古い動作の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="e0718-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="e0718-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="e0718-130">Requirements</span></span>

<span data-ttu-id="e0718-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0718-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="e0718-132">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0718-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="e0718-133">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0718-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e0718-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0718-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e0718-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0718-135">See also</span></span>

- [<span data-ttu-id="e0718-136">ICorProfilerInfo6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0718-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)