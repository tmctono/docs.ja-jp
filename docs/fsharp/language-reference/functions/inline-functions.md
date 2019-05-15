---
title: インライン関数
description: 呼び出し元のコードに直接統合される F# インライン関数を使用する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: d1c3fb3d2721024febc95b3c5e01e06cd547f81e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642062"
---
# <a name="inline-functions"></a><span data-ttu-id="2e6fe-103">インライン関数</span><span class="sxs-lookup"><span data-stu-id="2e6fe-103">Inline Functions</span></span>

<span data-ttu-id="2e6fe-104">*インライン関数*関数が呼び出し元のコードに直接統合されています。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="2e6fe-105">インライン関数を使用</span><span class="sxs-lookup"><span data-stu-id="2e6fe-105">Using Inline Functions</span></span>

<span data-ttu-id="2e6fe-106">静的な型のパラメーターを使用するときに型パラメーターでパラメーター化されるすべての関数はインラインである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="2e6fe-107">これは、コンパイラがこれらの型パラメーターを解決できることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="2e6fe-108">通常のジェネリック型パラメーターを使用すると、このような制限はありません。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="2e6fe-109">インライン関数がメンバー制約の使用を有効にする以外には、コードを最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="2e6fe-110">ただし、インライン関数の過剰使用には、コード コンパイラの最適化とライブラリ関数の実装の変更に小さいされにくい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="2e6fe-111">このため、他のすべての最適化手法をしようとした場合を除き、最適化のインライン関数の使用を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="2e6fe-112">関数またはメソッドのインラインを行うことができます、パフォーマンスが向上がありますは常に大文字と小文字になっていません。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="2e6fe-113">そのため、こと、特定の関数をインラインで行う実際には正の影響を確認するのにパフォーマンスの測定値を使用することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="2e6fe-114">`inline`修飾子は、最上位レベルで、モジュール レベルまたはクラスで、メソッド レベルでの関数に適用できます。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="2e6fe-115">次のコード例は、最上位レベル、インライン インスタンス メソッドをおよびインラインの静的メソッドで、インライン関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="2e6fe-116">インライン関数と型推論</span><span class="sxs-lookup"><span data-stu-id="2e6fe-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="2e6fe-117">有無`inline`に影響が推論を入力します。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="2e6fe-118">これは、非インライン関数のことはできませんが、インライン関数が静的に解決できる型のパラメーターがあるためです。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="2e6fe-119">次のコード例は、場合を示しています、`inline`を静的に解決される型パラメーターを持つ関数を使用しているので便利です、`float`変換演算子。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="2e6fe-120">なし、`inline`修飾子、型の推論はこの場合、特定の種類を実行する関数`int`します。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="2e6fe-121">ただし、`inline`修飾子は、関数が静的に解決される型パラメーターを持つと推論も。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="2e6fe-122">`inline`修飾子、型は、次の場所に推論されます。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="2e6fe-123">これは、関数への変換をサポートする任意の型を受け取ることを意味**float**します。</span><span class="sxs-lookup"><span data-stu-id="2e6fe-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e6fe-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e6fe-124">See also</span></span>

- [<span data-ttu-id="2e6fe-125">関数</span><span class="sxs-lookup"><span data-stu-id="2e6fe-125">Functions</span></span>](index.md)
- [<span data-ttu-id="2e6fe-126">制約</span><span class="sxs-lookup"><span data-stu-id="2e6fe-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="2e6fe-127">静的に解決される型パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e6fe-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
