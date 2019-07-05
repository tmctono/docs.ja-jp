---
title: モデル ビルダーの概要としくみ
description: ML.NET モデル ビルダーを使用し、機械学習モデルを自動的にトレーニングする方法
author: natke
ms.date: 06/26/2019
ms.custom: overview
ms.openlocfilehash: 6f5bbe3c389e3ca42550a48ef3e6edbc963ac2e9
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410590"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="3e052-103">モデル ビルダーの概要としくみ</span><span class="sxs-lookup"><span data-stu-id="3e052-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="3e052-104">ML.NET モデル ビルダーはわかりやすいグラフィックスでカスタムの機械学習モデルを構築、トレーニング、展開できる Visual Studio 拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="3e052-104">ML.NET Model Builder is an easy-to-understand graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span> 

<span data-ttu-id="3e052-105">モデル ビルダーでは自動化された機械学習 (AutoML) を利用してさまざまな機械学習のアルゴリズムや設定を見つけます。自分のシナリオに最適なものを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3e052-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="3e052-106">モデル ビルダーは機械学習の専門知識がなくても使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="3e052-107">必要なものはいくつかのデータと解決すべき問題です。</span><span class="sxs-lookup"><span data-stu-id="3e052-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="3e052-108">モデル ビルダーでは、.NET アプリケーションにモデルを追加するコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e052-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![モデル ビルダー Visual Studio 拡張機能のユーザー インターフェイスのアニメーション](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="3e052-110">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="3e052-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="3e052-111">シナリオ</span><span class="sxs-lookup"><span data-stu-id="3e052-111">Scenarios</span></span>

<span data-ttu-id="3e052-112">さまざまなシナリオをモデル ビルダーに取り込み、自分のアプリケーションのための機械学習モデルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="3e052-113">シナリオは、データで行う予測の種類を説明するものです。</span><span class="sxs-lookup"><span data-stu-id="3e052-113">A scenario is a description of the type of prediction you want to make on your data.</span></span> <span data-ttu-id="3e052-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3e052-114">For example:</span></span>
- <span data-ttu-id="3e052-115">過去の販売データに基づいて今後の製品売上高を予測する</span><span class="sxs-lookup"><span data-stu-id="3e052-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="3e052-116">顧客のレビューに基づいてセンチメントを肯定的と否定的に分類する</span><span class="sxs-lookup"><span data-stu-id="3e052-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="3e052-117">銀行取引が詐欺かどうかを検出する</span><span class="sxs-lookup"><span data-stu-id="3e052-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="3e052-118">顧客がフィードバックした問題を社内の該当チームに送信する</span><span class="sxs-lookup"><span data-stu-id="3e052-118">route customer feedback issues to the correct team in your company</span></span>

<span data-ttu-id="3e052-119">モデル ビルダーでは、シナリオを [ML.NET タスク](resources/tasks.md)にマッピングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e052-119">In Model Builder, you need to map your scenario onto an [ML.NET task](resources/tasks.md).</span></span> <span data-ttu-id="3e052-120">モデル ビルダーは**回帰** (数値の予測) と**分類** (カテゴリの予測) に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-120">You can use Model Builder for **regression** (predicting numbers) and **classification** (predicting categories).</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="3e052-121">自分に最適な機械学習シナリオとは?</span><span class="sxs-lookup"><span data-stu-id="3e052-121">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="3e052-122">モデル ビルダーには、センチメント分析、問題分類、価格予測、カスタム シナリオ向けのテンプレートが付属しています。</span><span class="sxs-lookup"><span data-stu-id="3e052-122">Model Builder comes with templates for sentiment analysis, issue classification, price prediction, and custom scenarios.</span></span> <span data-ttu-id="3e052-123">このようなテンプレートは、特定の ML.NET シナリオを始める際に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-123">These templates can be used as a starting point for your specific ML.NET scenario.</span></span>

#### <a name="sentiment-analysis-binary-classification"></a><span data-ttu-id="3e052-124">センチメント分析 (二項分類)</span><span class="sxs-lookup"><span data-stu-id="3e052-124">Sentiment analysis (binary classification)</span></span>

<span data-ttu-id="3e052-125">センチメント分析は、顧客からのフィードバックの肯定性/否定性を予測する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-125">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="3e052-126">これは二項分類タスクの一例です。</span><span class="sxs-lookup"><span data-stu-id="3e052-126">It is an example of the binary classification task.</span></span>

<span data-ttu-id="3e052-127">二項分類は、データを 2 つのクラス (はい/いいえ、合格/不合格、真/偽、肯定的/否定的) に分類する目的で利用されます。</span><span class="sxs-lookup"><span data-stu-id="3e052-127">Binary classification is used to categorize data into two classes (yes/no; pass/fail; true/false; positive/negative).</span></span> <span data-ttu-id="3e052-128">次のような質問に答える目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-128">It can be used to answer questions such as:</span></span>

