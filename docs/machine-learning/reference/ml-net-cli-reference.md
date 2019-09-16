---
title: ML.NET CLI ツールの auto-train コマンド
description: ML.NET CLI ツールの auto-train コマンドの概要、サンプル、およびリファレンス。
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: 8363a16ab5e793e715131ac37283106517850439
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929202"
---
# <a name="the-auto-train-command-in-mlnet-cli"></a><span data-ttu-id="c629b-103">ML.NET CLI の "auto-train" コマンド</span><span class="sxs-lookup"><span data-stu-id="c629b-103">The 'auto-train' command in ML.NET CLI</span></span>

> [!NOTE]
> <span data-ttu-id="c629b-104">このトピックは、現在プレビュー段階の ML.NET CLI と ML.NET AutoML について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-104">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

<span data-ttu-id="c629b-105">`auto-train` コマンドは、ML.NET CLI ツールが提供するメイン コマンドです。</span><span class="sxs-lookup"><span data-stu-id="c629b-105">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="c629b-106">このコマンドを使用すると、高品質の ML.NET モデル (シリアル化されたモデルの .zip ファイル) と、そのモデルを実行/スコア付けするサンプル C# コードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="c629b-106">The command allows you to generate a good quality ML.NET model (serialized model .zip file) plus the example C# code to run/score that model.</span></span> <span data-ttu-id="c629b-107">さらに、そのモデルを作成/トレーニングするための C# コードも生成され、その生成された "最適なモデル" に使用されているアルゴリズムと設定を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="c629b-107">In addition, the C# code to create/train that model is also generated for you to research what algorithm and settings it is using for that generated "best model".</span></span>

<span data-ttu-id="c629b-108">自力でコーディングすることなく、所有しているデータセットからこうした資産を生成できるので、ML.NET について知っている場合でも生産性が向上します。</span><span class="sxs-lookup"><span data-stu-id="c629b-108">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="c629b-109">現在、ML.NET CLI でサポートされている ML タスクは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c629b-109">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`

- <span data-ttu-id="c629b-110">予定:次のような他の機械学習タスク</span><span class="sxs-lookup"><span data-stu-id="c629b-110">Future: Other machine learning tasks, such as</span></span>
  - `recommendation`
  - `anomaly-detection`
  - `clustering`

<span data-ttu-id="c629b-111">コマンド プロンプトの使用例:</span><span class="sxs-lookup"><span data-stu-id="c629b-111">Example of usage on the command prompt:</span></span>

