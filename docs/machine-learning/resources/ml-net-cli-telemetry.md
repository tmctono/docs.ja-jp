---
title: ML.NET CLI によるテレメトリ収集
description: 分析のために使用状況の情報を収集する ML.NET CLI テレメトリ機能、収集されるデータ、機能を無効にする方法について説明します。 また、.NET の使用許諾契約と Microsoft GDPR 準拠に関する情報のリンクも紹介します。
ms.topic: conceptual
ms.date: 06/03/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 833ee2ae54cf3a52adaf070837a33e00267d25dc
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599840"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a><span data-ttu-id="884e1-104">ML.NET CLI によるテレメトリ収集</span><span class="sxs-lookup"><span data-stu-id="884e1-104">Telemetry collection by the ML.NET CLI</span></span>

<span data-ttu-id="884e1-105">[ML.NET CLI](https://aka.ms/mlnet-cli) には、Microsoft が利用するために集計している匿名の使用状況データを収集するテレメトリ機能があります。</span><span class="sxs-lookup"><span data-stu-id="884e1-105">The [ML.NET CLI](https://aka.ms/mlnet-cli) includes a telemetry feature that collects anonymous usage data that is aggregated for use by Microsoft.</span></span>

## <a name="how-microsoft-uses-the-data"></a><span data-ttu-id="884e1-106">Microsoft によるデータの使用方法</span><span class="sxs-lookup"><span data-stu-id="884e1-106">How Microsoft uses the data</span></span>

<span data-ttu-id="884e1-107">製品チームは、ツールの改善方法を理解するために ML.NET CLI のテレメトリ データを使用しています。</span><span class="sxs-lookup"><span data-stu-id="884e1-107">The product team uses ML.NET CLI telemetry data to help understand how to improve the tools.</span></span> <span data-ttu-id="884e1-108">たとえば、お客様が特定の機械学習タスクをあまり使用しない場合、製品チームはその理由を調査し、その結果を使用して機能開発の優先順位を決定します。</span><span class="sxs-lookup"><span data-stu-id="884e1-108">For example, if customers infrequently use a particular machine learning task, the product team investigates why and uses findings to prioritize feature development.</span></span> <span data-ttu-id="884e1-109">ML.NET CLI のテレメトリは、クラッシュやコードの異常などの問題のデバッグにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="884e1-109">ML.NET CLI telemetry also helps with debugging of issues such as crashes and code anomalies.</span></span>

<span data-ttu-id="884e1-110">製品チームはこの分析情報に感謝していますが、このデータを送信したくない方がいらっしゃることも理解しています。</span><span class="sxs-lookup"><span data-stu-id="884e1-110">While the product team appreciates this insight, we also know that not everyone wants to send this data.</span></span> [<span data-ttu-id="884e1-111">テレメトリを無効にする方法についてはこちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="884e1-111">Find out how to disable telemetry.</span></span>](#opt-out-of-data-collection)

## <a name="scope"></a><span data-ttu-id="884e1-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="884e1-112">Scope</span></span>

<span data-ttu-id="884e1-113">`mlnet` コマンドを実行すると、ML.NET CLI が起動しますが、このコマンド自体ではテレメトリが収集されません。</span><span class="sxs-lookup"><span data-stu-id="884e1-113">The `mlnet` command launches the ML.NET CLI, but the command itself doesn't collect telemetry.</span></span>

<span data-ttu-id="884e1-114">他のコマンドを添付せずに `mlnet` コマンドを実行すると、テレメトリは "*有効になりません*"。</span><span class="sxs-lookup"><span data-stu-id="884e1-114">Telemetry *isn't enabled* when you run the `mlnet` command with no other command attached.</span></span> <span data-ttu-id="884e1-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="884e1-115">For example:</span></span>

- `mlnet`
- `mlnet --help`

<span data-ttu-id="884e1-116">`mlnet classification` などの [ML.NET CLI コマンド](../reference/ml-net-cli-reference.md)を実行すると、テレメトリは "*有効です*"。</span><span class="sxs-lookup"><span data-stu-id="884e1-116">Telemetry *is enabled* when you run an [ML.NET CLI command](../reference/ml-net-cli-reference.md), such as `mlnet classification`.</span></span>

## <a name="opt-out-of-data-collection"></a><span data-ttu-id="884e1-117">データ収集のオプトアウト</span><span class="sxs-lookup"><span data-stu-id="884e1-117">Opt out of data collection</span></span>

<span data-ttu-id="884e1-118">ML.NET CLI のテレメトリ機能は既定で有効です。</span><span class="sxs-lookup"><span data-stu-id="884e1-118">The ML.NET CLI telemetry feature is enabled by default.</span></span>

<span data-ttu-id="884e1-119">`MLDOTNET_CLI_TELEMETRY_OPTOUT` 環境変数を `1` または `true` に設定して、製品利用統計情報の機能をオプトアウトします。</span><span class="sxs-lookup"><span data-stu-id="884e1-119">Opt out of the telemetry feature by setting the `MLDOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> <span data-ttu-id="884e1-120">この環境変数は、ML.NET CLI ツールにグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="884e1-120">This environment variable applies globally to the ML.NET CLI tool.</span></span>

## <a name="data-points-collected"></a><span data-ttu-id="884e1-121">収集されるデータ ポイント</span><span class="sxs-lookup"><span data-stu-id="884e1-121">Data points collected</span></span>

<span data-ttu-id="884e1-122">この機能は次のデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="884e1-122">The feature collects the following data:</span></span>

- <span data-ttu-id="884e1-123">呼び出されたコマンド (`classification` など)</span><span class="sxs-lookup"><span data-stu-id="884e1-123">What command was invoked, such as `classification`</span></span>
- <span data-ttu-id="884e1-124">使用されるコマンドライン パラメーターの名前 ("dataset、label-col、output-path、train-time、verbosity")</span><span class="sxs-lookup"><span data-stu-id="884e1-124">Command-line parameter names used (that is, "dataset, label-col, output-path, train-time, verbosity")</span></span>
- <span data-ttu-id="884e1-125">ハッシュされた MAC アドレス: マシンの暗号化された (SHA256) 匿名で一意の ID</span><span class="sxs-lookup"><span data-stu-id="884e1-125">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine</span></span>
- <span data-ttu-id="884e1-126">呼び出しのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="884e1-126">Timestamp of an invocation</span></span>
- <span data-ttu-id="884e1-127">地理的位置を特定するためにのみ使用される 3 オクテットの IP アドレス (完全な IP アドレスではない)</span><span class="sxs-lookup"><span data-stu-id="884e1-127">Three octet IP address (not full IP address) used only to determine geographical location</span></span>
- <span data-ttu-id="884e1-128">使用されているすべての引数/パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="884e1-128">Name of all arguments/parameters used.</span></span> <span data-ttu-id="884e1-129">文字列などのお客様の値ではありません</span><span class="sxs-lookup"><span data-stu-id="884e1-129">Not the customer's values, such as strings</span></span>
- <span data-ttu-id="884e1-130">ハッシュされたデータセット ファイル名</span><span class="sxs-lookup"><span data-stu-id="884e1-130">Hashed dataset filename</span></span>
- <span data-ttu-id="884e1-131">データセット ファイルサイズ バケット</span><span class="sxs-lookup"><span data-stu-id="884e1-131">Dataset file-size bucket</span></span>
- <span data-ttu-id="884e1-132">オペレーティング システムとバージョン</span><span class="sxs-lookup"><span data-stu-id="884e1-132">Operating system and version</span></span>
- <span data-ttu-id="884e1-133">ML タスク コマンドの値: カテゴリ値 (`regression`、`classification`、`recommendation` など)</span><span class="sxs-lookup"><span data-stu-id="884e1-133">Value of ML task commands: Categorical values, such as `regression`, `classification`, and `recommendation`</span></span>
- <span data-ttu-id="884e1-134">ML.NET CLI バージョン (0.3.27703.4)</span><span class="sxs-lookup"><span data-stu-id="884e1-134">ML.NET CLI version (that is, 0.3.27703.4)</span></span>

<span data-ttu-id="884e1-135">データは [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) テクノロジを使用して Microsoft サーバーに安全に送信され、制限されたアクセスの下で保持され、厳格なセキュリティ コントロールの下で安全な [Azure Storage](https://azure.microsoft.com/services/storage/) システムから使用されます。</span><span class="sxs-lookup"><span data-stu-id="884e1-135">The data is sent securely to Microsoft servers using [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and used under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

### <a name="data-points-not-collected"></a><span data-ttu-id="884e1-136">収集されないデータ ポイント</span><span class="sxs-lookup"><span data-stu-id="884e1-136">Data points not collected</span></span>

<span data-ttu-id="884e1-137">テレメトリ機能では、以下は収集 "*されません*"。</span><span class="sxs-lookup"><span data-stu-id="884e1-137">The telemetry feature *doesn't* collect:</span></span>

- <span data-ttu-id="884e1-138">ユーザー名などの個人データ</span><span class="sxs-lookup"><span data-stu-id="884e1-138">personal data, such as usernames</span></span>
- <span data-ttu-id="884e1-139">データ セットのファイル名</span><span class="sxs-lookup"><span data-stu-id="884e1-139">dataset filenames</span></span>
- <span data-ttu-id="884e1-140">データセット ファイルのデータ</span><span class="sxs-lookup"><span data-stu-id="884e1-140">data from dataset files</span></span>

<span data-ttu-id="884e1-141">ML.NET CLI テレメトリで機密データが収集されている、またはデータの処理が安全ではないか不適切であると思われる場合は、調査のために [ML.NET](https://github.com/dotnet/machinelearning) リポジトリで問題を報告してください。</span><span class="sxs-lookup"><span data-stu-id="884e1-141">If you suspect that the ML.NET CLI telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [ML.NET](https://github.com/dotnet/machinelearning) repository for investigation.</span></span>

## <a name="license"></a><span data-ttu-id="884e1-142">ライセンス</span><span class="sxs-lookup"><span data-stu-id="884e1-142">License</span></span>

<span data-ttu-id="884e1-143">Microsoft による ML.NET CLI の配布には、[マイクロソフト ソフトウェア ライセンス条項:Microsoft .NET ライブラリ](https://aka.ms/dotnet-core-eula)に基づいてライセンスが付与されます。</span><span class="sxs-lookup"><span data-stu-id="884e1-143">The Microsoft distribution of ML.NET CLI is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="884e1-144">データの収集と処理の詳細については、「データ」というタイトルのセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="884e1-144">For details on data collection and processing, see the section entitled "Data."</span></span>

## <a name="disclosure"></a><span data-ttu-id="884e1-145">開示</span><span class="sxs-lookup"><span data-stu-id="884e1-145">Disclosure</span></span>

<span data-ttu-id="884e1-146">`mlnet classification` などの [ML.NET CLI コマンド](../reference/ml-net-cli-reference.md)を初めて実行すると、ML.NET CLI ツールにテレメトリをオプトアウトする方法が説明された開示テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="884e1-146">When you first run a [ML.NET CLI command](../reference/ml-net-cli-reference.md) such as `mlnet classification`, the ML.NET CLI tool displays disclosure text that tells you how to opt out of telemetry.</span></span> <span data-ttu-id="884e1-147">テキストは、実行している CLI のバージョンによって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="884e1-147">Text may vary slightly depending on the version of the CLI you're running.</span></span>

## <a name="see-also"></a><span data-ttu-id="884e1-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="884e1-148">See also</span></span>

- [<span data-ttu-id="884e1-149">ML.NET CLI リファレンス</span><span class="sxs-lookup"><span data-stu-id="884e1-149">ML.NET CLI reference</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="884e1-150">マイクロソフト ソフトウェア ライセンス条項:Microsoft .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="884e1-150">Microsoft Software License Terms: Microsoft .NET Library</span></span>](https://aka.ms/dotnet-core-eula)
- [<span data-ttu-id="884e1-151">Microsoft におけるプライバシー</span><span class="sxs-lookup"><span data-stu-id="884e1-151">Privacy at Microsoft</span></span>](https://www.microsoft.com/trustcenter/privacy/)
- [<span data-ttu-id="884e1-152">Microsoft のプライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="884e1-152">Microsoft Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
