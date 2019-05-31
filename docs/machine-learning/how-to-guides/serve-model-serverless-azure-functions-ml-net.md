---
title: Azure Functions にモデルをデプロイする
description: Azure Functions を使用して、インターネット経由で予測用の ML.NET 感情分析機械学習モデルを提供します
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 9e62d8826227aed07451387cc733d27094327f99
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645104"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="5498d-103">Azure Functions にモデルをデプロイする</span><span class="sxs-lookup"><span data-stu-id="5498d-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="5498d-104">Azure Functions のサーバーレス環境を介して、HTTP 経由での予測のために、事前トレーニング済みの ML.NET 機械学習モデルをデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5498d-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="5498d-105">`PredictionEnginePool` サービスの拡張機能は、現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="5498d-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5498d-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5498d-106">Prerequisites</span></span>

- <span data-ttu-id="5498d-107">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" ワークロードおよび "Azure 開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="5498d-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- [<span data-ttu-id="5498d-108">Azure Functions ツール</span><span class="sxs-lookup"><span data-stu-id="5498d-108">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="5498d-109">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5498d-109">Powershell</span></span>
- <span data-ttu-id="5498d-110">事前トレーニング済みモデル</span><span class="sxs-lookup"><span data-stu-id="5498d-110">Pre-trained model.</span></span> <span data-ttu-id="5498d-111">[ML.NET Sentiment Analysis のチュートリアル](../tutorials/sentiment-analysis.md)を使用して独自のモデルを構築するか、この[事前トレーニング済みの感情分析の機械学習モデル](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)をダウンロードすること。</span><span class="sxs-lookup"><span data-stu-id="5498d-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="5498d-112">Azure Functions プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="5498d-112">Create Azure Functions project</span></span>

