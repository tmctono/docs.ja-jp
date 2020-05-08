---
title: dotnet コマンド
description: dotnet コマンド (.NET Core CLI の汎用ドライバー) とその使用方法について説明します。
ms.date: 02/13/2020
ms.openlocfilehash: 6a08297499d955db44e342dc82fed25b7b9b8171
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739079"
---
# <a name="dotnet-command"></a><span data-ttu-id="74bf3-103">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="74bf3-103">dotnet command</span></span>

<span data-ttu-id="74bf3-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="74bf3-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="74bf3-105">名前</span><span class="sxs-lookup"><span data-stu-id="74bf3-105">Name</span></span>

<span data-ttu-id="74bf3-106">`dotnet` - .NET Core CLI の汎用ドライバー。</span><span class="sxs-lookup"><span data-stu-id="74bf3-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="74bf3-107">構文</span><span class="sxs-lookup"><span data-stu-id="74bf3-107">Synopsis</span></span>

<span data-ttu-id="74bf3-108">利用できるコマンドと環境に関する情報を取得するには:</span><span class="sxs-lookup"><span data-stu-id="74bf3-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="74bf3-109">コマンドを実行するには (SDK のインストールが必要):</span><span class="sxs-lookup"><span data-stu-id="74bf3-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="74bf3-110">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="74bf3-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="74bf3-111">`--roll-forward` は、.NET Core 3.x 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="74bf3-112">.NET Core 2.x には `--roll-forward-on-no-candidate-fx` を使用します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="74bf3-113">説明</span><span class="sxs-lookup"><span data-stu-id="74bf3-113">Description</span></span>

<span data-ttu-id="74bf3-114">`dotnet` コマンドには、次の 2 つの機能があります。</span><span class="sxs-lookup"><span data-stu-id="74bf3-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="74bf3-115">.NET Core プロジェクトを操作するためのコマンドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="74bf3-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="74bf3-116">たとえば、[`dotnet build`](dotnet-build.md) を使うと、プロジェクトをビルドできます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="74bf3-117">各コマンドには独自のオプションと引数が定義されています。</span><span class="sxs-lookup"><span data-stu-id="74bf3-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="74bf3-118">すべてのコマンドは、コマンドの使用方法に関する簡単なドキュメントを出力するための `--help` オプションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="74bf3-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="74bf3-119">.NET Core アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="74bf3-120">アプリケーションを実行するには、アプリケーション `.dll` ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="74bf3-121">アプリケーションを実行するということは、エントリ ポイントを見つけて実行することを意味します。コンソール アプリの場合、これは `Main` メソッドです。</span><span class="sxs-lookup"><span data-stu-id="74bf3-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="74bf3-122">たとえば、`dotnet myapp.dll` を使うと、`myapp` アプリケーションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="74bf3-123">展開オプションについては、「[.NET Core アプリケーションの展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="74bf3-124">オプション</span><span class="sxs-lookup"><span data-stu-id="74bf3-124">Options</span></span>

<span data-ttu-id="74bf3-125">`dotnet` 単独、コマンドの実行、アプリケーションの実行にはさまざまなオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="74bf3-126">dotnet 単独のオプション</span><span class="sxs-lookup"><span data-stu-id="74bf3-126">Options for dotnet by itself</span></span>

<span data-ttu-id="74bf3-127">次のオプションは、`dotnet` 単独のものです。</span><span class="sxs-lookup"><span data-stu-id="74bf3-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="74bf3-128">たとえば、`dotnet --info` のようにします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="74bf3-129">環境に関する情報が出力されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="74bf3-130">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="74bf3-131">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="74bf3-132">インストールされている .NET Core ランタイムの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="74bf3-133">x86 バージョンの SDK には x86 ランタイムのみが登録され、x64 バージョンの SDK には x64 ランタイムのみが登録されています。</span><span class="sxs-lookup"><span data-stu-id="74bf3-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="74bf3-134">インストールされている .NET Core SDK の一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="74bf3-135">使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="74bf3-136">コマンドを実行するための SDK のオプション</span><span class="sxs-lookup"><span data-stu-id="74bf3-136">SDK options for running a command</span></span>

