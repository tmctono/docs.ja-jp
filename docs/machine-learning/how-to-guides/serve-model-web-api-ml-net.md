---
title: ASP.NET Core Web API でのモデルのデプロイ
description: ASP.NET Core Web API を使用して、インターネット経由で予測用の ML.NET 感情分析機械学習モデルを提供します
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: f8b8f74f752aeb243d4a2987929bd28ddc5f7d5a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641080"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="3b1b8-103">ASP.NET Core Web API でのモデルのデプロイ</span><span class="sxs-lookup"><span data-stu-id="3b1b8-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="3b1b8-104">ASP.NET Core Web API を使用して、事前トレーニング済みの ML.NET 機械学習モデルを Web 上に提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="3b1b8-105">Web API 経由でモデルを提供すると、標準の HTTP メソッドによる予測が可能になります。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="3b1b8-106">`PredictionEnginePool` サービスの拡張機能は、現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-106">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b1b8-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3b1b8-107">Prerequisites</span></span>

- <span data-ttu-id="3b1b8-108">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-108">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="3b1b8-109">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b1b8-109">Powershell.</span></span>
- <span data-ttu-id="3b1b8-110">事前トレーニング済みモデル</span><span class="sxs-lookup"><span data-stu-id="3b1b8-110">Pre-trained model.</span></span> <span data-ttu-id="3b1b8-111">[ML.NET Sentiment Analysis のチュートリアル](../tutorials/sentiment-analysis.md)を使用して独自のモデルを構築するか、この[事前トレーニング済みの感情分析の機械学習モデル](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)をダウンロードすること</span><span class="sxs-lookup"><span data-stu-id="3b1b8-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="3b1b8-112">ASP.NET Core Web API プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="3b1b8-112">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="3b1b8-113">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="3b1b8-114">メニュー バーから、 **[ファイル]、[新規]、[プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-114">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="3b1b8-115">[新しいプロジェクト] ダイアログで、 **[Visual C#]** ノードを選択し、 **[Web]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-115">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="3b1b8-116">次に、 **[ASP.NET Core Web アプリケーション]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-116">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="3b1b8-117">**[名前]** テキスト ボックスに「SentimentAnalysisWebAPI」と入力し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-117">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="3b1b8-118">ASP.NET Core プロジェクトの複数の種類が表示されているウィンドウで、 **[API]** を選択し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-118">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="3b1b8-119">構築済みの機械学習モデルを保存するための *MLModels* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-119">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="3b1b8-120">ソリューション エクスプローラーで、プロジェクトを右クリックし、[追加]、[新しいフォルダー] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-120">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="3b1b8-121">「MLModels」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-121">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="3b1b8-122">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="3b1b8-123">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="3b1b8-124">[パッケージ ソース] として [nuget.org] を選択します。[参照] タブを選択し、「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、[インストール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="3b1b8-125">**[変更のプレビュー]** ダイアログで **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、[ライセンスの同意] ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="3b1b8-126">**Microsoft.Extensions.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-126">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="3b1b8-127">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="3b1b8-128">パッケージ ソースとして "nuget.org" を選択します。[参照] タブを選択し、「**Microsoft.Extensions.ML**」を検索します。一覧からそのパッケージを選択して、[インストール] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="3b1b8-129">**[変更のプレビュー]** ダイアログで **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、[ライセンスの同意] ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="3b1b8-130">モデルを ASP.NET Core Web API プロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="3b1b8-130">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="3b1b8-131">構築済みのモデルを *MLModels* ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="3b1b8-132">ソリューション エクスプローラーで、モデルの zip ファイルを右クリックし、[プロパティ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="3b1b8-133">[詳細設定] で、[出力ディレクトリにコピー] の値を [新しい場合はコピーする] に変更します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="3b1b8-134">データ モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="3b1b8-134">Create data models</span></span>

<span data-ttu-id="3b1b8-135">入力データと予測のために、いくつかのクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="3b1b8-136">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="3b1b8-137">データ モデルを保存するための *DataModels* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="3b1b8-138">ソリューション エクスプローラーで、プロジェクトを右クリックし、[追加]、[新しいフォルダー] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="3b1b8-139">「DataModels」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="3b1b8-140">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、[追加]、[新しいアイテム] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="3b1b8-141">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="3b1b8-142">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-142">Then, select the **Add** button.</span></span> <span data-ttu-id="3b1b8-143">コード エディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="3b1b8-144">*SentimentData.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="3b1b8-145">既存のクラス定義を削除し、次のコードを **SentimentData.cs** ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>
    
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

4. <span data-ttu-id="3b1b8-146">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、 **[追加]、[新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="3b1b8-147">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *SentimentPrediction.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="3b1b8-148">次に、[追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-148">Then, select the Add button.</span></span> <span data-ttu-id="3b1b8-149">コード エディターに *SentimentPrediction.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="3b1b8-150">*SentimentPrediction.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="3b1b8-151">既存のクラス定義を削除し、次のコードを *SentimentPrediction.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>
    
    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="3b1b8-152">`SentimentPrediction` は `SentimentData`を継承します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-152">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="3b1b8-153">これにより、モデルによって生成された出力と共に、`SentimentText` プロパティ内の元のデータをより簡単に確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-153">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span> 

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="3b1b8-154">アプリケーション内で使用する PredictionEnginePool を登録する</span><span class="sxs-lookup"><span data-stu-id="3b1b8-154">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="3b1b8-155">1 つの予測を行うために、[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-155">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="3b1b8-156">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) をお使いのアプリケーションで使用するには、必要に応じて、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-156">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="3b1b8-157">その場合、ベスト プラクティスとして、依存関係を挿入することを検討します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-157">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="3b1b8-158">[ASP.NET Core での依存関係の挿入](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)については、リンク先で提供されている詳しい情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-158">The following link provides more information if you want to learn about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="3b1b8-159">*Startup.cs* を開き、ファイルの先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-159">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="3b1b8-160">*ConfigureServices* メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-160">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile("MLModels/sentiment_model.zip");
    }
    ```

<span data-ttu-id="3b1b8-161">大まかに言えば、このコードは、オブジェクトとサービスがアプリケーションによって要求されたときに、初期化を手動ではなく自動的に実行します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-161">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="3b1b8-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) はスレッド セーフではありません。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="3b1b8-163">パフォーマンスとスレッドの安全性を改善するために、`PredictionEnginePool` サービスを使用します。これにより、アプリケーションで使用される `PredictionEngine` オブジェクトの [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-163">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> <span data-ttu-id="3b1b8-164">詳しくは、[ASP.NET Core での `PredictionEngine` オブジェクト プールの作成と使用](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/)に関するブログ投稿で確認してください。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-164">Read the following blog post to learn more about [creating and using `PredictionEngine` object pools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>  

## <a name="create-predict-controller"></a><span data-ttu-id="3b1b8-165">予測コントローラーを作成する</span><span class="sxs-lookup"><span data-stu-id="3b1b8-165">Create Predict controller</span></span>

<span data-ttu-id="3b1b8-166">受信 HTTP 要求を処理するために、コントローラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-166">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="3b1b8-167">ソリューション エクスプローラーで、*Controllers* ディレクトリを右クリックし、 **[追加]、[コントローラー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-167">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="3b1b8-168">**[新しい項目の追加]** ダイアログ ボックスで、 **[空の API コントローラー]** を選択し、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-168">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="3b1b8-169">プロンプトで、 **[コントローラー名]** フィールドを*PredictController.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-169">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="3b1b8-170">次に、[追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-170">Then, select the Add button.</span></span> <span data-ttu-id="3b1b8-171">コード エディターに *PredictController.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-171">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="3b1b8-172">*PredictController.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-172">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="3b1b8-173">既存のクラス定義を削除し、次のコードを *PredictController.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-173">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>
    
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

            SentimentPrediction prediction = _predictionEnginePool.Predict(input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="3b1b8-174">このコードでは、依存関係の挿入によって取得したコントローラーのコンストラクターに渡すことで、`PredictionEnginePool` を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-174">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="3b1b8-175">次に、`Predict` コントローラーの `Post` メソッドでは、`PredictionEnginePool` を使用して予測を行い、成功した場合はその結果をユーザーに返します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-175">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="3b1b8-176">Web API をローカルでテストする</span><span class="sxs-lookup"><span data-stu-id="3b1b8-176">Test web API locally</span></span>

<span data-ttu-id="3b1b8-177">すべてが設定されたので、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-177">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="3b1b8-178">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-178">Run the application.</span></span>
1. <span data-ttu-id="3b1b8-179">PowerShell を開き、次のコードを入力します。PORT は、アプリケーションがリスニングしているポートです。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-179">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="3b1b8-180">成功した場合、出力は次のテキストのようになります。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-180">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="3b1b8-181">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="3b1b8-181">Congratulations!</span></span> <span data-ttu-id="3b1b8-182">ASP.NET Core Web API を使用して、インターネット経由で予測を実行するモデルを正常に提供できました。</span><span class="sxs-lookup"><span data-stu-id="3b1b8-182">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b1b8-183">次の手順</span><span class="sxs-lookup"><span data-stu-id="3b1b8-183">Next Steps</span></span>

- [<span data-ttu-id="3b1b8-184">Azure に配置する</span><span class="sxs-lookup"><span data-stu-id="3b1b8-184">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)
