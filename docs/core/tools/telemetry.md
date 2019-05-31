---
title: .NET Core SDK 製品利用統計情報
description: 利用情報を収集して分析する .NET Core SDK の製品利用統計情報機能と収集されるデータについて、およびこの機能を無効にする方法を説明します。
author: richlander
ms.date: 06/20/2018
ms.custom: seodec18
ms.openlocfilehash: 82410863c81faa95edfb120c95ec6bc186ed1328
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751679"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="55631-103">.NET Core SDK 製品利用統計情報</span><span class="sxs-lookup"><span data-stu-id="55631-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="55631-104">[.NET Core SDK](index.md) には、利用情報を収集する[製品利用統計情報機能](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)があります。</span><span class="sxs-lookup"><span data-stu-id="55631-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) that collects usage information.</span></span> <span data-ttu-id="55631-105">このツールがどのように利用されているかを .NET Team が理解することが重要です。それにより、ツールを改善できます。</span><span class="sxs-lookup"><span data-stu-id="55631-105">It's important that the .NET Team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="55631-106">詳細については、「[What we've learned from .NET Core SDK Telemetry](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/)」 (.NET Core SDK 製品利用統計情報からわかったこと) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55631-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="55631-107">収集されたデータは匿名で、[Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/) の下で、Microsoft とコミュニティの両者が利用するために集計された形で公開されます。</span><span class="sxs-lookup"><span data-stu-id="55631-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="55631-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="55631-108">Scope</span></span>

<span data-ttu-id="55631-109">`dotnet` コマンドは、アプリと .NET Core CLI の両方の起動に使用されます。</span><span class="sxs-lookup"><span data-stu-id="55631-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="55631-110">`dotnet` コマンド自体は製品利用統計情報を収集しません。</span><span class="sxs-lookup"><span data-stu-id="55631-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="55631-111">`dotnet` コマンドで実行される .NET Core CLI コマンドが製品利用統計情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="55631-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="55631-112">コマンドを添付せずに `dotnet` コマンドそのものを使うと、製品利用統計情報は*有効になりません*。</span><span class="sxs-lookup"><span data-stu-id="55631-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="55631-113">次のような [.NET Core CLI コマンド](index.md)を使用すると、製品利用統計情報が*有効になります*。</span><span class="sxs-lookup"><span data-stu-id="55631-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="55631-114">オプトアウトする方法</span><span class="sxs-lookup"><span data-stu-id="55631-114">How to opt out</span></span>

<span data-ttu-id="55631-115">.NET Core SDK の製品利用統計情報機能は既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="55631-115">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="55631-116">`DOTNET_CLI_TELEMETRY_OPTOUT` 環境変数を `1` または `true` に設定して、製品利用統計情報の機能をオプトアウトします。</span><span class="sxs-lookup"><span data-stu-id="55631-116">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="55631-117">データ ポイント</span><span class="sxs-lookup"><span data-stu-id="55631-117">Data points</span></span>

<span data-ttu-id="55631-118">この機能は次のデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="55631-118">The feature collects the following data:</span></span>

- <span data-ttu-id="55631-119">呼び出しのタイムスタンプ&#8224;</span><span class="sxs-lookup"><span data-stu-id="55631-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="55631-120">呼び出されたコマンド ("build" など)&#8224;</span><span class="sxs-lookup"><span data-stu-id="55631-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="55631-121">地理的な場所を決定するために使用する 3 つのオクテットの IP アドレス&#8224;</span><span class="sxs-lookup"><span data-stu-id="55631-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="55631-122">コマンドの `ExitCode`</span><span class="sxs-lookup"><span data-stu-id="55631-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="55631-123">(テスト プロジェクトの) テスト ランナー</span><span class="sxs-lookup"><span data-stu-id="55631-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="55631-124">オペレーティング システムとバージョン&#8224;</span><span class="sxs-lookup"><span data-stu-id="55631-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="55631-125">ランタイム ノードにランタイム ID が存在するかどうか</span><span class="sxs-lookup"><span data-stu-id="55631-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="55631-126">.NET Core SDK バージョン&#8224;</span><span class="sxs-lookup"><span data-stu-id="55631-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="55631-127">&#8224; このメトリックは公開されています。</span><span class="sxs-lookup"><span data-stu-id="55631-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="55631-128">.NET Core 2.0 SDK 以降、新しいデータ ポイントが収集されます。</span><span class="sxs-lookup"><span data-stu-id="55631-128">Starting with .NET Core 2.0 SDK, new data points are collected:</span></span>

