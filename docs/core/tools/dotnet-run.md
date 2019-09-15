---
title: dotnet run コマンド
description: dotnet run コマンドは、ソース コードからアプリケーションを実行する便利なオプションを提供します。
ms.date: 05/29/2018
ms.openlocfilehash: b21987ef9ee4dd7d8fdb93d0853b7faa93001688
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969747"
---
# <a name="dotnet-run"></a><span data-ttu-id="b80eb-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="b80eb-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b80eb-104">name</span><span class="sxs-lookup"><span data-stu-id="b80eb-104">Name</span></span>

<span data-ttu-id="b80eb-105">`dotnet run` -- 明示的なコンパイルや起動コマンドなしで、ソース コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b80eb-106">構文</span><span class="sxs-lookup"><span data-stu-id="b80eb-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b80eb-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b80eb-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b80eb-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b80eb-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b80eb-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b80eb-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="b80eb-110">説明</span><span class="sxs-lookup"><span data-stu-id="b80eb-110">Description</span></span>

<span data-ttu-id="b80eb-111">`dotnet run` コマンドは、1 つのコマンドを使用して、ソース コードからアプリケーションを実行する便利なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-111">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="b80eb-112">コマンド ラインからの短期間の反復開発に便利です。</span><span class="sxs-lookup"><span data-stu-id="b80eb-112">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="b80eb-113">このコマンドは [`dotnet build`](dotnet-build.md) コマンドに依存し、コードをビルドします。</span><span class="sxs-lookup"><span data-stu-id="b80eb-113">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="b80eb-114">そのため、プロジェクトを最初に復元する必要があるなど、ビルドに要件があれば、それが `dotnet run` にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-114">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="b80eb-115">出力ファイルは既定の場所である `bin/<configuration>/<target>` に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-115">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="b80eb-116">たとえば、`netcoreapp2.1` というアプリケーションがあり、`dotnet run` を実行する場合、`bin/Debug/netcoreapp2.1` に出力されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-116">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="b80eb-117">必要に応じて、ファイルは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-117">Files are overwritten as needed.</span></span> <span data-ttu-id="b80eb-118">一時ファイルは `obj` ディレクトリに置かれます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-118">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="b80eb-119">フレームワークを複数指定するプロジェクトの場合、`-f|--framework <FRAMEWORK>` オプションを使用してフレームワークを指定しない限り、`dotnet run` を実行するとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-119">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="b80eb-120">`dotnet run` コマンドは、ビルド済みのアセンブリではなく、プロジェクトのコンテキストで使用されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-120">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="b80eb-121">代わりにフレームワークに依存するアプリケーション DLL の実行を試みる場合は、コマンドなしで [dotnet](dotnet.md) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b80eb-121">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="b80eb-122">たとえば、`myapp.dll` を実行する場合は、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-122">For example, to run `myapp.dll`, use:</span></span>

```console
dotnet myapp.dll
```

