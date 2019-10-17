---
title: チュートリアル:モデル ビルダーで回帰を使用して価格を予測する
description: このチュートリアルでは、ML.NET モデル ビルダーを使用して、価格 (具体的にはニューヨーク市のタクシー運賃) を予測する回帰モデルを構築する方法を示します。
author: luisquintanilla
ms.author: luquinta
ms.date: 10/08/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a851bf3c405d15243bc1457b8c3dff815d072ebe
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180283"
---
# <a name="tutorial-predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="cd8a4-103">チュートリアル:モデル ビルダーで回帰を使用して価格を予測する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-103">Tutorial: Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="cd8a4-104">ML.NET モデル ビルダーを使用して、価格を予測する回帰モデルを構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-104">Learn how to use ML.NET Model Builder to build a regression model to predict prices.</span></span>  <span data-ttu-id="cd8a4-105">このチュートリアルで開発する .NET コンソール アプリでは、過去のニューヨーク市のタクシー運賃データに基づいてタクシー運賃を予測します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="cd8a4-106">モデル ビルダーの価格予測テンプレートは、数値による予測値を必要とするすべてのシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="cd8a4-107">シナリオの例には、住宅価格の予測、需要予測、売上予測などがあります。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="cd8a4-108">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="cd8a4-109">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="cd8a4-110">シナリオを選択する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-110">Choose a scenario</span></span>
> - <span data-ttu-id="cd8a4-111">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="cd8a4-111">Load the data</span></span>
> - <span data-ttu-id="cd8a4-112">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="cd8a4-112">Train the model</span></span>
> - <span data-ttu-id="cd8a4-113">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-113">Evaluate the model</span></span>
> - <span data-ttu-id="cd8a4-114">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="cd8a4-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="cd8a4-115">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="cd8a4-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="cd8a4-116">Pre-requisites</span></span>

