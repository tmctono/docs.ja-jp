---
title: dotnet restore コマンド
description: dotnet restore コマンドを使用して、依存関係とプロジェクト固有のツールを復元する方法について説明します。
ms.date: 02/27/2020
ms.openlocfilehash: e74027ba70ddf6905a12f9691caeb0a406428ad6
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157025"
---
# <a name="dotnet-restore"></a><span data-ttu-id="c8586-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c8586-103">dotnet restore</span></span>

<span data-ttu-id="c8586-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="c8586-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c8586-105">名前</span><span class="sxs-lookup"><span data-stu-id="c8586-105">Name</span></span>

<span data-ttu-id="c8586-106">`dotnet restore` - プロジェクトの依存関係とツールを復元します。</span><span class="sxs-lookup"><span data-stu-id="c8586-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c8586-107">構文</span><span class="sxs-lookup"><span data-stu-id="c8586-107">Synopsis</span></span>

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel]
    [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime]
    [-s|--source] [-v|--verbosity] [--interactive]

dotnet restore [-h|--help]
```

## <a name="description"></a><span data-ttu-id="c8586-108">説明</span><span class="sxs-lookup"><span data-stu-id="c8586-108">Description</span></span>

<span data-ttu-id="c8586-109">`dotnet restore` コマンドでは NuGet を使用して、依存関係と、プロジェクト ファイルに指定されているプロジェクト固有のツールを復元します。</span><span class="sxs-lookup"><span data-stu-id="c8586-109">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="c8586-110">既定では、依存関係とツールの復元は並列に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c8586-110">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

<span data-ttu-id="c8586-111">依存関係を復元するには、NuGet で、パッケージを配置するフィードが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c8586-111">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="c8586-112">フィードは、通常、"*nuget.config*" 構成ファイルを通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="c8586-112">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="c8586-113">既定の構成ファイルは、.NET Core SDK がインストールされている場合に提供されます。</span><span class="sxs-lookup"><span data-stu-id="c8586-113">A default configuration file is provided when the .NET Core SDK is installed.</span></span> <span data-ttu-id="c8586-114">プロジェクト ディレクトリに独自の "*nuget.config*" ファイルを作成して、さらにフィードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8586-114">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="c8586-115">\- `-s` オプションを使用して *nuget.config* フィードをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="c8586-115">You can override the *nuget.config* feeds with the - `-s` option.</span></span>

<span data-ttu-id="c8586-116">依存関係については、`--packages` 引数を使用して、復元操作中に復元されたパッケージの配置場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8586-116">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="c8586-117">指定されていない場合は、既定の NuGet パッケージ キャッシュが使用されます。これは、すべてのオペレーティング システムのユーザーのホーム ディレクトリ内の `.nuget/packages` ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="c8586-117">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="c8586-118">たとえば、Linux の場合は */home/user1*、Windows の場合は *C:\Users\user1* です。</span><span class="sxs-lookup"><span data-stu-id="c8586-118">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="c8586-119">プロジェクト固有のツールについては、`dotnet restore` はまず、ツールがパックされているパッケージを復元し、プロジェクト ファイルに指定されているツールの依存関係の復元に進みます。</span><span class="sxs-lookup"><span data-stu-id="c8586-119">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="c8586-120">nuget.config の相違点</span><span class="sxs-lookup"><span data-stu-id="c8586-120">nuget.config differences</span></span>

<span data-ttu-id="c8586-121">"*nuget.config*" がある場合、`dotnet restore` コマンドの動作はその設定に影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="c8586-121">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="c8586-122">たとえば、"*nuget.config*" に `globalPackagesFolder` を設定すると、指定されたフォルダーに NuGet パッケージが復元されます。</span><span class="sxs-lookup"><span data-stu-id="c8586-122">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="c8586-123">これは `dotnet restore` コマンドで `--packages` オプションを指定する操作の代替方法です。</span><span class="sxs-lookup"><span data-stu-id="c8586-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="c8586-124">詳細については、「[nuget の .config リファレンス](/nuget/schema/nuget-config-file)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8586-124">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="c8586-125">`dotnet restore` によって無視される、特定の設定が 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="c8586-125">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="c8586-126">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="c8586-126">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="c8586-127">バインド リダイレクトは、`<PackageReference>` 要素では機能しません。また、.NET Core では、NuGet パッケージの `<PackageReference>` 要素のみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c8586-127">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="c8586-128">solution</span><span class="sxs-lookup"><span data-stu-id="c8586-128">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="c8586-129">これは、Visual Studio 固有の設定であり、.NET Core には適用されません。</span><span class="sxs-lookup"><span data-stu-id="c8586-129">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="c8586-130">.NET Core では、`packages.config` ファイルは使用されず、代わりに NuGet パッケージの `<PackageReference>` 要素が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8586-130">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="c8586-131">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="c8586-131">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="c8586-132">この設定は、信頼できるパッケージの[クロスプラットフォーム検証が NuGet でまだサポートされていない](https://github.com/NuGet/Home/issues/7939)ため、適用されません。</span><span class="sxs-lookup"><span data-stu-id="c8586-132">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-restore"></a><span data-ttu-id="c8586-133">暗黙的な復元</span><span class="sxs-lookup"><span data-stu-id="c8586-133">Implicit restore</span></span>

<span data-ttu-id="c8586-134">次のコマンドを実行すると、必要に応じて `dotnet restore` コマンドが暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c8586-134">The `dotnet restore` command is run implicitly if necessary when you run the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="c8586-135">ほとんどの場合、`dotnet restore` コマンドを明示的に使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c8586-135">In most cases, you don't need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="c8586-136">ときには、`dotnet restore` を暗黙的に実行するのが不便な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8586-136">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="c8586-137">たとえば、ビルド システムなど、一部の自動化されているシステムでは、ネットワーク使用状況を制御できるように、`dotnet restore` を明示的に呼び出し、復元のタイミングを制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8586-137">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="c8586-138">`dotnet restore` の暗黙的実行を防ぐために、`--no-restore` フラグと共にこれらのコマンドのいずれかを使用し、暗黙的復元を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c8586-138">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="c8586-139">引数</span><span class="sxs-lookup"><span data-stu-id="c8586-139">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="c8586-140">復元するプロジェクト ファイルへのオプションのパスです。</span><span class="sxs-lookup"><span data-stu-id="c8586-140">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="c8586-141">オプション</span><span class="sxs-lookup"><span data-stu-id="c8586-141">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="c8586-142">復元操作で使用する NuGet 構成ファイル ("*nuget.config*") です。</span><span class="sxs-lookup"><span data-stu-id="c8586-142">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="c8586-143">複数プロジェクトの並行復元を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c8586-143">Disables restoring multiple projects in parallel.</span></span>

- **`--force`**

  <span data-ttu-id="c8586-144">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="c8586-144">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c8586-145">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="c8586-145">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c8586-146">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="c8586-146">Prints out a short help for the command.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="c8586-147">バージョン要件を満たしているパッケージがある場合は、失敗したソースに関する警告のみです。</span><span class="sxs-lookup"><span data-stu-id="c8586-147">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

- **`--no-cache`**

  <span data-ttu-id="c8586-148">パッケージとの HTTP 要求をキャッシュしないように指定します。</span><span class="sxs-lookup"><span data-stu-id="c8586-148">Specifies to not cache packages and HTTP requests.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="c8586-149">プロジェクト間 (P2P) 参照を含むプロジェクトを復元する場合は、参照ではなく、ルート プロジェクトを復元します。</span><span class="sxs-lookup"><span data-stu-id="c8586-149">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--packages <PACKAGES_DIRECTORY>`**

  <span data-ttu-id="c8586-150">復元されるパッケージのディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8586-150">Specifies the directory for restored packages.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="c8586-151">パッケージの復元用のランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8586-151">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="c8586-152">これは、 *.csproj* ファイルの `<RuntimeIdentifiers>` タグに明示的にリストされていないランタイムのパッケージを復元するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8586-152">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="c8586-153">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c8586-153">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c8586-154">このオプションを複数回指定して、複数の RID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8586-154">Provide multiple RIDs by specifying this option multiple times.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="c8586-155">復元操作時に使用する NuGet パッケージのソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8586-155">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="c8586-156">この設定により、"*nuget.config*" ファイルに指定されているすべてのソースがオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="c8586-156">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="c8586-157">このオプションを複数回指定することによって、複数のソースを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8586-157">Multiple sources can be provided by specifying this option multiple times.</span></span>

