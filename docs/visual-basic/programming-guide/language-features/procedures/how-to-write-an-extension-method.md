---
title: '方法: 拡張メソッドを記述する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 31ccb18e0e6d1569764ec2a67201d7f758129425
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332755"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="0307a-102">方法: 拡張メソッドを記述する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0307a-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="0307a-103">拡張メソッドを使用すると、既存のクラスにメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0307a-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="0307a-104">拡張メソッドは、そのクラスのインスタンスであるかのように呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0307a-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="0307a-105">拡張メソッドを定義するには</span><span class="sxs-lookup"><span data-stu-id="0307a-105">To define an extension method</span></span>

1. <span data-ttu-id="0307a-106">Visual Studio で新規または既存の Visual Basic アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="0307a-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="0307a-107">拡張メソッドを定義するファイルの先頭に、次の import ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="0307a-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="0307a-108">新規または既存のアプリケーションのモジュール内で、拡張属性を使用してメソッド定義を開始します。</span><span class="sxs-lookup"><span data-stu-id="0307a-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>

    ```vb
    <Extension()>
    ```

4. <span data-ttu-id="0307a-109">通常の方法でメソッドを宣言します。ただし、最初のパラメーターの型は、拡張するデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0307a-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="0307a-110">例</span><span class="sxs-lookup"><span data-stu-id="0307a-110">Example</span></span>

 <span data-ttu-id="0307a-111">次の例では、モジュール `StringExtensions` の拡張メソッドを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="0307a-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="0307a-112">2番目のモジュール (@no__t 0) は `StringExtensions` をインポートし、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0307a-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="0307a-113">拡張メソッドが呼び出されたときは、その拡張メソッドがスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0307a-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="0307a-114">拡張メソッド `PrintAndPunctuate` は、文字列インスタンスを表示するメソッドを使用して <xref:System.String> クラスを拡張し、パラメーターとしてに送信される区切り記号の文字列を続けます。</span><span class="sxs-lookup"><span data-stu-id="0307a-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

```vb
' Import the module that holds the extension method you want to use,
' and call it.

Imports ConsoleApplication2.StringExtensions

Module Module1
  
    Sub Main()
        Dim example = "Hello"
        example.PrintAndPunctuate("?")
        example.PrintAndPunctuate("!!!!")
    End Sub
    
End Module
```
  
 <span data-ttu-id="0307a-115">メソッドは2つのパラメーターで定義され、1つだけを使用して呼び出されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0307a-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="0307a-116">メソッド定義内の最初のパラメーターである @no__t 0 は、メソッドを呼び出す `String` のインスタンス @no__t にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="0307a-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="0307a-117">この例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0307a-117">The output of the example is as follows:</span></span>
  
 ```console
 Hello?
 Hello!!!!
 ```
  
## <a name="see-also"></a><span data-ttu-id="0307a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0307a-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="0307a-119">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="0307a-119">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="0307a-120">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="0307a-120">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="0307a-121">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="0307a-121">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0307a-122">Visual Basic 内のスコープ</span><span class="sxs-lookup"><span data-stu-id="0307a-122">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