- <span data-ttu-id="55631-129">`dotnet` コマンドの引数とオプション: (任意の文字列ではなく) 既知の引数とオプションのみが収集されます。</span><span class="sxs-lookup"><span data-stu-id="55631-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="55631-130">SDK がコンテナーで実行されているかどうか。</span><span class="sxs-lookup"><span data-stu-id="55631-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="55631-131">ターゲット フレームワーク。</span><span class="sxs-lookup"><span data-stu-id="55631-131">Target frameworks.</span></span>
- <span data-ttu-id="55631-132">ハッシュされた MAC アドレス: 暗号化の面で (SHA256) 匿名であり、マシンの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="55631-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="55631-133">このメトリックは公開されていません。</span><span class="sxs-lookup"><span data-stu-id="55631-133">This metric isn't published.</span></span>
- <span data-ttu-id="55631-134">ハッシュされた現在の作業ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="55631-134">Hashed current working directory.</span></span>

<span data-ttu-id="55631-135">この機能では、ユーザー名やメール アドレスなどの個人データは収集されません。</span><span class="sxs-lookup"><span data-stu-id="55631-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="55631-136">コードはスキャンされず、名前、リポジトリ、作成者などのプロジェクト レベルの機密データは抽出されません。</span><span class="sxs-lookup"><span data-stu-id="55631-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="55631-137">データは [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) テクノロジを使用して Microsoft サーバーに安全に送信され、制限されたアクセスの下で保持され、厳格なセキュリティ コントロールの下で安全な [Azure Storage](https://azure.microsoft.com/services/storage/) システムから公開されます。</span><span class="sxs-lookup"><span data-stu-id="55631-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="55631-138">.NET チームは、ツールで構築しているものではなく、ツールがどのように使われ、問題なく機能しているかどうかを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="55631-138">The .NET team wants to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="55631-139">利用統計情報で機密情報が収集されているのではないか、データがセキュリティ上問題がある、不適切な方法で処理されているのではないかという疑いがある場合は、調査のために [dotnet/cli](https://github.com/dotnet/cli/issues) リポジトリで問題を提起してください。</span><span class="sxs-lookup"><span data-stu-id="55631-139">If you suspect that the telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="55631-140">公開データ</span><span class="sxs-lookup"><span data-stu-id="55631-140">Published data</span></span>

<span data-ttu-id="55631-141">公開データは四半期ごとに利用可能で、「[.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)」 (.NET core SDK の使用状況データ) に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="55631-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="55631-142">データ ファイルの列は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="55631-142">The columns of a data file are:</span></span>

- <span data-ttu-id="55631-143">Timestamp</span><span class="sxs-lookup"><span data-stu-id="55631-143">Timestamp</span></span>
- <span data-ttu-id="55631-144">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="55631-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="55631-145">コマンド</span><span class="sxs-lookup"><span data-stu-id="55631-145">Command</span></span>
- <span data-ttu-id="55631-146">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="55631-146">Geography&#8225;</span></span>
- <span data-ttu-id="55631-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="55631-147">OSFamily</span></span>
- <span data-ttu-id="55631-148">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="55631-148">RuntimeID</span></span>
- <span data-ttu-id="55631-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="55631-149">OSVersion</span></span>
- <span data-ttu-id="55631-150">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="55631-150">SDKVersion</span></span>

<span data-ttu-id="55631-151">&#8224; *Occurrences* 列には、その行のメトリックに対するコマンドの使用回数の、その日の合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55631-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span>

<span data-ttu-id="55631-152">&#8225; 通常、*Geography* 列には、国の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55631-152">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="55631-153">場合によっては、調査担当者が南極や不正な場所データを使用して .NET Core を使用していることが原因で、この列に南極大陸が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="55631-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="55631-154">例</span><span class="sxs-lookup"><span data-stu-id="55631-154">Example</span></span>

| <span data-ttu-id="55631-155">Timestamp</span><span class="sxs-lookup"><span data-stu-id="55631-155">Timestamp</span></span>      | <span data-ttu-id="55631-156">Occurrences</span><span class="sxs-lookup"><span data-stu-id="55631-156">Occurrences</span></span> | <span data-ttu-id="55631-157">コマンド</span><span class="sxs-lookup"><span data-stu-id="55631-157">Command</span></span> | <span data-ttu-id="55631-158">Geography</span><span class="sxs-lookup"><span data-stu-id="55631-158">Geography</span></span> | <span data-ttu-id="55631-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="55631-159">OSFamily</span></span> | <span data-ttu-id="55631-160">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="55631-160">RuntimeID</span></span>     | <span data-ttu-id="55631-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="55631-161">OSVersion</span></span> | <span data-ttu-id="55631-162">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="55631-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="55631-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="55631-163">4/16/2017 0:00</span></span> | <span data-ttu-id="55631-164">8</span><span class="sxs-lookup"><span data-stu-id="55631-164">8</span></span>           | <span data-ttu-id="55631-165">実行</span><span class="sxs-lookup"><span data-stu-id="55631-165">run</span></span>     | <span data-ttu-id="55631-166">Uganda</span><span class="sxs-lookup"><span data-stu-id="55631-166">Uganda</span></span>    | <span data-ttu-id="55631-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="55631-167">Darwin</span></span>   | <span data-ttu-id="55631-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="55631-168">osx.10.12-x64</span></span> | <span data-ttu-id="55631-169">10.12</span><span class="sxs-lookup"><span data-stu-id="55631-169">10.12</span></span>     | <span data-ttu-id="55631-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="55631-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="55631-171">データセット</span><span class="sxs-lookup"><span data-stu-id="55631-171">Datasets</span></span>

- [<span data-ttu-id="55631-172">2016 - Q3</span><span class="sxs-lookup"><span data-stu-id="55631-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)
- [<span data-ttu-id="55631-173">2016 - Q4</span><span class="sxs-lookup"><span data-stu-id="55631-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)
- [<span data-ttu-id="55631-174">2017 - Q1</span><span class="sxs-lookup"><span data-stu-id="55631-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)
- [<span data-ttu-id="55631-175">2017 - Q2</span><span class="sxs-lookup"><span data-stu-id="55631-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)
- [<span data-ttu-id="55631-176">2017 - Q3</span><span class="sxs-lookup"><span data-stu-id="55631-176">2017 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q3.tsv)
- [<span data-ttu-id="55631-177">2017 - Q4</span><span class="sxs-lookup"><span data-stu-id="55631-177">2017 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q4.tsv)

<span data-ttu-id="55631-178">追加のデータセットは、標準の URL 形式を使用してポストされます。</span><span class="sxs-lookup"><span data-stu-id="55631-178">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="55631-179">`<YEAR>` を年で置き換え、`<QUARTER>` を四半期に置き換えます (`1`、`2`、`3`、 または `4` を使用)。</span><span class="sxs-lookup"><span data-stu-id="55631-179">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="55631-180">ファイルはタブ区切り値 (*TSV*) 形式です。</span><span class="sxs-lookup"><span data-stu-id="55631-180">The files are in tab-separated values (*TSV*) format.</span></span>

`https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv`

## <a name="license"></a><span data-ttu-id="55631-181">ライセンス</span><span class="sxs-lookup"><span data-stu-id="55631-181">License</span></span>

<span data-ttu-id="55631-182">Microsoft による .NET Core の配信は、[マイクロソフト ソフトウェア ライセンス条項:Mirosoft .NET ライブラリ](https://aka.ms/dotnet-core-eula)を利用して、ライセンス供与されます。</span><span class="sxs-lookup"><span data-stu-id="55631-182">The Microsoft distribution of .NET Core is licensed with the [Microsoft Software License Terms: Mirosoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="55631-183">データの収集と処理について詳しくは、タイトルに「データ」と付くセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55631-183">For details on data collection and processing, see the section entitled "Data."</span></span>

<span data-ttu-id="55631-184">[.NET NuGet パッケージ](https://www.nuget.org/profiles/dotnetframework)は同じライセンスを使用しますが、製品利用統計情報を有効にしません (「[スコープ](#scope)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="55631-184">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

## <a name="disclosure"></a><span data-ttu-id="55631-185">開示</span><span class="sxs-lookup"><span data-stu-id="55631-185">Disclosure</span></span>

<span data-ttu-id="55631-186">いずれかの [.NET Core CLI コマンド](index.md) (`dotnet restore` など) をはじめて実行するときに、.NET Core SDK では次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55631-186">The .NET Core SDK displays the following text when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet restore`).</span></span> <span data-ttu-id="55631-187">テキストは、実行している SDK のバージョンによって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="55631-187">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="55631-188">この "最初の実行" の際に、Microsoft がデータ回収に関して通知する方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="55631-188">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core: https://aka.ms/dotnet-docs
Use 'dotnet --help' to see available commands or visit: https://aka.ms/dotnet-cli-docs

Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience.
The data is anonymous and doesn't include command-line arguments.
The data is collected by Microsoft and shared with the community.
You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="see-also"></a><span data-ttu-id="55631-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="55631-189">See also</span></span>

- [<span data-ttu-id="55631-190">.NET Core SDK 製品利用統計情報からわかったこと</span><span class="sxs-lookup"><span data-stu-id="55631-190">What we've learned from .NET Core SDK Telemetry</span></span>](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/)
- [<span data-ttu-id="55631-191">製品利用統計情報の参照のソース (dotnet/cli リポジトリ)</span><span class="sxs-lookup"><span data-stu-id="55631-191">Telemetry reference source (dotnet/cli repo)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
- [<span data-ttu-id="55631-192">.NET core SDK の使用状況データ</span><span class="sxs-lookup"><span data-stu-id="55631-192">.NET Core SDK Usage Data</span></span>](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
