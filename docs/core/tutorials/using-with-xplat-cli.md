---
title: CLI を使用する .NET Core に関する概要
description: Windows、Linux、または macOS の .NET Core での、.NET Core コマンド ライン インターフェイス (CLI) の使用方法を段階的に説明するチュートリアル。
author: thraka
ms.author: adegeo
ms.date: 08/07/2019
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: 88e9501a776a026a311c5002674c15acf2324f2b
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868589"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="a8a4d-103">Windows/Linux/macOS の .NET Core でのコマンド ラインの使用に関する概要</span><span class="sxs-lookup"><span data-stu-id="a8a4d-103">Get started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="a8a4d-104">このトピックでは、.NET Core CLI ツールを利用し、自分のコンピューターでプラットフォームに依存しないアプリを開発する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-104">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="a8a4d-105">.NET Core CLI ツールセットに慣れていない場合は、「[.NET Core SDK overview](../tools/index.md)」(.NET Core SDK の概要) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8a4d-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a8a4d-106">Prerequisites</span></span>

- <span data-ttu-id="a8a4d-107">[.NET Core SDK 2.1](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="a8a4d-107">[.NET Core SDK 2.1](https://www.microsoft.com/net/download/core).</span></span>
- <span data-ttu-id="a8a4d-108">ユーザーが選んだテキスト エディターまたはコード エディター。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="a8a4d-109">Hello コンソール アプリ</span><span class="sxs-lookup"><span data-stu-id="a8a4d-109">Hello, Console App!</span></span>

<span data-ttu-id="a8a4d-110">GitHub の dotnet/samples レポジトリから、[サンプル コードを表示またはダウンロード](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild)することができます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="a8a4d-111">ダウンロード方法については、「[サンプルおよびチュートリアル](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="a8a4d-112">コマンド プロンプトを開き、*Hello* という名前のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="a8a4d-113">作成したフォルダーに移動して、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-113">Navigate to the folder you created and type the following:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="a8a4d-114">簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-114">Let's do a quick walkthrough:</span></span>

1. `dotnet new console`

   <span data-ttu-id="a8a4d-115">[`dotnet new`](../tools/dotnet-new.md) は、コンソール アプリのビルドに必要な依存関係を含む最新の `Hello.csproj` プロジェクト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-115">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="a8a4d-116">また、アプリケーションのエントリ ポイントを含む基本的なファイルである `Program.cs` も作成します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-116">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="a8a4d-117">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="a8a4d-117">`Hello.csproj`:</span></span>

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   <span data-ttu-id="a8a4d-118">プロジェクト ファイルでは、依存関係を復元し、プログラムをビルドするために必要なすべてのものを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="a8a4d-119">`OutputType` タグは、実行可能ファイル (つまり、コンソール アプリケーション) をビルドすることを示します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-119">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="a8a4d-120">`TargetFramework` タグは、対象の .NET 実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-120">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="a8a4d-121">高度なシナリオでは、複数の対象フレームワークを指定し、1 回の操作でそれらすべてにビルドすることができます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="a8a4d-122">このチュートリアルでは、.NET Core 2.1 の場合のビルドについてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-122">In this tutorial, we'll stick to building only for .NET Core 2.1.</span></span>

   <span data-ttu-id="a8a4d-123">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="a8a4d-123">`Program.cs`:</span></span>

   [!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]

   <span data-ttu-id="a8a4d-124">プログラムは `using System` で始まります。これは、"`System` 名前空間のすべてがこのファイルのスコープになる" こと意味します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="a8a4d-125">`System` 名前空間には、`string` などの基本的な構造、または数値型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-125">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="a8a4d-126">次に、`Hello` という名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="a8a4d-127">これを必要なものに変更できます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-127">You can change this to anything you want.</span></span> <span data-ttu-id="a8a4d-128">`Program` という名前のクラスは、引数として文字列配列を使用する `Main` メソッドで、その名前空間内に定義されます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="a8a4d-129">この配列には、コンパイル済みプログラムの呼び出し時に渡される引数のリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-129">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="a8a4d-130">実際は、この配列は使用されません。プログラムはコンソールに "Hello World!" と</span><span class="sxs-lookup"><span data-stu-id="a8a4d-130">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="a8a4d-131">記述するだけです。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-131">to the console.</span></span> <span data-ttu-id="a8a4d-132">後に、この引数を利用するようにコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   <span data-ttu-id="a8a4d-133">`dotnet new` は [`dotnet restore`](../tools/dotnet-restore.md) を暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-133">`dotnet new` calls [`dotnet restore`](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="a8a4d-134">`dotnet restore` は、[NuGet](https://www.nuget.org/) (.NET パッケージ マネージャー) を呼び出して依存関係ツリーを復元します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="a8a4d-135">NuGet は、*Hello.csproj* ファイルを分析し、ファイルに記載されている依存関係をダウンロードし (またはコンピューターのキャッシュから取得し)、サンプルをコンパイルして実行するために必要な *obj/project.assets.json* ファイルを記述します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a8a4d-136">.NET Core 1.x バージョンの SDK を使用している場合は、`dotnet new` の呼び出し後に `dotnet restore` を自分で呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-136">If you're using a .NET Core 1.x version of the SDK, you'll have to call `dotnet restore` yourself after calling `dotnet new`.</span></span>

2. `dotnet run`

   <span data-ttu-id="a8a4d-137">[`dotnet run`](../tools/dotnet-run.md) は、[`dotnet build`](../tools/dotnet-build.md) を呼び出してビルド ターゲットがビルドされていることを確認した後、`dotnet <assembly.dll>` を呼び出してターゲット アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-137">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```console
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="a8a4d-138">[`dotnet build`](../tools/dotnet-build.md) を実行し、ビルド コンソール アプリケーションを実行しないでコードをコンパイルすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-138">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="a8a4d-139">これで、Windows で `dotnet bin\Debug\netcoreapp2.1\Hello.dll` を使用して (Windows 以外のシステムの場合は `/` を使用して) 実行できる DLL ファイルとしてアプリケーションがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-139">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp2.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="a8a4d-140">アプリケーションには引数を指定することもできます。それについてはこのトピックの後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-140">You may also specify arguments to the application as you'll see later on the topic.</span></span>

    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="a8a4d-141">高度なシナリオでは、展開可能なプラットフォーム固有のファイルの自己完結型セットとしてアプリケーションをビルドし、.NET Core が必ずしもインストールされているとは限らないコンピューターに対して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-141">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="a8a4d-142">詳細については、「[.NET Core アプリケーション展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-142">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="a8a4d-143">プログラムの拡張</span><span class="sxs-lookup"><span data-stu-id="a8a4d-143">Augmenting the program</span></span>

<span data-ttu-id="a8a4d-144">プログラムを少し変更してみましょう。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-144">Let's change the program a bit.</span></span> <span data-ttu-id="a8a4d-145">フィボナッチ数は面白いです。アプリを実行した人に挨拶をする引数を使用するためにフィボナッチ数も追加しましょう。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-145">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="a8a4d-146">*Program.cs* ファイルの内容を次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-146">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. <span data-ttu-id="a8a4d-147">[`dotnet build`](../tools/dotnet-build.md) を実行し、変更内容をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-147">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="a8a4d-148">アプリにパラメーターを渡すプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-148">Run the program passing a parameter to the app:</span></span>

   ```console
   $ dotnet run -- John
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

<span data-ttu-id="a8a4d-149">以上です。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-149">And that's it!</span></span>  <span data-ttu-id="a8a4d-150">自由に `Program.cs` を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-150">You can augment `Program.cs` any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="a8a4d-151">複数のファイルの操作</span><span class="sxs-lookup"><span data-stu-id="a8a4d-151">Working with multiple files</span></span>

<span data-ttu-id="a8a4d-152">単純な 1 回だけのプログラムには 1 つのファイルで十分ですが、より複雑なアプリをビルドする場合、プロジェクトに複数のソース ファイルを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-152">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project.</span></span>
<span data-ttu-id="a8a4d-153">先のフィボナッチのサンプルから作成してみましょう。いくつかのフィボナッチ値をキャッシュしてから、再帰機能をいくつか追加します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-153">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

1. <span data-ttu-id="a8a4d-154">次のコードを利用し、*FibonacciGenerator.cs* という名前の *Hello* ディレクトリ内に新しいファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-154">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   [!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. <span data-ttu-id="a8a4d-155">*Program.cs* ファイルの `Main` メソッドを変更し、次の例のように新しいクラスをインスタンス化し、そのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-155">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   [!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. <span data-ttu-id="a8a4d-156">[`dotnet build`](../tools/dotnet-build.md) を実行し、変更内容をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-156">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="a8a4d-157">[`dotnet run`](../tools/dotnet-run.md) を実行し、アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-157">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="a8a4d-158">プログラムの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-158">The following shows the program output:</span></span>

   ```console
   $ dotnet run
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

## <a name="publish-your-app"></a><span data-ttu-id="a8a4d-159">アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="a8a4d-159">Publish your app</span></span>

<span data-ttu-id="a8a4d-160">アプリを配布する準備ができたら、[`dotnet publish`](../tools/dotnet-publish.md) コマンドを使って、_bin\\debug\\netcoreapp2.1\\publish\\_ に _publish_ フォルダーを生成します (Windows 以外のシステムの場合は `/` を使います)。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-160">Once you're ready to distribute your app, use the [`dotnet publish`](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp2.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="a8a4d-161">dotnet ランタイムが既にインストールされている他のプラットフォームには、_publish_ フォルダーの内容を配布できます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-161">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

<span data-ttu-id="a8a4d-162">[dotnet](../tools/dotnet.md) コマンドを使って、発行されたアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-162">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```console
$ dotnet bin\Debug\netcoreapp2.1\publish\Hello.dll
Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="a8a4d-163">まとめ</span><span class="sxs-lookup"><span data-stu-id="a8a4d-163">Conclusion</span></span>

<span data-ttu-id="a8a4d-164">以上です。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-164">And that's it!</span></span> <span data-ttu-id="a8a4d-165">これで、ここで学習した基本的な概念を利用し、自分だけのプログラムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a8a4d-165">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8a4d-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8a4d-166">See also</span></span>

- [<span data-ttu-id="a8a4d-167">.NET Core CLI ツールを使用したプロジェクトの整理およびテスト</span><span class="sxs-lookup"><span data-stu-id="a8a4d-167">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)
- [<span data-ttu-id="a8a4d-168">CLI を使用して .NET Core アプリを公開する</span><span class="sxs-lookup"><span data-stu-id="a8a4d-168">Publish .NET Core apps with the CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="a8a4d-169">アプリの展開についてさらに学習する</span><span class="sxs-lookup"><span data-stu-id="a8a4d-169">Learn more about app deployment</span></span>](../deploying/index.md)