<span data-ttu-id="b80eb-123">`dotnet` ドライバーの詳細については、「[.NET Core Command Line Tools (CLI)](index.md)」 (.NET Core コマンド ライン ツール (CLI)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b80eb-123">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="b80eb-124">アプリケーションを実行するため、`dotnet run` コマンドは、NuGet キャッシュから共有ランタイムの外にあるアプリケーションの依存関係を解決します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-124">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="b80eb-125">このコマンドではキャッシュされた依存関係を使用するため、`dotnet run` を使用してアプリケーションを実稼働環境で実行することは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="b80eb-125">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="b80eb-126">代わりに、[`dotnet publish`](dotnet-publish.md) コマンドを使用して[展開を作成](../deploying/index.md)し、発行された出力を展開します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-126">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="b80eb-127">オプション</span><span class="sxs-lookup"><span data-stu-id="b80eb-127">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b80eb-128">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b80eb-128">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="b80eb-129">実行中のアプリケーションの引数と `dotnet run` の引数を区切ります。</span><span class="sxs-lookup"><span data-stu-id="b80eb-129">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="b80eb-130">この区切り記号の後の引数はすべて実行中のアプリケーションに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-130">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b80eb-131">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-131">Defines the build configuration.</span></span> <span data-ttu-id="b80eb-132">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="b80eb-132">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b80eb-133">指定された[フレームワーク](../../standard/frameworks.md)を使用してアプリをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-133">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="b80eb-134">フレームワークはプロジェクト ファイルに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b80eb-134">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="b80eb-135">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="b80eb-136">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="b80eb-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="b80eb-137">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-137">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="b80eb-138">アプリケーションを起動する場合に使用する起動プロファイル (存在する場合) の名前です。</span><span class="sxs-lookup"><span data-stu-id="b80eb-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="b80eb-139">起動プロファイルは *launchSettings.json* ファイル内に定義されており、通常は、`Development`、`Staging`、`Production` と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="b80eb-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="b80eb-140">詳細については、[「Working with multiple environments」](/aspnet/core/fundamentals/environments) (複数の環境での使用) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b80eb-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="b80eb-141">実行前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="b80eb-141">Doesn't build the project before running.</span></span> <span data-ttu-id="b80eb-142">また、`--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-142">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="b80eb-143">プロジェクト間 (P2P) 参照を含むプロジェクトを復元する場合は、参照ではなく、ルート プロジェクトを復元します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="b80eb-144">アプリケーションを構成するための *launchSettings.json* の使用を試みません。</span><span class="sxs-lookup"><span data-stu-id="b80eb-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="b80eb-145">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="b80eb-145">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="b80eb-146">実行するプロジェクト ファイルのパスを指定します (フォルダー名または完全なパス)。</span><span class="sxs-lookup"><span data-stu-id="b80eb-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="b80eb-147">指定しない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-147">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="b80eb-148">パッケージを復元するターゲット ランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="b80eb-149">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b80eb-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b80eb-150">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b80eb-151">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="b80eb-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b80eb-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b80eb-152">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="b80eb-153">実行中のアプリケーションの引数と `dotnet run` の引数を区切ります。</span><span class="sxs-lookup"><span data-stu-id="b80eb-153">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="b80eb-154">この区切り記号の後の引数はすべて実行中のアプリケーションに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-154">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b80eb-155">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-155">Defines the build configuration.</span></span> <span data-ttu-id="b80eb-156">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="b80eb-156">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b80eb-157">指定された[フレームワーク](../../standard/frameworks.md)を使用してアプリをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-157">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="b80eb-158">フレームワークはプロジェクト ファイルに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b80eb-158">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="b80eb-159">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-159">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="b80eb-160">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="b80eb-160">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="b80eb-161">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-161">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="b80eb-162">アプリケーションを起動する場合に使用する起動プロファイル (存在する場合) の名前です。</span><span class="sxs-lookup"><span data-stu-id="b80eb-162">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="b80eb-163">起動プロファイルは *launchSettings.json* ファイル内に定義されており、通常は、`Development`、`Staging`、`Production` と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="b80eb-163">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="b80eb-164">詳細については、[「Working with multiple environments」](/aspnet/core/fundamentals/environments) (複数の環境での使用) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b80eb-164">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="b80eb-165">実行前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="b80eb-165">Doesn't build the project before running.</span></span> <span data-ttu-id="b80eb-166">また、`--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="b80eb-167">プロジェクト間 (P2P) 参照を含むプロジェクトを復元する場合は、参照ではなく、ルート プロジェクトを復元します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-167">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="b80eb-168">アプリケーションを構成するための *launchSettings.json* の使用を試みません。</span><span class="sxs-lookup"><span data-stu-id="b80eb-168">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="b80eb-169">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="b80eb-169">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="b80eb-170">実行するプロジェクト ファイルのパスを指定します (フォルダー名または完全なパス)。</span><span class="sxs-lookup"><span data-stu-id="b80eb-170">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="b80eb-171">指定しない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-171">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="b80eb-172">パッケージを復元するターゲット ランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-172">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="b80eb-173">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b80eb-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b80eb-174">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b80eb-174">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="b80eb-175">実行中のアプリケーションの引数と `dotnet run` の引数を区切ります。</span><span class="sxs-lookup"><span data-stu-id="b80eb-175">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="b80eb-176">この区切り記号の後の引数はすべて実行中のアプリケーションに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-176">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b80eb-177">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-177">Defines the build configuration.</span></span> <span data-ttu-id="b80eb-178">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="b80eb-178">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b80eb-179">指定された[フレームワーク](../../standard/frameworks.md)を使用してアプリをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-179">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="b80eb-180">フレームワークはプロジェクト ファイルに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b80eb-180">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="b80eb-181">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-181">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="b80eb-182">プロジェクト ファイルのパスと名前を指定します</span><span class="sxs-lookup"><span data-stu-id="b80eb-182">Specifies the path and name of the project file.</span></span> <span data-ttu-id="b80eb-183">(注を参照)。指定しない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="b80eb-183">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="b80eb-184">`-p|--project` オプションでプロジェクト ファイルのパスと名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-184">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="b80eb-185">CLI の回帰により、.NET Core SDK 1.x でフォルダー パスを指定できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b80eb-185">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="b80eb-186">この問題の詳細については、[「dotnet run -p, can not start a project (dotnet/cli #5992)」](https://github.com/dotnet/cli/issues/5992) (dotnet run -p でプロジェクトを開始できない (dotnet/cli #5992)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b80eb-186">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="b80eb-187">使用例</span><span class="sxs-lookup"><span data-stu-id="b80eb-187">Examples</span></span>

<span data-ttu-id="b80eb-188">現在のディレクトリのプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-188">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="b80eb-189">指定されたプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b80eb-189">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="b80eb-190">現在のディレクトリのプロジェクトを実行します (この例では、空の `--` オプションが使用されているため、`--help` 引数がアプリケーションに渡されます)。</span><span class="sxs-lookup"><span data-stu-id="b80eb-190">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="b80eb-191">現在のディレクトリでプロジェクトの依存関係とツールを復元し、最小限の出力のみを表示して、プロジェクトを実行します (.NET Core SDK 2.0 以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="b80eb-191">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
