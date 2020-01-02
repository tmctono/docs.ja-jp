---
title: ラムダ式内で繰り返し変数を使用すると、予期しない結果が発生する可能性があります。
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 3335da503b6fb9c33e44266997cc945214a3a365
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913088"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="86a34-102">ラムダ式内で繰り返し変数を使用すると、予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86a34-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="86a34-103">ラムダ式で繰り返し変数を使用する必要があります予期しない結果。</span><span class="sxs-lookup"><span data-stu-id="86a34-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="86a34-104">代わりに、ループ内でローカル変数を作成し、反復変数の値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="86a34-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="86a34-105">ループ内で宣言されているラムダ式でループの反復変数を使用すると、この警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="86a34-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="86a34-106">たとえば、次の例に表示される警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="86a34-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="86a34-107">次の例では、発生する可能性が予期しない結果を示します。</span><span class="sxs-lookup"><span data-stu-id="86a34-107">The following example shows the unexpected results that might occur.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="86a34-108">`For`ループがループの反復変数の値を返します、ラムダ式の配列を作成します`i`します。</span><span class="sxs-lookup"><span data-stu-id="86a34-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="86a34-109">ラムダ式を評価するときに、`For Each`ループされる予定である 0、1、2、3、および 4 の連続する値を表示するを参照してください`i`で、`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="86a34-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="86a34-110">最終的な値を表示する代わりに、 `i` 5 回表示されます。</span><span class="sxs-lookup"><span data-stu-id="86a34-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="86a34-111">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="86a34-111">By default, this message is a warning.</span></span> <span data-ttu-id="86a34-112">警告を表示しない方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86a34-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="86a34-113">**エラー ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="86a34-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86a34-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="86a34-114">To correct this error</span></span>  
  
- <span data-ttu-id="86a34-115">反復変数の値をローカル変数に割り当てるし、ローカル変数をラムダ式で使用します。</span><span class="sxs-lookup"><span data-stu-id="86a34-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="86a34-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="86a34-116">See also</span></span>

- [<span data-ttu-id="86a34-117">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="86a34-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