```console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="c629b-112">`mlnet auto-train` コマンドで、以下の資産が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-112">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="c629b-113">すぐに使用できるシリアル化されたモデル .zip ("最適なモデル")。</span><span class="sxs-lookup"><span data-stu-id="c629b-113">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="c629b-114">その生成されたモデルを実行/スコア付けする C# コード (そのモデルを使用してエンドユーザー アプリで予測を行うため)。</span><span class="sxs-lookup"><span data-stu-id="c629b-114">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
- <span data-ttu-id="c629b-115">そのモデルの生成に使用されるトレーニング コードを含む C# コード (学習目的)。</span><span class="sxs-lookup"><span data-stu-id="c629b-115">C# code with the training code used to generate that model (Learning purposes).</span></span>

<span data-ttu-id="c629b-116">最初の 2 つの資産は、その生成された ML モデルを使用して予測を行うために、エンドユーザー アプリ (ASP.NET Core Web アプリ、サービス、デスクトップ アプリなど) で直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="c629b-116">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="c629b-117">3 つ目の資産のトレーニング コードは、生成されたモデルをトレーニングするために CLI によって使用された ML.NET API コードを示しています。そのため、CLI および ML.NET AutoML エンジンによって選択された特定のトレーナー/アルゴリズムとハイパーパラメーターを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="c629b-117">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-parameters were selected by the CLI and the ML.NET AutoML engine.</span></span>

## <a name="the-auto-train-command-uses-the-automl-engine"></a><span data-ttu-id="c629b-118">"auto-train" コマンドには AutoML エンジンが使用される</span><span class="sxs-lookup"><span data-stu-id="c629b-118">The 'auto-train' command uses the AutoML engine</span></span>

<span data-ttu-id="c629b-119">次の図に示すように、最高品質のモデルの高度な検索のために、この CLI には ML.NET AutoML エンジン (NuGet パッケージ) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-119">The CLI uses the ML.NET AutoML engine (NuGet package) to intelligently search for the best quality models, as shown in the following diagram:</span></span>

<span data-ttu-id="c629b-120">![画像](./media/ml-net-automl-working-diagram.png "ML.NET CLI 内で動作する AutoML エンジン")</span><span class="sxs-lookup"><span data-stu-id="c629b-120">![image](./media/ml-net-automl-working-diagram.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="c629b-121">"auto-train" コマンドを使用して ML.NET CLI ツールを実行すると、さまざまなアルゴリズムと構成の組み合わせで何度も反復処理が試行されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="c629b-121">When running the ML.NET CLI tool with the \`auto-train- command, you'll see the tool trying many iterations with different algorithms and combinations of configuration.</span></span>

## <a name="reference-for-auto-train-command"></a><span data-ttu-id="c629b-122">"auto-train" コマンドのリファレンス</span><span class="sxs-lookup"><span data-stu-id="c629b-122">Reference for 'auto-train' command</span></span>

## <a name="examples"></a><span data-ttu-id="c629b-123">使用例</span><span class="sxs-lookup"><span data-stu-id="c629b-123">Examples</span></span>

<span data-ttu-id="c629b-124">二項分類問題に適した最も簡単な CLI コマンド (AutoML では、指定されたデータからほとんどの構成を推測する必要があります):</span><span class="sxs-lookup"><span data-stu-id="c629b-124">Simplest CLI command for a binary classification problem (AutoML will need to infer most of the configuration from the provided data):</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="c629b-125">回帰問題に適したもう 1 つの簡単な CLI コマンド:</span><span class="sxs-lookup"><span data-stu-id="c629b-125">Another simple CLI command for a regression problem:</span></span>

``` console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="c629b-126">トレーニング データセット、テスト データセット、およびその他のカスタマイズの明示的な引数を使用して、二項分類モデルを作成し、トレーニングします。</span><span class="sxs-lookup"><span data-stu-id="c629b-126">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="name"></a><span data-ttu-id="c629b-127">name</span><span class="sxs-lookup"><span data-stu-id="c629b-127">Name</span></span>

<span data-ttu-id="c629b-128">`mlnet auto-train` - 指定されたデータセットに基づいて複数のモデルをトレーニングし ("n" 回の反復処理)、最後に最適なモデルを選択し、シリアル化された .zip ファイルとして保存します。さらに、スコア付けとトレーニングに関連する C# コードを生成します。</span><span class="sxs-lookup"><span data-stu-id="c629b-128">`mlnet auto-train` - Trains multiple models ('n' iterations) based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c629b-129">構文</span><span class="sxs-lookup"><span data-stu-id="c629b-129">Synopsis</span></span>

