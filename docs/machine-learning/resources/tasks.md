---
title: 機械学習のタスク - ML.NET
description: ML.NET でサポートされる機械学習のさまざまなタスクと、それらに関連するタスクについて説明します。
ms.custom: seodec18
ms.date: 04/12/2019
author: natke
ms.openlocfilehash: bfed9cf12f8d539c4327549e5305415ce096e022
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613162"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="278d4-103">ML.NET での機械学習のタスク</span><span class="sxs-lookup"><span data-stu-id="278d4-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="278d4-104">機械学習モデルを構築する場合は、データを使用して実現したい目的を最初に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="278d4-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="278d4-105">これによって、状況に適した機械学習のタスクを選択できます。</span><span class="sxs-lookup"><span data-stu-id="278d4-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="278d4-106">選択可能な機械学習のさまざまなタスクといくつかの一般的なユース ケースについて以下で説明します。</span><span class="sxs-lookup"><span data-stu-id="278d4-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="278d4-107">どのタスクが自分のシナリオにとって適切かを決定したら、モデルをトレーニングするのに最適なアルゴリズムを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="278d4-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="278d4-108">使用可能なアルゴリズムは、タスクごとのセクションに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="278d4-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="278d4-109">二項分類</span><span class="sxs-lookup"><span data-stu-id="278d4-109">Binary classification</span></span>

