---
title: .NET Core CLI
titleSuffix: ''
description: .NET Core CLI とその機能に関する概要です。
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920478"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="b1f4c-103">.NET Core CLI の概要</span><span class="sxs-lookup"><span data-stu-id="b1f4c-103">.NET Core CLI overview</span></span>

<span data-ttu-id="b1f4c-104">.NET Core コマンド ライン インターフェイス (CLI) は、.NET Core アプリケーションを開発、ビルド、実行、発行するためのクロスプラットフォーム ツールチェーンです。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="b1f4c-105">.NET Core CLI は、[.NET Core SDK](../sdk.md) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-105">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="b1f4c-106">.NET Core SDK をインストールする方法については、「[.NET Core SDK をインストールする](../install/sdk.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-106">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="b1f4c-107">CLI コマンド</span><span class="sxs-lookup"><span data-stu-id="b1f4c-107">CLI commands</span></span>

<span data-ttu-id="b1f4c-108">既定では、次のコマンドがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-108">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b1f4c-109">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b1f4c-109">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="b1f4c-110">**基本的なコマンド**</span><span class="sxs-lookup"><span data-stu-id="b1f4c-110">**Basic commands**</span></span>

- [<span data-ttu-id="b1f4c-111">new</span><span class="sxs-lookup"><span data-stu-id="b1f4c-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="b1f4c-112">restore</span><span class="sxs-lookup"><span data-stu-id="b1f4c-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="b1f4c-113">build</span><span class="sxs-lookup"><span data-stu-id="b1f4c-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="b1f4c-114">publish</span><span class="sxs-lookup"><span data-stu-id="b1f4c-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="b1f4c-115">run</span><span class="sxs-lookup"><span data-stu-id="b1f4c-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="b1f4c-116">test</span><span class="sxs-lookup"><span data-stu-id="b1f4c-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="b1f4c-117">vstest</span><span class="sxs-lookup"><span data-stu-id="b1f4c-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="b1f4c-118">pack</span><span class="sxs-lookup"><span data-stu-id="b1f4c-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="b1f4c-119">migrate</span><span class="sxs-lookup"><span data-stu-id="b1f4c-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="b1f4c-120">clean</span><span class="sxs-lookup"><span data-stu-id="b1f4c-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="b1f4c-121">sln</span><span class="sxs-lookup"><span data-stu-id="b1f4c-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="b1f4c-122">help</span><span class="sxs-lookup"><span data-stu-id="b1f4c-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="b1f4c-123">store</span><span class="sxs-lookup"><span data-stu-id="b1f4c-123">store</span></span>](dotnet-store.md)

<span data-ttu-id="b1f4c-124">**プロジェクトの変更コマンド**</span><span class="sxs-lookup"><span data-stu-id="b1f4c-124">**Project modification commands**</span></span>

