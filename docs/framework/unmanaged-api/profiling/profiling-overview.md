---
title: プロファイリングの概要
ms.date: 03/30/2017
helpviewer_keywords:
- managed code, profiling API support
- unmanaged code, combining with managed code in profiling
- notification threads [.NET Framework profiling]
- unmanaged code, profiling
- profiling API [.NET Framework], and COM
- profiling API [.NET Framework], unmanaged code profiling
- profilers, writing
- profiling API [.NET Framework], call stacks
- code profilers, writing
- profiling API [.NET Framework], security considerations
- profiling API [.NET Framework], managed code support
- common language runtime, profiling
- profiling API [.NET Framework], notification threads
- call stacks [.NET Framework profiling]
- profiling API [.NET Framework], stack depth
- common language runtime, writing a profiler
- profiling API [.NET Framework], information retrieval interfaces
- shadow stacks [.NET Framework profiling]
- COM, using in the profiling API
- stack snapshots [.NET Framework profiling]
- profiling API [.NET Framework], supported features
- profiling API [.NET Framework], overview
- security, profiling API considerations
- stack depth [.NET Framework profiling]
ms.assetid: 864c2344-71dc-46f9-96b2-ed59fb6427a8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6dbf36cec1bcd2ec1e96d57a889ddd9d9baef269
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663887"
---
# <a name="profiling-overview"></a><span data-ttu-id="370eb-102">プロファイリングの概要</span><span class="sxs-lookup"><span data-stu-id="370eb-102">Profiling Overview</span></span>

<a name="top"></a> <span data-ttu-id="370eb-103">プロファイラーは、別のアプリケーションの実行を監視するツールです。</span><span class="sxs-lookup"><span data-stu-id="370eb-103">A profiler is a tool that monitors the execution of another application.</span></span> <span data-ttu-id="370eb-104">共通言語ランタイム (CLR: Common Language Runtime) プロファイラーは、プロファイル API を使用して CLR とのメッセージの送受信を行う関数で構成されるダイナミック リンク ライブラリ (DLL: Dynamic Link Library) です。</span><span class="sxs-lookup"><span data-stu-id="370eb-104">A common language runtime (CLR) profiler is a dynamic link library (DLL) that consists of functions that receive messages from, and send messages to, the CLR by using the profiling API.</span></span> <span data-ttu-id="370eb-105">プロファイラー DLL は、実行時に CLR によって読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="370eb-105">The profiler DLL is loaded by the CLR at run time.</span></span>

<span data-ttu-id="370eb-106">従来のプロファイリング ツールは、アプリケーションの実行を測定することに重点を置いていました。</span><span class="sxs-lookup"><span data-stu-id="370eb-106">Traditional profiling tools focus on measuring the execution of the application.</span></span> <span data-ttu-id="370eb-107">その主な役割は、各関数の実行にかかる時間やアプリケーションのメモリ使用状況を一定期間にわたって測定することでした。</span><span class="sxs-lookup"><span data-stu-id="370eb-107">That is, they measure the time that is spent in each function or the memory usage of the application over time.</span></span> <span data-ttu-id="370eb-108">プロファイル API は、コード カバレッジ ユーティリティや高度なデバッグ支援ツールなど、より幅広い診断ツールを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="370eb-108">The profiling API targets a broader class of diagnostic tools such as code-coverage utilities and even advanced debugging aids.</span></span> <span data-ttu-id="370eb-109">これらの用途には、いずれも診断的な性質があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-109">These uses are all diagnostic in nature.</span></span> <span data-ttu-id="370eb-110">プロファイル API は、アプリケーションの実行を測定するだけでなく、監視も行います。</span><span class="sxs-lookup"><span data-stu-id="370eb-110">The profiling API not only measures but also monitors the execution of an application.</span></span> <span data-ttu-id="370eb-111">そのため、プロファイル API をアプリケーション自体が使用することは避ける必要があります。また、アプリケーションの実行がプロファイラーに依存したり、プロファイラーの影響を受けたりしないようにする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="370eb-111">For this reason, the profiling API should never be used by the application itself, and the application’s execution should not depend on (or be affected by) the profiler.</span></span>

<span data-ttu-id="370eb-112">CLR アプリケーションのプロファイリングには、通常のコンパイル済みマシン語コードのプロファイリングよりも多くのサポートが必要です。</span><span class="sxs-lookup"><span data-stu-id="370eb-112">Profiling a CLR application requires more support than profiling conventionally compiled machine code.</span></span> <span data-ttu-id="370eb-113">その理由は、CLR には、アプリケーション ドメイン、ガベージ コレクション、マネージド例外処理、コードの Just-In-Time (JIT) コンパイル (Microsoft Intermediate Language (MSIL) コードからネイティブ マシン語コードへの変換) などの概念や同様の機能が採り入れられているためです。</span><span class="sxs-lookup"><span data-stu-id="370eb-113">This is because the CLR introduces concepts such as application domains, garbage collection, managed exception handling, just-in-time (JIT) compilation of code (converting Microsoft intermediate language, or MSIL, code into native machine code), and similar features.</span></span> <span data-ttu-id="370eb-114">通常のプロファイリング機構では、これらの機能に関する有益な情報を見つけたり、提供したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="370eb-114">Conventional profiling mechanisms cannot identify or provide useful information about these features.</span></span> <span data-ttu-id="370eb-115">プロファイル API は、CLR およびプロファイリングされたアプリケーションのパフォーマンスに大きな影響を与えることなく、この欠落した情報を効率的に提供します。</span><span class="sxs-lookup"><span data-stu-id="370eb-115">The profiling API provides this missing information efficiently, with minimal effect on the performance of the CLR and the profiled application.</span></span>

