---
title: CLI を使用する .NET Core に関する概要
description: Windows、Linux、または macOS 上で .NET Core CLI を使用して .NET Core の使用を開始する方法を詳細に説明するチュートリアルです。
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: 1a691ad0c1f8dbfadd642360d7f9629a136ff3ab
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156661"
---
# <a name="get-started-with-net-core-using-the-net-core-cli"></a><span data-ttu-id="ca426-103">.NET Core CLI を使用した .NET Core の概要</span><span class="sxs-lookup"><span data-stu-id="ca426-103">Get started with .NET Core using the .NET Core CLI</span></span>

<span data-ttu-id="ca426-104">この記事では、.NET Core CLI を使用して、Windows、Linux、macOS 上で動作する .NET Core アプリの開発を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca426-104">This article will show you how to start developing .NET Core apps that work on Windows, Linux, and macOS using the .NET Core CLI.</span></span>

<span data-ttu-id="ca426-105">.NET Core CLI に慣れていない場合は、「[.NET Core CLI の概要](../tools/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ca426-105">If you're unfamiliar with the .NET Core CLI, see the [.NET Core CLI overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca426-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ca426-106">Prerequisites</span></span>

- <span data-ttu-id="ca426-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) 以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="ca426-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="ca426-108">ユーザーが選んだテキスト エディターまたはコード エディター。</span><span class="sxs-lookup"><span data-stu-id="ca426-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="ca426-109">Hello コンソール アプリ</span><span class="sxs-lookup"><span data-stu-id="ca426-109">Hello, Console App!</span></span>

<span data-ttu-id="ca426-110">GitHub の dotnet/samples レポジトリから、[サンプル コードを表示またはダウンロード](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild)することができます。</span><span class="sxs-lookup"><span data-stu-id="ca426-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="ca426-111">ダウンロード方法については、「[サンプルおよびチュートリアル](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca426-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="ca426-112">コマンド プロンプトを開き、*Hello* という名前のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca426-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="ca426-113">作成したフォルダーに移動して、以下を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca426-113">Navigate to the folder you created and type the following.</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="ca426-114">簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="ca426-114">Let's do a quick walkthrough:</span></span>

01. `dotnet new console`

    <span data-ttu-id="ca426-115">[dotnet new](../tools/dotnet-new.md) で、コンソール アプリのビルドに必要な依存関係を含む最新の *Hello.csproj* プロジェクト ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-115">[dotnet new](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="ca426-116">また、アプリケーションのエントリ ポイントを含む基本的なファイルである *Program.cs* も作成します。</span><span class="sxs-lookup"><span data-stu-id="ca426-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>

    <span data-ttu-id="ca426-117">*Hello.csproj*:</span><span class="sxs-lookup"><span data-stu-id="ca426-117">*Hello.csproj*:</span></span>

    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]

    <span data-ttu-id="ca426-118">プロジェクト ファイルでは、依存関係を復元し、プログラムをビルドするために必要なすべてのものを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca426-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

    - <span data-ttu-id="ca426-119">`<OutputType>` 要素で、実行可能ファイル (つまり、コンソール アプリケーション) をビルドすることが示されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-119">The `<OutputType>` element specifies that we're building an executable, in other words a console application.</span></span>
    - <span data-ttu-id="ca426-120">`<TargetFramework>` 要素で、ターゲットの .NET 実装が指定されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-120">The `<TargetFramework>` element specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="ca426-121">高度なシナリオでは、複数の対象フレームワークを指定し、1 回の操作でそれらすべてにビルドすることができます。</span><span class="sxs-lookup"><span data-stu-id="ca426-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="ca426-122">このチュートリアルでは、.NET Core 3.1 の場合のビルドについてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="ca426-122">In this tutorial, we'll stick to building only for .NET Core 3.1.</span></span>

    <span data-ttu-id="ca426-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="ca426-123">*Program.cs*:</span></span>

    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]

    <span data-ttu-id="ca426-124">プログラムは `using System` で始まります。これは、"`System` 名前空間のすべてがこのファイルのスコープになる" こと意味します。</span><span class="sxs-lookup"><span data-stu-id="ca426-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="ca426-125">`System` 名前空間には、`Console` クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca426-125">The `System` namespace includes the `Console` class.</span></span>

    <span data-ttu-id="ca426-126">次に、`Hello` という名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="ca426-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="ca426-127">これを必要なものに変更できます。</span><span class="sxs-lookup"><span data-stu-id="ca426-127">You can change this to anything you want.</span></span> <span data-ttu-id="ca426-128">その名前空間に、`Program` という名前のクラスが、`args` という名前の文字列配列を使用する `Main` メソッドと共に定義されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings named `args`.</span></span> <span data-ttu-id="ca426-129">この配列には、プログラムの実行時に渡される引数のリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca426-129">This array contains the list of arguments passed in when the program is run.</span></span> <span data-ttu-id="ca426-130">このままではこの配列は使用されず、プログラムは単に "Hello World!" というテキストを</span><span class="sxs-lookup"><span data-stu-id="ca426-130">As it is, this array is not used and the program simply writes the text "Hello World!"</span></span> <span data-ttu-id="ca426-131">記述するだけです。</span><span class="sxs-lookup"><span data-stu-id="ca426-131">to the console.</span></span> <span data-ttu-id="ca426-132">後に、この引数を利用するようにコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="ca426-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

    <span data-ttu-id="ca426-133">`dotnet new` で、[dotnet restore](../tools/dotnet-restore.md) が暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-133">`dotnet new` calls [dotnet restore](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="ca426-134">`dotnet restore` は、[NuGet](https://www.nuget.org/) (.NET パッケージ マネージャー) を呼び出して依存関係ツリーを復元します。</span><span class="sxs-lookup"><span data-stu-id="ca426-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="ca426-135">NuGet は、*Hello.csproj* ファイルを分析し、ファイルに記載されている依存関係をダウンロードし (またはコンピューターのキャッシュから取得し)、サンプルをコンパイルして実行するために必要な *obj/project.assets.json* ファイルを記述します。</span><span class="sxs-lookup"><span data-stu-id="ca426-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

