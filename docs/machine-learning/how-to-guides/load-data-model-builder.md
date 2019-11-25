---
title: モデル ビルダーのトレーニング データの読み込み
description: ML.NET 用のモデル ビルダー シナリオのいずれかで使用するために、SQL Server データベースまたはファイルからトレーニング データを読み込む方法について説明します。
ms.date: 10/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: cc93b3f77284ed283a8d7cbd52b8cd02b4fd9066
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977052"
---
# <a name="load-training-data-into-model-builder"></a><span data-ttu-id="5970c-103">モデル ビルダーにトレーニング データを読み込む</span><span class="sxs-lookup"><span data-stu-id="5970c-103">Load training data into Model Builder</span></span>

<span data-ttu-id="5970c-104">ML.NET 用のモデル ビルダー シナリオのいずれかで使用するために、ファイルまたは SQL Server データベースからご利用のトレーニング データセットを読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5970c-104">Learn how to load your training datasets from a file or a SQL Server database for use in one of the Model Builder scenarios for ML.NET.</span></span> <span data-ttu-id="5970c-105">モデル ビルダーのシナリオでは、SQL Server データベース、イメージ ファイル、CSV または TSV ファイル形式をトレーニング データとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="5970c-105">Model Builder scenarios can use SQL Server databases, image files, and CSV or TSV file formats as training data.</span></span>

## <a name="training-dataset-limitations-in-model-builder"></a><span data-ttu-id="5970c-106">モデル ビルダーでのデータセットの制限のトレーニング</span><span class="sxs-lookup"><span data-stu-id="5970c-106">Training dataset limitations in Model Builder</span></span>

<span data-ttu-id="5970c-107">モデル ビルダーでは、モデルのトレーニングに使用できるデータの量と種類が制限されます。</span><span class="sxs-lookup"><span data-stu-id="5970c-107">Model Builder limits the amount and type of data you can use for training models:</span></span>

- <span data-ttu-id="5970c-108">SQL Server データ: 100,000 行</span><span class="sxs-lookup"><span data-stu-id="5970c-108">SQL Server data: 100,000 rows</span></span>
- <span data-ttu-id="5970c-109">CSV ファイルと TSV ファイル: サイズ制限なし</span><span class="sxs-lookup"><span data-stu-id="5970c-109">CSV and TSV files: No size limit</span></span>
- <span data-ttu-id="5970c-110">イメージ:PNG および JPG のみ。</span><span class="sxs-lookup"><span data-stu-id="5970c-110">Images: PNG and JPG only.</span></span>

## <a name="model-builder-scenarios"></a><span data-ttu-id="5970c-111">モデル ビルダーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="5970c-111">Model Builder scenarios</span></span>

<span data-ttu-id="5970c-112">モデル ビルダーは、次の機械学習シナリオ用のモデルを作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5970c-112">Model Builder helps you create models for the following machine learning scenarios:</span></span>

- <span data-ttu-id="5970c-113">センチメント分析 (二項分類)テキスト データを 2 つのカテゴリに分類します。</span><span class="sxs-lookup"><span data-stu-id="5970c-113">Sentiment analysis (binary classification): Classify textual data into two categories.</span></span>
- <span data-ttu-id="5970c-114">問題の分類 (多クラス分類)テキスト データを 3 つ以上のカテゴリに分類します。</span><span class="sxs-lookup"><span data-stu-id="5970c-114">Issue classification (multiclass classification): Classify textual data into 3 or more categories.</span></span>
- <span data-ttu-id="5970c-115">料金の予測 (回帰): 数値を予測します。</span><span class="sxs-lookup"><span data-stu-id="5970c-115">Price prediction (regression): Predict a numeric value.</span></span>
- <span data-ttu-id="5970c-116">イメージ分類 (ディープ ラーニング): 特性に基づいてイメージを分類します。</span><span class="sxs-lookup"><span data-stu-id="5970c-116">Image classification (deep learning): Categorize images based on characteristics.</span></span>
- <span data-ttu-id="5970c-117">カスタム シナリオ: 回帰、分類、およびその他のタスクを使用して、ご利用のデータからカスタム シナリオを作成します。</span><span class="sxs-lookup"><span data-stu-id="5970c-117">Custom scenario: Build custom scenarios from your data using regression, classification, and other tasks.</span></span>

<span data-ttu-id="5970c-118">この記事では、テキスト データまたは数値データを含む分類と回帰のシナリオと、イメージ分類シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5970c-118">This article covers classification and regression scenarios with textual or numerical data, and image classification scenarios.</span></span>

