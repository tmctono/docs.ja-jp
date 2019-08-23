---
title: Visual Basic の Main プロシージャ
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 19c6fcb04a373d782db3deafc732f69bf20e7f0e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962774"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="e7d4a-102">Visual Basic の Main プロシージャ</span><span class="sxs-lookup"><span data-stu-id="e7d4a-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="e7d4a-103">すべての Visual Basic アプリケーションには、と`Main`いうプロシージャが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="e7d4a-104">この手順は、アプリケーションの開始点と全体的な制御として機能します。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="e7d4a-105">.NET Framework は、アプリケーション`Main`を読み込んだときにプロシージャを呼び出し、そのプロシージャに制御を渡す準備ができています。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="e7d4a-106">Windows フォームアプリケーションを作成する場合を除き、独自に実行`Main`するアプリケーション用の手順を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>

 <span data-ttu-id="e7d4a-107">`Main`最初に実行されるコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="e7d4a-108">で`Main`は、プログラムの開始時に最初に読み込まれるフォームを決定し、アプリケーションのコピーが既にシステムで実行されているかどうかを確認したり、アプリケーションに対して一連の変数を設定したり、アプリケーションで必要なデータベースを開いたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>

## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="e7d4a-109">Main プロシージャの要件</span><span class="sxs-lookup"><span data-stu-id="e7d4a-109">Requirements for the Main Procedure</span></span>
 <span data-ttu-id="e7d4a-110">独自の (通常は拡張子 .exe) で実行されるファイルには、 `Main`プロシージャが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="e7d4a-111">ライブラリ (たとえば、拡張子 .dll) は独自には実行されず、プロシージャは`Main`必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="e7d4a-112">作成できるさまざまな種類のプロジェクトの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-112">The requirements for the different types of projects you can create are as follows:</span></span>

- <span data-ttu-id="e7d4a-113">コンソールアプリケーションは自身で実行されるため、少なくとも 1 `Main`つのプロシージャを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span>

- <span data-ttu-id="e7d4a-114">Windows フォームアプリケーションは独自に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-114">Windows Forms applications run on their own.</span></span> <span data-ttu-id="e7d4a-115">ただし、このようなアプリケーションでは`Main` 、Visual Basic コンパイラによってプロシージャが自動的に生成されるため、作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-115">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>

- <span data-ttu-id="e7d4a-116">クラスライブラリには、プロシージャ`Main`は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-116">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="e7d4a-117">これには、Windows コントロールライブラリと Web コントロールライブラリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-117">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="e7d4a-118">Web アプリケーションはクラスライブラリとして配置されます。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-118">Web applications are deployed as class libraries.</span></span>

## <a name="declaring-the-main-procedure"></a><span data-ttu-id="e7d4a-119">Main プロシージャの宣言</span><span class="sxs-lookup"><span data-stu-id="e7d4a-119">Declaring the Main Procedure</span></span>
 <span data-ttu-id="e7d4a-120">プロシージャを宣言するには、 `Main`次の4つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-120">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="e7d4a-121">引数を受け取ることも、それ以外の値を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-121">It can take arguments or not, and it can return a value or not.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d4a-122">クラスでを`Main`宣言する場合は、 `Shared`キーワードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-122">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="e7d4a-123">モジュールでは、 `Main`はである必要`Shared`はありません。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-123">In a module, `Main` does not need to be `Shared`.</span></span>

- <span data-ttu-id="e7d4a-124">最も簡単な方法は、引数`Sub`を取らず、値を返さないプロシージャを宣言することです。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-124">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- <span data-ttu-id="e7d4a-125">`Main`は、オペレーティングシステム`Integer`がプログラムの終了コードとして使用する値を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-125">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="e7d4a-126">他のプログラムでは、Windows の ERRORLEVEL 値を調べることによって、このコードをテストできます。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-126">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="e7d4a-127">終了コードを返すには、 `Main` `Sub`プロシージャではなく`Function` 、プロシージャとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-127">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>

    ```vb
    Module mainModule
        Function Main() As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- <span data-ttu-id="e7d4a-128">`Main`は、引数と`String`して配列を受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-128">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="e7d4a-129">配列内の各文字列には、プログラムを呼び出すために使用されるコマンドライン引数の1つが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-129">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="e7d4a-130">値に応じて、さまざまなアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-130">You can take different actions depending on their values.</span></span>

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- <span data-ttu-id="e7d4a-131">を宣言`Main`すると、次のように、コマンドライン引数を調べることができますが、終了コードは返されません。</span><span class="sxs-lookup"><span data-stu-id="e7d4a-131">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```
  
## <a name="see-also"></a><span data-ttu-id="e7d4a-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7d4a-132">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="e7d4a-133">Visual Basic プログラムの構造</span><span class="sxs-lookup"><span data-stu-id="e7d4a-133">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="e7d4a-134">/main</span><span class="sxs-lookup"><span data-stu-id="e7d4a-134">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="e7d4a-135">Shared</span><span class="sxs-lookup"><span data-stu-id="e7d4a-135">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="e7d4a-136">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="e7d4a-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="e7d4a-137">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="e7d4a-137">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e7d4a-138">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="e7d4a-138">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="e7d4a-139">String データ型</span><span class="sxs-lookup"><span data-stu-id="e7d4a-139">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
