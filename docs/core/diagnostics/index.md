---
title: 診断ツールの概要 - .NET Core
description: .NET Core アプリケーションの診断に使用できるツールと手法の概要。
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: ae3b9a1961f331c9cdea786bd5fe06b7bfa10927
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558115"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="a9454-103">.NET Core で使用できる診断ツール</span><span class="sxs-lookup"><span data-stu-id="a9454-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="a9454-104">ソフトウェアは期待どおりに動作するとは限りませんが、.NET Core には、そのような問題を迅速かつ効果的に診断するために役立つツールと API が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a9454-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="a9454-105">この記事は、必要な各種ツールを見つけるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9454-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="a9454-106">マネージド デバッガー</span><span class="sxs-lookup"><span data-stu-id="a9454-106">Managed debuggers</span></span>

<span data-ttu-id="a9454-107">[マネージド デバッガー](managed-debuggers.md)を使用すると、プログラムと対話することができます。</span><span class="sxs-lookup"><span data-stu-id="a9454-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="a9454-108">一時停止、段階的な実行、調査、および再開によって、コードの動作を分析できます。</span><span class="sxs-lookup"><span data-stu-id="a9454-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="a9454-109">デバッガーは、簡単に再現できる機能の問題を診断するための最初の選択肢です。</span><span class="sxs-lookup"><span data-stu-id="a9454-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="a9454-110">ログとトレース</span><span class="sxs-lookup"><span data-stu-id="a9454-110">Logging and tracing</span></span>

<span data-ttu-id="a9454-111">[ログとトレース](logging-tracing.md)は、関連する手法です。</span><span class="sxs-lookup"><span data-stu-id="a9454-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="a9454-112">ログ ファイルを作成するためのコードのインストルメント化を指します。</span><span class="sxs-lookup"><span data-stu-id="a9454-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="a9454-113">ファイルには、プログラムの機能の詳細が記録されます。</span><span class="sxs-lookup"><span data-stu-id="a9454-113">The files record the details of what a program does.</span></span> <span data-ttu-id="a9454-114">これらの詳細は、複雑度の高い問題を診断するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9454-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="a9454-115">タイム スタンプと組み合わせると、これらの手法はパフォーマンスの調査にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9454-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="a9454-116">単体テスト</span><span class="sxs-lookup"><span data-stu-id="a9454-116">Unit testing</span></span>

<span data-ttu-id="a9454-117">[単体テスト](../testing/index.md)は、高品質のソフトウェアを継続的に統合して展開するための重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a9454-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="a9454-118">単体テストは、何かを中断するときに早期警告を提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a9454-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="a9454-119">.NET Core dotnet 診断グローバル ツール</span><span class="sxs-lookup"><span data-stu-id="a9454-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="a9454-120">dotnet-カウンター</span><span class="sxs-lookup"><span data-stu-id="a9454-120">dotnet-counters</span></span>

<span data-ttu-id="a9454-121">[dotnet-カウンター](dotnet-counters.md)は、第 1 レベルの正常性監視とパフォーマンス調査のためのパフォーマンス監視ツールです。</span><span class="sxs-lookup"><span data-stu-id="a9454-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="a9454-122"><xref:System.Diagnostics.Tracing.EventCounter> API を使用して公開されたパフォーマンス カウンターの値を監視します。</span><span class="sxs-lookup"><span data-stu-id="a9454-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="a9454-123">たとえば、CPU 使用率や、.NET Core アプリケーションでスローされる例外の発生率などをすばやく監視できます。</span><span class="sxs-lookup"><span data-stu-id="a9454-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="a9454-124">dotnet-ダンプ</span><span class="sxs-lookup"><span data-stu-id="a9454-124">dotnet-dump</span></span>

<span data-ttu-id="a9454-125">[dotnet-ダンプ](dotnet-dump.md) ツールは、ネイティブ デバッガーを使用せずに Windows と Linux のコア ダンプを収集して分析する方法です。</span><span class="sxs-lookup"><span data-stu-id="a9454-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="a9454-126">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="a9454-126">dotnet-gcdump</span></span>

<span data-ttu-id="a9454-127">[dotnet-gcdump](dotnet-gcdump.md) ツールは、ライブ .NET プロセスの GC (ガベージ コレクター) ダンプを収集する手段です。</span><span class="sxs-lookup"><span data-stu-id="a9454-127">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="a9454-128">dotnet-トレース</span><span class="sxs-lookup"><span data-stu-id="a9454-128">dotnet-trace</span></span>

<span data-ttu-id="a9454-129">.NET Core には、診断データが公開される `EventPipe` と呼ばれるものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9454-129">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="a9454-130">[dotnet-トレース](dotnet-trace.md) ツールを使用すると、アプリから興味深いプロファイル データを使用できます。これは、アプリケーションの実行速度が低下する可能性のあるシナリオに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9454-130">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="a9454-131">.NET Core 診断チュートリアル</span><span class="sxs-lookup"><span data-stu-id="a9454-131">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="a9454-132">メモリ リークをデバッグする</span><span class="sxs-lookup"><span data-stu-id="a9454-132">Debug a memory leak</span></span>

<span data-ttu-id="a9454-133">[チュートリアル: メモリ リークをデバッグする](debug-memory-leak.md)では、メモリ リークを検出する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9454-133">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="a9454-134">リークを確認するには [dotnet-counters](dotnet-counters.md) ツールを使用し、リークを診断するには [dotnet-dump](dotnet-dump.md) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9454-134">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="a9454-135">高い CPU 使用率をデバッグする</span><span class="sxs-lookup"><span data-stu-id="a9454-135">Debug high CPU usage</span></span>

<span data-ttu-id="a9454-136">[チュートリアル: 高い CPU 使用率をデバッグする](debug-highcpu.md) に関するページに、高い CPU 使用率の調査方法が示されています。</span><span class="sxs-lookup"><span data-stu-id="a9454-136">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="a9454-137">高い CPU 使用率を確認するために、[dotnet-counters](dotnet-counters.md) ツールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a9454-137">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="a9454-138">次に、[パフォーマンス分析ユーティリティ (`dotnet-trace`) 用のトレース](dotnet-trace.md)または Linux `perf` を使用して、CPU 使用率プロファイルを収集および表示する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9454-138">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="a9454-139">デッドロックをデバッグする</span><span class="sxs-lookup"><span data-stu-id="a9454-139">Debug deadlock</span></span>

<span data-ttu-id="a9454-140">[チュートリアル: デッドロックのデバッグ](debug-deadlock.md)に関するページに、[dotnet-dump](dotnet-dump.md) ツールを使用してスレッドとロックを調査する方法が示されています。</span><span class="sxs-lookup"><span data-stu-id="a9454-140">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>
