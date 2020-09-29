---
title: '方法: 拡張メソッドを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 38d6e8534283f475be2409f4b7c74ef48f1f248b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91074993"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="9dd3d-102">方法: 拡張メソッドを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9dd3d-102">How to: Call an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="9dd3d-103">拡張メソッドを使用すると、既存のクラスにメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="9dd3d-104">拡張メソッドが宣言され、スコープ内に入ると、拡張される型のインスタンス メソッドと同様に呼び出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="9dd3d-105">拡張メソッドを記述する方法の詳細については、「[方法: 拡張メソッドを作成する](./how-to-write-an-extension-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>

 <span data-ttu-id="9dd3d-106">次の手順では、拡張メソッド `PrintAndPunctuate` を参照しています。これにより、それを呼び出す文字列インスタンスが表示されてから、2 番目のパラメーター `punc` に送信される値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>

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

<span data-ttu-id="9dd3d-107">メソッドは、呼び出されるときにスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-107">The method must be in scope when it is called.</span></span>

### <a name="to-call-an-extension-method"></a><span data-ttu-id="9dd3d-108">拡張メソッドを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="9dd3d-108">To call an extension method</span></span>

1. <span data-ttu-id="9dd3d-109">拡張メソッドの最初のパラメーターのデータ型を持つ変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="9dd3d-110">`PrintAndPunctuate` の場合、<xref:System.String> 変数が必要です。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>

    ```vb
    Dim example = "Ready"
    ```

2. <span data-ttu-id="9dd3d-111">この変数によって拡張メソッドが呼び出され、その値は 1 つ目のパラメーター `aString` にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="9dd3d-112">次の呼び出し元ステートメントによって `Ready?` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-112">The following calling statement will display `Ready?`.</span></span>

    ```vb
    example.PrintAndPunctuate("?")
    ```

     <span data-ttu-id="9dd3d-113">この拡張メソッドに対する呼び出しは、1 つのパラメーターを必要とする <xref:System.String> インスタンス メソッドのいずれかに対する呼び出しと同じように見えることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. <span data-ttu-id="9dd3d-114">別の文字列変数を宣言し、メソッドを再度呼び出して、任意の文字列で機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-114">Declare another string variable and call the method again to see that it works with any string.</span></span>

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     <span data-ttu-id="9dd3d-115">今回の結果は `or not!!!` になります。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-115">The result this time is: `or not!!!`.</span></span>

## <a name="example"></a><span data-ttu-id="9dd3d-116">例</span><span class="sxs-lookup"><span data-stu-id="9dd3d-116">Example</span></span>

 <span data-ttu-id="9dd3d-117">次のコードは、単純な拡張メソッドの作成と使用の完全な例です。</span><span class="sxs-lookup"><span data-stu-id="9dd3d-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9dd3d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9dd3d-118">See also</span></span>

- [<span data-ttu-id="9dd3d-119">方法: 拡張メソッドを作成する</span><span class="sxs-lookup"><span data-stu-id="9dd3d-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="9dd3d-120">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="9dd3d-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="9dd3d-121">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="9dd3d-121">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
