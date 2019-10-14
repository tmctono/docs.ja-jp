---
title: ML.NET CLI を使用してモデルのトレーニングを自動化する
description: ML.NET CLI ツールを使用してコマンドラインから最適なモデルを自動的にトレーニングする方法について説明します。
author: CESARDELATORRE
ms.date: 04/17/2019
ms.custom: how-to
ms.openlocfilehash: c147464ff59563d336363eed73fc6337bdb12e85
ms.sourcegitcommit: 992f80328b51b165051c42ff5330788627abe973
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "72275854"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a><span data-ttu-id="a9f81-103">ML.NET CLI を使用してモデルのトレーニングを自動化する</span><span class="sxs-lookup"><span data-stu-id="a9f81-103">Automate model training with the ML.NET CLI</span></span>

<span data-ttu-id="a9f81-104">ML.NET CLI は、ML.NET を学習する .NET 開発者のために ML.NET を "民主化" するものです。</span><span class="sxs-lookup"><span data-stu-id="a9f81-104">The ML.NET CLI "democratizes" ML.NET for .NET developers when learning ML.NET.</span></span>

<span data-ttu-id="a9f81-105">(ML.NET AutoML CLI を使用せずに) ML.NET API を単独で使用するには、トレーナー (特定のタスクに対する機械学習アルゴリズムの実装) と、データに適用する一連のデータ変換 (特徴エンジニアリング) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9f81-105">To use the ML.NET API by itself, (without the ML.NET AutoML CLI) you need to choose a trainer (implementation of a machine learning algorithm for a particular task), and the set of data transformations (feature engineering) to apply to your data.</span></span> <span data-ttu-id="a9f81-106">最適なパイプラインはデータセットごとに異なるので、すべての選択肢から最適なアルゴリズムを選択すると、複雑さが増します。</span><span class="sxs-lookup"><span data-stu-id="a9f81-106">The optimal pipeline will vary for each dataset and selecting the optimal algorithm from all the choices adds to the complexity.</span></span> <span data-ttu-id="a9f81-107">さらに、各アルゴリズムには調整が必要な一連のハイパーパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="a9f81-107">Even further, each algorithm has a set of hyperparameters to be tuned.</span></span> <span data-ttu-id="a9f81-108">そのため、特徴エンジニアリング、学習アルゴリズム、およびハイパーパラメーターの最適な組み合わせを見つけようとすると、機械学習モデルの最適化に数週間から数か月かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9f81-108">Hence, you can spend weeks and sometimes months on machine learning model optimization trying to find the best combinations of feature engineering, learning algorithms, and hyperparameters.</span></span>

<span data-ttu-id="a9f81-109">このプロセスは、ML.NET AutoML インテリジェント エンジンが実装されている ML.NET CLI を使用して自動化できます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-109">This process can be automated with the ML.NET CLI, which implements the ML.NET AutoML intelligent engine.</span></span>

> [!NOTE]
> <span data-ttu-id="a9f81-110">このトピックは、現在プレビュー段階の ML.NET **CLI** と ML.NET **AutoML** について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9f81-110">This topic refers to ML.NET **CLI** and ML.NET **AutoML**, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="what-is-the-mlnet-command-line-interface-cli"></a><span data-ttu-id="a9f81-111">ML.NET コマンドライン インターフェイス (CLI) とは</span><span class="sxs-lookup"><span data-stu-id="a9f81-111">What is the ML.NET Command-line Interface (CLI)?</span></span>

<span data-ttu-id="a9f81-112">ML.NET CLI は任意のコマンドプロンプト (Windows、Mac、または Linux) で実行して、トレーニング データセットに基づいて高品質の ML.NET モデルとソース コードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-112">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) for generating good quality ML.NET models and source code based on your training dataset.</span></span>

<span data-ttu-id="a9f81-113">次の図に示すように、高品質の ML.NET モデル (シリアル化されたモデルの .zip ファイル) と、そのモデルを実行/スコア付けするサンプル C# コードを簡単に生成できます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-113">As shown in the figure below, it is simple to generate a high quality ML.NET model (serialized model .zip file) plus the sample C# code to run/score that model.</span></span> <span data-ttu-id="a9f81-114">さらに、そのモデルを作成/トレーニングする C# コードも生成されるので、その生成された "最適なモデル" に使用されるアルゴリズムと設定を調べ、反復処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-114">In addition, the C# code to create/train that model is also generated, so that you can research and iterate on the algorithm and settings used for that generated "best model".</span></span>

