---
title: dotnet pack コマンド
description: dotnet pack コマンドでは、.NET Core プロジェクトの NuGet パッケージを作成します。
ms.date: 02/14/2020
ms.openlocfilehash: 3b9c46ecd5d67519728896b0018e27fb41ebd861
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463508"
---
# <a name="dotnet-pack"></a><span data-ttu-id="801e6-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="801e6-103">dotnet pack</span></span>

<span data-ttu-id="801e6-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="801e6-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="801e6-105">名前</span><span class="sxs-lookup"><span data-stu-id="801e6-105">Name</span></span>

<span data-ttu-id="801e6-106">`dotnet pack` - NuGet パッケージにコードをパックします。</span><span class="sxs-lookup"><span data-stu-id="801e6-106">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="801e6-107">構文</span><span class="sxs-lookup"><span data-stu-id="801e6-107">Synopsis</span></span>

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a><span data-ttu-id="801e6-108">説明</span><span class="sxs-lookup"><span data-stu-id="801e6-108">Description</span></span>

<span data-ttu-id="801e6-109">`dotnet pack` コマンドはプロジェクトをビルドし、NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="801e6-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="801e6-110">このコマンドの結果が NuGet パッケージ (つまり、 *.nupkg* ファイル) です。</span><span class="sxs-lookup"><span data-stu-id="801e6-110">The result of this command is a NuGet package (that is, a *.nupkg* file).</span></span>

<span data-ttu-id="801e6-111">デバッグ シンボルを含むパッケージを生成する場合、使用可能なオプションが 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="801e6-111">If you want to generate a package that contains the debug symbols, you have two options available:</span></span>

- <span data-ttu-id="801e6-112">`--include-symbols` -シンボル パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="801e6-112">`--include-symbols` - it creates the symbols package.</span></span>
- <span data-ttu-id="801e6-113">`--include-source` -ソース ファイルが含まれた `src` フォルダーを含むシンボル パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="801e6-113">`--include-source` - it creates the symbols package with a `src` folder inside containing the source files.</span></span>

<span data-ttu-id="801e6-114">パックされるプロジェクトの NuGet 依存関係が *.nuspec* ファイルに追加されるため、パッケージのインストール時に適切に解決されます。</span><span class="sxs-lookup"><span data-stu-id="801e6-114">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="801e6-115">プロジェクト間参照はプロジェクト内にはパッケージ化されません。</span><span class="sxs-lookup"><span data-stu-id="801e6-115">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="801e6-116">現時点では、プロジェクト間の依存関係がある場合は、プロジェクトごとにパッケージが必要になります。</span><span class="sxs-lookup"><span data-stu-id="801e6-116">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="801e6-117">既定では、`dotnet pack` は最初にプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="801e6-117">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="801e6-118">この動作を避けたい場合は、`--no-build` オプションを渡します。</span><span class="sxs-lookup"><span data-stu-id="801e6-118">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="801e6-119">このオプションは、コードが既にビルドされていることがわかっている場合の継続的インテグレーション (CI) ビルド シナリオで役立つことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="801e6-119">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

> [!NOTE]
> <span data-ttu-id="801e6-120">場合によっては、暗黙的なビルドは実行できません。</span><span class="sxs-lookup"><span data-stu-id="801e6-120">In some cases, the implicit build cannot be performed.</span></span> <span data-ttu-id="801e6-121">これは、ビルドとパック ターゲット間の循環依存を回避するため `GeneratePackageOnBuild` が設定されている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="801e6-121">This can occur when `GeneratePackageOnBuild` is set, to avoid a cyclic dependency between build and pack targets.</span></span> <span data-ttu-id="801e6-122">ロックされているファイルがある場合や、その他の問題がある場合にも、ビルドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="801e6-122">The build can also fail if there is a locked file or other issue.</span></span>

