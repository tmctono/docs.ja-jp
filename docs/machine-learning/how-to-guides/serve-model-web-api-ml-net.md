---
title: ASP.NET Core Web API でのモデルのデプロイ
description: ASP.NET Core Web API を使用して、インターネット経由で予測用の ML.NET 感情分析機械学習モデルを提供します
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: b6801b7de5a17257be706f77a7a67aa87df96524
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79397759"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="96fab-103">ASP.NET Core Web API でのモデルのデプロイ</span><span class="sxs-lookup"><span data-stu-id="96fab-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="96fab-104">ASP.NET Core Web API を使用して、事前トレーニング済みの ML.NET 機械学習モデルを Web 上に提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="96fab-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="96fab-105">Web API 経由でモデルを提供すると、標準の HTTP メソッドによる予測が可能になります。</span><span class="sxs-lookup"><span data-stu-id="96fab-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="96fab-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="96fab-106">Prerequisites</span></span>

- <span data-ttu-id="96fab-107">[Visual Studio 2017 バージョン 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" ワークロードと共にインストールされている</span><span class="sxs-lookup"><span data-stu-id="96fab-107">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="96fab-108">PowerShell</span><span class="sxs-lookup"><span data-stu-id="96fab-108">Powershell.</span></span>
- <span data-ttu-id="96fab-109">事前トレーニング済みモデル</span><span class="sxs-lookup"><span data-stu-id="96fab-109">Pre-trained model.</span></span> <span data-ttu-id="96fab-110">[ML.NET Sentiment Analysis のチュートリアル](../tutorials/sentiment-analysis.md)を使用して独自のモデルを構築するか、この[事前トレーニング済みの感情分析の機械学習モデル](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)をダウンロードすること。</span><span class="sxs-lookup"><span data-stu-id="96fab-110">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="96fab-111">ASP.NET Core Web API プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="96fab-111">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="96fab-112">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="96fab-112">Open Visual Studio 2017.</span></span> <span data-ttu-id="96fab-113">メニューバーから、 **[ファイル] > [新規作成] > [プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-113">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="96fab-114">[新しいプロジェクト] ダイアログで、 **[Visual C#]** ノードを選択し、 **[Web]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-114">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="96fab-115">次に、 **[ASP.NET Core Web アプリケーション]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-115">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="96fab-116">**[名前]** テキスト ボックスに「SentimentAnalysisWebAPI」と入力し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-116">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="96fab-117">ASP.NET Core プロジェクトの複数の種類が表示されているウィンドウで、 **[API]** を選択し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-117">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="96fab-118">事前トレーニング済みの機械学習モデルを保存するための *MLModels* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="96fab-118">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="96fab-119">ソリューションエクスプローラーで、プロジェクトを右クリックし、[追加] > [新しいフォルダー] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-119">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="96fab-120">「MLModels」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="96fab-120">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="96fab-121">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="96fab-121">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="96fab-122">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-122">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="96fab-123">[パッケージ ソース] として [nuget.org] を選択します。[参照] タブを選択し、「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、[インストール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-123">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="96fab-124">**[変更のプレビュー]** ダイアログで **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、[ライセンスの同意] ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-124">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="96fab-125">**Microsoft.Extensions.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="96fab-125">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="96fab-126">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-126">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="96fab-127">パッケージ ソースとして "nuget.org" を選択します。[参照] タブを選択し、「**Microsoft.Extensions.ML**」を検索します。一覧からそのパッケージを選択して、[インストール] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-127">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="96fab-128">**[変更のプレビュー]** ダイアログで **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、[ライセンスの同意] ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-128">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="96fab-129">モデルを ASP.NET Core Web API プロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="96fab-129">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="96fab-130">事前トレーニング済みのモデルを *MLModels* ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="96fab-130">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="96fab-131">ソリューション エクスプローラーで、モデルの zip ファイルを右クリックし、[プロパティ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-131">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="96fab-132">[プロパティ] で [出力ディレクトリにコピー] の値を [新しい場合はコピーする] に変更します。</span><span class="sxs-lookup"><span data-stu-id="96fab-132">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="96fab-133">データ モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="96fab-133">Create data models</span></span>

<span data-ttu-id="96fab-134">入力データと予測のために、いくつかのクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96fab-134">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="96fab-135">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="96fab-135">Add a new class to your project:</span></span>

1. <span data-ttu-id="96fab-136">データモデルを保存するための *DataModels* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="96fab-136">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="96fab-137">ソリューションエクスプローラーで、プロジェクトを右クリックし、[追加] > [新しいフォルダー] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-137">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="96fab-138">「DataModels」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="96fab-138">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="96fab-139">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、[追加] > [新しいアイテム] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-139">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="96fab-140">**[新しい項目の追加]** ダイアログボックスで **[クラス]** を選択し、 **[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="96fab-140">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="96fab-141">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-141">Then, select the **Add** button.</span></span> <span data-ttu-id="96fab-142">コードエディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="96fab-142">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="96fab-143">*SentimentData.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="96fab-143">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="96fab-144">既存のクラス定義を削除し、次のコードを **SentimentData.cs** ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="96fab-144">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

    ```csharp
    public class SentimentData
    {
        [LoadColumn(0)]
        public string SentimentText;

        [LoadColumn(1)]
        [ColumnName("Label")]
        public bool Sentiment;
    }
    ```

4. <span data-ttu-id="96fab-145">ソリューションエクスプローラーで、*DataModels* ディレクトリを右クリックし、 **[追加] > [新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-145">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="96fab-146">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *SentimentPrediction.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="96fab-146">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="96fab-147">次に、[追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-147">Then, select the Add button.</span></span> <span data-ttu-id="96fab-148">コード エディターに *SentimentPrediction.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="96fab-148">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="96fab-149">*SentimentPrediction.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="96fab-149">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="96fab-150">既存のクラス定義を削除し、次のコードを *SentimentPrediction.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="96fab-150">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="96fab-151">`SentimentPrediction` は `SentimentData` を継承します。</span><span class="sxs-lookup"><span data-stu-id="96fab-151">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="96fab-152">これにより、モデルによって生成された出力データと一緒に `SentimentText` プロパティの元のデータを容易に確認できます。</span><span class="sxs-lookup"><span data-stu-id="96fab-152">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span>

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="96fab-153">アプリケーションで使用する PredictionEnginePool を登録する</span><span class="sxs-lookup"><span data-stu-id="96fab-153">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="96fab-154">1 つの予測を作成するには、[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96fab-154">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="96fab-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) はスレッド セーフではありません。</span><span class="sxs-lookup"><span data-stu-id="96fab-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="96fab-156">さらに、アプリケーション内で必要なすべての場所にそのインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96fab-156">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="96fab-157">アプリケーションの規模が拡大すると、このプロセスが管理不能になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96fab-157">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="96fab-158">パフォーマンスとスレッド セーフを向上させるには、依存性の挿入と `PredictionEnginePool` サービスを組み合わせて使用します。これにより、アプリケーション全体で使用する [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) オブジェクトの [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="96fab-158">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="96fab-159">[ASP.NET Core での依存関係の挿入](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)については、リンク先で提供されている詳しい情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="96fab-159">The following link provides more information if you want to learn more about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="96fab-160">*Startup.cs* を開き、ファイルの先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="96fab-160">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="96fab-161">*ConfigureServices* メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="96fab-161">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
        .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    ```

<span data-ttu-id="96fab-162">大まかに言えば、オブジェクトとサービスがアプリケーションによって要求されたときに、このコードでは、後で使用できるように手動ではなく自動的に初期化が実行されます。</span><span class="sxs-lookup"><span data-stu-id="96fab-162">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="96fab-163">機械学習モデルは静的ではありません。</span><span class="sxs-lookup"><span data-stu-id="96fab-163">Machine learning models are not static.</span></span> <span data-ttu-id="96fab-164">新しいトレーニング データが使用可能になると、モデルの再トレーニングと再展開が行われます。</span><span class="sxs-lookup"><span data-stu-id="96fab-164">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="96fab-165">アプリケーションに最新バージョンのモデルを取り込む方法の 1 つは、アプリケーション全体を再展開することです。</span><span class="sxs-lookup"><span data-stu-id="96fab-165">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="96fab-166">ただし、これによってアプリケーションのダウンタイムが発生します。</span><span class="sxs-lookup"><span data-stu-id="96fab-166">However, this introduces application downtime.</span></span> <span data-ttu-id="96fab-167">`PredictionEnginePool` サービスには、アプリケーションを停止することなく、更新されたモデルを再度読み込むメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="96fab-167">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="96fab-168">`watchForChanges` パラメーターを `true` に設定すると、`PredictionEnginePool` では、ファイル システムの変更通知をリッスンし、ファイルに変更があったときにイベントを発生させる [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) が開始されます。</span><span class="sxs-lookup"><span data-stu-id="96fab-168">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="96fab-169">これにより、モデルを自動的に再度読み込む `PredictionEnginePool` のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96fab-169">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="96fab-170">モデルは `modelName` パラメーターによって識別されるため、変更時にアプリケーションごとに複数のモデルを再度読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="96fab-170">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="96fab-171">また、リモートに格納されているモデルを操作するときは `FromUri` メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="96fab-171">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="96fab-172">`FromUri` では、ファイルの変更イベントを監視するのではなく、リモートの場所の変更をポーリングします。</span><span class="sxs-lookup"><span data-stu-id="96fab-172">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="96fab-173">ポーリング間隔は既定で 5 分に設定されています。</span><span class="sxs-lookup"><span data-stu-id="96fab-173">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="96fab-174">アプリケーションの要件に基づいてポーリング間隔を増減することができます。</span><span class="sxs-lookup"><span data-stu-id="96fab-174">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="96fab-175">次のコード サンプルでは、`PredictionEnginePool` は、指定された URI に格納されているモデルを 1 分ごとにポーリングします。</span><span class="sxs-lookup"><span data-stu-id="96fab-175">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>
>```csharp
>services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="create-predict-controller"></a><span data-ttu-id="96fab-176">予測コントローラーを作成する</span><span class="sxs-lookup"><span data-stu-id="96fab-176">Create Predict controller</span></span>

<span data-ttu-id="96fab-177">HTTP 要求の受信の処理をするために、コントローラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="96fab-177">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="96fab-178">ソリューション エクスプローラーで、*Controllers* ディレクトリを右クリックし、 **[追加] > [コントローラー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-178">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="96fab-179">**[新しい項目の追加]** ダイアログ ボックスで、 **[空の API コントローラー]** を選択し、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-179">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="96fab-180">プロンプトで、 **[コントローラー名]** フィールドを*PredictController.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="96fab-180">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="96fab-181">次に、[追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96fab-181">Then, select the Add button.</span></span> <span data-ttu-id="96fab-182">コードエディターで *PredictController.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="96fab-182">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="96fab-183">*PredictController.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="96fab-183">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="96fab-184">既存のクラス定義を削除し、次のコードを *PredictController.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="96fab-184">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

    ```csharp
    public class PredictController : ControllerBase
    {
        private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

        public PredictController(PredictionEnginePool<SentimentData,SentimentPrediction> predictionEnginePool)
        {
            _predictionEnginePool = predictionEnginePool;
        }

        [HttpPost]
        public ActionResult<string> Post([FromBody] SentimentData input)
        {
            if(!ModelState.IsValid)
            {
                return BadRequest();
            }

            SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="96fab-185">このコードでは、`PredictionEnginePool` を依存関係の挿入によって取得してコントローラーのコンストラクターに渡すことで割り当てています。</span><span class="sxs-lookup"><span data-stu-id="96fab-185">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="96fab-186">次に、`Predict` コントローラーの `Post` メソッドで `PredictionEnginePool` を使用し、`SentimentAnalysisModel` クラスに登録されている `Startup` を使用して予測を行い、成功した場合に結果をユーザーに返します。</span><span class="sxs-lookup"><span data-stu-id="96fab-186">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="96fab-187">Web API をローカルでテストする</span><span class="sxs-lookup"><span data-stu-id="96fab-187">Test web API locally</span></span>

<span data-ttu-id="96fab-188">すべてが設定されたので、アプリケーションをテストしましょう。</span><span class="sxs-lookup"><span data-stu-id="96fab-188">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="96fab-189">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="96fab-189">Run the application.</span></span>
1. <span data-ttu-id="96fab-190">PowerShell を開き、次のコードを入力します。PORT には、アプリケーションがリスニングしているポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="96fab-190">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="96fab-191">成功した場合、出力は次のテキストのようになります。</span><span class="sxs-lookup"><span data-stu-id="96fab-191">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="96fab-192">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="96fab-192">Congratulations!</span></span> <span data-ttu-id="96fab-193">ASP.NET Core Web API を使用して、インターネット経由で予測を実行するモデルを正常に提供できました。</span><span class="sxs-lookup"><span data-stu-id="96fab-193">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96fab-194">次の手順</span><span class="sxs-lookup"><span data-stu-id="96fab-194">Next Steps</span></span>

- [<span data-ttu-id="96fab-195">Azure へのデプロイ</span><span class="sxs-lookup"><span data-stu-id="96fab-195">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)