1. <span data-ttu-id="5498d-113">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="5498d-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="5498d-114">**[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-114">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="5498d-115">**[新しいプロジェクト]** ダイアログで、 **[Visual C#]** ノードを選択し、 **[クラウド]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-115">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="5498d-116">次に、**Azure Functions** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-116">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="5498d-117">**[名前]** テキスト ボックスに「SentimentAnalysisFunctionsApp」と入力し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-117">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="5498d-118">**[新しいプロジェクト]** ダイアログで、プロジェクト オプションの上のドロップダウンを開き、 **[Azure Functions v2 (.NET Core)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-118">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="5498d-119">次に、 **[Http トリガー]** プロジェクトを選択し、 **[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-119">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="5498d-120">モデルを保存するための *MLModels* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="5498d-120">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="5498d-121">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-121">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="5498d-122">「MLModels」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5498d-122">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="5498d-123">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5498d-123">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="5498d-124">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-124">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5498d-125">[パッケージ ソース] として "nuget.org" を選択し、[参照] タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、 **[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-125">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="5498d-126">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-126">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="5498d-127">**Microsoft.Extensions.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5498d-127">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="5498d-128">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5498d-129">パッケージ ソースとして "nuget.org" を選択します。[参照] タブを選択し、「**Microsoft.Extensions.ML**」を検索します。一覧からそのパッケージを選択して、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="5498d-130">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="5498d-131">事前トレーニング済みモデルをプロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="5498d-131">Add pre-trained model to project</span></span>

1. <span data-ttu-id="5498d-132">構築済みのモデルを *MLModels* フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5498d-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="5498d-133">ソリューション エクスプローラーで、構築済みのモデルのファイルを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="5498d-134">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="5498d-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="5498d-135">Azure 関数を作成してセンチメントを分析する</span><span class="sxs-lookup"><span data-stu-id="5498d-135">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="5498d-136">センチメントを予測するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5498d-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="5498d-137">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="5498d-138">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="5498d-139">**[新しい項目の追加]** ダイアログ ボックスで、 **[Azure 関数]** を選択し、 **[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="5498d-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="5498d-140">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="5498d-141">**[新しい Azure 関数]** ダイアログ ボックスで、 **[Http トリガー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="5498d-142">次に、 **[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="5498d-143">コード エディターに *AnalyzeSentiment.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="5498d-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="5498d-144">*AnalyzeSentiment.cs* の先頭に次の `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-144">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

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
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="5498d-145">既定では、`AnalyzeSentiment` クラスは `static`です。</span><span class="sxs-lookup"><span data-stu-id="5498d-145">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="5498d-146">クラス定義から `static` キーワードを必ず削除します。</span><span class="sxs-lookup"><span data-stu-id="5498d-146">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="5498d-147">データ モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="5498d-147">Create data models</span></span>

<span data-ttu-id="5498d-148">入力データと予測のために、いくつかのクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5498d-148">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="5498d-149">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="5498d-150">データ モデルを保存するための *DataModels* という名前のディレクトリをプロジェクト内に作成します。ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[追加]、[新しいフォルダー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-150">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="5498d-151">「DataModels」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5498d-151">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="5498d-152">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、 **[追加]、[新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-152">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="5498d-153">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="5498d-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="5498d-154">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-154">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="5498d-155">コード エディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="5498d-155">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="5498d-156">*SentimentData.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-156">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="5498d-157">既存のクラス定義を削除し、次のコードを *SentimentData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-157">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
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

4. <span data-ttu-id="5498d-158">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、 **[追加]、[新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-158">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="5498d-159">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *SentimentPrediction.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="5498d-159">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="5498d-160">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-160">Then, select the **Add** button.</span></span> <span data-ttu-id="5498d-161">コード エディターに *SentimentPrediction.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="5498d-161">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="5498d-162">*SentimentPrediction.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-162">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="5498d-163">既存のクラス定義を削除し、次のコードを *SentimentPrediction.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-163">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="5498d-164">`SentimentPrediction` は `SentimentData` を継承し、モデルによって生成された出力だけでなく `SentimentText` プロパティで元のデータへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5498d-164">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="5498d-165">PredictionEnginePool サービスを登録する</span><span class="sxs-lookup"><span data-stu-id="5498d-165">Register PredictionEnginePool service</span></span>

<span data-ttu-id="5498d-166">1 つの予測をするためには、[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5498d-166">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="5498d-167">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) をお使いのアプリケーションで使用するには、必要に応じて、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5498d-167">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="5498d-168">その場合、ベスト プラクティスとして、依存関係を挿入することを検討します。</span><span class="sxs-lookup"><span data-stu-id="5498d-168">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="5498d-169">依存関係の注入の詳細については、[こちらのリンク](https://en.wikipedia.org/wiki/Dependency_injection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5498d-169">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="5498d-170">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-170">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="5498d-171">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを「*Startup.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="5498d-171">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="5498d-172">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-172">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="5498d-173">コード エディターに *Startup.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="5498d-173">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="5498d-174">*Startup.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-174">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="5498d-175">using ステートメントの下にある既存のコードを削除し、*Startup.cs* ファイルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-175">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: WebJobsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        class Startup : IWebJobsStartup
        {
            public void Configure(IWebJobsBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

<span data-ttu-id="5498d-176">大まかに言えば、このコードは、オブジェクトとサービスがアプリケーションによって要求されたときに、初期化を手動ではなく自動的に実行します。</span><span class="sxs-lookup"><span data-stu-id="5498d-176">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="5498d-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) はスレッド セーフではありません。</span><span class="sxs-lookup"><span data-stu-id="5498d-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="5498d-178">パフォーマンスの向上とスレッドの安全性のために、`PredictionEnginePool` サービスを使用します。これにより、アプリケーションで使用される `PredictionEngine` オブジェクトの [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5498d-178">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="register-startup-as-an-azure-functions-extension"></a><span data-ttu-id="5498d-179">Azure Functions の拡張機能として Startup を登録する</span><span class="sxs-lookup"><span data-stu-id="5498d-179">Register Startup as an Azure Functions extension</span></span>

<span data-ttu-id="5498d-180">`Startup` をお使いのアプリケーションで使用するには、Azure Functions の拡張機能として登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5498d-180">In order to use `Startup` in your application, you need to register it as an Azure Functions extension.</span></span> <span data-ttu-id="5498d-181">まだ存在しない場合は、*extensions.json* という新しいファイルをお使いのプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="5498d-181">Create a new file called *extensions.json* in your project if one does not already exist.</span></span>

1. <span data-ttu-id="5498d-182">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-182">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="5498d-183">**[新しい項目]** ダイアログで、 **[Visual C#]** ノード、 **[Web]** ノードの順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-183">In the **New Item** dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="5498d-184">次に、 **[Json ファイル]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-184">Then select the **Json File** option.</span></span> <span data-ttu-id="5498d-185">**[名前]** テキスト ボックスに「extensions.json」と入力し、 **[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-185">In the **Name** text box, type "extensions.json" and then select the **OK** button.</span></span>

    <span data-ttu-id="5498d-186">コード エディターに *extensions.json* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="5498d-186">The *extensions.json* file opens in the code editor.</span></span> <span data-ttu-id="5498d-187">次の内容を *extensions.json* に追加します。</span><span class="sxs-lookup"><span data-stu-id="5498d-187">Add the following content to *extensions.json*:</span></span>
    
    ```json
    {
      "extensions": [
        {
          "name": "Startup",
          "typename": "SentimentAnalysisFunctionsApp.Startup, SentimentAnalysisFunctionsApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"
        }
      ]
    }
    ```

1. <span data-ttu-id="5498d-188">ソリューション エクスプローラーで、*extensions.json* ファイルを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5498d-188">In Solution Explorer, right-click your *extensions.json* file and select **Properties**.</span></span> <span data-ttu-id="5498d-189">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="5498d-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="5498d-190">関数にモデルを読み込む</span><span class="sxs-lookup"><span data-stu-id="5498d-190">Load the model into the function</span></span>

<span data-ttu-id="5498d-191">次のコードを *AnalyzeSentiment* クラス内に挿入します。</span><span class="sxs-lookup"><span data-stu-id="5498d-191">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="5498d-192">このコードでは、依存関係の挿入を通して取得する関数のコンストラクターに渡すことで、`PredictionEnginePool` を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5498d-192">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="5498d-193">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="5498d-193">Use the model to make predictions</span></span>

<span data-ttu-id="5498d-194">*AnalyzeSentiment* クラスの *Run* メソッドの既存の実装を、次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5498d-194">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
[FunctionName("AnalyzeSentiment")]
public async Task<IActionResult> Run(
[HttpTrigger(AuthorizationLevel.Function, "post", Route = null)] HttpRequest req,
ILogger log)
{
    log.LogInformation("C# HTTP trigger function processed a request.");

    //Parse HTTP Request Body
    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);
    
    //Make Prediction
    SentimentPrediction prediction = _predictionEnginePool.Predict(data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

<span data-ttu-id="5498d-195">`Run` メソッドが実行されると、HTTP 要求からの受信データが逆シリアル化されて、`PredictionEnginePool` への入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="5498d-195">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="5498d-196">その後、予測を生成してその結果をユーザーに返すために、`Predict` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5498d-196">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="5498d-197">ローカルでテストする</span><span class="sxs-lookup"><span data-stu-id="5498d-197">Test locally</span></span>

<span data-ttu-id="5498d-198">すべてが設定されたので、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="5498d-198">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="5498d-199">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="5498d-199">Run the application</span></span>
1. <span data-ttu-id="5498d-200">PowerShell を開き、プロンプトにコードを入力します。PORT は、アプリケーションが実行されているポートです。</span><span class="sxs-lookup"><span data-stu-id="5498d-200">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="5498d-201">通常、このポートは 7071 です。</span><span class="sxs-lookup"><span data-stu-id="5498d-201">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="5498d-202">成功した場合、出力は次のテキストのようになります。</span><span class="sxs-lookup"><span data-stu-id="5498d-202">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="5498d-203">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="5498d-203">Congratulations!</span></span> <span data-ttu-id="5498d-204">Azure 関数を使用したインターネット経由での予測の実行に対して、モデルを正常に提供できました。</span><span class="sxs-lookup"><span data-stu-id="5498d-204">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5498d-205">次の手順</span><span class="sxs-lookup"><span data-stu-id="5498d-205">Next Steps</span></span>

- [<span data-ttu-id="5498d-206">Azure に配置する</span><span class="sxs-lookup"><span data-stu-id="5498d-206">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
