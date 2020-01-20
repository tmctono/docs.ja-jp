---
title: メモリ リークのデバッグ チュートリアル
description: .NET Core でメモリ リークをデバッグする方法について説明します。
ms.topic: tutorial
ms.date: 12/17/2019
ms.openlocfilehash: cb137503cbc81f5ab9438dadcf1dc1c6750a1ca8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715600"
---
# <a name="tutorial-debug-a-memory-leak-in-net-core"></a><span data-ttu-id="63ee1-103">チュートリアル: .NET Core でメモリ リークをデバッグする</span><span class="sxs-lookup"><span data-stu-id="63ee1-103">Tutorial: Debug a memory leak in .NET Core</span></span>

<span data-ttu-id="63ee1-104">**この記事の対象: ✓** .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="63ee1-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="63ee1-105">このチュートリアルでは、.NET Core のメモリ リークを分析するためのツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-105">This tutorial demonstrates the tools to analyze a .NET Core memory leak.</span></span>

<span data-ttu-id="63ee1-106">このチュートリアルでは、意図的にメモリをリークするように設計されたサンプル アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-106">This tutorial uses a sample app, which is designed to intentionally leak memory.</span></span> <span data-ttu-id="63ee1-107">このサンプルは演習として提供されています。</span><span class="sxs-lookup"><span data-stu-id="63ee1-107">The sample is provided as an exercise.</span></span> <span data-ttu-id="63ee1-108">意図せずにメモリをリークしているアプリも分析できます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-108">You can analyze an app that is unintentionally leaking memory too.</span></span>

<span data-ttu-id="63ee1-109">このチュートリアルでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="63ee1-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="63ee1-110">[dotnet-counters](dotnet-counters.md) を使用してマネージド メモリの使用量を確認します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-110">Examine managed memory usage with [dotnet-counters](dotnet-counters.md).</span></span>
> - <span data-ttu-id="63ee1-111">ダンプ ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-111">Generate a dump file.</span></span>
> - <span data-ttu-id="63ee1-112">ダンプ ファイルを使用してメモリ使用量を分析します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-112">Analyze the memory usage using the dump file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="63ee1-113">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="63ee1-113">Prerequisites</span></span>

<span data-ttu-id="63ee1-114">このチュートリアルでは次のものを使用します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-114">The tutorial uses:</span></span>

- <span data-ttu-id="63ee1-115">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) 以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="63ee1-115">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="63ee1-116">プロセスを一覧表示するための [dotnet-trace](dotnet-trace.md)。</span><span class="sxs-lookup"><span data-stu-id="63ee1-116">[dotnet-trace](dotnet-trace.md) to list processes.</span></span>
- <span data-ttu-id="63ee1-117">マネージド メモリ使用量を確認するための [dotnet-counters](dotnet-counters.md)。</span><span class="sxs-lookup"><span data-stu-id="63ee1-117">[dotnet-counters](dotnet-counters.md) to check managed memory usage.</span></span>
- <span data-ttu-id="63ee1-118">ダンプ ファイルを収集して分析するための [dotnet-dump](dotnet-dump.md)。</span><span class="sxs-lookup"><span data-stu-id="63ee1-118">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file.</span></span>
- <span data-ttu-id="63ee1-119">診断する[サンプル デバッグ ターゲット](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) アプリ。</span><span class="sxs-lookup"><span data-stu-id="63ee1-119">A [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) app to diagnose.</span></span>

<span data-ttu-id="63ee1-120">このチュートリアルでは、サンプルとツールがインストールされ、使用できる状態であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="63ee1-120">The tutorial assumes the sample and tools are installed and ready to use.</span></span>

## <a name="examine-managed-memory-usage"></a><span data-ttu-id="63ee1-121">マネージド メモリ使用量を確認する</span><span class="sxs-lookup"><span data-stu-id="63ee1-121">Examine managed memory usage</span></span>