02. `dotnet run`

    <span data-ttu-id="ca426-136">[dotnet run](../tools/dotnet-run.md) で [dotnet build](../tools/dotnet-build.md) が呼び出され、ビルド ターゲットがビルドされていることを確認した後、`dotnet <assembly.dll>` が呼び出されてターゲット アプリケーションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-136">[dotnet run](../tools/dotnet-run.md) calls [dotnet build](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="ca426-137">次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="ca426-137">You get the following output.</span></span>

    ```console
    Hello World!
    ```

    <span data-ttu-id="ca426-138">または、`dotnet build` を実行して、ビルド コンソール アプリケーションを実行しないでコードをコンパイルすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ca426-138">Alternatively, you can also run `dotnet build` to compile the code without running the build console applications.</span></span> <span data-ttu-id="ca426-139">これにより、プロジェクトの名前に基づいて、コンパイル済みのアプリケーションが DLL ファイルとして生成されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-139">This results in a compiled application, as a DLL file, based on the name of the project.</span></span> <span data-ttu-id="ca426-140">この場合、作成されるファイルの名前は *Hello.dll* になります。</span><span class="sxs-lookup"><span data-stu-id="ca426-140">In this case, the file created is named *Hello.dll*.</span></span> <span data-ttu-id="ca426-141">このアプリを、Windows 上で `dotnet bin\Debug\netcoreapp3.1\Hello.dll` を使用して実行できます (Windows 以外のシステムでは `/` を使用します)。</span><span class="sxs-lookup"><span data-stu-id="ca426-141">This app can be run with `dotnet bin\Debug\netcoreapp3.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span>

    ```dotnetcli
    dotnet bin\Debug\netcoreapp3.1\Hello.dll
    ```

    <span data-ttu-id="ca426-142">次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="ca426-142">You get the following output.</span></span>

    ```console
    Hello World!
    ```

    <span data-ttu-id="ca426-143">アプリがコンパイルされると、オペレーティング システム固有の実行可能ファイルが `Hello.dll` と共に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-143">When the app is compiled, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="ca426-144">Windows では、これは `Hello.exe` になります。Linux または macOS では、これは `hello` になります。</span><span class="sxs-lookup"><span data-stu-id="ca426-144">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="ca426-145">上記の例では、ファイルの名前は `Hello.exe` または `Hello` になります。</span><span class="sxs-lookup"><span data-stu-id="ca426-145">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="ca426-146">その実行可能ファイルを直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca426-146">You can run that executable directly.</span></span>

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a><span data-ttu-id="ca426-147">プログラムを変更する</span><span class="sxs-lookup"><span data-stu-id="ca426-147">Modify the program</span></span>

<span data-ttu-id="ca426-148">プログラムを少し変更してみましょう。</span><span class="sxs-lookup"><span data-stu-id="ca426-148">Let's change the program a bit.</span></span> <span data-ttu-id="ca426-149">フィボナッチ数列はおもしろいので、これを追加しましょう。また、引数を使用してアプリを実行している人にあいさつしましょう。</span><span class="sxs-lookup"><span data-stu-id="ca426-149">Fibonacci numbers are fun, so let's add that and also to use the argument to greet the person running the app.</span></span>

01. <span data-ttu-id="ca426-150">*Program.cs* ファイルの内容を次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ca426-150">Replace the contents of your *Program.cs*  file with the following code:</span></span>

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. <span data-ttu-id="ca426-151">[dotnet build](../tools/dotnet-build.md) を実行して、変更をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ca426-151">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

03. <span data-ttu-id="ca426-152">アプリにパラメーターを渡すプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca426-152">Run the program passing a parameter to the app.</span></span> <span data-ttu-id="ca426-153">`dotnet` コマンドを使用してアプリを実行する場合は、`--` を末尾に追加します。</span><span class="sxs-lookup"><span data-stu-id="ca426-153">When you use the `dotnet` command to run an app, add `--` to the end.</span></span> <span data-ttu-id="ca426-154">`--` の右側にあるものは、パラメーターとしてアプリに渡されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-154">Anything to the right of `--` will be passed as a parameter to the app.</span></span> <span data-ttu-id="ca426-155">次の例では、値 `John` がアプリに渡されます。</span><span class="sxs-lookup"><span data-stu-id="ca426-155">In the following example, the value `John` is passed to the app.</span></span>

    ```dotnetcli
    dotnet run -- John
    ```

    <span data-ttu-id="ca426-156">次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="ca426-156">You get the following output.</span></span>

    ```console
    Hello John!
    Fibonacci Numbers 1-15:
    1: 0
    2: 1
    3: 1
    4: 2
    5: 3
    6: 5
    7: 8
    8: 13
    9: 21
    10: 34
    11: 55
    12: 89
    13: 144
    14: 233
    15: 377
    ```

<span data-ttu-id="ca426-157">以上です。</span><span class="sxs-lookup"><span data-stu-id="ca426-157">And that's it!</span></span> <span data-ttu-id="ca426-158">*Program.cs* を自由に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="ca426-158">You can modify *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="ca426-159">複数のファイルの操作</span><span class="sxs-lookup"><span data-stu-id="ca426-159">Working with multiple files</span></span>

<span data-ttu-id="ca426-160">単純な 1 回だけのプログラムには 1 つのファイルで十分ですが、より複雑なアプリを構築する場合は、プロジェクトでおそらく複数のコード ファイルを使用するでしょう。</span><span class="sxs-lookup"><span data-stu-id="ca426-160">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple code files on your project.</span></span> <span data-ttu-id="ca426-161">先のフィボナッチのサンプルから作成してみましょう。いくつかのフィボナッチ値をキャッシュしてから、再帰機能をいくつか追加します。</span><span class="sxs-lookup"><span data-stu-id="ca426-161">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

01. <span data-ttu-id="ca426-162">次のコードを利用し、*FibonacciGenerator.cs* という名前の *Hello* ディレクトリ内に新しいファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca426-162">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. <span data-ttu-id="ca426-163">*Program.cs* ファイルの `Main` メソッドを変更し、次の例のように新しいクラスをインスタンス化し、そのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ca426-163">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. <span data-ttu-id="ca426-164">[dotnet build](../tools/dotnet-build.md) を実行して、変更をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ca426-164">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

04. <span data-ttu-id="ca426-165">[dotnet run](../tools/dotnet-run.md) を実行することで、アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca426-165">Run your app by executing [dotnet run](../tools/dotnet-run.md).</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="ca426-166">次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="ca426-166">You get the following output.</span></span>

    ```console
    0
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55
    89
    144
    233
    377
    ```

## <a name="publish-your-app"></a><span data-ttu-id="ca426-167">アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="ca426-167">Publish your app</span></span>

<span data-ttu-id="ca426-168">アプリを配布する準備ができたら、[dotnet publish](../tools/dotnet-publish.md) コマンドを使用して、_bin\\debug\\netcoreapp3.1\\publish\\_ に _publish_ フォルダーを生成します (Windows 以外のシステムの場合は `/` を使用します)。</span><span class="sxs-lookup"><span data-stu-id="ca426-168">Once you're ready to distribute your app, use the [dotnet publish](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp3.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="ca426-169">dotnet ランタイムが既にインストールされている他のプラットフォームには、_publish_ フォルダーの内容を配布できます。</span><span class="sxs-lookup"><span data-stu-id="ca426-169">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

```dotnetcli
dotnet publish
```

<span data-ttu-id="ca426-170">次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="ca426-170">You get output similar to the following.</span></span>

```console
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

