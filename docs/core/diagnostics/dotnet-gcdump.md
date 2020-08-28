---
title: dotnet-gcdump - .NET Core
description: dotnet-gcdump コマンドライン ツールのインストールおよび使用。
ms.date: 07/26/2020
ms.openlocfilehash: a7b19f4d7487677b975621e7267a17894dae2e3a
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656652"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="d3c9e-103">ヒープ分析ツール (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="d3c9e-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="d3c9e-104">**この記事の対象:** ✔️ .NET Core 3.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="d3c9e-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install-dotnet-gcdump"></a><span data-ttu-id="d3c9e-105">dotnet-gcdump のインストール</span><span class="sxs-lookup"><span data-stu-id="d3c9e-105">Install dotnet-gcdump</span></span>

<span data-ttu-id="d3c9e-106">`dotnet-gcdump` [NuGet パッケージ](https://www.nuget.org/packages/dotnet-gcdump)の最新のリリース バージョンをインストールするには、次のように [dotnet tool install](../tools/dotnet-tool-install.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-106">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a><span data-ttu-id="d3c9e-107">構文</span><span class="sxs-lookup"><span data-stu-id="d3c9e-107">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="d3c9e-108">説明</span><span class="sxs-lookup"><span data-stu-id="d3c9e-108">Description</span></span>

<span data-ttu-id="d3c9e-109">`dotnet-gcdump` グローバル ツールは、ライブ .NET プロセスの GC (ガベージ コレクター) ダンプを収集する手段です。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-109">The `dotnet-gcdump` global tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span> <span data-ttu-id="d3c9e-110">これには Windows の ETW に代わるクロス プラットフォームである EventPipe テクノロジが使用されています。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-110">It uses the EventPipe technology, which is a cross-platform alternative to ETW on Windows.</span></span> <span data-ttu-id="d3c9e-111">GC ダンプを作成するには、ターゲット プロセスで GC をトリガーし、特殊なイベントを有効にし、イベント ストリームからオブジェクト ルートのグラフを再生成します。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-111">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="d3c9e-112">このプロセスにより、プロセスの実行中のオーバーヘッドを最小限に抑えながら GC ダンプを収集できます。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-112">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="d3c9e-113">このようなダンプは、いくつかのシナリオで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-113">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="d3c9e-114">複数の時点でヒープ上にあるオブジェクト数を比較する。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-114">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="d3c9e-115">オブジェクトのルートを分析する ("この種類に対する参照がまだ残っているものはあるか" などの質問に回答する場合)。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-115">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="d3c9e-116">ヒープ上のオブジェクト数に関する一般的な統計情報を収集する。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-116">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="d3c9e-117">dotnet-gcdump からキャプチャされた GC ダンプを表示する</span><span class="sxs-lookup"><span data-stu-id="d3c9e-117">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="d3c9e-118">Windows では、分析のために [PerfView](https://github.com/microsoft/perfview) で、または Visual Studio で `.gcdump` ファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-118">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="d3c9e-119">現在、Windows 以外のプラットフォームで `.gcdump` を開く方法はありません。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-119">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="d3c9e-120">複数の `.gcdump` を収集し、それらを Visual Studio で同時に開いて、比較を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-120">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="d3c9e-121">Options</span><span class="sxs-lookup"><span data-stu-id="d3c9e-121">Options</span></span>

- **`--version`**

  <span data-ttu-id="d3c9e-122">`dotnet-gcdump` ユーティリティのバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-122">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d3c9e-123">コマンド ライン ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-123">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="d3c9e-124">現在実行中のプロセスから GC ダンプを収集します。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-124">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d3c9e-125">構文</span><span class="sxs-lookup"><span data-stu-id="d3c9e-125">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="d3c9e-126">オプション</span><span class="sxs-lookup"><span data-stu-id="d3c9e-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d3c9e-127">コマンド ライン ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-127">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="d3c9e-128">GC ダンプを収集するプロセス ID。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-128">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="d3c9e-129">収集された GC ダンプが書き込まれるパス。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-129">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="d3c9e-130">既定値は *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump* です。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-130">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="d3c9e-131">GC ダンプの収集時にログを出力します。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-131">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="d3c9e-132">この秒数より長くかかる場合は、GC ダンプの収集をあきらめてください。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-132">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="d3c9e-133">既定値は 30 です。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-133">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="d3c9e-134">GC ダンプを収集するプロセスの名前。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-134">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="d3c9e-135">GC ダンプを収集できる dotnet プロセスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-135">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d3c9e-136">概要</span><span class="sxs-lookup"><span data-stu-id="d3c9e-136">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="d3c9e-137">以前に生成された GC ダンプまたは実行中のプロセスからレポートを生成し、`stdout` に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-137">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d3c9e-138">構文</span><span class="sxs-lookup"><span data-stu-id="d3c9e-138">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="d3c9e-139">オプション</span><span class="sxs-lookup"><span data-stu-id="d3c9e-139">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d3c9e-140">コマンド ライン ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-140">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="d3c9e-141">GC ダンプを収集するプロセス ID。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-141">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="d3c9e-142">生成するレポートの種類。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-142">The type of report to generate.</span></span> <span data-ttu-id="d3c9e-143">使用可能なオプション: heapstat (既定値)。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-143">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="d3c9e-144">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d3c9e-144">Troubleshoot</span></span>

- <span data-ttu-id="d3c9e-145">gcdump に型情報はありません。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-145">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="d3c9e-146">.NET Core 3.1 より前のバージョンでは、EventPipe を使って呼び出されたときに、gcdump 間で型キャッシュがクリアされない問題がありました。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-146">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="d3c9e-147">これにより、型情報を判別するために必要なイベントが 2 番目以降の gcdump に対して送信されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-147">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="d3c9e-148">これは .NET Core 3.1-preview2 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-148">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="d3c9e-149">COM 型と静的な型は GC ダンプに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-149">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="d3c9e-150">.NET Core 3.1-preview2 より前のバージョンでは、EventPipe を介して GC ダンプが呼び出されたときに静的な型と COM 型が送信されない問題がありました。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-150">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="d3c9e-151">これは .NET Core 3.1-preview2 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="d3c9e-151">This has been fixed in .NET Core 3.1-preview2.</span></span>
