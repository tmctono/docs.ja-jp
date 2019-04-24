---
title: 映画のレコメンデーション シナリオで ML.NET を使用する
description: ユーザーに映画をお勧めするレコメンデーション シナリオでの ML.NET の使用方法を説明します。
author: briacht
ms.author: johalex
ms.date: 03/08/2019
ms.custom: mvc
ms.topic: tutorial
ms.openlocfilehash: bdc49f42e520f11ef63de873f0d30d11ba4b2366
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612278"
---
# <a name="tutorial-create-a-movie-recommender-with-mlnet"></a><span data-ttu-id="3cd99-103">チュートリアル: ML.NET を使用して映画の推奨システムを作成する</span><span class="sxs-lookup"><span data-stu-id="3cd99-103">Tutorial: Create a Movie Recommender with ML.NET</span></span>

<span data-ttu-id="3cd99-104">このサンプル チュートリアルでは、Visual Studio 2017 で ML.NET を使用して、C# を使用する .NET Core コンソール アプリケーションから映画の推奨システムを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-104">This sample tutorial illustrates using ML.NET to build a movie recommender via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="3cd99-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="3cd99-106">機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="3cd99-106">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="3cd99-107">データを準備して読み込む</span><span class="sxs-lookup"><span data-stu-id="3cd99-107">Prepare and load your data</span></span>
> * <span data-ttu-id="3cd99-108">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="3cd99-108">Build and train a model</span></span>
> * <span data-ttu-id="3cd99-109">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="3cd99-109">Evaluate a model</span></span>
> * <span data-ttu-id="3cd99-110">モデルを展開して使用する</span><span class="sxs-lookup"><span data-stu-id="3cd99-110">Deploy and consume a model</span></span>

> [!NOTE]
> <span data-ttu-id="3cd99-111">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-111">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="3cd99-112">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd99-112">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="3cd99-113">このチュートリアルと関連サンプルでは、現時点では **ML.NET バージョン 0.11** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="3cd99-113">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="3cd99-114">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd99-114">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="3cd99-115">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="3cd99-116">機械学習ワークフロー</span><span class="sxs-lookup"><span data-stu-id="3cd99-116">Machine learning workflow</span></span>

<span data-ttu-id="3cd99-117">次の手順を使用して、自分のタスクとその他の ML.NET タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-117">You will use the following steps to accomplish your task, as well as any other ML.NET task:</span></span>

