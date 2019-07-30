---
title: 例外:try...finally 式
description: 学習方法、F# 'try… 最後に' 式では、コードのブロックが例外をスローする場合でも、クリーンアップ コードを実行することができます。
ms.date: 05/16/2016
ms.openlocfilehash: 03fbda1ef5d55560232f0217f603fc04c0af0eb4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630277"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="7de6a-103">例外:try...finally 式</span><span class="sxs-lookup"><span data-stu-id="7de6a-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="7de6a-104">`try...finally`式を使用すると、コードのブロックで例外がスローされた場合でもクリーンアップコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7de6a-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="7de6a-105">構文</span><span class="sxs-lookup"><span data-stu-id="7de6a-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="7de6a-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="7de6a-106">Remarks</span></span>

<span data-ttu-id="7de6a-107">式は、 *expression1*の実行中に例外が生成されたかどうかに関係なく、前の構文で expression2 のコードを実行するために使用できます。 `try...finally`</span><span class="sxs-lookup"><span data-stu-id="7de6a-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="7de6a-108">*Expression2*の型は、式全体の値には影響しません。例外が発生しないときに返される型は、 *expression1*の最後の値です。</span><span class="sxs-lookup"><span data-stu-id="7de6a-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="7de6a-109">例外が発生した場合、値は返されず、制御のフローは、コールスタックの上位にある次の一致する例外ハンドラーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="7de6a-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="7de6a-110">例外ハンドラーが見つからない場合、プログラムは終了します。</span><span class="sxs-lookup"><span data-stu-id="7de6a-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="7de6a-111">一致するハンドラー内のコードが実行されるか、プログラムが終了する前に`finally` 、分岐内のコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7de6a-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="7de6a-112">次のコードは、 `try...finally`式の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7de6a-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="7de6a-113">コンソールへの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7de6a-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="7de6a-114">出力からわかるように、外側の例外が処理される前にストリームが閉じられてい`test.txt`ます。また`test1`、ファイルには、例外が転送されたにもかかわらず、バッファーがフラッシュされ、ディスクに書き込まれたことを示すテキストが含まれています。外側の例外ハンドラーに制御します。</span><span class="sxs-lookup"><span data-stu-id="7de6a-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="7de6a-115">コンストラクトは、 `try...with` `try...finally`コンストラクトとは別のコンストラクトであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7de6a-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="7de6a-116">したがって、コードに`with`ブロック`finally`とブロックの両方が必要な場合は、次のコード例に示すように、2つの構造体を入れ子にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7de6a-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="7de6a-117">シーケンス式と非同期ワークフローを含むコンピュテーション式のコンテキストでは、.. **.最後**の式には、カスタム実装を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7de6a-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="7de6a-118">詳細については、「[コンピュテーション式](../computation-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7de6a-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7de6a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7de6a-119">See also</span></span>

- [<span data-ttu-id="7de6a-120">例外処理</span><span class="sxs-lookup"><span data-stu-id="7de6a-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="7de6a-121">例外: `try...with`式</span><span class="sxs-lookup"><span data-stu-id="7de6a-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
