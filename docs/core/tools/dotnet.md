---
title: dotnet コマンド
description: dotnet コマンド (.NET Core CLI の汎用ドライバー) とその使用方法について説明します。
ms.date: 02/13/2020
ms.openlocfilehash: 8692d419afd528bf49e1dc7dc1a7a5fd698b363b
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134072"
---
# <a name="dotnet-command"></a><span data-ttu-id="c8c09-103">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="c8c09-103">dotnet command</span></span>

<span data-ttu-id="c8c09-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="c8c09-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c8c09-105">名前</span><span class="sxs-lookup"><span data-stu-id="c8c09-105">Name</span></span>

<span data-ttu-id="c8c09-106">`dotnet` - .NET Core CLI の汎用ドライバー。</span><span class="sxs-lookup"><span data-stu-id="c8c09-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c8c09-107">構文</span><span class="sxs-lookup"><span data-stu-id="c8c09-107">Synopsis</span></span>

<span data-ttu-id="c8c09-108">利用できるコマンドと環境に関する情報を取得するには:</span><span class="sxs-lookup"><span data-stu-id="c8c09-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [-h|--help] [--version] [--info]
    [--list-runtimes] [--list-sdks]
```

<span data-ttu-id="c8c09-109">コマンドを実行するには (SDK のインストールが必要):</span><span class="sxs-lookup"><span data-stu-id="c8c09-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity]
    [command-options] [arguments]
```

<span data-ttu-id="c8c09-110">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="c8c09-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="c8c09-111">`--roll-forward` は、.NET Core 3.x 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="c8c09-112">.NET Core 2.x には `--roll-forward-on-no-candidate-fx` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="c8c09-113">説明</span><span class="sxs-lookup"><span data-stu-id="c8c09-113">Description</span></span>