- <span data-ttu-id="3e052-129">この電子メールはスパムですか?</span><span class="sxs-lookup"><span data-stu-id="3e052-129">Is this email spam?</span></span> <span data-ttu-id="3e052-130">(迷惑メールの検出)</span><span class="sxs-lookup"><span data-stu-id="3e052-130">(spam detection)</span></span>
- <span data-ttu-id="3e052-131">会員になる資格があるのはどちらの応募者ですか?</span><span class="sxs-lookup"><span data-stu-id="3e052-131">Which applicants may be eligible for membership?</span></span> <span data-ttu-id="3e052-132">(申請の選別)</span><span class="sxs-lookup"><span data-stu-id="3e052-132">(application screening)</span></span>
- <span data-ttu-id="3e052-133">請求書が期日どおりに支払われない可能性があるのはどちらのアカウントですか?</span><span class="sxs-lookup"><span data-stu-id="3e052-133">Which accounts may not pay their invoices on time?</span></span> <span data-ttu-id="3e052-134">(リスクの軽減)</span><span class="sxs-lookup"><span data-stu-id="3e052-134">(risk mitigation)</span></span>
- <span data-ttu-id="3e052-135">このクレジット カード取引は詐欺ですか?</span><span class="sxs-lookup"><span data-stu-id="3e052-135">Is this credit card transaction fraudulent?</span></span> <span data-ttu-id="3e052-136">(詐欺の検出)</span><span class="sxs-lookup"><span data-stu-id="3e052-136">(fraud detection)</span></span>

<span data-ttu-id="3e052-137">2 つのカテゴリに分類することが自分のシナリオで求められる場合、独自のデータセットと共にこのテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-137">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>
 
#### <a name="issue-classification-multiclass-classification"></a><span data-ttu-id="3e052-138">問題の分類 (多クラス分類)</span><span class="sxs-lookup"><span data-stu-id="3e052-138">Issue classification (multiclass classification)</span></span>

<span data-ttu-id="3e052-139">問題分類は、顧客からのフィードバック (たとえば、GitHub で) に含まれる問題を問題のタイトルや説明で分類する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-139">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="3e052-140">これは多クラス分類タスクの一例です。</span><span class="sxs-lookup"><span data-stu-id="3e052-140">It is an example of the multi-class classification task.</span></span>

<span data-ttu-id="3e052-141">多クラス分類は、データを 3 つ以上のクラスに分類する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-141">Multiclass classification can be used to categorize data into three or more classes.</span></span> <span data-ttu-id="3e052-142">次のような質問に答える目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-142">It can be used to answer questions such as:</span></span>

- <span data-ttu-id="3e052-143">サポート チケットはどの部門に送信しますか?</span><span class="sxs-lookup"><span data-stu-id="3e052-143">To which department should I route a support ticket?</span></span> <span data-ttu-id="3e052-144">(サポート チケットの送信)</span><span class="sxs-lookup"><span data-stu-id="3e052-144">(support ticket routing)</span></span>
- <span data-ttu-id="3e052-145">顧客問題の優先度とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="3e052-145">What is the priority of a customer issue?</span></span> <span data-ttu-id="3e052-146">(顧客問題の優先順位)</span><span class="sxs-lookup"><span data-stu-id="3e052-146">(customer issue prioritization)</span></span>
- <span data-ttu-id="3e052-147">製品はどのカテゴリに属していますか?</span><span class="sxs-lookup"><span data-stu-id="3e052-147">What category does a product belong to?</span></span> <span data-ttu-id="3e052-148">(製品分類)</span><span class="sxs-lookup"><span data-stu-id="3e052-148">(product classification)</span></span>
- <span data-ttu-id="3e052-149">ドキュメントの種類は何ですか?</span><span class="sxs-lookup"><span data-stu-id="3e052-149">What type of document?</span></span> <span data-ttu-id="3e052-150">(ドキュメント/電子メールの分類)</span><span class="sxs-lookup"><span data-stu-id="3e052-150">(document/email classification)</span></span>

<span data-ttu-id="3e052-151">データを 3 つ以上のカテゴリに分類する場合、シナリオに問題分類テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-151">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="price-prediction-regression"></a><span data-ttu-id="3e052-152">料金の予測 (回帰)</span><span class="sxs-lookup"><span data-stu-id="3e052-152">Price prediction (regression)</span></span>

