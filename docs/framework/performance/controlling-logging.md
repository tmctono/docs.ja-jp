---
title: .NET Framework のログ記録の制御
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29f6f844c3cdf2d43437aed7fc19492a37f9f8fc
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971564"
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="aa2e1-102">.NET Framework のログ記録の制御</span><span class="sxs-lookup"><span data-stu-id="aa2e1-102">Controlling .NET Framework Logging</span></span>

<span data-ttu-id="aa2e1-103">Windows イベント トレーシング (ETW: Event Tracing for Windows) を使用して共通言語ランタイム (CLR: Common Language Runtime) イベントを記録できます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-103">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="aa2e1-104">トレースの作成および表示には次のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-104">You can create and view traces by using the following tools:</span></span>

- <span data-ttu-id="aa2e1-105">Windows オペレーティング システムに含まれる [Logman](/windows-server/administration/windows-commands/logman) および [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) コマンド ライン ツール。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-105">The [Logman](/windows-server/administration/windows-commands/logman) and [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) command-line tools, which are included with the Windows operating system.</span></span>

- <span data-ttu-id="aa2e1-106">[Windows Performance Toolkit](/windows-hardware/test/wpt/) の [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) ツール。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-106">The [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools in the [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span></span> <span data-ttu-id="aa2e1-107">Xperf の詳細については、[Windows のパフォーマンスに関するブログ](https://go.microsoft.com/fwlink/?LinkId=179509)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-107">For more information about Xperf, see the [Windows Performance blog](https://go.microsoft.com/fwlink/?LinkId=179509).</span></span>

<span data-ttu-id="aa2e1-108">CLR イベントの情報をキャプチャするには、コンピューターに CLR プロバイダーがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-108">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="aa2e1-109">プロバイダーがインストールされているかどうかを確認するには、コマンド プロンプトで「`logman query providers`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-109">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="aa2e1-110">プロバイダーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-110">A list of providers is displayed.</span></span> <span data-ttu-id="aa2e1-111">その一覧に、次のような CLR プロバイダーのエントリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-111">This list should contain an entry for the CLR provider, as follows.</span></span>

```
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

<span data-ttu-id="aa2e1-112">一覧に CLR プロバイダーが含まれていない場合は、Windows Vista 以降のオペレーティング システムで Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil) コマンド ライン ツールを使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-112">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil) command-line tool.</span></span> <span data-ttu-id="aa2e1-113">管理者としてコマンド プロンプト ウィンドウを開き、</span><span class="sxs-lookup"><span data-stu-id="aa2e1-113">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="aa2e1-114">Prompt ディレクトリを .NET Framework 4 フォルダー (%WINDIR%\Microsoft.NET\Framework [64] \ v4.\<」に変更します。NET version > \)。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-114">Change the prompt directory to the .NET Framework 4 folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="aa2e1-115">このフォルダーに、CLR-ETW.man ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-115">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="aa2e1-116">コマンド プロンプトで次のコマンドを入力して CLR プロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-116">At the command prompt, type the following command to install the CLR provider:</span></span>

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a><span data-ttu-id="aa2e1-117">CLR ETW イベントのキャプチャ</span><span class="sxs-lookup"><span data-stu-id="aa2e1-117">Capturing CLR ETW Events</span></span>

<span data-ttu-id="aa2e1-118">コマンド ライン ツールの [Logman](/windows-server/administration/windows-commands/logman) および [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) を使用して ETW イベントをキャプチャできます。また、[Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) および [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) ツールを使用してトレース イベントをデコードできます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-118">You can use the [Logman](/windows-server/administration/windows-commands/logman) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) command-line tools to capture ETW events, and the [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools to decode the trace events.</span></span>

<span data-ttu-id="aa2e1-119">ログを有効にするには、次の 3 つの項目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-119">To turn on logging, a user must specify three things:</span></span>

- <span data-ttu-id="aa2e1-120">通信先のプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-120">The provider to communicate to.</span></span>

- <span data-ttu-id="aa2e1-121">キーワード セットを表す 64 ビットの数値。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-121">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="aa2e1-122">各キーワードは、プロバイダーが有効にできる一連のイベントを表します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-122">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="aa2e1-123">この数値は、有効にするキーワードの組み合わせを表します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-123">The number represents a combined set of keywords to turn on.</span></span>

- <span data-ttu-id="aa2e1-124">記録レベル (詳細度) を表す小さな数値。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-124">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="aa2e1-125">レベル 1 が最も簡易であり、レベル 5 が最も詳細になります。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-125">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="aa2e1-126">レベル 0 は既定値であり、プロバイダー固有であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-126">Level 0 is a default whose meaning is provider-specific.</span></span>

### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="aa2e1-127">Logman を使用して CLR ETW イベントをキャプチャするには</span><span class="sxs-lookup"><span data-stu-id="aa2e1-127">To capture CLR ETW events using Logman</span></span>

1. <span data-ttu-id="aa2e1-128">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-128">At the command prompt, type:</span></span>

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     <span data-ttu-id="aa2e1-129">それぞれの文字について以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-129">where:</span></span>

    - <span data-ttu-id="aa2e1-130">`-p` パラメーターはプロバイダーの GUID を識別します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-130">The `-p` parameter identifies the provider GUID.</span></span>

    - <span data-ttu-id="aa2e1-131">`0x1CCBD` は、発生するイベントのカテゴリを指定しています。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-131">`0x1CCBD` specifies the categories of events that will be raised.</span></span>

    - <span data-ttu-id="aa2e1-132">`0x5` は、ログ レベルを設定しています (この場合は詳細 (5))。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-132">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>

    - <span data-ttu-id="aa2e1-133">`-ets` パラメーターは、コマンドをイベント トレース セッションに送信するように指定します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-133">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>

    - <span data-ttu-id="aa2e1-134">`-ct perf` パラメーターは、`QueryPerformanceCounter` 関数を使用して各イベントのタイム スタンプを記録するように指定します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-134">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>

2. <span data-ttu-id="aa2e1-135">イベントの記録を停止するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-135">To stop logging the events, type:</span></span>

     `logman stop clrevents -ets`

     <span data-ttu-id="aa2e1-136">これにより、clrevents.etl という名前のバイナリ トレース ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-136">This command creates a binary trace file named clrevents.etl.</span></span>

### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="aa2e1-137">Xperf を使用して CLR ETW イベントをキャプチャするには</span><span class="sxs-lookup"><span data-stu-id="aa2e1-137">To capture CLR ETW events using Xperf</span></span>

1. <span data-ttu-id="aa2e1-138">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-138">At the command prompt, type:</span></span>

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     <span data-ttu-id="aa2e1-139">GUID には CLR ETW プロバイダーの GUID を指定します。`0x1CCBD:5` を指定すると、レベル 5 (詳細) 以下のすべての内容がトレースされます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-139">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>

2. <span data-ttu-id="aa2e1-140">トレースを停止するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-140">To stop tracing, type:</span></span>

     `Xperf -stop clr`

     <span data-ttu-id="aa2e1-141">これにより、clrevents.etl という名前のトレース ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-141">This command creates a trace file named clrevents.etl.</span></span>

## <a name="viewing-clr-etw-events"></a><span data-ttu-id="aa2e1-142">CLR ETW イベントの表示</span><span class="sxs-lookup"><span data-stu-id="aa2e1-142">Viewing CLR ETW Events</span></span>

<span data-ttu-id="aa2e1-143">CLR ETW イベントを表示するには、以下のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-143">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="aa2e1-144">イベントの詳細については、「[CLR ETW イベント](../../../docs/framework/performance/clr-etw-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-144">For a description of the events, see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md).</span></span>

### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="aa2e1-145">Tracerpt を使用して CLR ETW イベントを表示するには</span><span class="sxs-lookup"><span data-stu-id="aa2e1-145">To view CLR ETW events using Tracerpt</span></span>

- <span data-ttu-id="aa2e1-146">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-146">At the command prompt, type:</span></span>

     `tracerpt clrevents.etl`

     <span data-ttu-id="aa2e1-147">これにより、dumpfile.xml と summary.txt という 2 つのファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-147">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="aa2e1-148">dumpfile.xml ファイルはすべてのイベントの一覧で、summary.txt はイベントの概要です。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-148">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>

### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="aa2e1-149">Xperf を使用して CLR ETW イベントを表示するには</span><span class="sxs-lookup"><span data-stu-id="aa2e1-149">To view CLR ETW events using Xperf</span></span>

- <span data-ttu-id="aa2e1-150">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-150">At the command prompt, type:</span></span>

     `xperf clrevents.etl`

     <span data-ttu-id="aa2e1-151">Xperf ETL ファイル ビューアーが開きます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-151">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="aa2e1-152">このビューアーでは、CLR イベントは、 **[一般的なイベント]** ビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-152">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="aa2e1-153">種類別に分類されたイベントのデータ グリッドを表示するには、このビューで時間帯を選択し、マウスを右クリックして **[概要]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-153">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="aa2e1-154">.etl ファイルをコンマ区切り値ファイルに変換するには</span><span class="sxs-lookup"><span data-stu-id="aa2e1-154">To convert the .etl file to a comma-separated value file</span></span>

- <span data-ttu-id="aa2e1-155">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-155">At the command prompt, type:</span></span>

     `xperf -i clrevents.etl -f clrevents.csv`

     <span data-ttu-id="aa2e1-156">このコマンドを使用すると、XPerf によって、表示可能なコンマ区切り値 (CSV) ファイルとしてイベントがダンプされます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-156">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="aa2e1-157">イベントが異なればフィールドも異なるので、この CSV ファイルには、データの前に複数のヘッダー行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-157">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="aa2e1-158">すべての行の先頭のフィールドはイベントの種類を表します。このフィールドは、残りのフィールドを判別するために使用されるヘッダーを示します。</span><span class="sxs-lookup"><span data-stu-id="aa2e1-158">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa2e1-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa2e1-159">See also</span></span>

- [<span data-ttu-id="aa2e1-160">Windows パフォーマンス ツールキット</span><span class="sxs-lookup"><span data-stu-id="aa2e1-160">Windows Performance Toolkit</span></span>](/windows-hardware/test/wpt/)
- [<span data-ttu-id="aa2e1-161">共通言語ランタイムの ETW イベント</span><span class="sxs-lookup"><span data-stu-id="aa2e1-161">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
