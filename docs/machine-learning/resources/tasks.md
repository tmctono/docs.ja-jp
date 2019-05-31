---
title: 機械学習のタスク
description: ML.NET でサポートされる機械学習のさまざまなタスクと、それらに関連するタスクについて説明します。
ms.custom: seodec18
ms.date: 04/23/2019
author: natke
ms.openlocfilehash: ed6361fdcbca11c100ee5cae4ca76e152ddfba11
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063547"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="80868-103">ML.NET での機械学習のタスク</span><span class="sxs-lookup"><span data-stu-id="80868-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="80868-104">機械学習モデルを構築する場合は、データを使用して実現したい目的を最初に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="80868-105">これによって、状況に適した機械学習のタスクを選択できます。</span><span class="sxs-lookup"><span data-stu-id="80868-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="80868-106">選択可能な機械学習のさまざまなタスクといくつかの一般的なユース ケースについて以下で説明します。</span><span class="sxs-lookup"><span data-stu-id="80868-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span>

<span data-ttu-id="80868-107">どのタスクが自分のシナリオにとって適切かを決定したら、モデルをトレーニングするのに最適なアルゴリズムを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-107">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="80868-108">使用可能なアルゴリズムは、タスクごとのセクションに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="80868-108">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="80868-109">二項分類</span><span class="sxs-lookup"><span data-stu-id="80868-109">Binary classification</span></span>