<span data-ttu-id="3e052-153">価格予測は、家の場所、規模、その他の特徴を利用し、家の価格を予測する目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-153">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="3e052-154">これは回帰タスクの一例です。</span><span class="sxs-lookup"><span data-stu-id="3e052-154">It is an example of the regression task.</span></span>

<span data-ttu-id="3e052-155">回帰は、数値を予測する目的で利用されます。</span><span class="sxs-lookup"><span data-stu-id="3e052-155">Regression is used to predict numbers.</span></span> <span data-ttu-id="3e052-156">次のような質問に答える目的で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-156">It can be used to answer questions such as:</span></span>

- <span data-ttu-id="3e052-157">家はいくらで売られていますか?</span><span class="sxs-lookup"><span data-stu-id="3e052-157">What price will a house sell for?</span></span> <span data-ttu-id="3e052-158">(価格の予測)</span><span class="sxs-lookup"><span data-stu-id="3e052-158">(price prediction)</span></span>
- <span data-ttu-id="3e052-159">どのくらいの時間が経過すれば、機械部品に保守整備が必要になりますか?</span><span class="sxs-lookup"><span data-stu-id="3e052-159">After how much time will a mechanical part require maintenance?</span></span> <span data-ttu-id="3e052-160">(予測的なメンテナンス)</span><span class="sxs-lookup"><span data-stu-id="3e052-160">(predictive maintenance)</span></span>
- <span data-ttu-id="3e052-161">この乾燥機の水分率は何ですか?</span><span class="sxs-lookup"><span data-stu-id="3e052-161">What is the moisture content in this dryer?</span></span> <span data-ttu-id="3e052-162">(機械監視)</span><span class="sxs-lookup"><span data-stu-id="3e052-162">(machine monitoring)</span></span>
- <span data-ttu-id="3e052-163">この地域の年間売上合計はどのくらいになりますか?</span><span class="sxs-lookup"><span data-stu-id="3e052-163">What will the total annual sales for this region be?</span></span> <span data-ttu-id="3e052-164">(売上予測)</span><span class="sxs-lookup"><span data-stu-id="3e052-164">(sales forecasting)</span></span>

<span data-ttu-id="3e052-165">独自のデータセットで数値を予測する場合、自分のシナリオに価格予測テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-165">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-task"></a><span data-ttu-id="3e052-166">カスタム シナリオ (タスクを選択します)</span><span class="sxs-lookup"><span data-stu-id="3e052-166">Custom scenario (choose your task)</span></span>

<span data-ttu-id="3e052-167">カスタム シナリオでは、独自のタスクを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-167">The custom scenario allows you to choose your own task.</span></span> <span data-ttu-id="3e052-168">問題に最適なシナリオを選択してください。</span><span class="sxs-lookup"><span data-stu-id="3e052-168">Pick the scenario that makes the most sense for your problem.</span></span>

<span data-ttu-id="3e052-169">カスタム シナリオでは、独自の機械学習タスクを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-169">The custom scenario allows you to choose your own machine learning task.</span></span> <span data-ttu-id="3e052-170">前のテンプレートでは、機械学習タスクがシナリオ (二項分類、多クラス分類、回帰) に固定されていました。</span><span class="sxs-lookup"><span data-stu-id="3e052-170">In the previous templates, the machine learning task was fixed to the scenario: binary classification, multi-class classification, or regression.</span></span> <span data-ttu-id="3e052-171">このテンプレートでは、自分のデータで使用する ML タスクを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-171">In this template, you can choose the ML task you want to use on your data.</span></span>

## <a name="data"></a><span data-ttu-id="3e052-172">データ</span><span class="sxs-lookup"><span data-stu-id="3e052-172">Data</span></span>

<span data-ttu-id="3e052-173">シナリオをタスクにマップすると、モデル ビルダーからデータセットを提供するように求められます。</span><span class="sxs-lookup"><span data-stu-id="3e052-173">Once you have mapped your scenario onto a task, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="3e052-174">このデータはモデルをトレーニングし、評価し、シナリオに最適なモデルを選択するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e052-174">The data is used to train, evaluate, and choose the best model for your scenario.</span></span> <span data-ttu-id="3e052-175">また、予測する出力を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e052-175">You also need to choose the output you want to predict.</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="3e052-176">予測する出力を選択します (ラベル)</span><span class="sxs-lookup"><span data-stu-id="3e052-176">Choose the output to predict (label)</span></span>

