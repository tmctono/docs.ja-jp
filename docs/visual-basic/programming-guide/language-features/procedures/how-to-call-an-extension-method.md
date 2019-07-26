---
title: '方法: 拡張メソッド (Visual Basic) を呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: f2058162ab939d2619d7255c884d88c35ee63715
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512671"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="0fe93-102">方法: 拡張メソッド (Visual Basic) を呼び出す</span><span class="sxs-lookup"><span data-stu-id="0fe93-102">How to: Call an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="0fe93-103">拡張メソッドを使用すると、既存のクラスにメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0fe93-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="0fe93-104">拡張メソッドが宣言され、スコープ内に入ると、拡張された型のインスタンスメソッドのように呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0fe93-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="0fe93-105">拡張メソッドを記述する方法の詳細については[、「方法:拡張メソッド](./how-to-write-an-extension-method.md)を記述します。</span><span class="sxs-lookup"><span data-stu-id="0fe93-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>

 <span data-ttu-id="0fe93-106">次の手順では、拡張`PrintAndPunctuate`メソッドについて説明します`punc`。拡張メソッドは、それを呼び出す文字列インスタンスを表示し、その後、2番目のパラメーターのに送信される任意の値を示します。</span><span class="sxs-lookup"><span data-stu-id="0fe93-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

<span data-ttu-id="0fe93-107">メソッドが呼び出されるときは、そのメソッドがスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fe93-107">The method must be in scope when it is called.</span></span>

### <a name="to-call-an-extension-method"></a><span data-ttu-id="0fe93-108">拡張メソッドを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="0fe93-108">To call an extension method</span></span>

1. <span data-ttu-id="0fe93-109">拡張メソッドの最初のパラメーターのデータ型を持つ変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="0fe93-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="0fe93-110">では、 <xref:System.String>変数が必要です。 `PrintAndPunctuate`</span><span class="sxs-lookup"><span data-stu-id="0fe93-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>

    ```vb
    Dim example = "Ready"
    ```

2. <span data-ttu-id="0fe93-111">その変数は拡張メソッドを呼び出し、その値は最初のパラメーターで`aString`あるにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="0fe93-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="0fe93-112">次の呼び出しステートメントが表示`Ready?`されます。</span><span class="sxs-lookup"><span data-stu-id="0fe93-112">The following calling statement will display `Ready?`.</span></span>

    ```vb
    example.PrintAndPunctuate("?")
    ```

     <span data-ttu-id="0fe93-113">この拡張メソッドへの呼び出しは、1つのパラメーターを必要とするいずれか<xref:System.String>のインスタンスメソッドの呼び出しと同じように見えます。</span><span class="sxs-lookup"><span data-stu-id="0fe93-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. <span data-ttu-id="0fe93-114">別の文字列変数を宣言し、メソッドを再度呼び出して、任意の文字列で動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0fe93-114">Declare another string variable and call the method again to see that it works with any string.</span></span>

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     <span data-ttu-id="0fe93-115">この時間は次のよう`or not!!!`になります。</span><span class="sxs-lookup"><span data-stu-id="0fe93-115">The result this time is: `or not!!!`.</span></span>

## <a name="example"></a><span data-ttu-id="0fe93-116">例</span><span class="sxs-lookup"><span data-stu-id="0fe93-116">Example</span></span>
 <span data-ttu-id="0fe93-117">次のコードは、単純な拡張メソッドの作成と使用の完全な例です。</span><span class="sxs-lookup"><span data-stu-id="0fe93-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>

```vb
Imports System.Runtime.CompilerServices
Imports ConsoleApplication1.StringExtensions

Module Module1

    Sub Main()

        Dim example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")

        Dim example2 = "Goodbye"
        example2.PrintAndPunctuate("?")
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module

' Output:
' Hello.
' Hello!!!!
' Goodbye?
```

## <a name="see-also"></a><span data-ttu-id="0fe93-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fe93-118">See also</span></span>

- [<span data-ttu-id="0fe93-119">方法: 拡張メソッドを記述する</span><span class="sxs-lookup"><span data-stu-id="0fe93-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="0fe93-120">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="0fe93-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="0fe93-121">Visual Basic 内のスコープ</span><span class="sxs-lookup"><span data-stu-id="0fe93-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
