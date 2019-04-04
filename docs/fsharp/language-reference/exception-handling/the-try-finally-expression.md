---
title: 例外:try...finally 式
description: 学習方法、F# 'try… 最後に' 式では、コードのブロックが例外をスローする場合でも、クリーンアップ コードを実行することができます。
ms.date: 05/16/2016
ms.openlocfilehash: 24613185818c8ea30b27dcf639b22af320c4b401
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611621"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="6a3c2-103">例外:try...finally 式</span><span class="sxs-lookup"><span data-stu-id="6a3c2-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="6a3c2-104">`try...finally`式では、コードのブロックが例外をスローする場合でも、クリーンアップ コードを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a3c2-105">構文</span><span class="sxs-lookup"><span data-stu-id="6a3c2-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="6a3c2-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a3c2-106">Remarks</span></span>

<span data-ttu-id="6a3c2-107">`try...finally`でコードを実行する式を使用できます*expression2*の実行中に例外を生成するかどうかに関係なく、上記の構文で*expression1*します。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="6a3c2-108">型*expression2* ; 式全体の値には含まれません、例外が発生していないときに返される型の最後の値は、 *expression1*します。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="6a3c2-109">例外が発生した場合、値は返されません、コントロールのフローは、コール スタックの上の次の一致する例外ハンドラーに転送します。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="6a3c2-110">例外ハンドラーが見つからない場合、プログラムを終了します。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="6a3c2-111">一致するハンドラーのコードが実行されるかプログラムが終了すると、コードでは、前に、`finally`分岐が実行されます。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="6a3c2-112">次のコードの使用を示します、`try...finally`式。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="6a3c2-113">コンソールに出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="6a3c2-114">外側の例外が処理された、前にストリームが閉じた出力からわかるとファイル`test.txt`テキストを含む`test1`バッファーがフラッシュされ、場合でも、例外の転送をディスクに書き込まれたことを示します外側の例外ハンドラーに制御します。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="6a3c2-115">なお、`try...with`コンストラクトが別のコンストラクトから、`try...finally`構築します。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="6a3c2-116">そのため、コードでは、両方が必要な場合、`with`ブロックと`finally`ブロック、次のコード例のように、2 つの構造を入れ子にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="6a3c2-117">コンピュテーション式のコンテキストで、シーケンス式と非同期のワークフローを含む**try… finally**式は、カスタム実装を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="6a3c2-118">詳細については、[コンピュテーション式](../computation-expressions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a3c2-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6a3c2-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a3c2-119">See also</span></span>

- [<span data-ttu-id="6a3c2-120">例外処理</span><span class="sxs-lookup"><span data-stu-id="6a3c2-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="6a3c2-121">例外処理:`try...with`式</span><span class="sxs-lookup"><span data-stu-id="6a3c2-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)