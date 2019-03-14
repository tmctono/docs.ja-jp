---
title: データ処理に使用するトレーニング データのノーマライザーによる前処理 - ML.NET
description: ML.NET で機械学習モデルの構築、トレーニング、スコア付けに使用するトレーニング データを、ノーマライザーを使用して前処理する方法について説明します
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2d18f7c19a51fd929ac6efb7f600cb1ac2733de8
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676604"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a><span data-ttu-id="f8274-103">データ処理に使用するトレーニング データのノーマライザーによる前処理 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="f8274-103">Preprocess training data with normalizers to use in data processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="f8274-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f8274-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="f8274-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8274-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="f8274-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="f8274-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="f8274-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8274-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="f8274-108">ML.NET には、多数の[パラメトリック アルゴリズムと非パラメトリック アルゴリズム](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/)が公開されています。</span><span class="sxs-lookup"><span data-stu-id="f8274-108">ML.NET exposes a number of [parametric and non-parametric algorithms](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span></span>

<span data-ttu-id="f8274-109">線形モデルや他のパラメトリック モデルのトレーニング時にノーマライザーを**使用する**ことは重要ですが、どのノーマライザーを選択するかはそれほど**重要ではありません**。</span><span class="sxs-lookup"><span data-stu-id="f8274-109">It's **not** as important which normalizer you choose as it is to **use** a normalizer when training linear or other parametric models.</span></span>

<span data-ttu-id="f8274-110">ノーマライザーは常に ML.NET の学習パイプラインに直接含めてください。その目的は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f8274-110">Always include the normalizer directly in the ML.NET learning pipeline, so it:</span></span>

- <span data-ttu-id="f8274-111">テスト データではなく、トレーニング データに対してのみトレーニングする。</span><span class="sxs-lookup"><span data-stu-id="f8274-111">is only trained on the training data, and not on your test data,</span></span>
- <span data-ttu-id="f8274-112">予測時に余計な前処理を行うことなく、すべての新しい受信データに正しく適用する。</span><span class="sxs-lookup"><span data-stu-id="f8274-112">is correctly applied to all the new incoming data, without the need for extra pre-processing at prediction time.</span></span>

<span data-ttu-id="f8274-113">次の例は、学習パイプラインの正規化方法を示すコード スニペットです。</span><span class="sxs-lookup"><span data-stu-id="f8274-113">Here's a snippet of code that demonstrates normalization in learning pipelines.</span></span> <span data-ttu-id="f8274-114">Iris データセットを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f8274-114">It assumes the Iris dataset:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features",DataKind.R4,0,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has comma.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
            new NormalizingEstimator.MinMaxColumn(inputColumnName:"Features", outputColumnName:"MinMaxNormalized", fixZero: true),
            new NormalizingEstimator.MeanVarColumn(inputColumnName: "Features", outputColumnName: "MeanVarNormalized", fixZero: true),
            new NormalizingEstimator.BinningColumn(inputColumnName: "Features", outputColumnName: "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
