---
title: .NET Core グローバル ツールの作成方法
description: グローバル ツールを作成する方法について説明します。 グローバル ツールは、.NET Core CLI を介してインストールされるコンソール アプリケーションです。
author: Thraka
ms.author: adegeo
ms.date: 08/22/2018
ms.openlocfilehash: 3d0a64d0473f51d73892cd40633e2982c1130469
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612668"
---
# <a name="create-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="0f236-104">.NET Core CLI を使用して .NET Core グローバル ツールを作成する</span><span class="sxs-lookup"><span data-stu-id="0f236-104">Create a .NET Core Global Tool using the .NET Core CLI</span></span>

<span data-ttu-id="0f236-105">この記事では、.NET Core グローバル ツールを作成してパッケージ化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f236-105">This article teaches you how to create and package a .NET Core Global Tool.</span></span> <span data-ttu-id="0f236-106">.NET Core CLI を使用すると、他のユーザーが簡単にインストールして実行できるコンソール アプリケーションをグローバル ツールとして作成できます。</span><span class="sxs-lookup"><span data-stu-id="0f236-106">The .NET Core CLI allows you to create a console application as a Global Tool, which others can easily install and run.</span></span> <span data-ttu-id="0f236-107">.NET Core グローバル ツールは、.NET Core CLI からインストールされる NuGet パッケージです。</span><span class="sxs-lookup"><span data-stu-id="0f236-107">.NET Core Global Tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="0f236-108">グローバル ツールの詳細については、「[.NET Core グローバル ツールの概要](global-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f236-108">For more information about Global Tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="create-a-project"></a><span data-ttu-id="0f236-109">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="0f236-109">Create a project</span></span>

<span data-ttu-id="0f236-110">この記事では、プロジェクトの作成と管理に .NET Core CLI を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f236-110">This article uses the .NET Core CLI to create and manage a project.</span></span>

<span data-ttu-id="0f236-111">ここでの例のツールは、ASCII ボットを生成してメッセージを出力するコンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="0f236-111">Our example tool will be a console application that generates an ASCII bot and prints a message.</span></span> <span data-ttu-id="0f236-112">まず、新しい .NET Core コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f236-112">First, create a new .NET Core Console Application.</span></span>

```console
dotnet new console -o botsay
```

<span data-ttu-id="0f236-113">前のコマンドで作成した `botsay` ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0f236-113">Navigate to the `botsay` directory created by the previous command.</span></span>

## <a name="add-the-code"></a><span data-ttu-id="0f236-114">コードの追加</span><span class="sxs-lookup"><span data-stu-id="0f236-114">Add the code</span></span>

