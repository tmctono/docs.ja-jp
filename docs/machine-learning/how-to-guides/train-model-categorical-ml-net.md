---
title: カテゴリ データに対するモデル トレーニングに特徴エンジニアリングを適用する - ML.NET
description: ML.NET でカテゴリ データに対する機械学習モデル トレーニングに特徴エンジニアリングを適用する方法を説明します。
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: c8e7a6f2429dd5ceda065332770e0ba3af374143
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677280"
---
# <a name="apply-feature-engineering-for-model-training-on-categorical-data---mlnet"></a><span data-ttu-id="3b365-103">カテゴリ データに対するモデル トレーニングに特徴エンジニアリングを適用する - ML.NET</span><span class="sxs-lookup"><span data-stu-id="3b365-103">Apply feature engineering for model training on categorical data - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="3b365-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b365-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="3b365-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b365-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="3b365-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="3b365-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="3b365-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b365-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="3b365-108">すべての ML.NET `learners` は `float vector` 型の特徴を想定しているため、float 以外のデータはすべて `float` データ型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b365-108">You need to convert any non float data to `float` data types since all ML.NET `learners` expect features as a `float vector`.</span></span>

<span data-ttu-id="3b365-109">データセットに `categorical` データ (たとえば、"enum") が含まれる場合、特徴に変換するいくつかの方法が ML.NET によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="3b365-109">If the dataset contains `categorical` data (for example, 'enum'), ML.NET offers several ways of converting it to features:</span></span>

- <span data-ttu-id="3b365-110">one-hot エンコード</span><span class="sxs-lookup"><span data-stu-id="3b365-110">One-hot encoding</span></span>
- <span data-ttu-id="3b365-111">ハッシュベース one-hot エンコード</span><span class="sxs-lookup"><span data-stu-id="3b365-111">Hash-based one-hot encoding</span></span>
- <span data-ttu-id="3b365-112">バイナリ エンコード (カテゴリ インデックスをビット シーケンスに変換してビットを特徴として使用)</span><span class="sxs-lookup"><span data-stu-id="3b365-112">Binary encoding (convert category index into a bit sequence and use bits as features)</span></span>

<span data-ttu-id="3b365-113">一部のカテゴリのカーディナリティが非常に高い (異なる値が多く、通常はごく一部の組み合わせしか発生しない) 場合、`one-hot encoding` は無駄になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b365-113">A `one-hot encoding` can be wasteful if some categories are very high-cardinality (lots of different values, with a small set commonly occurring.</span></span> <span data-ttu-id="3b365-114">その場合には、スロット数を減らして、件数ベースの特徴選択を使用してエンコーディングします。</span><span class="sxs-lookup"><span data-stu-id="3b365-114">In that case, reduce the number of slots to encode with count-based feature selection.</span></span>

<span data-ttu-id="3b365-115">カテゴリの特徴付けを ML.NET 学習パイプラインに組み込んで、次のようにカテゴリ変換を行うようにします。</span><span class="sxs-lookup"><span data-stu-id="3b365-115">Include categorical featurization directly in the ML.NET learning pipeline to ensure that the categorical transformation:</span></span>

- <span data-ttu-id="3b365-116">テスト データではなく、トレーニング データに対してのみトレーニングする。</span><span class="sxs-lookup"><span data-stu-id="3b365-116">is only 'trained' on the training data, and not on your test data,</span></span>
- <span data-ttu-id="3b365-117">予測時に余計な前処理を行うことなく、受信データに正しく適用する。</span><span class="sxs-lookup"><span data-stu-id="3b365-117">is correctly applied to new incoming data, without extra pre-processing at prediction time.</span></span>

<span data-ttu-id="3b365-118">次の例では、[成人国勢調査データセット](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt)のカテゴリ処理を示します。</span><span class="sxs-lookup"><span data-stu-id="3b365-118">The following example illustrates categorical handling for the [adult census dataset](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span></span>

```console
Label   Workclass   education   marital-status  occupation  relationship    ethnicity   sex native-country-region   age fnlwgt  education-num   capital-gain    capital-loss    hours-per-week
0   Private 11th    Never-married   Machine-op-inspct   Own-child   Black   Male    United-States   25  226802  7   0   0   40
0   Private HS-grad Married-civ-spouse  Farming-fishing Husband White   Male    United-States   38  89814   9   0   0   50
1   Local-gov   Assoc-acdm  Married-civ-spouse  Protective-serv Husband White   Male    United-States   28  336951  12  0   0   40
1   Private Some-college    Married-civ-spouse  Machine-op-inspct   Husband Black   Male    United-States   44  160323  10  7688    0   40
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(new[] 
    {
        new TextLoader.Column("Label", DataKind.BL, 0),
        // We will load all the categorical features into one vector column of size 8.
        new TextLoader.Column("CategoricalFeatures", DataKind.TX, 1, 8),
        // Similarly, load all numerical features into one vector of size 6.
        new TextLoader.Column("NumericalFeatures", DataKind.R4, 9, 14),
        // Let's also separately load the 'Workclass' column.
        new TextLoader.Column("Workclass", DataKind.TX, 1),
    },
    hasHeader: true
);

// Read the data.
var data = reader.Read(dataPath);

// Inspect the first 10 records of the categorical columns to check that they are correctly read.
var catColumns = data.GetColumn<string[]>(mlContext, "CategoricalFeatures").Take(10).ToArray();

// Build several alternative featurization pipelines.
var pipeline =
    // Convert each categorical feature into one-hot encoding independently.
    mlContext.Transforms.Categorical.OneHotEncoding("CategoricalFeatures", "CategoricalOneHot")
        // Convert all categorical features into indices, and build a 'word bag' of these.
        .Append(mlContext.Transforms.Categorical.OneHotEncoding("CategoricalFeatures", "CategoricalBag",OneHotEncodingTransformer.OutputKind.Bag))
        // One-hot encode the workclass column, then drop all the categories that have fewer than 10 instances in the train set.
        .Append(mlContext.Transforms.Categorical.OneHotEncoding("Workclass", "WorkclassOneHot"))
        .Append(mlContext.Transforms.FeatureSelection.SelectFeaturesBasedOnCount("WorkclassOneHot", "WorkclassOneHotTrimmed", count: 10));

// Let's train our pipeline, and then apply it to the same data.
var transformedData = pipeline.Fit(data).Transform(data);

// Inspect some columns of the resulting dataset.
var categoricalBags = transformedData.GetColumn<float[]>(mlContext, "CategoricalBag").Take(10).ToArray();
var workclasses = transformedData.GetColumn<float[]>(mlContext, "WorkclassOneHotTrimmed").Take(10).ToArray();

// Of course, if we want to train the model, we will need to compose a single float vector of all the features.
// Here's how we could do this:

var fullLearningPipeline = pipeline
    // Concatenate two of the 3 categorical pipelines, and the numeric features.
    .Append(mlContext.Transforms.Concatenate("Features", "NumericalFeatures", "CategoricalBag", "WorkclassOneHotTrimmed"))
    // Cache data in memory so that the following trainer will be able to access training examples without
    // reading them from disk multiple times.
    .AppendCacheCheckpoint(mlContext)
    // Now we're ready to train. We chose our FastTree trainer for this classification task.
    .Append(mlContext.BinaryClassification.Trainers.FastTree(numTrees: 50));

// Train the model.
var model = fullLearningPipeline.Fit(data);
```
