---
title: 遅延式
description: レイジー式F#を使用して、アプリとライブラリのパフォーマンスを向上させる方法について説明します。
ms.date: 03/13/2019
ms.openlocfilehash: 97429e9a4c3838cbaa2ead197db4443e0820e8b3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630738"
---
# <a name="lazy-expressions"></a><span data-ttu-id="51627-103">遅延式</span><span class="sxs-lookup"><span data-stu-id="51627-103">Lazy Expressions</span></span>

<span data-ttu-id="51627-104">*レイジー式*は、すぐに評価されるのではなく、結果が必要になったときに評価される式です。</span><span class="sxs-lookup"><span data-stu-id="51627-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="51627-105">これは、コードのパフォーマンスを向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51627-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="51627-106">構文</span><span class="sxs-lookup"><span data-stu-id="51627-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="51627-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="51627-107">Remarks</span></span>

<span data-ttu-id="51627-108">前の構文では、 *expression*は結果が必要な場合にのみ評価されるコードであり、 *identifier*は結果を格納する値です。</span><span class="sxs-lookup"><span data-stu-id="51627-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="51627-109">値は型[`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489)であり、に`'T`使用される実際の型は、式の結果から決定されます。</span><span class="sxs-lookup"><span data-stu-id="51627-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="51627-110">レイジー式を使用すると、式の実行を、結果が必要な状況のみに制限することで、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="51627-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="51627-111">式を強制的に実行するには、メソッド`Force`を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="51627-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="51627-112">`Force`実行を1回だけ実行します。</span><span class="sxs-lookup"><span data-stu-id="51627-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="51627-113">後続のを`Force`呼び出すと、同じ結果が返されますが、コードは実行されません。</span><span class="sxs-lookup"><span data-stu-id="51627-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="51627-114">次のコードは、レイジー式の使用方法との`Force`使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="51627-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="51627-115">このコードで`result`は、の型は`Lazy<int>`で、メソッドは`Force`を返し`int`ます。</span><span class="sxs-lookup"><span data-stu-id="51627-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="51627-116">遅延評価は、 `Lazy`型ではなく、シーケンスにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="51627-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="51627-117">詳細については、「[シーケンス](sequences.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51627-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="51627-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="51627-118">See also</span></span>

- [<span data-ttu-id="51627-119">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="51627-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="51627-120">LazyExtensions モジュール</span><span class="sxs-lookup"><span data-stu-id="51627-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
