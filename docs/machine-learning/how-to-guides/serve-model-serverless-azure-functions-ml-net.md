---
title: Azure Functions に ML.NET モデルをデプロイする
description: Azure Functions を使用して、インターネット経由で予測用の ML.NET 感情分析機械学習モデルを提供します
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4681b37da64097dd8e537b4c956917277ecff96b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330637"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a><span data-ttu-id="b8412-103">方法:Azure Functions で ML.NET モデルを使用する</span><span class="sxs-lookup"><span data-stu-id="b8412-103">How-To: Use ML.NET Model in Azure Functions</span></span>

<span data-ttu-id="b8412-104">このハウツー記事では、Azure Functions などのサーバーレス環境で、構築済みの ML.NET 機械学習モデルをインターネット経由で使用して個々の予測を行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b8412-104">This how-to shows how individual predictions can be made using a pre-built ML.NET machine learning model through the internet in a serverless environment such as Azure Functions.</span></span>

> [!NOTE]
> <span data-ttu-id="b8412-105">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8412-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="b8412-106">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8412-106">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="b8412-107">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="b8412-107">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="b8412-108">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8412-108">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8412-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b8412-109">Prerequisites</span></span>

- <span data-ttu-id="b8412-110">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" ワークロードおよび "Azure 開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="b8412-110">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span> 
- [<span data-ttu-id="b8412-111">Azure Functions ツール</span><span class="sxs-lookup"><span data-stu-id="b8412-111">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="b8412-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8412-112">Powershell</span></span>
- <span data-ttu-id="b8412-113">事前トレーニング済みモデル</span><span class="sxs-lookup"><span data-stu-id="b8412-113">Pre-trained model.</span></span> 
    - <span data-ttu-id="b8412-114">[ML.NET 感情分析のチュートリアル](../tutorials/sentiment-analysis.md)を使用して、独自のモデルを構築する。</span><span class="sxs-lookup"><span data-stu-id="b8412-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="b8412-115">この[事前トレーニング済みの感情分析機械学習モデル](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)をダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="b8412-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="b8412-116">Azure Functions プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="b8412-116">Create Azure Functions Project</span></span>

1. <span data-ttu-id="b8412-117">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="b8412-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="b8412-118">**[ファイル]** > **[新規作成]** > **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-118">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="b8412-119">**[新しいプロジェクト]** ダイアログで、**[Visual C#]** ノードを選択し、**[クラウド]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-119">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="b8412-120">次に、**Azure Functions** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-120">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="b8412-121">**[名前]** テキスト ボックスに「SentimentAnalysisFunctionsApp」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-121">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="b8412-122">**[新しいプロジェクト]** ダイアログで、プロジェクト オプションの上のドロップダウンを開き、**[Azure Functions v2 (.NET Core)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-122">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="b8412-123">次に、**[Http トリガー]** プロジェクトを選択し、**[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-123">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="b8412-124">モデルを保存するための *MLModels* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="b8412-124">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="b8412-125">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="b8412-126">「MLModels」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b8412-126">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="b8412-127">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b8412-127">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="b8412-128">ソリューション エクスプローラーで、プロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b8412-129">[パッケージ ソース] として "nuget.org" を選択し、[参照] タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="b8412-130">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、**[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-built-model-to-project"></a><span data-ttu-id="b8412-131">構築済みのモデルをプロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="b8412-131">Add Pre-built Model To Project</span></span>

1. <span data-ttu-id="b8412-132">構築済みのモデルを *MLModels* フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b8412-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="b8412-133">ソリューション エクスプローラーで、構築済みのモデルのファイルを右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="b8412-134">**[詳細設定]** で、**[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="b8412-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-function-to-analyze-sentiment"></a><span data-ttu-id="b8412-135">センチメントを分析する関数を作成する</span><span class="sxs-lookup"><span data-stu-id="b8412-135">Create Function to Analyze Sentiment</span></span>

<span data-ttu-id="b8412-136">センチメントを予測するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8412-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="b8412-137">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8412-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="b8412-138">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="b8412-139">**[新しい項目の追加]** ダイアログ ボックスで、**[Azure 関数]** を選択し、**[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="b8412-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="b8412-140">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="b8412-141">**[新しい Azure 関数]** ダイアログ ボックスで、**[Http トリガー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="b8412-142">次に、**[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="b8412-143">コード エディターに *AnalyzeSentiment.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="b8412-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="b8412-144">*GitHubIssueData.cs* の先頭に次の `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8412-144">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

```csharp
using System;
using System.IO;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Azure.WebJobs;
using Microsoft.Azure.WebJobs.Extensions.Http;
using Microsoft.AspNetCore.Http;
using Microsoft.Extensions.Logging;
using Newtonsoft.Json;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using Microsoft.ML.Data;
using MLNETServerless.DataModels;
```

### <a name="create-data-models"></a><span data-ttu-id="b8412-145">データ モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="b8412-145">Create Data Models</span></span>

<span data-ttu-id="b8412-146">入力データと予測のために、いくつかのクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8412-146">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="b8412-147">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8412-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="b8412-148">データ モデルを保存するための *DataModels* という名前のディレクトリをプロジェクト内に作成します。ソリューション エクスプローラーで、プロジェクトを右クリックし、**[追加]、[新しいフォルダー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-148">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="b8412-149">「DataModels」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b8412-149">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="b8412-150">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、**[追加]、[新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-150">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="b8412-151">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="b8412-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="b8412-152">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-152">Then, select the **Add** button.</span></span> <span data-ttu-id="b8412-153">コード エディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="b8412-153">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="b8412-154">*SentimentData.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8412-154">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="b8412-155">既存のクラス定義を削除し、次のコードを SentimentData.cs ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b8412-155">Remove the existing class definition and add the following code to the SentimentData.cs file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. <span data-ttu-id="b8412-156">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、**[追加]、[新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-156">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="b8412-157">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを *SentimentPrediction.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="b8412-157">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="b8412-158">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8412-158">Then, select the **Add** button.</span></span> <span data-ttu-id="b8412-159">コード エディターに *SentimentPrediction.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="b8412-159">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="b8412-160">*SentimentPrediction.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8412-160">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="b8412-161">既存のクラス定義を削除し、次のコードを *SentimentPrediction.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b8412-161">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a><span data-ttu-id="b8412-162">予測ロジックを追加する</span><span class="sxs-lookup"><span data-stu-id="b8412-162">Add Prediction Logic</span></span>

<span data-ttu-id="b8412-163">*AnalyzeSentiment* クラスの *Run* メソッドの既存の実装を、次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="b8412-163">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function,"post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        //Create Context
        MLContext mlContext = new MLContext();

        //Load Model
        using (var fs = File.OpenRead("MLModels/sentiment_model.zip"))
        {
            model = mlContext.Model.Load(fs);
        }

        //Parse HTTP Request Body
        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

        //Create Prediction Engine
        PredictionEngine<SentimentData, SentimentPrediction> predictionEngine = model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);

        //Make Prediction
        SentimentPrediction prediction = predictionEngine.Predict(data);

        //Convert prediction to string
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        //Return Prediction
        return (ActionResult)new OkObjectResult(isToxic);
    }
}
```

## <a name="test-locally"></a><span data-ttu-id="b8412-164">ローカルでテストする</span><span class="sxs-lookup"><span data-stu-id="b8412-164">Test Locally</span></span>

<span data-ttu-id="b8412-165">すべてが設定されたので、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="b8412-165">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="b8412-166">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="b8412-166">Run the application</span></span>
1. <span data-ttu-id="b8412-167">PowerShell を開き、プロンプトにコードを入力します。PORT は、アプリケーションが実行されているポートです。</span><span class="sxs-lookup"><span data-stu-id="b8412-167">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="b8412-168">通常、このポートは 7071 です。</span><span class="sxs-lookup"><span data-stu-id="b8412-168">Typically the port is 7071.</span></span> 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="b8412-169">成功した場合、出力は次のテキストのようになります。</span><span class="sxs-lookup"><span data-stu-id="b8412-169">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="b8412-170">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="b8412-170">Congratulations!</span></span> <span data-ttu-id="b8412-171">Azure 関数を使用したインターネット経由での予測の実行に対して、モデルを正常に提供できました。</span><span class="sxs-lookup"><span data-stu-id="b8412-171">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b8412-172">次の手順</span><span class="sxs-lookup"><span data-stu-id="b8412-172">Next Steps</span></span>

- [<span data-ttu-id="b8412-173">Azure に配置する</span><span class="sxs-lookup"><span data-stu-id="b8412-173">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)