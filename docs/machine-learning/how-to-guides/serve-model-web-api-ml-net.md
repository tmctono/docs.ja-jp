---
title: ASP.NET Core Web API で機械学習モデルを提供する
description: ASP.NET Core Web API を使用して、インターネット経由で予測用の ML.NET 感情分析機械学習モデルを提供します
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 07b751caff8ef0ca9a23bed68ddf88feb7b5ae4f
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57856704"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a><span data-ttu-id="b82c2-103">方法: ASP.NET Core Web API を通して機械学習モデルを提供する</span><span class="sxs-lookup"><span data-stu-id="b82c2-103">How-To: Serve Machine Learning Model Through ASP.NET Core Web API</span></span>

<span data-ttu-id="b82c2-104">このハウツー記事では、構築済みの ML.NET 機械学習モデルを ASP.NET Core Web API を使用して Web に提供する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-104">This how-to shows how to serve a pre-built ML.NET machine learning model to the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="b82c2-105">これを行うことで、ユーザーが標準の HTTP メソッドを使用して、予測目的の API にアクセスすることできます。</span><span class="sxs-lookup"><span data-stu-id="b82c2-105">By doing so it allows for users to access the API for prediction purposes via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="b82c2-106">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b82c2-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="b82c2-107">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b82c2-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="b82c2-108">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="b82c2-108">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="b82c2-109">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b82c2-109">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b82c2-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b82c2-110">Prerequisites</span></span>