<span data-ttu-id="3e052-177">データセットは、トレーニング サンプルの行と属性の列からなるテーブルです。</span><span class="sxs-lookup"><span data-stu-id="3e052-177">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="3e052-178">各行の内容:</span><span class="sxs-lookup"><span data-stu-id="3e052-178">Each row has:</span></span>
- <span data-ttu-id="3e052-179">**ラベル** (予測する属性)</span><span class="sxs-lookup"><span data-stu-id="3e052-179">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="3e052-180">**特徴** (ラベルを予測するための入力として使用される属性)。</span><span class="sxs-lookup"><span data-stu-id="3e052-180">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="3e052-181">家の価格予測シナリオの場合、特徴は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3e052-181">For the house-price prediction scenario, the features could be:</span></span>
- <span data-ttu-id="3e052-182">家の面積</span><span class="sxs-lookup"><span data-stu-id="3e052-182">the square footage of the house</span></span>
- <span data-ttu-id="3e052-183">寝室と浴室の数</span><span class="sxs-lookup"><span data-stu-id="3e052-183">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="3e052-184">郵便番号</span><span class="sxs-lookup"><span data-stu-id="3e052-184">the zip code</span></span>

<span data-ttu-id="3e052-185">ラベルは、面積、寝室数、浴室数、郵便番号からなるその行の過去の住宅価格です。</span><span class="sxs-lookup"><span data-stu-id="3e052-185">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![サイズ、部屋数、郵便番号、価格ラベルから構成される特徴を持つ住宅価格データからなる行と列を示す表](media/model-builder-data.png)

### <a name="data-formats"></a><span data-ttu-id="3e052-187">データ形式</span><span class="sxs-lookup"><span data-stu-id="3e052-187">Data formats</span></span>

<span data-ttu-id="3e052-188">モデル ビルダーでは、データに次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="3e052-188">Model Builder places the following limitations on the data:</span></span>

- <span data-ttu-id="3e052-189">データはファイル (ヘッダー行のある .csv または .tsv) または SQL Server データベースに格納する必要があります</span><span class="sxs-lookup"><span data-stu-id="3e052-189">Data must be stored in a file (.csv or .tsv with a header row), or in a SQL server database.</span></span>
- <span data-ttu-id="3e052-190">トレーニング データセットには 1 GB までの制限があります</span><span class="sxs-lookup"><span data-stu-id="3e052-190">A limit of 1 GB on the training dataset</span></span>
- <span data-ttu-id="3e052-191">SQL Server のトレーニング用の行は 10 万行までの制限があります。</span><span class="sxs-lookup"><span data-stu-id="3e052-191">SQL server has a limit of 100,000 rows for training</span></span>
- <span data-ttu-id="3e052-192">SQL Server からのデータは、トレーニング前に、サーバーからローカル コンピューターにコピーされます</span><span class="sxs-lookup"><span data-stu-id="3e052-192">Data from SQL server is copied from the server to your local machine before training</span></span>

### <a name="example-datasets"></a><span data-ttu-id="3e052-193">データセットの例</span><span class="sxs-lookup"><span data-stu-id="3e052-193">Example datasets</span></span>

