---
title: 遅延式
description: 学習方法F#遅延式は、アプリとライブラリのパフォーマンスを向上させることができます。
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57853326"
---
# <a name="lazy-expressions"></a><span data-ttu-id="f58bc-103">遅延式</span><span class="sxs-lookup"><span data-stu-id="f58bc-103">Lazy Expressions</span></span>

<span data-ttu-id="f58bc-104">*遅延式*は、すぐには評価されませんが、結果が必要な場合は代わりに評価される式です。</span><span class="sxs-lookup"><span data-stu-id="f58bc-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="f58bc-105">これは、コードのパフォーマンスを向上させるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f58bc-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="f58bc-106">構文</span><span class="sxs-lookup"><span data-stu-id="f58bc-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="f58bc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f58bc-107">Remarks</span></span>

<span data-ttu-id="f58bc-108">前の構文で*式*結果が、必要な場合にのみ評価されるコードと*識別子*は結果を格納する値です。</span><span class="sxs-lookup"><span data-stu-id="f58bc-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="f58bc-109">型の値は、 [ `Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)場所、実際の種類のために使用`'T`式の結果から決定されます。</span><span class="sxs-lookup"><span data-stu-id="f58bc-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="f58bc-110">遅延式を使用すると、結果が必要な場合のみ、式の実行を制限することでパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="f58bc-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="f58bc-111">メソッドを呼び出すを強制的に実行する式、`Force`します。</span><span class="sxs-lookup"><span data-stu-id="f58bc-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="f58bc-112">`Force` 1 回だけ実行する実行をします。</span><span class="sxs-lookup"><span data-stu-id="f58bc-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="f58bc-113">後続の呼び出し`Force`同じが、任意のコードを実行せずに返します。</span><span class="sxs-lookup"><span data-stu-id="f58bc-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="f58bc-114">次のコードは限定的な表現の使用と、使用して`Force`します。</span><span class="sxs-lookup"><span data-stu-id="f58bc-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="f58bc-115">このコードの種類で`result`は`Lazy<int>`、および`Force`メソッドを返します。、`int`します。</span><span class="sxs-lookup"><span data-stu-id="f58bc-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="f58bc-116">遅延評価は、ではなく、`Lazy`入力、シーケンスにも使用します。</span><span class="sxs-lookup"><span data-stu-id="f58bc-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="f58bc-117">詳細については、[シーケンス](sequences.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f58bc-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f58bc-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f58bc-118">See also</span></span>

- [<span data-ttu-id="f58bc-119">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="f58bc-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f58bc-120">LazyExtensions モジュール</span><span class="sxs-lookup"><span data-stu-id="f58bc-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
