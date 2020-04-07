---
title: dotnet publish コマンド
description: dotnet publish コマンドを実行すると、.NET Core プロジェクトまたはソリューションをディレクトリに発行できます。
ms.date: 02/24/2020
ms.openlocfilehash: 0e18220443f3713c86c257fcf401b98ddd716ebc
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588268"
---
# <a name="dotnet-publish"></a><span data-ttu-id="72d23-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="72d23-103">dotnet publish</span></span>

<span data-ttu-id="72d23-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="72d23-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="72d23-105">名前</span><span class="sxs-lookup"><span data-stu-id="72d23-105">Name</span></span>

<span data-ttu-id="72d23-106">`dotnet publish` - ホスティング システムへの展開のため、アプリケーションとその依存関係をフォルダーに発行します。</span><span class="sxs-lookup"><span data-stu-id="72d23-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="72d23-107">構文</span><span class="sxs-lookup"><span data-stu-id="72d23-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="72d23-108">説明</span><span class="sxs-lookup"><span data-stu-id="72d23-108">Description</span></span>

<span data-ttu-id="72d23-109">`dotnet publish` はアプリケーションをコンパイルし、プロジェクト ファイルに指定されたその依存関係を読み取り、結果のファイル セットをディレクトリに発行します。</span><span class="sxs-lookup"><span data-stu-id="72d23-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="72d23-110">出力には次のアセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="72d23-110">The output includes the following assets:</span></span>