<span data-ttu-id="63ee1-122">このシナリオの根本原因を突き止めるのに役立つ診断データの収集を開始する前に、メモリ リーク (メモリの増加) が実際に発生していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ee1-122">Before you start collecting diagnostics data to help us root cause this scenario, you need to make sure you're actually seeing a memory leak (memory growth).</span></span> <span data-ttu-id="63ee1-123">それを確認するには、[dotnet-counters](dotnet-counters.md) ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-123">You can use the [dotnet-counters](dotnet-counters.md) tool to confirm that.</span></span>

<span data-ttu-id="63ee1-124">コンソール ウィンドウを開き、[サンプル デバッグ ターゲット](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/)をダウンロードして解凍したディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-124">Open a console window and navigate to the directory where you downloaded and unzipped the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/).</span></span> <span data-ttu-id="63ee1-125">ターゲットを実行します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-125">Run the target:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="63ee1-126">別のコンソールから、[dotnet-trace](dotnet-trace.md) ツールを使用してプロセス ID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-126">From a separate console, find the process ID using the [dotnet-trace](dotnet-trace.md) tool:</span></span>

```console
dotnet-trace ps
```

<span data-ttu-id="63ee1-127">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="63ee1-127">The output should be similar to:</span></span>

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

<span data-ttu-id="63ee1-128">次に、[dotnet-counters](dotnet-counters.md) ツールを使用してマネージド メモリ使用量を確認します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-128">Now, check managed memory usage with the [dotnet-counters](dotnet-counters.md) tool.</span></span> <span data-ttu-id="63ee1-129">`--refresh-interval` は、更新間隔を秒数で指定します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-129">The `--refresh-interval` specifies the number of seconds between refreshes:</span></span>

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

<span data-ttu-id="63ee1-130">ライブ出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="63ee1-130">The live output should be similar to:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    # of Assemblies Loaded                           118
    % Time in GC (since last GC)                       0
    Allocation Rate (Bytes / sec)                 37,896
    CPU Usage (%)                                      0
    Exceptions / sec                                   0
    GC Heap Size (MB)                                  4
    Gen 0 GC / sec                                     0
    Gen 0 Size (B)                                     0
    Gen 1 GC / sec                                     0
    Gen 1 Size (B)                                     0
    Gen 2 GC / sec                                     0
    Gen 2 Size (B)                                     0
    LOH Size (B)                                       0
    Monitor Lock Contention Count / sec                0
    Number of Active Timers                            1
    ThreadPool Completed Work Items / sec             10
    ThreadPool Queue Length                            0
    ThreadPool Threads Count                           1
    Working Set (MB)                                  83
```

<span data-ttu-id="63ee1-131">次の行に焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-131">Focusing on this line:</span></span>

```console
    GC Heap Size (MB)                                  4
```

<span data-ttu-id="63ee1-132">スタートアップの直後、マネージド ヒープ メモリは 4 MB であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="63ee1-132">You can see that the managed heap memory is 4 MB right after startup.</span></span>

<span data-ttu-id="63ee1-133">次に、URL `http://localhost:5000/api/diagscenario/memleak/20000` を指定します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-133">Now, hit the URL `http://localhost:5000/api/diagscenario/memleak/20000`.</span></span>

<span data-ttu-id="63ee1-134">メモリ使用量が 30 MB に増加していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="63ee1-134">Observe that the memory usage has grown to 30 MB.</span></span>

```console
    GC Heap Size (MB)                                 30
```

<span data-ttu-id="63ee1-135">メモリ使用量を監視することにより、メモリが増加していること、またはリークしていることを確実に知ることができます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-135">By watching the memory usage, you can safely say that memory is growing or leaking.</span></span> <span data-ttu-id="63ee1-136">次の手順では、メモリ分析に適切なデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-136">The next step is to collect the right data for memory analysis.</span></span>

### <a name="generate-memory-dump"></a><span data-ttu-id="63ee1-137">メモリ ダンプを生成する</span><span class="sxs-lookup"><span data-stu-id="63ee1-137">Generate memory dump</span></span>

