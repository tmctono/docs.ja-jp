---
title: dotnet-counters - .NET Core
description: dotnet-counter コマンドライン ツールをインストールして使用する方法について説明します。
ms.date: 10/14/2019
ms.openlocfilehash: 10af451a8b1b4d8b27da1490b99b19a4359c860f
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740802"
---
# <a name="dotnet-counters"></a><span data-ttu-id="22e60-103">dotnet-カウンター</span><span class="sxs-lookup"><span data-stu-id="22e60-103">dotnet-counters</span></span>

<span data-ttu-id="22e60-104">**この記事の対象: ✓** .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="22e60-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="22e60-105">dotnet-counters のインストール</span><span class="sxs-lookup"><span data-stu-id="22e60-105">Install dotnet-counters</span></span>

<span data-ttu-id="22e60-106">`dotnet-counters` [NuGet パッケージ](https://www.nuget.org/packages/dotnet-counters)の最新のリリース バージョンをインストールするには、次のように [dotnet tool install](../tools/dotnet-tool-install.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="22e60-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="22e60-107">構文</span><span class="sxs-lookup"><span data-stu-id="22e60-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="22e60-108">説明</span><span class="sxs-lookup"><span data-stu-id="22e60-108">Description</span></span>

<span data-ttu-id="22e60-109">`dotnet-counters` は、アドホックな正常性監視と第 1 レベルのパフォーマンス調査のためのパフォーマンス監視ツールです。</span><span class="sxs-lookup"><span data-stu-id="22e60-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="22e60-110"><xref:System.Diagnostics.Tracing.EventCounter> API を使用して公開されたパフォーマンス カウンターの値を監視できます。</span><span class="sxs-lookup"><span data-stu-id="22e60-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="22e60-111">たとえば、CPU 使用率や .NET Core アプリケーションでスローされる例外の発生率などを迅速に監視して、`PerfView` または `dotnet-trace` を使用した、より重大なパフォーマンス調査を開始する前に疑わしいものがあるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="22e60-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="22e60-112">オプション</span><span class="sxs-lookup"><span data-stu-id="22e60-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="22e60-113">dotnet-counters ユーティリティのバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="22e60-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="22e60-114">コマンド ライン ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="22e60-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="22e60-115">コマンド</span><span class="sxs-lookup"><span data-stu-id="22e60-115">Commands</span></span>

| <span data-ttu-id="22e60-116">コマンド</span><span class="sxs-lookup"><span data-stu-id="22e60-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="22e60-117">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="22e60-117">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="22e60-118">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="22e60-118">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |

## <a name="dotnet-counters-list"></a><span data-ttu-id="22e60-119">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="22e60-119">dotnet-counters list</span></span>

<span data-ttu-id="22e60-120">カウンターの名前と説明の一覧をプロバイダー別にグループ化して表示します。</span><span class="sxs-lookup"><span data-stu-id="22e60-120">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="22e60-121">構文</span><span class="sxs-lookup"><span data-stu-id="22e60-121">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="22e60-122">例</span><span class="sxs-lookup"><span data-stu-id="22e60-122">Example</span></span>

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

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="22e60-123">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="22e60-123">dotnet-counters monitor</span></span>

<span data-ttu-id="22e60-124">選択したカウンターの定期的に更新される値を表示します。</span><span class="sxs-lookup"><span data-stu-id="22e60-124">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="22e60-125">構文</span><span class="sxs-lookup"><span data-stu-id="22e60-125">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="22e60-126">オプション</span><span class="sxs-lookup"><span data-stu-id="22e60-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="22e60-127">監視するプロセスの ID。</span><span class="sxs-lookup"><span data-stu-id="22e60-127">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="22e60-128">表示されているカウンターを更新するまでの遅延時間 (秒数)</span><span class="sxs-lookup"><span data-stu-id="22e60-128">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="22e60-129">カウンターのスペース区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="22e60-129">A space separated list of counters.</span></span> <span data-ttu-id="22e60-130">カウンターは `provider_name[:counter_name]` で指定できます。</span><span class="sxs-lookup"><span data-stu-id="22e60-130">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="22e60-131">`counter_name` を修飾せずに `provider_name` を使用すると、すべてのカウンターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22e60-131">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="22e60-132">プロバイダーとカウンターの名前を検出するには、[dotnet-counters list](#dotnet-counters-list) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="22e60-132">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="22e60-133">使用例</span><span class="sxs-lookup"><span data-stu-id="22e60-133">Examples</span></span>

- <span data-ttu-id="22e60-134">3 秒の更新間隔で `System.Runtime` のすべてのカウンターを監視します。</span><span class="sxs-lookup"><span data-stu-id="22e60-134">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

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

- <span data-ttu-id="22e60-135">`System.Runtime` から CPU 使用率と GC ヒープ サイズのみを監視します。</span><span class="sxs-lookup"><span data-stu-id="22e60-135">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="22e60-136">ユーザー定義の `EventSource` の `EventCounter` 値を監視します。</span><span class="sxs-lookup"><span data-stu-id="22e60-136">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="22e60-137">詳しくは、「[チュートリアル: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22e60-137">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
