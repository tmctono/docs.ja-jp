---
title: dotnet-dump - .NET Core
description: dotnet-dump コマンドライン ツールのインストールおよび使用。
ms.date: 10/14/2019
ms.openlocfilehash: 3c0e28d4efc96ae53ec7dfae243725ab400e6b8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76737673"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="68117-103">ダンプの収集と分析のユーティリティ (`dotnet-dump`)</span><span class="sxs-lookup"><span data-stu-id="68117-103">Dump collection and analysis utility (`dotnet-dump`)</span></span>

<span data-ttu-id="68117-104">**この記事の対象:** ✔️ .NET Core 3.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="68117-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="68117-105">macOS では、`dotnet-dump` はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="68117-105">`dotnet-dump` isn't supported on macOS.</span></span>

## <a name="installing-dotnet-dump"></a><span data-ttu-id="68117-106">`dotnet-dump` をインストールする</span><span class="sxs-lookup"><span data-stu-id="68117-106">Installing `dotnet-dump`</span></span>

<span data-ttu-id="68117-107">`dotnet-dump` [NuGet パッケージ](https://www.nuget.org/packages/dotnet-dump)の最新のリリース バージョンをインストールするには、次のように [dotnet tool install](../tools/dotnet-tool-install.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="68117-107">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-dump
```

## <a name="synopsis"></a><span data-ttu-id="68117-108">構文</span><span class="sxs-lookup"><span data-stu-id="68117-108">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="68117-109">説明</span><span class="sxs-lookup"><span data-stu-id="68117-109">Description</span></span>

<span data-ttu-id="68117-110">`dotnet-dump` グローバル ツールを使用すると、Linux の `lldb` などの任意のネイティブ デバッガーを使用せずに、Windows と Linux のダンプを収集して分析できます。</span><span class="sxs-lookup"><span data-stu-id="68117-110">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="68117-111">このツールは、`lldb` が完全に動作しない Alpine Linux などのプラットフォームで重要です。</span><span class="sxs-lookup"><span data-stu-id="68117-111">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="68117-112">`dotnet-dump` ツールでは、SOS コマンドを実行してクラッシュとガベージ コレクター (GC) を分析できますが、これはネイティブのデバッガーではないため、ネイティブ スタック フレームの表示などの操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="68117-112">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="68117-113">オプション</span><span class="sxs-lookup"><span data-stu-id="68117-113">Options</span></span>

- **`--version`**

  <span data-ttu-id="68117-114">dotnet-counters ユーティリティのバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-114">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="68117-115">コマンド ライン ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-115">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="68117-116">コマンド</span><span class="sxs-lookup"><span data-stu-id="68117-116">Commands</span></span>

| <span data-ttu-id="68117-117">コマンド</span><span class="sxs-lookup"><span data-stu-id="68117-117">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="68117-118">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="68117-118">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="68117-119">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="68117-119">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="68117-120">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="68117-120">dotnet-dump collect</span></span>

<span data-ttu-id="68117-121">プロセスからダンプをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="68117-121">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="68117-122">構文</span><span class="sxs-lookup"><span data-stu-id="68117-122">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="68117-123">オプション</span><span class="sxs-lookup"><span data-stu-id="68117-123">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="68117-124">コマンド ライン ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-124">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="68117-125">メモリ ダンプを収集するプロセスの ID 番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="68117-125">Specifies the process ID number to collect a memory dump from.</span></span>

- **`--type <Heap|Mini>`**

  <span data-ttu-id="68117-126">プロセスから収集する情報の種類を決定する、ダンプの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="68117-126">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="68117-127">次の 2 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="68117-127">There are two types:</span></span>

  - <span data-ttu-id="68117-128">`Heap`: モジュールの一覧、スレッドの一覧、すべてのスタック、例外情報、ハンドル情報、およびマップされたイメージを除くすべてのメモリを含む、大規模で比較的包括的なダンプです。</span><span class="sxs-lookup"><span data-stu-id="68117-128">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="68117-129">`Mini`: モジュールの一覧、スレッドの一覧、例外情報、およびすべてのスタックを含む小さいダンプです。</span><span class="sxs-lookup"><span data-stu-id="68117-129">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="68117-130">指定しない場合の既定は、`Heap` です。</span><span class="sxs-lookup"><span data-stu-id="68117-130">If not specified, `Heap` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="68117-131">収集したダンプを書き込む完全なパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="68117-131">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="68117-132">指定していない場合は、次になります。</span><span class="sxs-lookup"><span data-stu-id="68117-132">If not specified:</span></span>

  - <span data-ttu-id="68117-133">Windows での既定は、 *.\dump_YYYYMMDD_HHMMSS.dmp* です。</span><span class="sxs-lookup"><span data-stu-id="68117-133">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="68117-134">Linux での既定は、 *./core_YYYYMMDD_HHMMSS* です。</span><span class="sxs-lookup"><span data-stu-id="68117-134">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="68117-135">YYYYMMDD は、年/月/日で、HHMMSS は時間/分/秒です。</span><span class="sxs-lookup"><span data-stu-id="68117-135">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="68117-136">ダンプの収集の診断ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="68117-136">Enables dump collection diagnostic logging.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="68117-137">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="68117-137">dotnet-dump analyze</span></span>

<span data-ttu-id="68117-138">ダンプを検索する対話型シェルを開始します。</span><span class="sxs-lookup"><span data-stu-id="68117-138">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="68117-139">このシェルでは、さまざまな [SOS コマンド](#analyze-sos-commands)を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="68117-139">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="68117-140">構文</span><span class="sxs-lookup"><span data-stu-id="68117-140">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="68117-141">引数</span><span class="sxs-lookup"><span data-stu-id="68117-141">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="68117-142">分析のためにファイルをダンプするパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="68117-142">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="68117-143">オプション</span><span class="sxs-lookup"><span data-stu-id="68117-143">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="68117-144">起動時にシェルで実行する[コマンド](#analyze-sos-commands)を指定します。</span><span class="sxs-lookup"><span data-stu-id="68117-144">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="68117-145">SOS コマンドを分析する</span><span class="sxs-lookup"><span data-stu-id="68117-145">Analyze SOS commands</span></span>

| <span data-ttu-id="68117-146">コマンド</span><span class="sxs-lookup"><span data-stu-id="68117-146">Command</span></span>                             | <span data-ttu-id="68117-147">関数</span><span class="sxs-lookup"><span data-stu-id="68117-147">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="68117-148">使用可能なコマンドをすべて表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-148">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="68117-149">指定したコマンドを表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-149">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="68117-150">対話モードを終了します。</span><span class="sxs-lookup"><span data-stu-id="68117-150">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="68117-151">マネージド コードのみのスタック トレースを提供します。</span><span class="sxs-lookup"><span data-stu-id="68117-151">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="68117-152">実行中のマネージド スレッドを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-152">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="68117-153">ガベージ コレクトされたヒープ上の非同期状態のマシンに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-153">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="68117-154">アセンブリに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-154">Displays details about an assembly.</span></span>                                                           |
| `dumpclass <arguments>`             | <span data-ttu-id="68117-155">指定したアドレスにある EE クラスの構造体に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-155">Displays information about a EE class structure at the specified address.</span></span>                     |
| `dumpdelegate <arguments>`          | <span data-ttu-id="68117-156">デリゲートに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-156">Displays information about a delegate.</span></span>                                                        |
| `dumpdomain <arguments>`            | <span data-ttu-id="68117-157">すべての AppDomain と、そのドメイン内のすべてのアセンブリに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-157">Displays information all the AppDomains and all assemblies within the domains.</span></span>                |
| `dumpheap <arguments>`              | <span data-ttu-id="68117-158">ガベージ コレクトされたヒープと、オブジェクトの収集統計に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-158">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="68117-159">マネージド メソッドに関連付けられている Microsoft Intermediate Language (MSIL) を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-159">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="68117-160">メモリ内ストレス ログの内容を、指定したファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="68117-160">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="68117-161">指定したアドレスにある MethodDesc 構造体に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-161">Displays information about a MethodDesc structure at the specified address.</span></span>                   |
| `dumpmodule <arguments>`            | <span data-ttu-id="68117-162">指定したアドレスにある EE モジュール構造体に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-162">Displays information about a EE module structure at the specified address.</span></span>                    |
| `dumpmt <arguments>`                | <span data-ttu-id="68117-163">指定したアドレスにあるメソッド テーブルに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-163">Displays information about a method table at the specified address.</span></span>                           |
| `dumpobj <arguments>`               | <span data-ttu-id="68117-164">指定したアドレスにあるオブジェクトに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-164">Displays info about an object at the specified address.</span></span>                                       |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="68117-165">現在のスタックの範囲内で見つかったすべてのマネージド オブジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-165">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="68117-166">内部のランタイム データ構造体によって消費されたプロセス メモリに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-166">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="68117-167">完了の目的で登録されているすべてのオブジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-167">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="68117-168">指定したアドレスにあるオブジェクトへの参照 (またはルート) に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-168">Displays info about references (or roots) to an object at the specified address.</span></span>              |
| `gcwhere <arguments>`               | <span data-ttu-id="68117-169">渡された引数の GC ヒープ内の場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-169">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="68117-170">指定したアドレスにある JIT コード内の MethodDesc 構造体に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-170">Displays the MethodDesc structure at the specified address in JIT code.</span></span>                       |
| `histclear <arguments>`             | <span data-ttu-id="68117-171">`hist*` コマンドのファミリによって使用されているすべてのリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="68117-171">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="68117-172">デバッグ対象に保存されているストレス ログから SOS 構造体を初期化します。</span><span class="sxs-lookup"><span data-stu-id="68117-172">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="68117-173">`<arguments>` に関連するガベージ コレクションのストレス ログの再配置を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-173">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="68117-174">指定したアドレスにあるオブジェクトを参照するすべてのログ エントリを表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-174">Displays all the log entries that reference an object at the specified address.</span></span>               |
| `histroot <arguments>`              | <span data-ttu-id="68117-175">指定したルートの上位変換と再配置の両方に関係する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-175">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="68117-176">プロセス内のネイティブ モジュールを表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-176">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="68117-177">`<argument>` の MethodTable 構造体と EEClass 構造体を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-177">Displays the MethodTable structure and EEClass structure for the `<argument>`.</span></span>                |
| `pe|printexception <arguments>`     | <span data-ttu-id="68117-178">アドレス `<argument>` で Exception クラスから派生したすべてのオブジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-178">Displays any object derived from the Exception class at the address `<argument>`.</span></span>             |
| `setsymbolserver <arguments>`       | <span data-ttu-id="68117-179">シンボル サーバーのサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="68117-179">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="68117-180">SyncBlock の所有者の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-180">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="68117-181">SOS コマンドの現在のスレッド ID を設定するか表示します。</span><span class="sxs-lookup"><span data-stu-id="68117-181">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

## <a name="using-dotnet-dump"></a><span data-ttu-id="68117-182">`dotnet-dump` を使用する</span><span class="sxs-lookup"><span data-stu-id="68117-182">Using `dotnet-dump`</span></span>

<span data-ttu-id="68117-183">まずはダンプを収集します。</span><span class="sxs-lookup"><span data-stu-id="68117-183">The first step is to collect a dump.</span></span> <span data-ttu-id="68117-184">コア ダンプを既に生成している場合、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="68117-184">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="68117-185">コア ダンプは、オペレーティング システムまたは .NET Core ランタイムに組み込まれているそれぞれの[ダンプ生成機能](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md)で作成できます。</span><span class="sxs-lookup"><span data-stu-id="68117-185">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="68117-186">ここで、次のように `analyze` コマンドを使用して、コア ダンプを分析します。</span><span class="sxs-lookup"><span data-stu-id="68117-186">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="68117-187">この操作により、次のようなコマンドを受け取る対話型セッションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="68117-187">This action brings up an interactive session that accepts commands like:</span></span>

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

<span data-ttu-id="68117-188">アプリを強制終了させた未処理の例外を表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="68117-188">To see an unhandled exception that killed your app:</span></span>

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a><span data-ttu-id="68117-189">Docker 用の特別な手順</span><span class="sxs-lookup"><span data-stu-id="68117-189">Special instructions for Docker</span></span>

<span data-ttu-id="68117-190">ダンプの収集を Docker で実行している場合、`SYS_PTRACE` 機能 (`--cap-add=SYS_PTRACE` または `--privileged`) が必要です。</span><span class="sxs-lookup"><span data-stu-id="68117-190">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="68117-191">Microsoft .NET Core SDK Linux Docker イメージでは、一部の `dotnet-dump` コマンドで次の例外がスローされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="68117-191">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="68117-192">未処理の例外:System.DllNotFoundException:共有ライブラリ 'libdl.so' またはその依存関係の 1 つを読み込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="68117-192">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="68117-193">"libc6-dev" パッケージをインストールすると、この問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="68117-193">To work around this problem, install the "libc6-dev" package.</span></span>