- **`--verbosity <LEVEL>`**

  <span data-ttu-id="c8586-158">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8586-158">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c8586-159">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="c8586-159">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c8586-160">既定値は `minimal`にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8586-160">Default value is `minimal`.</span></span>

- **`--interactive`**

  <span data-ttu-id="c8586-161">コマンドを停止して、ユーザーの入力または操作のために待機させることができます (たとえば、認証を完了する場合)。</span><span class="sxs-lookup"><span data-stu-id="c8586-161">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="c8586-162">.NET Core 2.1.400 以降。</span><span class="sxs-lookup"><span data-stu-id="c8586-162">Since .NET Core 2.1.400.</span></span>

## <a name="examples"></a><span data-ttu-id="c8586-163">使用例</span><span class="sxs-lookup"><span data-stu-id="c8586-163">Examples</span></span>

- <span data-ttu-id="c8586-164">現在のディレクトリでプロジェクトの依存関係とツールを復元します。</span><span class="sxs-lookup"><span data-stu-id="c8586-164">Restore dependencies and tools for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet restore
  ```

- <span data-ttu-id="c8586-165">指定されたパスで見つかった `app1` プロジェクトの依存関係とツールを復元します。</span><span class="sxs-lookup"><span data-stu-id="c8586-165">Restore dependencies and tools for the `app1` project found in the   given path:</span></span>

  ```dotnetcli
  dotnet restore ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="c8586-166">ソースとして指定されたファイル パスを使用して、現在のディレクトリでプロジェクトの依存関係とツールを復元します。</span><span class="sxs-lookup"><span data-stu-id="c8586-166">Restore the dependencies and tools for the project in the current   directory using the file path provided as the source:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- <span data-ttu-id="c8586-167">ソースとして指定された 2 つのファイル パスを使用して、現在のディレクトリでプロジェクトの依存関係とツールを復元します。</span><span class="sxs-lookup"><span data-stu-id="c8586-167">Restore the dependencies and tools for the project in the current   directory using the two file paths provided as sources:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- <span data-ttu-id="c8586-168">詳細な出力を示して、現在のディレクトリでプロジェクトの依存関係とツールを復元します。</span><span class="sxs-lookup"><span data-stu-id="c8586-168">Restore dependencies and tools for the project in the current directory   showing detailed output:</span></span>

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