- [<span data-ttu-id="b1f4c-125">add package</span><span class="sxs-lookup"><span data-stu-id="b1f4c-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="b1f4c-126">add reference</span><span class="sxs-lookup"><span data-stu-id="b1f4c-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="b1f4c-127">remove package</span><span class="sxs-lookup"><span data-stu-id="b1f4c-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="b1f4c-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="b1f4c-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="b1f4c-129">list reference</span><span class="sxs-lookup"><span data-stu-id="b1f4c-129">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="b1f4c-130">**高度なコマンド**</span><span class="sxs-lookup"><span data-stu-id="b1f4c-130">**Advanced commands**</span></span>

- [<span data-ttu-id="b1f4c-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="b1f4c-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="b1f4c-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="b1f4c-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="b1f4c-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="b1f4c-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="b1f4c-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="b1f4c-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="b1f4c-135">dotnet install スクリプト</span><span class="sxs-lookup"><span data-stu-id="b1f4c-135">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b1f4c-136">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b1f4c-136">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b1f4c-137">**基本的なコマンド**</span><span class="sxs-lookup"><span data-stu-id="b1f4c-137">**Basic commands**</span></span>

- [<span data-ttu-id="b1f4c-138">new</span><span class="sxs-lookup"><span data-stu-id="b1f4c-138">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="b1f4c-139">restore</span><span class="sxs-lookup"><span data-stu-id="b1f4c-139">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="b1f4c-140">build</span><span class="sxs-lookup"><span data-stu-id="b1f4c-140">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="b1f4c-141">publish</span><span class="sxs-lookup"><span data-stu-id="b1f4c-141">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="b1f4c-142">run</span><span class="sxs-lookup"><span data-stu-id="b1f4c-142">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="b1f4c-143">test</span><span class="sxs-lookup"><span data-stu-id="b1f4c-143">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="b1f4c-144">vstest</span><span class="sxs-lookup"><span data-stu-id="b1f4c-144">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="b1f4c-145">pack</span><span class="sxs-lookup"><span data-stu-id="b1f4c-145">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="b1f4c-146">migrate</span><span class="sxs-lookup"><span data-stu-id="b1f4c-146">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="b1f4c-147">clean</span><span class="sxs-lookup"><span data-stu-id="b1f4c-147">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="b1f4c-148">sln</span><span class="sxs-lookup"><span data-stu-id="b1f4c-148">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="b1f4c-149">**プロジェクトの変更コマンド**</span><span class="sxs-lookup"><span data-stu-id="b1f4c-149">**Project modification commands**</span></span>

- [<span data-ttu-id="b1f4c-150">add package</span><span class="sxs-lookup"><span data-stu-id="b1f4c-150">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="b1f4c-151">add reference</span><span class="sxs-lookup"><span data-stu-id="b1f4c-151">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="b1f4c-152">remove package</span><span class="sxs-lookup"><span data-stu-id="b1f4c-152">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="b1f4c-153">remove reference</span><span class="sxs-lookup"><span data-stu-id="b1f4c-153">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="b1f4c-154">list reference</span><span class="sxs-lookup"><span data-stu-id="b1f4c-154">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="b1f4c-155">**高度なコマンド**</span><span class="sxs-lookup"><span data-stu-id="b1f4c-155">**Advanced commands**</span></span>

- [<span data-ttu-id="b1f4c-156">nuget delete</span><span class="sxs-lookup"><span data-stu-id="b1f4c-156">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="b1f4c-157">nuget locals</span><span class="sxs-lookup"><span data-stu-id="b1f4c-157">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="b1f4c-158">nuget push</span><span class="sxs-lookup"><span data-stu-id="b1f4c-158">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="b1f4c-159">msbuild</span><span class="sxs-lookup"><span data-stu-id="b1f4c-159">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="b1f4c-160">dotnet install スクリプト</span><span class="sxs-lookup"><span data-stu-id="b1f4c-160">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="b1f4c-161">CLI では、プロジェクトに追加のツールを指定できるようにする拡張モデルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-161">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="b1f4c-162">詳細については、「[.NET Core CLI の拡張モデル](extensibility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-162">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="b1f4c-163">コマンド構造</span><span class="sxs-lookup"><span data-stu-id="b1f4c-163">Command structure</span></span>

<span data-ttu-id="b1f4c-164">CLI コマンド構造は、[ドライバー ("dotnet")](#driver) と[コマンド](#command)、また場合によってはコマンドの[引数](#arguments)と[オプション](#options)で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-164">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="b1f4c-165">*my_app* という名前のディレクトリから実行する場合、次のコマンドで示されているように、新しいコンソール アプリの作成やコマンド ラインからの実行など、ほとんどの CLI 操作でこのパターンが見られます。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-165">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b1f4c-166">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b1f4c-166">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b1f4c-167">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b1f4c-167">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="b1f4c-168">ドライバー</span><span class="sxs-lookup"><span data-stu-id="b1f4c-168">Driver</span></span>

<span data-ttu-id="b1f4c-169">ドライバーは [dotnet](dotnet.md) という名前で、2 つの役割 ([フレームワークに依存するアプリ](../deploying/index.md)の実行と、コマンドの実行) があります。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-169">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="b1f4c-170">フレームワークに依存するアプリを実行するには、`dotnet /path/to/my_app.dll` など、ドライバーの後にアプリを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-170">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="b1f4c-171">アプリの DLL が存在するフォルダーからコマンドを実行する場合は、`dotnet my_app.dll` を実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-171">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="b1f4c-172">.NET Core ランタイムの特定のバージョンを使用する場合は、`--fx-version <VERSION>` オプションを使用してください (「[dotnet コマンド](dotnet.md)」リファレンスを参照)。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-172">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="b1f4c-173">ドライバーにコマンドを指定すると、`dotnet.exe` は CLI コマンドの実行プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-173">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="b1f4c-174">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-174">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="b1f4c-175">最初に、ドライバーは使用する SDK のバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-175">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="b1f4c-176">['global.json'](global-json.md) がない場合は、利用可能な SDK の最新バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-176">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="b1f4c-177">コンピューターで最新のプレビューまたは安定したバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-177">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="b1f4c-178">SDK バージョンが決定されたら、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-178">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="b1f4c-179">コマンド</span><span class="sxs-lookup"><span data-stu-id="b1f4c-179">Command</span></span>

<span data-ttu-id="b1f4c-180">コマンドは、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-180">The command performs an action.</span></span> <span data-ttu-id="b1f4c-181">たとえば、`dotnet build` はコードをビルドします。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-181">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="b1f4c-182">`dotnet publish` はコードを発行します。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-182">`dotnet publish` publishes code.</span></span> <span data-ttu-id="b1f4c-183">コマンドは、`dotnet {command}` 規則を使用してコンソール アプリケーションとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-183">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="b1f4c-184">引数</span><span class="sxs-lookup"><span data-stu-id="b1f4c-184">Arguments</span></span>

<span data-ttu-id="b1f4c-185">コマンド ラインで渡す引数は、呼び出されたコマンドへの引数です。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-185">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="b1f4c-186">たとえば、`dotnet publish my_app.csproj` を実行した場合、`my_app.csproj` 引数は、発行するプロジェクトを示し、`publish` コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-186">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="b1f4c-187">オプション</span><span class="sxs-lookup"><span data-stu-id="b1f4c-187">Options</span></span>

<span data-ttu-id="b1f4c-188">コマンド ラインで渡すオプションは、呼び出されたコマンドへのオプションです。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-188">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="b1f4c-189">たとえば、`dotnet publish --output /build_output` を実行した場合、`--output` オプションとその値は `publish` コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-189">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="b1f4c-190">project.json からの移行</span><span class="sxs-lookup"><span data-stu-id="b1f4c-190">Migration from project.json</span></span>

<span data-ttu-id="b1f4c-191">Preview 2 ツールを使用して *project.json* ベースのプロジェクトを生成した場合は、リリース ツールで使用するための MSBuild/ *.csproj* へのプロジェクトの移行について、「[dotnet-migrate](dotnet-migrate.md)」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-191">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="b1f4c-192">Preview 2 ツールのリリースの前に作成された .NET Core プロジェクトの場合は、「[DNX から .NET Core CLI への移行 (project.json)](../migration/from-dnx.md)」のガイダンスに従って手動でプロジェクトを更新してから `dotnet migrate` を使用するか、プロジェクトを直接アップグレードします。</span><span class="sxs-lookup"><span data-stu-id="b1f4c-192">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1f4c-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1f4c-193">See also</span></span>

- [<span data-ttu-id="b1f4c-194">dotnet/sdk GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="b1f4c-194">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="b1f4c-195">.NET Core のインストール ガイド</span><span class="sxs-lookup"><span data-stu-id="b1f4c-195">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