<span data-ttu-id="63ee1-138">メモリ リークの可能性について分析するときは、アプリのメモリ ヒープにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ee1-138">When analyzing possible memory leaks, you need access to the app's memory heap.</span></span> <span data-ttu-id="63ee1-139">その後、メモリーの内容を分析できます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-139">Then you can analyze the memory contents.</span></span> <span data-ttu-id="63ee1-140">オブジェクト間の関係を確認して、メモリが解放されない理由についての理論を作成します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-140">Looking at relationships between objects, you create theories on why memory isn't being freed.</span></span> <span data-ttu-id="63ee1-141">一般的な診断データのソースは、Windows 上のメモリ ダンプ、または Linux 上の同等のコア ダンプです。</span><span class="sxs-lookup"><span data-stu-id="63ee1-141">A common diagnostics data source is a memory dump on Windows or the equivalent core dump on Linux.</span></span> <span data-ttu-id="63ee1-142">.NET Core アプリケーションのダンプを生成するには、[dotnet-dump](dotnet-dump.md) ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-142">To generate a dump of a .NET Core application, you can use the [dotnet-dump)](dotnet-dump.md) tool.</span></span>

<span data-ttu-id="63ee1-143">前に開始した[サンプル デバッグ ターゲット](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/)を使用して、次のコマンドを実行し、Linux コア ダンプを生成します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-143">Using the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) previously started, run the following command to generate a Linux core dump:</span></span>

```dotnetcli
dotnet-dump collect -p 4807
```

<span data-ttu-id="63ee1-144">結果として、同じフォルダーにコア ダンプが生成されます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-144">The result is a core dump located in the same folder.</span></span>

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a><span data-ttu-id="63ee1-145">失敗したプロセスを再起動する</span><span class="sxs-lookup"><span data-stu-id="63ee1-145">Restart the failed process</span></span>

<span data-ttu-id="63ee1-146">ダンプが収集されると、失敗したプロセスを診断するのに十分な情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-146">Once the dump is collected, you should have sufficient information to diagnose the failed process.</span></span> <span data-ttu-id="63ee1-147">失敗したプロセスが運用サーバーで実行されている場合は、今が、そのプロセスを再起動して短期的な修復を行うのに最適なタイミングです。</span><span class="sxs-lookup"><span data-stu-id="63ee1-147">If the failed process is running on a production server, now it's the ideal time for short-term remediation by restarting the process.</span></span>

<span data-ttu-id="63ee1-148">このチュートリアルでは、[サンプル デバッグ ターゲット](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/)を終了したので、閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-148">In this tutorial, you're now done with the [Sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) and you can close it.</span></span> <span data-ttu-id="63ee1-149">サーバーを起動したターミナルに移動して、`Control-C` を押します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-149">Navigate to the terminal that started the server and press `Control-C`.</span></span>

### <a name="analyze-the-core-dump"></a><span data-ttu-id="63ee1-150">コア ダンプを分析する</span><span class="sxs-lookup"><span data-stu-id="63ee1-150">Analyze the core dump</span></span>

<span data-ttu-id="63ee1-151">コア ダンプが生成されたので、[dotnet-dump](dotnet-dump.md) ツールを使用してダンプを分析します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-151">Now that you have a core dump generated, use the [dotnet-dump)](dotnet-dump.md) tool to analyze the dump:</span></span>

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

<span data-ttu-id="63ee1-152">ここで、`core_20190430_185145` は、分析するコア ダンプの名前です。</span><span class="sxs-lookup"><span data-stu-id="63ee1-152">Where `core_20190430_185145` is the name of the core dump you want to analyze.</span></span>

> [!NOTE]
> <span data-ttu-id="63ee1-153">*libdl.so* が見つからないことを示すエラーが表示された場合は、*libc6-dev* パッケージのインストールが必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63ee1-153">If you see an error complaining that *libdl.so* cannot be found, you may have to install the *libc6-dev* package.</span></span> <span data-ttu-id="63ee1-154">詳細については、「[Linux における .NET Core の前提条件](../linux-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63ee1-154">For more information, see [Prerequisites for .NET Core on Linux](../linux-prerequisites.md).</span></span>

