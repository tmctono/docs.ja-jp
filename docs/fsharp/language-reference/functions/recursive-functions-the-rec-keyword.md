---
title: 再帰関数:Rec キーワード
description: 再帰関数の定義に 'let' キーワードを使用して、F# の 'rec' キーワードが使用される方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 86eaf1c8a5566d8b9cbc4dcb72f945e2497e5439
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645298"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="80913-103">再帰関数:Rec キーワード</span><span class="sxs-lookup"><span data-stu-id="80913-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="80913-104">`rec`と共にキーワードが使用される、`let`再帰関数を定義するキーワード。</span><span class="sxs-lookup"><span data-stu-id="80913-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="80913-105">構文</span><span class="sxs-lookup"><span data-stu-id="80913-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="80913-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="80913-106">Remarks</span></span>

<span data-ttu-id="80913-107">再帰関数は、自身を呼び出す関数は、F# 言語で明示的に識別されます。</span><span class="sxs-lookup"><span data-stu-id="80913-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="80913-108">これにより、関数のスコープで定義されている識別子を使用可能なにします。</span><span class="sxs-lookup"><span data-stu-id="80913-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="80913-109">次のコードは、再帰関数を計算する、 *n*<sup>th</sup>フィボナッチ数。</span><span class="sxs-lookup"><span data-stu-id="80913-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="80913-110">実際には、上記のようなコードは、事前に計算された値の再計算するため、メモリとプロセッサ時間の浪費になります。</span><span class="sxs-lookup"><span data-stu-id="80913-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="80913-111">メソッドは、暗黙的に型内で再帰追加する必要はありません、`rec`キーワード。</span><span class="sxs-lookup"><span data-stu-id="80913-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="80913-112">クラス内の let バインドは、暗黙的に再帰的ではできません。</span><span class="sxs-lookup"><span data-stu-id="80913-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="80913-113">相互再帰関数</span><span class="sxs-lookup"><span data-stu-id="80913-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="80913-114">関数は、場合によって*相互再帰*呼び出しが、1 つの関数呼び出しを呼び出して、最初の呼び出しの数に別間に、円を描くことを意味します。</span><span class="sxs-lookup"><span data-stu-id="80913-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="80913-115">1 つで、このような関数をまとめて定義する必要があります`let`を使用したバインド、`and`それらをリンクするキーワード。</span><span class="sxs-lookup"><span data-stu-id="80913-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="80913-116">次の例は、2 つを相互には再帰関数。</span><span class="sxs-lookup"><span data-stu-id="80913-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="80913-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="80913-117">See also</span></span>

- [<span data-ttu-id="80913-118">関数</span><span class="sxs-lookup"><span data-stu-id="80913-118">Functions</span></span>](index.md)
