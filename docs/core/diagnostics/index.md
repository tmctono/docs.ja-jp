---
title: 診断ツールの概要 - .NET Core
description: .NET Core アプリケーションの診断に使用できるツールと手法の概要。
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.topic: overview
ms.openlocfilehash: c0a45a1bfe866ad42890db576b5dd5098b1dbc3d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318347"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="07920-103">.NET Core で使用できる診断ツール</span><span class="sxs-lookup"><span data-stu-id="07920-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="07920-104">ソフトウェアは期待どおりに動作するとは限りませんが、.NET Core には、そのような問題を迅速かつ効果的に診断するために役立つツールと API が用意されています。</span><span class="sxs-lookup"><span data-stu-id="07920-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="07920-105">この記事は、必要な各種ツールを見つけるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07920-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="07920-106">マネージド デバッガー</span><span class="sxs-lookup"><span data-stu-id="07920-106">Managed debuggers</span></span>

<span data-ttu-id="07920-107">[マネージド デバッガー](managed-debuggers.md)を使用すると、プログラムと対話することができます。</span><span class="sxs-lookup"><span data-stu-id="07920-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="07920-108">一時停止、段階的な実行、調査、および再開によって、コードの動作を分析できます。</span><span class="sxs-lookup"><span data-stu-id="07920-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="07920-109">デバッガーは、簡単に再現できる機能の問題を診断するための最初の選択肢です。</span><span class="sxs-lookup"><span data-stu-id="07920-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="07920-110">ログとトレース</span><span class="sxs-lookup"><span data-stu-id="07920-110">Logging and tracing</span></span>

<span data-ttu-id="07920-111">[ログとトレース](logging-tracing.md)は、関連する手法です。</span><span class="sxs-lookup"><span data-stu-id="07920-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="07920-112">ログ ファイルを作成するためのコードのインストルメント化を指します。</span><span class="sxs-lookup"><span data-stu-id="07920-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="07920-113">ファイルには、プログラムの機能の詳細が記録されます。</span><span class="sxs-lookup"><span data-stu-id="07920-113">The files record the details of what a program does.</span></span> <span data-ttu-id="07920-114">これらの詳細は、複雑度の高い問題を診断するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="07920-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="07920-115">タイム スタンプと組み合わせると、これらの手法はパフォーマンスの調査にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07920-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="07920-116">単体テスト</span><span class="sxs-lookup"><span data-stu-id="07920-116">Unit testing</span></span>

<span data-ttu-id="07920-117">[単体テスト](../testing/index.md)は、高品質のソフトウェアを継続的に統合して展開するための重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="07920-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="07920-118">単体テストは、何かを中断するときに早期警告を提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="07920-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="07920-119">.NET Core dotnet 診断グローバル ツール</span><span class="sxs-lookup"><span data-stu-id="07920-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="07920-120">dotnet-カウンター</span><span class="sxs-lookup"><span data-stu-id="07920-120">dotnet-counters</span></span>

<span data-ttu-id="07920-121">[dotnet-カウンター](dotnet-counters.md)は、第 1 レベルの正常性監視とパフォーマンス調査のためのパフォーマンス監視ツールです。</span><span class="sxs-lookup"><span data-stu-id="07920-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="07920-122"><xref:System.Diagnostics.Tracing.EventCounter> API を使用して公開されたパフォーマンス カウンターの値を監視します。</span><span class="sxs-lookup"><span data-stu-id="07920-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="07920-123">たとえば、CPU 使用率や、.NET Core アプリケーションでスローされる例外の発生率などをすばやく監視できます。</span><span class="sxs-lookup"><span data-stu-id="07920-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="07920-124">dotnet-ダンプ</span><span class="sxs-lookup"><span data-stu-id="07920-124">dotnet-dump</span></span>

<span data-ttu-id="07920-125">[dotnet-ダンプ](dotnet-dump.md) ツールは、ネイティブ デバッガーを使用せずに Windows と Linux のコア ダンプを収集して分析する方法です。</span><span class="sxs-lookup"><span data-stu-id="07920-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="07920-126">dotnet-トレース</span><span class="sxs-lookup"><span data-stu-id="07920-126">dotnet-trace</span></span>

<span data-ttu-id="07920-127">.NET Core には、診断データが公開される `EventPipe` と呼ばれるものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="07920-127">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="07920-128">[dotnet-トレース](dotnet-trace.md) ツールを使用すると、アプリから興味深いプロファイル データを使用できます。これは、アプリケーションの実行速度が低下する可能性のあるシナリオに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07920-128">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>