<span data-ttu-id="a9f81-115">![画像](media/automate-training-with-cli/cli-high-level-process.png "ML.NET CLI 内で動作する AutoML エンジン")</span><span class="sxs-lookup"><span data-stu-id="a9f81-115">![image](media/automate-training-with-cli/cli-high-level-process.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="a9f81-116">自力でコーディングすることなく、所有しているデータセットからこうした資産を生成できるので、ML.NET について知っている場合でも生産性が向上します。</span><span class="sxs-lookup"><span data-stu-id="a9f81-116">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="a9f81-117">現在、ML.NET CLI でサポートされている ML タスクは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9f81-117">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`
- <span data-ttu-id="a9f81-118">予定: `recommendation`、`ranking`、`anomaly-detection`、`clustering` などの他の機械学習タスク</span><span class="sxs-lookup"><span data-stu-id="a9f81-118">Future: other machine learning tasks such as `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span></span>

<span data-ttu-id="a9f81-119">使用例:</span><span class="sxs-lookup"><span data-stu-id="a9f81-119">Example of usage:</span></span>

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![image](media/automate-training-with-cli/cli-model-generation.gif)

<span data-ttu-id="a9f81-121">*Windows PowerShell*、\*macOS/Linux bash、または *Windows CMD* でも同じ方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-121">You can run it the same way on *Windows PowerShell*, \*macOS/Linux bash, or *Windows CMD*.</span></span> <span data-ttu-id="a9f81-122">ただし、タブのオートコンプリート (パラメーター候補) は *Windows CMD* では機能しません。</span><span class="sxs-lookup"><span data-stu-id="a9f81-122">However, tabular auto-completion (parameter suggestions) won't work on *Windows CMD*.</span></span>

## <a name="output-assets-generated"></a><span data-ttu-id="a9f81-123">生成される出力資産</span><span class="sxs-lookup"><span data-stu-id="a9f81-123">Output assets generated</span></span>

<span data-ttu-id="a9f81-124">CLI `auto-train` コマンドを使用すると、出力フォルダーに以下の資産が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-124">The CLI `auto-train` command generates the following assets in the output folder:</span></span>

- <span data-ttu-id="a9f81-125">予測を実行する準備が完了したシリアル化されたモデル .zip ("最適なモデル")。</span><span class="sxs-lookup"><span data-stu-id="a9f81-125">A serialized model .zip ("best model") ready to use for running predictions.</span></span>
- <span data-ttu-id="a9f81-126">C# ソリューション:</span><span class="sxs-lookup"><span data-stu-id="a9f81-126">C# solution with:</span></span>
  - <span data-ttu-id="a9f81-127">その生成されたモデルを実行/スコア付けする C# コード (そのモデルを使用してエンドユーザー アプリで予測を行うため)。</span><span class="sxs-lookup"><span data-stu-id="a9f81-127">C# code to run/score that generated model (to make predictions in your end-user apps with that model).</span></span>
  - <span data-ttu-id="a9f81-128">そのモデルの生成に使用されるトレーニング コードを含む C# コード (学習目的またはモデルの再トレーニングのため)。</span><span class="sxs-lookup"><span data-stu-id="a9f81-128">C# code with the training code used to generate that model (for learning purposes or model retraining).</span></span>
- <span data-ttu-id="a9f81-129">詳細な構成/パイプラインなど、評価される複数のアルゴリズム全体にわたるすべての反復処理/スイープの情報を含むログ ファイル。</span><span class="sxs-lookup"><span data-stu-id="a9f81-129">Log file with information of all iterations/sweeps across the multiple algorithms evaluated, including their detailed configuration/pipeline.</span></span>

<span data-ttu-id="a9f81-130">最初の 2 つの資産は、その生成された ML モデルを使用して予測を行うために、エンドユーザー アプリ (ASP.NET Core Web アプリ、サービス、デスクトップ アプリなど) で直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-130">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="a9f81-131">3 つ目の資産のトレーニング コードは、生成されたモデルをトレーニングするために CLI によって使用された ML.NET API コードを示しています。そのため、モデルを再トレーニングし、背後で CLI および ML.NET AutoML エンジンによって選択された特定のトレーナー/アルゴリズムとハイパーパラメーターを調べて反復処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-131">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can retrain your model and investigate and iterate on which specific trainer/algorithm and hyperparameters were selected by the CLI and AutoML under the covers.</span></span>

## <a name="understanding-the-quality-of-the-model"></a><span data-ttu-id="a9f81-132">モデルの品質を理解する</span><span class="sxs-lookup"><span data-stu-id="a9f81-132">Understanding the quality of the model</span></span>

<span data-ttu-id="a9f81-133">CLI ツールを使用して "最適なモデル" を生成すると、対象の ML タスクに適した品質メトリック (正確度、R-2 乗など) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-133">When you generate a 'best model' with the CLI tool, you see quality metrics (such as accuracy, and R-Squared) as appropriate for the ML task you are targeting.</span></span>

<span data-ttu-id="a9f81-134">ここでは、自動生成された "最適なモデル" の品質を理解できるように、これらのメトリックを ML タスク別にグループ化してまとめています。</span><span class="sxs-lookup"><span data-stu-id="a9f81-134">Here we summarize those metrics grouped by ML task so you can understand the quality of your auto-generated 'best model'.</span></span>

### <a name="metrics-for-binary-classification-models"></a><span data-ttu-id="a9f81-135">二値分類モデルのメトリック</span><span class="sxs-lookup"><span data-stu-id="a9f81-135">Metrics for Binary Classification models</span></span>

<span data-ttu-id="a9f81-136">CLI によって検出される上位 5 つのモデルの二項分類 ML タスク メトリック一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a9f81-136">The following displays the binary classification ML task metrics list for the top five models found by the CLI:</span></span>

![image](media/automate-training-with-cli/cli-binary-classification-metrics.png)

<span data-ttu-id="a9f81-138">正確度は分類問題の一般的なメトリックですが、以下のリファレンスで説明されているように、最適なモデルを選択する場合に正確度が常に最適なメトリックとは限りません。</span><span class="sxs-lookup"><span data-stu-id="a9f81-138">Accuracy is a popular metric for classification problems, however accuracy is not always the best metric to select the best model from as explained in the references below.</span></span> <span data-ttu-id="a9f81-139">必要に応じて追加のメトリックを使用してモデルの品質を評価する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9f81-139">There are cases where you need to evaluate the quality of your model with additional metrics.</span></span>

<span data-ttu-id="a9f81-140">CLI によって出力されるメトリックを調べて理解するには、「[Metrics for binary classification (二項分類のメトリック)](resources/metrics.md#metrics-for-binary-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9f81-140">To explore and understand the metrics that are output by the CLI, see [Metrics for binary classification](resources/metrics.md#metrics-for-binary-classification).</span></span>

### <a name="metrics-for-multi-class-classification-models"></a><span data-ttu-id="a9f81-141">多クラス分類モデルのメトリック</span><span class="sxs-lookup"><span data-stu-id="a9f81-141">Metrics for Multi-class Classification models</span></span>

<span data-ttu-id="a9f81-142">CLI によって検出される上位 5 つのモデルの多クラス分類 ML タスク メトリック一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a9f81-142">The following displays the multi-class classification ML task metrics list for the top five models found by the CLI:</span></span>

![image](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

<span data-ttu-id="a9f81-144">CLI によって出力されるメトリックを調べて理解するには、「[Metrics for multiclass classification (多クラス分類のメトリック)](resources/metrics.md#metrics-for-multi-class-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9f81-144">To explore and understand the metrics that are output by the CLI, see [Metrics for multiclass classification](resources/metrics.md#metrics-for-multi-class-classification).</span></span>

### <a name="metrics-for-regression-models"></a><span data-ttu-id="a9f81-145">回帰モデルのメトリック</span><span class="sxs-lookup"><span data-stu-id="a9f81-145">Metrics for Regression models</span></span>

<span data-ttu-id="a9f81-146">観測値とモデルの予測値の差が小さく偏りがない場合、回帰モデルがデータに適しています。</span><span class="sxs-lookup"><span data-stu-id="a9f81-146">A regression model fits the data well if the differences between the observed values and the model's predicted values are small and unbiased.</span></span> <span data-ttu-id="a9f81-147">回帰は特定のメトリックを使用して評価できます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-147">Regression can be evaluated with certain metrics.</span></span>

<span data-ttu-id="a9f81-148">CLI によって検出される上位 5 つの高品質モデルの同様のメトリック一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9f81-148">You will see a similar list of metrics for the best top five quality models found by the CLI.</span></span> <span data-ttu-id="a9f81-149">回帰 ML タスクに関連するこの特定のケースでは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a9f81-149">In this particular case related to a regression ML task:</span></span>

![image](media/automate-training-with-cli/cli-regression-metrics.png)

<span data-ttu-id="a9f81-151">CLI によって出力されるメトリックを調べて理解するには、「[Metrics for regression (回帰のメトリック)](resources/metrics.md#metrics-for-regression)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9f81-151">To explore and understand the metrics that are output by the CLI, see [Metrics for regression](resources/metrics.md#metrics-for-regression).</span></span>

## <a name="see-also"></a><span data-ttu-id="a9f81-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9f81-152">See also</span></span>

- [<span data-ttu-id="a9f81-153">ML.NET CLI ツールのインストール方法</span><span class="sxs-lookup"><span data-stu-id="a9f81-153">How to install the ML.NET CLI tool</span></span>](how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="a9f81-154">チュートリアル:ML.NET CLI を使用して二項分類子を自動生成する</span><span class="sxs-lookup"><span data-stu-id="a9f81-154">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](tutorials/mlnet-cli.md)
- [<span data-ttu-id="a9f81-155">ML.NET CLI コマンド リファレンス</span><span class="sxs-lookup"><span data-stu-id="a9f81-155">ML.NET CLI command reference</span></span>](reference/ml-net-cli-reference.md)
- [<span data-ttu-id="a9f81-156">ML.NET CLI のテレメトリ</span><span class="sxs-lookup"><span data-stu-id="a9f81-156">Telemetry in ML.NET CLI</span></span>](resources/ml-net-cli-telemetry.md)
