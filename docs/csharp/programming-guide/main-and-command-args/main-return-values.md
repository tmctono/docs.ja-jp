---
title: Main() の戻り値 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: 1be04f98a4dec1317c485c7e482568cfe48ea9bf
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588888"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="35759-102">Main() の戻り値 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="35759-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="35759-103">`Main` メソッドは `void` を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="35759-103">The `Main` method can return `void`:</span></span>

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

<span data-ttu-id="35759-104">`int` を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="35759-104">It can also return an `int`:</span></span>

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

<span data-ttu-id="35759-105">`Main` からの戻り値を使用しない場合は、`void` を返すと少し簡単なコードにすることができます。</span><span class="sxs-lookup"><span data-stu-id="35759-105">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="35759-106">ただし、整数値を返すことによって、プログラムが状態の情報を、実行可能ファイルを呼び出す他のプログラムまたはスクリプトに伝達することができます。</span><span class="sxs-lookup"><span data-stu-id="35759-106">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="35759-107">`Main` からの戻り値は、プロセスの終了コードとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="35759-107">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="35759-108">`void` が `Main` から返された場合、終了コードは暗黙的に `0` になります。</span><span class="sxs-lookup"><span data-stu-id="35759-108">If `void` is returned from `Main` the exit code will be implicitly `0`.</span></span> <span data-ttu-id="35759-109">次の例では、`Main` からの戻り値にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="35759-109">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="35759-110">例</span><span class="sxs-lookup"><span data-stu-id="35759-110">Example</span></span>

<span data-ttu-id="35759-111">この例では、[.NET Core](../../../core/index.md) コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="35759-111">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="35759-112">.NET Core コマンド ライン ツールに慣れていない場合は、この[概要のトピック](../../../core/tutorials/using-with-xplat-cli.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35759-112">If you are unfamiliar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/using-with-xplat-cli.md).</span></span>

<span data-ttu-id="35759-113">*program.cs* の `Main` メソッドを次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="35759-113">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="35759-114">プログラムを Windows で実行する場合、`Main` 関数からの戻り値はすべて 1 つの環境変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="35759-114">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="35759-115">この環境変数を取得するには、バッチ ファイルから `ERRORLEVEL` を使用するか、PowerShell から `$LastExitCode` を使用します。</span><span class="sxs-lookup"><span data-stu-id="35759-115">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="35759-116">[dotnet CLI](../../../core/tools/dotnet.md) の `dotnet build` コマンドを使用してアプリケーションを構築できます。</span><span class="sxs-lookup"><span data-stu-id="35759-116">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="35759-117">次に、PowerShell スクリプトを使用してアプリケーションを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="35759-117">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="35759-118">次のコードをテキスト ファイルに貼り付け、プロジェクトが保存されているフォルダーに `test.ps1` として保存します。</span><span class="sxs-lookup"><span data-stu-id="35759-118">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="35759-119">PowerShell プロンプトに「`test.ps1`」と入力して PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="35759-119">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="35759-120">コードがゼロを返すため、バッチ ファイルで成功が報告されます。</span><span class="sxs-lookup"><span data-stu-id="35759-120">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="35759-121">ただし、MainReturnValTest.cs が 0 以外の値を返すように変更して、プログラムを再コンパイルする場合、PowerShell スクリプトの後続の実行では失敗が報告されます。</span><span class="sxs-lookup"><span data-stu-id="35759-121">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

```powershell
dotnet run
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="35759-122">出力例</span><span class="sxs-lookup"><span data-stu-id="35759-122">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="35759-123">非同期 Main の戻り値</span><span class="sxs-lookup"><span data-stu-id="35759-123">Async Main return values</span></span>

<span data-ttu-id="35759-124">非同期 Main の戻り値によって、`Main` 内の非同期メソッドを呼び出すために必要な定型コードを、コンパイラで生成されるコードに移動します。</span><span class="sxs-lookup"><span data-stu-id="35759-124">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="35759-125">以前のバージョンでは、このコンストラクトを出力して非同期コードを呼び出し、非同期操作が完了するまでプログラムが実行されるようにする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="35759-125">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

<span data-ttu-id="35759-126">現在のバージョンでは、以下のように書き換えられるようになりました。</span><span class="sxs-lookup"><span data-stu-id="35759-126">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="35759-127">新しい構文を使用すると、コンパイラから常に正しいコードが生成されるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="35759-127">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="35759-128">コンパイラから生成されるコード</span><span class="sxs-lookup"><span data-stu-id="35759-128">Compiler generated code</span></span>

<span data-ttu-id="35759-129">アプリケーションのエントリ ポイントから `Task` または `Task<int>` が返されると、コンパイラによって、アプリケーション コードで宣言されたエントリ ポイント メソッドを呼び出す新しいエントリ ポイントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="35759-129">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="35759-130">このエントリ ポイント名が `$GeneratedMain` だとすると、これらのエントリ ポイントについて次のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="35759-130">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="35759-131">`static Task Main()` の結果、`private static void $GeneratedMain() => Main().GetAwaiter().GetResult();` と同等のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="35759-131">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="35759-132">`static Task Main(string[])` の結果、`private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` と同等のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="35759-132">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="35759-133">`static Task<int> Main()` の結果、`private static int $GeneratedMain() => Main().GetAwaiter().GetResult();` と同等のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="35759-133">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="35759-134">`static Task<int> Main(string[])` の結果、`private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` と同等のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="35759-134">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="35759-135">この例の `Main` メソッドで `async` 修飾子を使用した場合、同じコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="35759-135">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="35759-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="35759-136">See also</span></span>

- [<span data-ttu-id="35759-137">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="35759-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="35759-138">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="35759-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="35759-139">Main() とコマンドライン引数</span><span class="sxs-lookup"><span data-stu-id="35759-139">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="35759-140">方法: コマンド ライン引数を表示する</span><span class="sxs-lookup"><span data-stu-id="35759-140">How to: Display Command Line Arguments</span></span>](./how-to-display-command-line-arguments.md)
