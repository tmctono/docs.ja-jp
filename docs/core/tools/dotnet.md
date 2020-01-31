---
title: dotnet コマンド
description: dotnet コマンド (.NET Core CLI ツールの一般的なドライバー) とその使用法について説明します。
ms.date: 06/04/2018
ms.openlocfilehash: fe90968560b58471c279fcd2097741ea476cef0b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734066"
---
# <a name="dotnet-command"></a><span data-ttu-id="66113-103">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="66113-104">名前</span><span class="sxs-lookup"><span data-stu-id="66113-104">Name</span></span>

<span data-ttu-id="66113-105">`dotnet` - .NET のソース コードとバイナリを管理するためのツール。</span><span class="sxs-lookup"><span data-stu-id="66113-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="66113-106">構文</span><span class="sxs-lookup"><span data-stu-id="66113-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="66113-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="66113-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="66113-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="66113-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="66113-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="66113-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="66113-110">説明</span><span class="sxs-lookup"><span data-stu-id="66113-110">Description</span></span>

<span data-ttu-id="66113-111">`dotnet` は .NET のソース コードとバイナリを管理するためのツールです。</span><span class="sxs-lookup"><span data-stu-id="66113-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="66113-112">[`dotnet build`](dotnet-build.md) や [`dotnet run`](dotnet-run.md) のような特定のタスクを実行するコマンドを公開します。</span><span class="sxs-lookup"><span data-stu-id="66113-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="66113-113">各コマンドによって、それ自体の引数が定義されます。</span><span class="sxs-lookup"><span data-stu-id="66113-113">Each command defines its own arguments.</span></span> <span data-ttu-id="66113-114">各コマンドの後ろに `--help` と入力すると、短いヘルプ ドキュメントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="66113-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="66113-115">`dotnet` は、`dotnet myapp.dll` など、アプリケーション DLL を指定することで、アプリケーションを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="66113-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="66113-116">展開オプションについては、「[.NET Core アプリケーションの展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="66113-117">オプション</span><span class="sxs-lookup"><span data-stu-id="66113-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="66113-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="66113-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="66113-119">追加の *.deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66113-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="66113-120">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="66113-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="66113-121">*deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66113-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="66113-122">*deps.json* ファイルには、依存関係、コンパイル依存関係、アセンブリ競合に対処するためのバージョン情報の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="66113-122">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="66113-123">このファイルの詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="66113-124">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="66113-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="66113-125">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="66113-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="66113-126">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="66113-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="66113-127">`dotnet --help` では、使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="66113-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="66113-128">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="66113-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="66113-129">インストールされている .NET Core ランタイムを表示します。</span><span class="sxs-lookup"><span data-stu-id="66113-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="66113-130">インストールされている .NET Core SDK を表示します。</span><span class="sxs-lookup"><span data-stu-id="66113-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="66113-131">必要な共有フレームワークが利用できない場合の動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="66113-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="66113-132">`N` には以下があります。</span><span class="sxs-lookup"><span data-stu-id="66113-132">`N` can be:</span></span>

- <span data-ttu-id="66113-133">`0` - マイナー バージョンのロールフォワードでも無効にします。</span><span class="sxs-lookup"><span data-stu-id="66113-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="66113-134">`1` - マイナー バージョンはロール フォワードしますが、メジャー バージョンはしません。</span><span class="sxs-lookup"><span data-stu-id="66113-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="66113-135">これが既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="66113-135">This is the default behavior.</span></span>
- <span data-ttu-id="66113-136">`2` - マイナー バージョンとメジャー バージョンをロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="66113-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="66113-137">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="66113-138">*runtimeconfig.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66113-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="66113-139">*runtimeconfig.json* ファイルは、ランタイム設定を含む構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="66113-139">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="66113-140">詳細については、「[.NET Core ランタイム構成設定](../run-time-config/index.md#runtimeconfigjson)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-140">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="66113-141">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="66113-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="66113-142">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="66113-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="66113-143">一部のコマンドではサポートされていません。このオプションが使用可能かどうかを判断するには、対象のコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="66113-144">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="66113-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="66113-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="66113-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="66113-146">追加の *.deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66113-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="66113-147">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="66113-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="66113-148">*deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66113-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="66113-149">*deps.json* ファイルには、依存関係、コンパイル依存関係、アセンブリ競合に対処するためのバージョン情報の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="66113-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="66113-150">このファイルの詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="66113-151">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="66113-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="66113-152">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="66113-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="66113-153">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="66113-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="66113-154">`dotnet --help` では、使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="66113-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="66113-155">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="66113-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="66113-156">`0` に設定されている場合、マイナー バージョンのロールフォワードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="66113-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="66113-157">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="66113-158">*runtimeconfig.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66113-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="66113-159">*runtimeconfig.json* ファイルは、ランタイム設定を含む構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="66113-159">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="66113-160">詳細については、「[.NET Core ランタイム構成設定](../run-time-config/index.md#runtimeconfigjson)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-160">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="66113-161">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="66113-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="66113-162">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="66113-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="66113-163">一部のコマンドではサポートされていません。このオプションが使用可能かどうかを判断するには、対象のコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="66113-164">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="66113-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="66113-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="66113-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="66113-166">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="66113-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="66113-167">*deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66113-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="66113-168">*deps.json* ファイルには、依存関係、コンパイル依存関係、アセンブリ競合に対処するためのバージョン情報の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="66113-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="66113-169">このファイルの詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="66113-170">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="66113-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="66113-171">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="66113-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="66113-172">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="66113-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="66113-173">`dotnet --help` では、使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="66113-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="66113-174">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="66113-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="66113-175">*runtimeconfig.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="66113-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="66113-176">*runtimeconfig.json* ファイルは、ランタイム設定を含む構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="66113-176">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="66113-177">詳細については、「[.NET Core ランタイム構成設定](../run-time-config/index.md#runtimeconfigjson)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-177">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="66113-178">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="66113-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="66113-179">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="66113-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="66113-180">一部のコマンドではサポートされていません。このオプションが使用可能かどうかを判断するには、対象のコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="66113-181">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="66113-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="66113-182">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="66113-183">全般</span><span class="sxs-lookup"><span data-stu-id="66113-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="66113-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="66113-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="66113-185">コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-185">Command</span></span>                                       | <span data-ttu-id="66113-186">関数</span><span class="sxs-lookup"><span data-stu-id="66113-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="66113-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="66113-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="66113-188">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="66113-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="66113-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="66113-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="66113-190">ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="66113-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="66113-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="66113-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="66113-192">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="66113-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="66113-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="66113-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="66113-194">コマンドのより詳細なドキュメントをオンラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="66113-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="66113-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="66113-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="66113-196">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="66113-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="66113-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="66113-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="66113-198">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="66113-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="66113-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="66113-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="66113-200">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="66113-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="66113-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="66113-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="66113-202">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66113-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="66113-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="66113-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="66113-204">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="66113-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="66113-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="66113-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="66113-206">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="66113-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="66113-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="66113-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="66113-208">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="66113-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="66113-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="66113-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="66113-210">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="66113-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="66113-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="66113-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="66113-212">ランタイム パッケージ ストアにアセンブリを格納します。</span><span class="sxs-lookup"><span data-stu-id="66113-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="66113-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="66113-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="66113-214">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="66113-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="66113-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="66113-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="66113-216">コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-216">Command</span></span>                             | <span data-ttu-id="66113-217">関数</span><span class="sxs-lookup"><span data-stu-id="66113-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="66113-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="66113-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="66113-219">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="66113-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="66113-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="66113-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="66113-221">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="66113-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="66113-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="66113-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="66113-223">コマンドのより詳細なドキュメントをオンラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="66113-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="66113-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="66113-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="66113-225">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="66113-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="66113-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="66113-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="66113-227">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="66113-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="66113-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="66113-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="66113-229">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="66113-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="66113-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="66113-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="66113-231">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66113-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="66113-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="66113-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="66113-233">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="66113-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="66113-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="66113-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="66113-235">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="66113-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="66113-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="66113-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="66113-237">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="66113-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="66113-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="66113-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="66113-239">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="66113-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="66113-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="66113-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="66113-241">ランタイム パッケージ ストアにアセンブリを格納します。</span><span class="sxs-lookup"><span data-stu-id="66113-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="66113-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="66113-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="66113-243">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="66113-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="66113-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="66113-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="66113-245">コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-245">Command</span></span>                             | <span data-ttu-id="66113-246">関数</span><span class="sxs-lookup"><span data-stu-id="66113-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="66113-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="66113-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="66113-248">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="66113-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="66113-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="66113-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="66113-250">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="66113-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="66113-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="66113-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="66113-252">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="66113-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="66113-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="66113-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="66113-254">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="66113-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="66113-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="66113-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="66113-256">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="66113-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="66113-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="66113-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="66113-258">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66113-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="66113-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="66113-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="66113-260">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="66113-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="66113-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="66113-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="66113-262">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="66113-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="66113-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="66113-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="66113-264">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="66113-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="66113-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="66113-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="66113-266">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="66113-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="66113-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="66113-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="66113-268">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="66113-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="66113-269">プロジェクト参照</span><span class="sxs-lookup"><span data-stu-id="66113-269">Project references</span></span>

<span data-ttu-id="66113-270">コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-270">Command</span></span> | <span data-ttu-id="66113-271">関数</span><span class="sxs-lookup"><span data-stu-id="66113-271">Function</span></span>
--- | ---
[<span data-ttu-id="66113-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="66113-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="66113-273">プロジェクト参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="66113-273">Adds a project reference.</span></span>
[<span data-ttu-id="66113-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="66113-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="66113-275">プロジェクト参照をリストします。</span><span class="sxs-lookup"><span data-stu-id="66113-275">Lists project references.</span></span>
[<span data-ttu-id="66113-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="66113-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="66113-277">プロジェクト参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="66113-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="66113-278">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="66113-278">NuGet packages</span></span>

<span data-ttu-id="66113-279">コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-279">Command</span></span> | <span data-ttu-id="66113-280">関数</span><span class="sxs-lookup"><span data-stu-id="66113-280">Function</span></span>
--- | ---
[<span data-ttu-id="66113-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="66113-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="66113-282">NuGet パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="66113-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="66113-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="66113-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="66113-284">NuGet パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="66113-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="66113-285">NuGet コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-285">NuGet commands</span></span>

<span data-ttu-id="66113-286">コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-286">Command</span></span> | <span data-ttu-id="66113-287">関数</span><span class="sxs-lookup"><span data-stu-id="66113-287">Function</span></span>
--- | ---
[<span data-ttu-id="66113-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="66113-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="66113-289">サーバーからパッケージを削除または一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="66113-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="66113-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="66113-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="66113-291">HTTP 要求キャッシュ、一時的なキャッシュ、コンピューター全体のグローバル パッケージ フォルダーなどのローカルの NuGet リソースをクリアまたは一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="66113-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="66113-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="66113-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="66113-293">パッケージをサーバーにプッシュして発行します。</span><span class="sxs-lookup"><span data-stu-id="66113-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="66113-294">グローバル ツール コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-294">Global Tools commands</span></span>

<span data-ttu-id="66113-295">[.NET Core グローバル ツール](global-tools.md)は .NET Core SDK 2.1.300 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="66113-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="66113-296">コマンド</span><span class="sxs-lookup"><span data-stu-id="66113-296">Command</span></span> | <span data-ttu-id="66113-297">関数</span><span class="sxs-lookup"><span data-stu-id="66113-297">Function</span></span>
--- | ---
[<span data-ttu-id="66113-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="66113-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="66113-299">グローバル ツールをマシンにインストールします。</span><span class="sxs-lookup"><span data-stu-id="66113-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="66113-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="66113-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="66113-301">マシン上の既定のディレクトリまたは指定したパスに現在インストールされているすべてのグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="66113-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="66113-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="66113-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="66113-303">グローバル ツールをマシンからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="66113-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="66113-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="66113-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="66113-305">マシン上のグローバル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="66113-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="66113-306">その他のツール</span><span class="sxs-lookup"><span data-stu-id="66113-306">Additional tools</span></span>

<span data-ttu-id="66113-307">.NET Core SDK 2.1.300 以降では、`DotnetCliToolReference` を使用してプロジェクト単位でのみ入手可能であった複数のツールを .NET Core SDK の一部として入手できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="66113-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="66113-308">これらのツールを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="66113-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="66113-309">ツール</span><span class="sxs-lookup"><span data-stu-id="66113-309">Tool</span></span>                                              | <span data-ttu-id="66113-310">関数</span><span class="sxs-lookup"><span data-stu-id="66113-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="66113-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="66113-311">dev-certs</span></span>                                         | <span data-ttu-id="66113-312">開発証明書を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="66113-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="66113-313">ef</span><span class="sxs-lookup"><span data-stu-id="66113-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="66113-314">Entity Framework Core コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="66113-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="66113-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="66113-315">sql-cache</span></span>                                         | <span data-ttu-id="66113-316">SQL Server キャッシュ コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="66113-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="66113-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="66113-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="66113-318">開発ユーザーのシークレットを管理します。</span><span class="sxs-lookup"><span data-stu-id="66113-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="66113-319">watch</span><span class="sxs-lookup"><span data-stu-id="66113-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="66113-320">ファイルが変化するとコマンドを実行するファイル ウォッチャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="66113-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="66113-321">各ツールの詳細については、`dotnet <tool-name> --help` と入力してください。</span><span class="sxs-lookup"><span data-stu-id="66113-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="66113-322">使用例</span><span class="sxs-lookup"><span data-stu-id="66113-322">Examples</span></span>

<span data-ttu-id="66113-323">新しい .NET Core コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="66113-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="66113-324">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="66113-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="66113-325">指定されたディレクトリにプロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="66113-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="66113-326">`myapp.dll` など、アプリケーション DLL を実行します。</span><span class="sxs-lookup"><span data-stu-id="66113-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="66113-327">環境変数</span><span class="sxs-lookup"><span data-stu-id="66113-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="66113-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="66113-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="66113-329">グローバル パッケージ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="66113-329">The global packages folder.</span></span> <span data-ttu-id="66113-330">設定されていない場合は、既定で `~/.nuget/packages` (Unix の場合) または `%userprofile%\.nuget\packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="66113-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="66113-331">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="66113-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="66113-332">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="66113-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="66113-333">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="66113-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="66113-334">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="66113-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="66113-335">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="66113-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="66113-336">.NET Core ランタイム、共有フレームワーク、または SDK がグローバルな場所から解決されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="66113-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="66113-337">設定されていない場合は、既定で `true` になります。</span><span class="sxs-lookup"><span data-stu-id="66113-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="66113-338">`false` に設定すると、グローバルな場所から解決されず、.NET Core インストールが分離されます (値 `0` または `false` が受け入れられます)。</span><span class="sxs-lookup"><span data-stu-id="66113-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="66113-339">複数レベルのルックアップの詳細については、「[Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)」 (複数レベルの SharedFX ルックアップ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="66113-340">`0` に設定されている場合、マイナー バージョンのロールフォワードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="66113-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="66113-341">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="66113-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="66113-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="66113-343">プライマリ パッケージのキャッシュです。</span><span class="sxs-lookup"><span data-stu-id="66113-343">The primary package cache.</span></span> <span data-ttu-id="66113-344">設定されていない場合は、既定で `$HOME/.nuget/packages` (Unix の場合) または `%userprofile%\.nuget\packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="66113-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="66113-345">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="66113-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="66113-346">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="66113-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="66113-347">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="66113-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="66113-348">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="66113-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="66113-349">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="66113-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="66113-350">.NET Core ランタイム、共有フレームワーク、または SDK がグローバルな場所から解決されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="66113-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="66113-351">設定されていない場合は、既定で `true` になります。</span><span class="sxs-lookup"><span data-stu-id="66113-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="66113-352">`false` に設定すると、グローバルな場所から解決されず、.NET Core インストールが分離されます (値 `0` または `false` が受け入れられます)。</span><span class="sxs-lookup"><span data-stu-id="66113-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="66113-353">複数レベルのルックアップの詳細については、「[Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)」 (複数レベルの SharedFX ルックアップ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66113-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="66113-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="66113-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="66113-355">プライマリ パッケージのキャッシュです。</span><span class="sxs-lookup"><span data-stu-id="66113-355">The primary package cache.</span></span> <span data-ttu-id="66113-356">設定されていない場合は、既定で `$HOME/.nuget/packages` (Unix の場合) または `%userprofile%\.nuget\packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="66113-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="66113-357">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="66113-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="66113-358">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="66113-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="66113-359">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="66113-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="66113-360">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="66113-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="66113-361">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="66113-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="66113-362">関連項目</span><span class="sxs-lookup"><span data-stu-id="66113-362">See also</span></span>

- [<span data-ttu-id="66113-363">ランタイム構成ファイル</span><span class="sxs-lookup"><span data-stu-id="66113-363">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="66113-364">.NET Core ランタイム構成設定</span><span class="sxs-lookup"><span data-stu-id="66113-364">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
