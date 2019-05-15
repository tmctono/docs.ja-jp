---
title: '方法: 作成し、コマンドライン (Visual Basic) を使用してアセンブリを使用します。'
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: a30d4b3ea203a8b4d3ba621fc7b0310477ddf10d
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592686"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="7ab5b-102">方法: 作成し、コマンドライン (Visual Basic) を使用してアセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="7ab5b-103">アセンブリとは、ダイナミック リンク ライブラリ (DLL) のことで、実行時にプログラムにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="7ab5b-104">DLL のビルド例および使用例として、次に示すシナリオを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
- <span data-ttu-id="7ab5b-105">`MathLibrary.DLL`:実行時に呼び出されるメソッドが格納されているライブラリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="7ab5b-106">この例では、DLL には 2 つのメソッド `Add` と `Multiply` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
- <span data-ttu-id="7ab5b-107">`Add`:`Add` メソッドが格納されているソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="7ab5b-108">パラメーターの和を返します。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="7ab5b-109">`Add` メソッドを含む `AddClass` クラスは `UtilityMethods` 名前空間のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="7ab5b-110">`Mult`:`Multiply` メソッドが格納されているソース コード。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="7ab5b-111">パラメーターの積を返します。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-111">It returns the product of its parameters.</span></span> <span data-ttu-id="7ab5b-112">`Multiply` メソッドを含む `MultiplyClass` クラスも `UtilityMethods` 名前空間のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="7ab5b-113">`TestCode`:`Main` メソッドが格納されているファイル。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="7ab5b-114">DLL ファイルのメソッドを使用して、実行時引数の和と積を計算します。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ab5b-115">例</span><span class="sxs-lookup"><span data-stu-id="7ab5b-115">Example</span></span>  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 <span data-ttu-id="7ab5b-116">このファイルには、DLL のメソッド `Add` と `Multiply` を使用するアルゴリズムが格納されています。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="7ab5b-117">最初に、コマンド ラインから入力された引数 `num1` と `num2` を解析します。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="7ab5b-118">次に、`AddClass` クラスの `Add` メソッドを使用して和を計算し、`MultiplyClass` クラスの `Multiply` メソッドを使って積を計算します。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="7ab5b-119">なお、`Imports`ファイルの先頭にあるステートメントでは、非修飾クラス名を使用して、次のように、コンパイル時に、DLL のメソッドを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="7ab5b-120">ディレクティブを指定しない場合は、次のように、完全修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="7ab5b-121">実行</span><span class="sxs-lookup"><span data-stu-id="7ab5b-121">Execution</span></span>  
 <span data-ttu-id="7ab5b-122">プログラムを実行するには、次のように、EXE ファイルの名前と 2 つの数値を順に入力します。</span><span class="sxs-lookup"><span data-stu-id="7ab5b-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a><span data-ttu-id="7ab5b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ab5b-123">See also</span></span>

- [<span data-ttu-id="7ab5b-124">プログラミングの概念</span><span class="sxs-lookup"><span data-stu-id="7ab5b-124">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="7ab5b-125">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="7ab5b-125">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="7ab5b-126">DLL 関数を保持するクラスの作成</span><span class="sxs-lookup"><span data-stu-id="7ab5b-126">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
