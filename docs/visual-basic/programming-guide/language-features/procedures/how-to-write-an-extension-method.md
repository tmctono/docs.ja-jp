---
title: '方法: 拡張メソッド (Visual Basic) を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 00d62d275f7afc06e066a375dc1ffcd74b23c9ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666002"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="23935-102">方法: 拡張メソッド (Visual Basic) を作成します。</span><span class="sxs-lookup"><span data-stu-id="23935-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="23935-103">拡張メソッドを使用すると、既存のクラスにメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="23935-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="23935-104">そのクラスのインスタンスの場合と同様、拡張メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="23935-104">The extension method can be called as if it were an instance of that class.</span></span>  
  
### <a name="to-define-an-extension-method"></a><span data-ttu-id="23935-105">拡張メソッドを定義するには</span><span class="sxs-lookup"><span data-stu-id="23935-105">To define an extension method</span></span>  
  
1. <span data-ttu-id="23935-106">Visual Studio では、新規または既存の Visual Basic アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="23935-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>  
  
2. <span data-ttu-id="23935-107">拡張メソッドを定義するファイルの上部にある次の import ステートメントを含めます。</span><span class="sxs-lookup"><span data-stu-id="23935-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3. <span data-ttu-id="23935-108">新規または既存のアプリケーションで、モジュール内には、拡張機能属性を持つメソッドの定義を開始します。</span><span class="sxs-lookup"><span data-stu-id="23935-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>  
  
    ```  
    <Extension()>  
    ```  
  
4. <span data-ttu-id="23935-109">最初のパラメーターの型が拡張するデータ型にする必要がありますが、通常の方法で、メソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="23935-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a><span data-ttu-id="23935-110">例</span><span class="sxs-lookup"><span data-stu-id="23935-110">Example</span></span>  
 <span data-ttu-id="23935-111">次の例では、モジュールの拡張メソッドを宣言する`StringExtensions`します。</span><span class="sxs-lookup"><span data-stu-id="23935-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="23935-112">2 番目のモジュール`Module1`、インポート`StringExtensions`メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="23935-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="23935-113">呼び出されると、拡張メソッドがスコープ内にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23935-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="23935-114">拡張メソッド`PrintAndPunctuate`拡張、<xref:System.String>文字列インスタンスを表示するメソッドを持つクラスが続けてでパラメーターとして送信される区切り記号の文字列。</span><span class="sxs-lookup"><span data-stu-id="23935-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>  
  
```vb  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
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
  
 <span data-ttu-id="23935-115">メソッドが 2 つのパラメーターで定義され、1 つだけということに注意してください。</span><span class="sxs-lookup"><span data-stu-id="23935-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="23935-116">最初のパラメーターでは、`aString`に、メソッドの定義がバインドされている`example`のインスタンス`String`メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="23935-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="23935-117">この例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23935-117">The output of the example is as follows:</span></span>  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="23935-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="23935-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="23935-119">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="23935-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="23935-120">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="23935-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="23935-121">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="23935-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="23935-122">Visual Basic におけるスコープ</span><span class="sxs-lookup"><span data-stu-id="23935-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
