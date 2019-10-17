---
title: チュートリアル:センチメントの分析 - 二項分類
description: このチュートリアルでは、Web サイトのコメントのセンチメントを分類して適切なアクションを実行する Razor Pages アプリケーションの作成方法について説明します。 この二項センチメント分類子では、Visual Studio の C# を使用します。
ms.date: 10/08/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 4a97fb70caafd7b0003830259ddbb0ec72a2ca8a
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180270"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a><span data-ttu-id="5531f-104">チュートリアル:ML.NET モデル ビルダーを使用して Web アプリケーションで Web サイトのコメントのセンチメントを分析する</span><span class="sxs-lookup"><span data-stu-id="5531f-104">Tutorial: Analyze sentiment of website comments in a web application using ML.NET Model Builder</span></span>

<span data-ttu-id="5531f-105">ここでは、Web アプリケーション内部でコメントからセンチメントをリアルタイムで分析する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="5531f-105">Learn how to analyze sentiment from comments in real-time inside a web application.</span></span>

<span data-ttu-id="5531f-106">このチュートリアルでは、Web サイトのコメントのセンチメントをリアルタイムで分類する ASP.NET Core Razor Pages アプリケーションの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5531f-106">This tutorial shows you how to create an ASP.NET Core Razor Pages application that classifies sentiment from website comments in real-time.</span></span>

<span data-ttu-id="5531f-107">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="5531f-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="5531f-108">ASP.NET Core Razor Pages アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="5531f-108">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="5531f-109">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="5531f-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="5531f-110">シナリオを選択する</span><span class="sxs-lookup"><span data-stu-id="5531f-110">Choose a scenario</span></span>
> - <span data-ttu-id="5531f-111">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="5531f-111">Load the data</span></span>
> - <span data-ttu-id="5531f-112">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="5531f-112">Train the model</span></span>
> - <span data-ttu-id="5531f-113">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="5531f-113">Evaluate the model</span></span>
> - <span data-ttu-id="5531f-114">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="5531f-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="5531f-115">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="5531f-115">Model Builder is currently in Preview.</span></span>

<span data-ttu-id="5531f-116">このチュートリアルのソース コードは、[dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="5531f-116">You can find the source code for this tutorial at the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples) repository.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="5531f-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="5531f-117">Pre-requisites</span></span>

