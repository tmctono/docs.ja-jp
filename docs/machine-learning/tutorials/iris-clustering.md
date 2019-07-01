---
title: 'チュートリアル: あやめ花の分類 - K-means クラスタリング'
description: クラスタリングのシナリオで ML.NET を使用する方法について説明します
author: pkulikov
ms.author: johalex
ms.date: 05/16/2019
ms.topic: tutorial
ms.custom: mvc, seodec18, title-hack-0516
ms.openlocfilehash: 965408a180245712ceda2c3c17bdf42755af1c2c
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402451"
---
# <a name="tutorial-categorize-iris-flowers-using-k-means-clustering-with-mlnet"></a><span data-ttu-id="63a78-103">チュートリアル: ML.NET でクラスタリングを使用してあやめの花を分類する</span><span class="sxs-lookup"><span data-stu-id="63a78-103">Tutorial: Categorize iris flowers using k-means clustering with ML.NET</span></span>

<span data-ttu-id="63a78-104">このチュートリアルでは、ML.NET を使って[あやめのデータ セット](https://en.wikipedia.org/wiki/Iris_flower_data_set)の[クラスタリング モデル](../resources/tasks.md#clustering)を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="63a78-104">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="63a78-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="63a78-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="63a78-106">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="63a78-106">Understand the problem</span></span>
> - <span data-ttu-id="63a78-107">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="63a78-107">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="63a78-108">データを準備する</span><span class="sxs-lookup"><span data-stu-id="63a78-108">Prepare the data</span></span>
> - <span data-ttu-id="63a78-109">データを読み込んで変換する</span><span class="sxs-lookup"><span data-stu-id="63a78-109">Load and transform the data</span></span>
> - <span data-ttu-id="63a78-110">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="63a78-110">Choose a learning algorithm</span></span>
> - <span data-ttu-id="63a78-111">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="63a78-111">Train the model</span></span>
> - <span data-ttu-id="63a78-112">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="63a78-112">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="63a78-113">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="63a78-113">Prerequisites</span></span>

- <span data-ttu-id="63a78-114">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="63a78-114">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="63a78-115">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="63a78-115">Understand the problem</span></span>

<span data-ttu-id="63a78-116">この問題は、アヤメの花のセットを特徴に基づいて異なるグループに分類するというものです。</span><span class="sxs-lookup"><span data-stu-id="63a78-116">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="63a78-117">対象となる特徴は、がくの長さと幅および花弁の長さと幅です。</span><span class="sxs-lookup"><span data-stu-id="63a78-117">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="63a78-118">このチュートリアルでは、各花の種類は不明であるものとします。</span><span class="sxs-lookup"><span data-stu-id="63a78-118">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="63a78-119">特徴からデータ セットの構造を理解し、データのインスタンスがこの構造にどのように当てはまるかを予測します。</span><span class="sxs-lookup"><span data-stu-id="63a78-119">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="63a78-120">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="63a78-120">Select the appropriate machine learning task</span></span>

<span data-ttu-id="63a78-121">各花がどのグループに属するかわからないので、[教師なし機械学習](../resources/glossary.md#unsupervised-machine-learning)タスクを選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-121">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="63a78-122">同じグループ内の要素同士の方が他のグループの要素より似ているようにデータ セットをグループに分割するので、[クラスタリング](../resources/tasks.md#clustering)機械学習タスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="63a78-122">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="63a78-123">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="63a78-123">Create a console application</span></span>

1. <span data-ttu-id="63a78-124">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="63a78-124">Open Visual Studio.</span></span> <span data-ttu-id="63a78-125">**[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-125">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="63a78-126">**[新しいプロジェクト]** ダイアログで、 **[Visual C#]** ノードを選択し、 **[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-126">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="63a78-127">次に、 **[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-127">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="63a78-128">**[名前]** テキスト ボックスに「IrisFlowerClustering」と入力し、 **[OK]** ボタンを選びます。</span><span class="sxs-lookup"><span data-stu-id="63a78-128">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="63a78-129">プロジェクトに *Data* という名前のディレクトリを作成して、データ セットとモデルのファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="63a78-129">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="63a78-130">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-130">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="63a78-131">「Data」と入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="63a78-131">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="63a78-132">**Microsoft.ML** NuGet パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="63a78-132">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="63a78-133">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-133">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="63a78-134">[パッケージ ソース] として [nuget.org] を選択します。 **[参照]** タブを選択し、「**Microsoft.ML**」を検索します。一覧から **v1.0.0** パッケージを選択し、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-134">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the **v1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="63a78-135">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="63a78-136">データを準備する</span><span class="sxs-lookup"><span data-stu-id="63a78-136">Prepare the data</span></span>

1. <span data-ttu-id="63a78-137">[iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) データ セットをダウンロードし、前の手順で作成した *Data* フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="63a78-137">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="63a78-138">あやめのデータ セットについて詳しくは、Wikipedia の「[Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set)」(あやめのデータ セット) のページと、データ セットのソースである「[Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris)」(あやめのデータ セット) のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63a78-138">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="63a78-139">**ソリューション エクスプローラー**で、*iris.data* ファイルを右クリックして、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-139">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="63a78-140">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="63a78-140">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="63a78-141">*Iris.data* ファイルには、次の値を表す 5 つの列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63a78-141">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="63a78-142">がくの長さ (センチメートル単位)</span><span class="sxs-lookup"><span data-stu-id="63a78-142">sepal length in centimetres</span></span>
- <span data-ttu-id="63a78-143">がくの幅 (センチメートル単位)</span><span class="sxs-lookup"><span data-stu-id="63a78-143">sepal width in centimetres</span></span>
- <span data-ttu-id="63a78-144">花弁の長さ (センチメートル単位)</span><span class="sxs-lookup"><span data-stu-id="63a78-144">petal length in centimetres</span></span>
- <span data-ttu-id="63a78-145">花弁の幅 (センチメートル単位)</span><span class="sxs-lookup"><span data-stu-id="63a78-145">petal width in centimetres</span></span>
- <span data-ttu-id="63a78-146">アヤメの種類</span><span class="sxs-lookup"><span data-stu-id="63a78-146">type of iris flower</span></span>

<span data-ttu-id="63a78-147">クラスタリングの例が目的なので、このチュートリアルでは最後の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="63a78-147">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="63a78-148">データ クラスを作成する</span><span class="sxs-lookup"><span data-stu-id="63a78-148">Create data classes</span></span>

<span data-ttu-id="63a78-149">入力データと予測のためのクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="63a78-149">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="63a78-150">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-150">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="63a78-151">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを「*IrisData.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="63a78-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="63a78-152">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-152">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="63a78-153">以下の `using` ディレクティブを新しいファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="63a78-153">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="63a78-154">既存のクラス定義を削除し、`IrisData` クラスと `ClusterPrediction` クラスを定義する次のコードを *IrisData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="63a78-154">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="63a78-155">`IrisData` は入力データ クラスであり、データ セットの各特徴の定義が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63a78-155">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="63a78-156">データ セット ファイル内のソース列のインデックスを指定するには、[LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="63a78-156">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="63a78-157">`ClusterPrediction` クラスは、`IrisData` インスタンスに適用されたクラスタリング モデルの出力を表します。</span><span class="sxs-lookup"><span data-stu-id="63a78-157">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="63a78-158">[ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性を使って、`PredictedClusterId` フィールドを **PredictedLabel** 列に、`Distances` フィールドを **Score** 列に、それぞれバインドします。</span><span class="sxs-lookup"><span data-stu-id="63a78-158">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="63a78-159">クラスタリング タスクの場合、これらの列には次の意味があります。</span><span class="sxs-lookup"><span data-stu-id="63a78-159">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="63a78-160">**PredictedLabel** 列には、予測されたクラスターの ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63a78-160">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="63a78-161">**Score** 列には、クラスターの重心へのユークリッド距離を二乗した値の配列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63a78-161">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="63a78-162">配列の長さは、クラスターの数と同じです。</span><span class="sxs-lookup"><span data-stu-id="63a78-162">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="63a78-163">入力データと予測データのクラス内の浮動小数点値を表すには、`float` 型を使います。</span><span class="sxs-lookup"><span data-stu-id="63a78-163">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="63a78-164">データおよびモデルのパスを定義する</span><span class="sxs-lookup"><span data-stu-id="63a78-164">Define data and model paths</span></span>

<span data-ttu-id="63a78-165">*Program.cs* ファイルに戻り、データ セット ファイルと、モデルを保存するファイルへのパスを保持するために、2 つのフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="63a78-165">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="63a78-166">`_dataPath` には、モデルのトレーニングに使用するデータ セットがあるファイルへのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="63a78-166">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="63a78-167">`_modelPath` には、トレーニング済みモデルが格納されるファイルへのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="63a78-167">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="63a78-168">`Main` メソッドのすぐ上に次のコードを追加して、それらのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="63a78-168">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="63a78-169">上記のコードをコンパイルするには、*Program.cs* ファイルの先頭に次の `using` ディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="63a78-169">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="63a78-170">ML のコンテキストの作成</span><span class="sxs-lookup"><span data-stu-id="63a78-170">Create ML context</span></span>

<span data-ttu-id="63a78-171">以下の追加の `using` ディレクティブを、*Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="63a78-171">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="63a78-172">`Main` メソッドの `Console.WriteLine("Hello World!");` 行を次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="63a78-172">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="63a78-173"><xref:Microsoft.ML.MLContext?displayProperty=nameWithType> クラスは機械学習環境を表し、ログ記録のメカニズムとデータの読み込みのエントリ ポイント、モデルのトレーニング、予測、およびその他のタスクを提供します。</span><span class="sxs-lookup"><span data-stu-id="63a78-173">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="63a78-174">これは、概念的には Entity Framework での `DbContext` の使用に相当します。</span><span class="sxs-lookup"><span data-stu-id="63a78-174">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="63a78-175">データの読み込みのセットアップ</span><span class="sxs-lookup"><span data-stu-id="63a78-175">Setup data loading</span></span>

<span data-ttu-id="63a78-176">`Main` メソッドに次のコードを追加して、データを読み込む方法をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="63a78-176">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

<span data-ttu-id="63a78-177">ジェネリック [`MLContext.Data.LoadFromTextFile` 拡張メソッド](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)は、指定された `IrisData` 型からデータ セット スキーマを推測し、<xref:Microsoft.ML.IDataView> を返します。これはトランスフォーマーの入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="63a78-177">The generic [`MLContext.Data.LoadFromTextFile` extension method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) infers the data set schema from the provided `IrisData` type and returns <xref:Microsoft.ML.IDataView> which can be used as input for transformers.</span></span>

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="63a78-178">学習パイプラインを作成する</span><span class="sxs-lookup"><span data-stu-id="63a78-178">Create a learning pipeline</span></span>

<span data-ttu-id="63a78-179">このチュートリアルでは、クラスタリング タスクの学習パイプラインは、次の 2 つの手順で構成されています。</span><span class="sxs-lookup"><span data-stu-id="63a78-179">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="63a78-180">読み込まれた列を、クラスタリング トレーナーによって使用される 1 つの **Features** 列に連結します。</span><span class="sxs-lookup"><span data-stu-id="63a78-180">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="63a78-181"><xref:Microsoft.ML.Trainers.KMeansTrainer> トレーナーを使用して、K- 平均法++ クラスタリング アルゴリズムを使用するモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="63a78-181">use a <xref:Microsoft.ML.Trainers.KMeansTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="63a78-182">`Main` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="63a78-182">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="63a78-183">このコードは、データ セットを 3 つのクラスターに分割することを指定します。</span><span class="sxs-lookup"><span data-stu-id="63a78-183">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="63a78-184">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="63a78-184">Train the model</span></span>

<span data-ttu-id="63a78-185">前のセクションで追加した手順では、トレーニング用にパイプラインを準備しましたが、トレーニングは実行されていません。</span><span class="sxs-lookup"><span data-stu-id="63a78-185">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="63a78-186">次の行を `Main` メソッドに追加して、データの読み込みとモデルのトレーニングを実行します。</span><span class="sxs-lookup"><span data-stu-id="63a78-186">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="63a78-187">モデルを保存する</span><span class="sxs-lookup"><span data-stu-id="63a78-187">Save the model</span></span>

<span data-ttu-id="63a78-188">この時点で、既存または新規のどの .NET アプリケーションにも統合できるモデルができました。</span><span class="sxs-lookup"><span data-stu-id="63a78-188">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="63a78-189">モデルを .zip ファイルに保存するには、次のコードを `Main` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="63a78-189">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="63a78-190">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="63a78-190">Use the model for predictions</span></span>

<span data-ttu-id="63a78-191">予測を行うには、トランスフォーマー パイプラインを介して入力の型のインスタンスを受け取り、出力の型のインスタンスを生成する <xref:Microsoft.ML.PredictionEngine%602> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="63a78-191">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="63a78-192">次の行を `Main` メソッドに追加して、そのクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="63a78-192">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="63a78-193">テスト データのインスタンスを格納するための `TestIrisData` クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="63a78-193">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="63a78-194">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-194">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="63a78-195">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを「*TestIrisData.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="63a78-195">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="63a78-196">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63a78-196">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="63a78-197">次の例に示すように、静的になるようにクラスを変更します。</span><span class="sxs-lookup"><span data-stu-id="63a78-197">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="63a78-198">このチュートリアルでは、このクラスで 1 つのあやめのデータ インスタンスを示します。</span><span class="sxs-lookup"><span data-stu-id="63a78-198">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="63a78-199">他のシナリオを追加してモデルで実験できます。</span><span class="sxs-lookup"><span data-stu-id="63a78-199">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="63a78-200">`TestIrisData` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="63a78-200">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="63a78-201">指定した項目が属するクラスターを発見するには、*Program.cs* ファイルに戻り、次のコードを `Main` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="63a78-201">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="63a78-202">プログラムを実行し、指定したデータ インスタンスが含まれるクラスターと、そのインスタンスからクラスターの重心までの平方距離を確認します。</span><span class="sxs-lookup"><span data-stu-id="63a78-202">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="63a78-203">結果は以下のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="63a78-203">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="63a78-204">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="63a78-204">Congratulations!</span></span> <span data-ttu-id="63a78-205">これで、アヤメのクラスタリングの機械学習モデルを作成し、それを使用して予測を行うことができました。</span><span class="sxs-lookup"><span data-stu-id="63a78-205">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="63a78-206">このチュートリアルのソース コードは、[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="63a78-206">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="63a78-207">次の手順</span><span class="sxs-lookup"><span data-stu-id="63a78-207">Next steps</span></span>

<span data-ttu-id="63a78-208">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="63a78-208">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="63a78-209">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="63a78-209">Understand the problem</span></span>
> - <span data-ttu-id="63a78-210">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="63a78-210">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="63a78-211">データを準備する</span><span class="sxs-lookup"><span data-stu-id="63a78-211">Prepare the data</span></span>
> - <span data-ttu-id="63a78-212">データを読み込んで変換する</span><span class="sxs-lookup"><span data-stu-id="63a78-212">Load and transform the data</span></span>
> - <span data-ttu-id="63a78-213">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="63a78-213">Choose a learning algorithm</span></span>
> - <span data-ttu-id="63a78-214">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="63a78-214">Train the model</span></span>
> - <span data-ttu-id="63a78-215">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="63a78-215">Use the model for predictions</span></span>

<span data-ttu-id="63a78-216">学習を続けてその他のサンプルを確認するには、GitHub リポジトリをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63a78-216">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="63a78-217">dotnet/machinelearning GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="63a78-217">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
