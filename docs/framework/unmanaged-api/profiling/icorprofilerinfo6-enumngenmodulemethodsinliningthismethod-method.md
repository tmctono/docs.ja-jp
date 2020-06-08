---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod メソッド
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 8ed3f305deceacb976aeff994db1588f9e1ce1fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495529"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="1fc0f-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="1fc0f-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="1fc0f-103">特定の NGen モジュールで定義され、指定されたメソッドにインライン化されているすべてのメソッドに対する列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="1fc0f-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fc0f-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="1fc0f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fc0f-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="1fc0f-106">からNGen モジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="1fc0f-107">からを定義するモジュールの識別子 `inlineeMethodId` 。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="1fc0f-108">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="1fc0f-109">からインラインメソッドの識別子。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="1fc0f-110">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="1fc0f-111">入出力`ppEnum`に、指定したメソッドをインライン展開するメソッドがすべて含まれているかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="1fc0f-112">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="1fc0f-113">入出力列挙子のアドレスへのポインター</span><span class="sxs-lookup"><span data-stu-id="1fc0f-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="1fc0f-114">解説</span><span class="sxs-lookup"><span data-stu-id="1fc0f-114">Remarks</span></span>

<span data-ttu-id="1fc0f-115">`inlineeModuleId`と `inlineeMethodId` は、インライン化される可能性のあるメソッドの完全な識別子を形成します。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="1fc0f-116">たとえば、module `A` がメソッドを定義するとし `Simple.Add` ます。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="1fc0f-117">モジュール B は次を定義し `Fancy.AddTwice` ます。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="1fc0f-118">は、への呼び出しをインラインで使用することも想定 `Fancy.AddTwice` `SimpleAdd` しています。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="1fc0f-119">プロファイラーは、この列挙子を使用して、モジュール B でインラインで定義されているすべてのメソッドを検索し、結果を列挙することができ `Simple.Add` `AddTwice` ます。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="1fc0f-120">`inlineeModuleId`はモジュールの識別子で、 `A` `inlineeMethodId` はの識別子です `Simple.Add(int a, int b)` 。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="1fc0f-121">`incompleteData`関数からが返された後にが true の場合、列挙子には、特定のメソッドをインライン展開するメソッドがすべて含まれているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="1fc0f-122">これは、inliners モジュールの1つ以上の直接または間接的な依存関係がまだ読み込まれていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="1fc0f-123">プロファイラーが正確なデータを必要とする場合、より多くのモジュールが読み込まれると、後でモジュールの負荷に応じて、後で再試行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="1fc0f-124">`EnumNgenModuleMethodsInliningThisMethod`メソッドを使用すると、ReJIT のインライン展開に関する制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="1fc0f-125">ReJIT を使用すると、プロファイラーはメソッドの実装を変更し、その場で新しいコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="1fc0f-126">たとえば、次のように変更でき `Simple.Add` ます。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="1fc0f-127">ただし、は既にインライン化されているため `Fancy.AddTwice` `Simple.Add` 、以前と同じ動作を続けます。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="1fc0f-128">この制限を回避するために、呼び出し元は、 `Simple.Add` `ICorProfilerInfo5::RequestRejit` これらの各メソッドでインラインで使用されるすべてのモジュール内のすべてのメソッドを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="1fc0f-129">メソッドを再コンパイルすると、以前の動作ではなく、の新しい動作が行われ `Simple.Add` ます。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="1fc0f-130">要件</span><span class="sxs-lookup"><span data-stu-id="1fc0f-130">Requirements</span></span>

<span data-ttu-id="1fc0f-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fc0f-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="1fc0f-132">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fc0f-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1fc0f-133">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fc0f-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1fc0f-134">**.NET Framework のバージョン:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fc0f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1fc0f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fc0f-135">See also</span></span>

- [<span data-ttu-id="1fc0f-136">ICorProfilerInfo6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fc0f-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
