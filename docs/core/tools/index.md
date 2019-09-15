---
title: .NET Core コマンドライン インターフェイス (CLI) ツール
description: .NET Core コマンドライン インターフェイス (CLI) ツールとその機能の概要です。
ms.date: 08/14/2017
ms.custom: seodec18
ms.openlocfilehash: 50d1bbdd87ecd275b97603a1b47c6f13f879365a
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969880"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="1d99e-103">.NET Core コマンドライン インターフェイス (CLI) ツール</span><span class="sxs-lookup"><span data-stu-id="1d99e-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="1d99e-104">.NET Core コマンドライン インターフェイス (CLI) は、.NET アプリケーションを開発するための新しいクロスプラットフォーム ツールチェーンです。</span><span class="sxs-lookup"><span data-stu-id="1d99e-104">The .NET Core command-line interface (CLI) is a new cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="1d99e-105">CLI は、統合開発環境 (IDE)、エディター、ビルド オーケストレーターなど、上位レベル ツールの基になるものです。</span><span class="sxs-lookup"><span data-stu-id="1d99e-105">The CLI is a foundation upon which higher-level tools, such as Integrated Development Environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="1d99e-106">インストール</span><span class="sxs-lookup"><span data-stu-id="1d99e-106">Installation</span></span>

<span data-ttu-id="1d99e-107">ネイティブ インストーラーを使用するか、インストール シェル スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-107">Either use the native installers or use the installation shell scripts:</span></span>

