---
title: .NET Core CLI
titleSuffix: ''
description: .NET Core CLI とその機能に関する概要です。
ms.date: 02/13/2020
ms.openlocfilehash: 1078d68ddc088274fa14b0094a81765f7af69dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543315"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="2df6d-103">.NET Core CLI の概要</span><span class="sxs-lookup"><span data-stu-id="2df6d-103">.NET Core CLI overview</span></span>

<span data-ttu-id="2df6d-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="2df6d-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="2df6d-105">.NET Core コマンド ライン インターフェイス (CLI) は、.NET Core アプリケーションを開発、ビルド、実行、発行するためのクロスプラットフォーム ツールチェーンです。</span><span class="sxs-lookup"><span data-stu-id="2df6d-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="2df6d-106">.NET Core CLI は、[.NET Core SDK](../sdk.md) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="2df6d-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="2df6d-107">.NET Core SDK をインストールする方法については、「[.NET Core SDK をインストールする](../install/sdk.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2df6d-107">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="2df6d-108">CLI コマンド</span><span class="sxs-lookup"><span data-stu-id="2df6d-108">CLI commands</span></span>

<span data-ttu-id="2df6d-109">既定では、次のコマンドがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2df6d-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="2df6d-110">基本的なコマンド</span><span class="sxs-lookup"><span data-stu-id="2df6d-110">Basic commands</span></span>

- [<span data-ttu-id="2df6d-111">new</span><span class="sxs-lookup"><span data-stu-id="2df6d-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="2df6d-112">restore</span><span class="sxs-lookup"><span data-stu-id="2df6d-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="2df6d-113">build</span><span class="sxs-lookup"><span data-stu-id="2df6d-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="2df6d-114">publish</span><span class="sxs-lookup"><span data-stu-id="2df6d-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="2df6d-115">run</span><span class="sxs-lookup"><span data-stu-id="2df6d-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="2df6d-116">test</span><span class="sxs-lookup"><span data-stu-id="2df6d-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="2df6d-117">vstest</span><span class="sxs-lookup"><span data-stu-id="2df6d-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="2df6d-118">pack</span><span class="sxs-lookup"><span data-stu-id="2df6d-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="2df6d-119">migrate</span><span class="sxs-lookup"><span data-stu-id="2df6d-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="2df6d-120">clean</span><span class="sxs-lookup"><span data-stu-id="2df6d-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="2df6d-121">sln</span><span class="sxs-lookup"><span data-stu-id="2df6d-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="2df6d-122">help</span><span class="sxs-lookup"><span data-stu-id="2df6d-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="2df6d-123">store</span><span class="sxs-lookup"><span data-stu-id="2df6d-123">store</span></span>](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="2df6d-124">プロジェクトの変更コマンド</span><span class="sxs-lookup"><span data-stu-id="2df6d-124">Project modification commands</span></span>

- [<span data-ttu-id="2df6d-125">add package</span><span class="sxs-lookup"><span data-stu-id="2df6d-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="2df6d-126">add reference</span><span class="sxs-lookup"><span data-stu-id="2df6d-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="2df6d-127">remove package</span><span class="sxs-lookup"><span data-stu-id="2df6d-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="2df6d-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="2df6d-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="2df6d-129">list reference</span><span class="sxs-lookup"><span data-stu-id="2df6d-129">list reference</span></span>](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="2df6d-130">高度なコマンド</span><span class="sxs-lookup"><span data-stu-id="2df6d-130">Advanced commands</span></span>

- [<span data-ttu-id="2df6d-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="2df6d-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="2df6d-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="2df6d-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="2df6d-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="2df6d-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="2df6d-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="2df6d-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="2df6d-135">dotnet install スクリプト</span><span class="sxs-lookup"><span data-stu-id="2df6d-135">dotnet install script</span></span>](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="2df6d-136">ツール管理コマンド</span><span class="sxs-lookup"><span data-stu-id="2df6d-136">Tool management commands</span></span>

- [<span data-ttu-id="2df6d-137">tool install</span><span class="sxs-lookup"><span data-stu-id="2df6d-137">tool install</span></span>](dotnet-tool-install.md)
- [<span data-ttu-id="2df6d-138">tool list</span><span class="sxs-lookup"><span data-stu-id="2df6d-138">tool list</span></span>](dotnet-tool-list.md)
- [<span data-ttu-id="2df6d-139">tool update</span><span class="sxs-lookup"><span data-stu-id="2df6d-139">tool update</span></span>](dotnet-tool-update.md)
- <span data-ttu-id="2df6d-140">[tool restore](global-tools.md#install-a-local-tool) **.NET Core SDK 3.0 以降で使用可能**</span><span class="sxs-lookup"><span data-stu-id="2df6d-140">[tool restore](global-tools.md#install-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- <span data-ttu-id="2df6d-141">[tool run](global-tools.md#invoke-a-local-tool) **.NET Core SDK 3.0 以降で使用可能**</span><span class="sxs-lookup"><span data-stu-id="2df6d-141">[tool run](global-tools.md#invoke-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- [<span data-ttu-id="2df6d-142">tool uninstall</span><span class="sxs-lookup"><span data-stu-id="2df6d-142">tool uninstall</span></span>](dotnet-tool-uninstall.md)

<span data-ttu-id="2df6d-143">ツールは、NuGet パッケージからインストールされ、コマンド プロンプトから呼び出されるコンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="2df6d-143">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="2df6d-144">ツールは自分で作成することも、サードパーティによって作成されたツールをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2df6d-144">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="2df6d-145">ツールは、グローバル ツール、ツールパス ツール、およびローカル ツールとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2df6d-145">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="2df6d-146">詳細については、[.NET Core ツールの概要](global-tools.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2df6d-146">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="2df6d-147">コマンド構造</span><span class="sxs-lookup"><span data-stu-id="2df6d-147">Command structure</span></span>

<span data-ttu-id="2df6d-148">CLI コマンド構造は、[ドライバー ("dotnet")](#driver) と[コマンド](#command)、また場合によってはコマンドの[引数](#arguments)と[オプション](#options)で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2df6d-148">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="2df6d-149">*my_app* という名前のディレクトリから実行する場合、次のコマンドで示されているように、新しいコンソール アプリの作成やコマンド ラインからの実行など、ほとんどの CLI 操作でこのパターンが見られます。</span><span class="sxs-lookup"><span data-stu-id="2df6d-149">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="2df6d-150">ドライバー</span><span class="sxs-lookup"><span data-stu-id="2df6d-150">Driver</span></span>

<span data-ttu-id="2df6d-151">ドライバーは [dotnet](dotnet.md) という名前で、2 つの役割 ([フレームワークに依存するアプリ](../deploying/index.md)の実行と、コマンドの実行) があります。</span><span class="sxs-lookup"><span data-stu-id="2df6d-151">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="2df6d-152">フレームワークに依存するアプリを実行するには、`dotnet /path/to/my_app.dll` など、ドライバーの後にアプリを指定します。</span><span class="sxs-lookup"><span data-stu-id="2df6d-152">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="2df6d-153">アプリの DLL が存在するフォルダーからコマンドを実行する場合は、`dotnet my_app.dll` を実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="2df6d-153">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="2df6d-154">.NET Core ランタイムの特定のバージョンを使用する場合は、`--fx-version <VERSION>` オプションを使用してください (「[dotnet コマンド](dotnet.md)」リファレンスを参照)。</span><span class="sxs-lookup"><span data-stu-id="2df6d-154">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="2df6d-155">ドライバーにコマンドを指定すると、`dotnet.exe` は CLI コマンドの実行プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="2df6d-155">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="2df6d-156">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2df6d-156">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="2df6d-157">最初に、ドライバーは使用する SDK のバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="2df6d-157">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="2df6d-158">['global.json'](global-json.md) がない場合は、利用可能な SDK の最新バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="2df6d-158">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="2df6d-159">コンピューターで最新のプレビューまたは安定したバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="2df6d-159">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="2df6d-160">SDK バージョンが決定されたら、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2df6d-160">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="2df6d-161">コマンド</span><span class="sxs-lookup"><span data-stu-id="2df6d-161">Command</span></span>

<span data-ttu-id="2df6d-162">コマンドは、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2df6d-162">The command performs an action.</span></span> <span data-ttu-id="2df6d-163">たとえば、`dotnet build` はコードをビルドします。</span><span class="sxs-lookup"><span data-stu-id="2df6d-163">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="2df6d-164">`dotnet publish` はコードを発行します。</span><span class="sxs-lookup"><span data-stu-id="2df6d-164">`dotnet publish` publishes code.</span></span> <span data-ttu-id="2df6d-165">コマンドは、`dotnet {command}` 規則を使用してコンソール アプリケーションとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="2df6d-165">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="2df6d-166">引数</span><span class="sxs-lookup"><span data-stu-id="2df6d-166">Arguments</span></span>

<span data-ttu-id="2df6d-167">コマンド ラインで渡す引数は、呼び出されたコマンドへの引数です。</span><span class="sxs-lookup"><span data-stu-id="2df6d-167">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="2df6d-168">たとえば、`dotnet publish my_app.csproj` を実行した場合、`my_app.csproj` 引数は、発行するプロジェクトを示し、`publish` コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="2df6d-168">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="2df6d-169">オプション</span><span class="sxs-lookup"><span data-stu-id="2df6d-169">Options</span></span>

<span data-ttu-id="2df6d-170">コマンド ラインで渡すオプションは、呼び出されたコマンドへのオプションです。</span><span class="sxs-lookup"><span data-stu-id="2df6d-170">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="2df6d-171">たとえば、`dotnet publish --output /build_output` を実行した場合、`--output` オプションとその値は `publish` コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="2df6d-171">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="2df6d-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="2df6d-172">See also</span></span>

- [<span data-ttu-id="2df6d-173">dotnet/sdk GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="2df6d-173">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="2df6d-174">.NET Core のインストール ガイド</span><span class="sxs-lookup"><span data-stu-id="2df6d-174">.NET Core installation guide</span></span>](../install/sdk.md)