<span data-ttu-id="5531f-118">前提条件の一覧とインストール手順は、[モデル ビルダーのインストール ガイド](../how-to-guides/install-model-builder.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5531f-118">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-razor-pages-application"></a><span data-ttu-id="5531f-119">Razor Pages アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="5531f-119">Create a Razor Pages application</span></span>

1. <span data-ttu-id="5531f-120">**ASP.NET Core Razor Pages アプリケーション**を作成します。</span><span class="sxs-lookup"><span data-stu-id="5531f-120">Create a **ASP.NET Core Razor Pages Application**.</span></span>

    1. <span data-ttu-id="5531f-121">Visual Studio を開いて、メニュー バーで **[ファイル]、[新規]、[プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-121">Open Visual Studio and select **File > New > Project** from the menu bar.</span></span>
    1. <span data-ttu-id="5531f-122">[新しいプロジェクト] ダイアログで、 **[Visual C#]** ノードを選択し、 **[Web]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-122">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span>
    1. <span data-ttu-id="5531f-123">次に、 **[ASP.NET Core Web アプリケーション]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-123">Then select the **ASP.NET Core Web Application** project template.</span></span>
    1. <span data-ttu-id="5531f-124">**[名前]** テキスト ボックスに「SentimentRazor」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5531f-124">In the **Name** text box, type "SentimentRazor".</span></span>
    1. <span data-ttu-id="5531f-125">**[ソリューションのディレクトリの作成]** チェックボックスは、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="5531f-125">The **Create a directory for solution** checkbox should be checked by default.</span></span> <span data-ttu-id="5531f-126">オンになっていない場合は、オンにします。</span><span class="sxs-lookup"><span data-stu-id="5531f-126">If that's not the case, check it.</span></span>
    1. <span data-ttu-id="5531f-127">**[OK]**  ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-127">Select the **OK** button.</span></span>
    1. <span data-ttu-id="5531f-128">さまざまな種類の ASP.NET Core プロジェクトが表示されているウィンドウで、 **[Web アプリケーション]** を選択し、 **[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-128">Choose **Web Application** in the window that displays the different types of ASP.NET Core Projects, and then select the **OK** button.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="5531f-129">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="5531f-129">Prepare and understand the data</span></span>

<span data-ttu-id="5531f-130">[Wikipedia detox データセット](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5531f-130">Download [Wikipedia detox dataset](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span> <span data-ttu-id="5531f-131">Web ページが開いたら、そのページを右クリックして、 **[名前を付けて保存]** を選択し、コンピューター上の任意の場所にファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5531f-131">When the webpage opens, right-click on the page, select **Save As** and save the file anywhere on your computer.</span></span>

<span data-ttu-id="5531f-132">*wikipedia-detox-250-line-data.tsv* データセットの各行は、ユーザーが Wikipedia に残した異なるレビューを表します。</span><span class="sxs-lookup"><span data-stu-id="5531f-132">Each row in the *wikipedia-detox-250-line-data.tsv* dataset represents a different review left by a user on Wikipedia.</span></span> <span data-ttu-id="5531f-133">最初の列は、テキストのセンチメントを表し (0 は無害、1 は有害)、2 番目の列はユーザーが残したコメントを表します。</span><span class="sxs-lookup"><span data-stu-id="5531f-133">The first column represents the sentiment of the text (0 is non-toxic, 1 is toxic), and the second column represents the comment left by the user.</span></span> <span data-ttu-id="5531f-134">列はタブで区切られます。</span><span class="sxs-lookup"><span data-stu-id="5531f-134">The columns are separated by tabs.</span></span> <span data-ttu-id="5531f-135">データは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5531f-135">The data looks like the following:</span></span>

| <span data-ttu-id="5531f-136">センチメント</span><span class="sxs-lookup"><span data-stu-id="5531f-136">Sentiment</span></span> | <span data-ttu-id="5531f-137">SentimentText</span><span class="sxs-lookup"><span data-stu-id="5531f-137">SentimentText</span></span> |
| :---: | :---: |
<span data-ttu-id="5531f-138">1</span><span class="sxs-lookup"><span data-stu-id="5531f-138">1</span></span> | <span data-ttu-id="5531f-139">==無礼== なんて無礼な。Carl のその画像をアップロードし戻しておくのが身のためだぞ。</span><span class="sxs-lookup"><span data-stu-id="5531f-139">==RUDE== Dude, you are rude upload that carl picture back, or else.</span></span>
<span data-ttu-id="5531f-140">1</span><span class="sxs-lookup"><span data-stu-id="5531f-140">1</span></span> | <span data-ttu-id="5531f-141">== OK!</span><span class="sxs-lookup"><span data-stu-id="5531f-141">== OK!</span></span> <span data-ttu-id="5531f-142">==  それなら、WILD ONES WIKI をぶっ壊す!!!</span><span class="sxs-lookup"><span data-stu-id="5531f-142">==  IM GOING TO VANDALIZE WILD ONES WIKI THEN!!!</span></span>
<span data-ttu-id="5531f-143">0</span><span class="sxs-lookup"><span data-stu-id="5531f-143">0</span></span> | <span data-ttu-id="5531f-144">この情報がお役に立てば幸いです。</span><span class="sxs-lookup"><span data-stu-id="5531f-144">I hope this helps.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="5531f-145">シナリオを選択する</span><span class="sxs-lookup"><span data-stu-id="5531f-145">Choose a scenario</span></span>

![Visual Studio のモデル ビルダー ウィザード](./media/sentiment-analysis-model-builder/model-builder-screen.png)

<span data-ttu-id="5531f-147">モデルをトレーニングするには、モデル ビルダーによって提供される機械学習シナリオの一覧から選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5531f-147">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span>

1. <span data-ttu-id="5531f-148">**ソリューション エクスプローラー**で、 *[SentimentRazor]* プロジェクトを右クリックし、 **[追加]**  >  **[機械学習]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-148">In **Solution Explorer**, right-click the *SentimentRazor* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="5531f-149">このサンプルのシナリオは、センチメント分析です。</span><span class="sxs-lookup"><span data-stu-id="5531f-149">For this sample, the scenario is sentiment analysis.</span></span> <span data-ttu-id="5531f-150">モデル ビルダー ツールの "*シナリオ*" の手順で、 **[センチメント分析]** シナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-150">In the *scenario* step of the Model Builder tool, select the **Sentiment Analysis** scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="5531f-151">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="5531f-151">Load the data</span></span>

<span data-ttu-id="5531f-152">モデル ビルダーは、SQL Server データベースか、`csv` 形式または `tsv` 形式のローカル ファイルという 2 つのソースからデータを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5531f-152">Model Builder accepts data from two sources, a SQL Server database or a local file in `csv` or `tsv` format.</span></span>

1. <span data-ttu-id="5531f-153">モデル ビルダー ツールのデータの手順で、データ ソースのドロップダウンから **[ファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-153">In the data step of the Model Builder tool, select **File** from the data source dropdown.</span></span>
1. <span data-ttu-id="5531f-154">**[ファイルの選択]** テキスト ボックスの横にあるボタンを選択し、エクスプローラーを使用してファイルを参照し、*wikipedia-detox-250-line-data.tsv* ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-154">Select the button next to the **Select a file** text box and use File Explorer to browse and select the *wikipedia-detox-250-line-data.tsv* file.</span></span>
1. <span data-ttu-id="5531f-155">**[Column to Predict (Label)]\(予測する列 (ラベル)\)** ドロップダウンで **[センチメント]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-155">Choose **Sentiment** in the **Column to Predict (Label)** dropdown.</span></span>
1. <span data-ttu-id="5531f-156">**[Input Columns (Features)]\(入力列 (特徴)\)** ドロップダウンは既定値のままにします。</span><span class="sxs-lookup"><span data-stu-id="5531f-156">Leave the default values for the **Input Columns (Features)** dropdown.</span></span>
1. <span data-ttu-id="5531f-157">**[トレーニング]** リンクを選択して、モデル ビルダー ツールの次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="5531f-157">Select the **Train** link to move to the next step in the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="5531f-158">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="5531f-158">Train the model</span></span>

<span data-ttu-id="5531f-159">このチュートリアルで、感情分析モデルのトレーニングに使用する機械学習のタスクは、二項分類です。</span><span class="sxs-lookup"><span data-stu-id="5531f-159">The machine learning task used to train the sentiment analysis model in this tutorial is binary classification.</span></span> <span data-ttu-id="5531f-160">モデルのトレーニング プロセス中、モデル ビルダーは、データセットに対して最もパフォーマンスの優れたモデルを見つけるために、さまざまな二項分類アルゴリズムと設定を使用して個々のモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="5531f-160">During the model training process, Model Builder trains separate models using different binary classification algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="5531f-161">モデルのトレーニングに必要な時間は、データの量に比例します。</span><span class="sxs-lookup"><span data-stu-id="5531f-161">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="5531f-162">モデル ビルダーにより、 **[Time to train (seconds)]\(トレーニング時間 (秒)\)** の既定値が、データ ソースのサイズに基づいて自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-162">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="5531f-163">モデル ビルダーによって **[トレーニング時間 (秒)]** の値が 10 秒に設定しますが、30 秒に増加します。</span><span class="sxs-lookup"><span data-stu-id="5531f-163">Although Model Builder sets the value of **Time to train (seconds)** to 10 seconds, increase it to 30 seconds.</span></span> <span data-ttu-id="5531f-164">トレーニング時間が長いほど、モデル ビルダーは最良のモデルの検索の中で、より多くのアルゴリズムやパラメーターの組み合わせを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="5531f-164">Training for a longer period of time allows Model Builder to explore a larger number of algorithms and combination of parameters in search of the best model.</span></span>
1. <span data-ttu-id="5531f-165">**[Start Training]\(トレーニング開始\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-165">Select **Start Training**.</span></span>

    <span data-ttu-id="5531f-166">トレーニング プロセスを通して、進捗データがトレーニングの手順の `Progress` セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-166">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

    - <span data-ttu-id="5531f-167">状態には、トレーニング プロセスの完了ステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-167">Status displays the completion status of the training process.</span></span>
    - <span data-ttu-id="5531f-168">[Best accuracy]\(最良の精度\) には、これまでにモデル ビルダーで見つかった最良のパフォーマンスのモデルの精度が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-168">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="5531f-169">精度が高くなるほど、テスト データでモデルが正確に予測されたことになります。</span><span class="sxs-lookup"><span data-stu-id="5531f-169">Higher accuracy means the model predicted more correctly on test data.</span></span>
    - <span data-ttu-id="5531f-170">[Best algorithm]\(最良のアルゴリズム\) には、これまでにモデル ビルダーで見つかった最良のパフォーマンスのアルゴリズムの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-170">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
    - <span data-ttu-id="5531f-171">[Last algorithm]\(最後のアルゴリズム\) には、モデル ビルダーがモデルのトレーニングに最近使用したアルゴリズムの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-171">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

1. <span data-ttu-id="5531f-172">トレーニングが完了したら、 **[評価]** リンクを選択して、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="5531f-172">Once training is complete, select the **evaluate** link to move to the next step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="5531f-173">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="5531f-173">Evaluate the model</span></span>

<span data-ttu-id="5531f-174">トレーニングの手順の結果が、最良のパフォーマンスだった 1 つのモデルになります。</span><span class="sxs-lookup"><span data-stu-id="5531f-174">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="5531f-175">モデル ビルダー ツールの評価の手順の出力セクションには、 **[Best Model]\(最良のモデル\)** エントリの最良のパフォーマンスのモデルで使用されたアルゴリズムと、 **[Best Model Accuracy]\(最良のモデル精度\)** のメトリックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5531f-175">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the **Best Model** entry along with metrics in **Best Model Accuracy**.</span></span> <span data-ttu-id="5531f-176">また、概要テーブルには上位 5 つのモデルとそのメトリックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5531f-176">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="5531f-177">精度のメトリックに不満がある場合、モデルのトレーニング時間を増やすか、さらに多くのデータを使用すると、モデルの精度を簡単に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="5531f-177">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="5531f-178">それ以外の場合、 **[コード]** リンクを選択して、モデル ビルダー ツールの最後の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="5531f-178">Otherwise, select the **code** link to move to the final step in the Model Builder tool.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="5531f-179">予測を行うコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5531f-179">Add the code to make predictions</span></span>

<span data-ttu-id="5531f-180">トレーニング プロセスの結果として 2 つのプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-180">Two projects will be created as a result of the training process.</span></span>

### <a name="reference-the-trained-model"></a><span data-ttu-id="5531f-181">トレーニング済みモデルの参照</span><span class="sxs-lookup"><span data-stu-id="5531f-181">Reference the trained model</span></span>

1. <span data-ttu-id="5531f-182">モデル ビルダー ツールの "*コード*" の手順で、 **[プロジェクトの追加]** を選択して、自動生成されたプロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="5531f-182">In the *code* step of the Model Builder tool, select **Add Projects** to add the autogenerated projects to the solution.</span></span>

    <span data-ttu-id="5531f-183">**ソリューション エクスプローラー**に次のプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-183">The following projects should appear in the **Solution Explorer**:</span></span>

    - <span data-ttu-id="5531f-184">*SentimentRazorML.ConsoleApp*: モデル トレーニングと予測コードが含まれる .NET Core コンソール アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="5531f-184">*SentimentRazorML.ConsoleApp*: A .NET Core Console application that contains the model training and prediction code.</span></span>
    - <span data-ttu-id="5531f-185">*SentimentRazorML.Model*: 入出力モデル データのスキーマを定義するデータ モデルと、トレーニング中にパフォーマンスが最も良かったモデルの保存済みバージョンが含まれる .NET Standard クラス ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="5531f-185">*SentimentRazorML.Model*: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the saved version of the best performing model during training.</span></span>

    <span data-ttu-id="5531f-186">このチュートリアルでは、コンソールではなく *SentimentRazor* Web アプリケーションで予測を行うため、*SentimentRazorML.Model* プロジェクトのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="5531f-186">For this tutorial, only the *SentimentRazorML.Model* project is used because predictions will be made in the *SentimentRazor* web application rather than in the console.</span></span> <span data-ttu-id="5531f-187">*SentimentRazorML.ConsoleApp* はスコアリングに使用されませんが、これは、後で新しいデータを使用してモデルを再トレーニングするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5531f-187">Although the *SentimentRazorML.ConsoleApp* won't be used for scoring, it can be used to retrain the model using new data at a later time.</span></span> <span data-ttu-id="5531f-188">ただし、再トレーニングはこのチュートリアルの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="5531f-188">Retraining is outside the scope of this tutorial though.</span></span>

### <a name="configure-the-predictionengine-pool"></a><span data-ttu-id="5531f-189">PredictionEngine プールの構成</span><span class="sxs-lookup"><span data-stu-id="5531f-189">Configure the PredictionEngine pool</span></span>

<span data-ttu-id="5531f-190">1 つの予測を作成するには、[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5531f-190">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="5531f-191">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) はスレッド セーフではありません。</span><span class="sxs-lookup"><span data-stu-id="5531f-191">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="5531f-192">さらに、アプリケーション内で必要なすべての場所にそのインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5531f-192">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="5531f-193">アプリケーションの規模が拡大すると、このプロセスが管理不能になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5531f-193">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="5531f-194">パフォーマンスとスレッド セーフを向上させるには、依存性の挿入と `PredictionEnginePool` サービスを組み合わせて使用します。これにより、アプリケーション全体で使用する [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) オブジェクトの [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-194">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

1. <span data-ttu-id="5531f-195">*Microsoft.Extensions.ML* NuGet パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5531f-195">Install the *Microsoft.Extensions.ML* NuGet package:</span></span>

    1. <span data-ttu-id="5531f-196">**ソリューション エクスプローラー**でプロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="5531f-196">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span>
    1. <span data-ttu-id="5531f-197">[パッケージ ソース] として [nuget.org] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-197">Choose "nuget.org" as the Package source.</span></span>
    1. <span data-ttu-id="5531f-198">**[参照]** タブを選択して、「**Microsoft.Extensions.ML**」を検索します。</span><span class="sxs-lookup"><span data-stu-id="5531f-198">Select the **Browse** tab and search for **Microsoft.Extensions.ML**.</span></span>
    1. <span data-ttu-id="5531f-199">リストでパッケージを選択して、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-199">Select the package in the list, and select the **Install** button.</span></span>
    1. <span data-ttu-id="5531f-200">**[変更のプレビュー]** ダイアログで **[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-200">Select the **OK** button on the **Preview Changes** dialog</span></span>
    1. <span data-ttu-id="5531f-201">一覧表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスへの同意]** ダイアログで **[同意する]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5531f-201">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="5531f-202">*SentimentRazor* プロジェクトで *Startup.cs* ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5531f-202">Open the *Startup.cs* file in the *SentimentRazor* project.</span></span>
1. <span data-ttu-id="5531f-203">*Microsoft.Extensions.ML* NuGet パッケージと *SentimentRazorML.Model* プロジェクトを参照する次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5531f-203">Add the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and *SentimentRazorML.Model* project:</span></span>

    ```csharp
    using System.IO;
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

1. <span data-ttu-id="5531f-204">トレーニング済みのモデル ファイルの場所を格納するグローバル変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="5531f-204">Create a global variable to store the location of the trained model file.</span></span>

    ```csharp
    private readonly string _modelPath;
    ```

1. <span data-ttu-id="5531f-205">モデル ファイルは、アプリケーションのアセンブリ ファイルと共にビルド ディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-205">The model file is stored in the build directory alongside the assembly files of your application.</span></span> <span data-ttu-id="5531f-206">アクセスしやすいように、`Configure` メソッドの後に `GetAbsolutePath` というヘルパー メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="5531f-206">To make it easier to access, create a helper method called `GetAbsolutePath` after the `Configure` method</span></span>

    ```csharp
    public static string GetAbsolutePath(string relativePath)
    {
        FileInfo _dataRoot = new FileInfo(typeof(Program).Assembly.Location);
        string assemblyFolderPath = _dataRoot.Directory.FullName;

        string fullPath = Path.Combine(assemblyFolderPath, relativePath);
        return fullPath;
    }    
    ```

1. <span data-ttu-id="5531f-207">`Startup` クラス コンストラクターで `GetAbsolutePath` メソッドを使用して、`_modelPath` を設定します。</span><span class="sxs-lookup"><span data-stu-id="5531f-207">Use the `GetAbsolutePath` method in the `Startup` class constructor to set the `_modelPath`.</span></span>

    ```csharp
    _modelPath = GetAbsolutePath("MLModel.zip");
    ```

1. <span data-ttu-id="5531f-208">`ConfigureServices` メソッドでアプリケーションの `PredictionEnginePool` を構成します。</span><span class="sxs-lookup"><span data-stu-id="5531f-208">Configure the `PredictionEnginePool` for your application in the `ConfigureServices` method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<ModelInput, ModelOutput>()
            .FromFile(_modelPath);
    ```

### <a name="create-sentiment-analysis-handler"></a><span data-ttu-id="5531f-209">センチメント分析ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="5531f-209">Create sentiment analysis handler</span></span>

<span data-ttu-id="5531f-210">予測は、アプリケーションのメイン ページ内で行われます。</span><span class="sxs-lookup"><span data-stu-id="5531f-210">Predictions will be made inside the main page of the application.</span></span> <span data-ttu-id="5531f-211">このため、ユーザー入力を受け取り、`PredictionEnginePool` を使用して予測を返すメソッドを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5531f-211">Therefore, a method that takes the user input and uses the `PredictionEnginePool` to return a prediction needs to be added.</span></span>

1. <span data-ttu-id="5531f-212">*Pages* ディレクトリにある *Index.cshtml.cs* ファイルを開いて、次の using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5531f-212">Open the *Index.cshtml.cs* file located in the *Pages* directory and add the following using statements:</span></span>

    ```csharp
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

    <span data-ttu-id="5531f-213">`Startup` クラスで構成された `PredictionEnginePool` を使用するには、使用するモデルのコンストラクターにそれを挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5531f-213">In order to use the `PredictionEnginePool` configured in the `Startup` class, you have to inject it into the constructor of the model where you want to use it.</span></span>

1. <span data-ttu-id="5531f-214">`IndexModel` クラス内で `PredictionEnginePool` を参照する変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="5531f-214">Add a variable to reference the `PredictionEnginePool` inside the `IndexModel` class.</span></span>

    ```csharp
    private readonly PredictionEnginePool<ModelInput, ModelOutput> _predictionEnginePool;
    ```

1. <span data-ttu-id="5531f-215">`IndexModel` クラスでコンストラクターを作成し、それに `PredictionEnginePool` サービスを挿入します。</span><span class="sxs-lookup"><span data-stu-id="5531f-215">Create a constructor in the `IndexModel` class and inject the `PredictionEnginePool` service into it.</span></span>

    ```csharp
    public IndexModel(PredictionEnginePool<ModelInput, ModelOutput> predictionEnginePool)
    {
        _predictionEnginePool = predictionEnginePool;
    }    
    ```

1. <span data-ttu-id="5531f-216">`PredictionEnginePool` を使用して、Web ページから受け取ったユーザー入力から予測を行うメソッド ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5531f-216">Create a method handler that uses the `PredictionEnginePool` to make predictions from user input received from the web page.</span></span>

    1. <span data-ttu-id="5531f-217">`OnGet` メソッドの下に、`OnGetAnalyzeSentiment` という新しいメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="5531f-217">Below the `OnGet` method, create a new method called `OnGetAnalyzeSentiment`</span></span>

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. <span data-ttu-id="5531f-218">ユーザーからの入力が空白または null の場合、`OnGetAnalyzeSentiment` メソッド内で、"*ニュートラル*" センチメントを返します。</span><span class="sxs-lookup"><span data-stu-id="5531f-218">Inside the `OnGetAnalyzeSentiment` method, return *Neutral* sentiment if the input from the user is blank or null.</span></span>

        ```csharp
        if (String.IsNullOrEmpty(text)) return Content("Neutral");
        ```

    1. <span data-ttu-id="5531f-219">入力が有効な場合は、`ModelInput` の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5531f-219">Given a valid input, create a new instance of `ModelInput`.</span></span>

        ```csharp
        var input = new ModelInput { SentimentText = text };
        ```

    1. <span data-ttu-id="5531f-220">`PredictionEnginePool` を使用してセンチメントを予測します。</span><span class="sxs-lookup"><span data-stu-id="5531f-220">Use the `PredictionEnginePool` to predict sentiment.</span></span>

        ```csharp
        var prediction = _predictionEnginePool.Predict(input);
        ```

    1. <span data-ttu-id="5531f-221">次のコードを使用して、予測された `bool` 値を有害または無害に変換します。</span><span class="sxs-lookup"><span data-stu-id="5531f-221">Convert the predicted `bool` value into toxic or not toxic with the following code.</span></span>

        ```csharp
        var sentiment = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";
        ```

    1. <span data-ttu-id="5531f-222">最後に、センチメントを Web ページに返します。</span><span class="sxs-lookup"><span data-stu-id="5531f-222">Finally, return the sentiment back to the web page.</span></span>

        ```csharp
        return Content(sentiment);
        ```

### <a name="configure-the-web-page"></a><span data-ttu-id="5531f-223">Web ページの構成</span><span class="sxs-lookup"><span data-stu-id="5531f-223">Configure the web page</span></span>

<span data-ttu-id="5531f-224">`OnGetAnalyzeSentiment` によって返される結果は、`Index` Web ページに動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5531f-224">The results returned by the `OnGetAnalyzeSentiment` will be dynamically displayed on the `Index` web page.</span></span>

1. <span data-ttu-id="5531f-225">*Pages* ディレクトリ内にある *Index.cshtm* を開いて、その内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5531f-225">Open the *Index.cshtml* file in the *Pages* directory and replace its contents with the following code:</span></span>

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. <span data-ttu-id="5531f-226">次に、*wwwroot\css* ディレクトリ内の *site.css* ページの末尾に css スタイル コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5531f-226">Next, add css styling code to the end of the *site.css* page in the *wwwroot\css* directory:</span></span>

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. <span data-ttu-id="5531f-227">その後、入力を Web ページから `OnGetAnalyzeSentiment` ハンドラーに送信するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5531f-227">After that, add code to send inputs from the web page to the `OnGetAnalyzeSentiment` handler.</span></span>

    1. <span data-ttu-id="5531f-228">*wwwroot\js* ディレクトリ内にある *site.js* ファイルで、`getSentiment` という関数を作成し、`OnGetAnalyzeSentiment` ハンドラーへのユーザー入力を使用して GET HTTP 要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="5531f-228">In the *site.js* file located in the *wwwroot\js* directory, create a function called `getSentiment` to make a GET HTTP request with the user input to the `OnGetAnalyzeSentiment` handler.</span></span>

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. <span data-ttu-id="5531f-229">その下に、`updateMarker` という別の関数を追加して、センチメントが予測されると、Web ページ上のマーカーの位置を動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="5531f-229">Below that, add another function called `updateMarker` to dynamically update the position of the marker on the web page as sentiment is predicted.</span></span>

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. <span data-ttu-id="5531f-230">`updateSentiment`というイベント ハンドラー関数を作成し、ユーザーから入力を取得し、`getSentiment` 関数を使用してそれを `OnGetAnalyzeSentiment` 関数に送信し、`updateMarker` 関数でマーカーを更新します。</span><span class="sxs-lookup"><span data-stu-id="5531f-230">Create an event handler function called `updateSentiment` to get the input from the user, send it to the `OnGetAnalyzeSentiment` function using the `getSentiment` function and update the marker with the `updateMarker` function.</span></span>

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. <span data-ttu-id="5531f-231">最後に、イベント ハンドラーを登録し、`id=Message` 属性を使ってそれを `textarea`要素にバインドします。</span><span class="sxs-lookup"><span data-stu-id="5531f-231">Finally, register the event handler and bind it to the `textarea` element with the `id=Message` attribute.</span></span>

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a><span data-ttu-id="5531f-232">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="5531f-232">Run the application</span></span>

<span data-ttu-id="5531f-233">アプリケーションがセットアップされたので、アプリケーションを実行します。アプリケーションはブラウザー内で起動します。</span><span class="sxs-lookup"><span data-stu-id="5531f-233">Now that your application is set up, run the application which should launch in your browser.</span></span>

<span data-ttu-id="5531f-234">アプリケーションが起動したら、テキスト領域に「*Model Builder is cool!* 」</span><span class="sxs-lookup"><span data-stu-id="5531f-234">When the application launches, enter *Model Builder is cool!*</span></span> <span data-ttu-id="5531f-235">と入力します。</span><span class="sxs-lookup"><span data-stu-id="5531f-235">into the text area.</span></span> <span data-ttu-id="5531f-236">表示される予測済みセンチメントは、「*無害*」になります。</span><span class="sxs-lookup"><span data-stu-id="5531f-236">The predicted sentiment displayed should be *Not Toxic*.</span></span>

![予測済みセンチメント ウィンドウの実行中ウィンドウ](./media/sentiment-analysis-model-builder/web-app.png)

<span data-ttu-id="5531f-238">別のソリューション内で後でモデル ビルダーによって生成されたプロジェクトを参照する必要がある場合、それらは、`C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` ディレクトリ内にあります。</span><span class="sxs-lookup"><span data-stu-id="5531f-238">If you need to reference the Model Builder generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5531f-239">次の手順</span><span class="sxs-lookup"><span data-stu-id="5531f-239">Next steps</span></span>

<span data-ttu-id="5531f-240">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="5531f-240">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="5531f-241">ASP.NET Core Razor Pages アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="5531f-241">Create an ASP.NET Core Razor Pages application</span></span>
> - <span data-ttu-id="5531f-242">データを準備して理解する</span><span class="sxs-lookup"><span data-stu-id="5531f-242">Prepare and understand the data</span></span>
> - <span data-ttu-id="5531f-243">シナリオを選択する</span><span class="sxs-lookup"><span data-stu-id="5531f-243">Choose a scenario</span></span>
> - <span data-ttu-id="5531f-244">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="5531f-244">Load the data</span></span>
> - <span data-ttu-id="5531f-245">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="5531f-245">Train the model</span></span>
> - <span data-ttu-id="5531f-246">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="5531f-246">Evaluate the model</span></span>
> - <span data-ttu-id="5531f-247">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="5531f-247">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5531f-248">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="5531f-248">Additional Resources</span></span>

<span data-ttu-id="5531f-249">このチュートリアルで説明しているトピックについて詳しくは、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5531f-249">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="5531f-250">モデル ビルダーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="5531f-250">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="5531f-251">二項分類</span><span class="sxs-lookup"><span data-stu-id="5531f-251">Binary Classification</span></span>](../resources/glossary.md#binary-classification)
- [<span data-ttu-id="5531f-252">二項分類モデル メトリック</span><span class="sxs-lookup"><span data-stu-id="5531f-252">Binary Classification Model Metrics</span></span>](../resources/metrics.md#metrics-for-binary-classification)
