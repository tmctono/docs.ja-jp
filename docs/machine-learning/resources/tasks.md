---
title: 機械学習のタスク
description: ML.NET でサポートされる機械学習のさまざまなタスクと、それらに関連するタスクについて説明します。
ms.date: 12/23/2019
ms.openlocfilehash: badb096ab3e7fbd575d8594b4fbd0e2ebaf63820
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739627"
---
# <a name="machine-learning-tasks-in-mlnet"></a><span data-ttu-id="20e04-103">ML.NET での機械学習のタスク</span><span class="sxs-lookup"><span data-stu-id="20e04-103">Machine learning tasks in ML.NET</span></span>

<span data-ttu-id="20e04-104">機械学習タスクとは、問題や質問、および利用可能なデータに基づいて行われる予測または推論の種類です。</span><span class="sxs-lookup"><span data-stu-id="20e04-104">A machine learning task is the type of prediction or inference being made, based on the problem or question that is being asked, and the available data.</span></span> <span data-ttu-id="20e04-105">たとえば、分類タスクはデータをカテゴリに割り当て、クラスター化タスクは類似性に従ってデータをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="20e04-105">For example, the classification task assigns data to categories, and the clustering task groups data according to similarity.</span></span>

<span data-ttu-id="20e04-106">機械学習タスクはデータのパターンに依存します。明示的にプログラミングされるのでありません。</span><span class="sxs-lookup"><span data-stu-id="20e04-106">Machine learning tasks rely on patterns in the data rather than being explicitly programmed.</span></span>

<span data-ttu-id="20e04-107">この記事では、ML.NET から選択できる機械学習のさまざまなタスクと、一般的なユース ケースをいくつか取り上げ説明します。</span><span class="sxs-lookup"><span data-stu-id="20e04-107">This article describes the different machine learning tasks that you can choose from in ML.NET and some common use cases.</span></span>

<span data-ttu-id="20e04-108">どのタスクが自分のシナリオにとって適切かを決定したら、モデルをトレーニングするのに最適なアルゴリズムを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-108">Once you have decided which task works for your scenario, then you need to choose the best algorithm to train your model.</span></span> <span data-ttu-id="20e04-109">使用可能なアルゴリズムは、タスクごとのセクションに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="20e04-109">The available algorithms are listed in the section for each task.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="20e04-110">二項分類</span><span class="sxs-lookup"><span data-stu-id="20e04-110">Binary classification</span></span>

