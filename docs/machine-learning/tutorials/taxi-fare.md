---
title: 回帰ラーナーと ML.NET を使用して料金を予測する
description: 回帰ラーナーと ML.NET を使用して料金を予測します。
author: aditidugar
ms.author: johalex
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 49770672ebcff98d8779a888372b5c9f40a55b1d
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611810"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a><span data-ttu-id="14e90-103">チュートリアル: 回帰ラーナーと ML.NET を使用して料金を予測する</span><span class="sxs-lookup"><span data-stu-id="14e90-103">Tutorial: Predict prices using a regression learner with ML.NET</span></span>

<span data-ttu-id="14e90-104">このチュートリアルでは、ML.NET を使用して、料金 (具体的にはニューヨーク市のタクシー運賃) を予測する[回帰モデル](../resources/glossary.md#regression)を構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14e90-104">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting prices, specifically, New York City taxi fares.</span></span>

> [!NOTE]
> <span data-ttu-id="14e90-105">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="14e90-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="14e90-106">詳しくは、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14e90-106">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="14e90-107">このチュートリアルと関連サンプルでは、現時点では **ML.NET バージョン 0.11** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="14e90-107">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="14e90-108">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e90-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="14e90-109">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14e90-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="14e90-110">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="14e90-110">Understand the problem</span></span>
> * <span data-ttu-id="14e90-111">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="14e90-111">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="14e90-112">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="14e90-112">Prepare and understand the data</span></span>
> * <span data-ttu-id="14e90-113">学習パイプラインを作成する</span><span class="sxs-lookup"><span data-stu-id="14e90-113">Create a learning pipeline</span></span>
> * <span data-ttu-id="14e90-114">データを読み込んで変換する</span><span class="sxs-lookup"><span data-stu-id="14e90-114">Load and transform the data</span></span>
> * <span data-ttu-id="14e90-115">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="14e90-115">Choose a learning algorithm</span></span>
> * <span data-ttu-id="14e90-116">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="14e90-116">Train the model</span></span>
> * <span data-ttu-id="14e90-117">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="14e90-117">Evaluate the model</span></span>
> * <span data-ttu-id="14e90-118">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="14e90-118">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14e90-119">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="14e90-119">Prerequisites</span></span>

* <span data-ttu-id="14e90-120">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="14e90-120">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="14e90-121">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="14e90-121">Understand the problem</span></span>

<span data-ttu-id="14e90-122">この問題の中心となるのは、ニューヨーク市のタクシー旅行の運賃の予測です。</span><span class="sxs-lookup"><span data-stu-id="14e90-122">This problem is about predicting the fare of a taxi trip in New York City.</span></span> <span data-ttu-id="14e90-123">一見すると、単に乗車距離に依存すると思われるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="14e90-123">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="14e90-124">しかし、ニューヨークのタクシー会社は追加の乗客数や現金でなくクレジット カードによる支払いなど、その他の要因によって請求額を変えます。</span><span class="sxs-lookup"><span data-stu-id="14e90-124">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="14e90-125">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="14e90-125">Select the appropriate machine learning task</span></span>

<span data-ttu-id="14e90-126">データ セットの他の要因に基づき、実際の値である、価格値を予測します。</span><span class="sxs-lookup"><span data-stu-id="14e90-126">You want to predict the price value, which is a real value, based on the other factors in the data set.</span></span> <span data-ttu-id="14e90-127">それを行うには、[回帰](../resources/glossary.md#regression)機械学習タスクを選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-127">To do that you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="14e90-128">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="14e90-128">Create a console application</span></span>

1. <span data-ttu-id="14e90-129">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="14e90-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="14e90-130">**[ファイル]** > **[新規作成]** > **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="14e90-131">**[新しいプロジェクト]** ダイアログで、**[Visual C#]** ノードを選択し、**[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="14e90-132">次に、**[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="14e90-133">**[名前]** テキスト ボックスに「TaxiFarePrediction」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

1. <span data-ttu-id="14e90-134">プロジェクトに *Data* という名前のディレクトリを作成して、データ セットとモデルのファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="14e90-134">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="14e90-135">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-135">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="14e90-136">「Data」と入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="14e90-136">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="14e90-137">**Microsoft.ML** NuGet パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="14e90-137">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="14e90-138">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-138">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="14e90-139">[パッケージ ソース] として "nuget.org" を選択し、**[参照]** タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-139">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="14e90-140">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、**[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="14e90-141">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="14e90-141">Prepare and understand the data</span></span>

1. <span data-ttu-id="14e90-142">[taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) データ セットと [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) データ セットをダウンロードして、前の手順で作成済みの *Data* フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="14e90-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="14e90-143">これらのデータ セットを使用して、機械学習モデルをトレーニングし、モデルの正確度を評価します。</span><span class="sxs-lookup"><span data-stu-id="14e90-143">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="14e90-144">これらのデータ セットは、[NYC TLC Taxi Trip データ セット](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)から取得したものです。</span><span class="sxs-lookup"><span data-stu-id="14e90-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="14e90-145">**ソリューション エクスプローラー**で、各 \*.csv ファイルを右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-145">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="14e90-146">**[詳細設定]** で、**[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="14e90-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="14e90-147">**taxi-fare-train.csv** データ セットを開き、最初の行の列ヘッダーを確認します。</span><span class="sxs-lookup"><span data-stu-id="14e90-147">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="14e90-148">各列を確認してください。</span><span class="sxs-lookup"><span data-stu-id="14e90-148">Take a look at each of the columns.</span></span> <span data-ttu-id="14e90-149">データについて把握し、どの列が**特徴**で、どの列が**ラベル**であるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="14e90-149">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="14e90-150">**ラベル**は、予測する列の識別子です。</span><span class="sxs-lookup"><span data-stu-id="14e90-150">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="14e90-151">識別された**特徴**は、ラベルを予測するために使用します。</span><span class="sxs-lookup"><span data-stu-id="14e90-151">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="14e90-152">提供されているデータ セットには、次の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="14e90-152">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="14e90-153">**vendor_id:** タクシー会社の ID は特徴です。</span><span class="sxs-lookup"><span data-stu-id="14e90-153">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="14e90-154">**rate_code:** タクシー旅行のレートの種類は特徴です。</span><span class="sxs-lookup"><span data-stu-id="14e90-154">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="14e90-155">**passenger_count:** 旅行の乗客数は特徴です。</span><span class="sxs-lookup"><span data-stu-id="14e90-155">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="14e90-156">**trip_time_in_secs:** 旅行の所要時間です。</span><span class="sxs-lookup"><span data-stu-id="14e90-156">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="14e90-157">旅行が終わる前に、旅行の運賃を予測したいと考えます。</span><span class="sxs-lookup"><span data-stu-id="14e90-157">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="14e90-158">その時点では、旅行の所要時間はわかりません。</span><span class="sxs-lookup"><span data-stu-id="14e90-158">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="14e90-159">したがって、旅行の所要時間は特徴ではなく、この列はモデルから除外します。</span><span class="sxs-lookup"><span data-stu-id="14e90-159">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="14e90-160">**trip_distance:** 旅行距離は特徴です。</span><span class="sxs-lookup"><span data-stu-id="14e90-160">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="14e90-161">**payment_type:** 支払い方法 (現金またはクレジット カード) は特徴です。</span><span class="sxs-lookup"><span data-stu-id="14e90-161">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="14e90-162">**fare_amount:** 支払った合計タクシー運賃はラベルです。</span><span class="sxs-lookup"><span data-stu-id="14e90-162">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="14e90-163">データ クラスを作成する</span><span class="sxs-lookup"><span data-stu-id="14e90-163">Create data classes</span></span>

<span data-ttu-id="14e90-164">入力データと予測のためのクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="14e90-164">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="14e90-165">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-165">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="14e90-166">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを *TaxiTrip.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="14e90-166">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="14e90-167">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-167">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="14e90-168">以下の `using` ディレクティブを新しいファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-168">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="14e90-169">既存のクラス定義を削除し、2 つのクラス `TaxiTrip` と `TaxiTripFarePrediction` を含む次のコードを *TaxiTrip.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-169">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="14e90-170">`TaxiTrip` は入力データ クラスであり、各データ セット列の定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="14e90-170">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="14e90-171"><xref:Microsoft.ML.Data.LoadColumnAttribute> 属性を使用して、データ セット内のソース列のインデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="14e90-171">Use the <xref:Microsoft.ML.Data.LoadColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="14e90-172">`TaxiTripFarePrediction` クラスは予測結果を表します。</span><span class="sxs-lookup"><span data-stu-id="14e90-172">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="14e90-173">このクラスには、`Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> 属性が適用された 1 つの浮動小数点型フィールド `FareAmount` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="14e90-173">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="14e90-174">回帰タスクの場合、**Score** 列には、予測ラベル値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="14e90-174">In case of the regression task the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="14e90-175">入力データと予測データのクラス内の浮動小数点値を表すには、`float` 型を使います。</span><span class="sxs-lookup"><span data-stu-id="14e90-175">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="14e90-176">データおよびモデルのパスを定義する</span><span class="sxs-lookup"><span data-stu-id="14e90-176">Define data and model paths</span></span>

<span data-ttu-id="14e90-177">次に示す追加の `using` ステートメントを *Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-177">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="14e90-178">データ セットを含むファイルのパスとモデルを保存するファイルのパスを保持するための 3 つのフィールドを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e90-178">You need to create three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="14e90-179">`_trainDataPath` には、モデルのトレーニングに使用するデータ セットがあるファイルへのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="14e90-179">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="14e90-180">`_testDataPath` には、モデルの評価に使用するデータ セットがあるファイルへのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="14e90-180">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="14e90-181">`_modelPath` には、トレーニング済みモデルが格納されるファイルへのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="14e90-181">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="14e90-182">`Main` メソッドのすぐ上に次のコードを追加して、それらのパスと `_textLoader` 変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="14e90-182">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="14e90-183">ML.NET を使用してモデルをビルドするときは、まず ML Context を作成します。</span><span class="sxs-lookup"><span data-stu-id="14e90-183">When building a model with ML.NET you start by creating an ML Context.</span></span> <span data-ttu-id="14e90-184">これは、概念的には Entity Framework での `DbContext` の使用に相当します。</span><span class="sxs-lookup"><span data-stu-id="14e90-184">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="14e90-185">環境によって、例外の追跡とログ記録に使用できる機械学習ジョブのコンテキストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="14e90-185">The environment provides a context for your machine learning job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="14e90-186">Main で変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="14e90-186">Initialize variables in Main</span></span>

<span data-ttu-id="14e90-187">`mlContext` という変数を作成し、`MLContext` の新しいインスタンスで初期化します。</span><span class="sxs-lookup"><span data-stu-id="14e90-187">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="14e90-188">`Main` メソッドの `Console.WriteLine("Hello World!")` 行を、次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="14e90-188">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="14e90-189">`Main` メソッドに次のコード行を追加して、`Train` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="14e90-189">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

<span data-ttu-id="14e90-190">`Train` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e90-190">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="14e90-191">データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="14e90-191">Loads the data.</span></span>
* <span data-ttu-id="14e90-192">データを抽出して変換します。</span><span class="sxs-lookup"><span data-stu-id="14e90-192">Extracts and transforms the data.</span></span>
* <span data-ttu-id="14e90-193">モデルをトレーニングする。</span><span class="sxs-lookup"><span data-stu-id="14e90-193">Trains the model.</span></span>
* <span data-ttu-id="14e90-194">モデルを .zip ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="14e90-194">Saves the model as .zip file.</span></span>
* <span data-ttu-id="14e90-195">モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="14e90-195">Returns the model.</span></span>

<span data-ttu-id="14e90-196">`Train` メソッドは、モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="14e90-196">The `Train` method trains the model.</span></span> <span data-ttu-id="14e90-197">次のコードを使用して、`Main` の直下にそのメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="14e90-197">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="14e90-198">`Train` メソッドに 2 つのパラメーターを渡します。つまり、コンテキスト (`mlContext`) には`MLContext`、データセット パス (`dataPath`) には文字列です。</span><span class="sxs-lookup"><span data-stu-id="14e90-198">We are passing two parameters into the `Train` method; an `MLContext` for the context (`mlContext`), and a string for the dataset path (`dataPath`).</span></span> <span data-ttu-id="14e90-199">このメソッドをデータセットの読み込みに再利用します。</span><span class="sxs-lookup"><span data-stu-id="14e90-199">We're going to reuse this method for loading datasets.</span></span>

## <a name="load-and-transform-data"></a><span data-ttu-id="14e90-200">データを読み込んで変換する</span><span class="sxs-lookup"><span data-stu-id="14e90-200">Load and transform data</span></span>

<span data-ttu-id="14e90-201">[LoadFromTextFile メソッド](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) の `MLContext.Data.LoadFromTextFile` ラッパーを使用して、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="14e90-201">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="14e90-202"><xref:Microsoft.Data.DataView.IDataView> が返されます。</span><span class="sxs-lookup"><span data-stu-id="14e90-202">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span>

<span data-ttu-id="14e90-203">`Transforms` の入力および出力として、`DataView` は基本的なデータ パイプラインの種類であり、`LINQ` の `IEnumerable` と同等です。</span><span class="sxs-lookup"><span data-stu-id="14e90-203">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="14e90-204">ML.NET ではデータは SQL ビューに似ています。</span><span class="sxs-lookup"><span data-stu-id="14e90-204">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="14e90-205">つまり、遅延評価、体系的、異種です。</span><span class="sxs-lookup"><span data-stu-id="14e90-205">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="14e90-206">オブジェクトはパイプラインの最初の部分であり、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="14e90-206">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="14e90-207">このチュートリアルでは、タクシーの運賃情報を含むデータセットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="14e90-207">For this tutorial, it loads a dataset with taxi trip pricing information.</span></span> <span data-ttu-id="14e90-208">これを使用して、モデルを作成してトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="14e90-208">This is used to create the model, and train it.</span></span>

<span data-ttu-id="14e90-209">`Train` メソッドの最初の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-209">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

<span data-ttu-id="14e90-210">次の手順では、`TaxiTrip` クラス内で定義された名前によって列を参照します。</span><span class="sxs-lookup"><span data-stu-id="14e90-210">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="14e90-211">モデルのトレーニングと評価が行われるとき、既定では、**Label** 列内の値が予測される適切な値と見なされます。</span><span class="sxs-lookup"><span data-stu-id="14e90-211">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="14e90-212">タクシー旅行の運賃を予測したいので、`FareAmount` 列を **Label** 列にコピーします。</span><span class="sxs-lookup"><span data-stu-id="14e90-212">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="14e90-213">これを行うには、`CopyColumnsEstimator` 変換クラスを使用して、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-213">To do that, use the `CopyColumnsEstimator` transformation class, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="14e90-214">モデルをトレーニングするアルゴリズムには、**数値**の特徴が必要であるため、カテゴリ データ (`VendorId`、`RateCode`、および `PaymentType`) の値を数値 (`VendorIdEncoded`、`RateCodeEncoded`、および`PaymentTypeEncoded`) に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e90-214">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers (`VendorIdEncoded`, `RateCodeEncoded`, and `PaymentTypeEncoded`).</span></span> <span data-ttu-id="14e90-215">これを行うには、異なる数値キーの値を各列内の異なる値に割り当てる Microsoft.ML.Transforms.OneHotEncodingTransformer> 変換クラスを使用する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-215">To do that, use the Microsoft.ML.Transforms.OneHotEncodingTransformer> transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="14e90-216">データの準備の最後の手順では、`mlContext.Transforms.Concatenate` 変換クラスを使用して、すべての特徴列を **Features** 列に結合します。</span><span class="sxs-lookup"><span data-stu-id="14e90-216">The last step in data preparation combines all of the feature columns into the **Features** column using the `mlContext.Transforms.Concatenate` transformation class.</span></span> <span data-ttu-id="14e90-217">既定では、学習アルゴリズムは **Features** 列の特徴のみを処理します。</span><span class="sxs-lookup"><span data-stu-id="14e90-217">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="14e90-218">次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-218">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="14e90-219">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="14e90-219">Choose a learning algorithm</span></span>

<span data-ttu-id="14e90-220">データをパイプラインに追加して正しい入力形式に変換したら、学習アルゴリズム (**ラーナー**) を選択します。</span><span class="sxs-lookup"><span data-stu-id="14e90-220">After adding the data to the pipeline and transforming it into the correct input format, we select a learning algorithm (**learner**).</span></span> <span data-ttu-id="14e90-221">ラーナーはモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="14e90-221">The learner trains the model.</span></span> <span data-ttu-id="14e90-222">この問題に対しては**回帰タスク**を選択するので、`FastTreeRegressionTrainer` ラーナー (ML.NET によって提供される回帰ラーナーの 1 つ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="14e90-222">We chose a **regression** task for this problem, so we use a `FastTreeRegressionTrainer` learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="14e90-223">`FastTreeRegressionTrainer`トレーニング アルゴリズムでは、勾配ブースティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="14e90-223">The `FastTreeRegressionTrainer` training algorithm utilizes gradient boosting.</span></span> <span data-ttu-id="14e90-224">勾配ブースティングは、回帰問題に対応する機械学習の手法です。</span><span class="sxs-lookup"><span data-stu-id="14e90-224">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="14e90-225">この手法では、それぞれの回帰ツリーを段階的に構築します。</span><span class="sxs-lookup"><span data-stu-id="14e90-225">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="14e90-226">また、定義済みの損失関数を使用して、各ステップの誤差を測定し、次の段階で修正します。</span><span class="sxs-lookup"><span data-stu-id="14e90-226">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="14e90-227">結果は予測モデルですが、実際は弱い予測モデルの集合です。</span><span class="sxs-lookup"><span data-stu-id="14e90-227">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="14e90-228">勾配ブースティングについて詳しくは、「[Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)」(ブーストされたデシジョン ツリー回帰) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e90-228">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="14e90-229">`Train` メソッドに次のコードを追加して、前の手順で追加したデータ処理コードに `FastTreeRegressionTrainer` を追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-229">Add the following code into the `Train` method to add the `FastTreeRegressionTrainer` to the data processing code added in the previous step:</span></span>

[!code-csharp[FastTreeRegressionTrainer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="14e90-230">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="14e90-230">Train the model</span></span>

<span data-ttu-id="14e90-231">最後の手順は、モデルのトレーニングです。</span><span class="sxs-lookup"><span data-stu-id="14e90-231">The final step is to train the model.</span></span> <span data-ttu-id="14e90-232">読み込まれて変換されたデータ セットに基づいて、モデル <xref:Microsoft.ML.Data.TransformerChain> をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="14e90-232">We train the model, <xref:Microsoft.ML.Data.TransformerChain>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="14e90-233">見積もり機能が定義されたら、既に読み込まれたトレーニング データを提供しながら、<xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> を使用してモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="14e90-233">Once the estimator has been defined, we train the model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="14e90-234">これにより、予測で使用されるモデルが返されます。</span><span class="sxs-lookup"><span data-stu-id="14e90-234">This returns a model to use for predictions.</span></span> <span data-ttu-id="14e90-235">`pipeline.Fit()` でパイプラインをトレーニングし、`DataView` に基づいて `Transformer` を返します。</span><span class="sxs-lookup"><span data-stu-id="14e90-235">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="14e90-236">これが行われるまで、実験は実行されません。</span><span class="sxs-lookup"><span data-stu-id="14e90-236">The experiment is not executed until this happens.</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

### <a name="save-the-model"></a><span data-ttu-id="14e90-237">モデルを保存する</span><span class="sxs-lookup"><span data-stu-id="14e90-237">Save the model</span></span>

<span data-ttu-id="14e90-238">この時点で、既存または新規のどの .NET アプリケーションにも統合できる、型が <xref:Microsoft.ML.Data.TransformerChain> のモデルができました。</span><span class="sxs-lookup"><span data-stu-id="14e90-238">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="14e90-239">モデルを .zip ファイルに保存するには、`Train` メソッドの終わりに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-239">To save the model to a .zip file, add the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="14e90-240">モデルを .zip ファイルとして保存する</span><span class="sxs-lookup"><span data-stu-id="14e90-240">Save the model as a .zip file</span></span>

<span data-ttu-id="14e90-241">`Train` メソッドの直後に、次のコードを使用して `SaveModelAsFile` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="14e90-241">Create the `SaveModelAsFile` method, just after the `Train` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="14e90-242">`SaveModelAsFile` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e90-242">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="14e90-243">モデルを .zip ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="14e90-243">Saves the model as a .zip file.</span></span>

<span data-ttu-id="14e90-244">他のアプリケーションで再利用し、使用できるように、モデルを保存するメソッドを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e90-244">We need to create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="14e90-245">`ITransformer` には <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> メソッドがあり、`_modelPath` グローバル フィールドと <xref:System.IO.Stream> を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="14e90-245">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="14e90-246">これを zip ファイルとして保存するために、`FileStream` を作成した直後に `SaveTo` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="14e90-246">Since we want to save this as a zip file, we'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="14e90-247">`SaveModelAsFile` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-247">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

<span data-ttu-id="14e90-248">`_modelPath` を使用してコンソール メッセージを記述することで、ファイルが書き込まれた場所も表示できるようになります。これには次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="14e90-248">We could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a><span data-ttu-id="14e90-249">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="14e90-249">Evaluate the model</span></span>

<span data-ttu-id="14e90-250">評価は、モデルがラベル値を適切に予測するかどうかを確認するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="14e90-250">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="14e90-251">モデルのトレーニング時に使用しなかったデータを適切に予測できるかどうかが重要になります。</span><span class="sxs-lookup"><span data-stu-id="14e90-251">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="14e90-252">そのための方法の 1 つとしては、このチュートリアルで行ったように、データをトレーニング用のデータ セットとテスト用のデータ セットに分けます。</span><span class="sxs-lookup"><span data-stu-id="14e90-252">One way to do this is to split the data into training and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="14e90-253">トレーニング用データでのモデルのトレーニングは完了しているので、テスト用データでモデルが適切に機能するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="14e90-253">Now that you've trained the model on the training data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="14e90-254">`Evaluate` メソッドはモデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="14e90-254">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="14e90-255">そのメソッドを作成するには、`Train` メソッドの下に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-255">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="14e90-256">`Evaluate` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e90-256">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="14e90-257">テスト データ セットを読み込む。</span><span class="sxs-lookup"><span data-stu-id="14e90-257">Loads the test dataset.</span></span>
* <span data-ttu-id="14e90-258">回帰エバリュエーターを作成する。</span><span class="sxs-lookup"><span data-stu-id="14e90-258">Creates the regression evaluator.</span></span>
* <span data-ttu-id="14e90-259">モデルを評価し、メトリックを作成する。</span><span class="sxs-lookup"><span data-stu-id="14e90-259">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="14e90-260">メトリックを表示する。</span><span class="sxs-lookup"><span data-stu-id="14e90-260">Displays the metrics.</span></span>

<span data-ttu-id="14e90-261">`Train` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-261">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="14e90-262">`MLContext.Data.LoadFromTextFile` ラッパーを使用して、テスト データセットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="14e90-262">Load the test dataset using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="14e90-263">このデータ セットを品質チェックとして使用して、モデルを評価できます。</span><span class="sxs-lookup"><span data-stu-id="14e90-263">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="14e90-264">`Evaluate` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-264">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="14e90-265">次に、機械学習 `model` パラメーター (変換器) を使用して特徴を入力し、予測を返します。</span><span class="sxs-lookup"><span data-stu-id="14e90-265">Next, use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="14e90-266">`Evaluate` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-266">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="14e90-267">`RegressionContext.Evaluate` メソッドは、指定されたデータセットを使用して `PredictionModel` の品質メトリックを計算します。</span><span class="sxs-lookup"><span data-stu-id="14e90-267">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="14e90-268">これによって返される <xref:Microsoft.ML.Data.RegressionMetrics> オブジェクトには、回帰エバリュエーターによって計算されるメトリック全体が含まれます。</span><span class="sxs-lookup"><span data-stu-id="14e90-268">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span> <span data-ttu-id="14e90-269">これらを表示してモデルの品質を判定するには、最初にメトリックを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e90-269">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="14e90-270">`Evaluate` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-270">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="14e90-271">次のコードを追加してモデルを評価し、評価メトリックを生成します。</span><span class="sxs-lookup"><span data-stu-id="14e90-271">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="14e90-272">[RSquared](../resources/glossary.md#coefficient-of-determination) は回帰モデルのもう 1 つの評価メトリックです。</span><span class="sxs-lookup"><span data-stu-id="14e90-272">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="14e90-273">RSquared は 0 から 1 までの値を取ります。</span><span class="sxs-lookup"><span data-stu-id="14e90-273">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="14e90-274">値が 1 に近づくほど、優れたモデルになります。</span><span class="sxs-lookup"><span data-stu-id="14e90-274">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="14e90-275">次のコードを `Evaluate` メソッドに追加して、RSquared 値を表示します。</span><span class="sxs-lookup"><span data-stu-id="14e90-275">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="14e90-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) は回帰モデルの評価メトリックの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="14e90-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="14e90-277">RMS が低いほど、優れたモデルになります。</span><span class="sxs-lookup"><span data-stu-id="14e90-277">The lower it is, the better the model is.</span></span> <span data-ttu-id="14e90-278">`Evaluate` メソッドに次のコードを追加することで、RMS 値を表示します。</span><span class="sxs-lookup"><span data-stu-id="14e90-278">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="14e90-279">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="14e90-279">Use the model for predictions</span></span>

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="14e90-280">モデルと 1 つのコメントを使用してテスト データの結果を予測する</span><span class="sxs-lookup"><span data-stu-id="14e90-280">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="14e90-281">`Evaluate` メソッドの直後に、次のコードを使用して `TestSinglePrediction` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="14e90-281">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

<span data-ttu-id="14e90-282">`TestSinglePrediction` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e90-282">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="14e90-283">テスト データの 1 つのコメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="14e90-283">Creates a single comment of test data.</span></span>
* <span data-ttu-id="14e90-284">テスト データに基づいて運賃合計を予測します。</span><span class="sxs-lookup"><span data-stu-id="14e90-284">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="14e90-285">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="14e90-285">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="14e90-286">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="14e90-286">Displays the predicted results.</span></span>

<span data-ttu-id="14e90-287">`Evaluate` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-287">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="14e90-288">保存した zip ファイルからモデルを読み込むために、`Load` メソッドを呼び出す直前に `FileStream` を作成します。</span><span class="sxs-lookup"><span data-stu-id="14e90-288">Since we want to load the model from the zip file we saved, we'll create the `FileStream` immediately before calling the `Load` method.</span></span> <span data-ttu-id="14e90-289">`TestSinglePrediction` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-289">Add the following code to the `TestSinglePrediction` method as the next line:</span></span>

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

<span data-ttu-id="14e90-290">`model` は多数のデータ行を操作する `transformer` ですが、よくある運用シナリオとして個々の例に対する予測のニーズがあります。</span><span class="sxs-lookup"><span data-stu-id="14e90-290">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="14e90-291"><xref:Microsoft.ML.PredictionEngine%602> は、`CreatePredictionEngine` メソッドから返されるラッパーです。</span><span class="sxs-lookup"><span data-stu-id="14e90-291">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="14e90-292">次の行を追加して、`PredictionEngine` を `TestSinglePrediction` メソッドの次の行として作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="14e90-292">Let's add the following code to create the `PredictionEngine` as the next line in the `TestSinglePrediction` Method:</span></span>

[!code-csharp[MakePredictionEngine](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]

<span data-ttu-id="14e90-293">このチュートリアルでは、このクラス内の 1 つのテスト用の旅行を使用します。</span><span class="sxs-lookup"><span data-stu-id="14e90-293">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="14e90-294">モデルを試行するために後で他のシナリオを追加できます。</span><span class="sxs-lookup"><span data-stu-id="14e90-294">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="14e90-295">`TaxiTrip` のインスタンスを作成して、`TestSinglePrediction` メソッドでコストのトレーニング済みモデルの予測をテストするために、旅行を追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-295">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

<span data-ttu-id="14e90-296">これを使用して、タクシー運賃データの 1 つのインスタンスに基づいて料金を予測することができます。</span><span class="sxs-lookup"><span data-stu-id="14e90-296">We can use that to predict the fare based on a single instance of the taxi trip data.</span></span> <span data-ttu-id="14e90-297">予測を取得するには、データに対して <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="14e90-297">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="14e90-298">入力データは文字列であり、モデルには、特徴付けが含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14e90-298">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="14e90-299">トレーニングと予測の間は、パイプラインが同期されます。</span><span class="sxs-lookup"><span data-stu-id="14e90-299">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="14e90-300">予測のために前処理/特徴付けのコードを特別に記述する必要はなく、同じ API によってバッチと 1 回限りの予測の両方が処理されます。</span><span class="sxs-lookup"><span data-stu-id="14e90-300">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="14e90-301">指定された旅行の予測運賃を表示するために、次のコードを `TestSinglePrediction` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="14e90-301">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="14e90-302">プログラムを実行し、テスト ケースに対して予測されたタクシー運賃を確認します。</span><span class="sxs-lookup"><span data-stu-id="14e90-302">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="14e90-303">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="14e90-303">Congratulations!</span></span> <span data-ttu-id="14e90-304">これで、タクシー旅行運賃を予測する機械学習モデルが正常に構築され、その正確度が評価され、このモデルを使用した予測が行われました。</span><span class="sxs-lookup"><span data-stu-id="14e90-304">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="14e90-305">このチュートリアルのソース コードは、[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="14e90-305">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="14e90-306">次の手順</span><span class="sxs-lookup"><span data-stu-id="14e90-306">Next steps</span></span>

<span data-ttu-id="14e90-307">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="14e90-307">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="14e90-308">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="14e90-308">Understand the problem</span></span>
> * <span data-ttu-id="14e90-309">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="14e90-309">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="14e90-310">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="14e90-310">Prepare and understand the data</span></span>
> * <span data-ttu-id="14e90-311">学習パイプラインを作成する</span><span class="sxs-lookup"><span data-stu-id="14e90-311">Create a learning pipeline</span></span>
> * <span data-ttu-id="14e90-312">データを読み込んで変換する</span><span class="sxs-lookup"><span data-stu-id="14e90-312">Load and transform the data</span></span>
> * <span data-ttu-id="14e90-313">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="14e90-313">Choose a learning algorithm</span></span>
> * <span data-ttu-id="14e90-314">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="14e90-314">Train the model</span></span>
> * <span data-ttu-id="14e90-315">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="14e90-315">Evaluate the model</span></span>
> * <span data-ttu-id="14e90-316">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="14e90-316">Use the model for predictions</span></span>

<span data-ttu-id="14e90-317">さらに詳しく学習するには、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="14e90-317">Advance to the next tutorial to learn more.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14e90-318">アヤメのクラスタリング</span><span class="sxs-lookup"><span data-stu-id="14e90-318">Iris clustering</span></span>](iris-clustering.md)