<span data-ttu-id="278d4-110">データのインスタンスが 2 つのうちのどちらのクラス (カテゴリ) に属しているかを予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="278d4-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="278d4-111">分類アルゴリズムの入力はラベル付けされた一連のサンプルであり、各ラベルは整数 0 または 1 です。</span><span class="sxs-lookup"><span data-stu-id="278d4-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="278d4-112">二項分類アルゴリズムの出力は分類子であり、ラベルのない新しいインスタンスのクラスを予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="278d4-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="278d4-113">二項分類のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="278d4-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="278d4-114">[Twitter コメントのセンチメントが "肯定的" か "否定的" かを理解する](../tutorials/sentiment-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="278d4-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="278d4-115">患者が特定の病気であるかどうかを診断する。</span><span class="sxs-lookup"><span data-stu-id="278d4-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="278d4-116">電子メールを "スパム" としてマークするかどうかを決定する。</span><span class="sxs-lookup"><span data-stu-id="278d4-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="278d4-117">写真に犬または果物が含まれているかどうかを決定する。</span><span class="sxs-lookup"><span data-stu-id="278d4-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="278d4-118">詳しくは、Wikipedia の[二項分類](https://en.wikipedia.org/wiki/Binary_classification)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="278d4-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-training-algorithms"></a><span data-ttu-id="278d4-119">二項分類トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="278d4-119">Binary Classification Training Algorithms</span></span>

<span data-ttu-id="278d4-120">次のアルゴリズムを使用して二項分類モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="278d4-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>

## <a name="multiclass-classification"></a><span data-ttu-id="278d4-121">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="278d4-121">Multiclass classification</span></span>

<span data-ttu-id="278d4-122">データのインスタンスのクラス (カテゴリ) を予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="278d4-122">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="278d4-123">分類アルゴリズムの入力は、ラベル付けされた一連のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="278d4-123">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="278d4-124">各ラベルは、通常、テキストとして開始されます。</span><span class="sxs-lookup"><span data-stu-id="278d4-124">Each label normally starts as text.</span></span> <span data-ttu-id="278d4-125">その後、TermTransform を経由してキー (数値) 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="278d4-125">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="278d4-126">分類アルゴリズムの出力は分類子であり、ラベルのない新しいインスタンスのクラスを予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="278d4-126">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="278d4-127">多クラス分類のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="278d4-127">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="278d4-128">"シベリアン ハスキー"、"ゴールデン レトリバー"、"プードル" などの犬種を特定する。</span><span class="sxs-lookup"><span data-stu-id="278d4-128">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="278d4-129">映画のレビューが "肯定的"、"中立"、"否定的" のどれかを理解する。</span><span class="sxs-lookup"><span data-stu-id="278d4-129">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="278d4-130">ホテルのレビューを "立地"、"価格"、"清潔さ" などに分類する。</span><span class="sxs-lookup"><span data-stu-id="278d4-130">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="278d4-131">詳しくは、Wikipedia の[多クラス分類](https://en.wikipedia.org/wiki/Multiclass_classification)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="278d4-131">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="278d4-132">一対全では、多クラス データセットに対して機能するように[二項分類学習器](#binary-classification)がアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="278d4-132">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="278d4-133">詳細については、[Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="278d4-133">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-training-algorithms"></a><span data-ttu-id="278d4-134">多クラス分類のトレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="278d4-134">Multiclass Classification training algorithms</span></span>

<span data-ttu-id="278d4-135">次のトレーニング アルゴリズムを使用して多クラス分類モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="278d4-135">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

## <a name="regression"></a><span data-ttu-id="278d4-136">回帰</span><span class="sxs-lookup"><span data-stu-id="278d4-136">Regression</span></span>

<span data-ttu-id="278d4-137">関連する一連の特徴からラベルの値を予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="278d4-137">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="278d4-138">ラベルには任意の実際の値を使用できます。分類タスクのように有限の値のセットから取得するものではありません。</span><span class="sxs-lookup"><span data-stu-id="278d4-138">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="278d4-139">回帰アルゴリズムでは、ラベルに関連する特徴におけるラベルの依存関係をモデル化して、特徴の値が変化するとラベルがどのように変化するかを判断します。</span><span class="sxs-lookup"><span data-stu-id="278d4-139">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="278d4-140">回帰アルゴリズムの入力は、既知の値のラベルが付いた一連のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="278d4-140">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="278d4-141">回帰アルゴリズムの出力は関数であり、新しい入力特徴のセットのラベル値を予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="278d4-141">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="278d4-142">回帰のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="278d4-142">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="278d4-143">住宅の属性 (寝室数、立地、規模など) に基づいて住宅価格を予測する。</span><span class="sxs-lookup"><span data-stu-id="278d4-143">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="278d4-144">履歴データと現在の市場動向に基づいて将来の株価を予測する。</span><span class="sxs-lookup"><span data-stu-id="278d4-144">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="278d4-145">広告予算に基づいて製品の売り上げを予測する。</span><span class="sxs-lookup"><span data-stu-id="278d4-145">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-training-algorithms"></a><span data-ttu-id="278d4-146">回帰トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="278d4-146">Regression training algorithms</span></span>

<span data-ttu-id="278d4-147">次のアルゴリズムを使用して回帰モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="278d4-147">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>

## <a name="clustering"></a><span data-ttu-id="278d4-148">クラスタリング</span><span class="sxs-lookup"><span data-stu-id="278d4-148">Clustering</span></span>

<span data-ttu-id="278d4-149">データのインスタンスを、同様の特性を持つクラスタにグループ化するために使用する[教師なし機械学習](glossary.md#unsupervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="278d4-149">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="278d4-150">また、閲覧や単純な観測では論理的に導き出せない可能性のあるデータ セットにおける関係をクラスタリングを使用して識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="278d4-150">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="278d4-151">クラスタリング アルゴリズムの入力と出力は、選択した方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="278d4-151">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="278d4-152">分布、重心、結合性、または密度に基づくアプローチを利用できます。</span><span class="sxs-lookup"><span data-stu-id="278d4-152">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="278d4-153">現在、ML.NET では、K 平均法によるクラスタリングを使用した重心に基づくアプローチをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="278d4-153">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="278d4-154">クラスタリングのシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="278d4-154">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="278d4-155">ホテル選択の傾向と特性に基づいてホテルの宿泊客のセグメントを理解する。</span><span class="sxs-lookup"><span data-stu-id="278d4-155">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="278d4-156">対象を絞った広告キャンペーンの構築に役立つ顧客セグメントと統計データを特定する。</span><span class="sxs-lookup"><span data-stu-id="278d4-156">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="278d4-157">製造メトリックに基づいてインベントリを分類する。</span><span class="sxs-lookup"><span data-stu-id="278d4-157">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-training-algorithms"></a><span data-ttu-id="278d4-158">クラスタリング トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="278d4-158">Clustering training algorithms</span></span>

<span data-ttu-id="278d4-159">次のアルゴリズムを使用してクラスタリング モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="278d4-159">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

## <a name="anomaly-detection"></a><span data-ttu-id="278d4-160">異常検出</span><span class="sxs-lookup"><span data-stu-id="278d4-160">Anomaly detection</span></span>

<span data-ttu-id="278d4-161">このタスクでは、主成分分析 (PCA) を使用して、異常検出モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="278d4-161">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="278d4-162">PCA に基づく異常分析は、有効なトランザクションなどの 1 つのクラスからトレーニング データを簡単に取得できるが、対象とする異常の十分なサンプルを取得するのが難しいシナリオでモデルを構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="278d4-162">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="278d4-163">機械学習における確立された手法である PCA は、データの内部構造を明らかにし、データの分散を説明するために、調査データ分析で頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="278d4-163">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="278d4-164">PCA は、複数の変数が含まれるデータを分析することで機能します。</span><span class="sxs-lookup"><span data-stu-id="278d4-164">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="278d4-165">変数の相関を探し、結果内の差異を最も捕らえている値の合成を決定します。</span><span class="sxs-lookup"><span data-stu-id="278d4-165">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="278d4-166">これらの合成されたフィーチャー値を使用して、主成分と呼ばれる、よりコンパクトなフィーチャー空間が作成されます。</span><span class="sxs-lookup"><span data-stu-id="278d4-166">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="278d4-167">異常検出には、機械学習における多くの重要なタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="278d4-167">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="278d4-168">不正な可能性があるトランザクションを識別します。</span><span class="sxs-lookup"><span data-stu-id="278d4-168">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="278d4-169">ネットワークへの侵入が発生していることを示唆するパターンを学習します。</span><span class="sxs-lookup"><span data-stu-id="278d4-169">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="278d4-170">患者の異常なクラスターを検出します。</span><span class="sxs-lookup"><span data-stu-id="278d4-170">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="278d4-171">システムに入力された値をチェックします。</span><span class="sxs-lookup"><span data-stu-id="278d4-171">Checking values entered into a system.</span></span>

<span data-ttu-id="278d4-172">異常とは定義上はまれに発生するイベントであるため、モデル化するために使用する代表的なデータ サンプルを収集するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="278d4-172">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="278d4-173">このカテゴリに含まれるアルゴリズムは、不均衡なデータセットの使用によるモデルの構築とトレーニングという主要な課題に対処するように特別に設計されています。</span><span class="sxs-lookup"><span data-stu-id="278d4-173">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-training-algorithms"></a><span data-ttu-id="278d4-174">異常検出トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="278d4-174">Anomaly detection training algorithms</span></span>

<span data-ttu-id="278d4-175">次のアルゴリズムを使用して異常検出モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="278d4-175">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

## <a name="ranking"></a><span data-ttu-id="278d4-176">ランキング</span><span class="sxs-lookup"><span data-stu-id="278d4-176">Ranking</span></span>

<span data-ttu-id="278d4-177">ランキング タスクでは、ラベル付きのサンプルのセットからランカーが構築されます。</span><span class="sxs-lookup"><span data-stu-id="278d4-177">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="278d4-178">この例のセットは、特定の条件を使用してスコア付けできるインスタンス グループで構成されています。</span><span class="sxs-lookup"><span data-stu-id="278d4-178">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="278d4-179">順位付けのラベルは、インスタンスごとに {0、1、2、3, 4} です。</span><span class="sxs-lookup"><span data-stu-id="278d4-179">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="278d4-180">各インスタンスのスコアが不明である新しいインスタンス グループをランク付けするように、ランカーがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="278d4-180">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="278d4-181">ML.NET のランキング学習器は、[機械が学習したランキング](https://en.wikipedia.org/wiki/Learning_to_rank)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="278d4-181">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="278d4-182">ランキング トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="278d4-182">Ranking training algorithms</span></span>

<span data-ttu-id="278d4-183">次のアルゴリズムを使ってランキング モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="278d4-183">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>

## <a name="recommendation"></a><span data-ttu-id="278d4-184">推奨事項</span><span class="sxs-lookup"><span data-stu-id="278d4-184">Recommendation</span></span>

<span data-ttu-id="278d4-185">レコメンデーション タスクによって、推奨される製品やサービスの一覧を作成できます。</span><span class="sxs-lookup"><span data-stu-id="278d4-185">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="278d4-186">ML.NET では、カタログ内に製品のレーティングの履歴データがある場合は、レコメンデーション用の[協調フィルタリング](https://en.wikipedia.org/wiki/Collaborative_filtering) アルゴリズムである[行列因子分解 (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="278d4-186">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="278d4-187">たとえば、ユーザーによる映画の採点の履歴データがあるときに、そのユーザーが次に見たいと思う映画を推薦できます。</span><span class="sxs-lookup"><span data-stu-id="278d4-187">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="278d4-188">レコメンデーション トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="278d4-188">Recommendation training algorithms</span></span>

<span data-ttu-id="278d4-189">次のアルゴリズムを使ってレコメンデーション モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="278d4-189">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
