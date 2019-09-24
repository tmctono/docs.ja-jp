---
title: 'ループ: while...do 式'
description: しばらくお待ちください...do 式は、指定されたテスト条件が true の間、反復実行 (ループ) を実行するために使用されます。
ms.date: 05/16/2016
ms.openlocfilehash: 73526279358db101f8d07721a200920f1e87f119
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216636"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="a6d14-103">ループ: while...do 式</span><span class="sxs-lookup"><span data-stu-id="a6d14-103">Loops: while...do Expression</span></span>

<span data-ttu-id="a6d14-104">式`while...do`は、指定されたテスト条件が true の間、反復実行 (ループ) を実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6d14-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="a6d14-105">構文</span><span class="sxs-lookup"><span data-stu-id="a6d14-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="a6d14-106">コメント</span><span class="sxs-lookup"><span data-stu-id="a6d14-106">Remarks</span></span>

<span data-ttu-id="a6d14-107">*テスト式*が評価されます。その`true`場合、*本体式*が実行され、テスト式が再評価されます。</span><span class="sxs-lookup"><span data-stu-id="a6d14-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="a6d14-108">*本体式*には型`unit`が必要です。</span><span class="sxs-lookup"><span data-stu-id="a6d14-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="a6d14-109">テスト式が`false`の場合、イテレーションは終了します。</span><span class="sxs-lookup"><span data-stu-id="a6d14-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="a6d14-110">次の例は、 `while...do`式の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6d14-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="a6d14-111">前のコードの出力は、1から20までのランダムな数値のストリームです。最後のバイトは10です。</span><span class="sxs-lookup"><span data-stu-id="a6d14-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```console
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="a6d14-112">は、シーケンス`while...do`式やその他のコンピュテーション式で使用できます。その場合は、 `while...do`式のカスタマイズされたバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6d14-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="a6d14-113">詳細については、「[シーケンス](sequences.md)、[非同期ワークフロー](asynchronous-workflows.md)、および[コンピュテーション式](computation-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6d14-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6d14-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6d14-114">See also</span></span>

- [<span data-ttu-id="a6d14-115">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="a6d14-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a6d14-116">For`for...in`条件</span><span class="sxs-lookup"><span data-stu-id="a6d14-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="a6d14-117">For`for...to`条件</span><span class="sxs-lookup"><span data-stu-id="a6d14-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