<span data-ttu-id="0f236-115">`vim` や [Visual Studio Code](https://code.visualstudio.com/) など、使い慣れたテキスト エディターで `Program.cs` ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f236-115">Open the `Program.cs` file with your favorite text editor, such as `vim` or [Visual Studio Code](https://code.visualstudio.com/).</span></span>

<span data-ttu-id="0f236-116">次の `using` ディレクティブをファイルの先頭に追加すると、アプリケーションのバージョン情報を表示するコードを短くすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f236-116">Add the following `using` directive to the top of the file, this helps shorten the code to display the version information of the application.</span></span>

```csharp
using System.Reflection;
```

<span data-ttu-id="0f236-117">次に、`Main` メソッドに移動します。</span><span class="sxs-lookup"><span data-stu-id="0f236-117">Next, move down to the `Main` method.</span></span> <span data-ttu-id="0f236-118">メソッドを次のコードに置き換えて、アプリケーションのコマンドライン引数を処理します。</span><span class="sxs-lookup"><span data-stu-id="0f236-118">Replace the method with the following code to process the command-line arguments for your application.</span></span> <span data-ttu-id="0f236-119">引数が渡されなかった場合、短いヘルプ メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f236-119">If no arguments were passed, a short help message is displayed.</span></span> <span data-ttu-id="0f236-120">それ以外の場合、それらの引数はすべて文字列に変換され、ボットで出力されます。</span><span class="sxs-lookup"><span data-stu-id="0f236-120">Otherwise, all of those arguments are transformed into a string and printed with the bot.</span></span>

```csharp
static void Main(string[] args)
{
    if (args.Length == 0)
    {
        var versionString = Assembly.GetEntryAssembly()
                                .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                .InformationalVersion
                                .ToString();

        Console.WriteLine($"botsay v{versionString}");
        Console.WriteLine("-------------");
        Console.WriteLine("\nUsage:");
        Console.WriteLine("  botsay <message>");
        return;
    }

    ShowBot(string.Join(' ', args));
}
```

### <a name="create-the-bot"></a><span data-ttu-id="0f236-121">ボットを作成する</span><span class="sxs-lookup"><span data-stu-id="0f236-121">Create the bot</span></span>

<span data-ttu-id="0f236-122">次に、文字列パラメーターを受け取る `ShowBot` という新しいメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f236-122">Next, add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="0f236-123">このメソッドは、メッセージと ASCII ボットを出力します。</span><span class="sxs-lookup"><span data-stu-id="0f236-123">This method prints out the message and the ASCII bot.</span></span> <span data-ttu-id="0f236-124">ASCII ボットのコードは、[dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs) サンプルの一部です。</span><span class="sxs-lookup"><span data-stu-id="0f236-124">The ASCII bot code was taken from the [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs) sample.</span></span>

```csharp
static void ShowBot(string message)
{
    string bot = $"\n        {message}";
    bot += @"
    __________________
                      \
                       \
                          ....
                          ....'
                           ....
                        ..........
                    .............'..'..
                 ................'..'.....
               .......'..........'..'..'....
              ........'..........'..'..'.....
             .'....'..'..........'..'.......'.
             .'..................'...   ......
             .  ......'.........         .....
             .    _            __        ......
            ..    #            ##        ......
           ....       .                 .......
           ......  .......          ............
            ................  ......................
            ........................'................
           ......................'..'......    .......
        .........................'..'.....       .......
     ........    ..'.............'..'....      ..........
   ..'..'...      ...............'.......      ..........
  ...'......     ...... ..........  ......         .......
 ...........   .......              ........        ......
.......        '...'.'.              '.'.'.'         ....
.......       .....'..               ..'.....
   ..       ..........               ..'........
          ............               ..............
         .............               '..............
        ...........'..              .'.'............
       ...............              .'.'.............
      .............'..               ..'..'...........
      ...............                 .'..............
       .........                        ..............
        .....
";
    Console.WriteLine(bot);
}
```

### <a name="test-the-tool"></a><span data-ttu-id="0f236-125">ツールをテストする</span><span class="sxs-lookup"><span data-stu-id="0f236-125">Test the tool</span></span>

<span data-ttu-id="0f236-126">プロジェクトを実行して出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="0f236-126">Run the project and see the output.</span></span> <span data-ttu-id="0f236-127">次のようにコマンドラインを変えて、異なる結果を表示してみてください。</span><span class="sxs-lookup"><span data-stu-id="0f236-127">Try these variations of the command-line to see different results:</span></span>

```csharp
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- hello from the bot
```

<span data-ttu-id="0f236-128">区切り記号 `--` の後の引数は、すべてアプリケーションに渡されます。</span><span class="sxs-lookup"><span data-stu-id="0f236-128">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="setup-the-global-tool"></a><span data-ttu-id="0f236-129">グローバル ツールを設定する</span><span class="sxs-lookup"><span data-stu-id="0f236-129">Setup the global tool</span></span>

<span data-ttu-id="0f236-130">アプリケーションをパッケージ化してグローバル ツールとして配布する前に、プロジェクト ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f236-130">Before you can pack and distribute the application as a Global Tool, you need to modify the project file.</span></span> <span data-ttu-id="0f236-131">`botsay.csproj` ファイルを開き、3 つの新しい XML ノードを `<Project><PropertyGroup>` ノードに追加します。</span><span class="sxs-lookup"><span data-stu-id="0f236-131">Open the `botsay.csproj` file and add three new XML nodes to the `<Project><PropertyGroup>` node:</span></span>

- `<PackAsTool>`\
<span data-ttu-id="0f236-132">[必須] アプリケーションがグローバル ツールとしてインストールされるようにパッケージ化されることを示します。</span><span class="sxs-lookup"><span data-stu-id="0f236-132">[REQUIRED] Indicates that the application will be packaged for install as a Global Tool.</span></span>

- `<ToolCommandName>`\
<span data-ttu-id="0f236-133">[省略可能] ツールの代替名。指定しない場合、プロジェクト ファイル名に従ってツールのコマンド名が付けられます。</span><span class="sxs-lookup"><span data-stu-id="0f236-133">[OPTIONAL] An alternative name for the tool, otherwise the command name for the tool will be named after the project file.</span></span> <span data-ttu-id="0f236-134">1 つのパッケージに複数のツールを含めることができます。一意のわかりやすい名前を選択すると、同じパッケージ内の他のツールと区別しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="0f236-134">You can have multiple tools in a package, choosing a unique and friendly name helps differentiate from other tools in the same package.</span></span>

- `<PackageOutputPath>`\
<span data-ttu-id="0f236-135">[省略可能] NuGet パッケージが生成される場所。</span><span class="sxs-lookup"><span data-stu-id="0f236-135">[OPTIONAL] Where the NuGet package will be produced.</span></span> <span data-ttu-id="0f236-136">NuGet パッケージは、.NET Core CLI グローバル ツールがツールのインストールに使用するパッケージです。</span><span class="sxs-lookup"><span data-stu-id="0f236-136">The NuGet package is what the .NET Core CLI Global Tools uses to install your tool.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>

    <PackAsTool>true</PackAsTool>
    <ToolCommandName>botsay</ToolCommandName>
    <PackageOutputPath>./nupkg</PackageOutputPath>

  </PropertyGroup>

</Project>
```

<span data-ttu-id="0f236-137">`<PackageOutputPath>` は省略可能ですが、この例では使用します。</span><span class="sxs-lookup"><span data-stu-id="0f236-137">Even though `<PackageOutputPath>` is optional, use it in this example.</span></span> <span data-ttu-id="0f236-138">必ず `<PackageOutputPath>./nupkg</PackageOutputPath>` を設定してください。</span><span class="sxs-lookup"><span data-stu-id="0f236-138">Make sure you set it: `<PackageOutputPath>./nupkg</PackageOutputPath>`.</span></span>

<span data-ttu-id="0f236-139">次に、アプリケーション用の NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f236-139">Next, create a NuGet package for your application.</span></span>

```console
dotnet pack
```

<span data-ttu-id="0f236-140">`botsay.1.0.0.nupkg` ファイルは、`botsay.csproj` ファイルの `<PackageOutputPath>` XML 値で識別されるフォルダー (この例では `./nupkg` フォルダー) に作成されます。</span><span class="sxs-lookup"><span data-stu-id="0f236-140">The `botsay.1.0.0.nupkg` file is created in the folder identified by the `<PackageOutputPath>` XML value from the `botsay.csproj` file, which in this example is the `./nupkg` folder.</span></span> <span data-ttu-id="0f236-141">これにより、インストールとテストが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="0f236-141">This makes it easy to install and test.</span></span> <span data-ttu-id="0f236-142">ツールを公開する場合は、<https://www.nuget.org> にアップロードしてください。</span><span class="sxs-lookup"><span data-stu-id="0f236-142">When you want to release a tool publicly, upload it to <https://www.nuget.org>.</span></span> <span data-ttu-id="0f236-143">NuGet でツールを使用できるようになると、開発者は [dotnet tool install](dotnet-tool-install.md) コマンドの `--global` オプションを使用してツールのユーザー全体のインストールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0f236-143">Once the tool is available on NuGet, developers can perform a user-wide installation of the tool using the `--global` option of the [dotnet tool install](dotnet-tool-install.md) command.</span></span>

<span data-ttu-id="0f236-144">パッケージを用意できたので、そのパッケージからツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f236-144">Now that you have a package, install the tool from that package:</span></span>

```console
dotnet tool install --global --add-source ./nupkg botsay
```

<span data-ttu-id="0f236-145">`--add-source` パラメーターで、NuGet パッケージの追加のソース フィードとして `./nupkg` フォルダー (ここでは `<PackageOutputPath>` フォルダー) を一時的に使用するように .NET CoreCLI に指示します。</span><span class="sxs-lookup"><span data-stu-id="0f236-145">The `--add-source` parameter tells the .NET Core CLI to temporarily use the `./nupkg` folder (our `<PackageOutputPath>` folder) as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="0f236-146">グローバル ツールのインストールの詳細については、「[.NET Core グローバル ツールの概要](global-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f236-146">For more information about installing Global Tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

<span data-ttu-id="0f236-147">インストールが成功すると、ツールの呼び出しに使用したコマンドとインストールされたバージョンを示す、次の例のようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f236-147">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```
You can invoke the tool using the following command: botsay
Tool 'botsay' (version '1.0.0') was successfully installed.
```

<span data-ttu-id="0f236-148">これで、`botsay` を入力してツールから応答を取得できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0f236-148">You should now be able to type `botsay` and get a response from the tool.</span></span>

> [!NOTE]
> <span data-ttu-id="0f236-149">インストールは成功しても `botsay` コマンドを使用できない場合は、新しい端末を開いて PATH を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f236-149">If the install was successful, but you cannot use the `botsay` command, you may need to open a new terminal to refresh the PATH.</span></span>

## <a name="remove-the-tool"></a><span data-ttu-id="0f236-150">ツールを削除する</span><span class="sxs-lookup"><span data-stu-id="0f236-150">Remove the tool</span></span>

<span data-ttu-id="0f236-151">ツールの実験を完了したら、次のコマンドでツールを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="0f236-151">Once you're done experimenting with the tool, you can remove it with the following command:</span></span>

```console
dotnet tool uninstall -g botsay
```
