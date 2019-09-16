---
title: ML.NET CLI によるテレメトリ収集
description: 分析のために使用状況の情報を収集する ML.NET CLI テレメトリ機能、収集されるデータ、機能を無効にする方法について説明します。 また、.NET の使用許諾契約と Microsoft GDPR 準拠に関する情報のリンクも紹介します。
ms.topic: conceptual
ms.date: 09/03/2019
ms.custom: ''
ms.openlocfilehash: 77a24416a8008d36006c293cb174b5a8c2f516b7
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929277"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a><span data-ttu-id="13e4e-104">ML.NET CLI によるテレメトリ収集</span><span class="sxs-lookup"><span data-stu-id="13e4e-104">Telemetry collection by the ML.NET CLI</span></span>

<span data-ttu-id="13e4e-105">[ML.NET CLI](https://aka.ms/mlnet-cli) には、Microsoft が利用するために集計している匿名の使用状況データを収集するテレメトリ機能があります。</span><span class="sxs-lookup"><span data-stu-id="13e4e-105">The [ML.NET CLI](https://aka.ms/mlnet-cli) includes a telemetry feature that collects anonymous usage data that is aggregated for use by Microsoft.</span></span>

## <a name="how-microsoft-uses-the-data"></a><span data-ttu-id="13e4e-106">Microsoft によるデータの使用方法</span><span class="sxs-lookup"><span data-stu-id="13e4e-106">How Microsoft uses the data</span></span>

<span data-ttu-id="13e4e-107">製品チームは、ツールの改善方法を理解するために ML.NET CLI のテレメトリ データを使用しています。</span><span class="sxs-lookup"><span data-stu-id="13e4e-107">The product team uses ML.NET CLI telemetry data to help understand how to improve the tools.</span></span> <span data-ttu-id="13e4e-108">たとえば、お客様が特定の機械学習タスクをあまり使用しない場合、製品チームはその理由を調査し、その結果を使用して機能開発の優先順位を決定します。</span><span class="sxs-lookup"><span data-stu-id="13e4e-108">For example, if customers infrequently use a particular machine learning task, the product team investigates why and uses findings to prioritize feature development.</span></span> <span data-ttu-id="13e4e-109">ML.NET CLI のテレメトリは、クラッシュやコードの異常などの問題のデバッグにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="13e4e-109">ML.NET CLI telemetry also helps with debugging of issues such as crashes and code anomalies.</span></span> 

<span data-ttu-id="13e4e-110">製品チームはこの分析情報に感謝していますが、このデータを送信したくない方がいらっしゃることも理解しています。</span><span class="sxs-lookup"><span data-stu-id="13e4e-110">While the product team appreciates this insight, we also know that not everyone wants to send this data.</span></span> [<span data-ttu-id="13e4e-111">テレメトリを無効にする方法についてはこちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13e4e-111">Find out how to disable telemetry.</span></span>](#opt-out-of-data-collection)

## <a name="scope"></a><span data-ttu-id="13e4e-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="13e4e-112">Scope</span></span>

<span data-ttu-id="13e4e-113">`mlnet` コマンドを実行すると、ML.NET CLI が起動しますが、このコマンド自体ではテレメトリが収集されません。</span><span class="sxs-lookup"><span data-stu-id="13e4e-113">The `mlnet` command launches the ML.NET CLI, but the command itself doesn't collect telemetry.</span></span>

<span data-ttu-id="13e4e-114">他のコマンドを添付せずに `mlnet` コマンドを実行すると、テレメトリは "*有効になりません*"。</span><span class="sxs-lookup"><span data-stu-id="13e4e-114">Telemetry *isn't enabled* when you run the `mlnet` command with no other command attached.</span></span> <span data-ttu-id="13e4e-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="13e4e-115">For example:</span></span>

- `mlnet`
- `mlnet --help`

<span data-ttu-id="13e4e-116">`mlnet auto-train` などの [ML.NET CLI コマンド](../reference/ml-net-cli-reference.md)を実行すると、テレメトリは "*有効です*"。</span><span class="sxs-lookup"><span data-stu-id="13e4e-116">Telemetry *is enabled* when you run an [ML.NET CLI command](../reference/ml-net-cli-reference.md), such as `mlnet auto-train`.</span></span>

## <a name="opt-out-of-data-collection"></a><span data-ttu-id="13e4e-117">データ収集のオプトアウト</span><span class="sxs-lookup"><span data-stu-id="13e4e-117">Opt out of data collection</span></span>

<span data-ttu-id="13e4e-118">ML.NET CLI のテレメトリ機能は既定で有効です。</span><span class="sxs-lookup"><span data-stu-id="13e4e-118">The ML.NET CLI telemetry feature is enabled by default.</span></span>

<span data-ttu-id="13e4e-119">`MLDOTNET_CLI_TELEMETRY_OPTOUT` 環境変数を `1` または `true` に設定して、製品利用統計情報の機能をオプトアウトします。</span><span class="sxs-lookup"><span data-stu-id="13e4e-119">Opt out of the telemetry feature by setting the `MLDOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> <span data-ttu-id="13e4e-120">この環境変数は、ML.NET CLI ツールにグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="13e4e-120">This environment variable applies globally to the ML.NET CLI tool.</span></span>

## <a name="data-points-collected"></a><span data-ttu-id="13e4e-121">収集されるデータ ポイント</span><span class="sxs-lookup"><span data-stu-id="13e4e-121">Data points collected</span></span>

<span data-ttu-id="13e4e-122">この機能は次のデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="13e4e-122">The feature collects the following data:</span></span>

- <span data-ttu-id="13e4e-123">呼び出されたコマンド (`auto-train` など)</span><span class="sxs-lookup"><span data-stu-id="13e4e-123">What command was invoked, such as `auto-train`</span></span>
- <span data-ttu-id="13e4e-124">使用されたコマンド ライン パラメーターの名前 ("dataset-name、label-column-name、ml-task、output-path、max-exploration-time、verbosity")</span><span class="sxs-lookup"><span data-stu-id="13e4e-124">Command-line parameter names used (that is, "dataset-name, label-column-name, ml-task, output-path, max-exploration-time, verbosity")</span></span>
- <span data-ttu-id="13e4e-125">ハッシュされた MAC アドレス: マシンの暗号化された (SHA256) 匿名で一意の ID</span><span class="sxs-lookup"><span data-stu-id="13e4e-125">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine</span></span>
- <span data-ttu-id="13e4e-126">呼び出しのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="13e4e-126">Timestamp of an invocation</span></span>
- <span data-ttu-id="13e4e-127">地理的位置を特定するためにのみ使用される 3 オクテットの IP アドレス (完全な IP アドレスではない)</span><span class="sxs-lookup"><span data-stu-id="13e4e-127">Three octet IP address (not full IP address) used only to determine geographical location</span></span>
- <span data-ttu-id="13e4e-128">使用されているすべての引数/パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="13e4e-128">Name of all arguments/parameters used.</span></span> <span data-ttu-id="13e4e-129">文字列などのお客様の値ではありません</span><span class="sxs-lookup"><span data-stu-id="13e4e-129">Not the customer's values, such as strings</span></span>
- <span data-ttu-id="13e4e-130">ハッシュされたデータセット ファイル名</span><span class="sxs-lookup"><span data-stu-id="13e4e-130">Hashed dataset filename</span></span>
- <span data-ttu-id="13e4e-131">データセット ファイルサイズ バケット</span><span class="sxs-lookup"><span data-stu-id="13e4e-131">Dataset file-size bucket</span></span>
- <span data-ttu-id="13e4e-132">オペレーティング システムとバージョン</span><span class="sxs-lookup"><span data-stu-id="13e4e-132">Operating system and version</span></span>
- <span data-ttu-id="13e4e-133">タスク パラメーターの値:カテゴリ値 (`regression`、`binary-classification`、`multiclass-classification` など)</span><span class="sxs-lookup"><span data-stu-id="13e4e-133">Value of --task parameter: Categorical values, such as `regression`, `binary-classification`, and `multiclass-classification`</span></span>
- <span data-ttu-id="13e4e-134">ML.NET CLI バージョン (0.3.27703.4)</span><span class="sxs-lookup"><span data-stu-id="13e4e-134">ML.NET CLI version (that is, 0.3.27703.4)</span></span>

<span data-ttu-id="13e4e-135">データは [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) テクノロジを使用して Microsoft サーバーに安全に送信され、制限されたアクセスの下で保持され、厳格なセキュリティ コントロールの下で安全な [Azure Storage](https://azure.microsoft.com/services/storage/) システムから使用されます。</span><span class="sxs-lookup"><span data-stu-id="13e4e-135">The data is sent securely to Microsoft servers using [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and used under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

### <a name="data-points-not-collected"></a><span data-ttu-id="13e4e-136">収集されないデータ ポイント</span><span class="sxs-lookup"><span data-stu-id="13e4e-136">Data points not collected</span></span>
<span data-ttu-id="13e4e-137">テレメトリ機能では、以下は収集 "*されません*"。</span><span class="sxs-lookup"><span data-stu-id="13e4e-137">The telemetry feature *doesn't* collect:</span></span>

- <span data-ttu-id="13e4e-138">ユーザー名などの個人データ</span><span class="sxs-lookup"><span data-stu-id="13e4e-138">personal data, such as usernames</span></span>
- <span data-ttu-id="13e4e-139">データ セットのファイル名</span><span class="sxs-lookup"><span data-stu-id="13e4e-139">dataset filenames</span></span>
- <span data-ttu-id="13e4e-140">データセット ファイルのデータ</span><span class="sxs-lookup"><span data-stu-id="13e4e-140">data from dataset files</span></span>

<span data-ttu-id="13e4e-141">ML.NET CLI テレメトリで機密データが収集されている、またはデータの処理が安全ではないか不適切であると思われる場合は、調査のために [ML.NET](https://github.com/dotnet/machinelearning) リポジトリで問題を報告してください。</span><span class="sxs-lookup"><span data-stu-id="13e4e-141">If you suspect that the ML.NET CLI telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [ML.NET](https://github.com/dotnet/machinelearning) repository for investigation.</span></span>

## <a name="license"></a><span data-ttu-id="13e4e-142">ライセンス</span><span class="sxs-lookup"><span data-stu-id="13e4e-142">License</span></span>

<span data-ttu-id="13e4e-143">Microsoft による ML.NET CLI の配布には、[マイクロソフト ソフトウェア ライセンス条項:Microsoft .NET ライブラリ](https://aka.ms/dotnet-core-eula)に基づいてライセンスが付与されます。</span><span class="sxs-lookup"><span data-stu-id="13e4e-143">The Microsoft distribution of ML.NET CLI is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="13e4e-144">データの収集と処理の詳細については、「データ」というタイトルのセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13e4e-144">For details on data collection and processing, see the section entitled "Data."</span></span>

## <a name="disclosure"></a><span data-ttu-id="13e4e-145">開示</span><span class="sxs-lookup"><span data-stu-id="13e4e-145">Disclosure</span></span>

<span data-ttu-id="13e4e-146">`mlnet auto-train` などの [ML.NET CLI コマンド](../reference/ml-net-cli-reference.md)を初めて実行すると、ML.NET CLI ツールにテレメトリをオプトアウトする方法が説明された開示テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13e4e-146">When you first run a [ML.NET CLI command](../reference/ml-net-cli-reference.md) such as `mlnet auto-train`, the ML.NET CLI tool displays disclosure text that tells you how to opt out of telemetry.</span></span> <span data-ttu-id="13e4e-147">テキストは、実行している CLI のバージョンによって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="13e4e-147">Text may vary slightly depending on the version of the CLI you're running.</span></span>

## <a name="see-also"></a><span data-ttu-id="13e4e-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="13e4e-148">See also</span></span>

- [<span data-ttu-id="13e4e-149">ML.NET CLI リファレンス</span><span class="sxs-lookup"><span data-stu-id="13e4e-149">ML.NET CLI reference</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="13e4e-150">マイクロソフト ソフトウェア ライセンス条項:Microsoft .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="13e4e-150">Microsoft Software License Terms: Microsoft .NET Library</span></span>](https://aka.ms/dotnet-core-eula)
- [<span data-ttu-id="13e4e-151">Microsoft におけるプライバシー</span><span class="sxs-lookup"><span data-stu-id="13e4e-151">Privacy at Microsoft</span></span>](https://www.microsoft.com/trustcenter/privacy/)
- [<span data-ttu-id="13e4e-152">Microsoft のプライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="13e4e-152">Microsoft Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