<span data-ttu-id="3e052-194">独自のデータをまだ用意していない場合、次のいずれかのデータセットをお試しください。</span><span class="sxs-lookup"><span data-stu-id="3e052-194">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="3e052-195">シナリオ</span><span class="sxs-lookup"><span data-stu-id="3e052-195">Scenario</span></span>|<span data-ttu-id="3e052-196">ML タスク</span><span class="sxs-lookup"><span data-stu-id="3e052-196">ML Task</span></span>|<span data-ttu-id="3e052-197">データ</span><span class="sxs-lookup"><span data-stu-id="3e052-197">Data</span></span>|<span data-ttu-id="3e052-198">group1</span><span class="sxs-lookup"><span data-stu-id="3e052-198">Label</span></span>|<span data-ttu-id="3e052-199">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="3e052-199">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="3e052-200">価格の予測</span><span class="sxs-lookup"><span data-stu-id="3e052-200">Price prediction</span></span>|<span data-ttu-id="3e052-201">回帰</span><span class="sxs-lookup"><span data-stu-id="3e052-201">regression</span></span>|[<span data-ttu-id="3e052-202">タクシーの料金データ</span><span class="sxs-lookup"><span data-stu-id="3e052-202">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="3e052-203">料金</span><span class="sxs-lookup"><span data-stu-id="3e052-203">Fare</span></span>|<span data-ttu-id="3e052-204">乗車時間、距離</span><span class="sxs-lookup"><span data-stu-id="3e052-204">Trip time, distance</span></span>|
|<span data-ttu-id="3e052-205">異常検出</span><span class="sxs-lookup"><span data-stu-id="3e052-205">Anomaly detection</span></span>|<span data-ttu-id="3e052-206">二項分類</span><span class="sxs-lookup"><span data-stu-id="3e052-206">binary classification</span></span>|[<span data-ttu-id="3e052-207">製品の売上データ</span><span class="sxs-lookup"><span data-stu-id="3e052-207">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="3e052-208">製品の売上</span><span class="sxs-lookup"><span data-stu-id="3e052-208">Product Sales</span></span>|<span data-ttu-id="3e052-209">月</span><span class="sxs-lookup"><span data-stu-id="3e052-209">Month</span></span>|
|<span data-ttu-id="3e052-210">センチメント分析</span><span class="sxs-lookup"><span data-stu-id="3e052-210">Sentiment analysis</span></span>|<span data-ttu-id="3e052-211">二項分類</span><span class="sxs-lookup"><span data-stu-id="3e052-211">binary classification</span></span>|[<span data-ttu-id="3e052-212">Web サイトのコメント データ</span><span class="sxs-lookup"><span data-stu-id="3e052-212">website comment data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_SentimentAnalysis/SentimentAnalysis/Data/wikiDetoxAnnotated40kRows.tsv)|<span data-ttu-id="3e052-213">ラベル (否定的なセンチメントのときは 0、肯定的なセンチメントのときは 1)</span><span class="sxs-lookup"><span data-stu-id="3e052-213">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="3e052-214">コメント、年度</span><span class="sxs-lookup"><span data-stu-id="3e052-214">Comment, Year</span></span>|
|<span data-ttu-id="3e052-215">不正行為の検出</span><span class="sxs-lookup"><span data-stu-id="3e052-215">Fraud detection</span></span>|<span data-ttu-id="3e052-216">二項分類</span><span class="sxs-lookup"><span data-stu-id="3e052-216">binary classification</span></span>|[<span data-ttu-id="3e052-217">クレジット カードのデータ</span><span class="sxs-lookup"><span data-stu-id="3e052-217">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="3e052-218">クラス (詐欺の場合は 1、それ以外の場合 0)</span><span class="sxs-lookup"><span data-stu-id="3e052-218">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="3e052-219">金額、V1-V28 (匿名化された特徴)</span><span class="sxs-lookup"><span data-stu-id="3e052-219">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="3e052-220">テキスト分類</span><span class="sxs-lookup"><span data-stu-id="3e052-220">Text classification</span></span>|<span data-ttu-id="3e052-221">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="3e052-221">multiclass classification</span></span>|[<span data-ttu-id="3e052-222">GitHub 問題のデータ</span><span class="sxs-lookup"><span data-stu-id="3e052-222">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="3e052-223">区分</span><span class="sxs-lookup"><span data-stu-id="3e052-223">Area</span></span>|<span data-ttu-id="3e052-224">タイトル、説明</span><span class="sxs-lookup"><span data-stu-id="3e052-224">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="3e052-225">トレーニング</span><span class="sxs-lookup"><span data-stu-id="3e052-225">Train</span></span>

<span data-ttu-id="3e052-226">シナリオ、データ、ラベルを選択すると、モデル ビルダーによってモデルがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="3e052-226">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="3e052-227">トレーニングとは何か?</span><span class="sxs-lookup"><span data-stu-id="3e052-227">What is training?</span></span>

<span data-ttu-id="3e052-228">トレーニングとは、モデル ビルダーがシナリオの質問に対する回答方法をモデルに教える自動プロセスです。</span><span class="sxs-lookup"><span data-stu-id="3e052-228">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="3e052-229">トレーニングが終わると、モデルは以前に見たことがない入力データで予測できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-229">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="3e052-230">たとえば、住宅価格を予測しているなら、新しい住宅が市場に出たとき、その販売価格を予測できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-230">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="3e052-231">モデル ビルダーで使用される機械学習は自動化されているため (AutoML)、トレーニング中に、ユーザーが入力したり、調整したりする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="3e052-231">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="3e052-232">どのくらいの時間、トレーニングしますか?</span><span class="sxs-lookup"><span data-stu-id="3e052-232">How long should I train for?</span></span>

<span data-ttu-id="3e052-233">トレーニング時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-233">You can provide a training time.</span></span> <span data-ttu-id="3e052-234">一般的に、トレーニング時間が長ければ、それだけモデルの精度が上がります。</span><span class="sxs-lookup"><span data-stu-id="3e052-234">In general, training for a longer time produces a more accurate model.</span></span> <span data-ttu-id="3e052-235">また、トレーニング データセットの規模が増えると、それだけ多くのトレーニング時間が必要になります。</span><span class="sxs-lookup"><span data-stu-id="3e052-235">More training time is also required as the size of the training dataset increases.</span></span> <span data-ttu-id="3e052-236">次の表には、データセットの規模を増やしたときのトレーニング時間の目安をまとめています。</span><span class="sxs-lookup"><span data-stu-id="3e052-236">The following table gives some training time guidelines for datasets of increasing size.</span></span>

<span data-ttu-id="3e052-237">データセットのサイズ</span><span class="sxs-lookup"><span data-stu-id="3e052-237">Dataset Size</span></span>  | <span data-ttu-id="3e052-238">データセットの種類</span><span class="sxs-lookup"><span data-stu-id="3e052-238">Dataset Type</span></span>       | <span data-ttu-id="3e052-239">Avg.トレーニング時間</span><span class="sxs-lookup"><span data-stu-id="3e052-239">Avg. Time to train</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="3e052-240">0 - 10 Mb</span><span class="sxs-lookup"><span data-stu-id="3e052-240">0 - 10 Mb</span></span>     | <span data-ttu-id="3e052-241">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="3e052-241">Numeric and Text</span></span>   | <span data-ttu-id="3e052-242">10 秒</span><span class="sxs-lookup"><span data-stu-id="3e052-242">10 sec</span></span>
<span data-ttu-id="3e052-243">10 - 100 Mb</span><span class="sxs-lookup"><span data-stu-id="3e052-243">10 - 100 Mb</span></span>   | <span data-ttu-id="3e052-244">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="3e052-244">Numeric and Text</span></span>   | <span data-ttu-id="3e052-245">10 分</span><span class="sxs-lookup"><span data-stu-id="3e052-245">10 min</span></span> 
<span data-ttu-id="3e052-246">100 - 500 Mb</span><span class="sxs-lookup"><span data-stu-id="3e052-246">100 - 500 Mb</span></span>  | <span data-ttu-id="3e052-247">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="3e052-247">Numeric and Text</span></span>   | <span data-ttu-id="3e052-248">30 分</span><span class="sxs-lookup"><span data-stu-id="3e052-248">30 min</span></span> 
<span data-ttu-id="3e052-249">500 - 1 Gb</span><span class="sxs-lookup"><span data-stu-id="3e052-249">500 - 1 Gb</span></span>    | <span data-ttu-id="3e052-250">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="3e052-250">Numeric and Text</span></span>   | <span data-ttu-id="3e052-251">60 分</span><span class="sxs-lookup"><span data-stu-id="3e052-251">60 min</span></span> 
<span data-ttu-id="3e052-252">1 Gb 超</span><span class="sxs-lookup"><span data-stu-id="3e052-252">1 Gb+</span></span>         | <span data-ttu-id="3e052-253">数値とテキスト</span><span class="sxs-lookup"><span data-stu-id="3e052-253">Numeric and Text</span></span>   | <span data-ttu-id="3e052-254">3 時間超</span><span class="sxs-lookup"><span data-stu-id="3e052-254">3 hour+</span></span> 

<span data-ttu-id="3e052-255">正確なトレーニング時間は次にも左右されます。</span><span class="sxs-lookup"><span data-stu-id="3e052-255">The exact time to train also depends on:</span></span>

- <span data-ttu-id="3e052-256">列の種類 (テキストまたは数値)</span><span class="sxs-lookup"><span data-stu-id="3e052-256">the type of columns that is, text vs numeric</span></span>
- <span data-ttu-id="3e052-257">機械学習タスクの種類 (回帰または分類)</span><span class="sxs-lookup"><span data-stu-id="3e052-257">the type of machine learning task (regression or classification)</span></span>
- <span data-ttu-id="3e052-258">トレーニングに使用される行の数</span><span class="sxs-lookup"><span data-stu-id="3e052-258">the number of rows used for training</span></span>
- <span data-ttu-id="3e052-259">トレーニングに使用される列の数</span><span class="sxs-lookup"><span data-stu-id="3e052-259">the number of feature columns used for training</span></span>

<span data-ttu-id="3e052-260">モデル ビルダーは 1-TB データセットの規模で試験済みですが、その規模のデータセットで高品質のモデルを作るとなると最大で 4 日かかります。</span><span class="sxs-lookup"><span data-stu-id="3e052-260">Model Builder has been tested for scale with a 1-TB dataset, but building a high-quality model for that size of dataset can take up to four days!</span></span>

## <a name="evaluate"></a><span data-ttu-id="3e052-261">評価</span><span class="sxs-lookup"><span data-stu-id="3e052-261">Evaluate</span></span>

<span data-ttu-id="3e052-262">評価は、トレーニングしたモデルを使用し、新しいテスト データで予測し、予測の精度を測定するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="3e052-262">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="3e052-263">モデル ビルダーでは、トレーニング セットとテスト セットにトレーニング データが分割されます。</span><span class="sxs-lookup"><span data-stu-id="3e052-263">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="3e052-264">トレーニング データ (80%) はモデルのトレーニングに使用されます。テスト データ (20%) はモデルの評価のための控えとなります。</span><span class="sxs-lookup"><span data-stu-id="3e052-264">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span>  <span data-ttu-id="3e052-265">評価のために使用されるメトリックは、ML タスクによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3e052-265">The metrics used for evaluation depend on the ML task.</span></span> <span data-ttu-id="3e052-266">詳しくは、[モデルの評価メトリック](resources/metrics.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e052-266">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>  

### <a name="sentiment-analysis-binary-classification"></a><span data-ttu-id="3e052-267">センチメント分析 (二項分類)</span><span class="sxs-lookup"><span data-stu-id="3e052-267">Sentiment analysis (binary classification)</span></span>

<span data-ttu-id="3e052-268">二項分類問題の既定のメトリックは**正解率**です。</span><span class="sxs-lookup"><span data-stu-id="3e052-268">The default metric for binary classification problems is **accuracy**.</span></span> <span data-ttu-id="3e052-269">正解率は、テスト データセットに基づいてモデルが正しく予測する比率を定めるものです。</span><span class="sxs-lookup"><span data-stu-id="3e052-269">Accuracy defines the proportion of correct predictions your model makes over the test dataset.</span></span> <span data-ttu-id="3e052-270">**100% に近ければ、近いほど良い**ということになります。</span><span class="sxs-lookup"><span data-stu-id="3e052-270">The **closer to 100%, the better it is**.</span></span>

<span data-ttu-id="3e052-271">真陽率と偽陽率を測定する AUC (曲線下面積) など、報告されるその他のメトリックは 0.50 以上であれば、モデルは許容されます。</span><span class="sxs-lookup"><span data-stu-id="3e052-271">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate, should be greater than 0.50 for models to be acceptable.</span></span> 

<span data-ttu-id="3e052-272">F1 スコアなど、追加のメトリックは、適合率 (正しい予測とそのクラスの予測合計の比率) と再現率 (正しい予測とそのクラスの実際のメンバー合計の比率) のバランスを調整する目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-272">Additional metrics such as F1 score can be used to control the balance between precision (ratio of correct predictions to the total predictions of that class) and recall (proportion of correct predictions to the total actual members of that class).</span></span>

### <a name="issue-classification-multiclass-classification"></a><span data-ttu-id="3e052-273">問題の分類 (多クラス分類)</span><span class="sxs-lookup"><span data-stu-id="3e052-273">Issue classification (multiclass classification)</span></span>

<span data-ttu-id="3e052-274">多クラス分類問題の既定のメトリックは**マイクロ正解率**です。</span><span class="sxs-lookup"><span data-stu-id="3e052-274">The default metric for multiclass classification problems is **micro accuracy**.</span></span> <span data-ttu-id="3e052-275">**100% に近ければ、近いほど良い**ということになります。</span><span class="sxs-lookup"><span data-stu-id="3e052-275">The **closer to 100%, the better it is**.</span></span>

<span data-ttu-id="3e052-276">データが多クラスに分類される問題の場合、正解率には 2 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="3e052-276">For problems where data is categorized into multiple classes there are two types of accuracy:</span></span>

- <span data-ttu-id="3e052-277">マイクロ正解率: 予測のうち、インスタンス全体で正しくなる部分。</span><span class="sxs-lookup"><span data-stu-id="3e052-277">Micro-accuracy: the fraction of predictions that are correct across all instances.</span></span> <span data-ttu-id="3e052-278">問題分類シナリオでは、マイクロ正解率は、入ってきた問題のうち、正しいカテゴリに割り当てられた問題の比率となります。</span><span class="sxs-lookup"><span data-stu-id="3e052-278">In the issue classification scenario, micro-accuracy is the proportion of incoming issues that get assigned to the correct category.</span></span> 
- <span data-ttu-id="3e052-279">マクロ正解率: クラス レベルでの平均正解率。</span><span class="sxs-lookup"><span data-stu-id="3e052-279">Macro-accuracy: the average accuracy at the class level.</span></span> <span data-ttu-id="3e052-280">問題分類シナリオでは、正解率はカテゴリごとに測定され、測定後、カテゴリ正解率の平均が求められます。</span><span class="sxs-lookup"><span data-stu-id="3e052-280">In the issue classification scenario, the accuracy is measured for each category, and then the category accuracies are averaged.</span></span> <span data-ttu-id="3e052-281">このメトリックの場合、すべてのクラスに等しい重みが与えられます。</span><span class="sxs-lookup"><span data-stu-id="3e052-281">For this metric, all classes are given equal weight.</span></span> <span data-ttu-id="3e052-282">完全にバランスの取れたデータセットの場合 (各カテゴリに等しい数の例がある)、マイクロ正解率とマクロ正解率は同じになります。</span><span class="sxs-lookup"><span data-stu-id="3e052-282">For perfectly balanced datasets (where there are an equal number of examples of each category), micro-accuracy and macro-accuracy are the same.</span></span>


### <a name="price-prediction-regression"></a><span data-ttu-id="3e052-283">料金の予測 (回帰)</span><span class="sxs-lookup"><span data-stu-id="3e052-283">Price prediction (regression)</span></span>

<span data-ttu-id="3e052-284">回帰問題の既定のメトリックは **RSquared** です。</span><span class="sxs-lookup"><span data-stu-id="3e052-284">The default metric for regression problems is **RSquared**.</span></span> <span data-ttu-id="3e052-285">1 は考えられる最適値です。</span><span class="sxs-lookup"><span data-stu-id="3e052-285">1 is the best possible value.</span></span> <span data-ttu-id="3e052-286">RSquared が 1 に近づくほど優れたモデルになります。</span><span class="sxs-lookup"><span data-stu-id="3e052-286">The closer RSquared is to 1, the better your model is.</span></span>

<span data-ttu-id="3e052-287">絶対損失、二乗損失、RMS 損失など、報告されるその他のメトリックは、モデルを理解し、それを他の回帰モデルと比較する目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-287">Other metrics reported, such as absolute-loss, squared-loss, and RMS loss can be used to understand your model, and compare it with other regression models.</span></span> 

## <a name="improve"></a><span data-ttu-id="3e052-288">改善</span><span class="sxs-lookup"><span data-stu-id="3e052-288">Improve</span></span>

<span data-ttu-id="3e052-289">モデルのパフォーマンス スコアが予想ほど良くない場合、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="3e052-289">If your model performance score is not as good as you want it to be, you can:</span></span>

* <span data-ttu-id="3e052-290">トレーニングの時間を長くします。</span><span class="sxs-lookup"><span data-stu-id="3e052-290">Train for a longer period of time.</span></span> <span data-ttu-id="3e052-291">時間を増やせば、自動化された機械学習エンジンは試行するアルゴリズムや設定をそれだけ増やします。</span><span class="sxs-lookup"><span data-stu-id="3e052-291">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

* <span data-ttu-id="3e052-292">データを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e052-292">Add more data.</span></span> <span data-ttu-id="3e052-293">高品質の機械学習モデルをトレーニングするにはデータ量が十分ではないことがあります。</span><span class="sxs-lookup"><span data-stu-id="3e052-293">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span> 

* <span data-ttu-id="3e052-294">データのバランスを調整します。</span><span class="sxs-lookup"><span data-stu-id="3e052-294">Balance your data.</span></span> <span data-ttu-id="3e052-295">分類タスクの場合、カテゴリ全体でトレーニング セットのバランスが取れていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e052-295">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="3e052-296">たとえば、100 のトレーニング例に対してクラスが 4 つあるとき、90 個のレコードに最初の 2 つのクラス (tag1 と tag2) を使用するが、残りの 2 つ (tag3 と tag4) は残りの 10 個のレコードでのみ使用する場合、データにバランスが欠け、tag3 か tag4 を正しく予測することがモデルにとって難しくなります。</span><span class="sxs-lookup"><span data-stu-id="3e052-296">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="3e052-297">コード</span><span class="sxs-lookup"><span data-stu-id="3e052-297">Code</span></span>

<span data-ttu-id="3e052-298">評価フェーズ後、モデル ビルダーからモデル ファイルとコードが出力されます。このコードを使用し、モデルをアプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-298">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="3e052-299">ML.NET モデルは zip ファイルで保存されます。</span><span class="sxs-lookup"><span data-stu-id="3e052-299">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="3e052-300">モデルを読み込み、使用するためのコードがソリューションに新しいプロジェクトとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e052-300">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="3e052-301">モデル ビルダーからはサンプル コンソール アプリも追加されます。これを実行すると、実際に動作するモデルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-301">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="3e052-302">さらに、モデル ビルダーからはモデルを生成したコードが出力されます。モデルの生成に使用された手順を理解できます。</span><span class="sxs-lookup"><span data-stu-id="3e052-302">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="3e052-303">モデル トレーニング コードを使用し、モデルを新しいデータで再トレーニングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3e052-303">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="3e052-304">次の内容</span><span class="sxs-lookup"><span data-stu-id="3e052-304">What's next?</span></span>

<span data-ttu-id="3e052-305">[価格予測または回帰のシナリオ](tutorials/predict-prices-with-model-builder.md)をお試しください。</span><span class="sxs-lookup"><span data-stu-id="3e052-305">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>
