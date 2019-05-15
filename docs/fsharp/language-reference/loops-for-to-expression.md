---
title: 'ループ: for...to 式'
description: 参照してください方法 F# for….. ループ変数の値の範囲をループで反復処理する式に使用されます。
ms.date: 05/16/2016
ms.openlocfilehash: 5b7bb9bac659ddf1d457be1ce17e90a2593666de
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645249"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="8acec-103">ループ: for...to 式</span><span class="sxs-lookup"><span data-stu-id="8acec-103">Loops: for...to Expression</span></span>

<span data-ttu-id="8acec-104">`for...to`ループ変数の値の範囲をループで反復処理する式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8acec-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="8acec-105">構文</span><span class="sxs-lookup"><span data-stu-id="8acec-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="8acec-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="8acec-106">Remarks</span></span>

<span data-ttu-id="8acec-107">識別子の型の型から推論されます、*開始*と*完了*式。</span><span class="sxs-lookup"><span data-stu-id="8acec-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="8acec-108">これらの式の型は、32 ビット整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8acec-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="8acec-109">式では技術的には、`for...to`は命令型プログラミング言語では、従来のステートメントのようにします。</span><span class="sxs-lookup"><span data-stu-id="8acec-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="8acec-110">戻り値の型、*式の本体*あります`unit`します。</span><span class="sxs-lookup"><span data-stu-id="8acec-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="8acec-111">次の例では、さまざまな使用、`for...to`式。</span><span class="sxs-lookup"><span data-stu-id="8acec-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="8acec-112">このコードの出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8acec-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="8acec-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8acec-113">See also</span></span>

- [<span data-ttu-id="8acec-114">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="8acec-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="8acec-115">ループ:`for...in` 式</span><span class="sxs-lookup"><span data-stu-id="8acec-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="8acec-116">ループ:`while...do` 式</span><span class="sxs-lookup"><span data-stu-id="8acec-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
