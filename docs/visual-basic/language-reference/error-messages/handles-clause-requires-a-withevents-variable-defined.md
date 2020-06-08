---
title: Handles 句には、含んでいる型またはその基本型の 1 つで定義した WithEvents 変数が必要です。
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 94c4229d4036382e344cffb09295e218642c55d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402902"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="b3217-102">Handles 句には、含んでいる型またはその基本型の 1 つで定義した WithEvents 変数が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3217-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="b3217-103">`Handles` 句に `WithEvents` 変数を指定していません。</span><span class="sxs-lookup"><span data-stu-id="b3217-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="b3217-104">プロシージャ宣言の最後にある `Handles` キーワードによって、`WithEvents` キーワードを使用して宣言されたオブジェクト変数によって発生したイベントが処理されるようになります。</span><span class="sxs-lookup"><span data-stu-id="b3217-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="b3217-105">**エラー ID:** BC30506</span><span class="sxs-lookup"><span data-stu-id="b3217-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b3217-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b3217-106">To correct this error</span></span>

<span data-ttu-id="b3217-107">必要な `WithEvents` 変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3217-107">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="b3217-108">例</span><span class="sxs-lookup"><span data-stu-id="b3217-108">Example</span></span>

<span data-ttu-id="b3217-109">次の例では、Visual Basic によってコンパイラ エラー `BC30506` が生成されます。これは、<xref:System.Timers.Timer?displayProperty=nameWithType> インスタンスの定義で [WithEvents](../modifiers/withevents.md) キーワードが使用されていないためです。</span><span class="sxs-lookup"><span data-stu-id="b3217-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

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

<span data-ttu-id="b3217-110">次の例では、`_timer1` 変数が `WithEvents` キーワードで定義されているため、正常にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="b3217-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b3217-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3217-111">See also</span></span>

- [<span data-ttu-id="b3217-112">Handles</span><span class="sxs-lookup"><span data-stu-id="b3217-112">Handles</span></span>](../statements/handles-clause.md)