<span data-ttu-id="370eb-116">実行時に行われる JIT コンパイルは、プロファイリングを行ううえで絶好のタイミングとなります。</span><span class="sxs-lookup"><span data-stu-id="370eb-116">JIT compilation at run time provides good opportunities for profiling.</span></span> <span data-ttu-id="370eb-117">プロファイル API を使用すると、プロファイラーは、ルーチンの JIT コンパイルが行われる前に、ルーチンのメモリ内 MSIL コード ストリームを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="370eb-117">The profiling API enables a profiler to change the in-memory MSIL code stream for a routine before it is JIT-compiled.</span></span> <span data-ttu-id="370eb-118">この方法により、プロファイラーは、さらに詳細な調査が必要な特定のルーチンに動的にインストルメンテーション コードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="370eb-118">In this manner, the profiler can dynamically add instrumentation code to particular routines that need deeper investigation.</span></span> <span data-ttu-id="370eb-119">この方法は従来のシナリオでも可能ですが、プロファイル API を使用する CLR の方が、実装はずっと簡単です。</span><span class="sxs-lookup"><span data-stu-id="370eb-119">Although this approach is possible in conventional scenarios, it is much easier to implement for the CLR by using the profiling API.</span></span>

<span data-ttu-id="370eb-120">この概要は、次のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="370eb-120">This overview consists of the following sections:</span></span>