## <a name="load-text-or-numeric-data-from-a-file"></a><span data-ttu-id="5970c-119">ファイルからのテキスト データまたは数値データの読み込み</span><span class="sxs-lookup"><span data-stu-id="5970c-119">Load text or numeric data from a file</span></span>

<span data-ttu-id="5970c-120">ファイルからモデル ビルダーにテキスト データまたは数値データを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5970c-120">You can load text or numeric data from a file into Model Builder.</span></span> <span data-ttu-id="5970c-121">コンマ区切り (CSV) またはタブ区切り (TSV) のファイル形式が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="5970c-121">It accepts comma-delimited (CSV) or tab-delimited (TSV) file formats.</span></span>

1. <span data-ttu-id="5970c-122">モデル ビルダーのデータの手順で、データ ソースのドロップダウンから **[ファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-122">In the data step of Model Builder, select **File** from the data source dropdown.</span></span>
2. <span data-ttu-id="5970c-123">**[ファイルの選択]** テキスト ボックスの横にあるボタンを選択し、エクスプローラーを使用してデータ ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="5970c-123">Select the button next to the **Select a file** text box, and use File Explorer to browse and select the data file.</span></span>
3. <span data-ttu-id="5970c-124">**[予測する列 (ラベル)]** ドロップダウンで [センチメント] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-124">Choose a category in the **Column to Predict (Label)** dropdown.</span></span>
4. <span data-ttu-id="5970c-125">**[入力列 (機能)]** ドロップダウンから、含めるデータ列がチェックされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5970c-125">From the **Input Columns (Features)** dropdown, confirm the data columns you want to include are checked.</span></span>

<span data-ttu-id="5970c-126">モデル ビルダーで使用するデータ ソース ファイルの設定が完了しました。</span><span class="sxs-lookup"><span data-stu-id="5970c-126">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="5970c-127">**[トレーニング]** リンクを選択して、モデル ビルダーの次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="5970c-127">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="load-data-from-a-sql-server-database"></a><span data-ttu-id="5970c-128">SQL Server データベースからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="5970c-128">Load data from a SQL Server database</span></span>

<span data-ttu-id="5970c-129">モデル ビルダーでは、ローカルおよびリモートの SQL Server データベースからのデータの読み込みがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5970c-129">Model Builder supports loading data from local and remote SQL Server databases.</span></span>

<span data-ttu-id="5970c-130">SQL Server データベースからモジュール ビルダーにデータを読み込むには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5970c-130">To load data from a SQL Server database into Module Builder:</span></span>

1. <span data-ttu-id="5970c-131">モデル ビルダーのデータの手順で、データ ソースのドロップダウンから **[SQL Server]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-131">In the data step of Model Builder, select **SQL Server** from the data source dropdown.</span></span>
1. <span data-ttu-id="5970c-132">**[SQL Server データベースに接続]** テキスト ボックスの横にあるボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-132">Select the button next to the **Connect to SQL Server database** text box.</span></span>
    1. <span data-ttu-id="5970c-133">**[データの選択]** ダイアログで、 **[Microsoft SQL Server データベース ファイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-133">In the **Choose Data** dialog, select **Microsoft SQL Server Database File**.</span></span>
    1. <span data-ttu-id="5970c-134">**[常にこれを選択する]** チェックボックスをオフにして、 **[続行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-134">Uncheck the **Always use this selection** checkbox and select **Continue**</span></span>
    1. <span data-ttu-id="5970c-135">**[接続プロパティ]** ダイアログで、 **[参照]** を選択し、ダウンロードした .MDF ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-135">In the **Connection Properties** dialog, select **Browse** and select the downloaded .MDF file.</span></span>
    1. <span data-ttu-id="5970c-136">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-136">Select **OK**</span></span>
1. <span data-ttu-id="5970c-137">**[テーブル名]** ドロップダウンからデータセット名を選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-137">Choose the dataset name from the **Table Name** dropdown.</span></span>
1. <span data-ttu-id="5970c-138">**[予測する列 (ラベル)]** ドロップダウンで、予測を作成するデータ カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="5970c-138">From the **Column to Predict (Label)** dropdown, choose the data category on which you want to make a prediction.</span></span>
1. <span data-ttu-id="5970c-139">**[入力列 (機能)]** ドロップダウンから、含める列がチェックされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5970c-139">From the **Input Columns (Features)** dropdown, confirm the columns you want to include are checked.</span></span>

<span data-ttu-id="5970c-140">モデル ビルダーで使用するデータ ソース ファイルの設定が完了しました。</span><span class="sxs-lookup"><span data-stu-id="5970c-140">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="5970c-141">**[トレーニング]** リンクを選択して、モデル ビルダーの次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="5970c-141">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="set-up-image-data-files"></a><span data-ttu-id="5970c-142">イメージ データ ファイルを設定する</span><span class="sxs-lookup"><span data-stu-id="5970c-142">Set up image data files</span></span>

<span data-ttu-id="5970c-143">モデル ビルダーでは、イメージ データが、分類のカテゴリに対応するフォルダーに整理された JPG または PNG ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5970c-143">Model Builder expects image data to be JPG or PNG files organized in folders that correspond to the categories of the classification.</span></span>

<span data-ttu-id="5970c-144">モデル ビルダーにイメージを読み込むには、単一の最上位ディレクトリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5970c-144">To load images into Model Builder, provide the path to a single top-level directory:</span></span>

- <span data-ttu-id="5970c-145">この最上位ディレクトリには、予測するカテゴリごとにサブフォルダーが 1 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="5970c-145">This top-level directory contains one subfolder for each of the categories to predict.</span></span>
- <span data-ttu-id="5970c-146">各サブフォルダーには、そのカテゴリに属するイメージ ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5970c-146">Each subfolder contains the image files belonging to its category.</span></span>

<span data-ttu-id="5970c-147">次に示すフォルダー構造で、最上位ディレクトリは *flower_photos* です。</span><span class="sxs-lookup"><span data-stu-id="5970c-147">In the folder structure illustrated below, the top-level directory is *flower_photos*.</span></span> <span data-ttu-id="5970c-148">予測するカテゴリに対応したサブディレクトリとして、daisy、dandelion、roses、sunflowers、および tulips の 5 つがあります。</span><span class="sxs-lookup"><span data-stu-id="5970c-148">There are five subdirectories corresponding to the categories you want to predict: daisy, dandelion, roses, sunflowers, and tulips.</span></span> <span data-ttu-id="5970c-149">これらの各サブディレクトリには、それぞれのカテゴリに属するイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5970c-149">Each of these subdirectories contains images belonging to its respective category.</span></span>

```text
\---flower_photos
    +---daisy
    |       100080576_f52e8ee070_n.jpg
    |       102841525_bd6628ae3c.jpg
    |       105806915_a9c13e2106_n.jpg
    |
    +---dandelion
    |       10443973_aeb97513fc_m.jpg
    |       10683189_bd6e371b97.jpg
    |       10919961_0af657c4e8.jpg
    |
    +---roses
    |       102501987_3cdb8e5394_n.jpg
    |       110472418_87b6a3aa98_m.jpg
    |       118974357_0faa23cce9_n.jpg
    |
    +---sunflowers
    |       127192624_afa3d9cb84.jpg
    |       145303599_2627e23815_n.jpg
    |       147804446_ef9244c8ce_m.jpg
    |
    \---tulips
            100930342_92e8746431_n.jpg
            107693873_86021ac4ea_n.jpg
            10791227_7168491604.jpg
```

## <a name="next-steps"></a><span data-ttu-id="5970c-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="5970c-150">Next steps</span></span>

<span data-ttu-id="5970c-151">次のチュートリアルに従って、モデル ビルダーを使用した機械学習アプリの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="5970c-151">Follow these tutorials to build machine learning apps with Model Builder:</span></span>

- [<span data-ttu-id="5970c-152">回帰を使用して価格を予測する</span><span class="sxs-lookup"><span data-stu-id="5970c-152">Predict prices using regression</span></span>](../tutorials/predict-prices-with-model-builder.md)
- [<span data-ttu-id="5970c-153">バイナリ分類を使用して Web アプリケーションのセンチメントを分析する</span><span class="sxs-lookup"><span data-stu-id="5970c-153">Analyze sentiment in a web application using binary classification</span></span>](../tutorials/sentiment-analysis-model-builder.md )

<span data-ttu-id="5970c-154">コードを使用してモデルをトレーニングする場合は、[ML.NET API を使用したデータ読み込みの方法](load-data-ml-net.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5970c-154">If you're training a model using code, [learn how to load data using the ML.NET API](load-data-ml-net.md).</span></span>