<span data-ttu-id="801e6-123">パッキング プロセスのために `dotnet pack` コマンドに MSBuild のプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="801e6-123">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="801e6-124">詳細については、「[NuGet メタデータ プロパティ](csproj.md#nuget-metadata-properties)」と「[MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="801e6-124">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="801e6-125">「[例](#examples)」のセクションでは、MSBuild の -p スイッチを使用する方法について、2 つの異なるシナリオで説明します。</span><span class="sxs-lookup"><span data-stu-id="801e6-125">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

<span data-ttu-id="801e6-126">Web プロジェクトは既定でパッケージ化可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="801e6-126">Web projects aren't packable by default.</span></span> <span data-ttu-id="801e6-127">既定の動作をオーバーライドするには、 *.csproj* ファイルに次のプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="801e6-127">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="801e6-128">引数</span><span class="sxs-lookup"><span data-stu-id="801e6-128">Arguments</span></span>

`PROJECT | SOLUTION`

  <span data-ttu-id="801e6-129">パックするプロジェクトまたはソリューション。</span><span class="sxs-lookup"><span data-stu-id="801e6-129">The project or solution to pack.</span></span> <span data-ttu-id="801e6-130">[csproj ファイル](csproj.md)、ソリューション ファイル、またはディレクトリのいずれかへのパスです。</span><span class="sxs-lookup"><span data-stu-id="801e6-130">It's either a path to a [csproj file](csproj.md), a solution file, or to a directory.</span></span> <span data-ttu-id="801e6-131">指定されていない場合、コマンドによりプロジェクトまたはソリューション ファイルが現在のディレクトリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="801e6-131">If not specified, the command searches the current directory for a project or solution file.</span></span>

## <a name="options"></a><span data-ttu-id="801e6-132">オプション</span><span class="sxs-lookup"><span data-stu-id="801e6-132">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="801e6-133">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="801e6-133">Defines the build configuration.</span></span> <span data-ttu-id="801e6-134">ほとんどのプロジェクトの既定値は `Debug` ですが、プロジェクトでビルド構成設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="801e6-134">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`--force`**

  <span data-ttu-id="801e6-135">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="801e6-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="801e6-136">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="801e6-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="801e6-137">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="801e6-137">Prints out a short help for the command.</span></span>

- **`--include-source`**

  <span data-ttu-id="801e6-138">通常の NuGet パッケージに加えて、デバッグ シンボル NuGet パッケージが出力ディレクトリ内に含まれます。</span><span class="sxs-lookup"><span data-stu-id="801e6-138">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span> <span data-ttu-id="801e6-139">ソース ファイルは、シンボル パッケージ内の `src` フォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="801e6-139">The sources files are included in the `src` folder within the symbols package.</span></span>

- **`--include-symbols`**

  <span data-ttu-id="801e6-140">通常の NuGet パッケージに加えて、デバッグ シンボル NuGet パッケージが出力ディレクトリ内に含まれます。</span><span class="sxs-lookup"><span data-stu-id="801e6-140">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span>

- **`--interactive`**

  <span data-ttu-id="801e6-141">コマンドを停止して、ユーザーの入力または操作のために待機させることができます (たとえば、認証を完了する場合)。</span><span class="sxs-lookup"><span data-stu-id="801e6-141">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="801e6-142">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="801e6-142">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-build`**

  <span data-ttu-id="801e6-143">パッキングの前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="801e6-143">Doesn't build the project before packing.</span></span> <span data-ttu-id="801e6-144">また、`--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="801e6-144">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="801e6-145">プロジェクト間参照を無視し、ルート プロジェクトのみを復元します。</span><span class="sxs-lookup"><span data-stu-id="801e6-145">Ignores project-to-project references and only restores the root project.</span></span>

- **`--no-restore`**

  <span data-ttu-id="801e6-146">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="801e6-146">Doesn't execute an implicit restore when running the command.</span></span>

- **`--nologo`**

  <span data-ttu-id="801e6-147">著作権情報を表示しません。</span><span class="sxs-lookup"><span data-stu-id="801e6-147">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="801e6-148">.NET Core 3.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="801e6-148">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="801e6-149">指定したディレクトリにビルド済みパッケージを配置します。</span><span class="sxs-lookup"><span data-stu-id="801e6-149">Places the built packages in the directory specified.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="801e6-150">パッケージを復元するターゲット ランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="801e6-150">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="801e6-151">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="801e6-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-s|--serviceable`**

  <span data-ttu-id="801e6-152">パッケージに処理可能フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="801e6-152">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="801e6-153">詳しくは、「[.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing)」(.NET ブログ: .NET 4.5.1 は .NET NuGet ライブラリに対する Microsoft セキュリティ更新プログラムをサポートする) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="801e6-153">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="801e6-154">プロジェクトの `$(VersionSuffix)` MSBuild プロパティの値を定義します。</span><span class="sxs-lookup"><span data-stu-id="801e6-154">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="801e6-155">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="801e6-155">Sets the verbosity level of the command.</span></span> <span data-ttu-id="801e6-156">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="801e6-156">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="801e6-157">使用例</span><span class="sxs-lookup"><span data-stu-id="801e6-157">Examples</span></span>

- <span data-ttu-id="801e6-158">現在のディレクトリのプロジェクトをパックします。</span><span class="sxs-lookup"><span data-stu-id="801e6-158">Pack the project in the current directory:</span></span>

  ```dotnetcli
  dotnet pack
  ```

- <span data-ttu-id="801e6-159">`app1` プロジェクトをパックします。</span><span class="sxs-lookup"><span data-stu-id="801e6-159">Pack the `app1` project:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- <span data-ttu-id="801e6-160">プロジェクトを現在のディレクトリにパックし、`nupkgs` フォルダーに生成されたパッケージを配置します。</span><span class="sxs-lookup"><span data-stu-id="801e6-160">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- <span data-ttu-id="801e6-161">現在のディレクトリのプロジェクトを `nupkgs` フォルダーにパックし、ビルド ステップをスキップします。</span><span class="sxs-lookup"><span data-stu-id="801e6-161">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- <span data-ttu-id="801e6-162">*.csproj* ファイルで `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` として構成されているプロジェクトのバージョン サフィックスで、現在のプロジェクトをパックし、結果のパッケージ バージョンを指定されたサフィックスで更新します。</span><span class="sxs-lookup"><span data-stu-id="801e6-162">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- <span data-ttu-id="801e6-163">`PackageVersion` MSBuild プロパティで `2.1.0` にパッケージ バージョンを設定します。</span><span class="sxs-lookup"><span data-stu-id="801e6-163">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- <span data-ttu-id="801e6-164">プロジェクトを特定の[ターゲット フレームワーク](../../standard/frameworks.md)用にパックします。</span><span class="sxs-lookup"><span data-stu-id="801e6-164">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- <span data-ttu-id="801e6-165">プロジェクトをパックして、復元操作用の特定のランタイム (Windows 10) を使用する:</span><span class="sxs-lookup"><span data-stu-id="801e6-165">Pack the project and use a specific runtime (Windows 10) for the restore operation:</span></span>

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- <span data-ttu-id="801e6-166">[.nuspec ファイル](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec)を使用してプロジェクトをパックします。</span><span class="sxs-lookup"><span data-stu-id="801e6-166">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```
