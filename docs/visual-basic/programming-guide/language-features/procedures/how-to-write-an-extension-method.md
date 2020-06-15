---
title: '方法: 拡張メソッドを作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 697508f86ff4ff0a89150b65782121395d0fed12
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346013"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="a309f-102">方法: 拡張メソッドを作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a309f-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="a309f-103">拡張メソッドを使用すると、既存のクラスにメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a309f-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="a309f-104">拡張メソッドは、そのクラスのインスタンスであるかのように呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a309f-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="a309f-105">拡張メソッドを定義するには</span><span class="sxs-lookup"><span data-stu-id="a309f-105">To define an extension method</span></span>

1. <span data-ttu-id="a309f-106">Visual Studio で、新規または既存の Visual Basic アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="a309f-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="a309f-107">拡張メソッドを定義するファイルの先頭に、次のインポート ステートメントを含めます。</span><span class="sxs-lookup"><span data-stu-id="a309f-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="a309f-108">新規または既存のアプリケーションのモジュール内で、メソッド定義を [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) 属性で開始します。</span><span class="sxs-lookup"><span data-stu-id="a309f-108">Within a module in your new or existing application, begin the method definition with the [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) attribute:</span></span>

    ```vb
    <Extension()>
    ```

    <span data-ttu-id="a309f-109">`Extension` 属性は、Visual Basic の [Module](../../../language-reference/statements/module-statement.md) 内のメソッド (`Sub` または `Function` プロシージャ) にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="a309f-109">Note that the `Extension` attribute can only be applied to a method (a `Sub` or `Function` procedure) in a Visual Basic [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="a309f-110">`Class` または `Structure` 内のメソッドに適用すると、Visual Basic コンパイラは、エラー [BC36551](../../../misc/bc36551.md) "Extension methods can be defined only in modules\(拡張メソッドはモジュール内でのみ定義できます\)" を生成します。</span><span class="sxs-lookup"><span data-stu-id="a309f-110">If you apply it to a method in a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules."</span></span>

4. <span data-ttu-id="a309f-111">通常の方法でメソッドを宣言します。ただし、最初のパラメーターの型は、拡張するデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a309f-111">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="a309f-112">例</span><span class="sxs-lookup"><span data-stu-id="a309f-112">Example</span></span>

<span data-ttu-id="a309f-113">次の例では、モジュール `StringExtensions` で拡張メソッドを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="a309f-113">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="a309f-114">2 番目のモジュール `Module1` は、`StringExtensions` をインポートし、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a309f-114">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="a309f-115">拡張メソッドは、呼び出されるときのスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="a309f-115">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="a309f-116">拡張メソッド `PrintAndPunctuate` は、文字列インスタンスを表示し、その後にパラメーターとして送信された句読記号の文字列を表示するメソッドで <xref:System.String> クラスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="a309f-116">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>

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

<span data-ttu-id="a309f-117">このメソッドは 2 つのパラメーターで定義され、その 1 つでのみ呼び出されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a309f-117">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="a309f-118">メソッド定義の最初のパラメーターである `aString` は、メソッドを呼び出す `String` のインスタンスである `example` にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="a309f-118">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="a309f-119">この例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a309f-119">The output of the example is as follows:</span></span>

```console
Hello?
Hello!!!!
```

## <a name="see-also"></a><span data-ttu-id="a309f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a309f-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="a309f-121">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="a309f-121">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="a309f-122">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="a309f-122">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="a309f-123">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="a309f-123">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a309f-124">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="a309f-124">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