<span data-ttu-id="cd8a4-117">前提条件の一覧とインストール手順は、[モデル ビルダーのインストール ガイド](../how-to-guides/install-model-builder.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="cd8a4-118">コンソール アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="cd8a4-118">Create a console application</span></span>

1. <span data-ttu-id="cd8a4-119">"TaxiFarePrediction" という名前の **.NET Core コンソール アプリケーション**を作成します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="cd8a4-120">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-120">Prepare and understand the data</span></span>

1. <span data-ttu-id="cd8a4-121">プロジェクトに *Data* という名前のディレクトリを作成して、データ セットのファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-121">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="cd8a4-122">機械学習モデルのトレーニングと評価に使用するデータ セットは、NYC TLC Taxi Trip データ セットから取得したものです。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-122">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    1. <span data-ttu-id="cd8a4-123">このデータ セットをダウンロードするには、[taxi-fare-train.csv のダウンロード リンク](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv)に移動します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-123">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    1. <span data-ttu-id="cd8a4-124">ページが読み込まれたら、ページ上の任意の場所を右クリックして、 **[名前を付けて保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-124">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    1. <span data-ttu-id="cd8a4-125">**[名前を付けて保存] ダイアログ**を使って、前の手順で作成した *Data* フォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-125">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="cd8a4-126">**ソリューション エクスプローラー**で、 *[taxi-fare-train.csv]* ファイルを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-126">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="cd8a4-127">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="cd8a4-128">`taxi-fare-train.csv` データ セットの各行に、タクシーの移動の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-128">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="cd8a4-129">**taxi-fare-train.csv** データ セットを開きます</span><span class="sxs-lookup"><span data-stu-id="cd8a4-129">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="cd8a4-130">提供されているデータ セットには、次の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-130">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="cd8a4-131">**vendor_id:** タクシー会社の ID は特徴です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-131">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="cd8a4-132">**rate_code:** タクシー旅行のレートの種類は特徴です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-132">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="cd8a4-133">**passenger_count:** 旅行の乗客数は特徴です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-133">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="cd8a4-134">**trip_time_in_secs:** 旅行の所要時間です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-134">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="cd8a4-135">旅行が終わる前に、旅行の運賃を予測したいと考えます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-135">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="cd8a4-136">その時点では、旅行の所要時間はわかりません。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-136">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="cd8a4-137">したがって、旅行の所要時間は特徴ではなく、この列はモデルから除外します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-137">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    - <span data-ttu-id="cd8a4-138">**trip_distance:** 旅行距離は特徴です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-138">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="cd8a4-139">**payment_type:** 支払い方法 (現金またはクレジット カード) は特徴です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-139">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="cd8a4-140">**fare_amount:** 支払った合計タクシー運賃はラベルです。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-140">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="cd8a4-141">`label` は予測する列です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-141">The `label` is the column you want to predict.</span></span> <span data-ttu-id="cd8a4-142">回帰タスクを実行する場合の目標は、数値を予測することです。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-142">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="cd8a4-143">この価格予測シナリオでは、タクシーの乗車のコストが予測されています。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-143">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="cd8a4-144">したがって、**fare_amount** がラベルです。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-144">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="cd8a4-145">識別された `features` は、`label` を予測するためにモデルを指定する入力です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-145">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="cd8a4-146">この場合、**trip_time_in_secs** を除く残りの列は、料金の合計を予測する特徴または入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-146">In this case, the rest of the columns with the exception of **trip_time_in_secs** are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="cd8a4-147">シナリオを選択する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-147">Choose a scenario</span></span>

<span data-ttu-id="cd8a4-148">モデルをトレーニングするには、モデル ビルダーによって提供される機械学習シナリオの一覧から選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-148">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="cd8a4-149">この場合、シナリオは `Price Prediction` です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-149">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="cd8a4-150">**ソリューション エクスプローラー**で、 *[TaxiFarePrediction]* プロジェクトを右クリックし、 **[追加]**  >  **[機械学習]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-150">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="cd8a4-151">モデル ビルダー ツールのシナリオの手順で、*価格の予測*のシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-151">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="cd8a4-152">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="cd8a4-152">Load the data</span></span>

<span data-ttu-id="cd8a4-153">モデル ビルダーは、SQL Server データベースか、csv または tsv 形式のローカル ファイルという 2 つのソースからデータを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-153">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="cd8a4-154">モデル ビルダー ツールのデータの手順で、データ ソースのドロップダウンから *[ファイル]* を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-154">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="cd8a4-155">*[ファイルの選択]* テキスト ボックスの横にあるボタンを選択し、ファイル エクスプローラーを使用して *Data* ディレクトリにある *[taxi-fare-test.csv]* を参照し、選択します</span><span class="sxs-lookup"><span data-stu-id="cd8a4-155">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="cd8a4-156">*[Column to Predict (Label)]\(予測する列 (ラベル)\)* ドロップダウンにある *[fare_amount]* を選択して、モデル ビルダー ツールのトレーニングの手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-156">Choose *fare_amount* in the *Column to Predict (Label)* dropdown and navigate to the train step of the Model Builder tool.</span></span>
1. <span data-ttu-id="cd8a4-157">*[Input Columns (Features)]\(入力列 (特徴)\)* ドロップダウンを展開し、 *[trip_time_in_secs]* 列をオフにして、トレーニング時の特徴から除外します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-157">Expand the *Input Columns (Features)* dropdown and uncheck the *trip_time_in_secs* column to exclude it as a feature during training.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="cd8a4-158">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="cd8a4-158">Train the model</span></span>

<span data-ttu-id="cd8a4-159">このチュートリアルで、価格予測モデルのトレーニングに使用する機械学習のタスクは、回帰です。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-159">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="cd8a4-160">モデルのトレーニング プロセス中、モデル ビルダーは、さまざまな回帰アルゴリズムと設定を使用して、データセットで最も良いパフォーマンスのモデルを見つける個別のモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-160">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="cd8a4-161">モデルのトレーニングに必要な時間は、データの量に比例します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-161">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="cd8a4-162">モデル ビルダーにより、 **[Time to train (seconds)]\(トレーニング時間 (秒)\)** の既定値が、データ ソースのサイズに基づいて自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-162">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="cd8a4-163">より長い時間トレーニングする場合を除き、 *[Time to train (seconds)]\(トレーニング時間 (秒)\)* は既定値のままとします。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-163">Leave the default value as is for *Time to train (seconds)* unless you prefer to train for a longer time.</span></span>
2. <span data-ttu-id="cd8a4-164">*[Start Training]\(トレーニング開始\)* を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-164">Select *Start Training*.</span></span>

<span data-ttu-id="cd8a4-165">トレーニング プロセスを通して、進捗データがトレーニングの手順の `Progress` セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-165">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="cd8a4-166">状態には、トレーニング プロセスの完了ステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-166">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="cd8a4-167">[Best accuracy]\(最良の精度\) には、これまでにモデル ビルダーで見つかった最良のパフォーマンスのモデルの精度が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-167">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="cd8a4-168">精度が高くなるほど、テスト データでモデルが正確に予測されたことになります。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-168">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="cd8a4-169">[Best algorithm]\(最良のアルゴリズム\) には、これまでにモデル ビルダーで見つかった最良のパフォーマンスのアルゴリズムの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-169">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="cd8a4-170">[Last algorithm]\(最後のアルゴリズム\) には、モデル ビルダーがモデルのトレーニングに最近使用したアルゴリズムの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-170">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="cd8a4-171">トレーニングが完了したら、評価の手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-171">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="cd8a4-172">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-172">Evaluate the model</span></span>

<span data-ttu-id="cd8a4-173">トレーニングの手順の結果が、最良のパフォーマンスだった 1 つのモデルになります。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-173">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="cd8a4-174">モデル ビルダー ツールの評価の手順の出力セクションには、 *[Best Model]\(最良のモデル\)* エントリの最良のパフォーマンスのモデルで使用されたアルゴリズムと、 *[Best Model Quality (RSquared)]\(最良のモデル品質 (RSquared)\)* のメトリックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-174">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="cd8a4-175">また、概要テーブルには上位 5 つのモデルとそのメトリックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-175">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="cd8a4-176">精度のメトリックに不満がある場合、モデルのトレーニング時間を増やすか、さらに多くのデータを使用すると、モデルの精度を簡単に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-176">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="cd8a4-177">そうでない場合は、コードの手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-177">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="cd8a4-178">予測を行うコードを追加する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-178">Add the code to make predictions</span></span>

<span data-ttu-id="cd8a4-179">トレーニング プロセスの結果として 2 つのプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-179">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="cd8a4-180">TaxiFarePredictionML.ConsoleApp: モデルのトレーニングとサンプルの使用に関するコードが含まれる .NET Core コンソール アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-180">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and sample consumption code.</span></span>
- <span data-ttu-id="cd8a4-181">TaxiFarePredictionML.Model: 入力および出力モデル データのスキーマを定義するデータ モデル、トレーニング時にパフォーマンスが最高のモデルの保存バージョン、および予測を行う `ConsumeModel` というヘルパー クラスを含む .NET Standard クラス ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-181">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data, the saved version of the best performing model during training and a helper class called `ConsumeModel` to make predictions.</span></span>

1. <span data-ttu-id="cd8a4-182">モデル ビルダー ツールのコードの手順で、 **[プロジェクトの追加]** を選択して、自動生成されたプロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-182">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="cd8a4-183">*[TaxiFarePrediction]* プロジェクトの *[Program.cs]* ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-183">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="cd8a4-184">*TaxiFarePredictionML.Model* プロジェクトを参照する次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-184">Add the following using statement to reference the *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using TaxiFarePredictionML.Model;
    ```

1. <span data-ttu-id="cd8a4-185">新しいデータに対してモデルを使用して予測を行うには、アプリケーションの `ModelInput` メソッド内に `Main` クラスの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-185">To make a prediction on new data using the model, create a new instance of the `ModelInput` class inside the `Main` method of your application.</span></span> <span data-ttu-id="cd8a4-186">運賃額が入力に含まれていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-186">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="cd8a4-187">これは、モデルによってその予測が生成されるためです。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-187">This is because the model will generate the prediction for it.</span></span> 

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };
    ```

1. <span data-ttu-id="cd8a4-188">`ConsumeModel` クラスの `Predict` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-188">Use the `Predict` method from the `ConsumeModel` class.</span></span> <span data-ttu-id="cd8a4-189">`Predict` メソッドでは、トレーニング済みモデルを読み込み、モデルに対して [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) を作成し、新しいデータに対してそれを使用して予測を行います。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-189">The `Predict` method loads the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and uses it to make predictions on new data.</span></span> 

    ```csharp
    // Make prediction
    ModelOutput prediction = ConsumeModel.Predict(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

1. <span data-ttu-id="cd8a4-190">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-190">Run the application.</span></span>

    <span data-ttu-id="cd8a4-191">プログラムによって生成される出力は次のスニペットのようになります。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-191">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 14.96086
    ```

<span data-ttu-id="cd8a4-192">別のソリューション内で後で生成されたプロジェクトを参照する必要がある場合は、`C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` ディレクトリを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-192">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cd8a4-193">次の手順</span><span class="sxs-lookup"><span data-stu-id="cd8a4-193">Next Steps</span></span>

<span data-ttu-id="cd8a4-194">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-194">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="cd8a4-195">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-195">Prepare and understand the data</span></span>
> - <span data-ttu-id="cd8a4-196">シナリオを選択する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-196">Choose a scenario</span></span>
> - <span data-ttu-id="cd8a4-197">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="cd8a4-197">Load the data</span></span>
> - <span data-ttu-id="cd8a4-198">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="cd8a4-198">Train the model</span></span>
> - <span data-ttu-id="cd8a4-199">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="cd8a4-199">Evaluate the model</span></span>
> - <span data-ttu-id="cd8a4-200">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="cd8a4-200">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="cd8a4-201">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="cd8a4-201">Additional Resources</span></span>

<span data-ttu-id="cd8a4-202">このチュートリアルで説明しているトピックについて詳しくは、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd8a4-202">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="cd8a4-203">モデル ビルダーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="cd8a4-203">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- <span data-ttu-id="cd8a4-204">[Regression](../resources/glossary.md#regression) (回帰)</span><span class="sxs-lookup"><span data-stu-id="cd8a4-204">[Regression](../resources/glossary.md#regression)</span></span>
- [<span data-ttu-id="cd8a4-205">回帰モデルのメトリック</span><span class="sxs-lookup"><span data-stu-id="cd8a4-205">Regression Model Metrics</span></span>](../resources/metrics.md#metrics-for-regression)
- [<span data-ttu-id="cd8a4-206">NYC TLC Taxi Trip データ セット</span><span class="sxs-lookup"><span data-stu-id="cd8a4-206">NYC TLC Taxi Trip data set</span></span>](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)
