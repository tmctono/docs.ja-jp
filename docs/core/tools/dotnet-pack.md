---
title: dotnet pack コマンド
description: dotnet pack コマンドでは、.NET Core プロジェクトの NuGet パッケージを作成します。
ms.date: 08/08/2019
ms.openlocfilehash: 99dd8e35601f82adf2a3101121028f191a4c3da4
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117649"
---
# <a name="dotnet-pack"></a><span data-ttu-id="a9f56-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="a9f56-103">dotnet pack</span></span>

<span data-ttu-id="a9f56-104">**このトピックの対象: ✓** .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="a9f56-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="a9f56-105">name</span><span class="sxs-lookup"><span data-stu-id="a9f56-105">Name</span></span>

<span data-ttu-id="a9f56-106">`dotnet pack` - NuGet パッケージにコードをパックします。</span><span class="sxs-lookup"><span data-stu-id="a9f56-106">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a9f56-107">構文</span><span class="sxs-lookup"><span data-stu-id="a9f56-107">Synopsis</span></span>

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--interactive] 
    [--no-build] [--no-dependencies] [--no-restore] [--nologo] [-o|--output] [--runtime] [-s|--serviceable] 
    [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

## <a name="description"></a><span data-ttu-id="a9f56-108">説明</span><span class="sxs-lookup"><span data-stu-id="a9f56-108">Description</span></span>

<span data-ttu-id="a9f56-109">`dotnet pack` コマンドはプロジェクトをビルドし、NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="a9f56-110">このコマンドの結果が NuGet パッケージ (つまり、 *.nupkg* ファイル) です。</span><span class="sxs-lookup"><span data-stu-id="a9f56-110">The result of this command is a NuGet package (that is, a *.nupkg* file).</span></span> 

<span data-ttu-id="a9f56-111">デバッグ シンボルを含むパッケージを生成する場合、使用可能なオプションが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="a9f56-111">If you want to generate a package that contains the debug symbols, you have two options available:</span></span>

- <span data-ttu-id="a9f56-112">`--include-symbols` -シンボル パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-112">`--include-symbols` - it creates the symbols package.</span></span>
- <span data-ttu-id="a9f56-113">`--include-source` -ソース ファイルが含まれた `src` フォルダーを含むシンボル パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-113">`--include-source` - it creates the symbols package with a `src` folder inside containing the source files.</span></span>

<span data-ttu-id="a9f56-114">パックされるプロジェクトの NuGet 依存関係が *.nuspec* ファイルに追加されるため、パッケージのインストール時に適切に解決されます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-114">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="a9f56-115">プロジェクト間参照はプロジェクト内にはパッケージ化されません。</span><span class="sxs-lookup"><span data-stu-id="a9f56-115">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="a9f56-116">現時点では、プロジェクト間の依存関係がある場合は、プロジェクトごとにパッケージが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a9f56-116">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="a9f56-117">既定では、`dotnet pack` は最初にプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a9f56-117">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="a9f56-118">この動作を避けたい場合は、`--no-build` オプションを渡します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-118">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="a9f56-119">このオプションは、コードが既にビルドされていることがわかっている場合の継続的インテグレーション (CI) ビルド シナリオで役立つことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="a9f56-119">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="a9f56-120">パッキング プロセスのために `dotnet pack` コマンドに MSBuild のプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-120">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="a9f56-121">詳細については、「[NuGet メタデータ プロパティ](csproj.md#nuget-metadata-properties)」と「[MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9f56-121">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="a9f56-122">「[例](#examples)」のセクションでは、MSBuild の -p スイッチを使用する方法について、2 つの異なるシナリオで説明します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-122">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

<span data-ttu-id="a9f56-123">Web プロジェクトは既定でパッケージ化可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="a9f56-123">Web projects aren't packable by default.</span></span> <span data-ttu-id="a9f56-124">既定の動作をオーバーライドするには、 *.csproj* ファイルに次のプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-124">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="a9f56-125">引数</span><span class="sxs-lookup"><span data-stu-id="a9f56-125">Arguments</span></span>

`PROJECT | SOLUTION`

  <span data-ttu-id="a9f56-126">パックするプロジェクトまたはソリューション。</span><span class="sxs-lookup"><span data-stu-id="a9f56-126">The project or solution to pack.</span></span> <span data-ttu-id="a9f56-127">[csproj ファイル](csproj.md)、ソリューション ファイル、またはディレクトリのいずれかへのパスです。</span><span class="sxs-lookup"><span data-stu-id="a9f56-127">It's either a path to a [csproj file](csproj.md), a solution file, or to a directory.</span></span> <span data-ttu-id="a9f56-128">指定されていない場合、コマンドによりプロジェクトまたはソリューション ファイルが現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-128">If not specified, the command searches the current directory for a project or solution file.</span></span>

## <a name="options"></a><span data-ttu-id="a9f56-129">オプション</span><span class="sxs-lookup"><span data-stu-id="a9f56-129">Options</span></span>

- **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="a9f56-130">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-130">Defines the build configuration.</span></span> <span data-ttu-id="a9f56-131">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="a9f56-131">The default value is `Debug`.</span></span>

- **`--force`**

  <span data-ttu-id="a9f56-132">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="a9f56-133">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="a9f56-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="a9f56-134">.NET Core 2.0 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="a9f56-134">Option available since .NET Core 2.0 SDK.</span></span>

- **`-h|--help`**

  <span data-ttu-id="a9f56-135">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-135">Prints out a short help for the command.</span></span>

- **`--include-source`**

  <span data-ttu-id="a9f56-136">通常の NuGet パッケージに加えて、デバッグ シンボル NuGet パッケージが出力ディレクトリ内に含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-136">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span> <span data-ttu-id="a9f56-137">ソース ファイルは、シンボル パッケージ内の `src` フォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-137">The sources files are included in the `src` folder within the symbols package.</span></span>

- **`--include-symbols`**

  <span data-ttu-id="a9f56-138">通常の NuGet パッケージに加えて、デバッグ シンボル NuGet パッケージが出力ディレクトリ内に含まれます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-138">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span>

- **`--interactive`**

  <span data-ttu-id="a9f56-139">コマンドを停止して、ユーザーの入力または操作のために待機させることができます (たとえば、認証を完了する場合)。</span><span class="sxs-lookup"><span data-stu-id="a9f56-139">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="a9f56-140">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-140">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-build`**

  <span data-ttu-id="a9f56-141">パッキングの前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="a9f56-141">Doesn't build the project before packing.</span></span> <span data-ttu-id="a9f56-142">また、`--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-142">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="a9f56-143">プロジェクト間参照を無視し、ルート プロジェクトのみを復元します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-143">Ignores project-to-project references and only restores the root project.</span></span> <span data-ttu-id="a9f56-144">.NET Core 2.0 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="a9f56-144">Option available since .NET Core 2.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="a9f56-145">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="a9f56-145">Doesn't execute an implicit restore when running the command.</span></span> <span data-ttu-id="a9f56-146">.NET Core 2.0 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="a9f56-146">Option available since .NET Core 2.0 SDK.</span></span>

- **`--nologo`**

  <span data-ttu-id="a9f56-147">著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="a9f56-147">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="a9f56-148">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9f56-148">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="a9f56-149">指定したディレクトリにビルド済みパッケージを配置します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-149">Places the built packages in the directory specified.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="a9f56-150">パッケージを復元するターゲット ランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-150">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="a9f56-151">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a9f56-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="a9f56-152">.NET Core 2.0 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="a9f56-152">Option available since .NET Core 2.0 SDK.</span></span>

- **`-s|--serviceable`**

  <span data-ttu-id="a9f56-153">パッケージに処理可能フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-153">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="a9f56-154">詳しくは、「[.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing)」(.NET ブログ: .NET 4.5.1 は .NET NuGet ライブラリに対する Microsoft セキュリティ更新プログラムをサポートする) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a9f56-154">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="a9f56-155">プロジェクトの `$(VersionSuffix)` MSBuild プロパティの値を定義します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-155">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="a9f56-156">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="a9f56-157">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="a9f56-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="a9f56-158">使用例</span><span class="sxs-lookup"><span data-stu-id="a9f56-158">Examples</span></span>

- <span data-ttu-id="a9f56-159">現在のディレクトリのプロジェクトをパックします。</span><span class="sxs-lookup"><span data-stu-id="a9f56-159">Pack the project in the current directory:</span></span>

  ```dotnetcli
  dotnet pack
  ```

- <span data-ttu-id="a9f56-160">`app1` プロジェクトをパックします。</span><span class="sxs-lookup"><span data-stu-id="a9f56-160">Pack the `app1` project:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- <span data-ttu-id="a9f56-161">プロジェクトを現在のディレクトリにパックし、`nupkgs` フォルダーに生成されたパッケージを配置します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-161">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- <span data-ttu-id="a9f56-162">現在のディレクトリのプロジェクトを `nupkgs` フォルダーにパックし、ビルド ステップをスキップします。</span><span class="sxs-lookup"><span data-stu-id="a9f56-162">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- <span data-ttu-id="a9f56-163">*.csproj* ファイルで `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` として構成されているプロジェクトのバージョン サフィックスで、現在のプロジェクトをパックし、結果のパッケージ バージョンを指定されたサフィックスで更新します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-163">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- <span data-ttu-id="a9f56-164">`PackageVersion` MSBuild プロパティで `2.1.0` にパッケージ バージョンを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9f56-164">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- <span data-ttu-id="a9f56-165">プロジェクトを特定の[ターゲット フレームワーク](../../standard/frameworks.md)用にパックします。</span><span class="sxs-lookup"><span data-stu-id="a9f56-165">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- <span data-ttu-id="a9f56-166">プロジェクトをパックして、復元操作の特定のランタイム (Windows 10) を使用します(.NET Core SDK 2.0 以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="a9f56-166">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- <span data-ttu-id="a9f56-167">[.nuspec ファイル](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec)を使用してプロジェクトをパックします。</span><span class="sxs-lookup"><span data-stu-id="a9f56-167">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```
