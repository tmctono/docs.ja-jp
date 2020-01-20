---
title: モデル ビルダーの概要としくみ
description: ML.NET モデル ビルダーを使用し、機械学習モデルを自動的にトレーニングする方法
ms.date: 01/07/2020
ms.custom: overview
ms.openlocfilehash: ac704b7961a8442a9174cdef5a4cd2a619236a4e
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777403"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="23dc2-103">モデル ビルダーの概要としくみ</span><span class="sxs-lookup"><span data-stu-id="23dc2-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="23dc2-104">ML.NET モデル ビルダーは、直観的なグラフィックスでカスタムの機械学習モデルを構築、トレーニング、展開できる Visual Studio 拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="23dc2-105">モデル ビルダーでは自動化された機械学習 (AutoML) を利用してさまざまな機械学習のアルゴリズムや設定を見つけます。自分のシナリオに最適なものを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="23dc2-106">モデル ビルダーは機械学習の専門知識がなくても使用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="23dc2-107">必要なものはいくつかのデータと解決すべき問題です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="23dc2-108">モデル ビルダーでは、.NET アプリケーションにモデルを追加するコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![モデル ビルダー Visual Studio 拡張機能のユーザー インターフェイスのアニメーション](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="23dc2-110">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="23dc2-111">シナリオ</span><span class="sxs-lookup"><span data-stu-id="23dc2-111">Scenarios</span></span>

<span data-ttu-id="23dc2-112">さまざまなシナリオをモデル ビルダーに取り込み、自分のアプリケーションのための機械学習モデルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="23dc2-113">シナリオは、自分のデータを使用して行う予測の種類を説明するものです。</span><span class="sxs-lookup"><span data-stu-id="23dc2-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="23dc2-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="23dc2-114">For example:</span></span>

- <span data-ttu-id="23dc2-115">過去の販売データに基づいて今後の製品売上高を予測する</span><span class="sxs-lookup"><span data-stu-id="23dc2-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="23dc2-116">顧客のレビューに基づいてセンチメントを肯定的と否定的に分類する</span><span class="sxs-lookup"><span data-stu-id="23dc2-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="23dc2-117">銀行取引が詐欺かどうかを検出する</span><span class="sxs-lookup"><span data-stu-id="23dc2-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="23dc2-118">顧客がフィードバックした問題を社内の該当チームに送信する</span><span class="sxs-lookup"><span data-stu-id="23dc2-118">route customer feedback issues to the correct team in your company</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="23dc2-119">自分に最適な機械学習シナリオとは?</span><span class="sxs-lookup"><span data-stu-id="23dc2-119">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="23dc2-120">モデル ビルダーでは、シナリオを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-120">In Model Builder, you need to select a scenario.</span></span> <span data-ttu-id="23dc2-121">シナリオの種類は、行おうとしている予測の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-121">The type of scenario depends on what type of prediction you are trying to make.</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="23dc2-122">カテゴリを予測する (カテゴリが 2 つのみの場合)</span><span class="sxs-lookup"><span data-stu-id="23dc2-122">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="23dc2-123">二項分類は、データを 2 つのカテゴリ (はい/いいえ、合格/不合格、真/偽、正/負) に分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-123">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![不正検出、リスク軽減、アプリケーション スクリーニングなど、二項分類の例を示す図](media/binary-classification-examples.png)

<span data-ttu-id="23dc2-125">センチメント分析は、顧客からのフィードバックの肯定性/否定性を予測する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-125">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="23dc2-126">これは二項分類の機械学習タスクの一例です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-126">It is an example of the binary classification machine learning task.</span></span>

<span data-ttu-id="23dc2-127">2 つのカテゴリに分類することが自分のシナリオで求められる場合、独自のデータセットと共にこのテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-127">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="23dc2-128">カテゴリを予測する (3 つ以上のカテゴリがある場合)</span><span class="sxs-lookup"><span data-stu-id="23dc2-128">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="23dc2-129">多クラス分類は、データを 3 つ以上のクラスに分類する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-129">Multiclass classification can be used to categorize data into three or more classes.</span></span>

![ドキュメントと製品の分類、サポート チケットのルーティング、顧客の問題の優先度設定など、多クラス分類の例](media/multiclass-classification-examples.png)

<span data-ttu-id="23dc2-131">問題分類は、顧客からのフィードバック (たとえば、GitHub で) に含まれる問題を問題のタイトルや説明で分類する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-131">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="23dc2-132">これは多クラス分類の機械学習タスクの一例です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-132">It is an example of the multi-class classification machine learning task.</span></span>

<span data-ttu-id="23dc2-133">データを 3 つ以上のカテゴリに分類する場合、シナリオに問題分類テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-133">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="23dc2-134">数値を予測する</span><span class="sxs-lookup"><span data-stu-id="23dc2-134">Predict a number</span></span>

<span data-ttu-id="23dc2-135">回帰は、数値を予測する目的で利用されます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-135">Regression is used to predict numbers.</span></span>

![価格予測、売上予測、予測メンテナンスなどの回帰の例を示す図](media/regression-examples.png)

<span data-ttu-id="23dc2-137">価格予測は、家の場所、規模、その他の特徴を利用し、家の価格を予測する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-137">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="23dc2-138">これは回帰の機械学習タスクの一例です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-138">It is an example of the regression machine learning task.</span></span>

<span data-ttu-id="23dc2-139">独自のデータセットで数値を予測する場合、自分のシナリオに価格予測テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-139">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="classify-images-into-categories"></a><span data-ttu-id="23dc2-140">イメージをカテゴリに分類する</span><span class="sxs-lookup"><span data-stu-id="23dc2-140">Classify images into categories</span></span>

<span data-ttu-id="23dc2-141">このシナリオは多クラス分類の特殊なケースで、分類される入力データが一連のイメージになっています。</span><span class="sxs-lookup"><span data-stu-id="23dc2-141">This scenario is a special case of multiclass classification, where the input data to be categorized is a set of images.</span></span>

<span data-ttu-id="23dc2-142">イメージ分類を使用すると、さまざまなカテゴリのイメージを特定できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-142">Image classification can be used to identify images of different categories.</span></span> <span data-ttu-id="23dc2-143">これには、さまざまな種類の地形、動物、製造上の不具合などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-143">For example, different types of terrain or animals or manufacturing defects.</span></span>

<span data-ttu-id="23dc2-144">一連のイメージがあり、イメージをさまざまなカテゴリに分類したいときは、ご自身のシナリオに合ったイメージ分類テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-144">You can use the image classification template for your scenario if you have a set of images, and you want to classify the images into different categories.</span></span>

#### <a name="custom-scenario"></a><span data-ttu-id="23dc2-145">カスタム シナリオ</span><span class="sxs-lookup"><span data-stu-id="23dc2-145">Custom scenario</span></span>

<span data-ttu-id="23dc2-146">カスタム シナリオでは、自分のシナリオを手動で選択できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-146">The custom scenario allows you to manually choose your scenario.</span></span>

## <a name="data"></a><span data-ttu-id="23dc2-147">データ</span><span class="sxs-lookup"><span data-stu-id="23dc2-147">Data</span></span>

<span data-ttu-id="23dc2-148">シナリオを選択すると、モデル ビルダーからデータセットを提供するように求められます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-148">Once you have chosen your scenario, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="23dc2-149">このデータはモデルをトレーニングし、評価し、シナリオに最適なモデルを選択するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-149">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![モデル ビルダーの手順を示す図](media/model-builder-steps.png)

<span data-ttu-id="23dc2-151">モデル ビルダーは、.tsv、.csv、.txt 形式のデータセットと、SQL データベース形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="23dc2-151">Model Builder supports datasets in .tsv, .csv, .txt formats, as well as SQL database format.</span></span> <span data-ttu-id="23dc2-152">.txt ファイルがある場合、列は `,`、`;`、または `/t` で区切る必要があり、ファイルにはヘッダー行が必要です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-152">If you have a .txt file, columns should be separated with `,`, `;` or `/t` and the file must have a header row.</span></span>

<span data-ttu-id="23dc2-153">データセットがイメージで構成されている場合、サポートされているファイルの種類は `.jpg` と `.png`です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-153">If the dataset is made up of images, the supported file types are `.jpg` and `.png`.</span></span>

<span data-ttu-id="23dc2-154">詳細については、「[モデル ビルダーにトレーニング データを読み込む](how-to-guides/load-data-model-builder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23dc2-154">For more information, see [Load training data into Model Builder](how-to-guides/load-data-model-builder.md).</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="23dc2-155">予測する出力を選択します (ラベル)</span><span class="sxs-lookup"><span data-stu-id="23dc2-155">Choose the output to predict (label)</span></span>

<span data-ttu-id="23dc2-156">データセットは、トレーニング サンプルの行と属性の列からなるテーブルです。</span><span class="sxs-lookup"><span data-stu-id="23dc2-156">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="23dc2-157">各行の内容:</span><span class="sxs-lookup"><span data-stu-id="23dc2-157">Each row has:</span></span>

- <span data-ttu-id="23dc2-158">**ラベル** (予測する属性)</span><span class="sxs-lookup"><span data-stu-id="23dc2-158">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="23dc2-159">**特徴** (ラベルを予測するための入力として使用される属性)。</span><span class="sxs-lookup"><span data-stu-id="23dc2-159">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="23dc2-160">家の価格予測シナリオの場合、特徴は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-160">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="23dc2-161">家の面積</span><span class="sxs-lookup"><span data-stu-id="23dc2-161">the square footage of the house</span></span>
- <span data-ttu-id="23dc2-162">寝室と浴室の数</span><span class="sxs-lookup"><span data-stu-id="23dc2-162">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="23dc2-163">郵便番号</span><span class="sxs-lookup"><span data-stu-id="23dc2-163">the zip code</span></span>

<span data-ttu-id="23dc2-164">ラベルは、面積、寝室数、浴室数、郵便番号からなるその行の過去の住宅価格です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-164">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![サイズ、部屋数、郵便番号、価格ラベルから構成される特徴を持つ住宅価格データからなる行と列を示す表](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="23dc2-166">データセットの例</span><span class="sxs-lookup"><span data-stu-id="23dc2-166">Example datasets</span></span>

<span data-ttu-id="23dc2-167">独自のデータをまだ用意していない場合、次のいずれかのデータセットをお試しください。</span><span class="sxs-lookup"><span data-stu-id="23dc2-167">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="23dc2-168">シナリオ</span><span class="sxs-lookup"><span data-stu-id="23dc2-168">Scenario</span></span>|<span data-ttu-id="23dc2-169">ML タスク</span><span class="sxs-lookup"><span data-stu-id="23dc2-169">ML task</span></span>|<span data-ttu-id="23dc2-170">データ</span><span class="sxs-lookup"><span data-stu-id="23dc2-170">Data</span></span>|<span data-ttu-id="23dc2-171">group1</span><span class="sxs-lookup"><span data-stu-id="23dc2-171">Label</span></span>|<span data-ttu-id="23dc2-172">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="23dc2-172">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="23dc2-173">価格の予測</span><span class="sxs-lookup"><span data-stu-id="23dc2-173">Price prediction</span></span>|<span data-ttu-id="23dc2-174">回帰</span><span class="sxs-lookup"><span data-stu-id="23dc2-174">regression</span></span>|[<span data-ttu-id="23dc2-175">タクシーの料金データ</span><span class="sxs-lookup"><span data-stu-id="23dc2-175">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="23dc2-176">料金</span><span class="sxs-lookup"><span data-stu-id="23dc2-176">Fare</span></span>|<span data-ttu-id="23dc2-177">乗車時間、距離</span><span class="sxs-lookup"><span data-stu-id="23dc2-177">Trip time, distance</span></span>|
|<span data-ttu-id="23dc2-178">異常検出</span><span class="sxs-lookup"><span data-stu-id="23dc2-178">Anomaly detection</span></span>|<span data-ttu-id="23dc2-179">二項分類</span><span class="sxs-lookup"><span data-stu-id="23dc2-179">binary classification</span></span>|[<span data-ttu-id="23dc2-180">製品の売上データ</span><span class="sxs-lookup"><span data-stu-id="23dc2-180">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="23dc2-181">製品の売上</span><span class="sxs-lookup"><span data-stu-id="23dc2-181">Product Sales</span></span>|<span data-ttu-id="23dc2-182">月</span><span class="sxs-lookup"><span data-stu-id="23dc2-182">Month</span></span>|
|<span data-ttu-id="23dc2-183">感情分析</span><span class="sxs-lookup"><span data-stu-id="23dc2-183">Sentiment analysis</span></span>|<span data-ttu-id="23dc2-184">二項分類</span><span class="sxs-lookup"><span data-stu-id="23dc2-184">binary classification</span></span>|[<span data-ttu-id="23dc2-185">Web サイトのコメント データ</span><span class="sxs-lookup"><span data-stu-id="23dc2-185">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="23dc2-186">ラベル (否定的なセンチメントのときは 0、肯定的なセンチメントのときは 1)</span><span class="sxs-lookup"><span data-stu-id="23dc2-186">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="23dc2-187">コメント、年度</span><span class="sxs-lookup"><span data-stu-id="23dc2-187">Comment, Year</span></span>|
|<span data-ttu-id="23dc2-188">不正検出</span><span class="sxs-lookup"><span data-stu-id="23dc2-188">Fraud detection</span></span>|<span data-ttu-id="23dc2-189">二項分類</span><span class="sxs-lookup"><span data-stu-id="23dc2-189">binary classification</span></span>|[<span data-ttu-id="23dc2-190">クレジット カードのデータ</span><span class="sxs-lookup"><span data-stu-id="23dc2-190">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="23dc2-191">クラス (詐欺の場合は 1、それ以外の場合 0)</span><span class="sxs-lookup"><span data-stu-id="23dc2-191">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="23dc2-192">金額、V1-V28 (匿名化された特徴)</span><span class="sxs-lookup"><span data-stu-id="23dc2-192">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="23dc2-193">テキスト分類</span><span class="sxs-lookup"><span data-stu-id="23dc2-193">Text classification</span></span>|<span data-ttu-id="23dc2-194">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="23dc2-194">multiclass classification</span></span>|[<span data-ttu-id="23dc2-195">GitHub 問題のデータ</span><span class="sxs-lookup"><span data-stu-id="23dc2-195">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="23dc2-196">区分</span><span class="sxs-lookup"><span data-stu-id="23dc2-196">Area</span></span>|<span data-ttu-id="23dc2-197">タイトル、説明</span><span class="sxs-lookup"><span data-stu-id="23dc2-197">Title, Description</span></span>|
|<span data-ttu-id="23dc2-198">イメージ分類</span><span class="sxs-lookup"><span data-stu-id="23dc2-198">Image classification</span></span>|<span data-ttu-id="23dc2-199">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="23dc2-199">multiclass classification</span></span>|[<span data-ttu-id="23dc2-200">花のイメージ</span><span class="sxs-lookup"><span data-stu-id="23dc2-200">Flowers images</span></span>](http://download.tensorflow.org/example_images/flower_photos.tgz)|<span data-ttu-id="23dc2-201">花の種類: デイジー、タンポポ、バラ、ヒマワリ、チューリップ</span><span class="sxs-lookup"><span data-stu-id="23dc2-201">The type of flower: daisy, dandelion, roses, sunflowers, tulips</span></span>|<span data-ttu-id="23dc2-202">イメージ データ自体</span><span class="sxs-lookup"><span data-stu-id="23dc2-202">The image data itself</span></span>|

## <a name="train"></a><span data-ttu-id="23dc2-203">トレーニング</span><span class="sxs-lookup"><span data-stu-id="23dc2-203">Train</span></span>

<span data-ttu-id="23dc2-204">シナリオ、データ、ラベルを選択すると、モデル ビルダーによってモデルがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-204">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="23dc2-205">トレーニングとは何か?</span><span class="sxs-lookup"><span data-stu-id="23dc2-205">What is training?</span></span>

<span data-ttu-id="23dc2-206">トレーニングとは、モデル ビルダーがシナリオの質問に対する回答方法をモデルに教える自動プロセスです。</span><span class="sxs-lookup"><span data-stu-id="23dc2-206">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="23dc2-207">トレーニングが終わると、モデルは以前に見たことがない入力データで予測できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-207">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="23dc2-208">たとえば、住宅価格を予測しているなら、新しい住宅が市場に出たとき、その販売価格を予測できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-208">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="23dc2-209">モデル ビルダーで使用される機械学習は自動化されているため (AutoML)、トレーニング中に、ユーザーが入力したり、調整したりする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="23dc2-209">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="23dc2-210">どのくらいの時間、トレーニングしますか?</span><span class="sxs-lookup"><span data-stu-id="23dc2-210">How long should I train for?</span></span>

<span data-ttu-id="23dc2-211">モデル ビルダーは、AutoML を使用して複数のモデルを探索し、最適なパフォーマンスを発揮するモデルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-211">Model Builder uses AutoML to explore multiple models to find you the best performing model.</span></span>

<span data-ttu-id="23dc2-212">トレーニング期間を長くすると、AutoML はより広い設定範囲でさらに多くのモデルを探索できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-212">Longer training periods allow AutoML to explore more models with a wider range of settings.</span></span>

<span data-ttu-id="23dc2-213">以下の表は、ローカル コンピューターにある一連のサンプル データセットで、優れたパフォーマンスを得るのに要した平均時間を示しています。</span><span class="sxs-lookup"><span data-stu-id="23dc2-213">The table below summarizes the average time taken to get good performance for a suite of example datasets, on a local machine.</span></span>

|<span data-ttu-id="23dc2-214">データセットのサイズ</span><span class="sxs-lookup"><span data-stu-id="23dc2-214">Dataset size</span></span>|<span data-ttu-id="23dc2-215">トレーニングの平均時間</span><span class="sxs-lookup"><span data-stu-id="23dc2-215">Average time to train</span></span>|
|------------|---------------------|
|<span data-ttu-id="23dc2-216">0 - 10 MB</span><span class="sxs-lookup"><span data-stu-id="23dc2-216">0 - 10 MB</span></span>|<span data-ttu-id="23dc2-217">10 秒</span><span class="sxs-lookup"><span data-stu-id="23dc2-217">10 sec</span></span>|
|<span data-ttu-id="23dc2-218">10 - 100 MB</span><span class="sxs-lookup"><span data-stu-id="23dc2-218">10 - 100 MB</span></span>|<span data-ttu-id="23dc2-219">10 分</span><span class="sxs-lookup"><span data-stu-id="23dc2-219">10 min</span></span>|
|<span data-ttu-id="23dc2-220">100 - 500 MB</span><span class="sxs-lookup"><span data-stu-id="23dc2-220">100 - 500 MB</span></span>|<span data-ttu-id="23dc2-221">30 分</span><span class="sxs-lookup"><span data-stu-id="23dc2-221">30 min</span></span>|
|<span data-ttu-id="23dc2-222">500 MB - 1 GB</span><span class="sxs-lookup"><span data-stu-id="23dc2-222">500 - 1 GB</span></span>|<span data-ttu-id="23dc2-223">60 分</span><span class="sxs-lookup"><span data-stu-id="23dc2-223">60 min</span></span>|
|<span data-ttu-id="23dc2-224">1 GB 超</span><span class="sxs-lookup"><span data-stu-id="23dc2-224">1 GB+</span></span>|<span data-ttu-id="23dc2-225">3 時間超</span><span class="sxs-lookup"><span data-stu-id="23dc2-225">3+ hours</span></span>|

<span data-ttu-id="23dc2-226">これらは参考用の数字に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="23dc2-226">These numbers are a guide only.</span></span> <span data-ttu-id="23dc2-227">トレーニングの正確な長さは、次の条件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-227">The exact length of training is dependent on:</span></span>

- <span data-ttu-id="23dc2-228">モデルへの入力として使用されている特徴 (列) の数</span><span class="sxs-lookup"><span data-stu-id="23dc2-228">the number of features (columns) being used to as input to the model</span></span>
- <span data-ttu-id="23dc2-229">列の種類</span><span class="sxs-lookup"><span data-stu-id="23dc2-229">the type of columns</span></span>
- <span data-ttu-id="23dc2-230">ML タスク</span><span class="sxs-lookup"><span data-stu-id="23dc2-230">the ML task</span></span>
- <span data-ttu-id="23dc2-231">トレーニングに使用されるマシンの CPU、ディスク、およびメモリのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="23dc2-231">the CPU, disk and memory performance of the machine used for training</span></span>

## <a name="evaluate"></a><span data-ttu-id="23dc2-232">評価</span><span class="sxs-lookup"><span data-stu-id="23dc2-232">Evaluate</span></span>

<span data-ttu-id="23dc2-233">評価は、モデルがどのくらい適切かを測定するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="23dc2-233">Evaluation is the process of measuring how good your model is.</span></span> <span data-ttu-id="23dc2-234">モデル ビルダーは、トレーニングしたモデルを使用して新しいテスト データで予測し、予測の精度を測定します。</span><span class="sxs-lookup"><span data-stu-id="23dc2-234">Model Builder uses the trained model to make predictions with new test data, and then measures how good the predictions are.</span></span>

<span data-ttu-id="23dc2-235">モデル ビルダーでは、トレーニング セットとテスト セットにトレーニング データが分割されます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-235">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="23dc2-236">トレーニング データ (80%) はモデルのトレーニングに使用されます。テスト データ (20%) はモデルの評価のための控えとなります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-236">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> 

### <a name="how-do-i-understand-my-model-performance"></a><span data-ttu-id="23dc2-237">モデルのパフォーマンスを把握するには</span><span class="sxs-lookup"><span data-stu-id="23dc2-237">How do I understand my model performance?</span></span>

<span data-ttu-id="23dc2-238">シナリオが機械学習タスクにマップされます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-238">A scenario maps to a machine learning task.</span></span> <span data-ttu-id="23dc2-239">各 ML タスクには、独自の評価メトリック セットがあります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-239">Each ML task has its own set of evaluation metrics.</span></span>

#### <a name="regression-for-example-price-prediction"></a><span data-ttu-id="23dc2-240">回帰 (価格の予測など)</span><span class="sxs-lookup"><span data-stu-id="23dc2-240">Regression (for example, Price Prediction)</span></span>

<span data-ttu-id="23dc2-241">回帰問題の既定のメトリックは RSquared で、RSquared の値の範囲は 0 から 1 です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-241">The default metric for regression problems is RSquared, the value of RSquared ranges between 0 and 1.</span></span> <span data-ttu-id="23dc2-242">最適な値は 1 です。つまり、RSquared の値が 1 に近いほど、モデルのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="23dc2-242">1 is the best possible value or in other words the closer the value of RSquared to 1 the better your model is performing.</span></span>

<span data-ttu-id="23dc2-243">絶対損失、二乗損失、RMS 損失など、報告されるその他のメトリックは追加メトリックで、モデルのパフォーマンスを理解し、それを他の回帰モデルと比較する目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-243">Other metrics reported such as absolute-loss, squared-loss, and RMS loss are additional metrics, which can be used to understand how your model is performing and comparing it against other regression models.</span></span>

#### <a name="binary-classification-for-example-sentiment-analysis"></a><span data-ttu-id="23dc2-244">二項分類 (感情分析など)</span><span class="sxs-lookup"><span data-stu-id="23dc2-244">Binary Classification (for example, Sentiment Analysis)</span></span>

<span data-ttu-id="23dc2-245">分類問題の既定のメトリックは正確度です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-245">The default metric for classification problems is accuracy.</span></span> <span data-ttu-id="23dc2-246">正確度は、テスト データセットに基づいてモデルが正しく予測する比率を定めるものです。</span><span class="sxs-lookup"><span data-stu-id="23dc2-246">Accuracy defines the proportion of correct predictions your model is making over the test dataset.</span></span> <span data-ttu-id="23dc2-247">100%、つまり 1.0 に近ければ近いほど、良いということになります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-247">The closer to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="23dc2-248">真陽性率と擬陽性率を測定する AUC (曲線下面積) など、報告されるその他のメトリックは 0.50 以上であれば、モデルは許容されます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-248">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate should be greater than 0.50 for models to be acceptable.</span></span>

<span data-ttu-id="23dc2-249">F1 スコアなどの追加メトリックを使用すると、精度と再現率のバランスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-249">Additional metrics like F1 score can be used to control the balance between Precision and Recall.</span></span>

#### <a name="multi-class-classification-for-example-issue-classification-image-classification"></a><span data-ttu-id="23dc2-250">多クラス分類 (問題の分類、イメージの分類など)</span><span class="sxs-lookup"><span data-stu-id="23dc2-250">Multi-Class Classification (for example, Issue Classification, Image Classification)</span></span>

<span data-ttu-id="23dc2-251">多クラス分類の既定のメトリックはマイクロ正確度です。</span><span class="sxs-lookup"><span data-stu-id="23dc2-251">The default metric for Multi-class classification is Micro Accuracy.</span></span> <span data-ttu-id="23dc2-252">マイクロ正確度が 100%、つまり 1.0 に近ければ近いほど、良いということになります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-252">The closer the Micro Accuracy to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="23dc2-253">多クラス分類のもう 1 つの重要なメトリックはマクロ正確度です。マイクロ正確度と同様、1.0 に近いほど良いことになります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-253">Another important metric for Multi-class classification is Macro-accuracy, similar to Micro-accuracy the closer to 1.0 the better it is.</span></span> <span data-ttu-id="23dc2-254">これらの 2 種類の正確度は次のように考えるとよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="23dc2-254">A good way to think about these two types of accuracy is:</span></span>

- <span data-ttu-id="23dc2-255">マイクロ正確度: 受信チケットが、どのくらいの頻度で適切なチームに分類されるか。</span><span class="sxs-lookup"><span data-stu-id="23dc2-255">Micro-accuracy: How often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="23dc2-256">マクロ正確度: 平均的なチームが受け取るチケットが、そのチームにとって適切である頻度はどのくらいか。</span><span class="sxs-lookup"><span data-stu-id="23dc2-256">Macro-accuracy: For an average team, how often is an incoming ticket correct for their team?</span></span>

### <a name="more-information-on-evaluation-metrics"></a><span data-ttu-id="23dc2-257">評価メトリックの詳細</span><span class="sxs-lookup"><span data-stu-id="23dc2-257">More information on evaluation metrics</span></span>

<span data-ttu-id="23dc2-258">詳しくは、[モデルの評価メトリック](resources/metrics.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="23dc2-258">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="23dc2-259">改善</span><span class="sxs-lookup"><span data-stu-id="23dc2-259">Improve</span></span>

<span data-ttu-id="23dc2-260">モデルのパフォーマンス スコアが予想ほど良くない場合、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-260">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="23dc2-261">トレーニングの時間を長くします。</span><span class="sxs-lookup"><span data-stu-id="23dc2-261">Train for a longer period of time.</span></span> <span data-ttu-id="23dc2-262">時間を増やせば、自動化された機械学習エンジンは試行するアルゴリズムや設定をそれだけ増やします。</span><span class="sxs-lookup"><span data-stu-id="23dc2-262">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="23dc2-263">データを追加します。</span><span class="sxs-lookup"><span data-stu-id="23dc2-263">Add more data.</span></span> <span data-ttu-id="23dc2-264">高品質の機械学習モデルをトレーニングするにはデータ量が十分ではないことがあります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-264">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="23dc2-265">データのバランスを調整します。</span><span class="sxs-lookup"><span data-stu-id="23dc2-265">Balance your data.</span></span> <span data-ttu-id="23dc2-266">分類タスクの場合、カテゴリ全体でトレーニング セットのバランスが取れていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="23dc2-266">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="23dc2-267">たとえば、100 のトレーニング例に対してクラスが 4 つあるとき、90 個のレコードに最初の 2 つのクラス (tag1 と tag2) を使用するが、残りの 2 つ (tag3 と tag4) は残りの 10 個のレコードでのみ使用する場合、データにバランスが欠け、tag3 か tag4 を正しく予測することがモデルにとって難しくなります。</span><span class="sxs-lookup"><span data-stu-id="23dc2-267">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="23dc2-268">コード</span><span class="sxs-lookup"><span data-stu-id="23dc2-268">Code</span></span>

<span data-ttu-id="23dc2-269">評価フェーズ後、モデル ビルダーからモデル ファイルとコードが出力されます。このコードを使用し、モデルをアプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-269">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="23dc2-270">ML.NET モデルは zip ファイルで保存されます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-270">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="23dc2-271">モデルを読み込み、使用するためのコードがソリューションに新しいプロジェクトとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-271">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="23dc2-272">モデル ビルダーからはサンプル コンソール アプリも追加されます。これを実行すると、実際に動作するモデルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-272">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="23dc2-273">さらに、モデル ビルダーからはモデルを生成したコードが出力されます。モデルの生成に使用された手順を理解できます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-273">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="23dc2-274">モデル トレーニング コードを使用し、モデルを新しいデータで再トレーニングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="23dc2-274">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="23dc2-275">次の内容</span><span class="sxs-lookup"><span data-stu-id="23dc2-275">What's next?</span></span>

<span data-ttu-id="23dc2-276">モデル ビルダーの Visual Studio 拡張機能の[インストール](how-to-guides/install-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="23dc2-276">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="23dc2-277">[価格予測または回帰のシナリオ](tutorials/predict-prices-with-model-builder.md)をお試しください。</span><span class="sxs-lookup"><span data-stu-id="23dc2-277">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
