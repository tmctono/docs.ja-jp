---
title: dotnet-trace ツール - .NET Core
description: dotnet-trace コマンドライン ツールのインストールおよび使用。
ms.date: 11/21/2019
ms.openlocfilehash: 6880c3721e4cab12677bd02c82ca944cc9812670
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888086"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="64cbd-103">dotnet-trace パフォーマンス分析ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="64cbd-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="64cbd-104">**この記事の対象:** ✔️ .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="64cbd-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="64cbd-105">dotnet-trace をインストールする</span><span class="sxs-lookup"><span data-stu-id="64cbd-105">Install dotnet-trace</span></span>

<span data-ttu-id="64cbd-106">[dotnet tool install](../tools/dotnet-tool-install.md) コマンドで `dotnet-trace` [NuGet パッケージ](https://www.nuget.org/packages/dotnet-trace)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="64cbd-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="64cbd-107">構文</span><span class="sxs-lookup"><span data-stu-id="64cbd-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="64cbd-108">説明</span><span class="sxs-lookup"><span data-stu-id="64cbd-108">Description</span></span>

<span data-ttu-id="64cbd-109">`dotnet-trace` ツール:</span><span class="sxs-lookup"><span data-stu-id="64cbd-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="64cbd-110">クロスプラットフォーム .NET Core ツールです。</span><span class="sxs-lookup"><span data-stu-id="64cbd-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="64cbd-111">ネイティブ プロファイラーなしで実行中のプロセスの .NET Core トレースを回収できます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="64cbd-112">.NET Core ランタイムのクロスプラットフォームの `EventPipe` テクノロジを中心に構築されています。</span><span class="sxs-lookup"><span data-stu-id="64cbd-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="64cbd-113">Windows、Linux または macOS でも同じエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="64cbd-114">オプション</span><span class="sxs-lookup"><span data-stu-id="64cbd-114">Options</span></span>

- **`--version`**

  <span data-ttu-id="64cbd-115">dotnet-trace ユーティリティのバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-115">Displays the version of the dotnet-trace utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="64cbd-116">コマンド ライン ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-116">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="64cbd-117">コマンド</span><span class="sxs-lookup"><span data-stu-id="64cbd-117">Commands</span></span>

| <span data-ttu-id="64cbd-118">コマンド</span><span class="sxs-lookup"><span data-stu-id="64cbd-118">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="64cbd-119">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="64cbd-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="64cbd-120">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="64cbd-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="64cbd-121">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="64cbd-121">dotnet-trace ps</span></span>](#dotnet-trace-ps) |
| [<span data-ttu-id="64cbd-122">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="64cbd-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="64cbd-123">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="64cbd-123">dotnet-trace collect</span></span>

<span data-ttu-id="64cbd-124">実行中のプロセスから診断トレースを収集します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="64cbd-125">構文</span><span class="sxs-lookup"><span data-stu-id="64cbd-125">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="64cbd-126">オプション</span><span class="sxs-lookup"><span data-stu-id="64cbd-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="64cbd-127">トレースを収集するプロセス。</span><span class="sxs-lookup"><span data-stu-id="64cbd-127">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="64cbd-128">メモリ内の循環バッファーのサイズをメガバイトに設定します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-128">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="64cbd-129">既定は 256 MB です。</span><span class="sxs-lookup"><span data-stu-id="64cbd-129">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="64cbd-130">収集されたトレース データの出力パス。</span><span class="sxs-lookup"><span data-stu-id="64cbd-130">The output path for the collected trace data.</span></span> <span data-ttu-id="64cbd-131">指定しない場合の既定は、`trace.nettrace` です。</span><span class="sxs-lookup"><span data-stu-id="64cbd-131">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="64cbd-132">有効にする `EventPipe` プロバイダーのコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="64cbd-132">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="64cbd-133">これらのプロバイダーは、`--profile <profile-name>` で示されている任意のプロバイダーを補完します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-133">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="64cbd-134">特定のプロバイダーに不整合がある場合、この構成がプロファイルの暗黙的な構成に優先されます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-134">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="64cbd-135">プロバイダーの一覧の形式は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64cbd-135">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="64cbd-136">`Provider` は、`KnownProviderName[:Flags[:Level][:KeyValueArgs]]` という形式です。</span><span class="sxs-lookup"><span data-stu-id="64cbd-136">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="64cbd-137">`KeyValueArgs` は、`[key1=value1][;key2=value2]` という形式です。</span><span class="sxs-lookup"><span data-stu-id="64cbd-137">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="64cbd-138">共通のトレース シナリオを簡潔に指定できるようにする、事前定義されたプロバイダーの名前付き構成のセット。</span><span class="sxs-lookup"><span data-stu-id="64cbd-138">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format {NetTrace|Speedscope}`**

  <span data-ttu-id="64cbd-139">トレース ファイルの出力の変換形式を設定します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-139">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="64cbd-140">既定値は、`NetTrace` です。</span><span class="sxs-lookup"><span data-stu-id="64cbd-140">The default is `NetTrace`.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="64cbd-141">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="64cbd-141">dotnet-trace convert</span></span>

<span data-ttu-id="64cbd-142">`nettrace` トレースを、別のトレース分析ツールで使用するために、別の形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-142">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="64cbd-143">構文</span><span class="sxs-lookup"><span data-stu-id="64cbd-143">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="64cbd-144">引数</span><span class="sxs-lookup"><span data-stu-id="64cbd-144">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="64cbd-145">変換する入力トレース ファイル。</span><span class="sxs-lookup"><span data-stu-id="64cbd-145">Input trace file to be converted.</span></span> <span data-ttu-id="64cbd-146">既定は *trace.nettrace* です。</span><span class="sxs-lookup"><span data-stu-id="64cbd-146">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="64cbd-147">オプション</span><span class="sxs-lookup"><span data-stu-id="64cbd-147">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="64cbd-148">トレース ファイルの出力の変換形式を設定します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-148">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="64cbd-149">出力ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="64cbd-149">Output filename.</span></span> <span data-ttu-id="64cbd-150">ターゲットの形式の拡張子が追加されます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-150">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="64cbd-151">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="64cbd-151">dotnet-trace ps</span></span>

<span data-ttu-id="64cbd-152">接続できる dotnet プロセスの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-152">Lists dotnet processes that can be attached to.</span></span>

### <a name="synopsis"></a><span data-ttu-id="64cbd-153">構文</span><span class="sxs-lookup"><span data-stu-id="64cbd-153">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="64cbd-154">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="64cbd-154">dotnet-trace list-profiles</span></span>

<span data-ttu-id="64cbd-155">各プロファイルに含まれるプロバイダーとフィルターの記述と共に、事前に構築されているトレースのプロファイルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-155">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="64cbd-156">構文</span><span class="sxs-lookup"><span data-stu-id="64cbd-156">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="64cbd-157">dotnet-trace を使用してトレースを収集する</span><span class="sxs-lookup"><span data-stu-id="64cbd-157">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="64cbd-158">`dotnet-trace` を使用してトレースを収集するには:</span><span class="sxs-lookup"><span data-stu-id="64cbd-158">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="64cbd-159">トレースを収集する .NET Core アプリケーションのプロセス識別子 (PID) を取得します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-159">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="64cbd-160">Windows で、タスク マネージャーや、たとえば、`tasklist` コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-160">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="64cbd-161">Linux の場合、たとえば、`ps` コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-161">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="64cbd-162">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="64cbd-162">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="64cbd-163">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-163">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="64cbd-164">上のコマンドを実行すると、次のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-164">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="64cbd-165">`<Enter>` キーを押すと、コレクションが停止します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-165">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="64cbd-166">`dotnet-trace` では、*trace.nettrace* ファイルにイベントをログ記録する作業が完了します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-166">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="64cbd-167">dotnet-trace からキャプチャされたトレースを表示する</span><span class="sxs-lookup"><span data-stu-id="64cbd-167">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="64cbd-168">Windows の場合、 *.nettrace* ファイルを [PerfView](https://github.com/microsoft/perfview) で表示し、分析できます。他のプラットフォームで収集されたトレースについては、トレース ファイルを Windows コンピューターに移動し、PerfView で表示できます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-168">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="64cbd-169">Linux の場合、`dotnet-trace` の出力形式を `speedscope` に変更することでトレースを表示できます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-169">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="64cbd-170">出力ファイル形式は `-f|--format` オプションで変更できます。`-f speedscope` により、`dotnet-trace` で `speedscope` ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-170">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="64cbd-171">`nettrace` (既定のオプション) か `speedscope` を選択できます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-171">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="64cbd-172">`Speedscope` ファイルは <https://www.speedscope.app> で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-172">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="64cbd-173">.NET Core ランタイムにより、`nettrace` 形式でトレースが生成されます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-173">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="64cbd-174">トレースの完了後、トレースは speedscope に変換されます (指定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="64cbd-174">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="64cbd-175">変換によってはデータが失われる場合もあるため、元の `nettrace` ファイルが変換されたファイルの横に保持されます。</span><span class="sxs-lookup"><span data-stu-id="64cbd-175">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="64cbd-176">dotnet-trace を使用して経時的なカウンター値を収集する</span><span class="sxs-lookup"><span data-stu-id="64cbd-176">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="64cbd-177">`dotnet-trace` でできること:</span><span class="sxs-lookup"><span data-stu-id="64cbd-177">`dotnet-trace` can:</span></span>

* <span data-ttu-id="64cbd-178">パフォーマンスで左右される環境で基本的な正常性監視を行うには `EventCounter` を使用します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-178">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="64cbd-179">たとえば、運用環境です。</span><span class="sxs-lookup"><span data-stu-id="64cbd-179">For example, in production.</span></span>
* <span data-ttu-id="64cbd-180">リアルタイムで表示する必要がないようにトレースを収集します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-180">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="64cbd-181">たとえば、実行時のパフォーマンス カウンター値を収集するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-181">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="64cbd-182">先のコマンドでは、正常性の簡易監視を 1 秒ごとに報告するようにランタイム カウンターに命令します。</span><span class="sxs-lookup"><span data-stu-id="64cbd-182">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="64cbd-183">`EventCounterIntervalSec=1` の値を (60 など) 大きい値に置き換えた場合、カウンター データの細分性の詳細度がより低いトレースをより少数収集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="64cbd-183">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="64cbd-184">次のコマンドでは、先のコマンドよりオーバーヘッドとトレース サイズが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="64cbd-184">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="64cbd-185">上のコマンドでは、ランタイム イベントとマネージド スタック プロファイラーが無効になります。</span><span class="sxs-lookup"><span data-stu-id="64cbd-185">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="64cbd-186">.NET プロバイダー</span><span class="sxs-lookup"><span data-stu-id="64cbd-186">.NET Providers</span></span>

<span data-ttu-id="64cbd-187">.NET Core ランタイムでは、次の .NET プロバイダーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="64cbd-187">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="64cbd-188">.NET Core では、`Event Tracing for Windows (ETW)` と `EventPipe` トレースの有効化に、いずれも同じキーワードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="64cbd-188">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="64cbd-189">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="64cbd-189">Provider name</span></span>                            | <span data-ttu-id="64cbd-190">情報</span><span class="sxs-lookup"><span data-stu-id="64cbd-190">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="64cbd-191">ランタイム プロバイダー</span><span class="sxs-lookup"><span data-stu-id="64cbd-191">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="64cbd-192">CLR ランタイム キーワード</span><span class="sxs-lookup"><span data-stu-id="64cbd-192">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="64cbd-193">ランダウン プロバイダー</span><span class="sxs-lookup"><span data-stu-id="64cbd-193">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="64cbd-194">CLR ランダウン キーワード</span><span class="sxs-lookup"><span data-stu-id="64cbd-194">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="64cbd-195">サンプル プロファイラーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="64cbd-195">Enables the sample profiler.</span></span> |