<span data-ttu-id="80868-110">データのインスタンスが 2 つのうちのどちらのクラス (カテゴリ) に属しているかを予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="80868-110">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="80868-111">分類アルゴリズムの入力はラベル付けされた一連のサンプルであり、各ラベルは整数 0 または 1 です。</span><span class="sxs-lookup"><span data-stu-id="80868-111">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="80868-112">二項分類アルゴリズムの出力は分類子であり、ラベルのない新しいインスタンスのクラスを予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="80868-112">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="80868-113">二項分類のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="80868-113">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="80868-114">[Twitter コメントのセンチメントが "肯定的" か "否定的" かを理解する](../tutorials/sentiment-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="80868-114">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="80868-115">患者が特定の病気であるかどうかを診断する。</span><span class="sxs-lookup"><span data-stu-id="80868-115">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="80868-116">電子メールを "スパム" としてマークするかどうかを決定する。</span><span class="sxs-lookup"><span data-stu-id="80868-116">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="80868-117">写真に犬または果物が含まれているかどうかを決定する。</span><span class="sxs-lookup"><span data-stu-id="80868-117">Determining if a photo contains a dog or fruit.</span></span>

<span data-ttu-id="80868-118">詳しくは、Wikipedia の[二項分類](https://en.wikipedia.org/wiki/Binary_classification)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80868-118">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="80868-119">二項分類トレーナー</span><span class="sxs-lookup"><span data-stu-id="80868-119">Binary classification trainers</span></span>

<span data-ttu-id="80868-120">次のアルゴリズムを使用して二項分類モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="80868-120">You can train a binary classification model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer> 
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer> 
* <xref:Microsoft.ML.Trainers.PriorTrainer> 
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="80868-121">二項分類の入力と出力</span><span class="sxs-lookup"><span data-stu-id="80868-121">Binary classification inputs and outputs</span></span>

<span data-ttu-id="80868-122">二値分類で最適な結果を得るには、バランスの取れた (つまり、正と負のトレーニング データの数が等しい) トレーニング データを使用します。</span><span class="sxs-lookup"><span data-stu-id="80868-122">For best results with binary classification, the training data should be balanced (i.e. equal numbers of positive and negative training data).</span></span> <span data-ttu-id="80868-123">不足や値はトレーニングの前に処理しておきます。</span><span class="sxs-lookup"><span data-stu-id="80868-123">Missing and values should be handled before training.</span></span>

<span data-ttu-id="80868-124">入力ラベル列データは <xref:System.Boolean> にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-124">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="80868-125">入力特徴列データは、<xref:System.Single> の固定サイズ ベクターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-125">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="80868-126">これらのトレーナーから、以下の列が出力されます。</span><span class="sxs-lookup"><span data-stu-id="80868-126">These trainers outputs the following columns:</span></span>

| <span data-ttu-id="80868-127">出力列の名前</span><span class="sxs-lookup"><span data-stu-id="80868-127">Output Column Name</span></span> | <span data-ttu-id="80868-128">列の型</span><span class="sxs-lookup"><span data-stu-id="80868-128">Column Type</span></span> | <span data-ttu-id="80868-129">説明</span><span class="sxs-lookup"><span data-stu-id="80868-129">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="80868-130">モデルによって計算された生のスコア</span><span class="sxs-lookup"><span data-stu-id="80868-130">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="80868-131">スコアの符号に基づく予測ラベル。</span><span class="sxs-lookup"><span data-stu-id="80868-131">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="80868-132">負のスコアは `false` にマップされ、正のスコアは `true` にマップされます。</span><span class="sxs-lookup"><span data-stu-id="80868-132">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="80868-133">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="80868-133">Multiclass classification</span></span>

<span data-ttu-id="80868-134">データのインスタンスのクラス (カテゴリ) を予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="80868-134">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="80868-135">分類アルゴリズムの入力は、ラベル付けされた一連のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="80868-135">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="80868-136">各ラベルは、通常、テキストとして開始されます。</span><span class="sxs-lookup"><span data-stu-id="80868-136">Each label normally starts as text.</span></span> <span data-ttu-id="80868-137">その後、TermTransform を経由してキー (数値) 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="80868-137">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="80868-138">分類アルゴリズムの出力は分類子であり、ラベルのない新しいインスタンスのクラスを予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="80868-138">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="80868-139">多クラス分類のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="80868-139">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="80868-140">"シベリアン ハスキー"、"ゴールデン レトリバー"、"プードル" などの犬種を特定する。</span><span class="sxs-lookup"><span data-stu-id="80868-140">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="80868-141">映画のレビューが "肯定的"、"中立"、"否定的" のどれかを理解する。</span><span class="sxs-lookup"><span data-stu-id="80868-141">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="80868-142">ホテルのレビューを "立地"、"価格"、"清潔さ" などに分類する。</span><span class="sxs-lookup"><span data-stu-id="80868-142">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="80868-143">詳しくは、Wikipedia の[多クラス分類](https://en.wikipedia.org/wiki/Multiclass_classification)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80868-143">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="80868-144">一対全では、多クラス データセットに対して機能するように[二項分類学習器](#binary-classification)がアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="80868-144">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="80868-145">詳細については、[Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80868-145">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="80868-146">多クラス分類トレーナー</span><span class="sxs-lookup"><span data-stu-id="80868-146">Multiclass classification trainers</span></span>

<span data-ttu-id="80868-147">次のトレーニング アルゴリズムを使用して多クラス分類モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="80868-147">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer> 
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer> 

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="80868-148">多クラス分類の入力と出力</span><span class="sxs-lookup"><span data-stu-id="80868-148">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="80868-149">入力ラベル列データは[キー](xref:Microsoft.ML.Data.KeyDataViewType)型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-149">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="80868-150">特徴列は、<xref:System.Single> の固定サイズ ベクターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-150">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="80868-151">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80868-151">This trainer outputs the following:</span></span>

| <span data-ttu-id="80868-152">出力の名前</span><span class="sxs-lookup"><span data-stu-id="80868-152">Output Name</span></span> | <span data-ttu-id="80868-153">型</span><span class="sxs-lookup"><span data-stu-id="80868-153">Type</span></span> | <span data-ttu-id="80868-154">説明</span><span class="sxs-lookup"><span data-stu-id="80868-154">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="80868-155"><xref:System.Single> のベクター</span><span class="sxs-lookup"><span data-stu-id="80868-155">Vector of <xref:System.Single></span></span> | <span data-ttu-id="80868-156">すべてのクラスのスコア。</span><span class="sxs-lookup"><span data-stu-id="80868-156">The scores of all classes.</span></span> <span data-ttu-id="80868-157">値が大きいほど、関連するクラスに分類される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="80868-157">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="80868-158">i 番目の要素が最大値の場合、予測ラベル インデックスは i になります。</span><span class="sxs-lookup"><span data-stu-id="80868-158">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="80868-159">i はゼロベースのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="80868-159">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="80868-160">[キー](xref:Microsoft.ML.Data.KeyDataViewType)型</span><span class="sxs-lookup"><span data-stu-id="80868-160">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="80868-161">予測ラベルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="80868-161">The predicted label's index.</span></span> <span data-ttu-id="80868-162">その値が i の場合、実際のラベルはキーと値の入力ラベルの型の i 番目のカテゴリになります。</span><span class="sxs-lookup"><span data-stu-id="80868-162">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="80868-163">回帰</span><span class="sxs-lookup"><span data-stu-id="80868-163">Regression</span></span>

<span data-ttu-id="80868-164">関連する一連の特徴からラベルの値を予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="80868-164">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="80868-165">ラベルには任意の実際の値を使用できます。分類タスクのように有限の値のセットから取得するものではありません。</span><span class="sxs-lookup"><span data-stu-id="80868-165">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="80868-166">回帰アルゴリズムでは、ラベルに関連する特徴におけるラベルの依存関係をモデル化して、特徴の値が変化するとラベルがどのように変化するかを判断します。</span><span class="sxs-lookup"><span data-stu-id="80868-166">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="80868-167">回帰アルゴリズムの入力は、既知の値のラベルが付いた一連のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="80868-167">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="80868-168">回帰アルゴリズムの出力は関数であり、新しい入力特徴のセットのラベル値を予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="80868-168">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="80868-169">回帰のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="80868-169">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="80868-170">住宅の属性 (寝室数、立地、規模など) に基づいて住宅価格を予測する。</span><span class="sxs-lookup"><span data-stu-id="80868-170">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="80868-171">履歴データと現在の市場動向に基づいて将来の株価を予測する。</span><span class="sxs-lookup"><span data-stu-id="80868-171">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="80868-172">広告予算に基づいて製品の売り上げを予測する。</span><span class="sxs-lookup"><span data-stu-id="80868-172">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="80868-173">回帰トレーナー</span><span class="sxs-lookup"><span data-stu-id="80868-173">Regression trainers</span></span>

<span data-ttu-id="80868-174">次のアルゴリズムを使用して回帰モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="80868-174">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer> 
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="80868-175">回帰の入力と出力</span><span class="sxs-lookup"><span data-stu-id="80868-175">Regression inputs and outputs</span></span>

<span data-ttu-id="80868-176">入力ラベル列データは <xref:System.Single> にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-176">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="80868-177">このタスクのトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80868-177">The trainers for this task output the following:</span></span>

| <span data-ttu-id="80868-178">出力の名前</span><span class="sxs-lookup"><span data-stu-id="80868-178">Output Name</span></span> | <span data-ttu-id="80868-179">型</span><span class="sxs-lookup"><span data-stu-id="80868-179">Type</span></span> | <span data-ttu-id="80868-180">説明</span><span class="sxs-lookup"><span data-stu-id="80868-180">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="80868-181">モデルによって予測された生のスコア</span><span class="sxs-lookup"><span data-stu-id="80868-181">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="80868-182">クラスタリング</span><span class="sxs-lookup"><span data-stu-id="80868-182">Clustering</span></span>

<span data-ttu-id="80868-183">データのインスタンスを、同様の特性を持つクラスタにグループ化するために使用する[教師なし機械学習](glossary.md#unsupervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="80868-183">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="80868-184">また、閲覧や単純な観測では論理的に導き出せない可能性のあるデータ セットにおける関係をクラスタリングを使用して識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="80868-184">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="80868-185">クラスタリング アルゴリズムの入力と出力は、選択した方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="80868-185">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="80868-186">分布、重心、結合性、または密度に基づくアプローチを利用できます。</span><span class="sxs-lookup"><span data-stu-id="80868-186">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="80868-187">現在、ML.NET では、K 平均法によるクラスタリングを使用した重心に基づくアプローチをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="80868-187">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="80868-188">クラスタリングのシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="80868-188">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="80868-189">ホテル選択の傾向と特性に基づいてホテルの宿泊客のセグメントを理解する。</span><span class="sxs-lookup"><span data-stu-id="80868-189">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="80868-190">対象を絞った広告キャンペーンの構築に役立つ顧客セグメントと統計データを特定する。</span><span class="sxs-lookup"><span data-stu-id="80868-190">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="80868-191">製造メトリックに基づいてインベントリを分類する。</span><span class="sxs-lookup"><span data-stu-id="80868-191">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="80868-192">クラスタリング トレーナー</span><span class="sxs-lookup"><span data-stu-id="80868-192">Clustering trainer</span></span>

<span data-ttu-id="80868-193">次のアルゴリズムを使用してクラスタリング モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="80868-193">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer> 

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="80868-194">入力と出力のクラスタリング</span><span class="sxs-lookup"><span data-stu-id="80868-194">Clustering inputs and outputs</span></span>

<span data-ttu-id="80868-195">入力特徴データは <xref:System.Single> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-195">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="80868-196">ラベルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="80868-196">No labels are needed.</span></span>

<span data-ttu-id="80868-197">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80868-197">This trainer outputs the following:</span></span>

| <span data-ttu-id="80868-198">出力の名前</span><span class="sxs-lookup"><span data-stu-id="80868-198">Output Name</span></span> | <span data-ttu-id="80868-199">型</span><span class="sxs-lookup"><span data-stu-id="80868-199">Type</span></span> | <span data-ttu-id="80868-200">説明</span><span class="sxs-lookup"><span data-stu-id="80868-200">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="80868-201"><xref:System.Single> のベクター</span><span class="sxs-lookup"><span data-stu-id="80868-201">vector of <xref:System.Single></span></span> | <span data-ttu-id="80868-202">与えられたデータ ポイントからすべてのクラスターの重心までの距離</span><span class="sxs-lookup"><span data-stu-id="80868-202">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="80868-203">[キー](xref:Microsoft.ML.Data.KeyDataViewType)型</span><span class="sxs-lookup"><span data-stu-id="80868-203">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="80868-204">モデルによって予測された最も近いクラスターのインデックス。</span><span class="sxs-lookup"><span data-stu-id="80868-204">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="80868-205">異常検出</span><span class="sxs-lookup"><span data-stu-id="80868-205">Anomaly detection</span></span>

<span data-ttu-id="80868-206">このタスクでは、主成分分析 (PCA) を使用して、異常検出モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="80868-206">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="80868-207">PCA に基づく異常分析は、有効なトランザクションなどの 1 つのクラスからトレーニング データを簡単に取得できるが、対象とする異常の十分なサンプルを取得するのが難しいシナリオでモデルを構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="80868-207">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="80868-208">機械学習における確立された手法である PCA は、データの内部構造を明らかにし、データの分散を説明するために、調査データ分析で頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="80868-208">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="80868-209">PCA は、複数の変数が含まれるデータを分析することで機能します。</span><span class="sxs-lookup"><span data-stu-id="80868-209">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="80868-210">変数の相関を探し、結果内の差異を最も捕らえている値の合成を決定します。</span><span class="sxs-lookup"><span data-stu-id="80868-210">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="80868-211">これらの合成されたフィーチャー値を使用して、主成分と呼ばれる、よりコンパクトなフィーチャー空間が作成されます。</span><span class="sxs-lookup"><span data-stu-id="80868-211">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="80868-212">異常検出には、機械学習における多くの重要なタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="80868-212">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="80868-213">不正な可能性があるトランザクションを識別します。</span><span class="sxs-lookup"><span data-stu-id="80868-213">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="80868-214">ネットワークへの侵入が発生していることを示唆するパターンを学習します。</span><span class="sxs-lookup"><span data-stu-id="80868-214">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="80868-215">患者の異常なクラスターを検出します。</span><span class="sxs-lookup"><span data-stu-id="80868-215">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="80868-216">システムに入力された値をチェックします。</span><span class="sxs-lookup"><span data-stu-id="80868-216">Checking values entered into a system.</span></span>

<span data-ttu-id="80868-217">異常とは定義上はまれに発生するイベントであるため、モデル化するために使用する代表的なデータ サンプルを収集するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="80868-217">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="80868-218">このカテゴリに含まれるアルゴリズムは、不均衡なデータセットの使用によるモデルの構築とトレーニングという主要な課題に対処するように特別に設計されています。</span><span class="sxs-lookup"><span data-stu-id="80868-218">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="80868-219">異常検出トレーナー</span><span class="sxs-lookup"><span data-stu-id="80868-219">Anomaly detection trainer</span></span>

<span data-ttu-id="80868-220">次のアルゴリズムを使用して異常検出モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="80868-220">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="80868-221">異常検出の入力と出力</span><span class="sxs-lookup"><span data-stu-id="80868-221">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="80868-222">入力特徴は、<xref:System.Single> の固定サイズのベクターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-222">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="80868-223">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80868-223">This trainer outputs the following:</span></span>

| <span data-ttu-id="80868-224">出力の名前</span><span class="sxs-lookup"><span data-stu-id="80868-224">Output Name</span></span> | <span data-ttu-id="80868-225">型</span><span class="sxs-lookup"><span data-stu-id="80868-225">Type</span></span> | <span data-ttu-id="80868-226">説明</span><span class="sxs-lookup"><span data-stu-id="80868-226">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="80868-227">異常検出モデルによって計算された、負ではない無制限のスコア</span><span class="sxs-lookup"><span data-stu-id="80868-227">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |

## <a name="ranking"></a><span data-ttu-id="80868-228">ランキング</span><span class="sxs-lookup"><span data-stu-id="80868-228">Ranking</span></span>

<span data-ttu-id="80868-229">ランキング タスクでは、ラベル付きのサンプルのセットからランカーが構築されます。</span><span class="sxs-lookup"><span data-stu-id="80868-229">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="80868-230">この例のセットは、特定の条件を使用してスコア付けできるインスタンス グループで構成されています。</span><span class="sxs-lookup"><span data-stu-id="80868-230">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="80868-231">順位付けのラベルは、インスタンスごとに {0、1、2、3, 4} です。</span><span class="sxs-lookup"><span data-stu-id="80868-231">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="80868-232">各インスタンスのスコアが不明である新しいインスタンス グループをランク付けするように、ランカーがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="80868-232">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="80868-233">ML.NET のランキング学習器は、[機械が学習したランキング](https://en.wikipedia.org/wiki/Learning_to_rank)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="80868-233">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="80868-234">ランキング トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="80868-234">Ranking training algorithms</span></span>

<span data-ttu-id="80868-235">次のアルゴリズムを使ってランキング モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="80868-235">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer> 

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="80868-236">入力と出力のランキング</span><span class="sxs-lookup"><span data-stu-id="80868-236">Ranking input and outputs</span></span>

<span data-ttu-id="80868-237">入力ラベル データ型は[キー](xref:Microsoft.ML.Data.KeyDataViewType)型または <xref:System.Single> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-237">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="80868-238">ラベルの値によって関連性が決まります。値が高いほど関連性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="80868-238">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="80868-239">ラベルが[キー](xref:Microsoft.ML.Data.KeyDataViewType)型の場合、キーのインデックスは関連性の値です。ここで、最小のインデックスは最も低い関連性です。</span><span class="sxs-lookup"><span data-stu-id="80868-239">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="80868-240">ラベルが <xref:System.Single> の場合、値が大きいほど関連性が高いことを示します。</span><span class="sxs-lookup"><span data-stu-id="80868-240">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="80868-241">特徴データは <xref:System.Single> の固定サイズのベクターにする必要があります。また、入力行グループ列は[キー](xref:Microsoft.ML.Data.KeyDataViewType)型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80868-241">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="80868-242">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80868-242">This trainer outputs the following:</span></span>

| <span data-ttu-id="80868-243">出力の名前</span><span class="sxs-lookup"><span data-stu-id="80868-243">Output Name</span></span> | <span data-ttu-id="80868-244">型</span><span class="sxs-lookup"><span data-stu-id="80868-244">Type</span></span> | <span data-ttu-id="80868-245">説明</span><span class="sxs-lookup"><span data-stu-id="80868-245">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="80868-246">予測を決定するためにモデルによって計算された無制限のスコア</span><span class="sxs-lookup"><span data-stu-id="80868-246">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="80868-247">推奨事項</span><span class="sxs-lookup"><span data-stu-id="80868-247">Recommendation</span></span>

<span data-ttu-id="80868-248">レコメンデーション タスクによって、推奨される製品やサービスの一覧を作成できます。</span><span class="sxs-lookup"><span data-stu-id="80868-248">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="80868-249">ML.NET では、カタログ内に製品のレーティングの履歴データがある場合は、レコメンデーション用の[協調フィルタリング](https://en.wikipedia.org/wiki/Collaborative_filtering) アルゴリズムである[行列因子分解 (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="80868-249">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="80868-250">たとえば、ユーザーによる映画の採点の履歴データがあるときに、そのユーザーが次に見たいと思う映画を推薦できます。</span><span class="sxs-lookup"><span data-stu-id="80868-250">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="80868-251">レコメンデーション トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="80868-251">Recommendation training algorithms</span></span>

<span data-ttu-id="80868-252">次のアルゴリズムを使ってレコメンデーション モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="80868-252">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
