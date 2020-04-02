---
title: モデル ビルダーの概要としくみ
description: ML.NET モデル ビルダーを使用し、機械学習モデルを自動的にトレーニングする方法
ms.date: 03/25/2020
ms.custom: overview, mlnet-tooling
ms.openlocfilehash: 9cf66455109908ebd9fc10e62cf4f067609b57d9
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344781"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="d9ad3-103">モデル ビルダーの概要としくみ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="d9ad3-104">ML.NET モデル ビルダーは、直観的なグラフィックスでカスタムの機械学習モデルを構築、トレーニング、展開できる Visual Studio 拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="d9ad3-105">モデル ビルダーでは自動化された機械学習 (AutoML) を利用してさまざまな機械学習のアルゴリズムや設定を見つけます。自分のシナリオに最適なものを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="d9ad3-106">モデル ビルダーは機械学習の専門知識がなくても使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="d9ad3-107">必要なものはいくつかのデータと解決すべき問題です。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="d9ad3-108">モデル ビルダーでは、.NET アプリケーションにモデルを追加するコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![モデル ビルダー Visual Studio 拡張機能のユーザー インターフェイスのアニメーション](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="d9ad3-110">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-110">Model Builder is currently in Preview.</span></span>

## <a name="scenario"></a><span data-ttu-id="d9ad3-111">シナリオ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-111">Scenario</span></span>

<span data-ttu-id="d9ad3-112">さまざまなシナリオをモデル ビルダーに取り込み、自分のアプリケーションのための機械学習モデルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="d9ad3-113">シナリオは、自分のデータを使用して行う予測の種類を説明するものです。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="d9ad3-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-114">For example:</span></span>

- <span data-ttu-id="d9ad3-115">過去の販売データに基づいて今後の製品売上高を予測する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="d9ad3-116">顧客のレビューに基づいてセンチメントを肯定的と否定的に分類する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="d9ad3-117">銀行取引が詐欺かどうかを検出する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="d9ad3-118">顧客がフィードバックした問題を社内の該当チームに送信する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-118">route customer feedback issues to the correct team in your company</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="d9ad3-119">自分に最適な機械学習シナリオとは?</span><span class="sxs-lookup"><span data-stu-id="d9ad3-119">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="d9ad3-120">モデル ビルダーでは、シナリオを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-120">In Model Builder, you need to select a scenario.</span></span> <span data-ttu-id="d9ad3-121">シナリオの種類は、行おうとしている予測の種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-121">The type of scenario depends on what type of prediction you are trying to make.</span></span>

#### <a name="text-classification"></a><span data-ttu-id="d9ad3-122">テキスト分類</span><span class="sxs-lookup"><span data-stu-id="d9ad3-122">Text classification</span></span>

<span data-ttu-id="d9ad3-123">分類は、データをカテゴリに分類するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-123">Classification is used to categorize data into categories.</span></span>

![不正検出、リスク軽減、アプリケーション スクリーニングなど、二項分類の例を示す図](media/binary-classification-examples.png)

![ドキュメントと製品の分類、サポート チケットのルーティング、顧客の問題の優先度設定など、多クラス分類の例](media/multiclass-classification-examples.png)

#### <a name="value-prediction"></a><span data-ttu-id="d9ad3-126">値の予測</span><span class="sxs-lookup"><span data-stu-id="d9ad3-126">Value prediction</span></span>

<span data-ttu-id="d9ad3-127">回帰は、数値を予測する目的で利用されます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-127">Regression is used to predict numbers.</span></span>

![価格予測、売上予測、予測メンテナンスなどの回帰の例を示す図](media/regression-examples.png)

#### <a name="image-classification"></a><span data-ttu-id="d9ad3-129">イメージ分類</span><span class="sxs-lookup"><span data-stu-id="d9ad3-129">Image classification</span></span>

<span data-ttu-id="d9ad3-130">イメージ分類を使用すると、さまざまなカテゴリのイメージを特定できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-130">Image classification can be used to identify images of different categories.</span></span> <span data-ttu-id="d9ad3-131">これには、さまざまな種類の地形、動物、製造上の不具合などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-131">For example, different types of terrain or animals or manufacturing defects.</span></span>