<span data-ttu-id="63ee1-155">SOS コマンドを入力できるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-155">You'll be presented with a prompt where you can enter SOS commands.</span></span> <span data-ttu-id="63ee1-156">一般的に、最初に調べる必要があるのは、マネージド ヒープの全体的な状態です。</span><span class="sxs-lookup"><span data-stu-id="63ee1-156">Commonly, the first thing you want to look at is the overall state of the managed heap:</span></span>

```console
> dumpheap -stat

Statistics:
              MT    Count    TotalSize Class Name
...
00007f6c1eeefba8      576        59904 System.Reflection.RuntimeMethodInfo
00007f6c1dc021c8     1749        95696 System.SByte[]
00000000008c9db0     3847       116080      Free
00007f6c1e784a18      175       128640 System.Char[]
00007f6c1dbf5510      217       133504 System.Object[]
00007f6c1dc014c0      467       416464 System.Byte[]
00007f6c21625038        6      4063376 testwebapi.Controllers.Customer[]
00007f6c20a67498   200000      4800000 testwebapi.Controllers.Customer
00007f6c1dc00f90   206770     19494060 System.String
Total 428516 objects
```

<span data-ttu-id="63ee1-157">ここで、ほとんどのオブジェクトが `String` または `Customer` オブジェクトであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="63ee1-157">Here you can see that most objects are either `String` or `Customer` objects.</span></span>

<span data-ttu-id="63ee1-158">メソッド テーブル (MT) を指定して `dumpheap` コマンドを再び使用すると、すべての `String` インスタンスの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-158">You can use the `dumpheap` command again with the method table (MT) to get a list of all the `String` instances:</span></span>

```console
> dumpheap -mt 00007faddaa50f90

         Address               MT     Size
...
00007f6ad09421f8 00007faddaa50f90       94
...
00007f6ad0965b20 00007f6c1dc00f90       80
00007f6ad0965c10 00007f6c1dc00f90       80
00007f6ad0965d00 00007f6c1dc00f90       80
00007f6ad0965df0 00007f6c1dc00f90       80
00007f6ad0965ee0 00007f6c1dc00f90       80

Statistics:
              MT    Count    TotalSize Class Name
00007f6c1dc00f90   206770     19494060 System.String
Total 206770 objects
```

<span data-ttu-id="63ee1-159">次に、`System.String` インスタンスで `gcroot` コマンドを使用して、このオブジェクトがルート指定されている方法と理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-159">You can now use the `gcroot` command on a `System.String` instance to see how and why the object is rooted.</span></span> <span data-ttu-id="63ee1-160">このコマンドは 30 MB のヒープで数分かかるため、しばらくお待ちください。</span><span class="sxs-lookup"><span data-stu-id="63ee1-160">Be patient because this command takes several minutes with a 30-MB heap:</span></span>

```console
> gcroot -all 00007f6ad09421f8

Thread 3f68:
    00007F6795BB58A0 00007F6C1D7D0745 System.Diagnostics.Tracing.CounterGroup.PollForValues() [/_/src/System.Private.CoreLib/shared/System/Diagnostics/Tracing/CounterGroup.cs @ 260]
        rbx:  (interior)
            ->  00007F6BDFFFF038 System.Object[]
            ->  00007F69D0033570 testwebapi.Controllers.Processor
            ->  00007F69D0033588 testwebapi.Controllers.CustomerCache
            ->  00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
            ->  00007F6C000148A0 testwebapi.Controllers.Customer[]
            ->  00007F6AD0942258 testwebapi.Controllers.Customer
            ->  00007F6AD09421F8 System.String

HandleTable:
    00007F6C98BB15F8 (pinned handle)
    -> 00007F6BDFFFF038 System.Object[]
    -> 00007F69D0033570 testwebapi.Controllers.Processor
    -> 00007F69D0033588 testwebapi.Controllers.CustomerCache
    -> 00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
    -> 00007F6C000148A0 testwebapi.Controllers.Customer[]
    -> 00007F6AD0942258 testwebapi.Controllers.Customer
    -> 00007F6AD09421F8 System.String

Found 2 roots.
```