```console
> mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

<span data-ttu-id="c629b-130">無効な入力オプションを指定すると、CLI ツールからは、有効な入力の一覧と、該当する場合は不足している引数について説明するエラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-130">Invalid input options should cause the CLI tool to emit a list of valid inputs and an error message explaining which arg is missing, if that is the case.</span></span>

## <a name="options"></a><span data-ttu-id="c629b-131">オプション</span><span class="sxs-lookup"><span data-stu-id="c629b-131">Options</span></span>

 ----------------------------------------------------------

<span data-ttu-id="c629b-132">`--task | --mltask | -T` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-132">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="c629b-133">解決する ML の問題を示す 1 つの文字列。</span><span class="sxs-lookup"><span data-stu-id="c629b-133">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="c629b-134">たとえば、次のいずれかのタスクです (CLI は、最終的には AutoML でサポートされているすべてのタスクをサポートする予定です)。</span><span class="sxs-lookup"><span data-stu-id="c629b-134">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="c629b-135">`regression` - 数値の予測に ML モデルを使用するかどうかを選択します</span><span class="sxs-lookup"><span data-stu-id="c629b-135">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="c629b-136">`binary-classification` - ML モデルの結果に、2 つの可能なカテゴリ別のブール値 (0 または 1) があるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c629b-136">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="c629b-137">`multiclass-classification` - ML モデルの結果に、複数の可能なカテゴリ別の値があるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c629b-137">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="c629b-138">今後のリリースでは、`recommendations`、`clustering`、`ranking` などの追加の ML タスクとシナリオがサポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="c629b-138">In future releases additional ML Tasks and scenarios such as `recommendations`, `clustering` and `ranking` will be supported.</span></span>

 <span data-ttu-id="c629b-139">この引数には、ML タスクを 1 つのみ指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-139">Only one ML task should be provided in this argument.</span></span>

 ----------------------------------------------------------

<span data-ttu-id="c629b-140">`--dataset | -d` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-140">`--dataset | -d` (string)</span></span>

<span data-ttu-id="c629b-141">この引数には、次のオプションのいずれかのファイルパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c629b-141">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="c629b-142">*A:データセット ファイル全体:* このオプションを使用し、ユーザーが `--test-dataset` と `--validation-dataset` を指定していない場合は、モデルの検証にクロス検証 (k 分割など) または自動データ分割アプローチが内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-142">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="c629b-143">その場合、ユーザーはデータセットのファイルパスを入力するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="c629b-143">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="c629b-144">*B:トレーニング データセット ファイル:* ユーザーがモデル検証用のデータセットも指定している場合 (`--test-dataset` と、必要に応じて `--validation-dataset` を使用)、`--dataset` 引数は "トレーニング データセット" のみがあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c629b-144">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="c629b-145">たとえば、80% - 20% のアプローチを使用してモデルの品質を検証し、正確度のメトリックを取得する場合、"トレーニング データセット" には 80% のデータが含まれ、"テスト データセット" には 20% のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c629b-145">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-146">`--test-dataset | -t` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-146">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="c629b-147">テスト データセット ファイルを指すファイル パス。たとえば、正確度のメトリックを取得するために定期的な検証を行うときに 80% - 20% のアプローチを使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="c629b-147">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="c629b-148">`--test-dataset` を使用する場合は `--dataset` も必要です。</span><span class="sxs-lookup"><span data-stu-id="c629b-148">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="c629b-149">--validation-dataset が使用されていない限り、`--test-dataset` 引数は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c629b-149">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="c629b-150">その場合、ユーザーは 3 つの引数を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-150">In that case, the user must use the three arguments.</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-151">`--validation-dataset | -v` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-151">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="c629b-152">検証データセット ファイルを指すファイル パス。</span><span class="sxs-lookup"><span data-stu-id="c629b-152">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="c629b-153">どのような場合でも、検証データセットは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c629b-153">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="c629b-154">`validation dataset` を使用している場合、動作は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c629b-154">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="c629b-155">`test-dataset` と `--dataset` の引数も必須です。</span><span class="sxs-lookup"><span data-stu-id="c629b-155">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="c629b-156">`validation-dataset` データセットは、モデル選択の予測誤差を推定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-156">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="c629b-157">`test-dataset` は、最終的に選択されたモデルの一般化誤差の評価に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-157">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="c629b-158">テスト セットを "コンテナー" に保管し、データ分析の最後にのみ取り出すのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="c629b-158">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="c629b-159">基本的に、`validation dataset` と `test dataset` を使用する場合、検証フェーズは 2 つの部分に分けられます。</span><span class="sxs-lookup"><span data-stu-id="c629b-159">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="c629b-160">1 つ目の部分では、モデルを見て、検証データを使用して最適なパフォーマンスのアプローチを選択します (= 検証)。</span><span class="sxs-lookup"><span data-stu-id="c629b-160">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="c629b-161">次に、選択したアプローチの正確度を見積もります (= テスト)。</span><span class="sxs-lookup"><span data-stu-id="c629b-161">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="c629b-162">そのため、データの分離は 80/10/10 または 75/15/10 になります。</span><span class="sxs-lookup"><span data-stu-id="c629b-162">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="c629b-163">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c629b-163">For example:</span></span>

- <span data-ttu-id="c629b-164">`training-dataset` ファイルには 75% のデータがあります。</span><span class="sxs-lookup"><span data-stu-id="c629b-164">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="c629b-165">`validation-dataset` ファイルには 15% のデータがあります。</span><span class="sxs-lookup"><span data-stu-id="c629b-165">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="c629b-166">`test-dataset` ファイルには 10% のデータがあります。</span><span class="sxs-lookup"><span data-stu-id="c629b-166">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="c629b-167">いずれの場合でも、これらのパーセンテージは、既に分割されているファイルを指定する CLI の使用ユーザーが決定します。</span><span class="sxs-lookup"><span data-stu-id="c629b-167">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-168">`--label-column-name | -n` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-168">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="c629b-169">この引数を使用すると、データセットのヘッダーに設定されている列の名前を使って、特定の目的/ターゲット列 (予測する変数) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c629b-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="c629b-170">この引数は、*分類問題*など、教師ありの ML タスクにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-170">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="c629b-171">*クラスタリング*など、教師なしの ML タスクには使用できません。</span><span class="sxs-lookup"><span data-stu-id="c629b-171">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-172">`--label-column-index | -i` (int)</span><span class="sxs-lookup"><span data-stu-id="c629b-172">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="c629b-173">この引数を使用すると、データセットのファイル内の列の数値インデックスを使用して、特定の目的/ターゲット列 (予測する変数) を指定できます (列インデックス値は 1 から始まります)。</span><span class="sxs-lookup"><span data-stu-id="c629b-173">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="c629b-174">*注:* ユーザーが `--label-column-name` も使用している場合は、`--label-column-name` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-174">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="c629b-175">この引数は、*分類問題*など、教師ありの ML タスクにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-175">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="c629b-176">*クラスタリング*など、教師なしの ML タスクには使用できません。</span><span class="sxs-lookup"><span data-stu-id="c629b-176">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-177">`--ignore-columns | -I` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-177">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="c629b-178">この引数を使用すると、トレーニング プロセスで読み込まれたり使用されたりしないように、データセット ファイル内の既存の列を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="c629b-178">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="c629b-179">無視する列名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c629b-179">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="c629b-180">複数の列名を区切るには、", " (コンマとスペース) または " " (スペース) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c629b-180">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="c629b-181">空白を含む列名には引用符を使用することができます (例: "logged in")。</span><span class="sxs-lookup"><span data-stu-id="c629b-181">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="c629b-182">例:</span><span class="sxs-lookup"><span data-stu-id="c629b-182">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

----------------------------------------------------------

<span data-ttu-id="c629b-183">`--has-header | -h` (ブール値)</span><span class="sxs-lookup"><span data-stu-id="c629b-183">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="c629b-184">データセット ファイルにヘッダー行があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c629b-184">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="c629b-185">指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c629b-185">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="c629b-186">この引数がユーザーによって指定されていない場合、既定で値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="c629b-186">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="c629b-187">`--label-column-name` 引数を使用するには、データセット ファイルにヘッダーを含め、`--has-header` を `true` に設定する必要があります (これが既定値です)。</span><span class="sxs-lookup"><span data-stu-id="c629b-187">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-188">`--max-exploration-time | -x` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-188">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="c629b-189">既定では、最大探索時間は 30 分です。</span><span class="sxs-lookup"><span data-stu-id="c629b-189">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="c629b-190">この引数では、プロセスで複数のトレーナーと構成を探索できる最長時間 (秒単位) を設定します。</span><span class="sxs-lookup"><span data-stu-id="c629b-190">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="c629b-191">指定した時間が 1 回の反復処理に対して短すぎる (たとえば 2 秒) 場合、構成された時間を超えることがあります。</span><span class="sxs-lookup"><span data-stu-id="c629b-191">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="c629b-192">この場合、実際の時間は、1 回の反復処理で 1 つのモデル構成を作成するために必要な時間です。</span><span class="sxs-lookup"><span data-stu-id="c629b-192">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="c629b-193">反復処理に必要な時間は、データセットのサイズによって変わります。</span><span class="sxs-lookup"><span data-stu-id="c629b-193">The needed time for iterations can vary depending on the size of the dataset.</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-194">`--cache | -c` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="c629b-195">キャッシングを使用すると、トレーニング データセット全体がメモリ内に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c629b-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="c629b-196">中小規模のデータセットでは、キャッシュを使用するとトレーニングのパフォーマンスが大幅に向上します。つまり、キャッシュを使用しない場合よりもトレーニング時間が短くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="c629b-197">ただし、大規模なデータセットの場合、メモリ内のすべてのデータを読み込むと、メモリ不足になる可能性があるので、悪影響が出る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c629b-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="c629b-198">大規模なデータセット ファイルを使用してトレーニングし、キャッシュを使用しない場合、ML.NET では、トレーニング中により多くのデータを読み込む必要があるときに、ドライブから大量のデータがストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="c629b-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="c629b-199">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c629b-199">You can specify the following values:</span></span>

<span data-ttu-id="c629b-200">`on`:トレーニング時にキャッシュを強制的に使用します。</span><span class="sxs-lookup"><span data-stu-id="c629b-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="c629b-201">`off`:トレーニング時にキャッシュを使用しないように強制します。</span><span class="sxs-lookup"><span data-stu-id="c629b-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="c629b-202">`auto`:AutoML のヒューリスティックに応じて、キャッシュを使用するかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="c629b-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="c629b-203">通常、`auto` を選択した場合、中小規模のデータセットではキャッシュが使用され、大規模なデータセットではキャッシュが使用されません。</span><span class="sxs-lookup"><span data-stu-id="c629b-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="c629b-204">`--cache` パラメーターを指定しない場合、既定でキャッシュの `auto` 構成が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-205">`--name | -N` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-205">`--name | -N` (string)</span></span>

<span data-ttu-id="c629b-206">作成される出力プロジェクトまたはソリューションの名前。</span><span class="sxs-lookup"><span data-stu-id="c629b-206">The name for the created output project or solution.</span></span> <span data-ttu-id="c629b-207">名前が指定されていない場合は、名前 `sample-{mltask}` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-207">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="c629b-208">ML.NET モデル ファイル (.ZIP ファイル) も同じ名前になります。</span><span class="sxs-lookup"><span data-stu-id="c629b-208">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-209">`--output-path | -o` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-209">`--output-path | -o` (string)</span></span>

<span data-ttu-id="c629b-210">生成された出力を配置するルートの場所/フォルダー。</span><span class="sxs-lookup"><span data-stu-id="c629b-210">Root location/folder to place the generated output.</span></span> <span data-ttu-id="c629b-211">既定値は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="c629b-211">The default is the current directory.</span></span>

----------------------------------------------------------

<span data-ttu-id="c629b-212">`--verbosity | -V` (文字列)</span><span class="sxs-lookup"><span data-stu-id="c629b-212">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="c629b-213">標準出力の詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="c629b-213">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="c629b-214">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c629b-214">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="c629b-215">`m[inimal]` (既定値)</span><span class="sxs-lookup"><span data-stu-id="c629b-215">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="c629b-216">`diag[nostic]` (ログ情報レベル)</span><span class="sxs-lookup"><span data-stu-id="c629b-216">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="c629b-217">既定で CLI ツールには、作業時に最小限のフィードバック (最小) が表示されます。たとえば、作業中かどうか、可能であれば残り時間、または完了した時間の割合などが示されます。</span><span class="sxs-lookup"><span data-stu-id="c629b-217">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

----------------------------------------------------------

`-h|--help`

<span data-ttu-id="c629b-218">各コマンドのパラメーターの説明と共に、コマンドのヘルプを出力します。</span><span class="sxs-lookup"><span data-stu-id="c629b-218">Prints out help for the command with a description for each command's parameter.</span></span>

----------------------------------------------------------

## <a name="see-also"></a><span data-ttu-id="c629b-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="c629b-219">See also</span></span>

- [<span data-ttu-id="c629b-220">ML.NET CLI ツールのインストール方法</span><span class="sxs-lookup"><span data-stu-id="c629b-220">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="c629b-221">ML.NET CLI を使用してモデルのトレーニングを自動化する</span><span class="sxs-lookup"><span data-stu-id="c629b-221">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="c629b-222">チュートリアル: ML.NET CLI を使用して二項分類子を自動生成する</span><span class="sxs-lookup"><span data-stu-id="c629b-222">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="c629b-223">ML.NET CLI のテレメトリ</span><span class="sxs-lookup"><span data-stu-id="c629b-223">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
