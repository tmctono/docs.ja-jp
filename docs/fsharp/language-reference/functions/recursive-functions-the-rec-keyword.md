---
title: 再帰関数:Rec キーワード
description: 再帰関数の定義に 'let' キーワードを使用して、F# の 'rec' キーワードが使用される方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630656"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="d8cca-103">再帰関数:Rec キーワード</span><span class="sxs-lookup"><span data-stu-id="d8cca-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="d8cca-104">キーワードは、再帰関数を定義`let`するためにキーワードと共に使用されます。 `rec`</span><span class="sxs-lookup"><span data-stu-id="d8cca-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8cca-105">構文</span><span class="sxs-lookup"><span data-stu-id="d8cca-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="d8cca-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8cca-106">Remarks</span></span>

<span data-ttu-id="d8cca-107">再帰関数は、自身を呼び出す関数は、F# 言語で明示的に識別されます。</span><span class="sxs-lookup"><span data-stu-id="d8cca-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="d8cca-108">これにより、定義されている識別子が関数のスコープで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d8cca-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="d8cca-109">次のコードは、 *n*<sup>番目</sup>のフィボナッチ数列を計算する再帰関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8cca-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="d8cca-110">実際には、上記のコードのようなコードでは、以前に計算された値の再計算が関係するため、メモリとプロセッサ時間が無駄になります。</span><span class="sxs-lookup"><span data-stu-id="d8cca-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="d8cca-111">メソッドは、型の中で暗黙的に再帰的になります。`rec`キーワードを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8cca-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="d8cca-112">クラス内のバインディングは暗黙的に再帰的ではありません。</span><span class="sxs-lookup"><span data-stu-id="d8cca-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="d8cca-113">相互再帰関数</span><span class="sxs-lookup"><span data-stu-id="d8cca-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="d8cca-114">場合によっては、関数が*相互に再帰的*であることを意味します。これは、呼び出しが円を形成することを意味します。この場合、1つ目の関数はを呼び出し、その間に任意の数の呼び出しを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d8cca-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="d8cca-115">このような関数は、1つ`let`のバインディングで定義し、 `and`キーワードを使用してそれらをリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8cca-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="d8cca-116">次の例は、2つの相互再帰関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="d8cca-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="d8cca-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8cca-117">See also</span></span>

- [<span data-ttu-id="d8cca-118">関数</span><span class="sxs-lookup"><span data-stu-id="d8cca-118">Functions</span></span>](index.md)
