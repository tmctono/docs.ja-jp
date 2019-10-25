---
title: dotnet-trace - .NET Core
description: dotnet-trace コマンドライン ツールのインストールおよび使用。
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: 6513cf63070bc1984006da75313e9912d76a6c95
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321532"
---
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a><span data-ttu-id="f1b95-103">パフォーマンス分析ユーティリティ (`dotnet-trace`) 用のトレース</span><span class="sxs-lookup"><span data-stu-id="f1b95-103">Trace for performance analysis utility (`dotnet-trace`)</span></span>

<span data-ttu-id="f1b95-104">**この記事の対象:** .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="f1b95-104">**This article applies to:** .NET Core 3.0 SDK and later versions</span></span>

## <a name="installing-dotnet-trace"></a><span data-ttu-id="f1b95-105">`dotnet-trace` のインストール</span><span class="sxs-lookup"><span data-stu-id="f1b95-105">Installing `dotnet-trace`</span></span>

<span data-ttu-id="f1b95-106">`dotnet-trace` [NuGet パッケージ](https://www.nuget.org/packages/dotnet-trace)の最新のリリース バージョンをインストールするには、次のように [dotnet tool install](../tools/dotnet-tool-install.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-106">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="f1b95-107">構文</span><span class="sxs-lookup"><span data-stu-id="f1b95-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="f1b95-108">説明</span><span class="sxs-lookup"><span data-stu-id="f1b95-108">Description</span></span>

<span data-ttu-id="f1b95-109">`dotnet-trace` ツールは、ネイティブ プロファイラーを使用せずに、実行中のプロセスの .NET Core のトレースを収集するクロスプラットフォームの CLI グローバル ツールです。</span><span class="sxs-lookup"><span data-stu-id="f1b95-109">The `dotnet-trace` tool is a cross-platform CLI global tool that enables the collection of .NET Core traces of a running process without any native profiler involved.</span></span> <span data-ttu-id="f1b95-110">これは、.NET Core ランタイムのクロスプラットフォームの `EventPipe` テクノロジを中心に構築されています。</span><span class="sxs-lookup"><span data-stu-id="f1b95-110">It's built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span> <span data-ttu-id="f1b95-111">`dotnet-trace` は、Windows、Linux または macOS でも同じエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-111">`dotnet-trace` delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="f1b95-112">オプション</span><span class="sxs-lookup"><span data-stu-id="f1b95-112">Options</span></span>

- **`--version`**

<span data-ttu-id="f1b95-113">dotnet-counters ユーティリティのバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-113">Display the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

<span data-ttu-id="f1b95-114">コマンド ラインのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-114">Show command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="f1b95-115">コマンド</span><span class="sxs-lookup"><span data-stu-id="f1b95-115">Commands</span></span>

| <span data-ttu-id="f1b95-116">コマンド</span><span class="sxs-lookup"><span data-stu-id="f1b95-116">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="f1b95-117">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="f1b95-117">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="f1b95-118">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="f1b95-118">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="f1b95-119">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="f1b95-119">dotnet-trace list-processes</span></span>](#dotnet-trace-list-processes) |
| [<span data-ttu-id="f1b95-120">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="f1b95-120">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="f1b95-121">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="f1b95-121">dotnet-trace collect</span></span>

<span data-ttu-id="f1b95-122">実行中のプロセスから診断トレースを収集します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-122">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f1b95-123">構文</span><span class="sxs-lookup"><span data-stu-id="f1b95-123">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="f1b95-124">オプション</span><span class="sxs-lookup"><span data-stu-id="f1b95-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="f1b95-125">トレースを収集するプロセス。</span><span class="sxs-lookup"><span data-stu-id="f1b95-125">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="f1b95-126">メモリ内の循環バッファーのサイズをメガバイトに設定します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-126">Sets the size of the in-memory circular buffer in megabytes.</span></span> <span data-ttu-id="f1b95-127">既定は 256 MB です。</span><span class="sxs-lookup"><span data-stu-id="f1b95-127">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="f1b95-128">収集されたトレース データの出力パス。</span><span class="sxs-lookup"><span data-stu-id="f1b95-128">The output path for the collected trace data.</span></span> <span data-ttu-id="f1b95-129">指定しない場合の既定は、`trace.nettrace` です。</span><span class="sxs-lookup"><span data-stu-id="f1b95-129">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="f1b95-130">有効にする `EventPipe` プロバイダーのコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="f1b95-130">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="f1b95-131">これらのプロバイダーは、`--profile <profile-name>` で示されている任意のプロバイダーを補完します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-131">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="f1b95-132">特定のプロバイダーに不整合がある場合、この構成がプロファイルの暗黙的な構成に優先されます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-132">If there's any inconsistency for a particular provider, the configuration here takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="f1b95-133">プロバイダーの一覧の形式は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1b95-133">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="f1b95-134">`Provider` は、`KnownProviderName[:Flags[:Level][:KeyValueArgs]]` という形式です。</span><span class="sxs-lookup"><span data-stu-id="f1b95-134">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="f1b95-135">`KeyValueArgs` は、`[key1=value1][;key2=value2]` という形式です。</span><span class="sxs-lookup"><span data-stu-id="f1b95-135">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="f1b95-136">共通のトレース シナリオを簡潔に指定できるようにする、事前定義されたプロバイダーの名前付き構成のセット。</span><span class="sxs-lookup"><span data-stu-id="f1b95-136">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="f1b95-137">トレース ファイルの出力の変換形式を設定します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-137">Sets the output format for the trace file conversion.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="f1b95-138">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="f1b95-138">dotnet-trace convert</span></span>

<span data-ttu-id="f1b95-139">`nettrace` トレースを、別のトレース分析ツールで使用するために、別の形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-139">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f1b95-140">構文</span><span class="sxs-lookup"><span data-stu-id="f1b95-140">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="f1b95-141">引数</span><span class="sxs-lookup"><span data-stu-id="f1b95-141">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="f1b95-142">変換する入力トレース ファイル。</span><span class="sxs-lookup"><span data-stu-id="f1b95-142">Input trace file to be converted.</span></span> <span data-ttu-id="f1b95-143">既定は *trace.nettrace* です。</span><span class="sxs-lookup"><span data-stu-id="f1b95-143">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="f1b95-144">オプション</span><span class="sxs-lookup"><span data-stu-id="f1b95-144">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="f1b95-145">トレース ファイルの出力の変換形式を設定します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-145">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="f1b95-146">出力ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="f1b95-146">Output filename.</span></span> <span data-ttu-id="f1b95-147">ターゲットの形式の拡張子が追加されます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-147">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-list-processes"></a><span data-ttu-id="f1b95-148">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="f1b95-148">dotnet-trace list-processes</span></span>

<span data-ttu-id="f1b95-149">トレースできる dotnet プロセスの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-149">Lists dotnet processes that can be traced.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f1b95-150">構文</span><span class="sxs-lookup"><span data-stu-id="f1b95-150">Synopsis</span></span>

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="f1b95-151">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="f1b95-151">dotnet-trace list-profiles</span></span>

<span data-ttu-id="f1b95-152">各プロファイルに含まれるプロバイダーとフィルターの記述と共に、事前に構築されているトレースのプロファイルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-152">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f1b95-153">構文</span><span class="sxs-lookup"><span data-stu-id="f1b95-153">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="f1b95-154">`dotnet-trace` を使用してトレースを収集する</span><span class="sxs-lookup"><span data-stu-id="f1b95-154">Collect a trace with `dotnet-trace`</span></span>

- <span data-ttu-id="f1b95-155">`dotnet-trace` を使用してトレースを収集するには、まずトレースを収集する .NET Core アプリケーションのプロセス識別子 (PID) を調べます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-155">To collect traces using `dotnet-trace`, you'll need to first, find out the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="f1b95-156">Windows では、タスク マネージャーや `tasklist` コマンドなどを使用するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f1b95-156">On Windows, there are options such as using the task manager or the `tasklist` command.</span></span>
  - <span data-ttu-id="f1b95-157">Linux での簡易オプションは、`ps` コマンドの使用です。</span><span class="sxs-lookup"><span data-stu-id="f1b95-157">On Linux, the trivial option could be using `ps` command.</span></span>

<span data-ttu-id="f1b95-158">また、その PID と共に [dotnet-trace list-processes](#dotnet-trace-list-processes) コマンドを使用して、実行中の .NET Core プロセスを調べることもできます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-158">You may also use the [dotnet-trace list-processes](#dotnet-trace-list-processes) command to find out what .NET Core processes are running, along with their PIDs.</span></span>

- <span data-ttu-id="f1b95-159">次に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-159">Then, run the following command:</span></span>

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- <span data-ttu-id="f1b95-160">最後に、`<Enter>` キーを押して収集を停止すると、`dotnet-trace` は `trace.nettrace` ファイルへのイベントのログ記録を終了します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-160">Finally, stop collection by pressing the `<Enter>` key, and `dotnet-trace` will finish logging events to `trace.nettrace` file.</span></span>

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="f1b95-161">`dotnet-trace` でキャプチャしたトレースを表示する</span><span class="sxs-lookup"><span data-stu-id="f1b95-161">Viewing the trace captured from `dotnet-trace`</span></span>

<span data-ttu-id="f1b95-162">Windows で `.nettrace` ファイルは、ETW または LTTng を使用して収集したトレースと同様、[PerfView ](https://github.com/microsoft/perfview) で参照して分析できます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-162">On Windows, `.nettrace` files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis, just like traces collected with ETW or LTTng.</span></span> <span data-ttu-id="f1b95-163">Linux で収集したトレースを PerfView で参照するには、トレースを Windows マシンに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-163">For traces collected on Linux, you can move the trace to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="f1b95-164">また、`dotnet-trace` の出力形式を `speedscope` に変更して、Linux マシンでトレースを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-164">You may also view the trace on a Linux machine by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="f1b95-165">出力ファイルの形式は、`-f|--format` オプションを使用して変更できます。`-f speedscope` が、`dotnet-trace` に `speedscope` ファイルを生成させます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-165">You can change the output file format using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` to produce a `speedscope` file.</span></span> <span data-ttu-id="f1b95-166">現在、`nettrace` (既定のオプション) と `speedscope` の間で選択できます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-166">You can currently choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="f1b95-167">`Speedscope` ファイルは <https://www.speedscope.app> で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-167">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="f1b95-168">.NET Core ランタイムは、トレースを `nettrace` 形式で生成し、トレースの完了後 (指定されている場合は)、それを speedscope に変換します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-168">The .NET Core runtime generates traces in the `nettrace` format, and they're converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="f1b95-169">変換によってはデータが失われる場合もあるため、元の `nettrace` ファイルが変換されたファイルの横に保持されます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-169">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="f1b95-170">`dotnet-trace` を使用して経時的なカウンター値を収集する</span><span class="sxs-lookup"><span data-stu-id="f1b95-170">Using `dotnet-trace` to collect counter values over time</span></span>

<span data-ttu-id="f1b95-171">パフォーマンスが影響する運用環境などの正常性の基本監視に `EventCounter` を使用する場合に、リアルタイムで監視するのではなく、トレースを収集したい場合は、`dotnet-trace` で行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-171">If you're trying to use `EventCounter` for basic health monitoring in  performance-sensitive settings like production environments and you want to collect traces instead of watching them in real time, you can do that with `dotnet-trace` as well.</span></span>

<span data-ttu-id="f1b95-172">たとえば、実行時のパフォーマンス カウンター値を収集したい場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1b95-172">For example, if you want to collect runtime performance counter values, you can use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="f1b95-173">このコマンドは、正常性の簡易監視のために 1 秒ごとにランタイム カウンターをレポートします。</span><span class="sxs-lookup"><span data-stu-id="f1b95-173">This command tells the runtime counters to be reported once every second for lightweight health monitoring.</span></span> <span data-ttu-id="f1b95-174">`EventCounterIntervalSec=1` の値を (60 など) 大きい値に置き換えた場合、カウンター データの細分性の詳細度がより低いトレースをより少数収集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f1b95-174">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows you to collect a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="f1b95-175">ランタイム イベントを無効にしてオーバーヘッド (およびトレースのサイズ) をさらに減らしたい場合は、次のコマンドを使用して、ランタイム イベントとマネージド スタック プロファイラーを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f1b95-175">If you want to disable runtime events to reduce the overhead (and trace size) even further, you can use the following command to disable runtime events and managed stack profiler.</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a><span data-ttu-id="f1b95-176">.NET プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f1b95-176">.NET Providers</span></span>

<span data-ttu-id="f1b95-177">.NET Core ランタイムでは、次の .NET プロバイダーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f1b95-177">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="f1b95-178">.NET Core では、`Event Tracing for Windows (ETW)` と `EventPipe` トレースの有効化に、いずれも同じキーワードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="f1b95-178">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="f1b95-179">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="f1b95-179">Provider name</span></span>                            | <span data-ttu-id="f1b95-180">情報</span><span class="sxs-lookup"><span data-stu-id="f1b95-180">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="f1b95-181">ランタイム プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f1b95-181">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="f1b95-182">CLR ランタイム キーワード</span><span class="sxs-lookup"><span data-stu-id="f1b95-182">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="f1b95-183">ランダウン プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f1b95-183">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="f1b95-184">CLR ランダウン キーワード</span><span class="sxs-lookup"><span data-stu-id="f1b95-184">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="f1b95-185">サンプル プロファイラーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f1b95-185">Enables the sample profiler.</span></span> |
