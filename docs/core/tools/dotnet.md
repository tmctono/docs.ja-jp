---
title: dotnet コマンド
description: dotnet コマンド (.NET Core CLI ツールの一般的なドライバー) とその使用法について説明します。
ms.date: 06/04/2018
ms.openlocfilehash: 61542a3fff8bba6e2c3e55a4db5a746620d79ca1
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202510"
---
# <a name="dotnet-command"></a><span data-ttu-id="991c7-103">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="991c7-104">name</span><span class="sxs-lookup"><span data-stu-id="991c7-104">Name</span></span>

<span data-ttu-id="991c7-105">`dotnet` - .NET のソース コードとバイナリを管理するためのツール。</span><span class="sxs-lookup"><span data-stu-id="991c7-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="991c7-106">構文</span><span class="sxs-lookup"><span data-stu-id="991c7-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="991c7-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="991c7-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="991c7-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="991c7-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="991c7-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="991c7-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="991c7-110">説明</span><span class="sxs-lookup"><span data-stu-id="991c7-110">Description</span></span>

<span data-ttu-id="991c7-111">`dotnet` は .NET のソース コードとバイナリを管理するためのツールです。</span><span class="sxs-lookup"><span data-stu-id="991c7-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="991c7-112">[`dotnet build`](dotnet-build.md) や [`dotnet run`](dotnet-run.md) のような特定のタスクを実行するコマンドを公開します。</span><span class="sxs-lookup"><span data-stu-id="991c7-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="991c7-113">各コマンドによって、それ自体の引数が定義されます。</span><span class="sxs-lookup"><span data-stu-id="991c7-113">Each command defines its own arguments.</span></span> <span data-ttu-id="991c7-114">各コマンドの後ろに `--help` と入力すると、短いヘルプ ドキュメントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="991c7-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="991c7-115">`dotnet` は、`dotnet myapp.dll` など、アプリケーション DLL を指定することで、アプリケーションを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="991c7-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="991c7-116">展開オプションについては、「[.NET Core アプリケーションの展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="991c7-117">オプション</span><span class="sxs-lookup"><span data-stu-id="991c7-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="991c7-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="991c7-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="991c7-119">追加の *.deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="991c7-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="991c7-120">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="991c7-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="991c7-121">*deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="991c7-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="991c7-122">*deps.json* ファイルには、依存関係、コンパイル依存関係、アセンブリ競合に対処するためのバージョン情報の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="991c7-122">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="991c7-123">このファイルの詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="991c7-124">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="991c7-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="991c7-125">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="991c7-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="991c7-126">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="991c7-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="991c7-127">`dotnet --help` では、使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="991c7-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="991c7-128">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="991c7-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="991c7-129">インストールされている .NET Core ランタイムを表示します。</span><span class="sxs-lookup"><span data-stu-id="991c7-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="991c7-130">インストールされている .NET Core SDK を表示します。</span><span class="sxs-lookup"><span data-stu-id="991c7-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="991c7-131">必要な共有フレームワークが利用できない場合の動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="991c7-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="991c7-132">`N` には以下があります。</span><span class="sxs-lookup"><span data-stu-id="991c7-132">`N` can be:</span></span>
* <span data-ttu-id="991c7-133">`0` - マイナー バージョンのロールフォワードでも無効にします。</span><span class="sxs-lookup"><span data-stu-id="991c7-133">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="991c7-134">`1` - マイナー バージョンはロール フォワードしますが、メジャー バージョンはしません。</span><span class="sxs-lookup"><span data-stu-id="991c7-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="991c7-135">これが既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="991c7-135">This is the default behavior.</span></span>
* <span data-ttu-id="991c7-136">`2` - マイナー バージョンとメジャー バージョンをロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="991c7-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="991c7-137">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="991c7-138">*runtimeconfig.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="991c7-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="991c7-139">*runtimeconfig.json* ファイルは、ランタイム構成設定が含まれる構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="991c7-139">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="991c7-140">詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-140">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="991c7-141">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="991c7-142">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="991c7-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="991c7-143">一部のコマンドではサポートされていません。このオプションが使用可能かどうかを判断するには、対象のコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="991c7-144">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="991c7-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="991c7-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="991c7-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="991c7-146">追加の *.deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="991c7-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="991c7-147">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="991c7-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="991c7-148">*deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="991c7-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="991c7-149">*deps.json* ファイルには、依存関係、コンパイル依存関係、アセンブリ競合に対処するためのバージョン情報の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="991c7-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="991c7-150">このファイルの詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="991c7-151">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="991c7-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="991c7-152">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="991c7-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="991c7-153">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="991c7-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="991c7-154">`dotnet --help` では、使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="991c7-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="991c7-155">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="991c7-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="991c7-156">`0` に設定されている場合、マイナー バージョンのロールフォワードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="991c7-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="991c7-157">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="991c7-158">*runtimeconfig.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="991c7-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="991c7-159">*runtimeconfig.json* ファイルは、ランタイム構成設定が含まれる構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="991c7-159">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="991c7-160">詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-160">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="991c7-161">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="991c7-162">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="991c7-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="991c7-163">一部のコマンドではサポートされていません。このオプションが使用可能かどうかを判断するには、対象のコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="991c7-164">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="991c7-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="991c7-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="991c7-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="991c7-166">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="991c7-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="991c7-167">*deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="991c7-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="991c7-168">*deps.json* ファイルには、依存関係、コンパイル依存関係、アセンブリ競合に対処するためのバージョン情報の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="991c7-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="991c7-169">このファイルの詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="991c7-170">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="991c7-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="991c7-171">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="991c7-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="991c7-172">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="991c7-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="991c7-173">`dotnet --help` では、使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="991c7-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="991c7-174">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="991c7-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="991c7-175">*runtimeconfig.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="991c7-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="991c7-176">*runtimeconfig.json* ファイルは、ランタイム構成設定が含まれる構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="991c7-176">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="991c7-177">詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-177">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="991c7-178">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="991c7-179">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="991c7-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="991c7-180">一部のコマンドではサポートされていません。このオプションが使用可能かどうかを判断するには、対象のコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="991c7-181">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="991c7-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="991c7-182">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="991c7-183">全般</span><span class="sxs-lookup"><span data-stu-id="991c7-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="991c7-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="991c7-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="991c7-185">コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-185">Command</span></span>                                       | <span data-ttu-id="991c7-186">関数</span><span class="sxs-lookup"><span data-stu-id="991c7-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="991c7-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="991c7-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="991c7-188">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="991c7-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="991c7-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="991c7-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="991c7-190">ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="991c7-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="991c7-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="991c7-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="991c7-192">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="991c7-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="991c7-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="991c7-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="991c7-194">コマンドのより詳細なドキュメントをオンラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="991c7-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="991c7-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="991c7-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="991c7-196">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="991c7-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="991c7-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="991c7-198">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="991c7-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="991c7-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="991c7-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="991c7-200">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="991c7-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="991c7-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="991c7-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="991c7-202">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="991c7-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="991c7-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="991c7-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="991c7-204">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="991c7-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="991c7-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="991c7-206">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="991c7-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="991c7-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="991c7-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="991c7-208">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="991c7-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="991c7-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="991c7-210">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="991c7-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="991c7-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="991c7-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="991c7-212">ランタイム パッケージ ストアにアセンブリを格納します。</span><span class="sxs-lookup"><span data-stu-id="991c7-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="991c7-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="991c7-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="991c7-214">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="991c7-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="991c7-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="991c7-216">コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-216">Command</span></span>                             | <span data-ttu-id="991c7-217">関数</span><span class="sxs-lookup"><span data-stu-id="991c7-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="991c7-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="991c7-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="991c7-219">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="991c7-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="991c7-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="991c7-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="991c7-221">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="991c7-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="991c7-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="991c7-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="991c7-223">コマンドのより詳細なドキュメントをオンラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="991c7-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="991c7-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="991c7-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="991c7-225">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="991c7-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="991c7-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="991c7-227">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="991c7-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="991c7-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="991c7-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="991c7-229">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="991c7-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="991c7-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="991c7-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="991c7-231">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="991c7-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="991c7-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="991c7-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="991c7-233">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="991c7-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="991c7-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="991c7-235">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="991c7-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="991c7-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="991c7-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="991c7-237">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="991c7-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="991c7-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="991c7-239">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="991c7-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="991c7-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="991c7-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="991c7-241">ランタイム パッケージ ストアにアセンブリを格納します。</span><span class="sxs-lookup"><span data-stu-id="991c7-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="991c7-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="991c7-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="991c7-243">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="991c7-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="991c7-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="991c7-245">コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-245">Command</span></span>                             | <span data-ttu-id="991c7-246">関数</span><span class="sxs-lookup"><span data-stu-id="991c7-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="991c7-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="991c7-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="991c7-248">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="991c7-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="991c7-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="991c7-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="991c7-250">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="991c7-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="991c7-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="991c7-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="991c7-252">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="991c7-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="991c7-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="991c7-254">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="991c7-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="991c7-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="991c7-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="991c7-256">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="991c7-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="991c7-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="991c7-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="991c7-258">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="991c7-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="991c7-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="991c7-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="991c7-260">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="991c7-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="991c7-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="991c7-262">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="991c7-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="991c7-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="991c7-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="991c7-264">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="991c7-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="991c7-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="991c7-266">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="991c7-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="991c7-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="991c7-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="991c7-268">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="991c7-269">プロジェクト参照</span><span class="sxs-lookup"><span data-stu-id="991c7-269">Project references</span></span>

<span data-ttu-id="991c7-270">コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-270">Command</span></span> | <span data-ttu-id="991c7-271">関数</span><span class="sxs-lookup"><span data-stu-id="991c7-271">Function</span></span>
--- | ---
[<span data-ttu-id="991c7-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="991c7-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="991c7-273">プロジェクト参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="991c7-273">Adds a project reference.</span></span>
[<span data-ttu-id="991c7-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="991c7-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="991c7-275">プロジェクト参照をリストします。</span><span class="sxs-lookup"><span data-stu-id="991c7-275">Lists project references.</span></span>
[<span data-ttu-id="991c7-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="991c7-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="991c7-277">プロジェクト参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="991c7-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="991c7-278">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="991c7-278">NuGet packages</span></span>

<span data-ttu-id="991c7-279">コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-279">Command</span></span> | <span data-ttu-id="991c7-280">関数</span><span class="sxs-lookup"><span data-stu-id="991c7-280">Function</span></span>
--- | ---
[<span data-ttu-id="991c7-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="991c7-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="991c7-282">NuGet パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="991c7-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="991c7-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="991c7-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="991c7-284">NuGet パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="991c7-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="991c7-285">NuGet コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-285">NuGet commands</span></span>

<span data-ttu-id="991c7-286">コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-286">Command</span></span> | <span data-ttu-id="991c7-287">関数</span><span class="sxs-lookup"><span data-stu-id="991c7-287">Function</span></span>
--- | ---
[<span data-ttu-id="991c7-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="991c7-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="991c7-289">サーバーからパッケージを削除または一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="991c7-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="991c7-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="991c7-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="991c7-291">HTTP 要求キャッシュ、一時的なキャッシュ、コンピューター全体のグローバル パッケージ フォルダーなどのローカルの NuGet リソースをクリアまたは一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="991c7-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="991c7-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="991c7-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="991c7-293">パッケージをサーバーにプッシュして発行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="991c7-294">グローバル ツール コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-294">Global Tools commands</span></span>

<span data-ttu-id="991c7-295">[.NET Core グローバル ツール](global-tools.md)は .NET Core SDK 2.1.300 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="991c7-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="991c7-296">コマンド</span><span class="sxs-lookup"><span data-stu-id="991c7-296">Command</span></span> | <span data-ttu-id="991c7-297">関数</span><span class="sxs-lookup"><span data-stu-id="991c7-297">Function</span></span>
--- | ---
[<span data-ttu-id="991c7-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="991c7-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="991c7-299">グローバル ツールをマシンにインストールします。</span><span class="sxs-lookup"><span data-stu-id="991c7-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="991c7-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="991c7-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="991c7-301">マシン上の既定のディレクトリまたは指定したパスに現在インストールされているすべてのグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="991c7-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="991c7-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="991c7-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="991c7-303">グローバル ツールをマシンからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="991c7-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="991c7-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="991c7-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="991c7-305">マシン上のグローバル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="991c7-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="991c7-306">その他のツール</span><span class="sxs-lookup"><span data-stu-id="991c7-306">Additional tools</span></span>

<span data-ttu-id="991c7-307">.NET Core SDK 2.1.300 以降では、`DotnetCliToolReference` を使用してプロジェクト単位でのみ入手可能であった複数のツールを .NET Core SDK の一部として入手できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="991c7-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="991c7-308">これらのツールを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="991c7-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="991c7-309">ツール</span><span class="sxs-lookup"><span data-stu-id="991c7-309">Tool</span></span>                                              | <span data-ttu-id="991c7-310">関数</span><span class="sxs-lookup"><span data-stu-id="991c7-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="991c7-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="991c7-311">dev-certs</span></span>                                         | <span data-ttu-id="991c7-312">開発証明書を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="991c7-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="991c7-313">ef</span><span class="sxs-lookup"><span data-stu-id="991c7-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="991c7-314">Entity Framework Core コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="991c7-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="991c7-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="991c7-315">sql-cache</span></span>                                         | <span data-ttu-id="991c7-316">SQL Server キャッシュ コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="991c7-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="991c7-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="991c7-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="991c7-318">開発ユーザーのシークレットを管理します。</span><span class="sxs-lookup"><span data-stu-id="991c7-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="991c7-319">watch</span><span class="sxs-lookup"><span data-stu-id="991c7-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="991c7-320">ファイルが変化するとコマンドを実行するファイル ウォッチャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="991c7-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="991c7-321">各ツールの詳細については、`dotnet <tool-name> --help` と入力してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="991c7-322">使用例</span><span class="sxs-lookup"><span data-stu-id="991c7-322">Examples</span></span>

<span data-ttu-id="991c7-323">新しい .NET Core コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="991c7-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="991c7-324">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="991c7-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="991c7-325">指定されたディレクトリにプロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="991c7-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="991c7-326">`myapp.dll` など、アプリケーション DLL を実行します。</span><span class="sxs-lookup"><span data-stu-id="991c7-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="991c7-327">環境変数</span><span class="sxs-lookup"><span data-stu-id="991c7-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="991c7-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="991c7-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="991c7-329">グローバル パッケージ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="991c7-329">The global packages folder.</span></span> <span data-ttu-id="991c7-330">設定されていない場合は、既定で `~/.nuget/packages` (Unix の場合) または `%userprofile%\.nuget\packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="991c7-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="991c7-331">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="991c7-332">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="991c7-333">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="991c7-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="991c7-334">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="991c7-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="991c7-335">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="991c7-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="991c7-336">.NET Core ランタイム、共有フレームワーク、または SDK がグローバルな場所から解決されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="991c7-337">設定されていない場合は、既定で `true` になります。</span><span class="sxs-lookup"><span data-stu-id="991c7-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="991c7-338">`false` に設定すると、グローバルな場所から解決されず、.NET Core インストールが分離されます (値 `0` または `false` が受け入れられます)。</span><span class="sxs-lookup"><span data-stu-id="991c7-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="991c7-339">複数レベルのルックアップの詳細については、「[Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)」 (複数レベルの SharedFX ルックアップ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="991c7-340">`0` に設定されている場合、マイナー バージョンのロールフォワードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="991c7-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="991c7-341">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="991c7-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="991c7-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="991c7-343">プライマリ パッケージのキャッシュです。</span><span class="sxs-lookup"><span data-stu-id="991c7-343">The primary package cache.</span></span> <span data-ttu-id="991c7-344">設定されていない場合は、既定で `$HOME/.nuget/packages` (Unix の場合) または `%userprofile%\.nuget\packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="991c7-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="991c7-345">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="991c7-346">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="991c7-347">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="991c7-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="991c7-348">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="991c7-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="991c7-349">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="991c7-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="991c7-350">.NET Core ランタイム、共有フレームワーク、または SDK がグローバルな場所から解決されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="991c7-351">設定されていない場合は、既定で `true` になります。</span><span class="sxs-lookup"><span data-stu-id="991c7-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="991c7-352">`false` に設定すると、グローバルな場所から解決されず、.NET Core インストールが分離されます (値 `0` または `false` が受け入れられます)。</span><span class="sxs-lookup"><span data-stu-id="991c7-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="991c7-353">複数レベルのルックアップの詳細については、「[Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)」 (複数レベルの SharedFX ルックアップ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="991c7-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="991c7-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="991c7-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="991c7-355">プライマリ パッケージのキャッシュです。</span><span class="sxs-lookup"><span data-stu-id="991c7-355">The primary package cache.</span></span> <span data-ttu-id="991c7-356">設定されていない場合は、既定で `$HOME/.nuget/packages` (Unix の場合) または `%userprofile%\.nuget\packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="991c7-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="991c7-357">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="991c7-358">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="991c7-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="991c7-359">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="991c7-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="991c7-360">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="991c7-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="991c7-361">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="991c7-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="991c7-362">関連項目</span><span class="sxs-lookup"><span data-stu-id="991c7-362">See also</span></span>

- [<span data-ttu-id="991c7-363">ランタイム構成ファイル</span><span class="sxs-lookup"><span data-stu-id="991c7-363">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
