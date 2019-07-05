---
title: モデル ビルダーで回帰を使用して価格を予測する
description: このチュートリアルでは、ML.NET モデル ビルダーを使用して、価格 (具体的にはニューヨーク市のタクシー運賃) を予測する回帰モデルを構築する方法を示します。
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: db9788e3065a0f2f21d712b2d4826efea2d8a829
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410580"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="f19ab-103">モデル ビルダーで回帰を使用して価格を予測する</span><span class="sxs-lookup"><span data-stu-id="f19ab-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="f19ab-104">ML.NET モデル ビルダーを使用して、価格を予測する[回帰モデル](../resources/glossary.md#regression)を構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-104">Learn how to use ML.NET Model Builder to build a [regression model](../resources/glossary.md#regression) to predict prices.</span></span>  <span data-ttu-id="f19ab-105">このチュートリアルで開発する .NET コンソール アプリでは、過去のニューヨーク市のタクシー運賃データに基づいてタクシー運賃を予測します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="f19ab-106">モデル ビルダーの価格予測テンプレートは、数値による予測値を必要とするすべてのシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="f19ab-107">シナリオの例には、住宅価格の予測、需要予測、売上予測などがあります。</span><span class="sxs-lookup"><span data-stu-id="f19ab-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="f19ab-108">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f19ab-109">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="f19ab-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="f19ab-110">シナリオを選択する</span><span class="sxs-lookup"><span data-stu-id="f19ab-110">Choose a scenario</span></span>
> * <span data-ttu-id="f19ab-111">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="f19ab-111">Load the data</span></span>
> * <span data-ttu-id="f19ab-112">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="f19ab-112">Train the model</span></span>
> * <span data-ttu-id="f19ab-113">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="f19ab-113">Evaluate the model</span></span>
> * <span data-ttu-id="f19ab-114">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="f19ab-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="f19ab-115">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="f19ab-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="f19ab-116">Pre-requisites</span></span>

<span data-ttu-id="f19ab-117">前提条件の一覧とインストール手順は、[モデル ビルダーのインストール ガイド](../how-to-guides/install-model-builder.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f19ab-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f19ab-118">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="f19ab-118">Create a console application</span></span>

1. <span data-ttu-id="f19ab-119">"TaxiFarePrediction" という名前の **.NET Core コンソール アプリケーション**を作成します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="f19ab-120">**Microsoft.ML** NuGet パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f19ab-120">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="f19ab-121">**ソリューション エクスプローラー**で、 *[TaxiFarePrediction]* プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-121">In **Solution Explorer**, right-click the *TaxiFarePrediction* project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f19ab-122">[パッケージ ソース] として [nuget.org] を選択します。 **[参照]** タブを選択し、「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-122">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f19ab-123">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="f19ab-124">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="f19ab-124">Prepare and understand the data</span></span>

1. <span data-ttu-id="f19ab-125">プロジェクトに *Data* という名前のディレクトリを作成して、データ セットのファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-125">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="f19ab-126">[taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) データ セットをダウンロードし、前の手順で作成した *Data* フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-126">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) data set and save it to the *Data* folder you created at the previous step.</span></span> <span data-ttu-id="f19ab-127">このデータ セットは、機械学習モデルのトレーニングと評価に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-127">This data set is used to train and evaluate the machine learning model.</span></span> <span data-ttu-id="f19ab-128">このデータ セットは、[NYC TLC Taxi Trip データ セット](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)から取得したものです。</span><span class="sxs-lookup"><span data-stu-id="f19ab-128">This data set is originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="f19ab-129">**ソリューション エクスプローラー**で、 *[taxi-fare-train.csv]* ファイルを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-129">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="f19ab-130">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-130">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="f19ab-131">`taxi-fare-train.csv` データ セットの各行に、タクシーの移動の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f19ab-131">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span> 

1. <span data-ttu-id="f19ab-132">**taxi-fare-train.csv** データ セットを開きます</span><span class="sxs-lookup"><span data-stu-id="f19ab-132">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="f19ab-133">提供されているデータ セットには、次の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-133">The provided data set contains the following columns:</span></span>

    * <span data-ttu-id="f19ab-134">**vendor_id:** タクシー会社の ID は特徴です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    * <span data-ttu-id="f19ab-135">**rate_code:** タクシー旅行のレートの種類は特徴です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    * <span data-ttu-id="f19ab-136">**passenger_count:** 旅行の乗客数は特徴です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    * <span data-ttu-id="f19ab-137">**trip_time_in_secs:** 旅行の所要時間です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="f19ab-138">旅行が終わる前に、旅行の運賃を予測したいと考えます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="f19ab-139">その時点では、旅行の所要時間はわかりません。</span><span class="sxs-lookup"><span data-stu-id="f19ab-139">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="f19ab-140">したがって、旅行の所要時間は特徴ではなく、この列はモデルから除外します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    * <span data-ttu-id="f19ab-141">**trip_distance:** 旅行距離は特徴です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-141">**trip_distance:** The distance of the trip is a feature.</span></span>
    * <span data-ttu-id="f19ab-142">**payment_type:** 支払い方法 (現金またはクレジット カード) は特徴です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    * <span data-ttu-id="f19ab-143">**fare_amount:** 支払った合計タクシー運賃はラベルです。</span><span class="sxs-lookup"><span data-stu-id="f19ab-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="f19ab-144">`label` は予測する列です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-144">The `label` is the column you want to predict.</span></span> <span data-ttu-id="f19ab-145">回帰タスクを実行する場合の目標は、数値を予測することです。</span><span class="sxs-lookup"><span data-stu-id="f19ab-145">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="f19ab-146">この価格予測シナリオでは、タクシーの乗車のコストが予測されています。</span><span class="sxs-lookup"><span data-stu-id="f19ab-146">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="f19ab-147">したがって、**fare_amount** がラベルです。</span><span class="sxs-lookup"><span data-stu-id="f19ab-147">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="f19ab-148">識別された `features` は、`label` を予測するためにモデルを指定する入力です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-148">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="f19ab-149">この場合、残りの列は、運賃の金額を予測するための機能または入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-149">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="f19ab-150">シナリオを選択する</span><span class="sxs-lookup"><span data-stu-id="f19ab-150">Choose a scenario</span></span>

<span data-ttu-id="f19ab-151">モデルをトレーニングするには、モデル ビルダーによって提供される機械学習シナリオの一覧から選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f19ab-151">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="f19ab-152">この場合、シナリオは `Price Prediction` です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-152">In this case, the scenario is `Price Prediction`.</span></span> <span data-ttu-id="f19ab-153">より広範な一覧については、[モデル ビルダーの概要記事](../automate-training-with-model-builder.md#scenarios)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f19ab-153">For a more extensive list visit the [Model Builder overview article](../automate-training-with-model-builder.md#scenarios).</span></span>

1. <span data-ttu-id="f19ab-154">**ソリューション エクスプローラー**で、 *[TaxiFarePrediction]* プロジェクトを右クリックし、 **[追加]**  >  **[機械学習]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-154">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="f19ab-155">モデル ビルダー ツールのシナリオの手順で、*価格の予測*のシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-155">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="f19ab-156">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="f19ab-156">Load the data</span></span>

<span data-ttu-id="f19ab-157">モデル ビルダーは、SQL Server データベースまたはローカル ファイル (csv または tsv ファイル) という 2 つのソースからデータを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-157">Model Builder accepts data from two sources, a SQL Server database or a local file csv or tsv file.</span></span> <span data-ttu-id="f19ab-158">データ形式の要件の詳細については、次の[リンク](../how-to-guides/install-model-builder.md#limitations)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f19ab-158">For more information on data format requirements, visit the following [link](../how-to-guides/install-model-builder.md#limitations).</span></span>

1. <span data-ttu-id="f19ab-159">モデル ビルダー ツールのデータの手順で、データ ソースのドロップダウンから *[ファイル]* を選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-159">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="f19ab-160">*[ファイルの選択]* テキスト ボックスの横にあるボタンを選択し、ファイル エクスプローラーを使用して *Data* ディレクトリにある *[taxi-fare-test.csv]* を参照し、選択します</span><span class="sxs-lookup"><span data-stu-id="f19ab-160">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="f19ab-161">*[Label or Column to Predict]\(予測するラベルまたは列\)* ドロップダウンにある *[fare_amount]* を選択して、モデル ビルダー ツールのトレーニングの手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-161">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="f19ab-162">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="f19ab-162">Train the model</span></span>

<span data-ttu-id="f19ab-163">このチュートリアルで、価格予測モデルのトレーニングに使用する機械学習のタスクは、回帰です。</span><span class="sxs-lookup"><span data-stu-id="f19ab-163">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="f19ab-164">モデルのトレーニング プロセス中、モデル ビルダーは、さまざまな回帰アルゴリズムと設定を使用して、データセットで最も良いパフォーマンスのモデルを見つける個別のモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="f19ab-164">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="f19ab-165">モデルのトレーニングに必要な時間は、データの量に比例します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-165">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="f19ab-166">このグラフをガイダンスとして使用して、`Time to train (seconds)` フィールドに適した値を選択してください。</span><span class="sxs-lookup"><span data-stu-id="f19ab-166">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="f19ab-167">\*データセットのサイズ</span><span class="sxs-lookup"><span data-stu-id="f19ab-167">\*Dataset Size</span></span>  | <span data-ttu-id="f19ab-168">データセットの種類</span><span class="sxs-lookup"><span data-stu-id="f19ab-168">Dataset Type</span></span>       | <span data-ttu-id="f19ab-169">Avg.トレーニング時間\*</span><span class="sxs-lookup"><span data-stu-id="f19ab-169">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="f19ab-170">0 - 10 Mb</span><span class="sxs-lookup"><span data-stu-id="f19ab-170">0 - 10 Mb</span></span>     | <span data-ttu-id="f19ab-171">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="f19ab-171">Numeric and Text</span></span>   | <span data-ttu-id="f19ab-172">10 秒</span><span class="sxs-lookup"><span data-stu-id="f19ab-172">10 sec</span></span>
<span data-ttu-id="f19ab-173">10 - 100 Mb</span><span class="sxs-lookup"><span data-stu-id="f19ab-173">10 - 100 Mb</span></span>   | <span data-ttu-id="f19ab-174">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="f19ab-174">Numeric and Text</span></span>   | <span data-ttu-id="f19ab-175">10 分</span><span class="sxs-lookup"><span data-stu-id="f19ab-175">10 min</span></span>
<span data-ttu-id="f19ab-176">100 - 500 Mb</span><span class="sxs-lookup"><span data-stu-id="f19ab-176">100 - 500 Mb</span></span>  | <span data-ttu-id="f19ab-177">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="f19ab-177">Numeric and Text</span></span>   | <span data-ttu-id="f19ab-178">30 分</span><span class="sxs-lookup"><span data-stu-id="f19ab-178">30 min</span></span>
<span data-ttu-id="f19ab-179">500 - 1 Gb</span><span class="sxs-lookup"><span data-stu-id="f19ab-179">500 - 1 Gb</span></span>    | <span data-ttu-id="f19ab-180">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="f19ab-180">Numeric and Text</span></span>   | <span data-ttu-id="f19ab-181">60 分</span><span class="sxs-lookup"><span data-stu-id="f19ab-181">60 min</span></span>
<span data-ttu-id="f19ab-182">1 Gb 超</span><span class="sxs-lookup"><span data-stu-id="f19ab-182">1 Gb+</span></span>         | <span data-ttu-id="f19ab-183">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="f19ab-183">Numeric and Text</span></span>   | <span data-ttu-id="f19ab-184">3 時間超</span><span class="sxs-lookup"><span data-stu-id="f19ab-184">3 hour+</span></span>

1. <span data-ttu-id="f19ab-185">トレーニング データ ファイルが 10 MB を超えているため、 *[Time to train (seconds)]\(トレーニング時間 (秒)\)* の値には 600 秒 (10 分) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="f19ab-185">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="f19ab-186">*[Start Training]\(トレーニング開始\)* を選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-186">Select *Start Training*.</span></span>

<span data-ttu-id="f19ab-187">トレーニング プロセスを通して、進捗データがトレーニングの手順の `Progress` セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-187">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="f19ab-188">状態には、トレーニング プロセスの完了ステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-188">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="f19ab-189">[Best accuracy]\(最良の精度\) には、これまでにモデル ビルダーで見つかった最良のパフォーマンスのモデルの精度が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-189">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="f19ab-190">精度が高くなるほど、テスト データでモデルが正確に予測されたことになります。</span><span class="sxs-lookup"><span data-stu-id="f19ab-190">Higher accuracy means the model predicted more correctly on test data.</span></span> 
- <span data-ttu-id="f19ab-191">[Best algorithm]\(最良のアルゴリズム\) には、これまでにモデル ビルダーで見つかった最良のパフォーマンスのアルゴリズムの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-191">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="f19ab-192">[Last algorithm]\(最後のアルゴリズム\) には、モデル ビルダーがモデルのトレーニングに最近使用したアルゴリズムの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-192">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="f19ab-193">トレーニングが完了したら、評価の手順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-193">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="f19ab-194">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="f19ab-194">Evaluate the model</span></span>

<span data-ttu-id="f19ab-195">トレーニングの手順の結果が、最良のパフォーマンスだった 1 つのモデルになります。</span><span class="sxs-lookup"><span data-stu-id="f19ab-195">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="f19ab-196">モデル ビルダー ツールの評価の手順の出力セクションには、 *[Best Model]\(最良のモデル\)* エントリの最良のパフォーマンスのモデルで使用されたアルゴリズムと、 *[Best Model Quality (RSquared)]\(最良のモデル品質 (RSquared)\)* のメトリックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-196">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="f19ab-197">また、概要テーブルには上位 5 つのモデルとそのメトリックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f19ab-197">Additionally, a summary table containing top five models and their metrics.</span></span> <span data-ttu-id="f19ab-198">モデル評価メトリックの詳細については、[次のリンク](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f19ab-198">Visit the following link to learn more about [evaluating model metrics](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span></span>

<span data-ttu-id="f19ab-199">精度のメトリックに不満がある場合、モデルのトレーニング時間を増やすか、さらに多くのデータを使用すると、モデルの精度を簡単に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-199">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="f19ab-200">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="f19ab-200">Use the model for predictions</span></span>

<span data-ttu-id="f19ab-201">トレーニング プロセスの結果として 2 つのプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-201">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="f19ab-202">TaxiFarePredictionML.ConsoleApp: モデルのトレーニングと消費コードが含まれる .NET コンソール アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="f19ab-202">TaxiFarePredictionML.ConsoleApp: A .NET Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="f19ab-203">TaxiFarePredictionML.Model: 入出力モデル データのスキーマを定義するデータ モデルと、トレーニング中にパフォーマンスが最も良かったモデルの永続化バージョンが含まれる .NET Standard クラス ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="f19ab-203">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="f19ab-204">モデル ビルダー ツールのコード セクションで **[Added Projects]\(追加されたプロジェクト\)** を選択して、プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-204">In the code section of the Model Builder tool, select **Added Projects** to add the projects to the solution.</span></span>
1. <span data-ttu-id="f19ab-205">ソリューション エクスプローラーで、 *[TaxiFarePrediction]* プロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f19ab-205">In solution explorer, right-click the *TaxiFarePrediction* project.</span></span> <span data-ttu-id="f19ab-206">次に、 **[追加]、[既存の項目]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-206">Then, select **Add > Existing Item**.</span></span> <span data-ttu-id="f19ab-207">[ファイルの種類] のドロップダウンで `All Files` を選択し、 *[TaxiFarePredictionML.Model]* のプロジェクト ディレクトリに移動して、`MLModel.zip` ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-207">For file type drop down, select `All Files`, navigate to the *TaxiFarePredictionML.Model* project directory and select the `MLModel.zip` file.</span></span> <span data-ttu-id="f19ab-208">最近追加した `MLModel.zip` ファイルを右クリックし、 *[プロパティ]* を選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-208">Then right-click the recently added `MLModel.zip` file and select *Properties*.</span></span> <span data-ttu-id="f19ab-209">[出力ディレクトリにコピー] オプションで、 *[新しい場合はコピーする]* をドロップダウンから選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-209">For the Copy to Output Directory option, select *Copy if Newer* from the dropdown.</span></span>
1. <span data-ttu-id="f19ab-210">*[TaxiFarePrediction]* プロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f19ab-210">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="f19ab-211">それから、 **[追加]、[参照]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-211">Then, **Add > Reference**.</span></span> <span data-ttu-id="f19ab-212">**[プロジェクト]、[ソリューション]** ノードを選択し、一覧で *[TaxiFarePredictionML.Model]* プロジェクトを選択して [OK] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-212">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>

4. <span data-ttu-id="f19ab-213">*[TaxiFarePrediction]* プロジェクトの *[Program.cs]* ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-213">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
5. <span data-ttu-id="f19ab-214">次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-214">Add the following using statements:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. <span data-ttu-id="f19ab-215">`ConsumeModel` メソッドを `Program` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-215">Add the `ConsumeModel` method to the `Program` class.</span></span> <span data-ttu-id="f19ab-216">`ConsumeModel` で、モデル ビルダーによって生成されたモデルに基づいて新しいデータの予測を行い、コンソールに出力する `PredictionEngine` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-216">The `ConsumeModel` will create a `PredictionEngine` based on the model generated by Model Builder to make predictions on new data and print them out to the console.</span></span>

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

7. <span data-ttu-id="f19ab-217">`Main` メソッドに次のコードを追加して、アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="f19ab-217">Add the following code to the `Main` method and run the application.</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    <span data-ttu-id="f19ab-218">プログラムによって生成される出力は次のスニペットのようになります。</span><span class="sxs-lookup"><span data-stu-id="f19ab-218">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="f19ab-219">別のソリューション内で後で生成されたプロジェクトを参照する必要がある場合は、`C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` ディレクトリを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="f19ab-219">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f19ab-220">次の手順</span><span class="sxs-lookup"><span data-stu-id="f19ab-220">Next Steps</span></span>

<span data-ttu-id="f19ab-221">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="f19ab-221">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f19ab-222">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="f19ab-222">Prepare and understand the data</span></span>
> * <span data-ttu-id="f19ab-223">シナリオを選択する</span><span class="sxs-lookup"><span data-stu-id="f19ab-223">Choose a scenario</span></span>
> * <span data-ttu-id="f19ab-224">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="f19ab-224">Load the data</span></span>
> * <span data-ttu-id="f19ab-225">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="f19ab-225">Train the model</span></span>
> * <span data-ttu-id="f19ab-226">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="f19ab-226">Evaluate the model</span></span>
> * <span data-ttu-id="f19ab-227">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="f19ab-227">Use the model for predictions</span></span>

<span data-ttu-id="f19ab-228">モデルをデプロイする方法を学習するには、次の How-To 記事のいずれかに進んでください。</span><span class="sxs-lookup"><span data-stu-id="f19ab-228">Advance to either of the following how-to articles to learn how to deploy your model.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f19ab-229">Azure Functions にモデルをデプロイする</span><span class="sxs-lookup"><span data-stu-id="f19ab-229">Deploy a model to Azure Functions</span></span>](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="f19ab-230">Web API にモデルをデプロイする</span><span class="sxs-lookup"><span data-stu-id="f19ab-230">Deploy a model to a Web API</span></span>](../how-to-guides/serve-model-web-api-ml-net.md)
