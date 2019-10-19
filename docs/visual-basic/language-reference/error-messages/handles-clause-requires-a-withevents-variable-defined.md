---
title: Handles 句には、含んでいる型またはその基本型の 1 つで定義した WithEvents 変数が必要です。
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 191415408f607d0ff768e50c41fa9b3c4405a688
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582826"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="d344b-102">Handles 句には、含んでいる型またはその基本型の 1 つで定義した WithEvents 変数が必要です。</span><span class="sxs-lookup"><span data-stu-id="d344b-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="d344b-103">@No__t_1 句に `WithEvents` 変数が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="d344b-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="d344b-104">プロシージャ宣言の最後にある `Handles` キーワードは、`WithEvents` キーワードを使用して宣言されたオブジェクト変数によって発生するイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="d344b-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="d344b-105">**エラー ID:** BC30506</span><span class="sxs-lookup"><span data-stu-id="d344b-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d344b-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d344b-106">To correct this error</span></span>

<span data-ttu-id="d344b-107">必要な `WithEvents` 変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d344b-107">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="d344b-108">例</span><span class="sxs-lookup"><span data-stu-id="d344b-108">Example</span></span>

<span data-ttu-id="d344b-109">次の例では、Visual Basic は、 [WithEvents](../modifiers/withevents.md)キーワードが <xref:System.Timers.Timer?displayProperty=nameWithType> インスタンスの定義で使用されていないため、コンパイラエラー `BC30506` を生成します。</span><span class="sxs-lookup"><span data-stu-id="d344b-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

```vb
Imports System.Timers

Module Module1
    Private _timer1 As New Timer() With {.Interval = 1000, .Enabled = True}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub
End Module
```

<span data-ttu-id="d344b-110">次の例は、`_timer1` 変数が `WithEvents` キーワードで定義されているため、正常にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="d344b-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

```vb
Imports System.Timers

Module Module1
    Private WithEvents _timer1 As New Timer() With {.Interval = 1000}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub

End Module
```

## <a name="see-also"></a><span data-ttu-id="d344b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d344b-111">See also</span></span>

- [<span data-ttu-id="d344b-112">Handles</span><span class="sxs-lookup"><span data-stu-id="d344b-112">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