<span data-ttu-id="ca426-171">上記の出力は、現在のフォルダーとオペレーティング システムによって異なっている場合がありますが、出力は似ています。</span><span class="sxs-lookup"><span data-stu-id="ca426-171">The output above may differ based on your current folder and operating system, but the output should be similar.</span></span>

<span data-ttu-id="ca426-172">[dotnet](../tools/dotnet.md) コマンドを使って、発行されたアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca426-172">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```dotnetcli
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll
```

<span data-ttu-id="ca426-173">次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="ca426-173">You get the following output.</span></span>

```console
Hello World!
```

<span data-ttu-id="ca426-174">この記事の冒頭で説明したように、オペレーティング システム固有の実行可能ファイルが `Hello.dll` と共に作成されています。</span><span class="sxs-lookup"><span data-stu-id="ca426-174">As mentioned at the start of this article, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="ca426-175">Windows では、これは `Hello.exe` になります。Linux または macOS では、これは `hello` になります。</span><span class="sxs-lookup"><span data-stu-id="ca426-175">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="ca426-176">上記の例では、ファイルの名前は `Hello.exe` または `Hello` になります。</span><span class="sxs-lookup"><span data-stu-id="ca426-176">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="ca426-177">この発行済みの実行可能ファイルを直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca426-177">You can run this published executable directly.</span></span>

```console
.\bin\Debug\netcoreapp3.1\publish\Hello.exe

Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="ca426-178">まとめ</span><span class="sxs-lookup"><span data-stu-id="ca426-178">Conclusion</span></span>

<span data-ttu-id="ca426-179">以上です。</span><span class="sxs-lookup"><span data-stu-id="ca426-179">And that's it!</span></span> <span data-ttu-id="ca426-180">これで、ここで学習した基本的な概念を利用し、自分だけのプログラムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ca426-180">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca426-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca426-181">See also</span></span>

- [<span data-ttu-id="ca426-182">.NET Core CLI を使用したプロジェクトの整理およびテスト</span><span class="sxs-lookup"><span data-stu-id="ca426-182">Organizing and testing projects with the .NET Core CLI</span></span>](testing-with-cli.md)
- [<span data-ttu-id="ca426-183">.NET Core CLI を使用して .NET Core アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="ca426-183">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="ca426-184">.NET Core アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="ca426-184">.NET Core application deployment</span></span>](../deploying/index.md)