1. [<span data-ttu-id="3cd99-118">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="3cd99-118">Load your data</span></span>](#load-your-data)
2. [<span data-ttu-id="3cd99-119">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="3cd99-119">Build and train your model</span></span>](#build-and-train-your-model)
3. [<span data-ttu-id="3cd99-120">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="3cd99-120">Evaluate your model</span></span>](#evaluate-your-model)
4. [<span data-ttu-id="3cd99-121">モデルを使用する</span><span class="sxs-lookup"><span data-stu-id="3cd99-121">Use your model</span></span>](#use-your-model)

## <a name="prerequisites"></a><span data-ttu-id="3cd99-122">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3cd99-122">Prerequisites</span></span>

* <span data-ttu-id="3cd99-123">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="3cd99-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="3cd99-124">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="3cd99-124">Select the appropriate machine learning task</span></span>

<span data-ttu-id="3cd99-125">レコメンデーションの問題にアプローチするには、映画のリストを推奨する、関連作品のリストを推奨するといった複数の方法がありますが、ここでは、ユーザーが特定の映画にどのような評価 (1 - 5) を付けるかを予測して、定義したしきい値よりも高い場合にその映画を推奨します (評価が高いほど、ユーザーが特定の映画を気に入る可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="3cd99-125">There are several ways to approach recommendation problems, such as recommending a list of movies or recommending a list of related products, but in this case you will predict what rating (1-5) a user will give to a particular movie and recommend that movie if it's higher than a defined threshold (the higher the rating, the higher the likelihood of a user liking a particular movie).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="3cd99-126">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="3cd99-126">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="3cd99-127">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="3cd99-127">Create a project</span></span>

1. <span data-ttu-id="3cd99-128">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="3cd99-129">**[ファイル]** > **[新規作成]** > **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="3cd99-130">**[新しいプロジェクト]** ダイアログで、**[Visual C#]** ノードを選択し、**[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="3cd99-131">次に、**[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="3cd99-132">**[名前]** テキスト ボックスに「MovieRecommender」と入力し、**[OK]** ボタンを選びます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-132">In the **Name** text box, type "MovieRecommender" and then select the **OK** button.</span></span>

2. <span data-ttu-id="3cd99-133">プロジェクトに *Data* という名前のディレクトリを作成して、データ セットを保存します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-133">Create a directory named *Data* in your project to store the data set:</span></span>

    <span data-ttu-id="3cd99-134">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="3cd99-135">「Data」と入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-135">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="3cd99-136">**Microsoft.ML** と **Microsoft.ML.Recommender** NuGet パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3cd99-136">Install the **Microsoft.ML** and **Microsoft.ML.Recommender** NuGet Packages:</span></span>

    <span data-ttu-id="3cd99-137">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="3cd99-138">[パッケージ ソース] として "nuget.org" を選択し、**[参照]** タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="3cd99-139">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、**[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="3cd99-140">**Microsoft.ML.Recommender** に対してこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-140">Repeat these steps for **Microsoft.ML.Recommender**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3cd99-141">このチュートリアルでは、**Microsoft.ML v0.11.0** と **Microsoft.ML.Recommender v0.11.0** を使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-141">This tutorial uses **Microsoft.ML v0.11.0** and **Microsoft.ML.Recommender v0.11.0**.</span></span>

4. <span data-ttu-id="3cd99-142">*Program.cs* の先頭に次の `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-142">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[UsingStatements](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="3cd99-143">データをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="3cd99-143">Download your data</span></span>

1. <span data-ttu-id="3cd99-144">2 つのデータセットをダウンロードし、以前に作成した *Data* フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-144">Download the two datasets and save them to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="3cd99-145">[*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) を右クリックして、[名前を付けてリンク先を保存] または [対象をファイルに保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-145">Right click on [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) and select "Save Link (or Target) As..."</span></span>
   * <span data-ttu-id="3cd99-146">[*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) 右クリックして、[名前を付けてリンク先を保存] または [対象をファイルに保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-146">Right click on [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="3cd99-147">\*.csv ファイルを、*Data* フォルダーに保存したことを確認します。または他の場所に保存した後に、\*.csv ファイルを *Data* フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-147">Make sure you either save the \*.csv files to the *Data* folder, or after you save it elsewhere, move the \*.csv files to the *Data* folder.</span></span>

2. <span data-ttu-id="3cd99-148">ソリューション エクスプローラーで、各 \*.csv ファイルを右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-148">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="3cd99-149">**[詳細設定]** で、**[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-149">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

   ![VS の [新しい場合はコピーする]](./media/movie-recommendation/copytoout.gif)

## <a name="load-your-data"></a><span data-ttu-id="3cd99-151">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="3cd99-151">Load your data</span></span>

<span data-ttu-id="3cd99-152">ML.NET プロセスの最初の手順では、モデルのトレーニングとテストのデータを準備して読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-152">The first step in the ML.NET process is to prepare and load your model training and testing data.</span></span>

<span data-ttu-id="3cd99-153">レコメンデーションの評価データは、`Train` と `Test` のデータセットに分割されます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-153">The recommendation ratings data is split into `Train` and `Test` datasets.</span></span> <span data-ttu-id="3cd99-154">`Train` データは、モデルを適合させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-154">The `Train` data is used to fit your model.</span></span> <span data-ttu-id="3cd99-155">`Test` データは、トレーニング済みモデルを使用して予測を行い、モデルのパフォーマンスを評価するのに使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-155">The `Test` data is used to make predictions with your trained model and evaluate model performance.</span></span> <span data-ttu-id="3cd99-156">`Train` データと `Test` データは通常、80 対 20 に分割されます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-156">It's common to have an 80/20 split with `Train` and `Test` data.</span></span>

<span data-ttu-id="3cd99-157">\*.csv ファイルからのデータのプレビューを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-157">Below is a preview of the data from your \*.csv files:</span></span>

![データのプレビュー](./media/movie-recommendation/csv-dataset-preview.png)

<span data-ttu-id="3cd99-159">\*.csv ファイルには、4 つの列があります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-159">In the \*.csv files, there are four columns:</span></span>

* `userId`
* `movieId`
* `rating`
* `timestamp`

<span data-ttu-id="3cd99-160">機械学習では、予測に使用される列は[特徴](../resources/glossary.md#feature)と呼ばれ、返された予測がある列は[ラベル](../resources/glossary.md#label)と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-160">In machine learning, the columns that are used to make a prediction are called [Features](../resources/glossary.md#feature), and the column with the returned prediction is called the [Label](../resources/glossary.md#label).</span></span>

<span data-ttu-id="3cd99-161">映画の評価を予測するので、rating (評価) 列が `Label` になります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-161">You want to predict movie ratings, so the rating column is the `Label`.</span></span> <span data-ttu-id="3cd99-162">他の 3 つの列 `userId`、`movieId`、`timestamp` はすべて、`Label` を予測するために使用される `Features` です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-162">The other three columns, `userId`, `movieId`, and `timestamp` are all `Features` used to predict the `Label`.</span></span>

| <span data-ttu-id="3cd99-163">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="3cd99-163">Features</span></span>      | <span data-ttu-id="3cd99-164">group1</span><span class="sxs-lookup"><span data-stu-id="3cd99-164">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

<span data-ttu-id="3cd99-165">`Label` を予測するために使用する `Features` を決めるかどうかは任意です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-165">It's up to you to decide which `Features` are used to predict the `Label`.</span></span> <span data-ttu-id="3cd99-166">最適な `Features` を選択を支援するため、[Permutation Feature Importance](../how-to-guides/determine-global-feature-importance-in-model.md) のような手法を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-166">You can also use methods like [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md) to help with selecting the best `Features`.</span></span>

<span data-ttu-id="3cd99-167">ここでは、`Feature` として `timestamp` 列を削除する必要があります。これは、タイムスタンプはユーザーが特定の映画をどのように評価するかにはまったく影響しないため、より正確な予測を行うことには役立たないからです。</span><span class="sxs-lookup"><span data-stu-id="3cd99-167">In this case, you should eliminate the `timestamp` column as a `Feature` because the timestamp does not really affect how a user rates a given movie and thus would not contribute to making a more accurate prediction:</span></span>

| <span data-ttu-id="3cd99-168">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="3cd99-168">Features</span></span>      | <span data-ttu-id="3cd99-169">group1</span><span class="sxs-lookup"><span data-stu-id="3cd99-169">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

<span data-ttu-id="3cd99-170">次に、入力クラスのデータ構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-170">Next you must define your data structure for the input class.</span></span>

<span data-ttu-id="3cd99-171">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-171">Add a new class to your project:</span></span>

1. <span data-ttu-id="3cd99-172">**ソリューション エクスプローラー**で、プロジェクトを右クリックして、**[追加]、[新しいアイテム]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-172">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="3cd99-173">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを「*MovieRatingData.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-173">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *MovieRatingData.cs*.</span></span> <span data-ttu-id="3cd99-174">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-174">Then, select the **Add** button.</span></span>

<span data-ttu-id="3cd99-175">コード エディターに *MovieRatingData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-175">The *MovieRatingData.cs* file opens in the code editor.</span></span> <span data-ttu-id="3cd99-176">*MovieRatingData.cs* の先頭に次の `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-176">Add the following `using` statement to the top of *MovieRatingData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="3cd99-177">既存のクラス定義を削除し、*MovieRatingData.cs* に次のコードを追加して、`MovieRating` というクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-177">Create a class called `MovieRating` by removing the existing class definition and adding the following code in *MovieRatingData.cs*:</span></span>

[!code-csharp[MovieRatingClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

<span data-ttu-id="3cd99-178">`MovieRating` は入力データ クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-178">`MovieRating` specifies an input data class.</span></span> <span data-ttu-id="3cd99-179">[LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 属性は、データセット内のどの列 (列インデックス) を読み込むかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-179">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="3cd99-180">`userId` 列と `movieId` 列が `Features` (`Label` を予測するためのモデルへの入力) で、rating (評価) 列が予測する `Label` (モデルの出力) です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-180">The `userId` and `movieId` columns are your `Features` (the inputs you will give the model to predict the `Label`), and the rating column is the `Label` that you will predict (the output of the model).</span></span>

<span data-ttu-id="3cd99-181">*MovieRatingData.cs* で `MovieRating` クラスの後に次のコードを追加して、予測結果を表す別のクラス `MovieRatingPrediction` を作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-181">Create another class, `MovieRatingPrediction`, to represent predicted results by adding the following code after the `MovieRating` class in *MovieRatingData.cs*:</span></span>

[!code-csharp[PredictionClass](~/samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

<span data-ttu-id="3cd99-182">*Program.cs* で、`Console.WriteLine("Hello World!")` を `Main()` 内の次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-182">In *Program.cs*, replace the `Console.WriteLine("Hello World!")` with the following code inside `Main()`:</span></span>

[!code-csharp[MLContext](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MLContext "Add MLContext")]

<span data-ttu-id="3cd99-183">[MLContext クラス](xref:Microsoft.ML.MLContext)は、すべての ML.NET 操作の開始点で、`mlContext` を初期化することで、モデル作成ワークフローのオブジェクト間で共有できる新しい ML.NET 環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-183">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="3cd99-184">これは Entity Framework における `DBContext` と概念的には同じです。</span><span class="sxs-lookup"><span data-stu-id="3cd99-184">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="3cd99-185">`Main()` の後に、`LoadData()` と呼ばれるメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-185">After `Main()`, create a method called `LoadData()`:</span></span>

```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{

}
```

> [!NOTE]
> <span data-ttu-id="3cd99-186">このメソッドは、次の手順で return ステートメントを追加するまでエラーになります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-186">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="3cd99-187">`LoadData()` の次のコード行として以下を追加して、データ パス変数を初期化し、\*.csv ファイルからデータを読み込み、`Train` と `Test` のデータを `IDataView` オブジェクトとして返します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-187">Initialize your data path variables, load the data from the \*.csv files, and return the `Train` and `Test` data as `IDataView` objects by adding the following as the next line of code in `LoadData()`:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadData "Load data from data paths")]

<span data-ttu-id="3cd99-188">ML.NET 内のデータは、[IDataView クラス](xref:Microsoft.ML.IDataView)として表されます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-188">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="3cd99-189">`IDataView` は、表形式のデータ (数値とテキスト) を表すための柔軟で効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-189">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="3cd99-190">データはテキスト ファイルから、またはリアルタイムで (SQL データベースやログ ファイルなど) `IDataView` オブジェクトに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-190">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="3cd99-191">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) は、データ スキーマを定義し、ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-191">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="3cd99-192">データ パス変数を取得して、`IDataView` を返します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-192">It takes in the data path variables and returns an `IDataView`.</span></span> <span data-ttu-id="3cd99-193">ここでは、`Test` ファイルと `Train` ファイルへのパスを指定して、テキスト ファイル ヘッダー (列名を正しく使用できるようにするため) とコンマ文字のデータ区切り記号 (既定の区切り記号はタブ) の両方を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-193">In this case, you provide the path for your `Test` and `Train` files and indicate both the text file header (so it can use the column names properly) and the comma character data separator (the default separator is a tab).</span></span>

<span data-ttu-id="3cd99-194">`Main()` メソッドの次の 2 つのコード行として以下を追加して、`LoadData()` メソッドを呼び出し、`Train` と `Test` のデータを返します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-194">Add the following as the next two lines of code in the `Main()` method to call your `LoadData()` method and return the `Train` and `Test` data:</span></span>

[!code-csharp[LoadDataMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadDataMain "Add LoadData method to Main")]

## <a name="build-and-train-your-model"></a><span data-ttu-id="3cd99-195">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="3cd99-195">Build and train your model</span></span>

<span data-ttu-id="3cd99-196">ML.NET には、次の 3 つの主要な概念があります。[データ](../basic-concepts-model-training-in-mldotnet.md#data)、[トランスフォーマー](../basic-concepts-model-training-in-mldotnet.md#transformer)、および[エスティメーター](../basic-concepts-model-training-in-mldotnet.md#estimator)です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-196">There are three major concepts in ML.NET: [Data](../basic-concepts-model-training-in-mldotnet.md#data), [Transformers](../basic-concepts-model-training-in-mldotnet.md#transformer), and [Estimators](../basic-concepts-model-training-in-mldotnet.md#estimator).</span></span>

<span data-ttu-id="3cd99-197">機械学習のトレーニング アルゴリズムには、特定の形式のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-197">Machine learning training algorithms require data in a certain format.</span></span> <span data-ttu-id="3cd99-198">`Transformers` は表形式のデータを互換性のある形式に変換 (トランスフォーム) するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-198">`Transformers` are used to transform tabular data to a compatible format.</span></span>

![トランスフォーマーの画像](./media/movie-recommendation/transformer.png)

<span data-ttu-id="3cd99-200">`Estimators` を作成して、ML.NET で `Transformers` を作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-200">You create `Transformers` in ML.NET by creating `Estimators`.</span></span> <span data-ttu-id="3cd99-201">`Estimators` はデータを取得して `Transformers` を返します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-201">`Estimators` take in data and return `Transformers`.</span></span>

![エスティメーターの画像](./media/movie-recommendation/estimator.png)

<span data-ttu-id="3cd99-203">モデルのトレーニングに使用するレコメンデーション トレーニング アルゴリズムは、`Estimator` の一例です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-203">The recommendation training algorithm you will use for training your model is an example of an `Estimator`.</span></span>

<span data-ttu-id="3cd99-204">次の手順に従って `Estimator` を構築します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-204">Build an `Estimator` with the following steps:</span></span>

<span data-ttu-id="3cd99-205">`LoadData()` メソッドの直後に、次のコードを使用して `BuildAndTrainModel()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-205">Create the `BuildAndTrainModel()` method, just after the `LoadData()` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{

}
```

> [!NOTE]
> <span data-ttu-id="3cd99-206">このメソッドは、次の手順で return ステートメントを追加するまでエラーになります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-206">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="3cd99-207">次のコードを `BuildAndTrainModel()` に追加して、データ変換を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-207">Define the data transformations by adding the following code to `BuildAndTrainModel()`:</span></span>

[!code-csharp[DataTransformations](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#DataTransformations "Define data transformations")]

<span data-ttu-id="3cd99-208">`userId` と `movieId` は実際の値ではなく、ユーザーと映画のタイトルを表しているため、[MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) メソッドを使って `userId` と `movieId` をそれぞれ数値キー型の `Feature` 列 (レコメンデーション アルゴリズムで受け入れられる形式) に変換して、新しいデータセットの列として追加します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-208">Since `userId` and `movieId` represent users and movie titles, not real values, you use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform each `userId` and each `movieId` into a numeric key type `Feature` column (a format accepted by recommendation algorithms) and add them as new dataset columns:</span></span>

| <span data-ttu-id="3cd99-209">userId</span><span class="sxs-lookup"><span data-stu-id="3cd99-209">userId</span></span> | <span data-ttu-id="3cd99-210">movieId</span><span class="sxs-lookup"><span data-stu-id="3cd99-210">movieId</span></span> | <span data-ttu-id="3cd99-211">group1</span><span class="sxs-lookup"><span data-stu-id="3cd99-211">Label</span></span> | <span data-ttu-id="3cd99-212">userIdEncoded</span><span class="sxs-lookup"><span data-stu-id="3cd99-212">userIdEncoded</span></span> | <span data-ttu-id="3cd99-213">movieIdEncoded</span><span class="sxs-lookup"><span data-stu-id="3cd99-213">movieIdEncoded</span></span> |
| ------------- |:-------------:| -----:|-----:|-----:|
| <span data-ttu-id="3cd99-214">1</span><span class="sxs-lookup"><span data-stu-id="3cd99-214">1</span></span> | <span data-ttu-id="3cd99-215">1</span><span class="sxs-lookup"><span data-stu-id="3cd99-215">1</span></span> | <span data-ttu-id="3cd99-216">4</span><span class="sxs-lookup"><span data-stu-id="3cd99-216">4</span></span> | <span data-ttu-id="3cd99-217">userKey1</span><span class="sxs-lookup"><span data-stu-id="3cd99-217">userKey1</span></span> | <span data-ttu-id="3cd99-218">movieKey1</span><span class="sxs-lookup"><span data-stu-id="3cd99-218">movieKey1</span></span> |
| <span data-ttu-id="3cd99-219">1</span><span class="sxs-lookup"><span data-stu-id="3cd99-219">1</span></span> | <span data-ttu-id="3cd99-220">3</span><span class="sxs-lookup"><span data-stu-id="3cd99-220">3</span></span> | <span data-ttu-id="3cd99-221">4</span><span class="sxs-lookup"><span data-stu-id="3cd99-221">4</span></span> | <span data-ttu-id="3cd99-222">userKey1</span><span class="sxs-lookup"><span data-stu-id="3cd99-222">userKey1</span></span> | <span data-ttu-id="3cd99-223">movieKey2</span><span class="sxs-lookup"><span data-stu-id="3cd99-223">movieKey2</span></span> |
| <span data-ttu-id="3cd99-224">1</span><span class="sxs-lookup"><span data-stu-id="3cd99-224">1</span></span> | <span data-ttu-id="3cd99-225">6</span><span class="sxs-lookup"><span data-stu-id="3cd99-225">6</span></span> | <span data-ttu-id="3cd99-226">4</span><span class="sxs-lookup"><span data-stu-id="3cd99-226">4</span></span> | <span data-ttu-id="3cd99-227">userKey1</span><span class="sxs-lookup"><span data-stu-id="3cd99-227">userKey1</span></span> | <span data-ttu-id="3cd99-228">movieKey3</span><span class="sxs-lookup"><span data-stu-id="3cd99-228">movieKey3</span></span> |

<span data-ttu-id="3cd99-229">機械学習アルゴリズムを選択し、`BuildAndTrainModel()` 内に次のコード行として以下を追加することで、データ変換定義にそれを追加します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-229">Choose the machine learning algorithm and append it to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddAlgorithm](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#AddAlgorithm "Add the training algorithm with options")]

<span data-ttu-id="3cd99-230">[MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) はレコメンデーション トレーニング アルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="3cd99-230">The [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) is your recommendation training algorithm.</span></span>  <span data-ttu-id="3cd99-231">[行列因子分解](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems))は、ユーザーが過去に作品をどのように評価したかに関するデータがある場合 (このチュートリアルでのデータセットがそれにあたります) のレコメンデーションへの一般的なアプローチです。</span><span class="sxs-lookup"><span data-stu-id="3cd99-231">[Matrix Factorization](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) is a common approach to recommendation when you have data on how users have rated products in the past, which is the case for the datasets in this tutorial.</span></span> <span data-ttu-id="3cd99-232">使用可能なさまざまなデータがある場合は、他のレコメンデーション アゴリズムがあります (詳細については、後述の「[その他のレコメンデーション アルゴリズム](#other-recommendation-algorithms)」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="3cd99-232">There are other recommendation algorithms for when you have different data available (see the [Other recommendation algorithms](#other-recommendation-algorithms) section below to learn more).</span></span>

<span data-ttu-id="3cd99-233">ここでは、`Matrix Factorization` アルゴリズムは "協調フィルタリング" と呼ばれる手法を使用します。これは、特定の問題についてユーザー 1 とユーザー 2 の意見が同じ場合、別の問題についてもユーザー 1 はユーザー 2 と同じように感じる可能性が高いと仮定します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-233">In this case, the `Matrix Factorization` algorithm uses a method called "collaborative filtering", which assumes that if User 1 has the same opinion as User 2 on a certain issue, then User 1 is more likely to feel the same way as User 2 about a different issue.</span></span>

<span data-ttu-id="3cd99-234">たとえば、ユーザー 1 とユーザー 2 が同じように映画を評価している場合、ユーザー 2 はユーザー 1 が鑑賞して高く評価した映画を気に入る可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-234">For instance, if User 1 and User 2 rate movies similarly, then User 2 is more likely to enjoy a movie that User 1 has watched and rated highly:</span></span>

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| <span data-ttu-id="3cd99-235">ユーザー 1</span><span class="sxs-lookup"><span data-stu-id="3cd99-235">User 1</span></span> | <span data-ttu-id="3cd99-236">映画を鑑賞して気に入った</span><span class="sxs-lookup"><span data-stu-id="3cd99-236">Watched and liked movie</span></span> | <span data-ttu-id="3cd99-237">映画を鑑賞して気に入った</span><span class="sxs-lookup"><span data-stu-id="3cd99-237">Watched and liked movie</span></span> | <span data-ttu-id="3cd99-238">映画を鑑賞して気に入った</span><span class="sxs-lookup"><span data-stu-id="3cd99-238">Watched and liked movie</span></span> |
| <span data-ttu-id="3cd99-239">ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="3cd99-239">User 2</span></span> | <span data-ttu-id="3cd99-240">映画を鑑賞して気に入った</span><span class="sxs-lookup"><span data-stu-id="3cd99-240">Watched and liked movie</span></span> | <span data-ttu-id="3cd99-241">映画を鑑賞して気に入った</span><span class="sxs-lookup"><span data-stu-id="3cd99-241">Watched and liked movie</span></span> | <span data-ttu-id="3cd99-242">まだ鑑賞していない - おすすめの映画</span><span class="sxs-lookup"><span data-stu-id="3cd99-242">Has not watched -- RECOMMEND movie</span></span> |

<span data-ttu-id="3cd99-243">`Matrix Factorization` トレーナーには、複数の[オプション](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options)があります。これについては後述の「[アルゴリズムのハイパーパラメーター](#algorithm-hyperparameters)」セクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-243">The `Matrix Factorization` trainer has several [Options](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), which you can read more about in the [Algorithm hyperparameters](#algorithm-hyperparameters) section below.</span></span>

<span data-ttu-id="3cd99-244">`BuildAndTrainModel()` メソッドの次のコード行として以下を追加して、モデルを `Train` データに適合させ、トレーニング済みモデルを返します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-244">Fit the model to the `Train` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[FitModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#FitModel "Call the Fit method and return back the trained model")]

<span data-ttu-id="3cd99-245">[Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) メソッドは、指定されたトレーニング データセットを使用してモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="3cd99-245">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model with the provided training dataset.</span></span> <span data-ttu-id="3cd99-246">正確には、データを変換してトレーニングを適用することで、`Estimator` 定義を実行し、トレーニング済みモデル (`Transformer`) を返します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-246">Technically, it executes the `Estimator` definitions by transforming the data and applying the training, and it returns back the trained model, which is a `Transformer`.</span></span>

<span data-ttu-id="3cd99-247">`Main()` メソッドの次のコード行として以下を追加して、`BuildAndTrainModel()` メソッドを呼び出し、トレーニング済みモデルを返します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-247">Add the following as the next line of code in the `Main()` method to call your `BuildAndTrainModel()` method and return the trained model:</span></span>

[!code-csharp[BuildTrainModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a><span data-ttu-id="3cd99-248">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="3cd99-248">Evaluate your model</span></span>

<span data-ttu-id="3cd99-249">モデルをトレーニングしたら、テスト データを使用してモデルのパフォーマンスを評価します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-249">Once you have trained your model, use your test data to evaluate how your model is performing.</span></span>

<span data-ttu-id="3cd99-250">`BuildAndTrainModel()` メソッドの直後に、次のコードを使用して `EvaluateModel()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-250">Create the `EvaluateModel()` method, just after the `BuildAndTrainModel()` method, using the following code:</span></span>

```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{

}
```

<span data-ttu-id="3cd99-251">次のコードを `EvaluateModel()` に追加して、`Test` データを変換します。[!code-csharp[Transform](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]</span><span class="sxs-lookup"><span data-stu-id="3cd99-251">Transform the `Test` data by adding the following code to `EvaluateModel()`: [!code-csharp[Transform](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]</span></span>

<span data-ttu-id="3cd99-252">[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) メソッドはテスト データセットの指定した複数の入力行に対して予測を行います。</span><span class="sxs-lookup"><span data-stu-id="3cd99-252">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="3cd99-253">`EvaluateModel()` メソッドの次のコード行として以下を追加して、モデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-253">Evaluate the model by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

<span data-ttu-id="3cd99-254">予測セットができたら、[Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) メソッドがモデルを評価します。これは予測された値をテスト データセット内の実際の `Labels` と比較して、モデルのパフォーマンスのメトリックを返します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-254">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="3cd99-255">`EvaluateModel()` メソッドの次のコード行として以下を追加して、評価メトリックをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-255">Print your evaluation metrics to the console by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[PrintMetrics](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintMetrics "Print the evaluation metrics")]

<span data-ttu-id="3cd99-256">`Main()` メソッドの次のコード行として以下を追加して、`EvaluateModel()` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-256">Add the following as the next line of code in the `Main()` method to call your `EvaluateModel()` method:</span></span>

[!code-csharp[EvaluateModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

<span data-ttu-id="3cd99-257">ここまでの出力は、次のテキストのようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="3cd99-257">The output so far should look similar to the following text:</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

<span data-ttu-id="3cd99-258">この出力には 20 のイテレーションがあります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-258">In this output, there are 20 iterations.</span></span> <span data-ttu-id="3cd99-259">イテレーションごとに測定誤差が低下し、0 にどんどん近づいていきます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-259">In each iteration, the measure of error decreases and converges closer and closer to 0.</span></span>

<span data-ttu-id="3cd99-260">モデル予測値とテスト データセットで観察された値の差を測定するために `root of mean squared error` (RMS または RMSE) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-260">The `root of mean squared error` (RMS or RMSE) is used to measure the differences between the model predicted values and the test dataset observed values.</span></span> <span data-ttu-id="3cd99-261">厳密には、これはエラーの 2 乗の平均の平方根です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-261">Technically it's the square root of the average of the squares of the errors.</span></span> <span data-ttu-id="3cd99-262">RMS が低いほど、優れたモデルになります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-262">The lower it is, the better the model is.</span></span>

<span data-ttu-id="3cd99-263">`R Squared` は、データがモデルにどの程度適合しているかを示します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-263">`R Squared` indicates how well data fits a model.</span></span> <span data-ttu-id="3cd99-264">0 ～ 1 の値になります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-264">Ranges from 0 to 1.</span></span> <span data-ttu-id="3cd99-265">値 0 は、データがランダムであるか、モデルに適合できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-265">A value of 0 means that the data is random or otherwise can't be fit to the model.</span></span> <span data-ttu-id="3cd99-266">値 1 は、モデルがデータと完全に一致していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-266">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="3cd99-267">`R Squared` スコアは可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-267">You want your `R Squared` score to be as close to 1 as possible.</span></span>

<span data-ttu-id="3cd99-268">優れたモデルの構築は、反復的なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="3cd99-268">Building successful models is an iterative process.</span></span> <span data-ttu-id="3cd99-269">このチュートリアルでは、モデルのトレーニングを短時間で実行するために小さなデータセットを使用しているため、このモデルの品質は最初は低くなっています。</span><span class="sxs-lookup"><span data-stu-id="3cd99-269">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="3cd99-270">このモデルの品質に満足できなければ、大規模なトレーニング データセットを使用するか、別のトレーニング アルゴリズムとアルゴリズムごとに異なるハイパーパラメーターを選択することで、モデルを改良することを試行できます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-270">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span> <span data-ttu-id="3cd99-271">詳細については、後述する「[モデルを改良する](#improve-your-model)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cd99-271">For more information, check out the [Improve your model](#improve-your-model) section below.</span></span>

## <a name="use-your-model"></a><span data-ttu-id="3cd99-272">モデルを使用する</span><span class="sxs-lookup"><span data-stu-id="3cd99-272">Use your model</span></span>

<span data-ttu-id="3cd99-273">これでトレーニング済みのモデルを使用して、新しいデータで予測を行えます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-273">Now you can use your trained model to make predictions on new data.</span></span>

<span data-ttu-id="3cd99-274">`EvaluateModel()` メソッドの直後に、次のコードを使用して `UseModelForSinglePrediction()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-274">Create the `UseModelForSinglePrediction()` method, just after the `EvaluateModel()` method, using the following code:</span></span>

```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="3cd99-275">次のコードを `UseModelForSinglePrediction()` に追加して評価を予測するには、`PredictionEngine` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-275">Use the `PredictionEngine` to predict the rating by adding the following code to `UseModelForSinglePrediction()`:</span></span>

[!code-csharp[PredictionEngine](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PredictionEngine "Create Prediction Engine")]

<span data-ttu-id="3cd99-276">[PredictionEngine クラス](xref:Microsoft.ML.PredictionEngine%602)は、データの 1 つのインスタンスを渡してから、このインスタンスで予測を実行できる便利な API です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-276">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass a single instance of data and then perform a prediction on this single instance of data.</span></span>

<span data-ttu-id="3cd99-277">`testInput` と呼ばれる `MovieRating` のインスタンスを作成し、`UseModelForSinglePrediction()` メソッドの次のコード行として以下を追加することで、それを PredictionEngine に渡します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-277">Create an instance of `MovieRating` called `testInput` and pass it to the Prediction Engine by adding the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[MakeSinglePrediction](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

<span data-ttu-id="3cd99-278">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 関数はデータの 1 つの列で予測を行います。</span><span class="sxs-lookup"><span data-stu-id="3cd99-278">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span>

<span data-ttu-id="3cd99-279">そして、`Score` (予測された評価) を使用して、movieId 10 の映画をユーザー 6 に推奨するかどうかを決めることができます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-279">You can then use the `Score`, or the predicted rating, to determine whether you want to recommend the movie with movieId 10 to user 6.</span></span> <span data-ttu-id="3cd99-280">`Score` が高くなるほど、ユーザーが特定の映画を気に入る可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-280">The higher the `Score`, the higher the likelihood of a user liking a particular movie.</span></span> <span data-ttu-id="3cd99-281">ここでは、予測された評価が 3.5 より高い映画を推奨するとします。</span><span class="sxs-lookup"><span data-stu-id="3cd99-281">In this case, let’s say that you recommend movies with a predicted rating of > 3.5.</span></span>

<span data-ttu-id="3cd99-282">結果を出力するには、`UseModelForSinglePrediction()` メソッドの次のコード行として以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-282">To print the results, add the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[PrintResults](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintResults "Print the recommendation prediction results")]

<span data-ttu-id="3cd99-283">`Main()` メソッドの次のコード行として以下を追加して、`UseModelForSinglePrediction()` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-283">Add the following as the next line of code in the `Main()` method to call your `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[UseModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

<span data-ttu-id="3cd99-284">このメソッドの出力は、次のテキストのようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="3cd99-284">The output of this method should look similar to the following text:</span></span>

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a><span data-ttu-id="3cd99-285">モデルを保存する</span><span class="sxs-lookup"><span data-stu-id="3cd99-285">Save your model</span></span>

<span data-ttu-id="3cd99-286">エンド ユーザー アプリケーションでモデルを使用して予測を行うには、最初にモデルを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-286">To use your model to make predictions in end-user applications, you must first save the model.</span></span>

<span data-ttu-id="3cd99-287">`UseModelForSinglePrediction()` メソッドの直後に、次のコードを使用して `SaveModel()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-287">Create the `SaveModel()` method, just after the `UseModelForSinglePrediction()` method, using the following code:</span></span>

```csharp
public static void SaveModel(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="3cd99-288">`SaveModel()` メソッドに次のコードを追加して、トレーニング済みモデルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-288">Save your trained model by adding the following code in the `SaveModel()` method:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModel "Save the model to a zip file")]

<span data-ttu-id="3cd99-289">このメソッドは、トレーニング済みモデルを ("Data" フォルダー内の) .zip ファイルに保存します。保存されたファイルは、他の .NET アプリケーションで予測を行うために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-289">This method saves your trained model to a .zip file (in the "Data" folder), which can then be used in other .NET applications to make predictions.</span></span>

<span data-ttu-id="3cd99-290">`Main()` メソッドの次のコード行として以下を追加して、`SaveModel()` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-290">Add the following as the next line of code in the `Main()` method to call your `SaveModel()` method:</span></span>

[!code-csharp[SaveModelMain](~/samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a><span data-ttu-id="3cd99-291">保存したモデルを使用する</span><span class="sxs-lookup"><span data-stu-id="3cd99-291">Use your saved model</span></span>

<span data-ttu-id="3cd99-292">トレーニング済みモデルを保存すると、さまざまな環境でそのモデルを利用できるようになります (トレーニング済みの機械学習モデルを運用化する方法については、[「ハウツー ガイド」](../how-to-guides/consuming-model-ml-net.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3cd99-292">Once you have saved your trained model, you can consume the model in different environments (see the ["How-to guide"](../how-to-guides/consuming-model-ml-net.md) to learn how to operationalize a trained machine learning model in apps).</span></span>

## <a name="results"></a><span data-ttu-id="3cd99-293">結果</span><span class="sxs-lookup"><span data-stu-id="3cd99-293">Results</span></span>

<span data-ttu-id="3cd99-294">上記の手順を実行した後、コンソール アプリを実行します (Ctrl + F5)。</span><span class="sxs-lookup"><span data-stu-id="3cd99-294">After following the steps above, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="3cd99-295">上記の 1 つの予測の結果は、次のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="3cd99-295">Your results from the single prediction above should be similar to the following.</span></span> <span data-ttu-id="3cd99-296">警告メッセージまたは処理中のメッセージが表示される場合がありますが、わかりやすくするため、これらのメッセージは結果から削除してあります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-296">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

<span data-ttu-id="3cd99-297">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="3cd99-297">Congratulations!</span></span> <span data-ttu-id="3cd99-298">映画をお勧めするための機械学習モデルが正常に作成されました。</span><span class="sxs-lookup"><span data-stu-id="3cd99-298">You've now successfully built a machine learning model for recommending movies.</span></span> <span data-ttu-id="3cd99-299">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-299">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="improve-your-model"></a><span data-ttu-id="3cd99-300">モデルを改良する</span><span class="sxs-lookup"><span data-stu-id="3cd99-300">Improve your model</span></span>

<span data-ttu-id="3cd99-301">より正確な予測を取得するために、モデルのパフォーマンスを向上させることができるいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-301">There are several ways that you can improve the performance of your model so that you can get more accurate predictions.</span></span>

### <a name="data"></a><span data-ttu-id="3cd99-302">データ</span><span class="sxs-lookup"><span data-stu-id="3cd99-302">Data</span></span>

<span data-ttu-id="3cd99-303">各ユーザーと映画 ID の十分なサンプルが含まれたトレーニング データをさらに追加することで、レコメンデーション モデルの品質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-303">Adding more training data that has enough samples for each user and movie id can help improve the quality of the recommendation model.</span></span>

<span data-ttu-id="3cd99-304">[クロス検証](../how-to-guides/train-cross-validation-ml-net.md)は、モデルを評価するための手法で、(このチュートリアルで行ったようにデータセットからテスト データを抽出するのではなく) データをサブセットにランダムに分割して、一部のグループをトレーニング データとして取得し、一部のグループをテスト データとして取得します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-304">[Cross validation](../how-to-guides/train-cross-validation-ml-net.md) is a technique for evaluating models that randomly splits up data into subsets (instead of extracting out test data from the dataset like you did in this tutorial) and takes some of the groups as train data and some of the groups as test data.</span></span> <span data-ttu-id="3cd99-305">この手法は、モデルの品質に関しては、トレーニングとテストを分割するよりも優れています。</span><span class="sxs-lookup"><span data-stu-id="3cd99-305">This method outperforms making a train-test split in terms of model quality.</span></span>

### <a name="features"></a><span data-ttu-id="3cd99-306">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="3cd99-306">Features</span></span>

<span data-ttu-id="3cd99-307">このチュートリアルでは、データセットで提供される 3 つの `Features` (`user id`、`movie id`、`rating`) のみを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-307">In this tutorial, you only use the three `Features` (`user id`, `movie id`, and `rating`) that are provided by the dataset.</span></span>

<span data-ttu-id="3cd99-308">これは出発点としては適切ですが、実際には、データセットに他の属性や `Features` (年齢、性別、地理的場所など) が含まれている場合には、これらを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-308">While this is a good start, in reality you might want to add other attributes or `Features` (for example, age, gender, geo-location, etc.) if they are included in the dataset.</span></span> <span data-ttu-id="3cd99-309">より関連性の高い `Features` を追加することで、レコメンデーション モデルのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-309">Adding more relevant `Features` can help improve the performance of your recommendation model.</span></span>

<span data-ttu-id="3cd99-310">自分の機械学習タスクにとってどの `Features` が最も関連性が高いかがわからない場合は、最も影響が大きい `Features` を検出するために ML.NET で提供されている Feature Contribution Calculation (FCC) および [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md) を利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-310">If you are unsure about which `Features` might be the most relevant for your machine learning task, you can also make use of Feature Contribution Calculation (FCC) and [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md), which ML.NET provides to discover the most influential `Features`.</span></span>

### <a name="algorithm-hyperparameters"></a><span data-ttu-id="3cd99-311">アルゴリズムのハイパーパラメーター</span><span class="sxs-lookup"><span data-stu-id="3cd99-311">Algorithm hyperparameters</span></span>

<span data-ttu-id="3cd99-312">ML.NET には優れたトレーニング アルゴリズムが既定で提供されていますが、アルゴリズムの[ハイパーパラメーター](../resources/glossary.md#hyperparameter)を変更することで、パフォーマンスをさらに微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-312">While ML.NET provides good default training algorithms, you can further fine-tune performance by changing the algorithm's [hyperparameters](../resources/glossary.md#hyperparameter).</span></span>

<span data-ttu-id="3cd99-313">`Matrix Factorization` の場合、[NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) や [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) などのハイパーパラメーターを使用して、より良い結果が出るかどうかを実験することができます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-313">For `Matrix Factorization`, you can experiment with hyperparameters such as [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) and [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) to see if that gives you better results.</span></span>

<span data-ttu-id="3cd99-314">たとえば、このチュートリアルでのアルゴリズムのオプションは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-314">For instance, in this tutorial the algorithm options are:</span></span>

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded",
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a><span data-ttu-id="3cd99-315">その他のレコメンデーション アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="3cd99-315">Other Recommendation Algorithms</span></span>

<span data-ttu-id="3cd99-316">協調フィルタリングを使用した行列因子分解アルゴリズムは、映画のレコメンデーションを実行するための唯一のアプローチです。</span><span class="sxs-lookup"><span data-stu-id="3cd99-316">The matrix factorization algorithm with collaborative filtering is only one approach for performing movie recommendations.</span></span> <span data-ttu-id="3cd99-317">利用可能な評価データがなく、ユーザーから映画の履歴を入手するしかない場合がよくあります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-317">In many cases, you may not have the ratings data available and only have movie history available from users.</span></span> <span data-ttu-id="3cd99-318">または、ユーザーの評価データ以上のものがある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3cd99-318">In other cases, you may have more than just the user’s rating data.</span></span>

| <span data-ttu-id="3cd99-319">アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="3cd99-319">Algorithm</span></span>       | <span data-ttu-id="3cd99-320">シナリオ</span><span class="sxs-lookup"><span data-stu-id="3cd99-320">Scenario</span></span>           | <span data-ttu-id="3cd99-321">サンプル</span><span class="sxs-lookup"><span data-stu-id="3cd99-321">Sample</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="3cd99-322">1 つのクラスの行列因子分解</span><span class="sxs-lookup"><span data-stu-id="3cd99-322">One Class Matrix Factorization</span></span> | <span data-ttu-id="3cd99-323">userId と movieId しかない場合はこれを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-323">Use this when you only have userId and movieId.</span></span> <span data-ttu-id="3cd99-324">このレコメンデーション スタイルは、共同購入シナリオ (よく一緒に購入される製品) に基づいています。つまり、顧客の購入履歴に基づいて、一連の製品を顧客に推奨します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-324">This style of recommendation is based upon the co-purchase scenario, or products frequently bought together, which means it will recommend to customers a set of products based upon their own purchase order history.</span></span> | [<span data-ttu-id="3cd99-325">> 試す</span><span class="sxs-lookup"><span data-stu-id="3cd99-325">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| <span data-ttu-id="3cd99-326">Field Aware Factorization Machines</span><span class="sxs-lookup"><span data-stu-id="3cd99-326">Field Aware Factorization Machines</span></span> | <span data-ttu-id="3cd99-327">userId、productId、rating 以外の特徴 (製品の説明や製品の価格など) がある場合にはこれを使用してレコメンデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-327">Use this to make recommendations when you have more Features beyond userId, productId, and rating (such as product description or product price).</span></span> <span data-ttu-id="3cd99-328">この手法では協調フィルタリング アプローチも使用します。</span><span class="sxs-lookup"><span data-stu-id="3cd99-328">This method also uses a collaborative filtering approach.</span></span> | [<span data-ttu-id="3cd99-329">> 試す</span><span class="sxs-lookup"><span data-stu-id="3cd99-329">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a><span data-ttu-id="3cd99-330">新規ユーザー シナリオ</span><span class="sxs-lookup"><span data-stu-id="3cd99-330">New user scenario</span></span>

<span data-ttu-id="3cd99-331">協調フィルタリングで一般的な問題の 1 つは、推測するための以前のデータがない新規ユーザーがいる場合のコールド スタートの問題です。</span><span class="sxs-lookup"><span data-stu-id="3cd99-331">One common problem in collaborative filtering is the cold start problem, which is when you have a new user with no previous data to draw inferences from.</span></span> <span data-ttu-id="3cd99-332">この問題は多くの場合、新規ユーザーにプロファイルを作成して、たとえば過去に見た映画を評価してもらうことで解決できます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-332">This problem is often solved by asking new users to create a profile and, for instance, rate movies they have seen in the past.</span></span> <span data-ttu-id="3cd99-333">この手法はユーザーに多少の負担をかけることになりますが、評価履歴がない新規ユーザーの開始データが得られます。</span><span class="sxs-lookup"><span data-stu-id="3cd99-333">While this method puts some burden on the user, it provides some starting data for new users with no rating history.</span></span>

## <a name="resources"></a><span data-ttu-id="3cd99-334">リソース</span><span class="sxs-lookup"><span data-stu-id="3cd99-334">Resources</span></span>

<span data-ttu-id="3cd99-335">このチュートリアルで使用したデータは、[MovieLens データセット](http://files.grouplens.org/datasets/movielens/)から派生しています。</span><span class="sxs-lookup"><span data-stu-id="3cd99-335">The data used in this tutorial is derived from [MovieLens Dataset](http://files.grouplens.org/datasets/movielens/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3cd99-336">次の手順</span><span class="sxs-lookup"><span data-stu-id="3cd99-336">Next steps</span></span>

<span data-ttu-id="3cd99-337">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="3cd99-337">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="3cd99-338">機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="3cd99-338">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="3cd99-339">データを準備して読み込む</span><span class="sxs-lookup"><span data-stu-id="3cd99-339">Prepare and load your data</span></span>
> * <span data-ttu-id="3cd99-340">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="3cd99-340">Build and train a model</span></span>
> * <span data-ttu-id="3cd99-341">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="3cd99-341">Evaluate a model</span></span>
> * <span data-ttu-id="3cd99-342">モデルを展開して使用する</span><span class="sxs-lookup"><span data-stu-id="3cd99-342">Deploy and consume a model</span></span>

<span data-ttu-id="3cd99-343">さらに詳しく学習するには、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="3cd99-343">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3cd99-344">感情分析</span><span class="sxs-lookup"><span data-stu-id="3cd99-344">Sentiment Analysis</span></span>](sentiment-analysis.md)