<span data-ttu-id="d9ad3-132">一連のイメージがあり、イメージをさまざまなカテゴリに分類したいときは、イメージ分類シナリオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-132">You can use the image classification scenario if you have a set of images, and you want to classify the images into different categories.</span></span>

#### <a name="recommendation"></a><span data-ttu-id="d9ad3-133">推奨事項</span><span class="sxs-lookup"><span data-stu-id="d9ad3-133">Recommendation</span></span>

<span data-ttu-id="d9ad3-134">推奨事項シナリオでは、他のユーザーとの好きや嫌いの類似度に基づいて、特定のユーザーに対する提案項目の一覧が予測されます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-134">The recommendation scenario predicts a list of suggested items for a particular user, based on how similar their likes and dislikes are to other users'.</span></span>

<span data-ttu-id="d9ad3-135">ユーザーのセットと、"製品" のセット (購入する品目、映画、本、テレビ番組など)、およびそれらの製品に対するユーザーの "評価" のセットがある場合は、推奨事項シナリオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-135">You can use the recommendation scenario when you have a set of users and a set of "products", such as items to purchase, movies, books, or TV shows, along with a set of users' "ratings" of those products.</span></span>

## <a name="environment"></a><span data-ttu-id="d9ad3-136">環境</span><span class="sxs-lookup"><span data-stu-id="d9ad3-136">Environment</span></span>

<span data-ttu-id="d9ad3-137">お使いのコンピューター上のローカル環境で、または Azure 上のクラウドで、機械学習モデルをトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-137">You can train your machine learning model locally on your machine or in the cloud on Azure.</span></span>

<span data-ttu-id="d9ad3-138">ローカル環境でトレーニングする場合は、コンピューター リソース (CPU、メモリ、ディスク) の制約内で作業します。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-138">When you train locally, you work within the constraints of your computer resources (CPU, memory, and disk).</span></span> <span data-ttu-id="d9ad3-139">クラウドでトレーニングする場合は、シナリオのニーズに合わせて、リソースをスケールアップできます (特に大規模なデータセット)。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-139">When you train in the cloud, you can scale up your resources to meet the demands of your scenario, especially for large datasets.</span></span>

<span data-ttu-id="d9ad3-140">ローカル トレーニングは、すべてのシナリオでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-140">Local training is supported for all scenarios.</span></span>

<span data-ttu-id="d9ad3-141">Azure トレーニングは、イメージ分類でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-141">Azure training is supported for Image Classification.</span></span>

## <a name="data"></a><span data-ttu-id="d9ad3-142">データ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-142">Data</span></span>

<span data-ttu-id="d9ad3-143">シナリオを選択すると、モデル ビルダーからデータセットを提供するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-143">Once you have chosen your scenario, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="d9ad3-144">このデータはモデルをトレーニングし、評価し、シナリオに最適なモデルを選択するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-144">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![モデル ビルダーの手順を示す図](media/model-builder-steps.png)

<span data-ttu-id="d9ad3-146">モデル ビルダーは、.tsv、.csv、.txt 形式のデータセットと、SQL データベース形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-146">Model Builder supports datasets in .tsv, .csv, .txt formats, as well as SQL database format.</span></span> <span data-ttu-id="d9ad3-147">.txt ファイルがある場合、列は `,`、`;`、または `/t` で区切る必要があり、ファイルにはヘッダー行が必要です。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-147">If you have a .txt file, columns should be separated with `,`, `;` or `/t` and the file must have a header row.</span></span>

<span data-ttu-id="d9ad3-148">データセットがイメージで構成されている場合、サポートされているファイルの種類は `.jpg` と `.png`です。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-148">If the dataset is made up of images, the supported file types are `.jpg` and `.png`.</span></span>

