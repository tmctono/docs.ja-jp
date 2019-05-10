---
title: '方法: 作成し、コマンドライン (Visual Basic) を使用してアセンブリを使用します。'
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: d58109dfbb03b752f4a46f895fa1093e4f37df71
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624778"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="f5f01-102">方法: 作成し、コマンドライン (Visual Basic) を使用してアセンブリを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="f5f01-103">アセンブリとは、ダイナミック リンク ライブラリ (DLL) のことで、実行時にプログラムにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="f5f01-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="f5f01-104">DLL のビルド例および使用例として、次に示すシナリオを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="f5f01-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
- <span data-ttu-id="f5f01-105">`MathLibrary.DLL`:実行時に呼び出されるメソッドが格納されているライブラリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="f5f01-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="f5f01-106">この例では、DLL には 2 つのメソッド `Add` と `Multiply` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5f01-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
- <span data-ttu-id="f5f01-107">`Add`:`Add` メソッドが格納されているソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="f5f01-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="f5f01-108">パラメーターの和を返します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="f5f01-109">`Add` メソッドを含む `AddClass` クラスは `UtilityMethods` 名前空間のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="f5f01-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="f5f01-110">`Mult`:`Multiply` メソッドが格納されているソース コード。</span><span class="sxs-lookup"><span data-stu-id="f5f01-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="f5f01-111">パラメーターの積を返します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-111">It returns the product of its parameters.</span></span> <span data-ttu-id="f5f01-112">`Multiply` メソッドを含む `MultiplyClass` クラスも `UtilityMethods` 名前空間のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="f5f01-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="f5f01-113">`TestCode`:`Main` メソッドが格納されているファイル。</span><span class="sxs-lookup"><span data-stu-id="f5f01-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="f5f01-114">DLL ファイルのメソッドを使用して、実行時引数の和と積を計算します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5f01-115">例</span><span class="sxs-lookup"><span data-stu-id="f5f01-115">Example</span></span>  
  
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
  
 <span data-ttu-id="f5f01-116">このファイルには、DLL のメソッド `Add` と `Multiply` を使用するアルゴリズムが格納されています。</span><span class="sxs-lookup"><span data-stu-id="f5f01-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="f5f01-117">最初に、コマンド ラインから入力された引数 `num1` と `num2` を解析します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="f5f01-118">次に、`AddClass` クラスの `Add` メソッドを使用して和を計算し、`MultiplyClass` クラスの `Multiply` メソッドを使って積を計算します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="f5f01-119">なお、`Imports`ファイルの先頭にあるステートメントでは、非修飾クラス名を使用して、次のように、コンパイル時に、DLL のメソッドを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="f5f01-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="f5f01-120">ディレクティブを指定しない場合は、次のように、完全修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5f01-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="f5f01-121">実行</span><span class="sxs-lookup"><span data-stu-id="f5f01-121">Execution</span></span>  
 <span data-ttu-id="f5f01-122">プログラムを実行するには、次のように、EXE ファイルの名前と 2 つの数値を順に入力します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f5f01-123">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f5f01-123">Compiling the Code</span></span>  
 <span data-ttu-id="f5f01-124">`MathLibrary.DLL` ファイルをビルドするには、次のコマンド ラインを使用して、`Add` ファイルと `Mult` ファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f5f01-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="f5f01-125">[-ターゲット (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md)コンパイラ オプション、EXE ファイルではなく、DLL を出力するようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-125">The [-target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="f5f01-126">[-(Visual Basic) を](../../../../visual-basic/reference/command-line-compiler/out.md)コンパイラ オプションの後にファイル名は DLL のファイル名を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-126">The [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="f5f01-127">このオプションを指定しないと、コンパイラは最初のファイル (`Add.vb`) を DLL の名前として使用します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="f5f01-128">実行可能ファイル `TestCode.exe` をビルドするには、次のコマンド ラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="f5f01-129">**-アウト**コンパイラ オプションは、コンパイラは EXE ファイルを出力して、出力ファイルの名前を指定します (`TestCode.exe`)。</span><span class="sxs-lookup"><span data-stu-id="f5f01-129">The **-out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="f5f01-130">このコンパイラ オプションは省略できます。</span><span class="sxs-lookup"><span data-stu-id="f5f01-130">This compiler option is optional.</span></span> <span data-ttu-id="f5f01-131">[-参照 (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md)コンパイラ オプションは、このプログラムで使用される DLL ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-131">The [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="f5f01-132">コマンドラインからのビルドの詳細については、次を参照してください。 および[、コマンドラインからビルドする](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5f01-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f01-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5f01-133">See also</span></span>

- [<span data-ttu-id="f5f01-134">プログラミングの概念</span><span class="sxs-lookup"><span data-stu-id="f5f01-134">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="f5f01-135">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="f5f01-135">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="f5f01-136">DLL 関数を保持するクラスの作成</span><span class="sxs-lookup"><span data-stu-id="f5f01-136">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
