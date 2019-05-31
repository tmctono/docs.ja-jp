---
title: dotnet build コマンド
description: dotnet build コマンドは、プロジェクトとそのすべての依存関係をビルドします。
ms.date: 04/24/2019
ms.openlocfilehash: 2e58bace8055ba793bf7a6ca3a51eb20aa689768
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64755217"
---
# <a name="dotnet-build"></a><span data-ttu-id="271df-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="271df-103">dotnet build</span></span>

<span data-ttu-id="271df-104">**この記事の対象: ✓** .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="271df-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="271df-105">name</span><span class="sxs-lookup"><span data-stu-id="271df-105">Name</span></span>

<span data-ttu-id="271df-106">`dotnet build` - プロジェクトとそのすべての依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="271df-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="271df-107">構文</span><span class="sxs-lookup"><span data-stu-id="271df-107">Synopsis</span></span>

```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--nologo] [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="271df-108">説明</span><span class="sxs-lookup"><span data-stu-id="271df-108">Description</span></span>

<span data-ttu-id="271df-109">`dotnet build` コマンドは、プロジェクトとその依存関係をバイナリ セットにビルドします。</span><span class="sxs-lookup"><span data-stu-id="271df-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="271df-110">バイナリには、拡張子が *.dll* である中間言語 (IL) ファイルのプロジェクトのコードと、拡張子が *.pdb* でありデバッグに使われるシンボル ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="271df-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="271df-111">アプリケーションの依存関係を一覧表示する依存関係 JSON ファイル (*\*.deps.json*) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="271df-111">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="271df-112">共有ランタイムと、そのアプリケーションのバージョンを指定する、*\*.runtimeconfig.json* ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="271df-112">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="271df-113">サードパーティ (NuGet のライブラリなど) との依存関係があるプロジェクトの場合、NuGet キャッシュから解決され、プロジェクトのビルドの出力では使うことができません。</span><span class="sxs-lookup"><span data-stu-id="271df-113">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="271df-114">この点を考慮すると、`dotnet build` の生成物は別のコンピューターに転送して実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="271df-114">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="271df-115">これは .NET Framework の動作とは対照的です。 .NET Framework の場合、実行可能なプロジェクト (アプリケーション) をビルドすると、.NET Framework がインストールされている任意のコンピューター上で実行できる出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="271df-115">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="271df-116">.NET Core でも同様の動作にするには、[dotnet publish](dotnet-publish.md) コマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="271df-116">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="271df-117">詳しくは、「[.NET Core アプリケーション展開](../deploying/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="271df-117">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="271df-118">ビルドには *project.assets.json* ファイルが必要です。このファイルには、アプリケーションの依存関係が一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="271df-118">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="271df-119">このファイルは、[`dotnet restore`](dotnet-restore.md) を実行すると作成されます。</span><span class="sxs-lookup"><span data-stu-id="271df-119">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="271df-120">アセット ファイルが配置されていないと、ツールは参照アセンブリを解決できないため、エラーになります。</span><span class="sxs-lookup"><span data-stu-id="271df-120">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="271df-121">.NET Core 1.x SDK の場合、`dotnet build` を実行する前に `dotnet restore` を明示的に実行する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="271df-121">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="271df-122">.NET Core 2.0 SDK 以降では、`dotnet build` を実行すると、`dotnet restore` が暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="271df-122">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="271df-123">ビルド コマンドの実行時に暗黙的な復元を無効にする場合は、`--no-restore` オプションを渡します。</span><span class="sxs-lookup"><span data-stu-id="271df-123">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="271df-124">プロジェクトを実行できるかどうかは、プロジェクト ファイルの `<OutputType>` プロパティで決まります。</span><span class="sxs-lookup"><span data-stu-id="271df-124">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="271df-125">次の例は、実行可能なコードを生成するプロジェクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="271df-125">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="271df-126">ライブラリを生成するには、`<OutputType>` プロパティを省略します。</span><span class="sxs-lookup"><span data-stu-id="271df-126">To produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="271df-127">ビルドされる出力の主な違いは、ライブラリの IL DLL にはエントリ ポイントが含まれず、実行できないことです。</span><span class="sxs-lookup"><span data-stu-id="271df-127">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="271df-128">MSBuild</span><span class="sxs-lookup"><span data-stu-id="271df-128">MSBuild</span></span>

<span data-ttu-id="271df-129">`dotnet build` では MSBuild を使用してプロジェクトをビルドするため、並列ビルドとインクリメンタル ビルドの両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="271df-129">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="271df-130">詳しくは、「[インクリメンタル ビルド](/visualstudio/msbuild/incremental-builds)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="271df-130">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="271df-131">このオプションに加え、`dotnet build` コマンドは、プロパティを設定する `-p` やロガーを定義する `-l` などの MSBuild オプションも受け入れます。</span><span class="sxs-lookup"><span data-stu-id="271df-131">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="271df-132">これらのオプションの詳細については、「[MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="271df-132">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="271df-133">また、[dotnet msbuild](dotnet-msbuild.md) コマンドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="271df-133">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="271df-134">`dotnet build` の実行は `dotnet msbuild -restore -target:Build` と同じです。</span><span class="sxs-lookup"><span data-stu-id="271df-134">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="271df-135">引数</span><span class="sxs-lookup"><span data-stu-id="271df-135">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="271df-136">ビルドするプロジェクトまたはソリューションのファイル。</span><span class="sxs-lookup"><span data-stu-id="271df-136">The project or solution file to build.</span></span> <span data-ttu-id="271df-137">プロジェクトまたはソリューションのファイルを指定しない場合、MSBuild は、現在の作業ディレクトリから *proj* または *sln* のどちらかで終わるファイル拡張子を持つファイルを検索して、そのファイルを使います。</span><span class="sxs-lookup"><span data-stu-id="271df-137">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="271df-138">オプション</span><span class="sxs-lookup"><span data-stu-id="271df-138">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="271df-139">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="271df-139">Defines the build configuration.</span></span> <span data-ttu-id="271df-140">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="271df-140">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="271df-141">特定の[フレームワーク](../../standard/frameworks.md)用にコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="271df-141">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="271df-142">フレームワークは、[プロジェクト ファイル](csproj.md)で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="271df-142">The framework must be defined in the [project file](csproj.md).</span></span>

* **`--force`**

  <span data-ttu-id="271df-143">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="271df-143">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="271df-144">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="271df-144">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="271df-145">.NET Core 2.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="271df-145">Available since .NET Core 2.0 SDK.</span></span>

* **`-h|--help`**

  <span data-ttu-id="271df-146">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="271df-146">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="271df-147">コマンドを停止して、ユーザーの入力または操作のために待機させることができます。</span><span class="sxs-lookup"><span data-stu-id="271df-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="271df-148">たとえば、認証を完了する場合があります。</span><span class="sxs-lookup"><span data-stu-id="271df-148">For example, to complete authentication.</span></span> <span data-ttu-id="271df-149">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="271df-149">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="271df-150">プロジェクト間 (P2P) 参照を無視し、指定されたルート プロジェクトのみをビルドします。</span><span class="sxs-lookup"><span data-stu-id="271df-150">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="271df-151">インクリメンタル ビルドとして安全でないビルドをマークします。</span><span class="sxs-lookup"><span data-stu-id="271df-151">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="271df-152">このフラグにより、インクリメンタル コンパイルは無効になり、プロジェクトの依存関係グラフのクリーン再ビルドが強制的に行われます。</span><span class="sxs-lookup"><span data-stu-id="271df-152">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`--no-logo`**

  <span data-ttu-id="271df-153">著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="271df-153">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="271df-154">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="271df-154">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-restore`**

  <span data-ttu-id="271df-155">ビルド時に暗黙的な復元は実行されません。</span><span class="sxs-lookup"><span data-stu-id="271df-155">Doesn't execute an implicit restore during build.</span></span> <span data-ttu-id="271df-156">.NET Core 2.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="271df-156">Available since .NET Core 2.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="271df-157">ビルド済みバイナリを配置するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="271df-157">Directory in which to place the built binaries.</span></span> <span data-ttu-id="271df-158">このオプションを指定する場合は、`--framework` を定義する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="271df-158">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="271df-159">指定しない場合、既定のパスは `./bin/<configuration>/<framework>/` になります。</span><span class="sxs-lookup"><span data-stu-id="271df-159">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="271df-160">ターゲットのランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="271df-160">Specifies the target runtime.</span></span> <span data-ttu-id="271df-161">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="271df-161">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="271df-162">MSBuild の詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="271df-162">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="271df-163">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="271df-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="271df-164">既定値は、`minimal` です。</span><span class="sxs-lookup"><span data-stu-id="271df-164">The default is `minimal`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="271df-165">プロジェクトをビルドするときに使用する `$(VersionSuffix)` プロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="271df-165">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="271df-166">これは、`$(Version)` プロパティが設定されていない場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="271df-166">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="271df-167">次に、`$(Version)` には、ダッシュで区切り `$(VersionSuffix)` と組み合わせた `$(VersionPrefix)` が設定されます。</span><span class="sxs-lookup"><span data-stu-id="271df-167">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="271df-168">使用例</span><span class="sxs-lookup"><span data-stu-id="271df-168">Examples</span></span>

* <span data-ttu-id="271df-169">プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="271df-169">Build a project and its dependencies:</span></span>

  ```console
  dotnet build
  ```

* <span data-ttu-id="271df-170">リリース構成を使用して、プロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="271df-170">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet build --configuration Release
  ```

* <span data-ttu-id="271df-171">特定のランタイム (この例では、Ubuntu 18.04) 用にプロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="271df-171">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```console
  dotnet build --runtime ubuntu.18.04-x64
  ```

* <span data-ttu-id="271df-172">プロジェクトをビルドし、復元操作中に指定された NuGet パッケージ ソースを使用します (.NET Core 2.0 SDK 以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="271df-172">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```console
  dotnet build --source c:\packages\mypackages
  ```

* <span data-ttu-id="271df-173">プロジェクトをビルドし、ビルド パラメーターに 1.2.3.4 バージョンを設定します。</span><span class="sxs-lookup"><span data-stu-id="271df-173">Build the project and set 1.2.3.4 version as a build parameter:</span></span>

  ```console
  dotnet build -p:Version=1.2.3.4
  ```