---
title: メインのプロシージャ
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: d6708ee13963aaae43a73b159032f64f0fffac10
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072211"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="d6150-102">Visual Basic の Main プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d6150-102">Main Procedure in Visual Basic</span></span>

<span data-ttu-id="d6150-103">すべての Visual Basic アプリケーションには、`Main` と呼ばれるプロシージャが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6150-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="d6150-104">このプロシージャは、アプリケーションの開始点となり、アプリケーションの全体的な制御を行います。</span><span class="sxs-lookup"><span data-stu-id="d6150-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="d6150-105">.NET Framework では、アプリケーションが読み込まれ、制御を渡す準備ができると、`Main` プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d6150-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="d6150-106">Windows フォーム アプリケーションを作成する場合を除き、単独で実行されるアプリケーションでは、`Main` プロシージャを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6150-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>

 <span data-ttu-id="d6150-107">`Main` には、最初に実行されるコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d6150-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="d6150-108">`Main` では、プログラムの起動時に最初に読み込まれるフォームを決定したり、アプリケーションのコピーがシステムで既に実行されているかどうかを確認したりできます。また、アプリケーションの一連の変数を確立したり、アプリケーションに必要なデータベースを開いたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d6150-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>

## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="d6150-109">Main プロシージャの要件</span><span class="sxs-lookup"><span data-stu-id="d6150-109">Requirements for the Main Procedure</span></span>

 <span data-ttu-id="d6150-110">単独で実行されるファイル (通常は拡張子が .exe) には、`Main` プロシージャが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6150-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="d6150-111">ライブラリ (拡張子.dll など) は単独では実行されないので、`Main` プロシージャは不要です。</span><span class="sxs-lookup"><span data-stu-id="d6150-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="d6150-112">作成できるさまざまな種類のプロジェクトの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d6150-112">The requirements for the different types of projects you can create are as follows:</span></span>

- <span data-ttu-id="d6150-113">コンソール アプリケーションは単独で実行されるので、少なくとも 1 つの `Main` プロシージャを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6150-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span>

- <span data-ttu-id="d6150-114">Windows フォーム アプリケーションは単独で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d6150-114">Windows Forms applications run on their own.</span></span> <span data-ttu-id="d6150-115">ただし、このようなアプリケーションの `Main` プロシージャは、Visual Basic コンパイラによって自動的に生成されるので、記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d6150-115">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>

- <span data-ttu-id="d6150-116">クラス ライブラリには、`Main` プロシージャは不要です。</span><span class="sxs-lookup"><span data-stu-id="d6150-116">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="d6150-117">これには、Windows コントロール ライブラリや Web コントロール ライブラリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d6150-117">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="d6150-118">Web アプリケーションは、クラス ライブラリとして展開されます。</span><span class="sxs-lookup"><span data-stu-id="d6150-118">Web applications are deployed as class libraries.</span></span>

## <a name="declaring-the-main-procedure"></a><span data-ttu-id="d6150-119">Main プロシージャの宣言</span><span class="sxs-lookup"><span data-stu-id="d6150-119">Declaring the Main Procedure</span></span>

 <span data-ttu-id="d6150-120">`Main` プロシージャを宣言するには、4 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="d6150-120">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="d6150-121">引数を受け取ることも、受け取らないこともできます。また、値を返すことも返さないこともできます。</span><span class="sxs-lookup"><span data-stu-id="d6150-121">It can take arguments or not, and it can return a value or not.</span></span>

> [!NOTE]
> <span data-ttu-id="d6150-122">`Main` をクラスで宣言する場合は、`Shared` キーワードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6150-122">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="d6150-123">モジュールでは、`Main` は `Shared` である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d6150-123">In a module, `Main` does not need to be `Shared`.</span></span>

- <span data-ttu-id="d6150-124">最も簡単な方法は、引数を受け取らず、値を返さない `Sub` プロシージャを宣言することです。</span><span class="sxs-lookup"><span data-stu-id="d6150-124">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- <span data-ttu-id="d6150-125">`Main` では、オペレーティング システムがプログラムの終了コードとして使用する `Integer` 値を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="d6150-125">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="d6150-126">他のプログラムは Windows の ERRORLEVEL 値を調べることで、このコードをテストできます。</span><span class="sxs-lookup"><span data-stu-id="d6150-126">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="d6150-127">終了コードを返すには、`Sub` プロシージャではなく、`Function` プロシージャとして `Main` を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6150-127">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>

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

- <span data-ttu-id="d6150-128">`Main` では、引数として `String` 配列を受け取ることもできます。</span><span class="sxs-lookup"><span data-stu-id="d6150-128">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="d6150-129">配列内の各文字列には、プログラムの呼び出しに使用されるコマンド ライン引数の 1 つが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d6150-129">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="d6150-130">値に応じてさまざまなアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d6150-130">You can take different actions depending on their values.</span></span>

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

- <span data-ttu-id="d6150-131">次のように、コマンド ライン引数を調べ、終了コードは返さないように、`Main` を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="d6150-131">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>

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
  
## <a name="see-also"></a><span data-ttu-id="d6150-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6150-132">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="d6150-133">Visual Basic プログラムの構造</span><span class="sxs-lookup"><span data-stu-id="d6150-133">Structure of a Visual Basic Program</span></span>](structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="d6150-134">-main</span><span class="sxs-lookup"><span data-stu-id="d6150-134">-main</span></span>](../../reference/command-line-compiler/main.md)
- [<span data-ttu-id="d6150-135">Shared</span><span class="sxs-lookup"><span data-stu-id="d6150-135">Shared</span></span>](../../language-reference/modifiers/shared.md)
- [<span data-ttu-id="d6150-136">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="d6150-136">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d6150-137">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="d6150-137">Function Statement</span></span>](../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="d6150-138">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="d6150-138">Integer Data Type</span></span>](../../language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="d6150-139">String データ型</span><span class="sxs-lookup"><span data-stu-id="d6150-139">String Data Type</span></span>](../../language-reference/data-types/string-data-type.md)
