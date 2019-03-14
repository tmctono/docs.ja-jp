---
title: ML.NET を使って値を予測する回帰モデルをトレーニングする
description: ML.NET を使って値を予測する機械学習回帰モデルをトレーニングする方法を説明します。
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: e7ea07471e155804a7ad36481aa469beda7028ae
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673146"
---
# <a name="train-a-regression-model-to-predict-a-value-using-mlnet"></a><span data-ttu-id="84048-103">ML.NET を使って値を予測する回帰モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="84048-103">Train a regression model to predict a value using ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="84048-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="84048-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="84048-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84048-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="84048-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="84048-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="84048-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84048-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="84048-108">通常、ML.NET でのモデルのトレーニングには 3 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="84048-108">Generally, there are three steps for model training in ML.NET:</span></span>

1. <span data-ttu-id="84048-109">`IDataView` の形式でトレーニング データを取得する。</span><span class="sxs-lookup"><span data-stu-id="84048-109">Get the training data in a form of an `IDataView`</span></span>
2. <span data-ttu-id="84048-110">基本の "演算子" のシーケンスとして "学習パイプライン" (推定器) を構築する。</span><span class="sxs-lookup"><span data-stu-id="84048-110">Build the 'learning pipeline' as a sequence of elementary 'operators' (estimators).</span></span>
3. <span data-ttu-id="84048-111">パイプライン上で `Fit` を呼び出して、トレーニングされたモデルを取得する。</span><span class="sxs-lookup"><span data-stu-id="84048-111">Call `Fit` on the pipeline to obtain the trained model.</span></span>

<span data-ttu-id="84048-112">この[例のファイル](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv)では、予測されたラベル (`target`) は最後の列 (12 番目) であり、それ以外すべては特徴です。</span><span class="sxs-lookup"><span data-stu-id="84048-112">In this [Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv),the predicted label (`target`) is the last column (12th) and all the rest are features:</span></span>

```console
feature_0;feature_1;feature_2;feature_3;feature_4;feature_5;feature_6;feature_7;feature_8;feature_9;feature_10;target
-2.75;0.77;-0.61;0.14;1.39;0.38;-0.53;-0.50;-2.13;-0.39;0.46;140.66
-0.61;-0.37;-0.12;0.55;-1.00;0.84;-0.02;1.30;-0.24;-0.50;-2.12;148.12
-0.85;-0.91;1.81;0.02;-0.78;-1.41;-1.09;-0.65;0.90;-0.37;-0.22;402.20
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.

// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
        columns: new TextLoader.Column[]
        {
            // We read the first 11 values as a single float vector.
            new TextLoader.Column("FeatureVector",DataKind.R4,0,10),
            // Separately, read the target variable.
            new TextLoader.Column("Target",DataKind.R4,11)
        },
        // Default separator is tab, but the dataset has semicolon.
        separatorChar: ';',
        // First line of the file is a header, not a data row.
        hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var trainData = reader.Read(dataPath);

// Step two: define the learning pipeline.

// We 'start' the pipeline with the output of the reader.
var pipeline =
        // First 'normalize' the data (rescale to be
        // between -1 and 1 for all examples)
        mlContext.Transforms.Normalize("FeatureVector")
        // Cache data in memory so that SDCA trainer will be able to randomly access training examples without
        // reading data from disk multiple times. Data will be cached at its first use in any downstream step.
        // Notice that unused part in the data may not be cached.
        .AppendCacheCheckpoint(mlContext)
        // First 'normalize' the data (rescale to be
        // between -1 and 1 for all examples)
        .Append(mlContext.Regression.Trainers.StochasticDualCoordinateAscent("Target", "FeatureVector"));

// Step three. Fit the pipeline to the training data.
var model = pipeline.Fit(trainData);
```