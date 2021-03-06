---
title: ラムダ式内で繰り返し変数を使用すると、予期しない結果が発生する可能性があります。
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: e7975dc767ae652359c904271d6610be34e4cb80
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870240"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>ラムダ式内で繰り返し変数を使用すると、予期しない結果が発生する可能性があります。

ラムダ式内で反復変数を使用すると、予期しない結果が発生する可能性があります。 代わりに、ループ内にローカル変数を作成して反復変数の値を割り当ててください。  
  
 この警告は、ループ内で宣言されているラムダ式でループの反復変数を使用すると表示されます。 たとえば、次のコード例では、警告が表示されます。  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 次の例は、予期しない結果が発生する可能性があることを示しています。  
  
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
  
 `For` ループは、それぞれがループの反復変数 `i` の値を返す、ラムダ式の配列を作成します。 ラムダ式が `For Each` ループで評価されると、0、1、2、3、および 4 (`For` ループ内の `i` の連続する値) が表示されると予想される場合があります。 そうではなく、`i` の最終的な値が 5 回表示されます。  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 既定では、このメッセージは警告です。 警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。  
  
 **エラー ID:** BC42324  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 反復変数の値をローカル変数に代入し、そのローカル変数をラムダ式で使用します。  
  
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
  
## <a name="see-also"></a>関連項目

- [ラムダ式](../../programming-guide/language-features/procedures/lambda-expressions.md)