<span data-ttu-id="d9ad3-149">詳細については、「[モデル ビルダーにトレーニング データを読み込む](how-to-guides/load-data-model-builder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-149">For more information, see [Load training data into Model Builder](how-to-guides/load-data-model-builder.md).</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="d9ad3-150">予測する出力を選択します (ラベル)</span><span class="sxs-lookup"><span data-stu-id="d9ad3-150">Choose the output to predict (label)</span></span>

<span data-ttu-id="d9ad3-151">データセットは、トレーニング サンプルの行と属性の列からなるテーブルです。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-151">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="d9ad3-152">各行の内容:</span><span class="sxs-lookup"><span data-stu-id="d9ad3-152">Each row has:</span></span>

- <span data-ttu-id="d9ad3-153">**ラベル** (予測する属性)</span><span class="sxs-lookup"><span data-stu-id="d9ad3-153">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="d9ad3-154">**特徴** (ラベルを予測するための入力として使用される属性)。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-154">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="d9ad3-155">家の価格予測シナリオの場合、特徴は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-155">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="d9ad3-156">家の面積</span><span class="sxs-lookup"><span data-stu-id="d9ad3-156">the square footage of the house</span></span>
- <span data-ttu-id="d9ad3-157">寝室と浴室の数</span><span class="sxs-lookup"><span data-stu-id="d9ad3-157">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="d9ad3-158">郵便番号</span><span class="sxs-lookup"><span data-stu-id="d9ad3-158">the zip code</span></span>

<span data-ttu-id="d9ad3-159">ラベルは、面積、寝室数、浴室数、郵便番号からなるその行の過去の住宅価格です。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-159">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![サイズ、部屋数、郵便番号、価格ラベルから構成される特徴を持つ住宅価格データからなる行と列を示す表](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="d9ad3-161">データセットの例</span><span class="sxs-lookup"><span data-stu-id="d9ad3-161">Example datasets</span></span>

<span data-ttu-id="d9ad3-162">独自のデータをまだ用意していない場合、次のいずれかのデータセットをお試しください。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-162">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="d9ad3-163">シナリオ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-163">Scenario</span></span>|<span data-ttu-id="d9ad3-164">例</span><span class="sxs-lookup"><span data-stu-id="d9ad3-164">Example</span></span>|<span data-ttu-id="d9ad3-165">データ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-165">Data</span></span>|<span data-ttu-id="d9ad3-166">group1</span><span class="sxs-lookup"><span data-stu-id="d9ad3-166">Label</span></span>|<span data-ttu-id="d9ad3-167">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="d9ad3-167">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="d9ad3-168">分類</span><span class="sxs-lookup"><span data-stu-id="d9ad3-168">Classification</span></span>|<span data-ttu-id="d9ad3-169">売上の異常を予測する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-169">Predict sales anomalies</span></span>|[<span data-ttu-id="d9ad3-170">製品の売上データ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-170">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="d9ad3-171">製品の売上</span><span class="sxs-lookup"><span data-stu-id="d9ad3-171">Product Sales</span></span>|<span data-ttu-id="d9ad3-172">月</span><span class="sxs-lookup"><span data-stu-id="d9ad3-172">Month</span></span>|
||<span data-ttu-id="d9ad3-173">Web サイトのコメントのセンチメントを予測する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-173">Predict sentiment of website comments</span></span>|[<span data-ttu-id="d9ad3-174">Web サイトのコメント データ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-174">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="d9ad3-175">ラベル (否定的なセンチメントのときは 0、肯定的なセンチメントのときは 1)</span><span class="sxs-lookup"><span data-stu-id="d9ad3-175">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="d9ad3-176">コメント、年度</span><span class="sxs-lookup"><span data-stu-id="d9ad3-176">Comment, Year</span></span>|
||<span data-ttu-id="d9ad3-177">クレジット カード取引の詐欺を予測する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-177">Predict fraudulent credit card transactions</span></span>|[<span data-ttu-id="d9ad3-178">クレジット カードのデータ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-178">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="d9ad3-179">クラス (詐欺の場合は 1、それ以外の場合 0)</span><span class="sxs-lookup"><span data-stu-id="d9ad3-179">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="d9ad3-180">金額、V1-V28 (匿名化された特徴)</span><span class="sxs-lookup"><span data-stu-id="d9ad3-180">Amount, V1-V28 (anonymized features)</span></span>|
||<span data-ttu-id="d9ad3-181">GitHub リポジトリでのイシューの種類を予測する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-181">Predict the type of issue in a GitHub repository</span></span>|[<span data-ttu-id="d9ad3-182">GitHub 問題のデータ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-182">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="d9ad3-183">区分</span><span class="sxs-lookup"><span data-stu-id="d9ad3-183">Area</span></span>|<span data-ttu-id="d9ad3-184">タイトル、説明</span><span class="sxs-lookup"><span data-stu-id="d9ad3-184">Title, Description</span></span>|
|<span data-ttu-id="d9ad3-185">値の予測</span><span class="sxs-lookup"><span data-stu-id="d9ad3-185">Value prediction</span></span>|<span data-ttu-id="d9ad3-186">タクシー料金を予測する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-186">Predict taxi fare price</span></span>|[<span data-ttu-id="d9ad3-187">タクシーの料金データ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-187">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="d9ad3-188">料金</span><span class="sxs-lookup"><span data-stu-id="d9ad3-188">Fare</span></span>|<span data-ttu-id="d9ad3-189">乗車時間、距離</span><span class="sxs-lookup"><span data-stu-id="d9ad3-189">Trip time, distance</span></span>|
|<span data-ttu-id="d9ad3-190">イメージ分類</span><span class="sxs-lookup"><span data-stu-id="d9ad3-190">Image classification</span></span>|<span data-ttu-id="d9ad3-191">イシューのカテゴリを予測する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-191">Predict the category of an issue</span></span>|[<span data-ttu-id="d9ad3-192">花の画像</span><span class="sxs-lookup"><span data-stu-id="d9ad3-192">flower images</span></span>](http://download.tensorflow.org/example_images/flower_photos.tgz)|<span data-ttu-id="d9ad3-193">花の種類: デイジー、タンポポ、バラ、ヒマワリ、チューリップ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-193">The type of flower: daisy, dandelion, roses, sunflowers, tulips</span></span>|<span data-ttu-id="d9ad3-194">イメージ データ自体</span><span class="sxs-lookup"><span data-stu-id="d9ad3-194">The image data itself</span></span>|
|<span data-ttu-id="d9ad3-195">推奨事項</span><span class="sxs-lookup"><span data-stu-id="d9ad3-195">Recommendation</span></span>|<span data-ttu-id="d9ad3-196">好きな映画を予測する</span><span class="sxs-lookup"><span data-stu-id="d9ad3-196">Predict movies that someone will like</span></span>|[<span data-ttu-id="d9ad3-197">映画の評価</span><span class="sxs-lookup"><span data-stu-id="d9ad3-197">movie ratings</span></span>](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip)|<span data-ttu-id="d9ad3-198">ユーザー、映画</span><span class="sxs-lookup"><span data-stu-id="d9ad3-198">Users, Movies</span></span>|<span data-ttu-id="d9ad3-199">評価</span><span class="sxs-lookup"><span data-stu-id="d9ad3-199">Ratings</span></span>|

## <a name="train"></a><span data-ttu-id="d9ad3-200">トレーニング</span><span class="sxs-lookup"><span data-stu-id="d9ad3-200">Train</span></span>

<span data-ttu-id="d9ad3-201">シナリオ、データ、ラベルを選択すると、モデル ビルダーによってモデルがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-201">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="d9ad3-202">トレーニングとは何か?</span><span class="sxs-lookup"><span data-stu-id="d9ad3-202">What is training?</span></span>

<span data-ttu-id="d9ad3-203">トレーニングとは、モデル ビルダーがシナリオの質問に対する回答方法をモデルに教える自動プロセスです。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-203">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="d9ad3-204">トレーニングが終わると、モデルは以前に見たことがない入力データで予測できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-204">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="d9ad3-205">たとえば、住宅価格を予測しているなら、新しい住宅が市場に出たとき、その販売価格を予測できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-205">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="d9ad3-206">モデル ビルダーで使用される機械学習は自動化されているため (AutoML)、トレーニング中に、ユーザーが入力したり、調整したりする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-206">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="d9ad3-207">どのくらいの時間、トレーニングしますか?</span><span class="sxs-lookup"><span data-stu-id="d9ad3-207">How long should I train for?</span></span>

<span data-ttu-id="d9ad3-208">モデル ビルダーは、AutoML を使用して複数のモデルを探索し、最適なパフォーマンスを発揮するモデルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-208">Model Builder uses AutoML to explore multiple models to find you the best performing model.</span></span>

<span data-ttu-id="d9ad3-209">トレーニング期間を長くすると、AutoML はより広い設定範囲でさらに多くのモデルを探索できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-209">Longer training periods allow AutoML to explore more models with a wider range of settings.</span></span>

<span data-ttu-id="d9ad3-210">以下の表は、ローカル コンピューターにある一連のサンプル データセットで、優れたパフォーマンスを得るのに要した平均時間を示しています。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-210">The table below summarizes the average time taken to get good performance for a suite of example datasets, on a local machine.</span></span>

|<span data-ttu-id="d9ad3-211">データセットのサイズ</span><span class="sxs-lookup"><span data-stu-id="d9ad3-211">Dataset size</span></span>|<span data-ttu-id="d9ad3-212">トレーニングの平均時間</span><span class="sxs-lookup"><span data-stu-id="d9ad3-212">Average time to train</span></span>|
|------------|---------------------|
|<span data-ttu-id="d9ad3-213">0 - 10 MB</span><span class="sxs-lookup"><span data-stu-id="d9ad3-213">0 - 10 MB</span></span>|<span data-ttu-id="d9ad3-214">10 秒</span><span class="sxs-lookup"><span data-stu-id="d9ad3-214">10 sec</span></span>|
|<span data-ttu-id="d9ad3-215">10 - 100 MB</span><span class="sxs-lookup"><span data-stu-id="d9ad3-215">10 - 100 MB</span></span>|<span data-ttu-id="d9ad3-216">10 分</span><span class="sxs-lookup"><span data-stu-id="d9ad3-216">10 min</span></span>|
|<span data-ttu-id="d9ad3-217">100 - 500 MB</span><span class="sxs-lookup"><span data-stu-id="d9ad3-217">100 - 500 MB</span></span>|<span data-ttu-id="d9ad3-218">30 分</span><span class="sxs-lookup"><span data-stu-id="d9ad3-218">30 min</span></span>|
|<span data-ttu-id="d9ad3-219">500 MB - 1 GB</span><span class="sxs-lookup"><span data-stu-id="d9ad3-219">500 - 1 GB</span></span>|<span data-ttu-id="d9ad3-220">60 分</span><span class="sxs-lookup"><span data-stu-id="d9ad3-220">60 min</span></span>|
|<span data-ttu-id="d9ad3-221">1 GB 超</span><span class="sxs-lookup"><span data-stu-id="d9ad3-221">1 GB+</span></span>|<span data-ttu-id="d9ad3-222">3 時間超</span><span class="sxs-lookup"><span data-stu-id="d9ad3-222">3+ hours</span></span>|

<span data-ttu-id="d9ad3-223">これらは参考用の数字に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-223">These numbers are a guide only.</span></span> <span data-ttu-id="d9ad3-224">トレーニングの正確な長さは、次の条件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-224">The exact length of training is dependent on:</span></span>

- <span data-ttu-id="d9ad3-225">モデルへの入力として使用されている特徴 (列) の数</span><span class="sxs-lookup"><span data-stu-id="d9ad3-225">the number of features (columns) being used to as input to the model</span></span>
- <span data-ttu-id="d9ad3-226">列の種類</span><span class="sxs-lookup"><span data-stu-id="d9ad3-226">the type of columns</span></span>
- <span data-ttu-id="d9ad3-227">ML タスク</span><span class="sxs-lookup"><span data-stu-id="d9ad3-227">the ML task</span></span>
- <span data-ttu-id="d9ad3-228">トレーニングに使用されるマシンの CPU、ディスク、およびメモリのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="d9ad3-228">the CPU, disk, and memory performance of the machine used for training</span></span>

## <a name="evaluate"></a><span data-ttu-id="d9ad3-229">評価</span><span class="sxs-lookup"><span data-stu-id="d9ad3-229">Evaluate</span></span>

<span data-ttu-id="d9ad3-230">評価は、モデルがどのくらい適切かを測定するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-230">Evaluation is the process of measuring how good your model is.</span></span> <span data-ttu-id="d9ad3-231">モデル ビルダーは、トレーニングしたモデルを使用して新しいテスト データで予測し、予測の精度を測定します。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-231">Model Builder uses the trained model to make predictions with new test data, and then measures how good the predictions are.</span></span>

<span data-ttu-id="d9ad3-232">モデル ビルダーでは、トレーニング セットとテスト セットにトレーニング データが分割されます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-232">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="d9ad3-233">トレーニング データ (80%) はモデルのトレーニングに使用されます。テスト データ (20%) はモデルの評価のための控えとなります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-233">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span>

### <a name="how-do-i-understand-my-model-performance"></a><span data-ttu-id="d9ad3-234">モデルのパフォーマンスを把握するには</span><span class="sxs-lookup"><span data-stu-id="d9ad3-234">How do I understand my model performance?</span></span>

<span data-ttu-id="d9ad3-235">シナリオが機械学習タスクにマップされます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-235">A scenario maps to a machine learning task.</span></span> <span data-ttu-id="d9ad3-236">各 ML タスクには、独自の評価メトリック セットがあります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-236">Each ML task has its own set of evaluation metrics.</span></span>

#### <a name="value-prediction"></a><span data-ttu-id="d9ad3-237">値の予測</span><span class="sxs-lookup"><span data-stu-id="d9ad3-237">Value prediction</span></span>

<span data-ttu-id="d9ad3-238">値の予測問題の既定のメトリックは RSquared で、RSquared の値の範囲は 0 から 1 です。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-238">The default metric for value prediction problems is RSquared, the value of RSquared ranges between 0 and 1.</span></span> <span data-ttu-id="d9ad3-239">最適な値は 1 です。つまり、RSquared の値が 1 に近いほど、モデルのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-239">1 is the best possible value or in other words the closer the value of RSquared to 1 the better your model is performing.</span></span>

<span data-ttu-id="d9ad3-240">絶対損失、二乗損失、RMS 損失など、報告されるその他のメトリックは追加メトリックで、モデルのパフォーマンスを理解し、それを他の値の予測モデルと比較する目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-240">Other metrics reported such as absolute-loss, squared-loss, and RMS loss are additional metrics, which can be used to understand how your model is performing and comparing it against other value prediction models.</span></span>

#### <a name="classification-2-categories"></a><span data-ttu-id="d9ad3-241">分類 (2 つのカテゴリ)</span><span class="sxs-lookup"><span data-stu-id="d9ad3-241">Classification (2 categories)</span></span>

<span data-ttu-id="d9ad3-242">分類問題の既定のメトリックは正確度です。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-242">The default metric for classification problems is accuracy.</span></span> <span data-ttu-id="d9ad3-243">正確度は、テスト データセットに基づいてモデルが正しく予測する比率を定めるものです。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-243">Accuracy defines the proportion of correct predictions your model is making over the test dataset.</span></span> <span data-ttu-id="d9ad3-244">100%、つまり 1.0 に近ければ近いほど、良いということになります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-244">The closer to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="d9ad3-245">真陽性率と擬陽性率を測定する AUC (曲線下面積) など、報告されるその他のメトリックは 0.50 以上であれば、モデルは許容されます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-245">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate should be greater than 0.50 for models to be acceptable.</span></span>

<span data-ttu-id="d9ad3-246">F1 スコアなどの追加メトリックを使用すると、精度と再現率のバランスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-246">Additional metrics like F1 score can be used to control the balance between Precision and Recall.</span></span>

#### <a name="classification-3-categories"></a><span data-ttu-id="d9ad3-247">分類 (3 つ以上のカテゴリ)</span><span class="sxs-lookup"><span data-stu-id="d9ad3-247">Classification (3+ categories)</span></span>

<span data-ttu-id="d9ad3-248">多クラス分類の既定のメトリックはマイクロ正確度です。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-248">The default metric for Multi-class classification is Micro Accuracy.</span></span> <span data-ttu-id="d9ad3-249">マイクロ正確度が 100%、つまり 1.0 に近ければ近いほど、良いということになります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-249">The closer the Micro Accuracy to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="d9ad3-250">多クラス分類のもう 1 つの重要なメトリックはマクロ正確度です。マイクロ正確度と同様、1.0 に近いほど良いことになります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-250">Another important metric for Multi-class classification is Macro-accuracy, similar to Micro-accuracy the closer to 1.0 the better it is.</span></span> <span data-ttu-id="d9ad3-251">これらの 2 種類の正確度は次のように考えるとよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-251">A good way to think about these two types of accuracy is:</span></span>

- <span data-ttu-id="d9ad3-252">マイクロ正確度: 受信チケットが、どのくらいの頻度で適切なチームに分類されるか。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-252">Micro-accuracy: How often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="d9ad3-253">マクロ正確度: 平均的なチームが受け取るチケットが、そのチームにとって適切である頻度はどのくらいか。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-253">Macro-accuracy: For an average team, how often is an incoming ticket correct for their team?</span></span>

### <a name="more-information-on-evaluation-metrics"></a><span data-ttu-id="d9ad3-254">評価メトリックの詳細</span><span class="sxs-lookup"><span data-stu-id="d9ad3-254">More information on evaluation metrics</span></span>

<span data-ttu-id="d9ad3-255">詳しくは、[モデルの評価メトリック](resources/metrics.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-255">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="d9ad3-256">改善</span><span class="sxs-lookup"><span data-stu-id="d9ad3-256">Improve</span></span>

<span data-ttu-id="d9ad3-257">モデルのパフォーマンス スコアが予想ほど良くない場合、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-257">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="d9ad3-258">トレーニングの時間を長くします。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-258">Train for a longer period of time.</span></span> <span data-ttu-id="d9ad3-259">時間を増やせば、自動化された機械学習エンジンによって実験されるアルゴリズムや設定が増えます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-259">With more time, the automated machine learning engine experiments with more algorithms and settings.</span></span>

- <span data-ttu-id="d9ad3-260">データを追加します。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-260">Add more data.</span></span> <span data-ttu-id="d9ad3-261">高品質の機械学習モデルをトレーニングするにはデータ量が十分ではないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-261">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="d9ad3-262">データのバランスを調整します。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-262">Balance your data.</span></span> <span data-ttu-id="d9ad3-263">分類タスクの場合、カテゴリ全体でトレーニング セットのバランスが取れていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-263">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="d9ad3-264">たとえば、100 のトレーニング例に対してクラスが 4 つあるとき、90 個のレコードに最初の 2 つのクラス (tag1 と tag2) を使用するが、残りの 2 つ (tag3 と tag4) は残りの 10 個のレコードでのみ使用する場合、データにバランスが欠け、tag3 か tag4 を正しく予測することがモデルにとって難しくなります。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-264">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="d9ad3-265">コード</span><span class="sxs-lookup"><span data-stu-id="d9ad3-265">Code</span></span>

<span data-ttu-id="d9ad3-266">評価フェーズ後、モデル ビルダーからモデル ファイルとコードが出力されます。このコードを使用し、モデルをアプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-266">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="d9ad3-267">ML.NET モデルは zip ファイルで保存されます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-267">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="d9ad3-268">モデルを読み込み、使用するためのコードがソリューションに新しいプロジェクトとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-268">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="d9ad3-269">モデル ビルダーからはサンプル コンソール アプリも追加されます。これを実行すると、実際に動作するモデルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-269">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="d9ad3-270">さらに、モデル ビルダーからはモデルを生成したコードが出力されます。モデルの生成に使用された手順を理解できます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-270">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="d9ad3-271">モデル トレーニング コードを使用し、モデルを新しいデータで再トレーニングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-271">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="d9ad3-272">次の内容</span><span class="sxs-lookup"><span data-stu-id="d9ad3-272">What's next?</span></span>

<span data-ttu-id="d9ad3-273">モデル ビルダーの Visual Studio 拡張機能の[インストール](how-to-guides/install-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="d9ad3-273">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="d9ad3-274">[価格予測または回帰のシナリオ](tutorials/predict-prices-with-model-builder.md)をお試しください。</span><span class="sxs-lookup"><span data-stu-id="d9ad3-274">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
