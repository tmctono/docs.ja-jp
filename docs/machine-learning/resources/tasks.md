---
title: 機械学習のタスク
description: ML.NET でサポートされる機械学習のさまざまなタスクと、それらに関連するタスクについて説明します。
ms.custom: seodec18
ms.date: 04/23/2019
author: natke
ms.openlocfilehash: d0634ce8a0559ab3cdb5bf27fc5406ab02af8df6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977256"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="5566e-103">ML.NET での機械学習のタスク</span><span class="sxs-lookup"><span data-stu-id="5566e-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="5566e-104">機械学習モデルを構築する場合は、データを使用して実現したい目的を最初に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="5566e-105">これによって、状況に適した機械学習のタスクを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5566e-105">This allows you to choose the right machine learning task for your situation.</span></span> <span data-ttu-id="5566e-106">選択可能な機械学習のさまざまなタスクといくつかの一般的なユース ケースについて以下で説明します。</span><span class="sxs-lookup"><span data-stu-id="5566e-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span> <span data-ttu-id="5566e-107">シナリオに適したタスクを選択する方法の詳細については、「[アルゴリズム](../how-to-choose-an-ml-net-algorithm.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5566e-107">For more information about choosing the task that is appropriate for your scenario, see [Algorithms](../how-to-choose-an-ml-net-algorithm.md).</span></span>

<span data-ttu-id="5566e-108">どのタスクが自分のシナリオにとって適切かを決定したら、モデルをトレーニングするのに最適なアルゴリズムを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-108">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="5566e-109">使用可能なアルゴリズムは、タスクごとのセクションに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="5566e-109">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="5566e-110">二項分類</span><span class="sxs-lookup"><span data-stu-id="5566e-110">Binary classification</span></span>

<span data-ttu-id="5566e-111">データのインスタンスが 2 つのうちのどちらのクラス (カテゴリ) に属しているかを予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="5566e-111">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="5566e-112">分類アルゴリズムの入力はラベル付けされた一連のサンプルであり、各ラベルは整数 0 または 1 です。</span><span class="sxs-lookup"><span data-stu-id="5566e-112">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="5566e-113">二項分類アルゴリズムの出力は分類子であり、ラベルのない新しいインスタンスのクラスを予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5566e-113">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="5566e-114">二項分類のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5566e-114">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="5566e-115">[Twitter コメントのセンチメントが "肯定的" か "否定的" かを理解する](../tutorials/sentiment-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="5566e-115">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="5566e-116">患者が特定の病気であるかどうかを診断する。</span><span class="sxs-lookup"><span data-stu-id="5566e-116">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="5566e-117">電子メールを "スパム" としてマークするかどうかを決定する。</span><span class="sxs-lookup"><span data-stu-id="5566e-117">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="5566e-118">写真にイヌや果物などの特定のアイテムが含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5566e-118">Determining if a photo contains a particular item or not, such as a dog or fruit.</span></span>

<span data-ttu-id="5566e-119">詳しくは、Wikipedia の[二項分類](https://en.wikipedia.org/wiki/Binary_classification)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5566e-119">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="5566e-120">二項分類トレーナー</span><span class="sxs-lookup"><span data-stu-id="5566e-120">Binary classification trainers</span></span>

<span data-ttu-id="5566e-121">次のアルゴリズムを使用して二項分類モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="5566e-121">You can train a binary classification model using the following algorithms:</span></span>

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

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="5566e-122">二項分類の入力と出力</span><span class="sxs-lookup"><span data-stu-id="5566e-122">Binary classification inputs and outputs</span></span>

<span data-ttu-id="5566e-123">二値分類で最適な結果を得るには、バランスの取れた (すなわち、正と負のトレーニング データの数が等しい) トレーニング データを使用します。</span><span class="sxs-lookup"><span data-stu-id="5566e-123">For best results with binary classification, the training data should be balanced (that is, equal numbers of positive and negative training data).</span></span> <span data-ttu-id="5566e-124">欠損値はトレーニングの前に処理しておきます。</span><span class="sxs-lookup"><span data-stu-id="5566e-124">Missing values should be handled before training.</span></span>

<span data-ttu-id="5566e-125">入力ラベル列データは <xref:System.Boolean> にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-125">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="5566e-126">入力特徴列データは、<xref:System.Single> の固定サイズ ベクターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-126">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="5566e-127">これらのトレーナーから、以下の列が出力されます。</span><span class="sxs-lookup"><span data-stu-id="5566e-127">These trainers output the following columns:</span></span>

| <span data-ttu-id="5566e-128">出力列の名前</span><span class="sxs-lookup"><span data-stu-id="5566e-128">Output Column Name</span></span> | <span data-ttu-id="5566e-129">列の型</span><span class="sxs-lookup"><span data-stu-id="5566e-129">Column Type</span></span> | <span data-ttu-id="5566e-130">説明</span><span class="sxs-lookup"><span data-stu-id="5566e-130">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="5566e-131">モデルによって計算された生のスコア</span><span class="sxs-lookup"><span data-stu-id="5566e-131">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="5566e-132">スコアの符号に基づく予測ラベル。</span><span class="sxs-lookup"><span data-stu-id="5566e-132">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="5566e-133">負のスコアは `false` にマップされ、正のスコアは `true` にマップされます。</span><span class="sxs-lookup"><span data-stu-id="5566e-133">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="5566e-134">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="5566e-134">Multiclass classification</span></span>

<span data-ttu-id="5566e-135">データのインスタンスのクラス (カテゴリ) を予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="5566e-135">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="5566e-136">分類アルゴリズムの入力は、ラベル付けされた一連のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="5566e-136">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="5566e-137">各ラベルは、通常、テキストとして開始されます。</span><span class="sxs-lookup"><span data-stu-id="5566e-137">Each label normally starts as text.</span></span> <span data-ttu-id="5566e-138">その後、TermTransform を経由してキー (数値) 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5566e-138">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="5566e-139">分類アルゴリズムの出力は分類子であり、ラベルのない新しいインスタンスのクラスを予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5566e-139">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="5566e-140">多クラス分類のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5566e-140">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="5566e-141">"シベリアン ハスキー"、"ゴールデン レトリバー"、"プードル" などの犬種を特定する。</span><span class="sxs-lookup"><span data-stu-id="5566e-141">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="5566e-142">映画のレビューが "肯定的"、"中立"、"否定的" のどれかを理解する。</span><span class="sxs-lookup"><span data-stu-id="5566e-142">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="5566e-143">ホテルのレビューを "立地"、"価格"、"清潔さ" などに分類する。</span><span class="sxs-lookup"><span data-stu-id="5566e-143">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="5566e-144">詳しくは、Wikipedia の[多クラス分類](https://en.wikipedia.org/wiki/Multiclass_classification)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5566e-144">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="5566e-145">一対全では、多クラス データセットに対して機能するように[二項分類学習器](#binary-classification)がアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="5566e-145">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="5566e-146">詳細については、[Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest) ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5566e-146">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="5566e-147">多クラス分類トレーナー</span><span class="sxs-lookup"><span data-stu-id="5566e-147">Multiclass classification trainers</span></span>

<span data-ttu-id="5566e-148">次のトレーニング アルゴリズムを使用して多クラス分類モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="5566e-148">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="5566e-149">多クラス分類の入力と出力</span><span class="sxs-lookup"><span data-stu-id="5566e-149">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="5566e-150">入力ラベル列データは[キー](xref:Microsoft.ML.Data.KeyDataViewType)型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-150">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="5566e-151">特徴列は、<xref:System.Single> の固定サイズ ベクターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-151">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="5566e-152">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5566e-152">This trainer outputs the following:</span></span>

| <span data-ttu-id="5566e-153">出力の名前</span><span class="sxs-lookup"><span data-stu-id="5566e-153">Output Name</span></span> | <span data-ttu-id="5566e-154">型</span><span class="sxs-lookup"><span data-stu-id="5566e-154">Type</span></span> | <span data-ttu-id="5566e-155">説明</span><span class="sxs-lookup"><span data-stu-id="5566e-155">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="5566e-156"><xref:System.Single> のベクター</span><span class="sxs-lookup"><span data-stu-id="5566e-156">Vector of <xref:System.Single></span></span> | <span data-ttu-id="5566e-157">すべてのクラスのスコア。</span><span class="sxs-lookup"><span data-stu-id="5566e-157">The scores of all classes.</span></span> <span data-ttu-id="5566e-158">値が大きいほど、関連するクラスに分類される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="5566e-158">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="5566e-159">i 番目の要素が最大値の場合、予測ラベル インデックスは i になります。</span><span class="sxs-lookup"><span data-stu-id="5566e-159">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="5566e-160">i はゼロベースのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="5566e-160">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="5566e-161">[キー](xref:Microsoft.ML.Data.KeyDataViewType)型</span><span class="sxs-lookup"><span data-stu-id="5566e-161">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="5566e-162">予測ラベルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="5566e-162">The predicted label's index.</span></span> <span data-ttu-id="5566e-163">その値が i の場合、実際のラベルはキーと値の入力ラベルの型の i 番目のカテゴリになります。</span><span class="sxs-lookup"><span data-stu-id="5566e-163">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="5566e-164">回帰</span><span class="sxs-lookup"><span data-stu-id="5566e-164">Regression</span></span>

<span data-ttu-id="5566e-165">関連する一連の特徴からラベルの値を予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="5566e-165">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="5566e-166">ラベルには任意の実際の値を使用できます。分類タスクのように有限の値のセットから取得するものではありません。</span><span class="sxs-lookup"><span data-stu-id="5566e-166">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="5566e-167">回帰アルゴリズムでは、ラベルに関連する特徴におけるラベルの依存関係をモデル化して、特徴の値が変化するとラベルがどのように変化するかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5566e-167">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="5566e-168">回帰アルゴリズムの入力は、既知の値のラベルが付いた一連のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="5566e-168">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="5566e-169">回帰アルゴリズムの出力は関数であり、新しい入力特徴のセットのラベル値を予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5566e-169">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="5566e-170">回帰のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5566e-170">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="5566e-171">住宅の属性 (寝室数、立地、規模など) に基づいて住宅価格を予測する。</span><span class="sxs-lookup"><span data-stu-id="5566e-171">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="5566e-172">履歴データと現在の市場動向に基づいて将来の株価を予測する。</span><span class="sxs-lookup"><span data-stu-id="5566e-172">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="5566e-173">広告予算に基づいて製品の売り上げを予測する。</span><span class="sxs-lookup"><span data-stu-id="5566e-173">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="5566e-174">回帰トレーナー</span><span class="sxs-lookup"><span data-stu-id="5566e-174">Regression trainers</span></span>

<span data-ttu-id="5566e-175">次のアルゴリズムを使用して回帰モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="5566e-175">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="5566e-176">回帰の入力と出力</span><span class="sxs-lookup"><span data-stu-id="5566e-176">Regression inputs and outputs</span></span>

<span data-ttu-id="5566e-177">入力ラベル列データは <xref:System.Single> にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-177">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="5566e-178">このタスクのトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5566e-178">The trainers for this task output the following:</span></span>

| <span data-ttu-id="5566e-179">出力の名前</span><span class="sxs-lookup"><span data-stu-id="5566e-179">Output Name</span></span> | <span data-ttu-id="5566e-180">型</span><span class="sxs-lookup"><span data-stu-id="5566e-180">Type</span></span> | <span data-ttu-id="5566e-181">説明</span><span class="sxs-lookup"><span data-stu-id="5566e-181">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="5566e-182">モデルによって予測された生のスコア</span><span class="sxs-lookup"><span data-stu-id="5566e-182">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="5566e-183">クラスタリング</span><span class="sxs-lookup"><span data-stu-id="5566e-183">Clustering</span></span>

<span data-ttu-id="5566e-184">データのインスタンスを、同様の特性を持つクラスタにグループ化するために使用する[教師なし機械学習](glossary.md#unsupervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="5566e-184">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="5566e-185">また、閲覧や単純な観測では論理的に導き出せない可能性のあるデータ セットにおける関係をクラスタリングを使用して識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="5566e-185">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="5566e-186">クラスタリング アルゴリズムの入力と出力は、選択した方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5566e-186">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="5566e-187">分布、重心、結合性、または密度に基づくアプローチを利用できます。</span><span class="sxs-lookup"><span data-stu-id="5566e-187">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="5566e-188">現在、ML.NET では、K 平均法によるクラスタリングを使用した重心に基づくアプローチをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5566e-188">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="5566e-189">クラスタリングのシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5566e-189">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="5566e-190">ホテル選択の傾向と特性に基づいてホテルの宿泊客のセグメントを理解する。</span><span class="sxs-lookup"><span data-stu-id="5566e-190">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="5566e-191">対象を絞った広告キャンペーンの構築に役立つ顧客セグメントと統計データを特定する。</span><span class="sxs-lookup"><span data-stu-id="5566e-191">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="5566e-192">製造メトリックに基づいてインベントリを分類する。</span><span class="sxs-lookup"><span data-stu-id="5566e-192">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="5566e-193">クラスタリング トレーナー</span><span class="sxs-lookup"><span data-stu-id="5566e-193">Clustering trainer</span></span>

<span data-ttu-id="5566e-194">次のアルゴリズムを使用してクラスタリング モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="5566e-194">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="5566e-195">入力と出力のクラスタリング</span><span class="sxs-lookup"><span data-stu-id="5566e-195">Clustering inputs and outputs</span></span>

<span data-ttu-id="5566e-196">入力特徴データは <xref:System.Single> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-196">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="5566e-197">ラベルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5566e-197">No labels are needed.</span></span>

<span data-ttu-id="5566e-198">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5566e-198">This trainer outputs the following:</span></span>

| <span data-ttu-id="5566e-199">出力の名前</span><span class="sxs-lookup"><span data-stu-id="5566e-199">Output Name</span></span> | <span data-ttu-id="5566e-200">型</span><span class="sxs-lookup"><span data-stu-id="5566e-200">Type</span></span> | <span data-ttu-id="5566e-201">説明</span><span class="sxs-lookup"><span data-stu-id="5566e-201">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="5566e-202"><xref:System.Single> のベクター</span><span class="sxs-lookup"><span data-stu-id="5566e-202">vector of <xref:System.Single></span></span> | <span data-ttu-id="5566e-203">与えられたデータ ポイントからすべてのクラスターの重心までの距離</span><span class="sxs-lookup"><span data-stu-id="5566e-203">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="5566e-204">[キー](xref:Microsoft.ML.Data.KeyDataViewType)型</span><span class="sxs-lookup"><span data-stu-id="5566e-204">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="5566e-205">モデルによって予測された最も近いクラスターのインデックス。</span><span class="sxs-lookup"><span data-stu-id="5566e-205">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="5566e-206">異常検出</span><span class="sxs-lookup"><span data-stu-id="5566e-206">Anomaly detection</span></span>

<span data-ttu-id="5566e-207">このタスクでは、主成分分析 (PCA) を使用して、異常検出モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5566e-207">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="5566e-208">PCA に基づく異常分析は、有効なトランザクションなどの 1 つのクラスからトレーニング データを簡単に取得できるが、対象とする異常の十分なサンプルを取得するのが難しいシナリオでモデルを構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5566e-208">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="5566e-209">機械学習における確立された手法である PCA は、データの内部構造を明らかにし、データの分散を説明するために、調査データ分析で頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5566e-209">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="5566e-210">PCA は、複数の変数が含まれるデータを分析することで機能します。</span><span class="sxs-lookup"><span data-stu-id="5566e-210">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="5566e-211">変数の相関を探し、結果内の差異を最も捕らえている値の合成を決定します。</span><span class="sxs-lookup"><span data-stu-id="5566e-211">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="5566e-212">これらの合成されたフィーチャー値を使用して、主成分と呼ばれる、よりコンパクトなフィーチャー空間が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5566e-212">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="5566e-213">異常検出には、機械学習における多くの重要なタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5566e-213">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="5566e-214">不正な可能性があるトランザクションを識別します。</span><span class="sxs-lookup"><span data-stu-id="5566e-214">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="5566e-215">ネットワークへの侵入が発生していることを示唆するパターンを学習します。</span><span class="sxs-lookup"><span data-stu-id="5566e-215">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="5566e-216">患者の異常なクラスターを検出します。</span><span class="sxs-lookup"><span data-stu-id="5566e-216">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="5566e-217">システムに入力された値をチェックします。</span><span class="sxs-lookup"><span data-stu-id="5566e-217">Checking values entered into a system.</span></span>

<span data-ttu-id="5566e-218">異常とは定義上はまれに発生するイベントであるため、モデル化するために使用する代表的なデータ サンプルを収集するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="5566e-218">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="5566e-219">このカテゴリに含まれるアルゴリズムは、不均衡なデータセットの使用によるモデルの構築とトレーニングという主要な課題に対処するように特別に設計されています。</span><span class="sxs-lookup"><span data-stu-id="5566e-219">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="5566e-220">異常検出トレーナー</span><span class="sxs-lookup"><span data-stu-id="5566e-220">Anomaly detection trainer</span></span>

<span data-ttu-id="5566e-221">次のアルゴリズムを使用して異常検出モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="5566e-221">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="5566e-222">異常検出の入力と出力</span><span class="sxs-lookup"><span data-stu-id="5566e-222">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="5566e-223">入力特徴は、<xref:System.Single> の固定サイズのベクターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-223">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="5566e-224">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5566e-224">This trainer outputs the following:</span></span>

| <span data-ttu-id="5566e-225">出力の名前</span><span class="sxs-lookup"><span data-stu-id="5566e-225">Output Name</span></span> | <span data-ttu-id="5566e-226">型</span><span class="sxs-lookup"><span data-stu-id="5566e-226">Type</span></span> | <span data-ttu-id="5566e-227">説明</span><span class="sxs-lookup"><span data-stu-id="5566e-227">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="5566e-228">異常検出モデルによって計算された、負ではない無制限のスコア</span><span class="sxs-lookup"><span data-stu-id="5566e-228">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |

## <a name="ranking"></a><span data-ttu-id="5566e-229">ランキング</span><span class="sxs-lookup"><span data-stu-id="5566e-229">Ranking</span></span>

<span data-ttu-id="5566e-230">ランキング タスクでは、ラベル付きのサンプルのセットからランカーが構築されます。</span><span class="sxs-lookup"><span data-stu-id="5566e-230">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="5566e-231">この例のセットは、特定の条件を使用してスコア付けできるインスタンス グループで構成されています。</span><span class="sxs-lookup"><span data-stu-id="5566e-231">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="5566e-232">順位付けのラベルは、インスタンスごとに {0、1、2、3, 4} です。</span><span class="sxs-lookup"><span data-stu-id="5566e-232">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="5566e-233">各インスタンスのスコアが不明である新しいインスタンス グループをランク付けするように、ランカーがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="5566e-233">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="5566e-234">ML.NET のランキング学習器は、[機械が学習したランキング](https://en.wikipedia.org/wiki/Learning_to_rank)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="5566e-234">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="5566e-235">ランキング トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="5566e-235">Ranking training algorithms</span></span>

<span data-ttu-id="5566e-236">次のアルゴリズムを使ってランキング モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="5566e-236">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="5566e-237">入力と出力のランキング</span><span class="sxs-lookup"><span data-stu-id="5566e-237">Ranking input and outputs</span></span>

<span data-ttu-id="5566e-238">入力ラベル データ型は[キー](xref:Microsoft.ML.Data.KeyDataViewType)型または <xref:System.Single> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-238">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="5566e-239">ラベルの値によって関連性が決まります。値が高いほど関連性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="5566e-239">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="5566e-240">ラベルが[キー](xref:Microsoft.ML.Data.KeyDataViewType)型の場合、キーのインデックスは関連性の値です。ここで、最小のインデックスは最も低い関連性です。</span><span class="sxs-lookup"><span data-stu-id="5566e-240">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="5566e-241">ラベルが <xref:System.Single> の場合、値が大きいほど関連性が高いことを示します。</span><span class="sxs-lookup"><span data-stu-id="5566e-241">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="5566e-242">特徴データは <xref:System.Single> の固定サイズのベクターにする必要があります。また、入力行グループ列は[キー](xref:Microsoft.ML.Data.KeyDataViewType)型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5566e-242">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="5566e-243">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5566e-243">This trainer outputs the following:</span></span>

| <span data-ttu-id="5566e-244">出力の名前</span><span class="sxs-lookup"><span data-stu-id="5566e-244">Output Name</span></span> | <span data-ttu-id="5566e-245">型</span><span class="sxs-lookup"><span data-stu-id="5566e-245">Type</span></span> | <span data-ttu-id="5566e-246">説明</span><span class="sxs-lookup"><span data-stu-id="5566e-246">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="5566e-247">予測を決定するためにモデルによって計算された無制限のスコア</span><span class="sxs-lookup"><span data-stu-id="5566e-247">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="5566e-248">推奨事項</span><span class="sxs-lookup"><span data-stu-id="5566e-248">Recommendation</span></span>

<span data-ttu-id="5566e-249">レコメンデーション タスクによって、推奨される製品やサービスの一覧を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5566e-249">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="5566e-250">ML.NET では、カタログ内に製品のレーティングの履歴データがある場合は、レコメンデーション用の[協調フィルタリング](https://en.wikipedia.org/wiki/Collaborative_filtering) アルゴリズムである[行列因子分解 (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5566e-250">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="5566e-251">たとえば、ユーザーによる映画の採点の履歴データがあるときに、そのユーザーが次に見たいと思う映画を推薦できます。</span><span class="sxs-lookup"><span data-stu-id="5566e-251">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="5566e-252">レコメンデーション トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="5566e-252">Recommendation training algorithms</span></span>

<span data-ttu-id="5566e-253">次のアルゴリズムを使ってレコメンデーション モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="5566e-253">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