- <span data-ttu-id="72d23-111">アセンブリの中間言語 (IL) コード (*dll* 拡張子)。</span><span class="sxs-lookup"><span data-stu-id="72d23-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="72d23-112">*.deps.json* ファイル。プロジェクトのすべての依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="72d23-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="72d23-113">*.runtimeconfig.json* ファイル。アプリケーションが想定する共有ランタイムと、ランタイム用の他の構成オプション (ガベージ コレクションの種類など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="72d23-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="72d23-114">アプリケーションの依存関係。NuGet キャッシュから出力フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="72d23-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="72d23-115">`dotnet publish` コマンドの出力は、実行のためにホスト システム (サーバー、PC、Mac、ラップトップなど) にすぐに展開できます。</span><span class="sxs-lookup"><span data-stu-id="72d23-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="72d23-116">これは、アプリケーションの展開を準備するための正式にサポートされている唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="72d23-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="72d23-117">プロジェクトに指定されている展開の種類によっては、ホスティング システムに .NET Core 共有ランタイムがインストールされている場合とされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="72d23-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="72d23-118">詳細については、「[.NET Core CLI を使用して .NET Core アプリを発行する](../deploying/deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72d23-118">For more information, see [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

### <a name="msbuild"></a><span data-ttu-id="72d23-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="72d23-119">MSBuild</span></span>

<span data-ttu-id="72d23-120">`dotnet publish` コマンドは、`Publish` ターゲットを呼び出す MSBuild を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="72d23-120">The `dotnet publish` command calls MSBuild, which invokes the `Publish` target.</span></span> <span data-ttu-id="72d23-121">`dotnet publish` に渡されたすべてのパラメーターが MSBuild に渡されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-121">Any parameters passed to `dotnet publish` are passed to MSBuild.</span></span> <span data-ttu-id="72d23-122">`-c` と `-o` のパラメーターは、それぞれ MSBuild の `Configuration` と `OutputPath` にマップします。</span><span class="sxs-lookup"><span data-stu-id="72d23-122">The `-c` and `-o` parameters map to MSBuild's `Configuration` and `OutputPath` properties, respectively.</span></span>

<span data-ttu-id="72d23-123">`dotnet publish` コマンドは、プロパティを設定する `-p` やロガーを定義する `-l` などの MSBuild オプションも受け入れます。</span><span class="sxs-lookup"><span data-stu-id="72d23-123">The `dotnet publish` command accepts MSBuild options, such as `-p` for setting properties and `-l` to define a logger.</span></span> <span data-ttu-id="72d23-124">たとえば、`-p:<NAME>=<VALUE>` という形式を使用して、MSBuild プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="72d23-124">For example, you can set an MSBuild property by using the format: `-p:<NAME>=<VALUE>`.</span></span> <span data-ttu-id="72d23-125">また、 *.pubxml* ファイルを参照することで、公開関連のプロパティを設定することもできます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="72d23-125">You can also set publish-related properties by referring to a *.pubxml* file, for example:</span></span>

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

<span data-ttu-id="72d23-126">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72d23-126">For more information, see the following resources:</span></span>

- [<span data-ttu-id="72d23-127">MSBuild コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="72d23-127">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="72d23-128">ASP.NET Core アプリを配置するための Visual Studio 発行プロファイル (.pubxml)</span><span class="sxs-lookup"><span data-stu-id="72d23-128">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="72d23-129">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="72d23-129">dotnet msbuild</span></span>](dotnet-msbuild.md)

## <a name="arguments"></a><span data-ttu-id="72d23-130">引数</span><span class="sxs-lookup"><span data-stu-id="72d23-130">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="72d23-131">発行するプロジェクトまたはソリューション。</span><span class="sxs-lookup"><span data-stu-id="72d23-131">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="72d23-132">`PROJECT` は、[C#](csproj.md)、F#、または Visual Basic のプロジェクト ファイルのパスおよびファイル名か、C#、F#、または Visual Basic のプロジェクト ファイルを含むディレクトリへのパスです。</span><span class="sxs-lookup"><span data-stu-id="72d23-132">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="72d23-133">ディレクトリが指定されていない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-133">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="72d23-134">`SOLUTION` は、ソリューション ファイルのパスとファイル名 ( *.sln* 拡張子)、またはソリューション ファイルを含むディレクトリのパスです。</span><span class="sxs-lookup"><span data-stu-id="72d23-134">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="72d23-135">ディレクトリが指定されていない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-135">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="72d23-136">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="72d23-136">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="72d23-137">オプション</span><span class="sxs-lookup"><span data-stu-id="72d23-137">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="72d23-138">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="72d23-138">Defines the build configuration.</span></span> <span data-ttu-id="72d23-139">ほとんどのプロジェクトの既定値は `Debug` ですが、プロジェクトでビルド構成設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="72d23-139">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="72d23-140">指定した[ターゲット フレームワーク](../../standard/frameworks.md)のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="72d23-140">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="72d23-141">ターゲット フレームワークはプロジェクト ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72d23-141">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="72d23-142">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="72d23-143">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="72d23-143">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="72d23-144">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="72d23-144">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="72d23-145">コマンドを停止して、ユーザーの入力または操作のために待機させることができます。</span><span class="sxs-lookup"><span data-stu-id="72d23-145">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="72d23-146">たとえば、認証を完了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="72d23-146">For example, to complete authentication.</span></span> <span data-ttu-id="72d23-147">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="72d23-147">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="72d23-148">アプリによって公開された一連のパッケージをトリミングするために使用する[ターゲット マニフェスト](../deploying/runtime-store.md)を 1 つまたは複数指定します。</span><span class="sxs-lookup"><span data-stu-id="72d23-148">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="72d23-149">マニフェスト ファイルは、[`dotnet store` コマンド](dotnet-store.md)の出力の一部です。</span><span class="sxs-lookup"><span data-stu-id="72d23-149">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="72d23-150">複数のマニフェストを指定するには、マニフェストごとに `--manifest` を追加します。</span><span class="sxs-lookup"><span data-stu-id="72d23-150">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="72d23-151">発行の前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="72d23-151">Doesn't build the project before publishing.</span></span> <span data-ttu-id="72d23-152">また、`--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-152">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="72d23-153">プロジェクト間参照を無視し、ルート プロジェクトのみを復元します。</span><span class="sxs-lookup"><span data-stu-id="72d23-153">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="72d23-154">著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="72d23-154">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="72d23-155">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="72d23-155">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="72d23-156">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="72d23-156">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="72d23-157">出力ディレクトリのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="72d23-157">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="72d23-158">指定しない場合、ランタイムに依存する実行可能ファイルおよびクロスプラットフォーム バイナリの既定値は *[project_file_folder]./bin/[configuration]/[framework]/publish/* に設定されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-158">If not specified, it defaults to *[project_file_folder]./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="72d23-159">自己完結型の実行可能ファイルの場合、既定値は *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* に設定されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-159">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  - <span data-ttu-id="72d23-160">.NET Core 3.x SDK 以降</span><span class="sxs-lookup"><span data-stu-id="72d23-160">.NET Core 3.x SDK and later</span></span>
  
    <span data-ttu-id="72d23-161">プロジェクトの発行時に相対パスが指定された場合、生成された出力ディレクトリは、プロジェクト ファイルの場所ではなく、現在の作業ディレクトリに相対的なパスとなります。</span><span class="sxs-lookup"><span data-stu-id="72d23-161">If a relative path is specified when publishing a project, the output directory generated is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="72d23-162">ソリューションの発行時に相対パスが指定されている場合、すべてのプロジェクトに対する出力はすべて、現在の作業ディレクトリと相対的な指定されたフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-162">If a relative path is specified when publishing a solution, all output for all projects go into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="72d23-163">発行の出力が各プロジェクトの個別のフォルダーに移動されるようにするには、`--output` オプションの代わりに、msbuild `PublishDir` プロパティを使用して相対パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="72d23-163">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="72d23-164">たとえば、`dotnet publish -p:PublishDir=.\publish` を使用すると、プロジェクト ファイルが格納されているフォルダーの下にある `publish` フォルダーに、各プロジェクトの発行の出力が送信されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-164">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="72d23-165">.NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="72d23-165">.NET Core 2.x SDK</span></span>
  
    <span data-ttu-id="72d23-166">プロジェクトの発行時に相対パスが指定された場合、生成された出力ディレクトリは、現在の作業ディレクトリではなく、プロジェクト ファイルの場所に相対的なパスとなります。</span><span class="sxs-lookup"><span data-stu-id="72d23-166">If a relative path is specified when publishing a project, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="72d23-167">ソリューションの発行時に相対パスを指定すると、各プロジェクトの出力は、プロジェクト ファイルの場所に相対的な別のフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-167">If a relative path is specified when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="72d23-168">ソリューションの発行時に絶対パスを指定すると、すべてのプロジェクトに対する発行の出力はすべて、指定されたフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-168">If an absolute path is specified when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="72d23-169">アプリケーションと一緒に .NET Core ランタイムを発行します。これにより、ランタイムをターゲット コンピューターにインストールする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="72d23-169">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="72d23-170">ランタイム識別子が指定され、プロジェクトが (ライブラリ プロジェクトではなく) 実行可能なプロジェクトである場合、既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="72d23-170">Default is `true` if a runtime identifier is specified and the project is an executable project (not a library project).</span></span> <span data-ttu-id="72d23-171">詳細については、[.NET Core アプリケーションの発行](../deploying/index.md)に関する記事と「[.NET Core CLI を使用して .NET Core アプリを発行する](../deploying/deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72d23-171">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

  <span data-ttu-id="72d23-172">`true` または `false` を指定せずに、このオプションを使用した場合、既定値は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="72d23-172">If this option is used without specifying `true` or `false`, the default is `true`.</span></span> <span data-ttu-id="72d23-173">その場合は、その位置で `true` または `false` が想定されているため、`--self-contained` の直後にソリューションまたはプロジェクト引数を配置しないでください。</span><span class="sxs-lookup"><span data-stu-id="72d23-173">In that case, don't put the solution or project argument immediately after `--self-contained`, because `true` or `false` is expected in that position.</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="72d23-174">これは、`--self-contained false` に相当します。</span><span class="sxs-lookup"><span data-stu-id="72d23-174">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="72d23-175">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="72d23-175">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="72d23-176">指定されたランタイムのアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="72d23-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="72d23-177">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="72d23-177">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="72d23-178">詳細については、[.NET Core アプリケーションの発行](../deploying/index.md)に関する記事と「[.NET Core CLI を使用して .NET Core アプリを発行する](../deploying/deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72d23-178">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="72d23-179">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="72d23-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="72d23-180">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="72d23-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="72d23-181">既定値は `minimal`にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72d23-181">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="72d23-182">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) を置き換えるバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="72d23-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="72d23-183">使用例</span><span class="sxs-lookup"><span data-stu-id="72d23-183">Examples</span></span>

- <span data-ttu-id="72d23-184">現在のディレクトリ内にプロジェクト用の[ランタイムに依存するクロスプラットフォーム バイナリ](../deploying/index.md#produce-a-cross-platform-binary)を作成します。</span><span class="sxs-lookup"><span data-stu-id="72d23-184">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="72d23-185">.NET Core 3.0 SDK 以降の場合、この例では、現在のプラットフォーム用の[ランタイムに依存する実行可能ファイル](../deploying/index.md#publish-runtime-dependent)も作成されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-185">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="72d23-186">特定のランタイムに対して、現在のディレクトリ内にプロジェクト用の[自己完結型の実行可能ファイル](../deploying/index.md#publish-self-contained)を作成します。</span><span class="sxs-lookup"><span data-stu-id="72d23-186">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="72d23-187">RID をプロジェクト ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="72d23-187">The RID must be in the project file.</span></span>

- <span data-ttu-id="72d23-188">特定のプラットフォーム用に、プロジェクト用の[ランタイムに依存する実行可能ファイル](../deploying/index.md#publish-runtime-dependent)を現在のディレクトリに作成します。</span><span class="sxs-lookup"><span data-stu-id="72d23-188">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="72d23-189">RID をプロジェクト ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="72d23-189">The RID must be in the project file.</span></span> <span data-ttu-id="72d23-190">この例は、.NET Core 3.0 SDK 以降のバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="72d23-190">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="72d23-191">特定のランタイムとターゲット フレームワーク用に、現在のディレクトリのプロジェクトを発行します。</span><span class="sxs-lookup"><span data-stu-id="72d23-191">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="72d23-192">指定されたプロジェクト ファイルを発行します。</span><span class="sxs-lookup"><span data-stu-id="72d23-192">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="72d23-193">現在のアプリケーションを発行します。ただし、復元操作中はルート プロジェクトのみを復元し、プロジェクト間 (P2P) 参照は復元しないでください。</span><span class="sxs-lookup"><span data-stu-id="72d23-193">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="72d23-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="72d23-194">See also</span></span>

- [<span data-ttu-id="72d23-195">.NET Core アプリケーションの発行の概要</span><span class="sxs-lookup"><span data-stu-id="72d23-195">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="72d23-196">.NET Core CLI を使用して .NET Core アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="72d23-196">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="72d23-197">ターゲット フレームワーク</span><span class="sxs-lookup"><span data-stu-id="72d23-197">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="72d23-198">ランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="72d23-198">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="72d23-199">macOS Catalina の公証に対応する</span><span class="sxs-lookup"><span data-stu-id="72d23-199">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- [<span data-ttu-id="72d23-200">発行されたアプリケーションのディレクトリ構造</span><span class="sxs-lookup"><span data-stu-id="72d23-200">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
- [<span data-ttu-id="72d23-201">MSBuild コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="72d23-201">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="72d23-202">ASP.NET Core アプリを配置するための Visual Studio 発行プロファイル (.pubxml)</span><span class="sxs-lookup"><span data-stu-id="72d23-202">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="72d23-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="72d23-203">dotnet msbuild</span></span>](dotnet-msbuild.md)
