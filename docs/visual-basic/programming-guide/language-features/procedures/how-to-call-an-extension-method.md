---
title: '方法: 拡張メソッド (Visual Basic) を呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 5cb0684637a716dfec947740ba345c62eaabddd7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863676"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="1eaed-102">方法: 拡張メソッド (Visual Basic) を呼び出す</span><span class="sxs-lookup"><span data-stu-id="1eaed-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="1eaed-103">拡張メソッドを使用すると、既存のクラスにメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1eaed-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="1eaed-104">拡張メソッドが宣言され、スコープに取り込む後、は、拡張する型のインスタンス メソッドのように呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="1eaed-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="1eaed-105">拡張メソッドを記述する方法の詳細については、次を参照してください。[方法。拡張メソッドを記述](./how-to-write-an-extension-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="1eaed-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="1eaed-106">次の手順は、拡張メソッドを参照してください`PrintAndPunctuate`、2 番目のパラメーターに渡される文字列インスタンスを呼び出した後にどのような値が表示されますが`punc`します。</span><span class="sxs-lookup"><span data-stu-id="1eaed-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
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
  
 <span data-ttu-id="1eaed-107">メソッドは、呼び出された場合、スコープ内にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eaed-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="1eaed-108">拡張メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="1eaed-108">To call an extension method</span></span>  
  
1. <span data-ttu-id="1eaed-109">拡張メソッドの最初のパラメーターのデータ型を持つ変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="1eaed-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="1eaed-110">`PrintAndPunctuate`、する必要があります、<xref:System.String>変数。</span><span class="sxs-lookup"><span data-stu-id="1eaed-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2. <span data-ttu-id="1eaed-111">変数が、拡張メソッドを呼び出し、その値が最初のパラメーターにバインドされている`aString`します。</span><span class="sxs-lookup"><span data-stu-id="1eaed-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="1eaed-112">次のステートメントの呼び出しが表示されます`Ready?`します。</span><span class="sxs-lookup"><span data-stu-id="1eaed-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="1eaed-113">この拡張メソッドの呼び出しは単に注意してくださいなどのいずれかを呼び出し、<xref:System.String>インスタンス メソッドを 1 つのパラメーターを必要とします。</span><span class="sxs-lookup"><span data-stu-id="1eaed-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3. <span data-ttu-id="1eaed-114">もう 1 つの文字列変数を宣言し、任意の文字列で動作するかを確認するには、もう一度メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1eaed-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="1eaed-115">この時間になります:`or not!!!`します。</span><span class="sxs-lookup"><span data-stu-id="1eaed-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eaed-116">例</span><span class="sxs-lookup"><span data-stu-id="1eaed-116">Example</span></span>  
 <span data-ttu-id="1eaed-117">次のコード作成の完全な例を単純な拡張メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1eaed-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1eaed-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1eaed-118">See also</span></span>

- [<span data-ttu-id="1eaed-119">方法: 拡張メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="1eaed-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="1eaed-120">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="1eaed-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="1eaed-121">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="1eaed-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
