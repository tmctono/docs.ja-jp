---
title: ML.NET CLI によるテレメトリ収集
description: 分析のために使用状況の情報を収集する ML.NET CLI テレメトリ機能、収集されるデータ、機能を無効にする方法について説明します。 また、.NET の使用許諾契約と Microsoft GDPR 準拠に関する情報のリンクも紹介します。
ms.topic: conceptual
ms.date: 05/05/2019
ms.custom: ''
ms.openlocfilehash: 49ebd6c9e1b77c85d891b8c9fb8cbd5c66b478a9
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065545"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a><span data-ttu-id="0512c-104">ML.NET CLI によるテレメトリ収集</span><span class="sxs-lookup"><span data-stu-id="0512c-104">Telemetry collection by the ML.NET CLI</span></span>

<span data-ttu-id="0512c-105">[ML.NET CLI](http://aka.ms/mlnet-cli) には、Microsoft が利用するために集計している匿名の使用状況データを収集するテレメトリ機能があります。</span><span class="sxs-lookup"><span data-stu-id="0512c-105">The [ML.NET CLI](http://aka.ms/mlnet-cli) includes a telemetry feature that collects anonymous usage data that is aggregated for use by Microsoft.</span></span>

## <a name="how-microsoft-uses-the-data"></a><span data-ttu-id="0512c-106">Microsoft によるデータの使用方法</span><span class="sxs-lookup"><span data-stu-id="0512c-106">How Microsoft uses the data</span></span>

<span data-ttu-id="0512c-107">製品チームは、ツールの改善方法を理解するために ML.NET CLI のテレメトリ データを使用しています。</span><span class="sxs-lookup"><span data-stu-id="0512c-107">The product team uses ML.NET CLI telemetry data to help understand how to improve the tools.</span></span> <span data-ttu-id="0512c-108">たとえば、お客様が特定の機械学習タスクをあまり使用しない場合、製品チームはその理由を調査し、その結果を使用して機能開発の優先順位を決定します。</span><span class="sxs-lookup"><span data-stu-id="0512c-108">For example, if customers infrequently use a particular machine learning task, the product team investigates why and uses findings to prioritize feature development.</span></span> <span data-ttu-id="0512c-109">ML.NET CLI のテレメトリは、クラッシュやコードの異常などの問題のデバッグにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0512c-109">ML.NET CLI telemetry also helps with debugging of issues such as crashes and code anomalies.</span></span> 

<span data-ttu-id="0512c-110">製品チームはこの分析情報に感謝していますが、このデータを送信したくない方がいらっしゃることも理解しています。</span><span class="sxs-lookup"><span data-stu-id="0512c-110">While the product team appreciates this insight, we also know that not everyone wants to send this data.</span></span> [<span data-ttu-id="0512c-111">テレメトリを無効にする方法についてはこちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-111">Find out how to disable telemetry.</span></span>](#opt-out-of-data-collection)

## <a name="scope"></a><span data-ttu-id="0512c-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="0512c-112">Scope</span></span>

<span data-ttu-id="0512c-113">`mlnet` コマンドを実行すると、ML.NET CLI が起動しますが、このコマンド自体ではテレメトリが収集されません。</span><span class="sxs-lookup"><span data-stu-id="0512c-113">The `mlnet` command launches the ML.NET CLI, but the command itself doesn't collect telemetry.</span></span>

<span data-ttu-id="0512c-114">他のコマンドを添付せずに `mlnet` コマンドを実行すると、テレメトリは "*有効になりません*"。</span><span class="sxs-lookup"><span data-stu-id="0512c-114">Telemetry *isn't enabled* when you run the `mlnet` command with no other command attached.</span></span> <span data-ttu-id="0512c-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0512c-115">For example:</span></span>

- `mlnet`
- `mlnet --help`

<span data-ttu-id="0512c-116">`mlnet auto-train` などの [ML.NET CLI コマンド](../reference/ml-net-cli-reference.md)を実行すると、テレメトリは "*有効です*"。</span><span class="sxs-lookup"><span data-stu-id="0512c-116">Telemetry *is enabled* when you run an [ML.NET CLI command](../reference/ml-net-cli-reference.md), such as `mlnet auto-train`.</span></span>

## <a name="opt-out-of-data-collection"></a><span data-ttu-id="0512c-117">データ収集のオプトアウト</span><span class="sxs-lookup"><span data-stu-id="0512c-117">Opt out of data collection</span></span>

<span data-ttu-id="0512c-118">ML.NET CLI のテレメトリ機能は既定で有効です。</span><span class="sxs-lookup"><span data-stu-id="0512c-118">The ML.NET CLI telemetry feature is enabled by default.</span></span>

<span data-ttu-id="0512c-119">`DOTNET_CLI_TELEMETRY_OPTOUT` 環境変数を `1` または `true` に設定して、製品利用統計情報の機能をオプトアウトします。</span><span class="sxs-lookup"><span data-stu-id="0512c-119">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> <span data-ttu-id="0512c-120">この環境変数は、.NET CLI ツールにグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-120">This environment variable applies globally to the .NET CLI tool.</span></span>

## <a name="data-points-collected"></a><span data-ttu-id="0512c-121">収集されるデータ ポイント</span><span class="sxs-lookup"><span data-stu-id="0512c-121">Data points collected</span></span>

<span data-ttu-id="0512c-122">この機能は次のデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="0512c-122">The feature collects the following data:</span></span>

- <span data-ttu-id="0512c-123">呼び出されたコマンド (`auto-train` など)</span><span class="sxs-lookup"><span data-stu-id="0512c-123">Which commands are invoked, such as `auto-train`</span></span>
- <span data-ttu-id="0512c-124">ハッシュされた MAC アドレス: マシンの暗号化された (SHA256) 匿名で一意の ID</span><span class="sxs-lookup"><span data-stu-id="0512c-124">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine</span></span>
- <span data-ttu-id="0512c-125">呼び出しのタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="0512c-125">Timestamp of an invocation</span></span>
- <span data-ttu-id="0512c-126">地理的位置を特定するためにのみ使用される 3 オクテットの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="0512c-126">Three octet IP address used only to determine geographical location</span></span>
- <span data-ttu-id="0512c-127">使用されているすべての引数/パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="0512c-127">Name of all arguments/parameters used.</span></span> <span data-ttu-id="0512c-128">文字列などのお客様の値ではありません</span><span class="sxs-lookup"><span data-stu-id="0512c-128">Not the customer's values, such as strings</span></span>
- <span data-ttu-id="0512c-129">オペレーティング システムとバージョン</span><span class="sxs-lookup"><span data-stu-id="0512c-129">Operating system and version</span></span>
- <span data-ttu-id="0512c-130">--ml-task パラメーターの値:カテゴリ値 (`regression`、`binary-classification`、`multiclass-classification` など)</span><span class="sxs-lookup"><span data-stu-id="0512c-130">Value of --ml-task parameter: Categorical values, such as `regression`, `binary-classification`, and `multiclass-classification`</span></span>
- <span data-ttu-id="0512c-131">[丸め対数](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power)のデータ セット ファイル サイズ (最も近い 2 の累乗)</span><span class="sxs-lookup"><span data-stu-id="0512c-131">[Logarithmic rounded](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) dataset file size (nearest power of 2)</span></span>
- <span data-ttu-id="0512c-132">コマンドの `ExitCode`</span><span class="sxs-lookup"><span data-stu-id="0512c-132">`ExitCode` of the command</span></span>

<span data-ttu-id="0512c-133">データは [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) テクノロジを使用して Microsoft サーバーに安全に送信され、制限されたアクセスの下で保持され、厳格なセキュリティ コントロールの下で安全な [Azure Storage](https://azure.microsoft.com/services/storage/) システムから使用されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-133">The data is sent securely to Microsoft servers using [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and used under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

### <a name="data-points-not-collected"></a><span data-ttu-id="0512c-134">収集されないデータ ポイント</span><span class="sxs-lookup"><span data-stu-id="0512c-134">Data points not collected</span></span>
<span data-ttu-id="0512c-135">テレメトリ機能では、以下は収集 "*されません*"。</span><span class="sxs-lookup"><span data-stu-id="0512c-135">The telemetry feature *doesn't* collect:</span></span>
- <span data-ttu-id="0512c-136">ユーザー名などの個人データ</span><span class="sxs-lookup"><span data-stu-id="0512c-136">personal data, such as usernames</span></span>
- <span data-ttu-id="0512c-137">データ セットのファイル名</span><span class="sxs-lookup"><span data-stu-id="0512c-137">dataset filenames</span></span>
- <span data-ttu-id="0512c-138">データセット ファイルのデータ</span><span class="sxs-lookup"><span data-stu-id="0512c-138">data from dataset files</span></span>

<span data-ttu-id="0512c-139">ML.NET CLI テレメトリで機密データが収集されている、またはデータの処理が安全ではないか不適切であると思われる場合は、調査のために [ML.NET](https://github.com/dotnet/machinelearning) リポジトリで問題を報告してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-139">If you suspect that the ML.NET CLI telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [ML.NET](https://github.com/dotnet/machinelearning) repository for investigation.</span></span>

## <a name="license"></a><span data-ttu-id="0512c-140">ライセンス</span><span class="sxs-lookup"><span data-stu-id="0512c-140">License</span></span>

<span data-ttu-id="0512c-141">Microsoft による ML.NET CLI の配布には、[マイクロソフト ソフトウェア ライセンス条項:Microsoft .NET ライブラリ](https://aka.ms/dotnet-core-eula)に基づいてライセンスが付与されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-141">The Microsoft distribution of ML.NET CLI is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="0512c-142">データの収集と処理の詳細については、「データ」というタイトルのセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-142">For details on data collection and processing, see the section entitled "Data."</span></span>

## <a name="disclosure"></a><span data-ttu-id="0512c-143">開示</span><span class="sxs-lookup"><span data-stu-id="0512c-143">Disclosure</span></span>

<span data-ttu-id="0512c-144">`mlnet auto-train` などの [ML.NET CLI コマンド](../reference/ml-net-cli-reference.md)を初めて実行すると、ML.NET CLI ツールにテレメトリをオプトアウトする方法が説明された開示テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-144">When you first run a [ML.NET CLI command](../reference/ml-net-cli-reference.md) such as `mlnet auto-train`, the ML.NET CLI tool displays disclosure text that tells you how to opt out of telemetry.</span></span> <span data-ttu-id="0512c-145">テキストは、実行している CLI のバージョンによって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="0512c-145">Text may vary slightly depending on the version of the CLI you're running.</span></span>

## <a name="see-also"></a><span data-ttu-id="0512c-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="0512c-146">See also</span></span>
- [<span data-ttu-id="0512c-147">ML.NET CLI リファレンス</span><span class="sxs-lookup"><span data-stu-id="0512c-147">ML.NET CLI reference</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="0512c-148">マイクロソフト ソフトウェア ライセンス条項:Microsoft .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="0512c-148">Microsoft Software License Terms: Microsoft .NET Library</span></span>](https://aka.ms/dotnet-core-eula)
- [<span data-ttu-id="0512c-149">Microsoft におけるプライバシー</span><span class="sxs-lookup"><span data-stu-id="0512c-149">Privacy at Microsoft</span></span>](https://www.microsoft.com/en-us/trustcenter/privacy/)
- [<span data-ttu-id="0512c-150">Microsoft のプライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="0512c-150">Microsoft Privacy Statement</span></span>](https://privacy.microsoft.com/en-us/privacystatement)