<span data-ttu-id="c8c09-114">`dotnet` コマンドには、次の 2 つの機能があります。</span><span class="sxs-lookup"><span data-stu-id="c8c09-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="c8c09-115">.NET Core プロジェクトを操作するためのコマンドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c8c09-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="c8c09-116">たとえば、[`dotnet build`](dotnet-build.md) を使うと、プロジェクトをビルドできます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="c8c09-117">各コマンドには独自のオプションと引数が定義されています。</span><span class="sxs-lookup"><span data-stu-id="c8c09-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="c8c09-118">すべてのコマンドは、コマンドの使用方法に関する簡単なドキュメントを出力するための `--help` オプションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c8c09-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="c8c09-119">.NET Core アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="c8c09-120">アプリケーションを実行するには、アプリケーション `.dll` ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-120">You specify the path to an application `.dll` file to run the application.</span></span> <span data-ttu-id="c8c09-121">たとえば、`dotnet myapp.dll` を使うと、`myapp` アプリケーションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-121">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="c8c09-122">展開オプションについては、「[.NET Core アプリケーションの展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-122">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="c8c09-123">オプション</span><span class="sxs-lookup"><span data-stu-id="c8c09-123">Options</span></span>

<span data-ttu-id="c8c09-124">`dotnet` 単独、コマンドの実行、アプリケーションの実行にはさまざまなオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-124">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="c8c09-125">dotnet 単独のオプション</span><span class="sxs-lookup"><span data-stu-id="c8c09-125">Options for dotnet by itself</span></span>

<span data-ttu-id="c8c09-126">次のオプションは、`dotnet` 単独のものです。</span><span class="sxs-lookup"><span data-stu-id="c8c09-126">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="c8c09-127">たとえば、`dotnet --info` のようにします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-127">For example, `dotnet --info`.</span></span> <span data-ttu-id="c8c09-128">環境に関する情報が出力されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-128">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="c8c09-129">現在のオペレーティング システムや .NET Core バージョンのコミット SHA など、.NET Core インストールとコンピューター環境に関する詳細を出力します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-129">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="c8c09-130">使用中の .NET Core SDK のバージョンを印刷します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-130">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="c8c09-131">インストールされている .NET Core ランタイムの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-131">Prints out a list of the installed .NET Core runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="c8c09-132">インストールされている .NET Core SDK の一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-132">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c8c09-133">使用できるコマンドの一覧が出力されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-133">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="c8c09-134">コマンドを実行するための SDK のオプション</span><span class="sxs-lookup"><span data-stu-id="c8c09-134">SDK options for running a command</span></span>

<span data-ttu-id="c8c09-135">次のオプションは、コマンドを指定した `dotnet` 用です。</span><span class="sxs-lookup"><span data-stu-id="c8c09-135">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="c8c09-136">たとえば、`dotnet build --help` のようにします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-136">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="c8c09-137">診断出力を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-137">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c8c09-138">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c8c09-139">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="c8c09-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c8c09-140">すべてのコマンドでサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c8c09-140">Not supported in every command.</span></span> <span data-ttu-id="c8c09-141">このオプションを使用できるかどうかについては、そのコマンド ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-141">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c8c09-142">`dotnet build --help` など、特定のコマンドのドキュメントを出力します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-142">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="c8c09-143">各コマンドには、そのコマンドに固有のオプションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="c8c09-143">Each command defines options specific to that command.</span></span> <span data-ttu-id="c8c09-144">使用できるオプションの一覧については、そのコマンドのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-144">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="c8c09-145">ランタイム オプション</span><span class="sxs-lookup"><span data-stu-id="c8c09-145">Runtime options</span></span>

<span data-ttu-id="c8c09-146">次のオプションは、`dotnet` でアプリケーションを実行するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-146">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="c8c09-147">たとえば、`dotnet myapp.dll --fx-version 3.1.1` のようにします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-147">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="c8c09-148">プローブ ポリシーとプローブするアセンブリを含むパスです。</span><span class="sxs-lookup"><span data-stu-id="c8c09-148">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="c8c09-149">追加の *.deps.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="c8c09-149">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="c8c09-150">*deps.json* ファイルには、依存関係、コンパイル依存関係、アセンブリ競合に対処するためのバージョン情報の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8c09-150">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="c8c09-151">詳細については、GitHub の「[Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)」 (ランタイム構成ファイル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-151">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="c8c09-152">アプリケーションを実行するために使用する .NET Core ランタイムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="c8c09-152">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="c8c09-153">*runtimeconfig.json* ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="c8c09-153">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="c8c09-154">*runtimeconfig.json* ファイルは、ランタイム設定を含む構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c8c09-154">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="c8c09-155">詳細については、「[.NET Core ランタイム構成設定](../run-time-config/index.md#runtimeconfigjson)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-155">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="c8c09-156">**`--roll-forward-on-no-candidate-fx <N>`** **.NET Core 2.x SDK で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="c8c09-156">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="c8c09-157">必要な共有フレームワークが利用できない場合の動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-157">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="c8c09-158">`N` には以下があります。</span><span class="sxs-lookup"><span data-stu-id="c8c09-158">`N` can be:</span></span>

  - <span data-ttu-id="c8c09-159">`0` - マイナー バージョンのロールフォワードでも無効にします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-159">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="c8c09-160">`1` - マイナー バージョンはロール フォワードしますが、メジャー バージョンはしません。</span><span class="sxs-lookup"><span data-stu-id="c8c09-160">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="c8c09-161">これが既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="c8c09-161">This is the default behavior.</span></span>
  - <span data-ttu-id="c8c09-162">`2` - マイナー バージョンとメジャー バージョンをロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-162">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="c8c09-163">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-163">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="c8c09-164">**`--roll-forward <SETTING>`** **.NET Core SDK 3.0 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="c8c09-164">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="c8c09-165">アプリにロール フォ ワードを適用する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-165">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="c8c09-166">`SETTING` には次のいずれかの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-166">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="c8c09-167">指定しない場合の既定は、`Minor` です。</span><span class="sxs-lookup"><span data-stu-id="c8c09-167">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="c8c09-168">`LatestPatch` - 最新のパッチ バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-168">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="c8c09-169">これで、マイナー バージョンのロールフォワードが無効になります。</span><span class="sxs-lookup"><span data-stu-id="c8c09-169">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="c8c09-170">`Minor` - 要求されたマイナー バージョンが見つからない場合は、それよりも高い最小マイナー バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-170">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="c8c09-171">要求されたマイナー バージョンが存在する場合は、LatestPatch ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-171">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="c8c09-172">`Major` - 要求されたメジャー バージョンが見つからない場合は、それよりも高い最小メジャー バージョンで最小マイナー バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-172">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="c8c09-173">要求されたメジャー バージョンが存在する場合は、Minor ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-173">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="c8c09-174">`LatestMinor` - 要求されたマイナー バージョンが存在する場合でも、最上位のマイナー バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-174">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="c8c09-175">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="c8c09-175">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="c8c09-176">`LatestMajor` - 要求されたメジャーが存在する場合でも、最上位のメジャー バージョンで最上位のマイナー バージョンにロール フォワードします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-176">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="c8c09-177">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="c8c09-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="c8c09-178">`Disable` - ロール フォワードしません。</span><span class="sxs-lookup"><span data-stu-id="c8c09-178">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="c8c09-179">指定されたバージョンにのみバインドします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-179">Only bind to specified version.</span></span> <span data-ttu-id="c8c09-180">このポリシーは、最新のパッチにロールフォワードする機能が無効になるため、一般的な使用にはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="c8c09-180">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="c8c09-181">この値はテスト用にのみ推奨されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-181">This value is only recommended for testing.</span></span>

<span data-ttu-id="c8c09-182">`Disable` を除いて、すべての設定は使用できる最高のパッチ バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-182">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="c8c09-183">ロール フォワード動作は、プロジェクト ファイル プロパティ、ランタイム構成ファイル プロパティ、および環境変数でも構成できます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-183">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="c8c09-184">詳細については、「[メジャーバージョン ランタイムのロールフォワード](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-184">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="c8c09-185">dotnet コマンド</span><span class="sxs-lookup"><span data-stu-id="c8c09-185">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="c8c09-186">全般</span><span class="sxs-lookup"><span data-stu-id="c8c09-186">General</span></span>

| <span data-ttu-id="c8c09-187">コマンド</span><span class="sxs-lookup"><span data-stu-id="c8c09-187">Command</span></span>                                       | <span data-ttu-id="c8c09-188">関数</span><span class="sxs-lookup"><span data-stu-id="c8c09-188">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c8c09-189">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c8c09-189">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="c8c09-190">.NET Core アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-190">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c8c09-191">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="c8c09-191">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="c8c09-192">ビルドによって起動されたサーバーとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-192">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="c8c09-193">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c8c09-193">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="c8c09-194">クリーン ビルド出力です。</span><span class="sxs-lookup"><span data-stu-id="c8c09-194">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="c8c09-195">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c8c09-195">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="c8c09-196">コマンドのより詳細なドキュメントをオンラインで表示します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-196">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c8c09-197">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c8c09-197">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="c8c09-198">有効な Preview 2 プロジェクトを .NET Core SDK 1.0 プロジェクトに移行します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-198">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c8c09-199">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c8c09-199">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="c8c09-200">MSBuild コマンド ラインへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-200">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c8c09-201">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c8c09-201">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="c8c09-202">指定されたテンプレートの C# または F# プロジェクトを初期化します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-202">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c8c09-203">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c8c09-203">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="c8c09-204">コードの NuGet パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-204">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c8c09-205">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c8c09-205">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="c8c09-206">.NET Framework に依存するアプリケーションまたは自己完結型アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-206">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c8c09-207">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c8c09-207">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="c8c09-208">指定されたアプリケーションの依存関係を復元します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-208">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c8c09-209">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c8c09-209">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="c8c09-210">ソースからアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-210">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c8c09-211">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c8c09-211">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="c8c09-212">ソリューション ファイルのプロジェクトを追加、削除、一覧表示するオプション。</span><span class="sxs-lookup"><span data-stu-id="c8c09-212">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c8c09-213">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c8c09-213">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="c8c09-214">ランタイム パッケージ ストアにアセンブリを格納します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-214">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c8c09-215">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c8c09-215">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="c8c09-216">テスト ランナーを使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-216">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="c8c09-217">プロジェクト参照</span><span class="sxs-lookup"><span data-stu-id="c8c09-217">Project references</span></span>

<span data-ttu-id="c8c09-218">コマンド</span><span class="sxs-lookup"><span data-stu-id="c8c09-218">Command</span></span> | <span data-ttu-id="c8c09-219">関数</span><span class="sxs-lookup"><span data-stu-id="c8c09-219">Function</span></span>
--- | ---
[<span data-ttu-id="c8c09-220">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="c8c09-220">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="c8c09-221">プロジェクト参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-221">Adds a project reference.</span></span>
[<span data-ttu-id="c8c09-222">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c8c09-222">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="c8c09-223">プロジェクト参照をリストします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-223">Lists project references.</span></span>
[<span data-ttu-id="c8c09-224">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="c8c09-224">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="c8c09-225">プロジェクト参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-225">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="c8c09-226">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="c8c09-226">NuGet packages</span></span>

<span data-ttu-id="c8c09-227">コマンド</span><span class="sxs-lookup"><span data-stu-id="c8c09-227">Command</span></span> | <span data-ttu-id="c8c09-228">関数</span><span class="sxs-lookup"><span data-stu-id="c8c09-228">Function</span></span>
--- | ---
[<span data-ttu-id="c8c09-229">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="c8c09-229">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="c8c09-230">NuGet パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-230">Adds a NuGet package.</span></span>
[<span data-ttu-id="c8c09-231">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="c8c09-231">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="c8c09-232">NuGet パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-232">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="c8c09-233">NuGet コマンド</span><span class="sxs-lookup"><span data-stu-id="c8c09-233">NuGet commands</span></span>

<span data-ttu-id="c8c09-234">コマンド</span><span class="sxs-lookup"><span data-stu-id="c8c09-234">Command</span></span> | <span data-ttu-id="c8c09-235">関数</span><span class="sxs-lookup"><span data-stu-id="c8c09-235">Function</span></span>
--- | ---
[<span data-ttu-id="c8c09-236">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="c8c09-236">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="c8c09-237">サーバーからパッケージを削除または一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-237">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="c8c09-238">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c8c09-238">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="c8c09-239">パッケージをサーバーにプッシュして発行します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-239">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="c8c09-240">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="c8c09-240">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="c8c09-241">HTTP 要求キャッシュ、一時的なキャッシュ、コンピューター全体のグローバル パッケージ フォルダーなどのローカルの NuGet リソースをクリアまたは一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-241">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="c8c09-242">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="c8c09-242">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="c8c09-243">NuGet ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-243">Adds a NuGet source.</span></span>
[<span data-ttu-id="c8c09-244">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="c8c09-244">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="c8c09-245">NuGet ソースを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-245">Disables a NuGet source.</span></span>
[<span data-ttu-id="c8c09-246">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="c8c09-246">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="c8c09-247">NuGet ソースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-247">Enables a NuGet source.</span></span>
[<span data-ttu-id="c8c09-248">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="c8c09-248">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="c8c09-249">構成されている NuGet ソースをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-249">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="c8c09-250">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="c8c09-250">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="c8c09-251">NuGet ソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-251">Removes a NuGet source.</span></span>
[<span data-ttu-id="c8c09-252">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="c8c09-252">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="c8c09-253">NuGet ソースを更新します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-253">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="c8c09-254">グローバル、ツールパス、およびローカル ツールのコマンド</span><span class="sxs-lookup"><span data-stu-id="c8c09-254">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="c8c09-255">ツールは、NuGet パッケージからインストールされ、コマンド プロンプトから呼び出されるコンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c8c09-255">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="c8c09-256">ツールは自分で作成することも、サードパーティによって作成されたツールをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-256">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="c8c09-257">ツールは、グローバル ツール、ツールパス ツール、およびローカル ツールとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-257">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="c8c09-258">詳細については、[.NET Core ツールの概要](global-tools.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-258">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="c8c09-259">グローバル ツールとツールパス ツールは、.NET Core SDK 2.1 以降使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-259">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="c8c09-260">ローカル ツールは、.NET Core SDK 3.0 以降使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-260">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="c8c09-261">コマンド</span><span class="sxs-lookup"><span data-stu-id="c8c09-261">Command</span></span> | <span data-ttu-id="c8c09-262">関数</span><span class="sxs-lookup"><span data-stu-id="c8c09-262">Function</span></span>
--- | ---
[<span data-ttu-id="c8c09-263">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="c8c09-263">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="c8c09-264">ツールをお使いのコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-264">Installs a tool on your machine.</span></span>
[<span data-ttu-id="c8c09-265">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="c8c09-265">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="c8c09-266">コンピューターに現在インストールされているグローバル、ツールパス、またはローカル ツールをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-266">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="c8c09-267">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="c8c09-267">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="c8c09-268">ツールをお使いのコンピューターからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-268">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="c8c09-269">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="c8c09-269">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="c8c09-270">コンピューターにインストールされているツールを更新します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-270">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="c8c09-271">その他のツール</span><span class="sxs-lookup"><span data-stu-id="c8c09-271">Additional tools</span></span>

<span data-ttu-id="c8c09-272">.NET Core SDK 2.1.300 以降では、`DotnetCliToolReference` を使用してプロジェクト単位でのみ入手可能であった複数のツールを .NET Core SDK の一部として入手できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c8c09-272">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="c8c09-273">これらのツールを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-273">These tools are listed in the following table:</span></span>

| <span data-ttu-id="c8c09-274">ツール</span><span class="sxs-lookup"><span data-stu-id="c8c09-274">Tool</span></span>                                              | <span data-ttu-id="c8c09-275">関数</span><span class="sxs-lookup"><span data-stu-id="c8c09-275">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="c8c09-276">dev-certs</span><span class="sxs-lookup"><span data-stu-id="c8c09-276">dev-certs</span></span>                                         | <span data-ttu-id="c8c09-277">開発証明書を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-277">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="c8c09-278">ef</span><span class="sxs-lookup"><span data-stu-id="c8c09-278">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="c8c09-279">Entity Framework Core コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="c8c09-279">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="c8c09-280">sql-cache</span><span class="sxs-lookup"><span data-stu-id="c8c09-280">sql-cache</span></span>                                         | <span data-ttu-id="c8c09-281">SQL Server キャッシュ コマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="c8c09-281">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="c8c09-282">user-secrets</span><span class="sxs-lookup"><span data-stu-id="c8c09-282">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="c8c09-283">開発ユーザーのシークレットを管理します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-283">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="c8c09-284">watch</span><span class="sxs-lookup"><span data-stu-id="c8c09-284">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="c8c09-285">ファイルが変化するとコマンドを実行するファイル ウォッチャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-285">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="c8c09-286">各ツールの詳細については、`dotnet <tool-name> --help` と入力してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-286">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="c8c09-287">使用例</span><span class="sxs-lookup"><span data-stu-id="c8c09-287">Examples</span></span>

<span data-ttu-id="c8c09-288">新しい .NET Core コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-288">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="c8c09-289">指定されたディレクトリにプロジェクトとその依存関係をビルドします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-289">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="c8c09-290">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-290">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="c8c09-291">環境変数</span><span class="sxs-lookup"><span data-stu-id="c8c09-291">Environment variables</span></span>

- <span data-ttu-id="c8c09-292">`DOTNET_ROOT`、`DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="c8c09-292">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="c8c09-293">.NET Core ランタイムが既定の場所にインストールされていない場合、それらの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-293">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="c8c09-294">Windows 上の既定の場所は `C:\Program Files\dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="c8c09-294">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="c8c09-295">Linux と macOS 上の既定の場所は `/usr/share/dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="c8c09-295">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="c8c09-296">この環境変数は、生成された実行可能ファイル (apphosts) を介してアプリを実行する場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-296">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="c8c09-297">64 ビット OS 上で 32 ビット実行可能ファイルを実行する場合は、代わりに `DOTNET_ROOT(x86)` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-297">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="c8c09-298">グローバル パッケージ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="c8c09-298">The global packages folder.</span></span> <span data-ttu-id="c8c09-299">設定されていない場合は、既定で `~/.nuget/packages` (Unix の場合) または `%userprofile%\.nuget\packages` (Windows の場合) になります。</span><span class="sxs-lookup"><span data-stu-id="c8c09-299">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="c8c09-300">ランタイムの読み込み時に共有ホストで使用するサービス インデックスの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-300">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="c8c09-301">最初の実行時に .NET Core のウェルカム メッセージとテレメトリ メッセージを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-301">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="c8c09-302">`true` に設定すると、これらのメッセージは表示されません (値 `true`、`1`、または `yes` が受け入れられます)。`false` に設定すると許可されます (値 `false`、`0`、または `no` が受け入れられます)。</span><span class="sxs-lookup"><span data-stu-id="c8c09-302">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c8c09-303">設定しない場合、既定値は `false` であり、最初の実行時にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-303">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="c8c09-304">このフラグはテレメトリに影響しないことに注意してください (テレメトリの送信のオプトアウトについては `DOTNET_CLI_TELEMETRY_OPTOUT` を参照)。</span><span class="sxs-lookup"><span data-stu-id="c8c09-304">Note that this flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="c8c09-305">.NET Core ツールの使用に関するデータを収集し、Microsoft に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-305">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c8c09-306">`true` に設定するとテレメトリ機能が無効になります (指定できる値は `true`、`1`、または `yes` です)。</span><span class="sxs-lookup"><span data-stu-id="c8c09-306">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c8c09-307">それ以外の場合は `false` に設定します。この場合、テレメトリ機能が有効になります (指定できる値は `false`、`0`、または `no` です)。</span><span class="sxs-lookup"><span data-stu-id="c8c09-307">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c8c09-308">設定されていない場合、既定で `false` になり、テレメトリ機能はアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="c8c09-308">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="c8c09-309">.NET Core ランタイム、共有フレームワーク、または SDK がグローバルな場所から解決されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-309">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="c8c09-310">設定されていない場合、既定値は 1 (論理 `true`) です。</span><span class="sxs-lookup"><span data-stu-id="c8c09-310">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="c8c09-311">グローバルな場所から解決せず、.NET Core インストールを分離するには、0 (論理 `false`) に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-311">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="c8c09-312">複数レベルのルックアップの詳細については、「[Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)」 (複数レベルの SharedFX ルックアップ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-312">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="c8c09-313">`DOTNET_ROLL_FORWARD` **.NET Core 3.x SDK 以降で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="c8c09-313">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="c8c09-314">ロール フォワード動作を決定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-314">Determines roll forward behavior.</span></span> <span data-ttu-id="c8c09-315">詳細については、この記事で前述した `--roll-forward` オプションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-315">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="c8c09-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **.NET Core 2.x SDK で使用できます。**</span><span class="sxs-lookup"><span data-stu-id="c8c09-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="c8c09-317">`0` に設定されている場合、マイナー バージョンのロールフォワードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="c8c09-318">詳細については、「[Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward)」(ロールフォワード) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="c8c09-319">`en-us` などのロケール値を使用して、CLI UI の言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-319">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="c8c09-320">サポートされている値は、Visual Studio の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="c8c09-320">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="c8c09-321">詳細については、[Visual Studio のインストール ドキュメント](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)のインストーラーの言語を変更する方法に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c09-321">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="c8c09-322">.NET リソース マネージャーの規則が適用されるため、完全一致を選択する必要はありません。`CultureInfo` ツリーで子孫を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-322">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="c8c09-323">たとえば、`fr-CA` に設定すると、CLI によって `fr` の翻訳が検索され、使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c09-323">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="c8c09-324">サポートされていない言語に設定すると、CLI は英語にフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-324">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="c8c09-325">GUI 対応の生成された実行可能ファイルの場合、通常は特定のクラスのエラーに対して表示されるダイアログ ポップアップが無効になります。</span><span class="sxs-lookup"><span data-stu-id="c8c09-325">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="c8c09-326">この場合、`stderr` にのみ書き込まれ、終了します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-326">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="c8c09-327">CLI オプション `--additional-deps` に相当します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-327">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="c8c09-328">検出された RID をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="c8c09-328">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="c8c09-329">アセンブリの解決がフォールバックする "共有ストア" の場所。</span><span class="sxs-lookup"><span data-stu-id="c8c09-329">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="c8c09-330">スタートアップ フックを読み込み、実行するアセンブリの一覧。</span><span class="sxs-lookup"><span data-stu-id="c8c09-330">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="c8c09-331">`COREHOST_TRACE`、`COREHOST_TRACEFILE`、`COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="c8c09-331">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="c8c09-332">`dotnet.exe`、`hostfxr`、`hostpolicy` などのホスティング コンポーネントからの診断トレースを制御します。</span><span class="sxs-lookup"><span data-stu-id="c8c09-332">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8c09-333">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8c09-333">See also</span></span>

- [<span data-ttu-id="c8c09-334">ランタイム構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c8c09-334">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="c8c09-335">.NET Core ランタイム構成設定</span><span class="sxs-lookup"><span data-stu-id="c8c09-335">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
