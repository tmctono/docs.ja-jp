---
title: ラムダ式:funキーワード
description: '\"fun\" キーワードを使用してラムダ式を定義する方法について説明します。これは匿名関数です。'
ms.date: 05/16/2016
ms.openlocfilehash: 9818724686dd83a7e352fb36819289fa19b002df
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630661"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="f4338-103">ラムダ式:funキーワード (F#)</span><span class="sxs-lookup"><span data-stu-id="f4338-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="f4338-104">`fun`キーワードは、ラムダ式、つまり匿名関数を定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4338-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4338-105">構文</span><span class="sxs-lookup"><span data-stu-id="f4338-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="f4338-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="f4338-106">Remarks</span></span>

<span data-ttu-id="f4338-107">*パラメーターリスト*は、通常、名前と、必要に応じてパラメーターの型で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f4338-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="f4338-108">一般的に、*パラメーター リスト*F# のパターンで構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f4338-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="f4338-109">使用可能なパターンの完全な一覧については、「[パターン一致](../pattern-matching.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4338-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="f4338-110">有効なパラメーターの一覧を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="f4338-110">Lists of valid parameters include the following examples.</span></span>

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

<span data-ttu-id="f4338-111">*式*は関数の本体であり、の最後の式で戻り値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f4338-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="f4338-112">有効なラムダ式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f4338-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="f4338-113">ラムダ式の使用</span><span class="sxs-lookup"><span data-stu-id="f4338-113">Using Lambda Expressions</span></span>

<span data-ttu-id="f4338-114">ラムダ式は、リストまたは他のコレクションに対して操作を実行し、関数を定義する余分な作業を避ける必要がある場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="f4338-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="f4338-115">多くF#のライブラリ関数は関数の値を引数として受け取り、そのような場合にラムダ式を使用すると特に便利です。</span><span class="sxs-lookup"><span data-stu-id="f4338-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="f4338-116">次のコードは、リストの要素にラムダ式を適用します。</span><span class="sxs-lookup"><span data-stu-id="f4338-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="f4338-117">この場合、匿名関数はリストのすべての要素に1を追加します。</span><span class="sxs-lookup"><span data-stu-id="f4338-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="f4338-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4338-118">See also</span></span>

- [<span data-ttu-id="f4338-119">関数</span><span class="sxs-lookup"><span data-stu-id="f4338-119">Functions</span></span>](index.md)