<span data-ttu-id="20e04-111">データのインスタンスが 2 つのうちのどちらのクラス (カテゴリ) に属しているかを予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="20e04-111">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="20e04-112">分類アルゴリズムの入力はラベル付けされた一連のサンプルであり、各ラベルは整数 0 または 1 です。</span><span class="sxs-lookup"><span data-stu-id="20e04-112">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="20e04-113">二項分類アルゴリズムの出力は分類子であり、ラベルのない新しいインスタンスのクラスを予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="20e04-113">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="20e04-114">二項分類のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="20e04-114">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="20e04-115">[Twitter コメントのセンチメントが "肯定的" か "否定的" かを理解する](../tutorials/sentiment-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="20e04-115">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="20e04-116">患者が特定の病気であるかどうかを診断する。</span><span class="sxs-lookup"><span data-stu-id="20e04-116">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="20e04-117">電子メールを "スパム" としてマークするかどうかを決定する。</span><span class="sxs-lookup"><span data-stu-id="20e04-117">Making a decision to mark an email as "spam" or not.</span></span>
* <span data-ttu-id="20e04-118">写真にイヌや果物などの特定のアイテムが含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="20e04-118">Determining if a photo contains a particular item or not, such as a dog or fruit.</span></span>

<span data-ttu-id="20e04-119">詳しくは、Wikipedia の[二項分類](https://en.wikipedia.org/wiki/Binary_classification)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20e04-119">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

### <a name="binary-classification-trainers"></a><span data-ttu-id="20e04-120">二項分類トレーナー</span><span class="sxs-lookup"><span data-stu-id="20e04-120">Binary classification trainers</span></span>

<span data-ttu-id="20e04-121">次のアルゴリズムを使用して二項分類モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="20e04-121">You can train a binary classification model using the following algorithms:</span></span>

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

### <a name="binary-classification-inputs-and-outputs"></a><span data-ttu-id="20e04-122">二項分類の入力と出力</span><span class="sxs-lookup"><span data-stu-id="20e04-122">Binary classification inputs and outputs</span></span>

<span data-ttu-id="20e04-123">二値分類で最適な結果を得るには、バランスの取れた (すなわち、正と負のトレーニング データの数が等しい) トレーニング データを使用します。</span><span class="sxs-lookup"><span data-stu-id="20e04-123">For best results with binary classification, the training data should be balanced (that is, equal numbers of positive and negative training data).</span></span> <span data-ttu-id="20e04-124">欠損値はトレーニングの前に処理しておきます。</span><span class="sxs-lookup"><span data-stu-id="20e04-124">Missing values should be handled before training.</span></span>

<span data-ttu-id="20e04-125">入力ラベル列データは <xref:System.Boolean> にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-125">The input label column data must be <xref:System.Boolean>.</span></span>
<span data-ttu-id="20e04-126">入力特徴列データは、<xref:System.Single> の固定サイズ ベクターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-126">The input features column data must be a fixed-size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="20e04-127">これらのトレーナーから、以下の列が出力されます。</span><span class="sxs-lookup"><span data-stu-id="20e04-127">These trainers output the following columns:</span></span>

| <span data-ttu-id="20e04-128">出力列の名前</span><span class="sxs-lookup"><span data-stu-id="20e04-128">Output Column Name</span></span> | <span data-ttu-id="20e04-129">列の型</span><span class="sxs-lookup"><span data-stu-id="20e04-129">Column Type</span></span> | <span data-ttu-id="20e04-130">説明</span><span class="sxs-lookup"><span data-stu-id="20e04-130">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="20e04-131">モデルによって計算された生のスコア</span><span class="sxs-lookup"><span data-stu-id="20e04-131">The raw score that was calculated by the model</span></span>|
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="20e04-132">スコアの符号に基づく予測ラベル。</span><span class="sxs-lookup"><span data-stu-id="20e04-132">The predicted label, based on the sign of the score.</span></span> <span data-ttu-id="20e04-133">負のスコアは `false` にマップされ、正のスコアは `true` にマップされます。</span><span class="sxs-lookup"><span data-stu-id="20e04-133">A negative score maps to `false` and a positive score maps to `true`.</span></span>|

## <a name="multiclass-classification"></a><span data-ttu-id="20e04-134">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="20e04-134">Multiclass classification</span></span>

<span data-ttu-id="20e04-135">データのインスタンスのクラス (カテゴリ) を予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="20e04-135">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="20e04-136">分類アルゴリズムの入力は、ラベル付けされた一連のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="20e04-136">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="20e04-137">各ラベルは、通常、テキストとして開始されます。</span><span class="sxs-lookup"><span data-stu-id="20e04-137">Each label normally starts as text.</span></span> <span data-ttu-id="20e04-138">その後、TermTransform を経由してキー (数値) 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="20e04-138">It is then run through the TermTransform, which converts it to the Key (numeric) type.</span></span> <span data-ttu-id="20e04-139">分類アルゴリズムの出力は分類子であり、ラベルのない新しいインスタンスのクラスを予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="20e04-139">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="20e04-140">多クラス分類のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="20e04-140">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="20e04-141">"シベリアン ハスキー"、"ゴールデン レトリバー"、"プードル" などの犬種を特定する。</span><span class="sxs-lookup"><span data-stu-id="20e04-141">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="20e04-142">映画のレビューが "肯定的"、"中立"、"否定的" のどれかを理解する。</span><span class="sxs-lookup"><span data-stu-id="20e04-142">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="20e04-143">ホテルのレビューを "立地"、"価格"、"清潔さ" などに分類する。</span><span class="sxs-lookup"><span data-stu-id="20e04-143">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="20e04-144">詳しくは、Wikipedia の[多クラス分類](https://en.wikipedia.org/wiki/Multiclass_classification)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20e04-144">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

>[!NOTE]
><span data-ttu-id="20e04-145">一対全では、多クラス データセットに対して機能するように[二項分類学習器](#binary-classification)がアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="20e04-145">One vs all upgrades any [binary classification learner](#binary-classification) to act on multiclass datasets.</span></span> <span data-ttu-id="20e04-146">詳細については、[Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest) ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20e04-146">More information on [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).</span></span>

### <a name="multiclass-classification-trainers"></a><span data-ttu-id="20e04-147">多クラス分類トレーナー</span><span class="sxs-lookup"><span data-stu-id="20e04-147">Multiclass classification trainers</span></span>

<span data-ttu-id="20e04-148">次のトレーニング アルゴリズムを使用して多クラス分類モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="20e04-148">You can train a multiclass classification model using the following training algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

### <a name="multiclass-classification-inputs-and-outputs"></a><span data-ttu-id="20e04-149">多クラス分類の入力と出力</span><span class="sxs-lookup"><span data-stu-id="20e04-149">Multiclass classification inputs and outputs</span></span>

<span data-ttu-id="20e04-150">入力ラベル列データは[キー](xref:Microsoft.ML.Data.KeyDataViewType)型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-150">The input label column data must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>
<span data-ttu-id="20e04-151">特徴列は、<xref:System.Single> の固定サイズ ベクターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-151">The feature column must be a fixed size vector of <xref:System.Single>.</span></span>

<span data-ttu-id="20e04-152">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20e04-152">This trainer outputs the following:</span></span>

| <span data-ttu-id="20e04-153">出力の名前</span><span class="sxs-lookup"><span data-stu-id="20e04-153">Output Name</span></span> | <span data-ttu-id="20e04-154">種類</span><span class="sxs-lookup"><span data-stu-id="20e04-154">Type</span></span> | <span data-ttu-id="20e04-155">説明</span><span class="sxs-lookup"><span data-stu-id="20e04-155">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="20e04-156"><xref:System.Single> のベクター</span><span class="sxs-lookup"><span data-stu-id="20e04-156">Vector of <xref:System.Single></span></span> | <span data-ttu-id="20e04-157">すべてのクラスのスコア。</span><span class="sxs-lookup"><span data-stu-id="20e04-157">The scores of all classes.</span></span> <span data-ttu-id="20e04-158">値が大きいほど、関連するクラスに分類される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="20e04-158">Higher value means higher probability to fall into the associated class.</span></span> <span data-ttu-id="20e04-159">i 番目の要素が最大値の場合、予測ラベル インデックスは i になります。</span><span class="sxs-lookup"><span data-stu-id="20e04-159">If the i-th element has the largest value, the predicted label index would be i.</span></span> <span data-ttu-id="20e04-160">i はゼロベースのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="20e04-160">Note that i is zero-based index.</span></span> |
| `PredictedLabel` | <span data-ttu-id="20e04-161">[キー](xref:Microsoft.ML.Data.KeyDataViewType)型</span><span class="sxs-lookup"><span data-stu-id="20e04-161">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="20e04-162">予測ラベルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="20e04-162">The predicted label's index.</span></span> <span data-ttu-id="20e04-163">その値が i の場合、実際のラベルはキーと値の入力ラベルの型の i 番目のカテゴリになります。</span><span class="sxs-lookup"><span data-stu-id="20e04-163">If its value is i, the actual label would be the i-th category in the key-valued input label type.</span></span> |

## <a name="regression"></a><span data-ttu-id="20e04-164">回帰</span><span class="sxs-lookup"><span data-stu-id="20e04-164">Regression</span></span>

<span data-ttu-id="20e04-165">関連する一連の特徴からラベルの値を予測するために使用する[教師あり機械学習](glossary.md#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="20e04-165">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="20e04-166">ラベルには任意の実際の値を使用できます。分類タスクのように有限の値のセットから取得するものではありません。</span><span class="sxs-lookup"><span data-stu-id="20e04-166">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="20e04-167">回帰アルゴリズムでは、ラベルに関連する特徴におけるラベルの依存関係をモデル化して、特徴の値が変化するとラベルがどのように変化するかを判断します。</span><span class="sxs-lookup"><span data-stu-id="20e04-167">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="20e04-168">回帰アルゴリズムの入力は、既知の値のラベルが付いた一連のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="20e04-168">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="20e04-169">回帰アルゴリズムの出力は関数であり、新しい入力特徴のセットのラベル値を予測するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="20e04-169">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="20e04-170">回帰のシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="20e04-170">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="20e04-171">住宅の属性 (寝室数、立地、規模など) に基づいて住宅価格を予測する。</span><span class="sxs-lookup"><span data-stu-id="20e04-171">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="20e04-172">履歴データと現在の市場動向に基づいて将来の株価を予測する。</span><span class="sxs-lookup"><span data-stu-id="20e04-172">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="20e04-173">広告予算に基づいて製品の売り上げを予測する。</span><span class="sxs-lookup"><span data-stu-id="20e04-173">Predicting sales of a product based on advertising budgets.</span></span>

### <a name="regression-trainers"></a><span data-ttu-id="20e04-174">回帰トレーナー</span><span class="sxs-lookup"><span data-stu-id="20e04-174">Regression trainers</span></span>

<span data-ttu-id="20e04-175">次のアルゴリズムを使用して回帰モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="20e04-175">You can train a regression model using the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a><span data-ttu-id="20e04-176">回帰の入力と出力</span><span class="sxs-lookup"><span data-stu-id="20e04-176">Regression inputs and outputs</span></span>

<span data-ttu-id="20e04-177">入力ラベル列データは <xref:System.Single> にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-177">The input label column data must be <xref:System.Single>.</span></span>

<span data-ttu-id="20e04-178">このタスクのトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20e04-178">The trainers for this task output the following:</span></span>

| <span data-ttu-id="20e04-179">出力の名前</span><span class="sxs-lookup"><span data-stu-id="20e04-179">Output Name</span></span> | <span data-ttu-id="20e04-180">種類</span><span class="sxs-lookup"><span data-stu-id="20e04-180">Type</span></span> | <span data-ttu-id="20e04-181">説明</span><span class="sxs-lookup"><span data-stu-id="20e04-181">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="20e04-182">モデルによって予測された生のスコア</span><span class="sxs-lookup"><span data-stu-id="20e04-182">The raw score that was predicted by the model</span></span> |

## <a name="clustering"></a><span data-ttu-id="20e04-183">クラスタリング</span><span class="sxs-lookup"><span data-stu-id="20e04-183">Clustering</span></span>

<span data-ttu-id="20e04-184">データのインスタンスを、同様の特性を持つクラスタにグループ化するために使用する[教師なし機械学習](glossary.md#unsupervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="20e04-184">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="20e04-185">また、閲覧や単純な観測では論理的に導き出せない可能性のあるデータ セットにおける関係をクラスタリングを使用して識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="20e04-185">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="20e04-186">クラスタリング アルゴリズムの入力と出力は、選択した方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="20e04-186">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="20e04-187">分布、重心、結合性、または密度に基づくアプローチを利用できます。</span><span class="sxs-lookup"><span data-stu-id="20e04-187">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="20e04-188">現在、ML.NET では、K 平均法によるクラスタリングを使用した重心に基づくアプローチをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="20e04-188">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="20e04-189">クラスタリングのシナリオの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="20e04-189">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="20e04-190">ホテル選択の傾向と特性に基づいてホテルの宿泊客のセグメントを理解する。</span><span class="sxs-lookup"><span data-stu-id="20e04-190">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="20e04-191">対象を絞った広告キャンペーンの構築に役立つ顧客セグメントと統計データを特定する。</span><span class="sxs-lookup"><span data-stu-id="20e04-191">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="20e04-192">製造メトリックに基づいてインベントリを分類する。</span><span class="sxs-lookup"><span data-stu-id="20e04-192">Categorizing inventory based on manufacturing metrics.</span></span>

### <a name="clustering-trainer"></a><span data-ttu-id="20e04-193">クラスタリング トレーナー</span><span class="sxs-lookup"><span data-stu-id="20e04-193">Clustering trainer</span></span>

<span data-ttu-id="20e04-194">次のアルゴリズムを使用してクラスタリング モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="20e04-194">You can train a clustering model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

### <a name="clustering-inputs-and-outputs"></a><span data-ttu-id="20e04-195">入力と出力のクラスタリング</span><span class="sxs-lookup"><span data-stu-id="20e04-195">Clustering inputs and outputs</span></span>

<span data-ttu-id="20e04-196">入力特徴データは <xref:System.Single> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-196">The input features data must be <xref:System.Single>.</span></span> <span data-ttu-id="20e04-197">ラベルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="20e04-197">No labels are needed.</span></span>

<span data-ttu-id="20e04-198">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20e04-198">This trainer outputs the following:</span></span>

| <span data-ttu-id="20e04-199">出力の名前</span><span class="sxs-lookup"><span data-stu-id="20e04-199">Output Name</span></span> | <span data-ttu-id="20e04-200">種類</span><span class="sxs-lookup"><span data-stu-id="20e04-200">Type</span></span> | <span data-ttu-id="20e04-201">説明</span><span class="sxs-lookup"><span data-stu-id="20e04-201">Description</span></span>|
| -- | -- | -- |
| `Score` | <span data-ttu-id="20e04-202"><xref:System.Single> のベクター</span><span class="sxs-lookup"><span data-stu-id="20e04-202">vector of <xref:System.Single></span></span> | <span data-ttu-id="20e04-203">与えられたデータ ポイントからすべてのクラスターの重心までの距離</span><span class="sxs-lookup"><span data-stu-id="20e04-203">The distances of the given data point to all clusters' centriods</span></span> |
| `PredictedLabel` | <span data-ttu-id="20e04-204">[キー](xref:Microsoft.ML.Data.KeyDataViewType)型</span><span class="sxs-lookup"><span data-stu-id="20e04-204">[key](xref:Microsoft.ML.Data.KeyDataViewType) type</span></span> | <span data-ttu-id="20e04-205">モデルによって予測された最も近いクラスターのインデックス。</span><span class="sxs-lookup"><span data-stu-id="20e04-205">The closest cluster's index predicted by the model.</span></span> |

## <a name="anomaly-detection"></a><span data-ttu-id="20e04-206">異常検出</span><span class="sxs-lookup"><span data-stu-id="20e04-206">Anomaly detection</span></span>

<span data-ttu-id="20e04-207">このタスクでは、主成分分析 (PCA) を使用して、異常検出モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="20e04-207">This task creates an anomaly detection model by using Principal Component Analysis (PCA).</span></span> <span data-ttu-id="20e04-208">PCA に基づく異常分析は、有効なトランザクションなどの 1 つのクラスからトレーニング データを簡単に取得できるが、対象とする異常の十分なサンプルを取得するのが難しいシナリオでモデルを構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20e04-208">PCA-Based Anomaly Detection helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies.</span></span>

<span data-ttu-id="20e04-209">機械学習における確立された手法である PCA は、データの内部構造を明らかにし、データの分散を説明するために、調査データ分析で頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="20e04-209">An established technique in machine learning, PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.</span></span> <span data-ttu-id="20e04-210">PCA は、複数の変数が含まれるデータを分析することで機能します。</span><span class="sxs-lookup"><span data-stu-id="20e04-210">PCA works by analyzing data that contains multiple variables.</span></span> <span data-ttu-id="20e04-211">変数の相関を探し、結果内の差異を最も捕らえている値の合成を決定します。</span><span class="sxs-lookup"><span data-stu-id="20e04-211">It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes.</span></span> <span data-ttu-id="20e04-212">これらの合成されたフィーチャー値を使用して、主成分と呼ばれる、よりコンパクトなフィーチャー空間が作成されます。</span><span class="sxs-lookup"><span data-stu-id="20e04-212">These combined feature values are used to create a more compact feature space called the principal components.</span></span>

<span data-ttu-id="20e04-213">異常検出には、機械学習における多くの重要なタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20e04-213">Anomaly detection encompasses many important tasks in machine learning:</span></span>

* <span data-ttu-id="20e04-214">不正な可能性があるトランザクションを識別します。</span><span class="sxs-lookup"><span data-stu-id="20e04-214">Identifying transactions that are potentially fraudulent.</span></span>
* <span data-ttu-id="20e04-215">ネットワークへの侵入が発生していることを示唆するパターンを学習します。</span><span class="sxs-lookup"><span data-stu-id="20e04-215">Learning patterns that indicate that a network intrusion has occurred.</span></span>
* <span data-ttu-id="20e04-216">患者の異常なクラスターを検出します。</span><span class="sxs-lookup"><span data-stu-id="20e04-216">Finding abnormal clusters of patients.</span></span>
* <span data-ttu-id="20e04-217">システムに入力された値をチェックします。</span><span class="sxs-lookup"><span data-stu-id="20e04-217">Checking values entered into a system.</span></span>

<span data-ttu-id="20e04-218">異常とは定義上はまれに発生するイベントであるため、モデル化するために使用する代表的なデータ サンプルを収集するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="20e04-218">Because anomalies are rare events by definition, it can be difficult to collect a representative sample of data to use for modeling.</span></span> <span data-ttu-id="20e04-219">このカテゴリに含まれるアルゴリズムは、不均衡なデータセットの使用によるモデルの構築とトレーニングという主要な課題に対処するように特別に設計されています。</span><span class="sxs-lookup"><span data-stu-id="20e04-219">The algorithms included in this category have been especially designed to address the core challenges of building and training models by using imbalanced data sets.</span></span>

### <a name="anomaly-detection-trainer"></a><span data-ttu-id="20e04-220">異常検出トレーナー</span><span class="sxs-lookup"><span data-stu-id="20e04-220">Anomaly detection trainer</span></span>

<span data-ttu-id="20e04-221">次のアルゴリズムを使用して異常検出モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="20e04-221">You can train an anomaly detection model using the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a><span data-ttu-id="20e04-222">異常検出の入力と出力</span><span class="sxs-lookup"><span data-stu-id="20e04-222">Anomaly detection inputs and outputs</span></span>

<span data-ttu-id="20e04-223">入力特徴は、<xref:System.Single> の固定サイズのベクターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-223">The input features must be a fixed-sized vector of <xref:System.Single>.</span></span>

<span data-ttu-id="20e04-224">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20e04-224">This trainer outputs the following:</span></span>

| <span data-ttu-id="20e04-225">出力の名前</span><span class="sxs-lookup"><span data-stu-id="20e04-225">Output Name</span></span> | <span data-ttu-id="20e04-226">種類</span><span class="sxs-lookup"><span data-stu-id="20e04-226">Type</span></span> | <span data-ttu-id="20e04-227">説明</span><span class="sxs-lookup"><span data-stu-id="20e04-227">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="20e04-228">異常検出モデルによって計算された、負ではない無制限のスコア</span><span class="sxs-lookup"><span data-stu-id="20e04-228">The non-negative, unbounded score that was calculated by the anomaly detection model</span></span> |
| `PredictedLabel` | <xref:System.Boolean> | <span data-ttu-id="20e04-229">入力が異常 (PredictedLabel = true) か異常でないか (PredictedLabel = false) を表す true/false 値</span><span class="sxs-lookup"><span data-stu-id="20e04-229">A true/false value representing whether the input is an anomaly (PredictedLabel=true) or not (PredictedLabel=false)</span></span> |

## <a name="ranking"></a><span data-ttu-id="20e04-230">ランキング</span><span class="sxs-lookup"><span data-stu-id="20e04-230">Ranking</span></span>

<span data-ttu-id="20e04-231">ランキング タスクでは、ラベル付きのサンプルのセットからランカーが構築されます。</span><span class="sxs-lookup"><span data-stu-id="20e04-231">A ranking task constructs a ranker from a set of labeled examples.</span></span> <span data-ttu-id="20e04-232">この例のセットは、特定の条件を使用してスコア付けできるインスタンス グループで構成されています。</span><span class="sxs-lookup"><span data-stu-id="20e04-232">This example set consists of instance groups that can be scored with a given criteria.</span></span> <span data-ttu-id="20e04-233">順位付けのラベルは、インスタンスごとに {0、1、2、3, 4} です。</span><span class="sxs-lookup"><span data-stu-id="20e04-233">The ranking labels are { 0, 1, 2, 3, 4 } for each instance.</span></span>  <span data-ttu-id="20e04-234">各インスタンスのスコアが不明である新しいインスタンス グループをランク付けするように、ランカーがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="20e04-234">The ranker is trained to rank new instance groups with unknown scores for each instance.</span></span> <span data-ttu-id="20e04-235">ML.NET のランキング学習器は、[機械が学習したランキング](https://en.wikipedia.org/wiki/Learning_to_rank)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="20e04-235">ML.NET ranking learners are [machine learned ranking](https://en.wikipedia.org/wiki/Learning_to_rank) based.</span></span>

### <a name="ranking-training-algorithms"></a><span data-ttu-id="20e04-236">ランキング トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="20e04-236">Ranking training algorithms</span></span>

<span data-ttu-id="20e04-237">次のアルゴリズムを使ってランキング モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="20e04-237">You can train a ranking model with the following algorithms:</span></span>

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>

### <a name="ranking-input-and-outputs"></a><span data-ttu-id="20e04-238">入力と出力のランキング</span><span class="sxs-lookup"><span data-stu-id="20e04-238">Ranking input and outputs</span></span>

<span data-ttu-id="20e04-239">入力ラベル データ型は[キー](xref:Microsoft.ML.Data.KeyDataViewType)型または <xref:System.Single> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-239">The input label data type must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type or <xref:System.Single>.</span></span> <span data-ttu-id="20e04-240">ラベルの値によって関連性が決まります。値が高いほど関連性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="20e04-240">The value of the label determines relevance, where higher values indicate higher relevance.</span></span> <span data-ttu-id="20e04-241">ラベルが[キー](xref:Microsoft.ML.Data.KeyDataViewType)型の場合、キーのインデックスは関連性の値です。ここで、最小のインデックスは最も低い関連性です。</span><span class="sxs-lookup"><span data-stu-id="20e04-241">If the label is a [key](xref:Microsoft.ML.Data.KeyDataViewType) type, then the key index is the relevance value, where the smallest index is the least relevant.</span></span> <span data-ttu-id="20e04-242">ラベルが <xref:System.Single> の場合、値が大きいほど関連性が高いことを示します。</span><span class="sxs-lookup"><span data-stu-id="20e04-242">If the label is a <xref:System.Single>, larger values indicate higher relevance.</span></span>

<span data-ttu-id="20e04-243">特徴データは <xref:System.Single> の固定サイズのベクターにする必要があります。また、入力行グループ列は[キー](xref:Microsoft.ML.Data.KeyDataViewType)型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e04-243">The feature data must be a fixed size vector of <xref:System.Single> and input row group column must be [key](xref:Microsoft.ML.Data.KeyDataViewType) type.</span></span>

<span data-ttu-id="20e04-244">このトレーナーの出力は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20e04-244">This trainer outputs the following:</span></span>

| <span data-ttu-id="20e04-245">出力の名前</span><span class="sxs-lookup"><span data-stu-id="20e04-245">Output Name</span></span> | <span data-ttu-id="20e04-246">種類</span><span class="sxs-lookup"><span data-stu-id="20e04-246">Type</span></span> | <span data-ttu-id="20e04-247">説明</span><span class="sxs-lookup"><span data-stu-id="20e04-247">Description</span></span>|
| -- | -- | -- |
| `Score` | <xref:System.Single> | <span data-ttu-id="20e04-248">予測を決定するためにモデルによって計算された無制限のスコア</span><span class="sxs-lookup"><span data-stu-id="20e04-248">The unbounded score that was calculated by the model to determine the prediction</span></span> |

## <a name="recommendation"></a><span data-ttu-id="20e04-249">推奨事項</span><span class="sxs-lookup"><span data-stu-id="20e04-249">Recommendation</span></span>

<span data-ttu-id="20e04-250">レコメンデーション タスクによって、推奨される製品やサービスの一覧を作成できます。</span><span class="sxs-lookup"><span data-stu-id="20e04-250">A recommendation task enables producing a list of recommended products or services.</span></span> <span data-ttu-id="20e04-251">ML.NET では、カタログ内に製品のレーティングの履歴データがある場合は、レコメンデーション用の[協調フィルタリング](https://en.wikipedia.org/wiki/Collaborative_filtering) アルゴリズムである[行列因子分解 (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="20e04-251">ML.NET uses [Matrix factorization (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), a [collaborative filtering](https://en.wikipedia.org/wiki/Collaborative_filtering) algorithm for recommendations when you have historical product rating data in your catalog.</span></span> <span data-ttu-id="20e04-252">たとえば、ユーザーによる映画の採点の履歴データがあるときに、そのユーザーが次に見たいと思う映画を推薦できます。</span><span class="sxs-lookup"><span data-stu-id="20e04-252">For example, you have historical movie rating data for your users and want to recommend  other movies they are likely to watch next.</span></span>

### <a name="recommendation-training-algorithms"></a><span data-ttu-id="20e04-253">レコメンデーション トレーニング アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="20e04-253">Recommendation training algorithms</span></span>

<span data-ttu-id="20e04-254">次のアルゴリズムを使ってレコメンデーション モデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="20e04-254">You can train a recommendation model with the following algorithm:</span></span>

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
