---
title: ラムダ式:Fun キーワード
description: 使用する方法について説明します、F#匿名関数は、ラムダ式を定義する '楽しい' キーワード。
ms.date: 05/16/2016
ms.openlocfilehash: 6ad15173bb8643bff330e3ca3823cba5d43ad445
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941025"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="899d0-103">ラムダ式:Fun キーワード (F#)</span><span class="sxs-lookup"><span data-stu-id="899d0-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="899d0-104">`fun`キーワードの使用をラムダ式、つまり、匿名関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="899d0-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="899d0-105">構文</span><span class="sxs-lookup"><span data-stu-id="899d0-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="899d0-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="899d0-106">Remarks</span></span>

<span data-ttu-id="899d0-107">*パラメーター リスト*通常の名前と、必要に応じて、パラメーターの型で構成されます。</span><span class="sxs-lookup"><span data-stu-id="899d0-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="899d0-108">一般的に、*パラメーター リスト*F# のパターンで構成することができます。</span><span class="sxs-lookup"><span data-stu-id="899d0-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="899d0-109">可能なパターンの完全な一覧を参照してください。[パターン マッチング](../pattern-matching.md)します。</span><span class="sxs-lookup"><span data-stu-id="899d0-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="899d0-110">有効なパラメーターのリストには、次の例が含まれます。</span><span class="sxs-lookup"><span data-stu-id="899d0-110">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="899d0-111">*式*うち、最後の式が戻り値を生成、関数の本文です。</span><span class="sxs-lookup"><span data-stu-id="899d0-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="899d0-112">有効なラムダ式の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="899d0-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="899d0-113">ラムダ式の使用</span><span class="sxs-lookup"><span data-stu-id="899d0-113">Using Lambda Expressions</span></span>

<span data-ttu-id="899d0-114">ラムダ式は、リストまたはその他のコレクションで操作を実行し、追加の関数を定義する作業を回避するために必要な場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="899d0-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="899d0-115">多くF#ライブラリ関数が引数として関数の値を受け取るし、ラムダ式を使用して、そのような場合に特に便利であることができます。</span><span class="sxs-lookup"><span data-stu-id="899d0-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="899d0-116">次のコードでは、リストの要素にラムダ式が適用されます。</span><span class="sxs-lookup"><span data-stu-id="899d0-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="899d0-117">この場合、匿名関数では、一覧のすべての要素に 1 を追加します。</span><span class="sxs-lookup"><span data-stu-id="899d0-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="899d0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="899d0-118">See also</span></span>

- [<span data-ttu-id="899d0-119">関数</span><span class="sxs-lookup"><span data-stu-id="899d0-119">Functions</span></span>](index.md)