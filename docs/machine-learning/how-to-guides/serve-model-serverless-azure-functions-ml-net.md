---
title: Azure Functions にモデルをデプロイする
description: Azure Functions を使用して、インターネット経由で予測用の ML.NET 感情分析機械学習モデルを提供します
ms.date: 06/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 7df7a6f9fcc5a4702171e1aac4b6b67e0c343748
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025982"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="594d9-103">Azure Functions にモデルをデプロイする</span><span class="sxs-lookup"><span data-stu-id="594d9-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="594d9-104">Azure Functions のサーバーレス環境を介して、HTTP 経由での予測のために、事前トレーニング済みの ML.NET 機械学習モデルをデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="594d9-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="594d9-105">`PredictionEnginePool` サービスの拡張機能は、現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="594d9-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="594d9-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="594d9-106">Prerequisites</span></span>

- <span data-ttu-id="594d9-107">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" ワークロードおよび "Azure 開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="594d9-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- <span data-ttu-id="594d9-108">Microsoft.NET.Sdk.Functions NuGet パッケージ バージョン 1.0.28 以降。</span><span class="sxs-lookup"><span data-stu-id="594d9-108">Microsoft.NET.Sdk.Functions NuGet Package version 1.0.28+.</span></span>
- [<span data-ttu-id="594d9-109">Azure Functions ツール</span><span class="sxs-lookup"><span data-stu-id="594d9-109">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="594d9-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="594d9-110">Powershell</span></span>
- <span data-ttu-id="594d9-111">事前トレーニング済みモデル</span><span class="sxs-lookup"><span data-stu-id="594d9-111">Pre-trained model.</span></span> <span data-ttu-id="594d9-112">[ML.NET Sentiment Analysis のチュートリアル](../tutorials/sentiment-analysis.md)を使用して独自のモデルを構築するか、この[事前トレーニング済みの感情分析の機械学習モデル](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)をダウンロードすること。</span><span class="sxs-lookup"><span data-stu-id="594d9-112">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="594d9-113">Azure Functions プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="594d9-113">Create Azure Functions project</span></span>

1. <span data-ttu-id="594d9-114">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="594d9-114">Open Visual Studio 2017.</span></span> <span data-ttu-id="594d9-115">**[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="594d9-116">**[新しいプロジェクト]** ダイアログで、 **[Visual C#]** ノードを選択し、 **[クラウド]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-116">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="594d9-117">次に、**Azure Functions** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-117">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="594d9-118">**[名前]** テキスト ボックスに「SentimentAnalysisFunctionsApp」と入力し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-118">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="594d9-119">**[新しいプロジェクト]** ダイアログで、プロジェクト オプションの上のドロップダウンを開き、 **[Azure Functions v2 (.NET Core)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-119">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="594d9-120">次に、 **[Http トリガー]** プロジェクトを選択し、 **[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-120">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="594d9-121">モデルを保存するための *MLModels* という名前のディレクトリをプロジェクト内に作成します。</span><span class="sxs-lookup"><span data-stu-id="594d9-121">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="594d9-122">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-122">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="594d9-123">「MLModels」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="594d9-123">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="594d9-124">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="594d9-124">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="594d9-125">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-125">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="594d9-126">[パッケージ ソース] として "nuget.org" を選択し、[参照] タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、 **[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-126">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="594d9-127">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-127">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="594d9-128">**Microsoft.Azure.Functions.Extensions NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="594d9-128">Install the **Microsoft.Azure.Functions.Extensions NuGet Package**:</span></span>

    <span data-ttu-id="594d9-129">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-129">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="594d9-130">パッケージ ソースとして "nuget.org" を選択します。[参照] タブを選択し、「**Microsoft.Azure.Functions.Extensions**」を検索します。一覧からそのパッケージを選択し、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-130">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Azure.Functions.Extensions**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="594d9-131">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-131">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="594d9-132">**Microsoft.Extensions.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="594d9-132">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="594d9-133">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-133">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="594d9-134">パッケージ ソースとして "nuget.org" を選択します。[参照] タブを選択し、「**Microsoft.Extensions.ML**」を検索します。一覧からそのパッケージを選択して、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-134">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="594d9-135">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="594d9-136">**Microsoft.NET.Sdk.Functions NuGet パッケージ**をバージョン 1.0.28 に更新します。</span><span class="sxs-lookup"><span data-stu-id="594d9-136">Update the **Microsoft.NET.Sdk.Functions NuGet Package** to version 1.0.28:</span></span>

    <span data-ttu-id="594d9-137">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-137">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="594d9-138">パッケージ ソースとして "nuget.org" を選択します。[参照] タブを選択し、「**Microsoft.NET.Sdk.Functions**」を検索します。一覧からそのパッケージを選択し、[バージョン] ドロップダウンから [1.0.28] またはそれ以降を選択し、 **[更新]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-138">Choose "nuget.org" as the Package source, select the Installed tab, search for **Microsoft.NET.Sdk.Functions**, select that package in the list, select 1.0.28 or later from the Version dropdown, and select the **Update** button.</span></span> <span data-ttu-id="594d9-139">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="594d9-140">事前トレーニング済みモデルをプロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="594d9-140">Add pre-trained model to project</span></span>

1. <span data-ttu-id="594d9-141">構築済みのモデルを *MLModels* フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="594d9-141">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="594d9-142">ソリューション エクスプローラーで、構築済みのモデルのファイルを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-142">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="594d9-143">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="594d9-143">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="594d9-144">Azure 関数を作成してセンチメントを分析する</span><span class="sxs-lookup"><span data-stu-id="594d9-144">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="594d9-145">センチメントを予測するクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="594d9-145">Create a class to predict sentiment.</span></span> <span data-ttu-id="594d9-146">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="594d9-146">Add a new class to your project:</span></span>

1. <span data-ttu-id="594d9-147">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-147">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="594d9-148">**[新しい項目の追加]** ダイアログ ボックスで、 **[Azure 関数]** を選択し、 **[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="594d9-148">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="594d9-149">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-149">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="594d9-150">**[新しい Azure 関数]** ダイアログ ボックスで、 **[Http トリガー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-150">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="594d9-151">次に、 **[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-151">Then, select the **OK** button.</span></span>

    <span data-ttu-id="594d9-152">コード エディターに *AnalyzeSentiment.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="594d9-152">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="594d9-153">*AnalyzeSentiment.cs* の先頭に次の `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="594d9-153">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

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

    <span data-ttu-id="594d9-154">既定では、`AnalyzeSentiment` クラスは `static`です。</span><span class="sxs-lookup"><span data-stu-id="594d9-154">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="594d9-155">クラス定義から `static` キーワードを必ず削除します。</span><span class="sxs-lookup"><span data-stu-id="594d9-155">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="594d9-156">データ モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="594d9-156">Create data models</span></span>

<span data-ttu-id="594d9-157">入力データと予測のために、いくつかのクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="594d9-157">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="594d9-158">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="594d9-158">Add a new class to your project:</span></span>

1. <span data-ttu-id="594d9-159">データ モデルを保存するための *DataModels* という名前のディレクトリをプロジェクト内に作成します。ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[追加]、[新しいフォルダー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-159">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="594d9-160">「DataModels」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="594d9-160">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="594d9-161">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、 **[追加]、[新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-161">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="594d9-162">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="594d9-162">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="594d9-163">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-163">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="594d9-164">コード エディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="594d9-164">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="594d9-165">*SentimentData.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="594d9-165">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="594d9-166">既存のクラス定義を削除し、次のコードを *SentimentData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="594d9-166">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
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

4. <span data-ttu-id="594d9-167">ソリューション エクスプローラーで、*DataModels* ディレクトリを右クリックし、 **[追加]、[新しいアイテム]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-167">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="594d9-168">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *SentimentPrediction.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="594d9-168">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="594d9-169">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-169">Then, select the **Add** button.</span></span> <span data-ttu-id="594d9-170">コード エディターに *SentimentPrediction.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="594d9-170">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="594d9-171">*SentimentPrediction.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="594d9-171">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="594d9-172">既存のクラス定義を削除し、次のコードを *SentimentPrediction.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="594d9-172">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="594d9-173">`SentimentPrediction` は `SentimentData` を継承し、モデルによって生成された出力だけでなく `SentimentText` プロパティで元のデータへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="594d9-173">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="594d9-174">PredictionEnginePool サービスを登録する</span><span class="sxs-lookup"><span data-stu-id="594d9-174">Register PredictionEnginePool service</span></span>

<span data-ttu-id="594d9-175">1 つの予測をするためには、[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) を使用します。</span><span class="sxs-lookup"><span data-stu-id="594d9-175">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="594d9-176">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) をお使いのアプリケーションで使用するには、必要に応じて、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="594d9-176">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="594d9-177">その場合、ベスト プラクティスとして、依存関係を挿入することを検討します。</span><span class="sxs-lookup"><span data-stu-id="594d9-177">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="594d9-178">依存関係の注入の詳細については、[こちらのリンク](https://en.wikipedia.org/wiki/Dependency_injection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="594d9-178">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="594d9-179">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-179">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="594d9-180">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを「*Startup.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="594d9-180">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="594d9-181">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="594d9-181">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="594d9-182">コード エディターに *Startup.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="594d9-182">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="594d9-183">*Startup.cs* の先頭に次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="594d9-183">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="594d9-184">using ステートメントの下にある既存のコードを削除し、*Startup.cs* ファイルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="594d9-184">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

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

<span data-ttu-id="594d9-185">大まかに言えば、このコードは、オブジェクトとサービスがアプリケーションによって要求されたときに、初期化を手動ではなく自動的に実行します。</span><span class="sxs-lookup"><span data-stu-id="594d9-185">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="594d9-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) はスレッド セーフではありません。</span><span class="sxs-lookup"><span data-stu-id="594d9-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="594d9-187">パフォーマンスとスレッドの安全性を改善するために、`PredictionEnginePool` サービスを使用します。これにより、アプリケーションで使用される `PredictionEngine` オブジェクトの [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="594d9-187">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="594d9-188">関数にモデルを読み込む</span><span class="sxs-lookup"><span data-stu-id="594d9-188">Load the model into the function</span></span>

<span data-ttu-id="594d9-189">次のコードを *AnalyzeSentiment* クラス内に挿入します。</span><span class="sxs-lookup"><span data-stu-id="594d9-189">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="594d9-190">このコードでは、依存関係の挿入を通して取得する関数のコンストラクターに渡すことで、`PredictionEnginePool` を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="594d9-190">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="594d9-191">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="594d9-191">Use the model to make predictions</span></span>

<span data-ttu-id="594d9-192">*AnalyzeSentiment* クラスの *Run* メソッドの既存の実装を、次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="594d9-192">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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

<span data-ttu-id="594d9-193">`Run` メソッドが実行されると、HTTP 要求からの受信データが逆シリアル化されて、`PredictionEnginePool` への入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="594d9-193">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="594d9-194">その後、予測を生成してその結果をユーザーに返すために、`Predict` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="594d9-194">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="594d9-195">ローカルでテストする</span><span class="sxs-lookup"><span data-stu-id="594d9-195">Test locally</span></span>

<span data-ttu-id="594d9-196">すべてが設定されたので、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="594d9-196">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="594d9-197">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="594d9-197">Run the application</span></span>
1. <span data-ttu-id="594d9-198">PowerShell を開き、プロンプトにコードを入力します。PORT は、アプリケーションが実行されているポートです。</span><span class="sxs-lookup"><span data-stu-id="594d9-198">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="594d9-199">通常、このポートは 7071 です。</span><span class="sxs-lookup"><span data-stu-id="594d9-199">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="594d9-200">成功した場合、出力は次のテキストのようになります。</span><span class="sxs-lookup"><span data-stu-id="594d9-200">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="594d9-201">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="594d9-201">Congratulations!</span></span> <span data-ttu-id="594d9-202">Azure 関数を使用したインターネット経由での予測の実行に対して、モデルを正常に提供できました。</span><span class="sxs-lookup"><span data-stu-id="594d9-202">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="594d9-203">次の手順</span><span class="sxs-lookup"><span data-stu-id="594d9-203">Next Steps</span></span>

- [<span data-ttu-id="594d9-204">Azure に配置する</span><span class="sxs-lookup"><span data-stu-id="594d9-204">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
