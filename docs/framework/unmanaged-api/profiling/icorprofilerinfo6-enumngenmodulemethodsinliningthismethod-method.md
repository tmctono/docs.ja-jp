---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod メソッド
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130383"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="c78dc-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="c78dc-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="c78dc-103">特定の NGen モジュールで定義され、指定されたメソッドにインライン化されているすべてのメソッドに対する列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="c78dc-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="c78dc-104">構文</span><span class="sxs-lookup"><span data-stu-id="c78dc-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="c78dc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c78dc-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="c78dc-106">からNGen モジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="c78dc-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="c78dc-107">から`inlineeMethodId`を定義するモジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="c78dc-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="c78dc-108">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78dc-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="c78dc-109">からインラインメソッドの識別子。</span><span class="sxs-lookup"><span data-stu-id="c78dc-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="c78dc-110">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78dc-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="c78dc-111">入出力指定したメソッドをインライン展開するすべてのメソッドが `ppEnum` に含まれているかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="c78dc-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="c78dc-112">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78dc-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="c78dc-113">入出力列挙子のアドレスへのポインター</span><span class="sxs-lookup"><span data-stu-id="c78dc-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="c78dc-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="c78dc-114">Remarks</span></span>

<span data-ttu-id="c78dc-115">`inlineeModuleId` と `inlineeMethodId` は、インライン化される可能性のあるメソッドの完全な識別子を形成します。</span><span class="sxs-lookup"><span data-stu-id="c78dc-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="c78dc-116">たとえば、モジュール `A` がメソッド `Simple.Add`を定義するとします。</span><span class="sxs-lookup"><span data-stu-id="c78dc-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="c78dc-117">モジュール B は `Fancy.AddTwice`を定義します。</span><span class="sxs-lookup"><span data-stu-id="c78dc-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="c78dc-118">また、`SimpleAdd`への呼び出しをインライン `Fancy.AddTwice` ことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c78dc-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="c78dc-119">プロファイラーは、この列挙子を使用して、モジュール B で定義されているすべてのメソッド (インライン `Simple.Add`) を検索し、結果は `AddTwice`を列挙できます。</span><span class="sxs-lookup"><span data-stu-id="c78dc-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="c78dc-120">`inlineeModuleId` は、モジュール `A`の識別子であり、`inlineeMethodId` は `Simple.Add(int a, int b)`の識別子です。</span><span class="sxs-lookup"><span data-stu-id="c78dc-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="c78dc-121">関数がを返した後に `incompleteData` が true の場合、列挙子には、特定のメソッドのインライン展開を行うメソッドがすべて含まれているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c78dc-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="c78dc-122">これは、inliners モジュールの1つ以上の直接または間接的な依存関係がまだ読み込まれていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c78dc-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="c78dc-123">プロファイラーが正確なデータを必要とする場合、より多くのモジュールが読み込まれると、後でモジュールの負荷に応じて、後で再試行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c78dc-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="c78dc-124">`EnumNgenModuleMethodsInliningThisMethod` メソッドを使用すると、ReJIT のインライン展開に関する制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="c78dc-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="c78dc-125">ReJIT を使用すると、プロファイラーはメソッドの実装を変更し、その場で新しいコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c78dc-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="c78dc-126">たとえば、次のように `Simple.Add` を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c78dc-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="c78dc-127">ただし、`Fancy.AddTwice` は既に `Simple.Add`インライン化されているので、以前と同じ動作を続けます。</span><span class="sxs-lookup"><span data-stu-id="c78dc-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="c78dc-128">この制限を回避するには、呼び出し元は、インライン `Simple.Add` されているすべてのモジュール内のすべてのメソッドを検索し、これらの各メソッドで `ICorProfilerInfo5::RequestRejit` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c78dc-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="c78dc-129">メソッドを再コンパイルすると、以前の動作ではなく、`Simple.Add` の新しい動作が行われます。</span><span class="sxs-lookup"><span data-stu-id="c78dc-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="c78dc-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="c78dc-130">Requirements</span></span>

<span data-ttu-id="c78dc-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c78dc-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c78dc-132">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c78dc-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c78dc-133">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c78dc-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c78dc-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c78dc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c78dc-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="c78dc-135">See also</span></span>

- [<span data-ttu-id="c78dc-136">ICorProfilerInfo6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c78dc-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
