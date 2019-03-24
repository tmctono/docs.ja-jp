---
title: dotnet コマンド
description: dotnet コマンド (.NET Core CLI ツールの一般的なドライバー) とその使用法について説明します。
ms.date: 06/04/2018
ms.openlocfilehash: 107a529952cce62dac840874fa5d6d8986376adf
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185637"
---
# <a name="dotnet-command"></a><span data-ttu-id="3849d-103">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3849d-104">name</span><span class="sxs-lookup"><span data-stu-id="3849d-104">Name</span></span>

<span data-ttu-id="3849d-105">`dotnet` - .NET のソース コードとバイナリを管理するためのツール。</span><span class="sxs-lookup"><span data-stu-id="3849d-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3849d-106">構文</span><span class="sxs-lookup"><span data-stu-id="3849d-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3849d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3849d-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3849d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3849d-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3849d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3849d-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="3849d-110">説明</span><span class="sxs-lookup"><span data-stu-id="3849d-110">Description</span></span>

<span data-ttu-id="3849d-111">`dotnet` は .NET のソース コードとバイナリを管理するためのツールです。</span><span class="sxs-lookup"><span data-stu-id="3849d-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="3849d-112">[`dotnet build`](dotnet-build.md) や [`dotnet run`](dotnet-run.md) のような特定のタスクを実行するコマンドを公開します。</span><span class="sxs-lookup"><span data-stu-id="3849d-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="3849d-113">各コマンドによって、それ自体の引数が定義されます。</span><span class="sxs-lookup"><span data-stu-id="3849d-113">Each command defines its own arguments.</span></span> <span data-ttu-id="3849d-114">各コマンドの後ろに `--help` と入力すると、短いヘルプ ドキュメントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3849d-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="3849d-115">`dotnet` は、`dotnet myapp.dll` など、アプリケーション DLL を指定することで、アプリケーションを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3849d-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="3849d-116">展開オプションについては、「[.NET Core アプリケーションの展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="3849d-117">オプション</span><span class="sxs-lookup"><span data-stu-id="3849d-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3849d-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3849d-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="3849d-119">追加の *deps.json* ファイルへのパスです。</span><span class="sxs-lookup"><span data-stu-id="3849d-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="3849d-120">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="3849d-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="3849d-121">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3849d-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="3849d-122">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="3849d-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="3849d-123">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="3849d-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="3849d-124">`dotnet --help` では、使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="3849d-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="3849d-125">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="3849d-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="3849d-126">インストールされている .NET Core ランタイムを表示します。</span><span class="sxs-lookup"><span data-stu-id="3849d-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="3849d-127">インストールされている .NET Core SDK を表示します。</span><span class="sxs-lookup"><span data-stu-id="3849d-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="3849d-128">必要な共有フレームワークが利用できない場合の動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="3849d-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="3849d-129">`N` には以下があります。</span><span class="sxs-lookup"><span data-stu-id="3849d-129">`N` can be:</span></span>
* <span data-ttu-id="3849d-130">`0` - マイナー バージョンのロールフォワードでも無効にします。</span><span class="sxs-lookup"><span data-stu-id="3849d-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="3849d-131">`1` - マイナー バージョンはロール フォワードしますが、メジャー バージョンはしません。</span><span class="sxs-lookup"><span data-stu-id="3849d-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="3849d-132">これが既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="3849d-132">This is the default behavior.</span></span>
* <span data-ttu-id="3849d-133">`2` - マイナー バージョンとメジャー バージョンをロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="3849d-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="3849d-134">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="3849d-135">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3849d-136">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="3849d-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3849d-137">一部のコマンドではサポートされていません。このオプションが使用可能かどうかを判断するには、対象のコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="3849d-138">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="3849d-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3849d-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3849d-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="3849d-140">追加の *deps.json* ファイルへのパスです。</span><span class="sxs-lookup"><span data-stu-id="3849d-140">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="3849d-141">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="3849d-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="3849d-142">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3849d-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="3849d-143">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="3849d-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="3849d-144">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="3849d-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="3849d-145">`dotnet --help` では、使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="3849d-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="3849d-146">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="3849d-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="3849d-147">`0` に設定されている場合、マイナー バージョンのロールフォワードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3849d-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="3849d-148">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="3849d-149">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3849d-150">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="3849d-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3849d-151">一部のコマンドではサポートされていません。このオプションが使用可能かどうかを判断するには、対象のコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="3849d-152">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="3849d-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3849d-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3849d-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="3849d-154">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="3849d-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="3849d-155">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3849d-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="3849d-156">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="3849d-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="3849d-157">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="3849d-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="3849d-158">`dotnet --help` では、使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="3849d-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="3849d-159">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="3849d-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="3849d-160">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3849d-161">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="3849d-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="3849d-162">一部のコマンドではサポートされていません。このオプションが使用可能かどうかを判断するには、対象のコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="3849d-163">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="3849d-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="3849d-164">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="3849d-165">全般</span><span class="sxs-lookup"><span data-stu-id="3849d-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3849d-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3849d-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="3849d-167">コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-167">Command</span></span>                                       | <span data-ttu-id="3849d-168">関数</span><span class="sxs-lookup"><span data-stu-id="3849d-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="3849d-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="3849d-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="3849d-170">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3849d-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="3849d-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="3849d-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="3849d-172">ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="3849d-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="3849d-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="3849d-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="3849d-174">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="3849d-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="3849d-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="3849d-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="3849d-176">コマンドのより詳細なドキュメントをオンラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="3849d-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="3849d-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="3849d-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="3849d-178">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="3849d-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="3849d-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="3849d-180">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3849d-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="3849d-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="3849d-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="3849d-182">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="3849d-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="3849d-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="3849d-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="3849d-184">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3849d-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="3849d-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="3849d-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="3849d-186">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="3849d-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="3849d-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="3849d-188">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="3849d-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="3849d-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="3849d-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="3849d-190">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="3849d-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="3849d-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="3849d-192">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="3849d-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="3849d-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="3849d-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="3849d-194">ランタイム パッケージ ストアにアセンブリを格納します。</span><span class="sxs-lookup"><span data-stu-id="3849d-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="3849d-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="3849d-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="3849d-196">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3849d-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3849d-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="3849d-198">コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-198">Command</span></span>                             | <span data-ttu-id="3849d-199">関数</span><span class="sxs-lookup"><span data-stu-id="3849d-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="3849d-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="3849d-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="3849d-201">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3849d-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="3849d-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="3849d-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="3849d-203">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="3849d-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="3849d-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="3849d-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="3849d-205">コマンドのより詳細なドキュメントをオンラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="3849d-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="3849d-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="3849d-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="3849d-207">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="3849d-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="3849d-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="3849d-209">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3849d-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="3849d-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="3849d-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="3849d-211">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="3849d-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="3849d-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="3849d-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="3849d-213">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3849d-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="3849d-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="3849d-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="3849d-215">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="3849d-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="3849d-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="3849d-217">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="3849d-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="3849d-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="3849d-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="3849d-219">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="3849d-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="3849d-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="3849d-221">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="3849d-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="3849d-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="3849d-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="3849d-223">ランタイム パッケージ ストアにアセンブリを格納します。</span><span class="sxs-lookup"><span data-stu-id="3849d-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="3849d-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="3849d-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="3849d-225">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3849d-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3849d-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="3849d-227">コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-227">Command</span></span>                             | <span data-ttu-id="3849d-228">関数</span><span class="sxs-lookup"><span data-stu-id="3849d-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="3849d-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="3849d-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="3849d-230">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3849d-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="3849d-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="3849d-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="3849d-232">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="3849d-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="3849d-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="3849d-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="3849d-234">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="3849d-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="3849d-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="3849d-236">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3849d-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="3849d-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="3849d-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="3849d-238">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="3849d-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="3849d-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="3849d-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="3849d-240">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3849d-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="3849d-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="3849d-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="3849d-242">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="3849d-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="3849d-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="3849d-244">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="3849d-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="3849d-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="3849d-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="3849d-246">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="3849d-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="3849d-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="3849d-248">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="3849d-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="3849d-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="3849d-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="3849d-250">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="3849d-251">プロジェクト参照</span><span class="sxs-lookup"><span data-stu-id="3849d-251">Project references</span></span>

<span data-ttu-id="3849d-252">コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-252">Command</span></span> | <span data-ttu-id="3849d-253">関数</span><span class="sxs-lookup"><span data-stu-id="3849d-253">Function</span></span>
--- | ---
[<span data-ttu-id="3849d-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="3849d-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="3849d-255">プロジェクト参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="3849d-255">Adds a project reference.</span></span>
[<span data-ttu-id="3849d-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="3849d-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="3849d-257">プロジェクト参照をリストします。</span><span class="sxs-lookup"><span data-stu-id="3849d-257">Lists project references.</span></span>
[<span data-ttu-id="3849d-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="3849d-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="3849d-259">プロジェクト参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="3849d-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="3849d-260">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="3849d-260">NuGet packages</span></span>

<span data-ttu-id="3849d-261">コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-261">Command</span></span> | <span data-ttu-id="3849d-262">関数</span><span class="sxs-lookup"><span data-stu-id="3849d-262">Function</span></span>
--- | ---
[<span data-ttu-id="3849d-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="3849d-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="3849d-264">NuGet パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="3849d-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="3849d-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="3849d-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="3849d-266">NuGet パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="3849d-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="3849d-267">NuGet コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-267">NuGet commands</span></span>

<span data-ttu-id="3849d-268">コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-268">Command</span></span> | <span data-ttu-id="3849d-269">関数</span><span class="sxs-lookup"><span data-stu-id="3849d-269">Function</span></span>
--- | ---
[<span data-ttu-id="3849d-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="3849d-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="3849d-271">サーバーからパッケージを削除または一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="3849d-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="3849d-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="3849d-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="3849d-273">HTTP 要求キャッシュ、一時的なキャッシュ、コンピューター全体のグローバル パッケージ フォルダーなどのローカルの NuGet リソースをクリアまたは一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3849d-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="3849d-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="3849d-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="3849d-275">パッケージをサーバーにプッシュして発行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="3849d-276">グローバル ツール コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-276">Global Tools commands</span></span>

<span data-ttu-id="3849d-277">[.NET Core グローバル ツール](global-tools.md)は .NET Core SDK 2.1.300 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3849d-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="3849d-278">コマンド</span><span class="sxs-lookup"><span data-stu-id="3849d-278">Command</span></span> | <span data-ttu-id="3849d-279">関数</span><span class="sxs-lookup"><span data-stu-id="3849d-279">Function</span></span>
--- | ---
[<span data-ttu-id="3849d-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="3849d-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="3849d-281">グローバル ツールをマシンにインストールします。</span><span class="sxs-lookup"><span data-stu-id="3849d-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="3849d-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="3849d-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="3849d-283">マシン上の既定のディレクトリまたは指定したパスに現在インストールされているすべてのグローバル ツールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3849d-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="3849d-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="3849d-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="3849d-285">グローバル ツールをマシンからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="3849d-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="3849d-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="3849d-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="3849d-287">マシン上のグローバル ツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="3849d-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="3849d-288">その他のツール</span><span class="sxs-lookup"><span data-stu-id="3849d-288">Additional tools</span></span>

<span data-ttu-id="3849d-289">.NET Core SDK 2.1.300 以降では、`DotnetCliToolReference` を使用してプロジェクト単位でのみ入手可能であった複数のツールを .NET Core SDK の一部として入手できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3849d-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="3849d-290">これらのツールを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="3849d-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="3849d-291">ツール</span><span class="sxs-lookup"><span data-stu-id="3849d-291">Tool</span></span>                                              | <span data-ttu-id="3849d-292">関数</span><span class="sxs-lookup"><span data-stu-id="3849d-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="3849d-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="3849d-293">dev-certs</span></span>                                         | <span data-ttu-id="3849d-294">開発証明書を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="3849d-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="3849d-295">ef</span><span class="sxs-lookup"><span data-stu-id="3849d-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="3849d-296">Entity Framework Core コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="3849d-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="3849d-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="3849d-297">sql-cache</span></span>                                         | <span data-ttu-id="3849d-298">SQL Server キャッシュ コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="3849d-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="3849d-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="3849d-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="3849d-300">開発ユーザーのシークレットを管理します。</span><span class="sxs-lookup"><span data-stu-id="3849d-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="3849d-301">watch</span><span class="sxs-lookup"><span data-stu-id="3849d-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="3849d-302">ファイルが変化するとコマンドを実行するファイル ウォッチャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="3849d-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="3849d-303">各ツールの詳細については、`dotnet <tool-name> --help` と入力してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="3849d-304">使用例</span><span class="sxs-lookup"><span data-stu-id="3849d-304">Examples</span></span>

<span data-ttu-id="3849d-305">新しい .NET Core コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3849d-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="3849d-306">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="3849d-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="3849d-307">指定されたディレクトリにプロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="3849d-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="3849d-308">`myapp.dll` など、アプリケーション DLL を実行します。</span><span class="sxs-lookup"><span data-stu-id="3849d-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="3849d-309">環境変数</span><span class="sxs-lookup"><span data-stu-id="3849d-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3849d-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3849d-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="3849d-311">プライマリ パッケージのキャッシュです。</span><span class="sxs-lookup"><span data-stu-id="3849d-311">The primary package cache.</span></span> <span data-ttu-id="3849d-312">設定されていない場合は、既定で `$HOME/.nuget/packages` (Unix の場合) または `%HOME%\NuGet\Packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="3849d-312">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="3849d-313">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="3849d-314">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="3849d-315">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="3849d-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="3849d-316">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="3849d-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="3849d-317">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="3849d-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="3849d-318">.NET Core ランタイム、共有フレームワーク、または SDK がグローバルな場所から解決されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="3849d-319">設定されていない場合は、既定で `true` になります。</span><span class="sxs-lookup"><span data-stu-id="3849d-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="3849d-320">`false` に設定すると、グローバルな場所から解決されず、.NET Core インストールが分離されます (値 `0` または `false` が受け入れられます)。</span><span class="sxs-lookup"><span data-stu-id="3849d-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="3849d-321">複数レベルのルックアップの詳細については、「[Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)」 (複数レベルの SharedFX ルックアップ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="3849d-322">`0` に設定されている場合、マイナー バージョンのロールフォワードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3849d-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="3849d-323">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3849d-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3849d-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="3849d-325">プライマリ パッケージのキャッシュです。</span><span class="sxs-lookup"><span data-stu-id="3849d-325">The primary package cache.</span></span> <span data-ttu-id="3849d-326">設定されていない場合は、既定で `$HOME/.nuget/packages` (Unix の場合) または `%HOME%\NuGet\Packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="3849d-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="3849d-327">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="3849d-328">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="3849d-329">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="3849d-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="3849d-330">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="3849d-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="3849d-331">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="3849d-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="3849d-332">.NET Core ランタイム、共有フレームワーク、または SDK がグローバルな場所から解決されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="3849d-333">設定されていない場合は、既定で `true` になります。</span><span class="sxs-lookup"><span data-stu-id="3849d-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="3849d-334">`false` に設定すると、グローバルな場所から解決されず、.NET Core インストールが分離されます (値 `0` または `false` が受け入れられます)。</span><span class="sxs-lookup"><span data-stu-id="3849d-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="3849d-335">複数レベルのルックアップの詳細については、「[Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)」 (複数レベルの SharedFX ルックアップ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3849d-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3849d-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3849d-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="3849d-337">プライマリ パッケージのキャッシュです。</span><span class="sxs-lookup"><span data-stu-id="3849d-337">The primary package cache.</span></span> <span data-ttu-id="3849d-338">設定されていない場合は、既定で `$HOME/.nuget/packages` (Unix の場合) または `%HOME%\NuGet\Packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="3849d-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="3849d-339">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="3849d-340">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3849d-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="3849d-341">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="3849d-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="3849d-342">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="3849d-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="3849d-343">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="3849d-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