<span data-ttu-id="74bf3-137">次のオプションは、コマンドを指定した `dotnet` 用です。</span><span class="sxs-lookup"><span data-stu-id="74bf3-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="74bf3-138">たとえば、`dotnet build --help` のようにします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="74bf3-139">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="74bf3-140">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="74bf3-141">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="74bf3-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="74bf3-142">すべてのコマンドでサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="74bf3-142">Not supported in every command.</span></span> <span data-ttu-id="74bf3-143">このオプションを使用できるかどうかについては、そのコマンド ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="74bf3-144">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="74bf3-145">各コマンドには、そのコマンドに固有のオプションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="74bf3-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="74bf3-146">使用できるオプションの一覧については、そのコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="74bf3-147">ランタイム オプション</span><span class="sxs-lookup"><span data-stu-id="74bf3-147">Runtime options</span></span>

<span data-ttu-id="74bf3-148">次のオプションは、`dotnet` でアプリケーションを実行するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="74bf3-149">たとえば、`dotnet myapp.dll --fx-version 3.1.1` のようにします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-149">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="74bf3-150">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="74bf3-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="74bf3-151">追加の *.deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="74bf3-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="74bf3-152">*deps.json* ファイルには、依存関係、コンパイル依存関係、アセンブリ競合に対処するためのバージョン情報の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="74bf3-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="74bf3-153">詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="74bf3-154">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="74bf3-154">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="74bf3-155">*runtimeconfig.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="74bf3-155">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="74bf3-156">*runtimeconfig.json* ファイルは、ランタイム設定を含む構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="74bf3-156">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="74bf3-157">詳細については、「[.NET Core ランタイム構成設定](../run-time-config/index.md#runtimeconfigjson)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-157">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="74bf3-158">**`--roll-forward-on-no-candidate-fx <N>`** **.NET Core 2.x SDK で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="74bf3-158">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="74bf3-159">必要な共有フレームワークが利用できない場合の動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-159">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="74bf3-160">`N` には以下があります。</span><span class="sxs-lookup"><span data-stu-id="74bf3-160">`N` can be:</span></span>

  - <span data-ttu-id="74bf3-161">`0` - マイナー バージョンのロールフォワードでも無効にします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-161">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="74bf3-162">`1` - マイナー バージョンはロール フォワードしますが、メジャー バージョンはしません。</span><span class="sxs-lookup"><span data-stu-id="74bf3-162">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="74bf3-163">これが既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="74bf3-163">This is the default behavior.</span></span>
  - <span data-ttu-id="74bf3-164">`2` - マイナー バージョンとメジャー バージョンをロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-164">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="74bf3-165">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-165">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="74bf3-166">**`--roll-forward <SETTING>`** **.NET Core SDK 3.0 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="74bf3-166">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="74bf3-167">アプリにロール フォ ワードを適用する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-167">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="74bf3-168">`SETTING` には次のいずれかの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-168">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="74bf3-169">指定しない場合の既定は、`Minor` です。</span><span class="sxs-lookup"><span data-stu-id="74bf3-169">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="74bf3-170">`LatestPatch` - 最新のパッチ バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-170">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="74bf3-171">これで、マイナー バージョンのロールフォワードが無効になります。</span><span class="sxs-lookup"><span data-stu-id="74bf3-171">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="74bf3-172">`Minor` - 要求されたマイナー バージョンが見つからない場合は、それよりも高い最小マイナー バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-172">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="74bf3-173">要求されたマイナー バージョンが存在する場合は、LatestPatch ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-173">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="74bf3-174">`Major` - 要求されたメジャー バージョンが見つからない場合は、それよりも高い最小メジャー バージョンで最小マイナー バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-174">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="74bf3-175">要求されたメジャー バージョンが存在する場合は、Minor ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-175">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="74bf3-176">`LatestMinor` - 要求されたマイナー バージョンが存在する場合でも、最上位のマイナー バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-176">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="74bf3-177">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="74bf3-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="74bf3-178">`LatestMajor` - 要求されたメジャーが存在する場合でも、最上位のメジャー バージョンで最上位のマイナー バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-178">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="74bf3-179">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="74bf3-179">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="74bf3-180">`Disable` - ロール フォワードしません。</span><span class="sxs-lookup"><span data-stu-id="74bf3-180">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="74bf3-181">指定されたバージョンにのみバインドします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-181">Only bind to specified version.</span></span> <span data-ttu-id="74bf3-182">このポリシーは、最新のパッチにロールフォワードする機能が無効になるため、一般的な使用にはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="74bf3-182">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="74bf3-183">この値はテスト用にのみ推奨されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-183">This value is only recommended for testing.</span></span>

<span data-ttu-id="74bf3-184">`Disable` を除いて、すべての設定は使用できる最高のパッチ バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-184">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="74bf3-185">ロール フォワード動作は、プロジェクト ファイル プロパティ、ランタイム構成ファイル プロパティ、および環境変数でも構成できます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-185">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="74bf3-186">詳細については、「[メジャーバージョン ランタイムのロールフォワード](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-186">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="74bf3-187">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="74bf3-187">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="74bf3-188">全般</span><span class="sxs-lookup"><span data-stu-id="74bf3-188">General</span></span>

| <span data-ttu-id="74bf3-189">コマンド</span><span class="sxs-lookup"><span data-stu-id="74bf3-189">Command</span></span>                                       | <span data-ttu-id="74bf3-190">関数</span><span class="sxs-lookup"><span data-stu-id="74bf3-190">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="74bf3-191">dotnet build</span><span class="sxs-lookup"><span data-stu-id="74bf3-191">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="74bf3-192">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-192">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="74bf3-193">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="74bf3-193">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="74bf3-194">ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-194">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="74bf3-195">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="74bf3-195">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="74bf3-196">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="74bf3-196">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="74bf3-197">dotnet help</span><span class="sxs-lookup"><span data-stu-id="74bf3-197">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="74bf3-198">コマンドのより詳細なドキュメントをオンラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-198">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="74bf3-199">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="74bf3-199">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="74bf3-200">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-200">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="74bf3-201">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="74bf3-201">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="74bf3-202">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-202">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="74bf3-203">dotnet new</span><span class="sxs-lookup"><span data-stu-id="74bf3-203">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="74bf3-204">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-204">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="74bf3-205">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="74bf3-205">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="74bf3-206">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-206">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="74bf3-207">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="74bf3-207">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="74bf3-208">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-208">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="74bf3-209">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="74bf3-209">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="74bf3-210">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-210">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="74bf3-211">dotnet run</span><span class="sxs-lookup"><span data-stu-id="74bf3-211">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="74bf3-212">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-212">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="74bf3-213">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="74bf3-213">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="74bf3-214">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="74bf3-214">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="74bf3-215">dotnet store</span><span class="sxs-lookup"><span data-stu-id="74bf3-215">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="74bf3-216">ランタイム パッケージ ストアにアセンブリを格納します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-216">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="74bf3-217">dotnet test</span><span class="sxs-lookup"><span data-stu-id="74bf3-217">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="74bf3-218">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-218">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="74bf3-219">プロジェクト参照</span><span class="sxs-lookup"><span data-stu-id="74bf3-219">Project references</span></span>

<span data-ttu-id="74bf3-220">コマンド</span><span class="sxs-lookup"><span data-stu-id="74bf3-220">Command</span></span> | <span data-ttu-id="74bf3-221">関数</span><span class="sxs-lookup"><span data-stu-id="74bf3-221">Function</span></span>
--- | ---
[<span data-ttu-id="74bf3-222">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="74bf3-222">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="74bf3-223">プロジェクト参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-223">Adds a project reference.</span></span>
[<span data-ttu-id="74bf3-224">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="74bf3-224">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="74bf3-225">プロジェクト参照をリストします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-225">Lists project references.</span></span>
[<span data-ttu-id="74bf3-226">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="74bf3-226">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="74bf3-227">プロジェクト参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-227">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="74bf3-228">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="74bf3-228">NuGet packages</span></span>

<span data-ttu-id="74bf3-229">コマンド</span><span class="sxs-lookup"><span data-stu-id="74bf3-229">Command</span></span> | <span data-ttu-id="74bf3-230">関数</span><span class="sxs-lookup"><span data-stu-id="74bf3-230">Function</span></span>
--- | ---
[<span data-ttu-id="74bf3-231">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="74bf3-231">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="74bf3-232">NuGet パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-232">Adds a NuGet package.</span></span>
[<span data-ttu-id="74bf3-233">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="74bf3-233">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="74bf3-234">NuGet パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-234">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="74bf3-235">NuGet コマンド</span><span class="sxs-lookup"><span data-stu-id="74bf3-235">NuGet commands</span></span>

<span data-ttu-id="74bf3-236">コマンド</span><span class="sxs-lookup"><span data-stu-id="74bf3-236">Command</span></span> | <span data-ttu-id="74bf3-237">関数</span><span class="sxs-lookup"><span data-stu-id="74bf3-237">Function</span></span>
--- | ---
[<span data-ttu-id="74bf3-238">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="74bf3-238">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="74bf3-239">サーバーからパッケージを削除または一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-239">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="74bf3-240">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="74bf3-240">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="74bf3-241">パッケージをサーバーにプッシュして発行します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-241">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="74bf3-242">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="74bf3-242">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="74bf3-243">HTTP 要求キャッシュ、一時的なキャッシュ、コンピューター全体のグローバル パッケージ フォルダーなどのローカルの NuGet リソースをクリアまたは一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-243">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="74bf3-244">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="74bf3-244">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="74bf3-245">NuGet ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-245">Adds a NuGet source.</span></span>
[<span data-ttu-id="74bf3-246">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="74bf3-246">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="74bf3-247">NuGet ソースを無効にします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-247">Disables a NuGet source.</span></span>
[<span data-ttu-id="74bf3-248">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="74bf3-248">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="74bf3-249">NuGet ソースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-249">Enables a NuGet source.</span></span>
[<span data-ttu-id="74bf3-250">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="74bf3-250">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="74bf3-251">構成されている NuGet ソースをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-251">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="74bf3-252">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="74bf3-252">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="74bf3-253">NuGet ソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-253">Removes a NuGet source.</span></span>
[<span data-ttu-id="74bf3-254">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="74bf3-254">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="74bf3-255">NuGet ソースを更新します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-255">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="74bf3-256">グローバル、ツールパス、およびローカル ツールのコマンド</span><span class="sxs-lookup"><span data-stu-id="74bf3-256">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="74bf3-257">ツールは、NuGet パッケージからインストールされ、コマンド プロンプトから呼び出されるコンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="74bf3-257">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="74bf3-258">ツールは自分で作成することも、サードパーティによって作成されたツールをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-258">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="74bf3-259">ツールは、グローバル ツール、ツールパス ツール、およびローカル ツールとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-259">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="74bf3-260">詳細については、[.NET Core ツールの概要](global-tools.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-260">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="74bf3-261">グローバル ツールとツールパス ツールは、.NET Core SDK 2.1 以降使用できます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-261">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="74bf3-262">ローカル ツールは、.NET Core SDK 3.0 以降使用できます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-262">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="74bf3-263">コマンド</span><span class="sxs-lookup"><span data-stu-id="74bf3-263">Command</span></span> | <span data-ttu-id="74bf3-264">関数</span><span class="sxs-lookup"><span data-stu-id="74bf3-264">Function</span></span>
--- | ---
[<span data-ttu-id="74bf3-265">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="74bf3-265">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="74bf3-266">ツールをお使いのコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-266">Installs a tool on your machine.</span></span>
[<span data-ttu-id="74bf3-267">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="74bf3-267">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="74bf3-268">コンピューターに現在インストールされているグローバル、ツールパス、またはローカル ツールをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-268">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="74bf3-269">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="74bf3-269">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="74bf3-270">ツールをお使いのコンピューターからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-270">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="74bf3-271">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="74bf3-271">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="74bf3-272">コンピューターにインストールされているツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-272">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="74bf3-273">その他のツール</span><span class="sxs-lookup"><span data-stu-id="74bf3-273">Additional tools</span></span>

<span data-ttu-id="74bf3-274">.NET Core SDK 2.1.300 以降では、`DotnetCliToolReference` を使用してプロジェクト単位でのみ入手可能であった複数のツールを .NET Core SDK の一部として入手できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74bf3-274">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="74bf3-275">これらのツールを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-275">These tools are listed in the following table:</span></span>

| <span data-ttu-id="74bf3-276">ツール</span><span class="sxs-lookup"><span data-stu-id="74bf3-276">Tool</span></span>                                              | <span data-ttu-id="74bf3-277">関数</span><span class="sxs-lookup"><span data-stu-id="74bf3-277">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="74bf3-278">dev-certs</span><span class="sxs-lookup"><span data-stu-id="74bf3-278">dev-certs</span></span>                                         | <span data-ttu-id="74bf3-279">開発証明書を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-279">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="74bf3-280">ef</span><span class="sxs-lookup"><span data-stu-id="74bf3-280">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="74bf3-281">Entity Framework Core コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="74bf3-281">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="74bf3-282">sql-cache</span><span class="sxs-lookup"><span data-stu-id="74bf3-282">sql-cache</span></span>                                         | <span data-ttu-id="74bf3-283">SQL Server キャッシュ コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="74bf3-283">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="74bf3-284">user-secrets</span><span class="sxs-lookup"><span data-stu-id="74bf3-284">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="74bf3-285">開発ユーザーのシークレットを管理します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-285">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="74bf3-286">watch</span><span class="sxs-lookup"><span data-stu-id="74bf3-286">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="74bf3-287">ファイルが変化するとコマンドを実行するファイル ウォッチャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-287">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="74bf3-288">各ツールの詳細については、`dotnet <tool-name> --help` と入力してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-288">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="74bf3-289">使用例</span><span class="sxs-lookup"><span data-stu-id="74bf3-289">Examples</span></span>

<span data-ttu-id="74bf3-290">新しい .NET Core コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-290">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="74bf3-291">指定されたディレクトリにプロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-291">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="74bf3-292">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-292">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="74bf3-293">環境変数</span><span class="sxs-lookup"><span data-stu-id="74bf3-293">Environment variables</span></span>

- <span data-ttu-id="74bf3-294">`DOTNET_ROOT`、`DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="74bf3-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="74bf3-295">.NET Core ランタイムが既定の場所にインストールされていない場合、それらの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-295">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="74bf3-296">Windows 上の既定の場所は `C:\Program Files\dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="74bf3-296">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="74bf3-297">Linux と macOS 上の既定の場所は `/usr/share/dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="74bf3-297">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="74bf3-298">この環境変数は、生成された実行可能ファイル (apphosts) を介してアプリを実行する場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-298">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="74bf3-299">64 ビット OS 上で 32 ビット実行可能ファイルを実行する場合は、代わりに `DOTNET_ROOT(x86)` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-299">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="74bf3-300">グローバル パッケージ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="74bf3-300">The global packages folder.</span></span> <span data-ttu-id="74bf3-301">設定されていない場合は、既定で `~/.nuget/packages` (Unix の場合) または `%userprofile%\.nuget\packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="74bf3-301">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="74bf3-302">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-302">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="74bf3-303">最初の実行時に .NET Core のウェルカム メッセージとテレメトリ メッセージを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-303">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="74bf3-304">`true` に設定すると、これらのメッセージは表示されません (値 `true`、`1`、または `yes` が受け入れられます)。`false` に設定すると許可されます (値 `false`、`0`、または `no` が受け入れられます)。</span><span class="sxs-lookup"><span data-stu-id="74bf3-304">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="74bf3-305">設定しない場合、既定値は `false` であり、最初の実行時にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-305">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="74bf3-306">このフラグはテレメトリには影響しません (テレメトリの送信のオプトアウトについては `DOTNET_CLI_TELEMETRY_OPTOUT` を参照)。</span><span class="sxs-lookup"><span data-stu-id="74bf3-306">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="74bf3-307">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-307">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="74bf3-308">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="74bf3-308">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="74bf3-309">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="74bf3-309">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="74bf3-310">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="74bf3-310">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="74bf3-311">.NET Core ランタイム、共有フレームワーク、または SDK がグローバルな場所から解決されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-311">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="74bf3-312">設定されていない場合、既定値は 1 (論理 `true`) です。</span><span class="sxs-lookup"><span data-stu-id="74bf3-312">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="74bf3-313">グローバルな場所から解決せず、.NET Core インストールを分離するには、0 (論理 `false`) に設定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-313">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="74bf3-314">複数レベルのルックアップの詳細については、「[Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)」 (複数レベルの SharedFX ルックアップ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-314">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="74bf3-315">`DOTNET_ROLL_FORWARD` **.NET Core 3.x SDK 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="74bf3-315">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="74bf3-316">ロール フォワード動作を決定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-316">Determines roll forward behavior.</span></span> <span data-ttu-id="74bf3-317">詳細については、この記事で前述した `--roll-forward` オプションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-317">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="74bf3-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **.NET Core 2.x SDK で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="74bf3-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="74bf3-319">`0` に設定されている場合、マイナー バージョンのロールフォワードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-319">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="74bf3-320">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-320">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="74bf3-321">`en-us` などのロケール値を使用して、CLI UI の言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-321">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="74bf3-322">サポートされている値は、Visual Studio の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="74bf3-322">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="74bf3-323">詳細については、[Visual Studio のインストール ドキュメント](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)のインストーラーの言語を変更する方法に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="74bf3-323">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="74bf3-324">.NET リソース マネージャーの規則が適用されるため、完全一致を選択する必要はありません。`CultureInfo` ツリーで子孫を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-324">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="74bf3-325">たとえば、`fr-CA` に設定すると、CLI によって `fr` の翻訳が検索され、使用されます。</span><span class="sxs-lookup"><span data-stu-id="74bf3-325">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="74bf3-326">サポートされていない言語に設定すると、CLI は英語にフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-326">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="74bf3-327">GUI 対応の生成された実行可能ファイルの場合、通常は特定のクラスのエラーに対して表示されるダイアログ ポップアップが無効になります。</span><span class="sxs-lookup"><span data-stu-id="74bf3-327">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="74bf3-328">この場合、`stderr` にのみ書き込まれ、終了します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-328">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="74bf3-329">CLI オプション `--additional-deps` に相当します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-329">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="74bf3-330">検出された RID をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="74bf3-330">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="74bf3-331">アセンブリの解決がフォールバックする "共有ストア" の場所。</span><span class="sxs-lookup"><span data-stu-id="74bf3-331">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="74bf3-332">スタートアップ フックを読み込み、実行するアセンブリの一覧。</span><span class="sxs-lookup"><span data-stu-id="74bf3-332">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="74bf3-333">`COREHOST_TRACE`、`COREHOST_TRACEFILE`、`COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="74bf3-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="74bf3-334">`dotnet.exe`、`hostfxr`、`hostpolicy` などのホスティング コンポーネントからの診断トレースを制御します。</span><span class="sxs-lookup"><span data-stu-id="74bf3-334">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="74bf3-335">関連項目</span><span class="sxs-lookup"><span data-stu-id="74bf3-335">See also</span></span>

- [<span data-ttu-id="74bf3-336">ランタイム構成ファイル</span><span class="sxs-lookup"><span data-stu-id="74bf3-336">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="74bf3-337">.NET Core ランタイム構成設定</span><span class="sxs-lookup"><span data-stu-id="74bf3-337">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
