---
title: dotnet-counters - .NET Core
description: dotnet-counter コマンドライン ツールをインストールして使用する方法について説明します。
ms.date: 02/26/2020
ms.openlocfilehash: 88f701a60d0ee03dd0236ae54c57679943e14939
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157883"
---
# <a name="dotnet-counters"></a><span data-ttu-id="78897-103">dotnet-カウンター</span><span class="sxs-lookup"><span data-stu-id="78897-103">dotnet-counters</span></span>

<span data-ttu-id="78897-104">**この記事の対象:** ✔️ .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="78897-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="78897-105">dotnet-counters のインストール</span><span class="sxs-lookup"><span data-stu-id="78897-105">Install dotnet-counters</span></span>

<span data-ttu-id="78897-106">`dotnet-counters` [NuGet パッケージ](https://www.nuget.org/packages/dotnet-counters)の最新のリリース バージョンをインストールするには、次のように [dotnet tool install](../tools/dotnet-tool-install.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="78897-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="78897-107">構文</span><span class="sxs-lookup"><span data-stu-id="78897-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="78897-108">説明</span><span class="sxs-lookup"><span data-stu-id="78897-108">Description</span></span>

<span data-ttu-id="78897-109">`dotnet-counters` は、アドホックな正常性監視と第 1 レベルのパフォーマンス調査のためのパフォーマンス監視ツールです。</span><span class="sxs-lookup"><span data-stu-id="78897-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="78897-110"><xref:System.Diagnostics.Tracing.EventCounter> API を使用して公開されたパフォーマンス カウンターの値を監視できます。</span><span class="sxs-lookup"><span data-stu-id="78897-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="78897-111">たとえば、CPU 使用率や .NET Core アプリケーションでスローされる例外の発生率などを迅速に監視して、`PerfView` または `dotnet-trace` を使用した、より重大なパフォーマンス調査を開始する前に疑わしいものがあるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="78897-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="78897-112">オプション</span><span class="sxs-lookup"><span data-stu-id="78897-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="78897-113">dotnet-counters ユーティリティのバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="78897-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="78897-114">コマンド ライン ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="78897-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="78897-115">コマンド</span><span class="sxs-lookup"><span data-stu-id="78897-115">Commands</span></span>

| <span data-ttu-id="78897-116">コマンド</span><span class="sxs-lookup"><span data-stu-id="78897-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="78897-117">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="78897-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="78897-118">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="78897-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="78897-119">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="78897-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="78897-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="78897-120">dotnet-counters ps</span></span>](#dotnet-counters-ps) |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="78897-121">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="78897-121">dotnet-counters collect</span></span>

<span data-ttu-id="78897-122">選択されたカウンター値を定期的に収集し、後処理用に指定されたファイル形式にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="78897-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="78897-123">構文</span><span class="sxs-lookup"><span data-stu-id="78897-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="78897-124">オプション</span><span class="sxs-lookup"><span data-stu-id="78897-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="78897-125">監視するプロセスの ID。</span><span class="sxs-lookup"><span data-stu-id="78897-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="78897-126">表示されているカウンターを更新するまでの遅延時間 (秒数)</span><span class="sxs-lookup"><span data-stu-id="78897-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="78897-127">カウンターのスペース区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="78897-127">A space separated list of counters.</span></span> <span data-ttu-id="78897-128">カウンターは `provider_name[:counter_name]` で指定できます。</span><span class="sxs-lookup"><span data-stu-id="78897-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="78897-129">`counter_name` を修飾せずに `provider_name` を使用すると、すべてのカウンターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="78897-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="78897-130">プロバイダーとカウンターの名前を検出するには、[dotnet-counters list](#dotnet-counters-list) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="78897-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="78897-131">エクスポートされる形式。</span><span class="sxs-lookup"><span data-stu-id="78897-131">TThe format to be exported.</span></span> <span data-ttu-id="78897-132">現在使用可能: csv、json。</span><span class="sxs-lookup"><span data-stu-id="78897-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="78897-133">出力ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="78897-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="78897-134">使用例</span><span class="sxs-lookup"><span data-stu-id="78897-134">Examples</span></span>

- <span data-ttu-id="78897-135">すべてのカウンターを更新間隔 3 秒で収集し、csv を出力として生成します。</span><span class="sxs-lookup"><span data-stu-id="78897-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="78897-136">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="78897-136">dotnet-counters list</span></span>

<span data-ttu-id="78897-137">カウンターの名前と説明の一覧をプロバイダー別にグループ化して表示します。</span><span class="sxs-lookup"><span data-stu-id="78897-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="78897-138">構文</span><span class="sxs-lookup"><span data-stu-id="78897-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="78897-139">例</span><span class="sxs-lookup"><span data-stu-id="78897-139">Example</span></span>

```console
> dotnet-counters list

    Showing well-known counters only. Specific processes may support additional counters.
    System.Runtime
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="78897-140">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="78897-140">dotnet-counters monitor</span></span>

<span data-ttu-id="78897-141">選択したカウンターの定期的に更新される値を表示します。</span><span class="sxs-lookup"><span data-stu-id="78897-141">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="78897-142">構文</span><span class="sxs-lookup"><span data-stu-id="78897-142">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="78897-143">オプション</span><span class="sxs-lookup"><span data-stu-id="78897-143">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="78897-144">監視するプロセスの ID。</span><span class="sxs-lookup"><span data-stu-id="78897-144">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="78897-145">表示されているカウンターを更新するまでの遅延時間 (秒数)</span><span class="sxs-lookup"><span data-stu-id="78897-145">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="78897-146">カウンターのスペース区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="78897-146">A space separated list of counters.</span></span> <span data-ttu-id="78897-147">カウンターは `provider_name[:counter_name]` で指定できます。</span><span class="sxs-lookup"><span data-stu-id="78897-147">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="78897-148">`counter_name` を修飾せずに `provider_name` を使用すると、すべてのカウンターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="78897-148">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="78897-149">プロバイダーとカウンターの名前を検出するには、[dotnet-counters list](#dotnet-counters-list) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="78897-149">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="78897-150">使用例</span><span class="sxs-lookup"><span data-stu-id="78897-150">Examples</span></span>

- <span data-ttu-id="78897-151">3 秒の更新間隔で `System.Runtime` のすべてのカウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="78897-151">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="78897-152">`System.Runtime` から CPU 使用率と GC ヒープ サイズのみを監視します。</span><span class="sxs-lookup"><span data-stu-id="78897-152">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="78897-153">ユーザー定義の `EventSource` の `EventCounter` 値を監視します。</span><span class="sxs-lookup"><span data-stu-id="78897-153">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="78897-154">詳しくは、「[チュートリアル: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78897-154">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="78897-155">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="78897-155">dotnet-counters ps</span></span> 

<span data-ttu-id="78897-156">監視できる dotnet プロセスの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="78897-156">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="78897-157">構文</span><span class="sxs-lookup"><span data-stu-id="78897-157">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="78897-158">例</span><span class="sxs-lookup"><span data-stu-id="78897-158">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
