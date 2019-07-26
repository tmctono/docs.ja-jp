---
title: Handles 句には、含んでいる型またはその基本型の 1 つで定義した WithEvents 変数が必要です。
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 04c94d3d32660d1a186a9bb377c49a53e1451be6
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512740"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="a65ed-102">Handles 句には、含んでいる型またはその基本型の 1 つで定義した WithEvents 変数が必要です。</span><span class="sxs-lookup"><span data-stu-id="a65ed-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>
<span data-ttu-id="a65ed-103">句に変数が`WithEvents`指定されていません。 `Handles`</span><span class="sxs-lookup"><span data-stu-id="a65ed-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="a65ed-104">プロシージャ宣言の最後にある`WithEvents` キーワードを使用すると、キーワードを使用して宣言されたオブジェクト変数によって生成されるイベントを処理できます。`Handles`</span><span class="sxs-lookup"><span data-stu-id="a65ed-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>
  
 <span data-ttu-id="a65ed-105">**エラー ID:** BC30506</span><span class="sxs-lookup"><span data-stu-id="a65ed-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a65ed-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="a65ed-106">To correct this error</span></span>
  
- <span data-ttu-id="a65ed-107">必要な`WithEvents`変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a65ed-107">Supply the necessary `WithEvents` variable.</span></span>
  
## <a name="example"></a><span data-ttu-id="a65ed-108">例</span><span class="sxs-lookup"><span data-stu-id="a65ed-108">Example</span></span>

<span data-ttu-id="a65ed-109">次の例では、Visual Basic、 `BC30506` [WithEvents](../modifiers/withevents.md)キーワードが<xref:System.Timers.Timer?displayProperty=nameWithType>インスタンスの定義で使用されていないため、コンパイラエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a65ed-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

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

<span data-ttu-id="a65ed-110">次の例は、 `_timer1` `WithEvents`キーワードを使用して変数が定義されているため、正常にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="a65ed-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a65ed-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a65ed-111">See also</span></span>

- [<span data-ttu-id="a65ed-112">Handles</span><span class="sxs-lookup"><span data-stu-id="a65ed-112">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
