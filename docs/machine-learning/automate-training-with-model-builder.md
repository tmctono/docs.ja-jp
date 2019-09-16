---
title: モデル ビルダーの概要としくみ
description: ML.NET モデル ビルダーを使用し、機械学習モデルを自動的にトレーニングする方法
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: 77b5e75fede1a4aa93eadcf7e21591d82f565cab
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929479"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="796bb-103">モデル ビルダーの概要としくみ</span><span class="sxs-lookup"><span data-stu-id="796bb-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="796bb-104">ML.NET モデル ビルダーは、直観的なグラフィックスでカスタムの機械学習モデルを構築、トレーニング、展開できる Visual Studio 拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="796bb-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="796bb-105">モデル ビルダーでは自動化された機械学習 (AutoML) を利用してさまざまな機械学習のアルゴリズムや設定を見つけます。自分のシナリオに最適なものを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="796bb-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="796bb-106">モデル ビルダーは機械学習の専門知識がなくても使用できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="796bb-107">必要なものはいくつかのデータと解決すべき問題です。</span><span class="sxs-lookup"><span data-stu-id="796bb-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="796bb-108">モデル ビルダーでは、.NET アプリケーションにモデルを追加するコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="796bb-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![モデル ビルダー Visual Studio 拡張機能のユーザー インターフェイスのアニメーション](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="796bb-110">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="796bb-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="796bb-111">シナリオ</span><span class="sxs-lookup"><span data-stu-id="796bb-111">Scenarios</span></span>

<span data-ttu-id="796bb-112">さまざまなシナリオをモデル ビルダーに取り込み、自分のアプリケーションのための機械学習モデルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="796bb-113">シナリオは、自分のデータを使用して行う予測の種類を説明するものです。</span><span class="sxs-lookup"><span data-stu-id="796bb-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="796bb-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="796bb-114">For example:</span></span>

- <span data-ttu-id="796bb-115">過去の販売データに基づいて今後の製品売上高を予測する</span><span class="sxs-lookup"><span data-stu-id="796bb-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="796bb-116">顧客のレビューに基づいてセンチメントを肯定的と否定的に分類する</span><span class="sxs-lookup"><span data-stu-id="796bb-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="796bb-117">銀行取引が詐欺かどうかを検出する</span><span class="sxs-lookup"><span data-stu-id="796bb-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="796bb-118">顧客がフィードバックした問題を社内の該当チームに送信する</span><span class="sxs-lookup"><span data-stu-id="796bb-118">route customer feedback issues to the correct team in your company</span></span>

## <a name="choose-a-model-type"></a><span data-ttu-id="796bb-119">モデルの種類の選択</span><span class="sxs-lookup"><span data-stu-id="796bb-119">Choose a model type</span></span>

<span data-ttu-id="796bb-120">モデル ビルダーでは、機械学習モデルの種類を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="796bb-120">In Model Builder, you need to select a machine learning model type.</span></span> <span data-ttu-id="796bb-121">モデルの種類は、行おうとしている予測の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="796bb-121">The type of model depends on what sort of prediction you are trying to make.</span></span>

<span data-ttu-id="796bb-122">数値を予測するシナリオの場合、機械学習モデルの種類は `regression` と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="796bb-122">For scenarios that predict a number, the machine learning model type is called `regression`.</span></span>

<span data-ttu-id="796bb-123">カテゴリを予測するシナリオの場合、モデルの種類は `classification` です。</span><span class="sxs-lookup"><span data-stu-id="796bb-123">For scenarios that predict a category, the model type is `classification`.</span></span> <span data-ttu-id="796bb-124">分類には、次の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="796bb-124">There are two types of classification:</span></span>

- <span data-ttu-id="796bb-125">カテゴリが 2 つのみの場合は `binary classification`。</span><span class="sxs-lookup"><span data-stu-id="796bb-125">where there are only 2 categories: `binary classification`.</span></span>
- <span data-ttu-id="796bb-126">カテゴリが 3 つ以上ある場合は `multiclass classification`。</span><span class="sxs-lookup"><span data-stu-id="796bb-126">where there are three or more categories: `multiclass classification`.</span></span>

### <a name="which-model-type-is-right-for-me"></a><span data-ttu-id="796bb-127">適切なモデルの種類はどれですか?</span><span class="sxs-lookup"><span data-stu-id="796bb-127">Which model type is right for me?</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="796bb-128">カテゴリを予測する (カテゴリが 2 つのみの場合)</span><span class="sxs-lookup"><span data-stu-id="796bb-128">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="796bb-129">二項分類は、データを 2 つのカテゴリ (はい/いいえ、合格/不合格、真/偽、正/負) に分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="796bb-129">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![不正検出、リスク軽減、アプリケーション スクリーニングなど、二項分類の例を示す図](media/binary-classification-examples.png)

<span data-ttu-id="796bb-131">センチメント分析は、顧客からのフィードバックの肯定性/否定性を予測する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-131">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="796bb-132">これは二項分類のモデルの種類の一例です。</span><span class="sxs-lookup"><span data-stu-id="796bb-132">It is an example of a binary classification model type.</span></span>

<span data-ttu-id="796bb-133">2 つのカテゴリに分類することが自分のシナリオで求められる場合、独自のデータセットと共にこのテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-133">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="796bb-134">カテゴリを予測する (3 つ以上のカテゴリがある場合)</span><span class="sxs-lookup"><span data-stu-id="796bb-134">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="796bb-135">多クラス分類は、データを 3 つ以上のクラスに分類する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-135">Multiclass classification can be used to categorize data into three or more classes.</span></span> 

![ドキュメントと製品の分類、サポート チケットのルーティング、顧客の問題の優先度設定など、多クラス分類の例](media/multiclass-classification-examples.png)

<span data-ttu-id="796bb-137">問題分類は、顧客からのフィードバック (たとえば、GitHub で) に含まれる問題を問題のタイトルや説明で分類する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-137">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="796bb-138">これは多クラス分類のモデルの種類の一例です。</span><span class="sxs-lookup"><span data-stu-id="796bb-138">It is an example of the multi-class classification model type.</span></span>

<span data-ttu-id="796bb-139">データを 3 つ以上のカテゴリに分類する場合、シナリオに問題分類テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-139">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="796bb-140">数値を予測する</span><span class="sxs-lookup"><span data-stu-id="796bb-140">Predict a number</span></span>

<span data-ttu-id="796bb-141">回帰は、数値を予測する目的で利用されます。</span><span class="sxs-lookup"><span data-stu-id="796bb-141">Regression is used to predict numbers.</span></span>

![価格予測、売上予測、予測メンテナンスなどの回帰の例を示す図](media/regression-examples.png)

<span data-ttu-id="796bb-143">価格予測は、家の場所、規模、その他の特徴を利用し、家の価格を予測する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-143">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="796bb-144">これは回帰のモデルの種類の一例です。</span><span class="sxs-lookup"><span data-stu-id="796bb-144">It is an example of a regression model type.</span></span>

<span data-ttu-id="796bb-145">独自のデータセットで数値を予測する場合、自分のシナリオに価格予測テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-145">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-model-type"></a><span data-ttu-id="796bb-146">カスタム シナリオ (モデルの種類を選択する)</span><span class="sxs-lookup"><span data-stu-id="796bb-146">Custom scenario (choose your model type)</span></span>

<span data-ttu-id="796bb-147">カスタム シナリオでは、自分のモデルの種類を手動で選択できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-147">The custom scenario allows you to manually choose your model type.</span></span>

## <a name="data"></a><span data-ttu-id="796bb-148">データ</span><span class="sxs-lookup"><span data-stu-id="796bb-148">Data</span></span>

<span data-ttu-id="796bb-149">モデルの種類を選択すると、モデル ビルダーからデータセットを提供するように求められます。</span><span class="sxs-lookup"><span data-stu-id="796bb-149">Once you have chosen your model type, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="796bb-150">このデータはモデルをトレーニングし、評価し、シナリオに最適なモデルを選択するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="796bb-150">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![モデル ビルダーの手順を示す図](media/model-builder-steps.png)

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="796bb-152">予測する出力を選択します (ラベル)</span><span class="sxs-lookup"><span data-stu-id="796bb-152">Choose the output to predict (label)</span></span>

<span data-ttu-id="796bb-153">データセットは、トレーニング サンプルの行と属性の列からなるテーブルです。</span><span class="sxs-lookup"><span data-stu-id="796bb-153">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="796bb-154">各行の内容:</span><span class="sxs-lookup"><span data-stu-id="796bb-154">Each row has:</span></span>

- <span data-ttu-id="796bb-155">**ラベル** (予測する属性)</span><span class="sxs-lookup"><span data-stu-id="796bb-155">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="796bb-156">**特徴** (ラベルを予測するための入力として使用される属性)。</span><span class="sxs-lookup"><span data-stu-id="796bb-156">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="796bb-157">家の価格予測シナリオの場合、特徴は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="796bb-157">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="796bb-158">家の面積</span><span class="sxs-lookup"><span data-stu-id="796bb-158">the square footage of the house</span></span>
- <span data-ttu-id="796bb-159">寝室と浴室の数</span><span class="sxs-lookup"><span data-stu-id="796bb-159">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="796bb-160">郵便番号</span><span class="sxs-lookup"><span data-stu-id="796bb-160">the zip code</span></span>

<span data-ttu-id="796bb-161">ラベルは、面積、寝室数、浴室数、郵便番号からなるその行の過去の住宅価格です。</span><span class="sxs-lookup"><span data-stu-id="796bb-161">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![サイズ、部屋数、郵便番号、価格ラベルから構成される特徴を持つ住宅価格データからなる行と列を示す表](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="796bb-163">データセットの例</span><span class="sxs-lookup"><span data-stu-id="796bb-163">Example datasets</span></span>

<span data-ttu-id="796bb-164">独自のデータをまだ用意していない場合、次のいずれかのデータセットをお試しください。</span><span class="sxs-lookup"><span data-stu-id="796bb-164">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="796bb-165">シナリオ</span><span class="sxs-lookup"><span data-stu-id="796bb-165">Scenario</span></span>|<span data-ttu-id="796bb-166">モデルの種類</span><span class="sxs-lookup"><span data-stu-id="796bb-166">Model Type</span></span>|<span data-ttu-id="796bb-167">データ</span><span class="sxs-lookup"><span data-stu-id="796bb-167">Data</span></span>|<span data-ttu-id="796bb-168">group1</span><span class="sxs-lookup"><span data-stu-id="796bb-168">Label</span></span>|<span data-ttu-id="796bb-169">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="796bb-169">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="796bb-170">価格の予測</span><span class="sxs-lookup"><span data-stu-id="796bb-170">Price prediction</span></span>|<span data-ttu-id="796bb-171">回帰</span><span class="sxs-lookup"><span data-stu-id="796bb-171">regression</span></span>|[<span data-ttu-id="796bb-172">タクシーの料金データ</span><span class="sxs-lookup"><span data-stu-id="796bb-172">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="796bb-173">料金</span><span class="sxs-lookup"><span data-stu-id="796bb-173">Fare</span></span>|<span data-ttu-id="796bb-174">乗車時間、距離</span><span class="sxs-lookup"><span data-stu-id="796bb-174">Trip time, distance</span></span>|
|<span data-ttu-id="796bb-175">異常検出</span><span class="sxs-lookup"><span data-stu-id="796bb-175">Anomaly detection</span></span>|<span data-ttu-id="796bb-176">二項分類</span><span class="sxs-lookup"><span data-stu-id="796bb-176">binary classification</span></span>|[<span data-ttu-id="796bb-177">製品の売上データ</span><span class="sxs-lookup"><span data-stu-id="796bb-177">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="796bb-178">製品の売上</span><span class="sxs-lookup"><span data-stu-id="796bb-178">Product Sales</span></span>|<span data-ttu-id="796bb-179">月</span><span class="sxs-lookup"><span data-stu-id="796bb-179">Month</span></span>|
|<span data-ttu-id="796bb-180">センチメント分析</span><span class="sxs-lookup"><span data-stu-id="796bb-180">Sentiment analysis</span></span>|<span data-ttu-id="796bb-181">二項分類</span><span class="sxs-lookup"><span data-stu-id="796bb-181">binary classification</span></span>|[<span data-ttu-id="796bb-182">Web サイトのコメント データ</span><span class="sxs-lookup"><span data-stu-id="796bb-182">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="796bb-183">ラベル (否定的なセンチメントのときは 0、肯定的なセンチメントのときは 1)</span><span class="sxs-lookup"><span data-stu-id="796bb-183">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="796bb-184">コメント、年度</span><span class="sxs-lookup"><span data-stu-id="796bb-184">Comment, Year</span></span>|
|<span data-ttu-id="796bb-185">不正行為の検出</span><span class="sxs-lookup"><span data-stu-id="796bb-185">Fraud detection</span></span>|<span data-ttu-id="796bb-186">二項分類</span><span class="sxs-lookup"><span data-stu-id="796bb-186">binary classification</span></span>|[<span data-ttu-id="796bb-187">クレジット カードのデータ</span><span class="sxs-lookup"><span data-stu-id="796bb-187">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="796bb-188">クラス (詐欺の場合は 1、それ以外の場合 0)</span><span class="sxs-lookup"><span data-stu-id="796bb-188">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="796bb-189">金額、V1-V28 (匿名化された特徴)</span><span class="sxs-lookup"><span data-stu-id="796bb-189">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="796bb-190">テキスト分類</span><span class="sxs-lookup"><span data-stu-id="796bb-190">Text classification</span></span>|<span data-ttu-id="796bb-191">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="796bb-191">multiclass classification</span></span>|[<span data-ttu-id="796bb-192">GitHub 問題のデータ</span><span class="sxs-lookup"><span data-stu-id="796bb-192">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="796bb-193">区分</span><span class="sxs-lookup"><span data-stu-id="796bb-193">Area</span></span>|<span data-ttu-id="796bb-194">タイトル、説明</span><span class="sxs-lookup"><span data-stu-id="796bb-194">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="796bb-195">トレーニング</span><span class="sxs-lookup"><span data-stu-id="796bb-195">Train</span></span>

<span data-ttu-id="796bb-196">シナリオ、データ、ラベルを選択すると、モデル ビルダーによってモデルがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="796bb-196">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="796bb-197">トレーニングとは何か?</span><span class="sxs-lookup"><span data-stu-id="796bb-197">What is training?</span></span>

<span data-ttu-id="796bb-198">トレーニングとは、モデル ビルダーがシナリオの質問に対する回答方法をモデルに教える自動プロセスです。</span><span class="sxs-lookup"><span data-stu-id="796bb-198">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="796bb-199">トレーニングが終わると、モデルは以前に見たことがない入力データで予測できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-199">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="796bb-200">たとえば、住宅価格を予測しているなら、新しい住宅が市場に出たとき、その販売価格を予測できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-200">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="796bb-201">モデル ビルダーで使用される機械学習は自動化されているため (AutoML)、トレーニング中に、ユーザーが入力したり、調整したりする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="796bb-201">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

## <a name="evaluate"></a><span data-ttu-id="796bb-202">評価</span><span class="sxs-lookup"><span data-stu-id="796bb-202">Evaluate</span></span>

<span data-ttu-id="796bb-203">評価は、トレーニングしたモデルを使用し、新しいテスト データで予測し、予測の精度を測定するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="796bb-203">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="796bb-204">モデル ビルダーでは、トレーニング セットとテスト セットにトレーニング データが分割されます。</span><span class="sxs-lookup"><span data-stu-id="796bb-204">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="796bb-205">トレーニング データ (80%) はモデルのトレーニングに使用されます。テスト データ (20%) はモデルの評価のための控えとなります。</span><span class="sxs-lookup"><span data-stu-id="796bb-205">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> <span data-ttu-id="796bb-206">モデル ビルダーでは、メトリックを使用して、モデルがどの程度適切かを測定します。</span><span class="sxs-lookup"><span data-stu-id="796bb-206">Model Builder uses metrics to measure how good the model is.</span></span> <span data-ttu-id="796bb-207">使用される特定のメトリックは、モデルの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="796bb-207">The specific metrics used are dependent on the type of model.</span></span> <span data-ttu-id="796bb-208">詳しくは、[モデルの評価メトリック](resources/metrics.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="796bb-208">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="796bb-209">改善</span><span class="sxs-lookup"><span data-stu-id="796bb-209">Improve</span></span>

<span data-ttu-id="796bb-210">モデルのパフォーマンス スコアが予想ほど良くない場合、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="796bb-210">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="796bb-211">トレーニングの時間を長くします。</span><span class="sxs-lookup"><span data-stu-id="796bb-211">Train for a longer period of time.</span></span> <span data-ttu-id="796bb-212">時間を増やせば、自動化された機械学習エンジンは試行するアルゴリズムや設定をそれだけ増やします。</span><span class="sxs-lookup"><span data-stu-id="796bb-212">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="796bb-213">データを追加します。</span><span class="sxs-lookup"><span data-stu-id="796bb-213">Add more data.</span></span> <span data-ttu-id="796bb-214">高品質の機械学習モデルをトレーニングするにはデータ量が十分ではないことがあります。</span><span class="sxs-lookup"><span data-stu-id="796bb-214">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="796bb-215">データのバランスを調整します。</span><span class="sxs-lookup"><span data-stu-id="796bb-215">Balance your data.</span></span> <span data-ttu-id="796bb-216">分類タスクの場合、カテゴリ全体でトレーニング セットのバランスが取れていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="796bb-216">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="796bb-217">たとえば、100 のトレーニング例に対してクラスが 4 つあるとき、90 個のレコードに最初の 2 つのクラス (tag1 と tag2) を使用するが、残りの 2 つ (tag3 と tag4) は残りの 10 個のレコードでのみ使用する場合、データにバランスが欠け、tag3 か tag4 を正しく予測することがモデルにとって難しくなります。</span><span class="sxs-lookup"><span data-stu-id="796bb-217">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="796bb-218">コード</span><span class="sxs-lookup"><span data-stu-id="796bb-218">Code</span></span>

<span data-ttu-id="796bb-219">評価フェーズ後、モデル ビルダーからモデル ファイルとコードが出力されます。このコードを使用し、モデルをアプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-219">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="796bb-220">ML.NET モデルは zip ファイルで保存されます。</span><span class="sxs-lookup"><span data-stu-id="796bb-220">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="796bb-221">モデルを読み込み、使用するためのコードがソリューションに新しいプロジェクトとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="796bb-221">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="796bb-222">モデル ビルダーからはサンプル コンソール アプリも追加されます。これを実行すると、実際に動作するモデルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-222">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="796bb-223">さらに、モデル ビルダーからはモデルを生成したコードが出力されます。モデルの生成に使用された手順を理解できます。</span><span class="sxs-lookup"><span data-stu-id="796bb-223">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="796bb-224">モデル トレーニング コードを使用し、モデルを新しいデータで再トレーニングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="796bb-224">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="796bb-225">次の内容</span><span class="sxs-lookup"><span data-stu-id="796bb-225">What's next?</span></span>

<span data-ttu-id="796bb-226">モデル ビルダーの Visual Studio 拡張機能の[インストール](how-to-guides/install-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="796bb-226">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="796bb-227">[価格予測または回帰のシナリオ](tutorials/predict-prices-with-model-builder.md)をお試しください。</span><span class="sxs-lookup"><span data-stu-id="796bb-227">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
