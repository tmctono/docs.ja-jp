---
title: 'ループ: for...to 式'
description: 参照してください方法 F# for….. ループ変数の値の範囲をループで反復処理する式に使用されます。
ms.date: 05/16/2016
ms.openlocfilehash: 910c04aa4ea6b2c637dcad147347c1c317b5e0c0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626628"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="85aba-103">ループ: for...to 式</span><span class="sxs-lookup"><span data-stu-id="85aba-103">Loops: for...to Expression</span></span>

<span data-ttu-id="85aba-104">式`for...to`は、ループ内でループ変数の値の範囲を反復処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="85aba-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="85aba-105">構文</span><span class="sxs-lookup"><span data-stu-id="85aba-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="85aba-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="85aba-106">Remarks</span></span>

<span data-ttu-id="85aba-107">識別子の型は、 *start*および*finish*式の型から推論されます。</span><span class="sxs-lookup"><span data-stu-id="85aba-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="85aba-108">これらの式の型は、32ビットの整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="85aba-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="85aba-109">技術的には式です`for...to`が、命令型プログラミング言語では従来のステートメントに似ています。</span><span class="sxs-lookup"><span data-stu-id="85aba-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="85aba-110">*本体式*の戻り値の型はで`unit`ある必要があります。</span><span class="sxs-lookup"><span data-stu-id="85aba-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="85aba-111">次の例では、 `for...to`式のさまざまな用途を示します。</span><span class="sxs-lookup"><span data-stu-id="85aba-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="85aba-112">このコードの出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85aba-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="85aba-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="85aba-113">See also</span></span>

- [<span data-ttu-id="85aba-114">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="85aba-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="85aba-115">For`for...in`条件</span><span class="sxs-lookup"><span data-stu-id="85aba-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="85aba-116">For`while...do`条件</span><span class="sxs-lookup"><span data-stu-id="85aba-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