<span data-ttu-id="63ee1-161">`String` が `Customer` オブジェクトによって直接保持され、`CustomerCache` オブジェクトによって間接的に保持されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="63ee1-161">You can see that the `String` is directly held by the `Customer` object and indirectly held by a `CustomerCache` object.</span></span>

<span data-ttu-id="63ee1-162">オブジェクトのダンプを続けて、ほとんどの `String` オブジェクトが同様のパターンに従っていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-162">You can continue dumping out objects to see that most `String` objects follow a similar pattern.</span></span> <span data-ttu-id="63ee1-163">この時点で、コードの根本原因を特定するのに十分な情報が調査によって提供されています。</span><span class="sxs-lookup"><span data-stu-id="63ee1-163">At this point, the investigation provided sufficient information to identify the root cause in your code.</span></span>

<span data-ttu-id="63ee1-164">この一般的な手順では、主要なメモリ リークの原因を特定できます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-164">This general procedure allows you to identify the source of major memory leaks.</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="63ee1-165">リソースをクリーンアップする</span><span class="sxs-lookup"><span data-stu-id="63ee1-165">Clean up resources</span></span>

<span data-ttu-id="63ee1-166">このチュートリアルでは、サンプル Web サーバーを開始しました。</span><span class="sxs-lookup"><span data-stu-id="63ee1-166">In this tutorial, you started a sample web server.</span></span> <span data-ttu-id="63ee1-167">このサーバーは、「[失敗したプロセスを再起動する](#restart-the-failed-process)」セクションの説明に従ってシャットダウンされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ee1-167">This server should have been shut down as explained in the [Restart the failed process](#restart-the-failed-process) section.</span></span>

<span data-ttu-id="63ee1-168">また、作成されたダンプ ファイルを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-168">You can also delete the dump file that was created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="63ee1-169">次の手順</span><span class="sxs-lookup"><span data-stu-id="63ee1-169">Next steps</span></span>

<span data-ttu-id="63ee1-170">これでこのチュートリアルは完了です。</span><span class="sxs-lookup"><span data-stu-id="63ee1-170">Congratulations on completing this tutorial.</span></span>

<span data-ttu-id="63ee1-171">引き続き診断チュートリアルを公開します。</span><span class="sxs-lookup"><span data-stu-id="63ee1-171">We're still publishing more diagnostic tutorials.</span></span> <span data-ttu-id="63ee1-172">ドラフト バージョンは、[dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial) リポジトリで読むことができます。</span><span class="sxs-lookup"><span data-stu-id="63ee1-172">You can read the draft versions on the [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial) repository.</span></span>

<span data-ttu-id="63ee1-173">このチュートリアルでは、主要な .NET 診断ツールの基本について説明しました。</span><span class="sxs-lookup"><span data-stu-id="63ee1-173">This tutorial covered the basics of key .NET diagnostic tools.</span></span> <span data-ttu-id="63ee1-174">高度な使用方法については、次の参照ドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63ee1-174">For advanced usage, see the following reference documentation:</span></span>

* <span data-ttu-id="63ee1-175">プロセスを一覧表示するための [dotnet-trace](dotnet-trace.md)。</span><span class="sxs-lookup"><span data-stu-id="63ee1-175">[dotnet-trace](dotnet-trace.md) to list processes.</span></span>
* <span data-ttu-id="63ee1-176">マネージド メモリ使用量を確認するための [dotnet-counters](dotnet-counters.md)。</span><span class="sxs-lookup"><span data-stu-id="63ee1-176">[dotnet-counters](dotnet-counters.md) to check managed memory usage.</span></span>
* <span data-ttu-id="63ee1-177">ダンプ ファイルを収集して分析するための [dotnet-dump](dotnet-dump.md)。</span><span class="sxs-lookup"><span data-stu-id="63ee1-177">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file.</span></span>