- [<span data-ttu-id="370eb-121">プロファイル API</span><span class="sxs-lookup"><span data-stu-id="370eb-121">The Profiling API</span></span>](#profiling_api)

- [<span data-ttu-id="370eb-122">サポートされる機能</span><span class="sxs-lookup"><span data-stu-id="370eb-122">Supported Features</span></span>](#support)

- [<span data-ttu-id="370eb-123">通知スレッド</span><span class="sxs-lookup"><span data-stu-id="370eb-123">Notification Threads</span></span>](#notification_threads)

- [<span data-ttu-id="370eb-124">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="370eb-124">Security</span></span>](#security)

- [<span data-ttu-id="370eb-125">マネージし、アンマネージ コード Profiler でのコードの結合</span><span class="sxs-lookup"><span data-stu-id="370eb-125">Combining Managed and Unmanaged Code in a Code Profiler</span></span>](#combining_managed_unmanaged)

- [<span data-ttu-id="370eb-126">アンマネージ コードのプロファイリング</span><span class="sxs-lookup"><span data-stu-id="370eb-126">Profiling Unmanaged Code</span></span>](#unmanaged)

- [<span data-ttu-id="370eb-127">COM の使用</span><span class="sxs-lookup"><span data-stu-id="370eb-127">Using COM</span></span>](#com)

- [<span data-ttu-id="370eb-128">呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="370eb-128">Call stacks</span></span>](#call_stacks)

- [<span data-ttu-id="370eb-129">コールバックとスタックの深さ</span><span class="sxs-lookup"><span data-stu-id="370eb-129">Callbacks and Stack Depth</span></span>](#callbacks)

- [<span data-ttu-id="370eb-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="370eb-130">Related Topics</span></span>](#related_topics)

<a name="profiling_api"></a>

## <a name="the-profiling-api"></a><span data-ttu-id="370eb-131">プロファイル API</span><span class="sxs-lookup"><span data-stu-id="370eb-131">The Profiling API</span></span>

<span data-ttu-id="370eb-132">通常、プロファイル API が書き込みに使用、*コード プロファイラー*、マネージ アプリケーションの実行を監視するプログラムであります。</span><span class="sxs-lookup"><span data-stu-id="370eb-132">Typically, the profiling API is used to write a *code profiler*, which is a program that monitors the execution of a managed application.</span></span>

<span data-ttu-id="370eb-133">プロファイル API は、プロファイラー DLL によって使用されます。プロファイラー DLL は、プロファイリング対象アプリケーションと同じプロセスに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="370eb-133">The profiling API is used by a profiler DLL, which is loaded into the same process as the application that is being profiled.</span></span> <span data-ttu-id="370eb-134">プロファイラー DLL は、コールバック インターフェイスを実装 ([ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) .NET Framework version 1.0 および 1.1 で[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)バージョン 2.0 以降)。</span><span class="sxs-lookup"><span data-stu-id="370eb-134">The profiler DLL implements a callback interface ([ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) in the .NET Framework version 1.0 and 1.1, [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) in version 2.0 and later).</span></span> <span data-ttu-id="370eb-135">CLR は、このインターフェイス内のメソッドを呼び出して、プロファイリングされたプロセスのイベントをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="370eb-135">The CLR calls the methods in that interface to notify the profiler of events in the profiled process.</span></span> <span data-ttu-id="370eb-136">プロファイラーにコールバックするで、ランタイム内のメソッドを使用して、 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)と[ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)インターフェイス、プロファイリングされたアプリケーションの状態に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="370eb-136">The profiler can call back into the runtime by using the methods in the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) and [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) interfaces to obtain information about the state of the profiled application.</span></span>

> [!NOTE]
> <span data-ttu-id="370eb-137">プロファイリングされたアプリケーションと同じプロセスで実行するのは、プロファイラー ソリューションのデータ収集の部分だけにしてください。</span><span class="sxs-lookup"><span data-stu-id="370eb-137">Only the data-gathering part of the profiler solution should be running in the same process as the profiled application.</span></span> <span data-ttu-id="370eb-138">ユーザー インターフェイスとデータ分析は、すべて別のプロセスで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-138">All user interface and data analysis should be performed in a separate process.</span></span>

<span data-ttu-id="370eb-139">次の図は、プロファイラー DLL がプロファイリング対象アプリケーションおよび CLR とやり取りする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="370eb-139">The following illustration shows how the profiler DLL interacts with the application that is being profiled and the CLR.</span></span>

![プロファイリング アーキテクチャを示すスクリーン ショット。](./media/profiling-overview/profiling-architecture.png)

### <a name="the-notification-interfaces"></a><span data-ttu-id="370eb-141">通知インターフェイス</span><span class="sxs-lookup"><span data-stu-id="370eb-141">The Notification Interfaces</span></span>

<span data-ttu-id="370eb-142">[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)と[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)通知インターフェイスと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="370eb-142">[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) can be considered notification interfaces.</span></span> <span data-ttu-id="370eb-143">これらのインターフェイスで構成されているメソッドのなど[ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)、 [ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)、および[JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="370eb-143">These interfaces consist of methods such as [ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md), [ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md), and [JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md).</span></span> <span data-ttu-id="370eb-144">クラスのロードまたはアンロード、関数のコンパイルなどを行うたびに、プロファイラーの `ICorProfilerCallback` インターフェイスまたは `ICorProfilerCallback2` インターフェイスの対応するメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="370eb-144">Each time the CLR loads or unloads a class, compiles a function, and so on, it calls the corresponding method in the profiler's `ICorProfilerCallback` or `ICorProfilerCallback2` interface.</span></span>

<span data-ttu-id="370eb-145">たとえば、プロファイラーでは、2 つの通知関数を使用してコードのパフォーマンスを測定でした。[FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)と[FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="370eb-145">For example, a profiler could measure code performance through two notification functions: [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) and [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md).</span></span> <span data-ttu-id="370eb-146">この場合は、各通知のタイムスタンプを記録し、結果を累積して、アプリケーションの実行時に CPU またはウォール クロック時間を最も多く使用した関数を示す一覧を出力します。</span><span class="sxs-lookup"><span data-stu-id="370eb-146">It just time-stamps each notification, accumulates results, and outputs a list that indicates which functions consumed the most CPU or wall-clock time during the execution of the application.</span></span>

### <a name="the-information-retrieval-interfaces"></a><span data-ttu-id="370eb-147">情報取得インターフェイス</span><span class="sxs-lookup"><span data-stu-id="370eb-147">The Information Retrieval Interfaces</span></span>

<span data-ttu-id="370eb-148">プロファイルに関連するその他のメイン インターフェイスは[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)と[ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="370eb-148">The other main interfaces involved in profiling are [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) and [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md).</span></span> <span data-ttu-id="370eb-149">プロファイラーは、分析に役立つ追加情報を取得する必要がある場合に、これらのインターフェイスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="370eb-149">The profiler calls these interfaces as required to obtain more information to help its analysis.</span></span> <span data-ttu-id="370eb-150">たとえば、CLR を呼び出すたびに、 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)関数、関数の識別子が指定されます。</span><span class="sxs-lookup"><span data-stu-id="370eb-150">For example, whenever the CLR calls the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function, it supplies a function identifier.</span></span> <span data-ttu-id="370eb-151">プロファイラーは呼び出すことでその関数の詳細についてを取得することができます、 [icorprofilerinfo 2::getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)関数の親クラス、その名前、および具合を探索する方法。</span><span class="sxs-lookup"><span data-stu-id="370eb-151">The profiler can get more information about that function by calling the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method to discover the function's parent class, its name, and so on.</span></span>

[<span data-ttu-id="370eb-152">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="370eb-152">Back to top</span></span>](#top)

<a name="support"></a>

## <a name="supported-features"></a><span data-ttu-id="370eb-153">サポートされている機能</span><span class="sxs-lookup"><span data-stu-id="370eb-153">Supported Features</span></span>

<span data-ttu-id="370eb-154">プロファイル API は、共通言語ランタイムで発生するさまざまなイベントとアクションについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="370eb-154">The profiling API provides information about a variety of events and actions that occur in the common language runtime.</span></span> <span data-ttu-id="370eb-155">この情報を使用して、プロセスの内部動作を監視し、.NET Framework アプリケーションのパフォーマンスを分析できます。</span><span class="sxs-lookup"><span data-stu-id="370eb-155">You can use this information to monitor the inner workings of processes and to analyze the performance of your .NET Framework application.</span></span>

<span data-ttu-id="370eb-156">プロファイル API は、CLR で発生する以下のアクションとイベントについての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="370eb-156">The profiling API retrieves information about the following actions and events that occur in the CLR:</span></span>

- <span data-ttu-id="370eb-157">CLR のスタートアップ イベントとシャットダウン イベント。</span><span class="sxs-lookup"><span data-stu-id="370eb-157">CLR startup and shutdown events.</span></span>

- <span data-ttu-id="370eb-158">アプリケーション ドメインの作成イベントとシャットダウン イベント。</span><span class="sxs-lookup"><span data-stu-id="370eb-158">Application domain creation and shutdown events.</span></span>

- <span data-ttu-id="370eb-159">アセンブリの読み込みイベントとアンロード イベント。</span><span class="sxs-lookup"><span data-stu-id="370eb-159">Assembly loading and unloading events.</span></span>

- <span data-ttu-id="370eb-160">モジュールの読み込みイベントとアンロード イベント。</span><span class="sxs-lookup"><span data-stu-id="370eb-160">Module loading and unloading events.</span></span>

- <span data-ttu-id="370eb-161">COM vtable の作成イベントと破棄イベント。</span><span class="sxs-lookup"><span data-stu-id="370eb-161">COM vtable creation and destruction events.</span></span>

- <span data-ttu-id="370eb-162">Just-In-Time (JIT) コンパイル イベントとコード ピッチ イベント。</span><span class="sxs-lookup"><span data-stu-id="370eb-162">Just-in-time (JIT) compilation and code-pitching events.</span></span>

- <span data-ttu-id="370eb-163">クラスの読み込みイベントとアンロード イベント。</span><span class="sxs-lookup"><span data-stu-id="370eb-163">Class loading and unloading events.</span></span>

- <span data-ttu-id="370eb-164">スレッドの作成イベントと破棄イベント。</span><span class="sxs-lookup"><span data-stu-id="370eb-164">Thread creation and destruction events.</span></span>

- <span data-ttu-id="370eb-165">関数の開始イベントと終了イベント。</span><span class="sxs-lookup"><span data-stu-id="370eb-165">Function entry and exit events.</span></span>

- <span data-ttu-id="370eb-166">例外。</span><span class="sxs-lookup"><span data-stu-id="370eb-166">Exceptions.</span></span>

- <span data-ttu-id="370eb-167">マネージド コードとアンマネージド コードの実行の切り替え。</span><span class="sxs-lookup"><span data-stu-id="370eb-167">Transitions between managed and unmanaged code execution.</span></span>

- <span data-ttu-id="370eb-168">異なるランタイム コンテキスト間の切り替え。</span><span class="sxs-lookup"><span data-stu-id="370eb-168">Transitions between different runtime contexts.</span></span>

- <span data-ttu-id="370eb-169">ランタイムの中断に関する情報。</span><span class="sxs-lookup"><span data-stu-id="370eb-169">Information about runtime suspensions.</span></span>

- <span data-ttu-id="370eb-170">ランタイムのメモリ ヒープとガベージ コレクションのアクティビティに関する情報。</span><span class="sxs-lookup"><span data-stu-id="370eb-170">Information about the runtime memory heap and garbage collection activity.</span></span>

<span data-ttu-id="370eb-171">プロファイル API は、任意の (非マネージ) COM 互換言語から呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="370eb-171">The profiling API can be called from any (non-managed) COM-compatible language.</span></span>

<span data-ttu-id="370eb-172">API は、CPU とメモリの消費に関しては効率的です。</span><span class="sxs-lookup"><span data-stu-id="370eb-172">The API is efficient with regard to CPU and memory consumption.</span></span> <span data-ttu-id="370eb-173">プロファイルを実行しても、誤った結果をもたらすほどの大きい変化がプロファイリング対象のアプリケーションで発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="370eb-173">Profiling does not involve changes to the profiled application that are significant enough to cause misleading results.</span></span>

<span data-ttu-id="370eb-174">プロファイル API は、サンプリング プロファイラーと非サンプリング プロファイラーの両方に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="370eb-174">The profiling API is useful to both sampling and non-sampling profilers.</span></span> <span data-ttu-id="370eb-175">A*サンプリング プロファイラー*検査一定のクロック ティック単位でプロファイルと答えると、5 ミリ秒間隔。</span><span class="sxs-lookup"><span data-stu-id="370eb-175">A *sampling profiler* inspects the profile at regular clock ticks, say, at 5 milliseconds apart.</span></span> <span data-ttu-id="370eb-176">A*非サンプリング プロファイラー*イベントの原因になったスレッドで同期的にイベントが通知されます。</span><span class="sxs-lookup"><span data-stu-id="370eb-176">A *non-sampling profiler* is informed of an event synchronously with the thread that causes the event.</span></span>

### <a name="unsupported-functionality"></a><span data-ttu-id="370eb-177">サポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="370eb-177">Unsupported Functionality</span></span>

<span data-ttu-id="370eb-178">プロファイル API は、以下の機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="370eb-178">The profiling API does not support the following functionality:</span></span>

- <span data-ttu-id="370eb-179">従来の Win32 メソッドを使用してプロファイリングする必要があるアンマネージ コード。</span><span class="sxs-lookup"><span data-stu-id="370eb-179">Unmanaged code, which must be profiled using conventional Win32 methods.</span></span> <span data-ttu-id="370eb-180">ただし、CLR プロファイラーには、マネージド コードとアンマネージド コードの境界を判定するための遷移イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="370eb-180">However, the CLR profiler includes transition events to determine the boundaries between managed and unmanaged code.</span></span>

- <span data-ttu-id="370eb-181">アスペクト指向プログラミングなどの目的で自身のコードを変更する自動変更アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="370eb-181">Self-modifying applications that modify their own code for purposes such as aspect-oriented programming.</span></span>

- <span data-ttu-id="370eb-182">範囲チェック (プロファイル API がこの情報を提供しないため)。</span><span class="sxs-lookup"><span data-stu-id="370eb-182">Bounds checking, because the profiling API does not provide this information.</span></span> <span data-ttu-id="370eb-183">CLR には、すべてのマネージド コードの範囲チェックのための組み込みサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="370eb-183">The CLR provides intrinsic support for bounds checking of all managed code.</span></span>

- <span data-ttu-id="370eb-184">リモート プロファイル。次の理由によりサポートされません。</span><span class="sxs-lookup"><span data-stu-id="370eb-184">Remote profiling, which is not supported for the following reasons:</span></span>

  - <span data-ttu-id="370eb-185">リモート プロファイルは実行時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="370eb-185">Remote profiling extends execution time.</span></span> <span data-ttu-id="370eb-186">プロファイル インターフェイスを使用するときは、プロファイリングの結果が必要以上に影響を受けないように、実行時間を最小限にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-186">When you use the profiling interfaces, you must minimize execution time so that profiling results will not be unduly affected.</span></span> <span data-ttu-id="370eb-187">実行パフォーマンスを監視するときには、これが特に重要です。</span><span class="sxs-lookup"><span data-stu-id="370eb-187">This is especially true when execution performance is being monitored.</span></span> <span data-ttu-id="370eb-188">ただし、メモリの使用状況を監視するため、またはスタック フレームやオブジェクトなどについてのランタイム情報を取得するためにプロファイル インターフェイスを使用するときは、リモート プロファイルは制約になりません。</span><span class="sxs-lookup"><span data-stu-id="370eb-188">However, remote profiling is not a limitation when the profiling interfaces are used to monitor memory usage or to obtain run-time information about stack frames, objects, and so on.</span></span>

  - <span data-ttu-id="370eb-189">CLR コード プロファイラーは、プロファイリング対象のアプリケーションが実行しているローカル コンピューターのランタイムに、1 つ以上のコールバック インターフェイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-189">The CLR code profiler must register one or more callback interfaces with the runtime on the local computer on which the profiled application is running.</span></span> <span data-ttu-id="370eb-190">これにより、リモート コード プロファイラーの作成が制限されます。</span><span class="sxs-lookup"><span data-stu-id="370eb-190">This limits the ability to create a remote code profiler.</span></span>

- <span data-ttu-id="370eb-191">高可用性が必要な稼働環境でのプロファイル。</span><span class="sxs-lookup"><span data-stu-id="370eb-191">Profiling in production environments with high-availability requirements.</span></span> <span data-ttu-id="370eb-192">プロファイル API は、開発時の診断をサポートするために作成された API です。</span><span class="sxs-lookup"><span data-stu-id="370eb-192">The profiling API was created to support development-time diagnostics.</span></span> <span data-ttu-id="370eb-193">稼働環境をサポートするために必要な厳密なテストは実施されていません。</span><span class="sxs-lookup"><span data-stu-id="370eb-193">It has not undergone the rigorous testing required to support production environments.</span></span>

[<span data-ttu-id="370eb-194">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="370eb-194">Back to top</span></span>](#top)

<a name="notification_threads"></a>

## <a name="notification-threads"></a><span data-ttu-id="370eb-195">通知スレッド</span><span class="sxs-lookup"><span data-stu-id="370eb-195">Notification Threads</span></span>

<span data-ttu-id="370eb-196">通常は、イベントを生成するスレッドが通知も実行します。</span><span class="sxs-lookup"><span data-stu-id="370eb-196">In most cases, the thread that generates an event also executes notifications.</span></span> <span data-ttu-id="370eb-197">このような通知 (たとえば、 [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)と[FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md))、明示的なを指定する必要はありません`ThreadID`します。</span><span class="sxs-lookup"><span data-stu-id="370eb-197">Such notifications (for example, [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) and [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)) do not need to supply the explicit `ThreadID`.</span></span> <span data-ttu-id="370eb-198">また、プロファイラーでは、グローバル ストレージに分析ブロックのインデックスを作成するのではなく、影響を受けるスレッドの `ThreadID` を基に、スレッド ローカル ストレージを使用して分析ブロックを格納および更新する方法を採用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-198">Also, the profiler might decide to use thread-local storage to store and update its analysis blocks instead of indexing the analysis blocks in global storage, based on the `ThreadID` of the affected thread.</span></span>

<span data-ttu-id="370eb-199">これらのコールバックはシリアル化されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="370eb-199">Note that these callbacks are not serialized.</span></span> <span data-ttu-id="370eb-200">ユーザーは、スレッド セーフなデータ構造を作成すると共に、必要に応じてプロファイラー コードをロックして、複数のスレッドからの並行アクセスを防ぐことで、コードを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-200">Users must protect their code by creating thread-safe data structures and by locking the profiler code where necessary to prevent parallel access from multiple threads.</span></span> <span data-ttu-id="370eb-201">そのため、状況によっては、通常とは異なるシーケンスでコールバックを受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-201">Therefore, in certain cases you can receive an unusual sequence of callbacks.</span></span> <span data-ttu-id="370eb-202">たとえば、マネージド アプリケーションで、まったく同じコードを実行する 2 つのスレッドを生成するとします。</span><span class="sxs-lookup"><span data-stu-id="370eb-202">For example, assume that a managed application is spawning two threads that are executing identical code.</span></span> <span data-ttu-id="370eb-203">ここを受信することは、 [icorprofilercallback::jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)イベントを 1 つのスレッドからのいくつかの関数と`FunctionEnter`受信する前に、その他のスレッドからのコールバック、 [Icorprofilercallback::jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="370eb-203">In this case, it is possible to receive a [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) event for some function from one thread and a `FunctionEnter` callback from the other thread before receiving the [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) callback.</span></span> <span data-ttu-id="370eb-204">この場合、ユーザーは、まだ完全に Just-In-Time (JIT) コンパイルが行われていない可能性がある関数についての `FunctionEnter` コールバックを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="370eb-204">In this case, the user will receive a `FunctionEnter` callback for a function that may not have been fully just-in-time (JIT) compiled yet.</span></span>

[<span data-ttu-id="370eb-205">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="370eb-205">Back to top</span></span>](#top)

<a name="security"></a>

## <a name="security"></a><span data-ttu-id="370eb-206">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="370eb-206">Security</span></span>

<span data-ttu-id="370eb-207">プロファイラーの DLL は、共通言語ランタイムの実行エンジンの一部として動作するアンマネージ DLL です。</span><span class="sxs-lookup"><span data-stu-id="370eb-207">A profiler DLL is an unmanaged DLL that runs as part of the common language runtime execution engine.</span></span> <span data-ttu-id="370eb-208">そのため、プロファイラー DLL のコードは、マネージド コード アクセス セキュリティの制限を受けません。</span><span class="sxs-lookup"><span data-stu-id="370eb-208">As a result, the code in the profiler DLL is not subject to the restrictions of managed code access security.</span></span> <span data-ttu-id="370eb-209">プロファイラー DLL に対する唯一の制限は、プロファイリング対象のアプリケーションを実行しているユーザーに適用されるオペレーティング システムの制限です。</span><span class="sxs-lookup"><span data-stu-id="370eb-209">The only limitations on the profiler DLL are those imposed by the operating system on the user who is running the profiled application.</span></span>

<span data-ttu-id="370eb-210">プロファイラーを作成するときは、セキュリティ関連の問題が発生しないように、適切な予防措置を講じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-210">Profiler authors should take appropriate precautions to avoid security-related issues.</span></span> <span data-ttu-id="370eb-211">たとえば、インストール時には、プロファイラー DLL をアクセス制御リスト (ACL: Access Control List) に追加して、悪意のあるユーザーが DLL を変更できないようにします。</span><span class="sxs-lookup"><span data-stu-id="370eb-211">For example, during installation, a profiler DLL should be added to an access control list (ACL) so that a malicious user cannot modify it.</span></span>

[<span data-ttu-id="370eb-212">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="370eb-212">Back to top</span></span>](#top)

<a name="combining_managed_unmanaged"></a>

## <a name="combining-managed-and-unmanaged-code-in-a-code-profiler"></a><span data-ttu-id="370eb-213">コード プロファイラーでのマネージド コードとアンマネージド コードの結合</span><span class="sxs-lookup"><span data-stu-id="370eb-213">Combining Managed and Unmanaged Code in a Code Profiler</span></span>

<span data-ttu-id="370eb-214">プロファイラーが正しく記述されていないと、循環参照が発生し、予期しない動作が引き起こされることがあります。</span><span class="sxs-lookup"><span data-stu-id="370eb-214">An incorrectly written profiler can cause circular references to itself, resulting in unpredictable behavior.</span></span>

<span data-ttu-id="370eb-215">CLR プロファイル API をレビューすると、マネージド コンポーネントとアンマネージド コンポーネントの両方を使用してプロファイラーを作成し、COM 相互運用機能や間接呼び出しを通して互いを呼び出すことができるような印象を受けるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="370eb-215">A review of the CLR profiling API may create the impression that you can write a profiler that contains managed and unmanaged components that call each other through COM interop or indirect calls.</span></span>

<span data-ttu-id="370eb-216">これは設計上は可能ですが、プロファイル API はマネージド コンポーネントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="370eb-216">Although this is possible from a design perspective, the profiling API does not support managed components.</span></span> <span data-ttu-id="370eb-217">CLR プロファイラーは完全にアンマネージにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-217">A CLR profiler must be completely unmanaged.</span></span> <span data-ttu-id="370eb-218">CLR プロファイラーでマネージド コードとアンマネージド コードを組み合わせようとすると、アクセス違反、プログラム エラー、またはデッドロックが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-218">Attempts to combine managed and unmanaged code in a CLR profiler may cause access violations, program failure, or deadlocks.</span></span> <span data-ttu-id="370eb-219">プロファイラーのマネージド コンポーネントからアンマネージド コンポーネントに対してイベントが生成され、そのイベントでマネージド コンポーネントが再度呼び出されて、循環参照が発生することになります。</span><span class="sxs-lookup"><span data-stu-id="370eb-219">The managed components of the profiler will fire events back to their unmanaged components, which would subsequently call the managed components again, resulting in circular references.</span></span>

<span data-ttu-id="370eb-220">CLR プロファイラーがマネージド コードを安全に呼び出すことができる唯一の場所は、Microsoft Intermediate Language (MSIL) で表されたメソッドの本体です。</span><span class="sxs-lookup"><span data-stu-id="370eb-220">The only location where a CLR profiler can call managed code safely is in the Microsoft intermediate language (MSIL) body of a method.</span></span> <span data-ttu-id="370eb-221">MSIL 本体を変更するための推奨される方法は、JIT 再コンパイル メソッドを使用する、 [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="370eb-221">The recommended practice for modifying the MSIL body is to use the  JIT recompilation methods in the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span></span>

<span data-ttu-id="370eb-222">また、MSIL を変更するために古いインストルメンテーション メソッドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="370eb-222">It is also possible to use the older instrumentation methods to modify MSIL.</span></span> <span data-ttu-id="370eb-223">プロファイラーがメソッドと、JIT コンパイルの MSIL 本体にマネージ呼び出しを挿入できる関数の・ イン タイム (JIT) コンパイルが完了する前に (を参照してください、 [icorprofilerinfo::getilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)メソッド)。</span><span class="sxs-lookup"><span data-stu-id="370eb-223">Before the just-in-time (JIT) compilation of a function is completed, the profiler can insert managed calls in the MSIL body of a method and then JIT-compile it (see the [ICorProfilerInfo::GetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md) method).</span></span> <span data-ttu-id="370eb-224">この方法で、マネージド コードの選択的インストルメンテーションや、JIT に関する統計およびパフォーマンス データの収集を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="370eb-224">This technique can successfully be used for selective instrumentation of managed code, or to gather statistics and performance data about the JIT.</span></span>

<span data-ttu-id="370eb-225">または、コード プロファイラーを使用して、アンマネージド コードを呼び出すすべてのマネージド関数の MSIL 本体にネイティブ フックを挿入することもできます。</span><span class="sxs-lookup"><span data-stu-id="370eb-225">Alternatively, a code profiler can insert native hooks in the MSIL body of every managed function that calls into unmanaged code.</span></span> <span data-ttu-id="370eb-226">この方法は、インストルメンテーションやカバレッジに使用できます。</span><span class="sxs-lookup"><span data-stu-id="370eb-226">This technique can be used for instrumentation and coverage.</span></span> <span data-ttu-id="370eb-227">たとえば、コード プロファイラーで各 MSIL ブロックの後ろにインストルメンテーション フックを挿入すると、そのブロックが実行されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="370eb-227">For example, a code profiler could insert instrumentation hooks after every MSIL block to ensure that the block has been executed.</span></span> <span data-ttu-id="370eb-228">メソッドの MSIL 本体の変更には細心の注意が要求され、多くの要素を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-228">The modification of the MSIL body of a method is a very delicate operation, and there are many factors that should be taken into consideration.</span></span>

[<span data-ttu-id="370eb-229">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="370eb-229">Back to top</span></span>](#top)

<a name="unmanaged"></a>

## <a name="profiling-unmanaged-code"></a><span data-ttu-id="370eb-230">アンマネージ コードのプロファイリング</span><span class="sxs-lookup"><span data-stu-id="370eb-230">Profiling Unmanaged Code</span></span>

<span data-ttu-id="370eb-231">共通言語ランタイム (CLR: Common Language Runtime) には、アンマネージ コードのプロファイリングについて最小限のサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="370eb-231">The common language runtime (CLR) profiling API provides minimal support for profiling unmanaged code.</span></span> <span data-ttu-id="370eb-232">次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-232">The following functionality is provided:</span></span>

- <span data-ttu-id="370eb-233">スタック チェーンの列挙。</span><span class="sxs-lookup"><span data-stu-id="370eb-233">Enumeration of stack chains.</span></span> <span data-ttu-id="370eb-234">この機能を使用すると、コード プロファイラーはマネージド コードとアンマネージド コードの境界を特定できます。</span><span class="sxs-lookup"><span data-stu-id="370eb-234">This feature enables a code profiler to determine the boundary between managed code and unmanaged code.</span></span>

- <span data-ttu-id="370eb-235">スタック チェーンがマネージド コードまたはネイティブ コードに対応するかどうかの判定。</span><span class="sxs-lookup"><span data-stu-id="370eb-235">Determination whether a stack chain corresponds to managed code or native code.</span></span>

<span data-ttu-id="370eb-236">.NET Framework Versions 1.0 および 1.1 では、これらのメソッドは CLR デバッグ API のインプロセス サブセットを通して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="370eb-236">In the .NET Framework versions 1.0 and 1.1, these methods are available through the in-process subset of the CLR debugging API.</span></span> <span data-ttu-id="370eb-237">これらは CorDebug.idl ファイルに定義されています。</span><span class="sxs-lookup"><span data-stu-id="370eb-237">They are defined in the CorDebug.idl file.</span></span>

<span data-ttu-id="370eb-238">.NET Framework 2.0 以降では、使用、 [icorprofilerinfo 2::dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)この機能のためのメソッド。</span><span class="sxs-lookup"><span data-stu-id="370eb-238">In the .NET Framework 2.0 and later, you can use the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method for this functionality.</span></span>

[<span data-ttu-id="370eb-239">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="370eb-239">Back to top</span></span>](#top)

<a name="com"></a>

## <a name="using-com"></a><span data-ttu-id="370eb-240">COM の使用</span><span class="sxs-lookup"><span data-stu-id="370eb-240">Using COM</span></span>

<span data-ttu-id="370eb-241">プロファイリングのインターフェイスは COM インターフェイスとして定義されますが、共通言語ランタイム (CLR: Common Language Runtime) は、これらのインターフェイスを使用するための COM の初期化を行いません。</span><span class="sxs-lookup"><span data-stu-id="370eb-241">Although the profiling interfaces are defined as COM interfaces, the common language runtime (CLR) does not actually initialize COM to use these interfaces.</span></span> <span data-ttu-id="370eb-242">使用して、スレッド処理モデルを設定しなくてもすむようにするため、 [CoInitialize](/windows/desktop/api/objbase/nf-objbase-coinitialize)関数の前に、マネージ アプリケーションの目的のスレッド処理モデルを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="370eb-242">The reason is to avoid having to set the threading model by using the [CoInitialize](/windows/desktop/api/objbase/nf-objbase-coinitialize) function before the managed application has had a chance to specify its desired threading model.</span></span> <span data-ttu-id="370eb-243">同様に、プロファイラーでも、プロファイリング対象アプリケーションと互換性のないスレッド処理モデルが選択されてアプリケーション エラーが発生する可能性を避けるために、`CoInitialize` を呼び出さないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-243">Similarly, the profiler itself should not call `CoInitialize`, because it may pick a threading model that is incompatible with the application being profiled and may cause the application to fail.</span></span>

[<span data-ttu-id="370eb-244">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="370eb-244">Back to top</span></span>](#top)

<a name="call_stacks"></a>

## <a name="call-stacks"></a><span data-ttu-id="370eb-245">呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="370eb-245">Call Stacks</span></span>

<span data-ttu-id="370eb-246">プロファイル API には、呼び出し履歴を呼び出す 2 とおりの方法が用意されています。スタック スナップショットによる方法では呼び出し履歴を少ない頻度で収集でき、シャドウ スタックによる方法では呼び出し履歴を常時追跡します。</span><span class="sxs-lookup"><span data-stu-id="370eb-246">The profiling API provides two ways to obtain call stacks: a stack snapshot method, which enables sparse gathering of call stacks, and a shadow stack method, which tracks the call stack at every instant.</span></span>

### <a name="stack-snapshot"></a><span data-ttu-id="370eb-247">スタック スナップショット</span><span class="sxs-lookup"><span data-stu-id="370eb-247">Stack Snapshot</span></span>

<span data-ttu-id="370eb-248">スタック スナップショットは、ある特定の時点でのスレッドのスタックのトレースです。</span><span class="sxs-lookup"><span data-stu-id="370eb-248">A stack snapshot is a trace of the stack of a thread at an instant in time.</span></span> <span data-ttu-id="370eb-249">プロファイル API はスタックでのマネージド関数のトレースをサポートしますが、アンマネージド 関数のトレースはプロファイラー独自のスタック ウォーカーで処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-249">The profiling API supports the tracing of managed functions on the stack, but it leaves the tracing of unmanaged functions to the profiler's own stack walker.</span></span>

<span data-ttu-id="370eb-250">プロファイラーでマネージ スタックをプログラムする方法の詳細については、次を参照してください。、 [icorprofilerinfo 2::dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)このドキュメント セット内のメソッドと[、.NET Framework 2.0 における Profiler スタック ウォーク。基本、そしてその向こう](https://go.microsoft.com/fwlink/?LinkId=73638)します。</span><span class="sxs-lookup"><span data-stu-id="370eb-250">For more information about how to program the profiler to walk managed stacks, see the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method in this documentation set, and [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](https://go.microsoft.com/fwlink/?LinkId=73638).</span></span>

### <a name="shadow-stack"></a><span data-ttu-id="370eb-251">シャドウ スタック</span><span class="sxs-lookup"><span data-stu-id="370eb-251">Shadow Stack</span></span>

<span data-ttu-id="370eb-252">スナップショット方式を頻繁に使用すると、すぐにパフォーマンスの問題につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-252">Using the snapshot method too frequently can quickly create a performance issue.</span></span> <span data-ttu-id="370eb-253">使用して場合、プロファイラーで代わりに、シャドウ スタックを構築スタック トレースを頻繁に行う場合は、 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)、 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)、[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)例外コールバック。</span><span class="sxs-lookup"><span data-stu-id="370eb-253">If you want to take stack traces frequently, your profiler should instead build a shadow stack by using the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md), and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) exception callbacks.</span></span> <span data-ttu-id="370eb-254">シャドウ スタックは常に最新であり、スタック スナップショットが必要なときいつでも簡単にストレージにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="370eb-254">The shadow stack is always current and can quickly be copied to storage whenever a stack snapshot is needed.</span></span>

<span data-ttu-id="370eb-255">シャドウ スタックでは、関数の引数、戻り値、およびジェネリックなインスタンス化に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="370eb-255">A shadow stack may obtain function arguments, return values, and information about generic instantiations.</span></span> <span data-ttu-id="370eb-256">この情報は、シャドウ スタックを通してのみ使用でき、制御が関数に渡されたときに取得できます。</span><span class="sxs-lookup"><span data-stu-id="370eb-256">This information is available only through the shadow stack and may be obtained when control is handed to a function.</span></span> <span data-ttu-id="370eb-257">ただし、後から関数の実行中にこの情報を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="370eb-257">However, this information may not be available later during the run of the function.</span></span>

[<span data-ttu-id="370eb-258">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="370eb-258">Back to top</span></span>](#top)

<a name="callbacks"></a>

## <a name="callbacks-and-stack-depth"></a><span data-ttu-id="370eb-259">コールバックとスタックの深さ</span><span class="sxs-lookup"><span data-stu-id="370eb-259">Callbacks and Stack Depth</span></span>

<span data-ttu-id="370eb-260">プロファイラー コールバックはスタックが非常に制約された環境で発行される場合があり、プロファイラー コールバックでスタック オーバーフローが発生すると、プロセスが直ちに終了することになります。</span><span class="sxs-lookup"><span data-stu-id="370eb-260">Profiler callbacks may be issued in very stack-constrained circumstances, and a stack overflow in a profiler callback will lead to an immediate process exit.</span></span> <span data-ttu-id="370eb-261">プロファイラーは、コールバックへの応答で使用するスタックを可能な限り少なくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-261">A profiler should make sure to use as little stack as possible in response to callbacks.</span></span> <span data-ttu-id="370eb-262">スタック オーバーフローに対して耐性のあるプロセスでプロファイラーを使用する場合は、プロファイラー自体もスタック オーバーフローを発生させないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="370eb-262">If the profiler is intended for use against processes that are robust against stack overflow, the profiler itself should also avoid triggering stack overflow.</span></span>

[<span data-ttu-id="370eb-263">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="370eb-263">Back to top</span></span>](#top)

<a name="related_topics"></a>

## <a name="related-topics"></a><span data-ttu-id="370eb-264">関連トピック</span><span class="sxs-lookup"><span data-stu-id="370eb-264">Related Topics</span></span>

|<span data-ttu-id="370eb-265">タイトル</span><span class="sxs-lookup"><span data-stu-id="370eb-265">Title</span></span>|<span data-ttu-id="370eb-266">説明</span><span class="sxs-lookup"><span data-stu-id="370eb-266">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="370eb-267">プロファイル環境の設定</span><span class="sxs-lookup"><span data-stu-id="370eb-267">Setting Up a Profiling Environment</span></span>](../../../../docs/framework/unmanaged-api/profiling/setting-up-a-profiling-environment.md)|<span data-ttu-id="370eb-268">プロファイラーを初期化し、イベント通知を設定して、Windows サービスをプロファイリングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="370eb-268">Explains how to initialize a profiler, set event notifications, and profile a Windows Service.</span></span>|
|[<span data-ttu-id="370eb-269">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="370eb-269">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)|<span data-ttu-id="370eb-270">プロファイル API で使用されるアンマネージ インターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="370eb-270">Describes the unmanaged interfaces that the profiling API uses.</span></span>|
|[<span data-ttu-id="370eb-271">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="370eb-271">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)|<span data-ttu-id="370eb-272">プロファイル API で使用されるアンマネージ グローバル静的関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="370eb-272">Describes the unmanaged global static functions that the profiling API uses.</span></span>|
|[<span data-ttu-id="370eb-273">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="370eb-273">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)|<span data-ttu-id="370eb-274">プロファイル API で使用されるアンマネージ列挙体について説明します。</span><span class="sxs-lookup"><span data-stu-id="370eb-274">Describes the unmanaged enumerations that the profiling API uses.</span></span>|
|[<span data-ttu-id="370eb-275">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="370eb-275">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)|<span data-ttu-id="370eb-276">プロファイル API で使用されるアンマネージ構造体について説明します。</span><span class="sxs-lookup"><span data-stu-id="370eb-276">Describes the unmanaged structures that the profiling API uses.</span></span>|