- <span data-ttu-id="1d99e-108">ネイティブ インストーラーは主に開発者のコンピューター上で使用され、それぞれサポートされるプラットフォームのネイティブ インストール メカニズムを使用します。たとえば、Ubuntu の場合は DEB パッケージ、Windows の場合は MSI バンドルを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="1d99e-109">これらのインストーラーでは、開発者がすぐに使用できる環境をインストールして構成します。ただし、コンピューターに対する管理者特権が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1d99e-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="1d99e-110">インストール手順は、[.NET Core のインストール ガイド](https://aka.ms/dotnetcoregs)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
- <span data-ttu-id="1d99e-111">シェル スクリプトは主に管理者特権なしでツールをインストールするときや、ビルド サーバーを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="1d99e-112">インストール スクリプトの場合、前提条件はインストールされないため、手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d99e-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="1d99e-113">詳細については、[インストール スクリプト参照](dotnet-install-script.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d99e-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="1d99e-114">継続的インテグレーション (CI) ビルド サーバーで CLI を設定する方法については、「[継続的インテグレーション (CI) で .NET Core SDK とツールを使用する](using-ci-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d99e-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="1d99e-115">既定では、CLI は SxS (side-by-side) 方式でインストールを実行するため、複数のバージョンの CLI ツールが 1 台のコンピューターで共存できます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="1d99e-116">複数のバージョンがインストールされたコンピューターで使用するバージョンの決定方法について詳しくは、「[ドライバー](#driver)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d99e-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="1d99e-117">CLI コマンド</span><span class="sxs-lookup"><span data-stu-id="1d99e-117">CLI commands</span></span>

<span data-ttu-id="1d99e-118">既定では、次のコマンドがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-118">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="1d99e-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="1d99e-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="1d99e-120">**基本的なコマンド**</span><span class="sxs-lookup"><span data-stu-id="1d99e-120">**Basic commands**</span></span>

- [<span data-ttu-id="1d99e-121">new</span><span class="sxs-lookup"><span data-stu-id="1d99e-121">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="1d99e-122">restore</span><span class="sxs-lookup"><span data-stu-id="1d99e-122">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="1d99e-123">build</span><span class="sxs-lookup"><span data-stu-id="1d99e-123">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="1d99e-124">publish</span><span class="sxs-lookup"><span data-stu-id="1d99e-124">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="1d99e-125">run</span><span class="sxs-lookup"><span data-stu-id="1d99e-125">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="1d99e-126">test</span><span class="sxs-lookup"><span data-stu-id="1d99e-126">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="1d99e-127">vstest</span><span class="sxs-lookup"><span data-stu-id="1d99e-127">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="1d99e-128">pack</span><span class="sxs-lookup"><span data-stu-id="1d99e-128">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="1d99e-129">migrate</span><span class="sxs-lookup"><span data-stu-id="1d99e-129">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="1d99e-130">clean</span><span class="sxs-lookup"><span data-stu-id="1d99e-130">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="1d99e-131">sln</span><span class="sxs-lookup"><span data-stu-id="1d99e-131">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="1d99e-132">help</span><span class="sxs-lookup"><span data-stu-id="1d99e-132">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="1d99e-133">store</span><span class="sxs-lookup"><span data-stu-id="1d99e-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="1d99e-134">**プロジェクトの変更コマンド**</span><span class="sxs-lookup"><span data-stu-id="1d99e-134">**Project modification commands**</span></span>

- [<span data-ttu-id="1d99e-135">add package</span><span class="sxs-lookup"><span data-stu-id="1d99e-135">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="1d99e-136">add reference</span><span class="sxs-lookup"><span data-stu-id="1d99e-136">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="1d99e-137">remove package</span><span class="sxs-lookup"><span data-stu-id="1d99e-137">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="1d99e-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="1d99e-138">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="1d99e-139">list reference</span><span class="sxs-lookup"><span data-stu-id="1d99e-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="1d99e-140">**高度なコマンド**</span><span class="sxs-lookup"><span data-stu-id="1d99e-140">**Advanced commands**</span></span>

- [<span data-ttu-id="1d99e-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="1d99e-141">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="1d99e-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="1d99e-142">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="1d99e-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="1d99e-143">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="1d99e-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="1d99e-144">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="1d99e-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="1d99e-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1d99e-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1d99e-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="1d99e-147">**基本的なコマンド**</span><span class="sxs-lookup"><span data-stu-id="1d99e-147">**Basic commands**</span></span>

- [<span data-ttu-id="1d99e-148">new</span><span class="sxs-lookup"><span data-stu-id="1d99e-148">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="1d99e-149">restore</span><span class="sxs-lookup"><span data-stu-id="1d99e-149">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="1d99e-150">build</span><span class="sxs-lookup"><span data-stu-id="1d99e-150">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="1d99e-151">publish</span><span class="sxs-lookup"><span data-stu-id="1d99e-151">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="1d99e-152">run</span><span class="sxs-lookup"><span data-stu-id="1d99e-152">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="1d99e-153">test</span><span class="sxs-lookup"><span data-stu-id="1d99e-153">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="1d99e-154">vstest</span><span class="sxs-lookup"><span data-stu-id="1d99e-154">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="1d99e-155">pack</span><span class="sxs-lookup"><span data-stu-id="1d99e-155">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="1d99e-156">migrate</span><span class="sxs-lookup"><span data-stu-id="1d99e-156">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="1d99e-157">clean</span><span class="sxs-lookup"><span data-stu-id="1d99e-157">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="1d99e-158">sln</span><span class="sxs-lookup"><span data-stu-id="1d99e-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="1d99e-159">**プロジェクトの変更コマンド**</span><span class="sxs-lookup"><span data-stu-id="1d99e-159">**Project modification commands**</span></span>

- [<span data-ttu-id="1d99e-160">add package</span><span class="sxs-lookup"><span data-stu-id="1d99e-160">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="1d99e-161">add reference</span><span class="sxs-lookup"><span data-stu-id="1d99e-161">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="1d99e-162">remove package</span><span class="sxs-lookup"><span data-stu-id="1d99e-162">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="1d99e-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="1d99e-163">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="1d99e-164">list reference</span><span class="sxs-lookup"><span data-stu-id="1d99e-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="1d99e-165">**高度なコマンド**</span><span class="sxs-lookup"><span data-stu-id="1d99e-165">**Advanced commands**</span></span>

- [<span data-ttu-id="1d99e-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="1d99e-166">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="1d99e-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="1d99e-167">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="1d99e-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="1d99e-168">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="1d99e-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="1d99e-169">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="1d99e-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="1d99e-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="1d99e-171">CLI では、プロジェクトに追加のツールを指定できるようにする拡張モデルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="1d99e-172">詳細については、「[.NET Core CLI の拡張モデル](extensibility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d99e-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="1d99e-173">コマンド構造</span><span class="sxs-lookup"><span data-stu-id="1d99e-173">Command structure</span></span>

<span data-ttu-id="1d99e-174">CLI コマンド構造は、[ドライバー ("dotnet")](#driver) と[コマンド](#command)、また場合によってはコマンドの[引数](#arguments)と[オプション](#options)で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="1d99e-175">*my_app* という名前のディレクトリから実行する場合、次のコマンドで示されているように、新しいコンソール アプリの作成やコマンド ラインからの実行など、ほとんどの CLI 操作でこのパターンが見られます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="1d99e-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="1d99e-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```console
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1d99e-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1d99e-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="1d99e-178">ドライバー</span><span class="sxs-lookup"><span data-stu-id="1d99e-178">Driver</span></span>

<span data-ttu-id="1d99e-179">ドライバーは [dotnet](dotnet.md) という名前で、2 つの役割 ([フレームワークに依存するアプリ](../deploying/index.md)の実行と、コマンドの実行) があります。</span><span class="sxs-lookup"><span data-stu-id="1d99e-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="1d99e-180">フレームワークに依存するアプリを実行するには、`dotnet /path/to/my_app.dll` など、ドライバーの後にアプリを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="1d99e-181">アプリの DLL が存在するフォルダーからコマンドを実行する場合は、`dotnet my_app.dll` を実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="1d99e-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="1d99e-182">.NET Core ランタイムの特定のバージョンを使用する場合は、`--fx-version <VERSION>` オプションを使用してください (「[dotnet コマンド](dotnet.md)」リファレンスを参照)。</span><span class="sxs-lookup"><span data-stu-id="1d99e-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="1d99e-183">ドライバーにコマンドを指定すると、`dotnet.exe` は CLI コマンドの実行プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="1d99e-184">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-184">For example:</span></span>

```bash
> dotnet build
```

<span data-ttu-id="1d99e-185">最初に、ドライバーは使用する SDK のバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="1d99e-186">['global.json'](global-json.md) がない場合は、利用可能な SDK の最新バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="1d99e-187">コンピューターで最新のプレビューまたは安定したバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="1d99e-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="1d99e-188">SDK バージョンが決定されたら、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="1d99e-189">コマンド</span><span class="sxs-lookup"><span data-stu-id="1d99e-189">Command</span></span>

<span data-ttu-id="1d99e-190">コマンドは、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-190">The command performs an action.</span></span> <span data-ttu-id="1d99e-191">たとえば、`dotnet build` はコードをビルドします。</span><span class="sxs-lookup"><span data-stu-id="1d99e-191">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="1d99e-192">`dotnet publish` はコードを発行します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-192">`dotnet publish` publishes code.</span></span> <span data-ttu-id="1d99e-193">コマンドは、`dotnet {command}` 規則を使用してコンソール アプリケーションとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-193">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="1d99e-194">引数</span><span class="sxs-lookup"><span data-stu-id="1d99e-194">Arguments</span></span>

<span data-ttu-id="1d99e-195">コマンド ラインで渡す引数は、呼び出されたコマンドへの引数です。</span><span class="sxs-lookup"><span data-stu-id="1d99e-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="1d99e-196">たとえば、`dotnet publish my_app.csproj` を実行した場合、`my_app.csproj` 引数は、発行するプロジェクトを示し、`publish` コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="1d99e-197">オプション</span><span class="sxs-lookup"><span data-stu-id="1d99e-197">Options</span></span>

<span data-ttu-id="1d99e-198">コマンド ラインで渡すオプションは、呼び出されたコマンドへのオプションです。</span><span class="sxs-lookup"><span data-stu-id="1d99e-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="1d99e-199">たとえば、`dotnet publish --output /build_output` を実行した場合、`--output` オプションとその値は `publish` コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="1d99e-200">project.json からの移行</span><span class="sxs-lookup"><span data-stu-id="1d99e-200">Migration from project.json</span></span>

<span data-ttu-id="1d99e-201">Preview 2 ツールを使用して *project.json* ベースのプロジェクトを生成した場合は、リリース ツールで使用するための MSBuild/ *.csproj* へのプロジェクトの移行について、「[dotnet-migrate](dotnet-migrate.md)」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d99e-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="1d99e-202">Preview 2 ツールのリリースの前に作成された .NET Core プロジェクトの場合は、「[DNX から .NET Core CLI への移行 (project.json)](../migration/from-dnx.md)」のガイダンスに従って手動でプロジェクトを更新してから `dotnet migrate` を使用するか、プロジェクトを直接アップグレードします。</span><span class="sxs-lookup"><span data-stu-id="1d99e-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d99e-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d99e-203">See also</span></span>

- [<span data-ttu-id="1d99e-204">dotnet/CLI GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="1d99e-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- [<span data-ttu-id="1d99e-205">.NET Core のインストール ガイド</span><span class="sxs-lookup"><span data-stu-id="1d99e-205">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