- <span data-ttu-id="b82c2-111">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="b82c2-111">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="b82c2-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b82c2-112">Powershell.</span></span>
- <span data-ttu-id="b82c2-113">事前トレーニング済みモデル</span><span class="sxs-lookup"><span data-stu-id="b82c2-113">Pre-trained model.</span></span>
    - <span data-ttu-id="b82c2-114">[ML.NET 感情分析のチュートリアル](../tutorials/sentiment-analysis.md)を使用して、独自のモデルを構築する。</span><span class="sxs-lookup"><span data-stu-id="b82c2-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="b82c2-115">この[事前トレーニング済みの感情分析機械学習モデル](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)をダウンロードする。</span><span class="sxs-lookup"><span data-stu-id="b82c2-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="b82c2-116">ASP.NET Core Web API プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="b82c2-116">Create ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="b82c2-117">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="b82c2-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="b82c2-118">メニュー バーから、**[ファイル]、[新規]、[プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-118">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="b82c2-119">[新しいプロジェクト] ダイアログで、**[Visual C#]** ノードを選択し、**[Web]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-119">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="b82c2-120">次に、**[ASP.NET Core Web アプリケーション]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-120">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="b82c2-121">**[名前]** テキスト ボックスに「SentimentAnalysisWebAPI」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-121">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>
1. <span data-ttu-id="b82c2-122">ASP.NET Core プロジェクトの複数の種類が表示されているウィンドウで、**[API]** を選択し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-122">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>
1. <span data-ttu-id="b82c2-123">構築済みの機械学習モデルを保存するための *MLModels* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-123">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="b82c2-124">ソリューション エクスプローラーで、プロジェクトを右クリックし、[追加]、[新しいフォルダー] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-124">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="b82c2-125">「MLModels」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-125">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="b82c2-126">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b82c2-126">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="b82c2-127">ソリューション エクスプローラーで、プロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="b82c2-128">[パッケージ ソース] として [nuget.org] を選択します。[参照] タブを選択し、「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、[インストール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="b82c2-129">**[変更のプレビュー]** ダイアログで **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、[ライセンスの同意] ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="b82c2-130">モデルを ASP.NET Core Web API プロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="b82c2-130">Add Model to ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="b82c2-131">構築済みのモデルを *MLModels* ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b82c2-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="b82c2-132">ソリューション エクスプローラーで、モデルの zip ファイルを右クリックし、[プロパティ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="b82c2-133">[詳細設定] で、[出力ディレクトリにコピー] の値を [新しい場合はコピーする] に変更します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="build-data-models"></a><span data-ttu-id="b82c2-134">データ モデルを構築する</span><span class="sxs-lookup"><span data-stu-id="b82c2-134">Build Data Models</span></span>

<span data-ttu-id="b82c2-135">入力データと予測のために、いくつかのクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b82c2-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="b82c2-136">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="b82c2-137">データ モデルを保存するための *DataModels* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="b82c2-138">ソリューション エクスプローラーで、プロジェクトを右クリックし、[追加]、[新しいフォルダー] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="b82c2-139">「DataModels」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="b82c2-140">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、[追加]、[新しいアイテム] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="b82c2-141">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="b82c2-142">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-142">Then, select the **Add** button.</span></span> <span data-ttu-id="b82c2-143">コード エディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="b82c2-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="b82c2-144">*SentimentData.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="b82c2-145">既存のクラス定義を削除し、次のコードを **SentimentData.cs** ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. <span data-ttu-id="b82c2-146">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、**[追加]、[新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="b82c2-147">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを *SentimentPrediction.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="b82c2-148">次に、[追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-148">Then, select the Add button.</span></span> <span data-ttu-id="b82c2-149">コード エディターに *SentimentPrediction.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="b82c2-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="b82c2-150">*SentimentPrediction.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="b82c2-151">既存のクラス定義を削除し、次のコードを *SentimentPrediction.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="create-prediction-service"></a><span data-ttu-id="b82c2-152">予測サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="b82c2-152">Create Prediction Service</span></span>

<span data-ttu-id="b82c2-153">予測ロジックを整理し、アプリケーション全体で再利用するために、予測サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-153">To organize and re-use the prediction logic throughout the entire application, create a prediction service.</span></span>

1. <span data-ttu-id="b82c2-154">アプリケーションによって使用されるサービスを保持するために、*Services* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-154">Create a directory named *Services* in your project to hold services to be used by the application:</span></span>

    <span data-ttu-id="b82c2-155">ソリューション エクスプローラーで、プロジェクトを右クリックし、**[追加]、[新しいフォルダー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-155">In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="b82c2-156">「Services」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-156">Type "Services" and hit **Enter**.</span></span>

1. <span data-ttu-id="b82c2-157">ソリューション エクスプローラーで、*Services* ディレクトリを右クリックし、**[追加]、[新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-157">In Solution Explorer, right-click the *Services* directory, and then select **Add > New Item**.</span></span>
1. <span data-ttu-id="b82c2-158">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを *PredictionService.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-158">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *PredictionService.cs*.</span></span> <span data-ttu-id="b82c2-159">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-159">Then, select the **Add** button.</span></span> <span data-ttu-id="b82c2-160">コード エディターに *PredictionService.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="b82c2-160">The *PredictionService.cs* file opens in the code editor.</span></span> <span data-ttu-id="b82c2-161">*PredictionService.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-161">Add the following using statement to the top of *PredictionService.cs*:</span></span>

```csharp
using System;
using System.IO;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

<span data-ttu-id="b82c2-162">既存のクラス定義を削除し、次のコードを *PredictionService.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-162">Remove the existing class definition and add the following code to the *PredictionService.cs* file:</span></span>

```csharp
public class PredictionService
{
    private readonly PredictionEngine<SentimentData, SentimentPrediction> _predictionEngine;
    public PredictionService(PredictionEngine<SentimentData,SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine;
    }

    public string Predict(SentimentData input)
    {
        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return isToxic;

    }
}
```

## <a name="register-predictions-service-for-use-in-application"></a><span data-ttu-id="b82c2-163">アプリケーションで使用するために予測サービスを登録する</span><span class="sxs-lookup"><span data-stu-id="b82c2-163">Register Predictions Service for Use in Application</span></span>

<span data-ttu-id="b82c2-164">アプリケーションで予測サービスを使用するには、必要になるたびにそれを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b82c2-164">To use the prediction service in your application you will have to create it every time it is needed.</span></span> <span data-ttu-id="b82c2-165">この場合のベスト プラクティスは、ASP.NET Core の依存関係の挿入を考慮することです。</span><span class="sxs-lookup"><span data-stu-id="b82c2-165">In that case, a best practice to consider is ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="b82c2-166">依存関係の注入の詳細については、[こちらのリンク](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b82c2-166">The following link provides more information if you want to learn about [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="b82c2-167">*Startup.cs* を開き、ファイルの先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-167">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

```csharp
using System.IO;
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Configuration;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

1. <span data-ttu-id="b82c2-168">*ConfigureServices* メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-168">Add the following lines of code to the *ConfigureServices* method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddSingleton<MLContext>();
    services.AddSingleton<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
    {
        MLContext mlContext = ctx.GetRequiredService<MLContext>();
        string modelFilePathName = "MLModels/sentiment_model.zip";

        //Load model from file
        ITransformer model;
        using (var stream = File.OpenRead(modelFilePathName))
        {
            model = mlContext.Model.Load(stream);
        }

        // Return prediction engine
        return model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);
    });
    services.AddSingleton<PredictionService>();
}
```

<span data-ttu-id="b82c2-169">大まかに言えば、このコードは、オブジェクトとサービスがアプリケーションによって要求されたときに、初期化を手動ではなく自動的に実行します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-169">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="b82c2-170">予測コントローラーを作成する</span><span class="sxs-lookup"><span data-stu-id="b82c2-170">Create Predict Controller</span></span>

<span data-ttu-id="b82c2-171">受信 HTTP 要求を処理するために、コントローラーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b82c2-171">To process your incoming HTTP requests, you need to create a controller.</span></span>

1. <span data-ttu-id="b82c2-172">ソリューション エクスプローラーで、*Controllers* ディレクトリを右クリックし、**[追加]、[コントローラー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-172">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="b82c2-173">**[新しい項目の追加]** ダイアログ ボックスで、**[空の API コントローラー]** を選択し、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-173">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="b82c2-174">プロンプトで、**[コントローラー名]** フィールドを*PredictController.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-174">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="b82c2-175">次に、[追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-175">Then, select the Add button.</span></span> <span data-ttu-id="b82c2-176">コード エディターに *PredictController.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="b82c2-176">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="b82c2-177">*PredictController.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-177">Add the following using statement to the top of *PredictController.cs*:</span></span>

```csharp
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

<span data-ttu-id="b82c2-178">既存のクラス定義を削除し、次のコードを *PredictController.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-178">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

```csharp
public class PredictController : ControllerBase
{

    private readonly PredictionService _predictionService;

    public PredictController(PredictionService predictionService)
    {
        _predictionService = predictionService; //Define prediction service
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }
        return Ok(_predictionService.Predict(input));
    }

}
```

<span data-ttu-id="b82c2-179">これは、依存関係の挿入を通して取得するコントローラーのコンストラクターに渡すことによる予測サービスの割り当てです。</span><span class="sxs-lookup"><span data-stu-id="b82c2-179">This is assigning the Prediction service by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="b82c2-180">これで、このコントローラーの POST メソッドの中で予測サービスを使用して予測が行われ、成功した場合はその結果がユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="b82c2-180">Then, in the POST method of this controller the Prediction service is being used to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="b82c2-181">Web API をローカルでテストする</span><span class="sxs-lookup"><span data-stu-id="b82c2-181">Test Web API Locally</span></span>

<span data-ttu-id="b82c2-182">すべてが設定されたので、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="b82c2-182">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="b82c2-183">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b82c2-183">Run the application.</span></span>
1. <span data-ttu-id="b82c2-184">PowerShell を開き、次のコードを入力します。PORT は、アプリケーションがリスニングしているポートです。</span><span class="sxs-lookup"><span data-stu-id="b82c2-184">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="b82c2-185">成功した場合、出力は次のテキストのようになります。</span><span class="sxs-lookup"><span data-stu-id="b82c2-185">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="b82c2-186">おつかれさまでした。</span><span class="sxs-lookup"><span data-stu-id="b82c2-186">Congratulations!</span></span> <span data-ttu-id="b82c2-187">ASP.NET Core API を使用したインターネット経由での予測の実行に対して、モデルを正常に提供できました。</span><span class="sxs-lookup"><span data-stu-id="b82c2-187">You have successfully served your model to make predictions over the internet using an ASP.NET Core API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b82c2-188">次の手順</span><span class="sxs-lookup"><span data-stu-id="b82c2-188">Next Steps</span></span>

- [<span data-ttu-id="b82c2-189">Azure に配置する</span><span class="sxs-lookup"><span data-stu-id="b82c2-189">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)