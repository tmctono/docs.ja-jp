---
title: .NET の機械学習に関するハウツー ガイド - ML.NET
description: カスタム AI ソリューションの作成と、.NET アプリケーションへの Machine Learning 統合を支援するための、特定のタスクを実行する方法について説明します。
ms.custom: seodec18
ms.date: 03/01/2019
ms.openlocfilehash: c8d1258629f777cd8bced47e4b956c9cf100a682
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427584"
---
# <a name="net-machine-learning-how-to-guides---mlnet"></a><span data-ttu-id="12372-103">.NET の機械学習に関するハウツー ガイド - ML.NET</span><span class="sxs-lookup"><span data-stu-id="12372-103">.NET Machine learning how-to guides - ML.NET</span></span>

<span data-ttu-id="12372-104">ML.NET ガイドの方法に関するセクションには、よく寄せられる質問に対する簡単な回答が記載されています。</span><span class="sxs-lookup"><span data-stu-id="12372-104">In the How to section of the ML.NET Guide, you can find quick answers to common questions.</span></span> <span data-ttu-id="12372-105">場合によっては、見つけやすいように、記事が複数のセクションで表示されることもあります。</span><span class="sxs-lookup"><span data-stu-id="12372-105">In some cases, articles may be listed in multiple sections to make them easy to find.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="12372-106">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="12372-106">Load the data</span></span>

* [<span data-ttu-id="12372-107">機械学習の処理のために多数の列を含むデータを CSV ファイルから読み込みます。</span><span class="sxs-lookup"><span data-stu-id="12372-107">Load data with many columns from a CSV file for machine learning processing.</span></span>](load-data-from-mult-column-csv-ml-net.md)

* [<span data-ttu-id="12372-108">機械学習の処理のために複数ファイルからデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="12372-108">Load data from multiple files for machine learning processing.</span></span>](load-data-from-multiple-files-ml-net.md)

* [<span data-ttu-id="12372-109">機械学習の処理のためにテキスト ファイルからデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="12372-109">Load data from a text file for machine learning processing.</span></span>](load-data-from-text-file-ml-net.md)

### <a name="prepare-the-data"></a><span data-ttu-id="12372-110">データを準備する</span><span class="sxs-lookup"><span data-stu-id="12372-110">Prepare the data</span></span>

* [<span data-ttu-id="12372-111">データ処理で使うためにノーマライザーでトレーニング データを前処理します。</span><span class="sxs-lookup"><span data-stu-id="12372-111">Preprocess training data with normalizers to use in data processing.</span></span>](normalizers-preprocess-data-ml-net.md)

## <a name="train-the-model"></a><span data-ttu-id="12372-112">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="12372-112">Train the model</span></span>

* [<span data-ttu-id="12372-113">テキスト ファイルではないデータを使って機械学習モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="12372-113">Train a machine learning model with data that's not in a text file.</span></span>](load-non-file-training-data-ml-net.md)

* [<span data-ttu-id="12372-114">クロス検証を使って機械学習モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="12372-114">Train a machine learning model using cross-validation.</span></span>](train-cross-validation-ml-net.md)

* [<span data-ttu-id="12372-115">ML.NET を使って値を予測する回帰モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="12372-115">Train a regression model to predict a value using ML.NET.</span></span>](train-regression-model-ml-net.md)

### <a name="evaluate-the-model-quality"></a><span data-ttu-id="12372-116">モデルの品質を評価する</span><span class="sxs-lookup"><span data-stu-id="12372-116">Evaluate the model quality</span></span>

* [<span data-ttu-id="12372-117">メトリックを計算してモデルの品質を評価します。</span><span class="sxs-lookup"><span data-stu-id="12372-117">Calculate metrics to evaluate model quality.</span></span>](verify-model-quality-ml-net.md)

### <a name="model-explainability"></a><span data-ttu-id="12372-118">モデルの説明可能性</span><span class="sxs-lookup"><span data-stu-id="12372-118">Model explainability</span></span>

* [<span data-ttu-id="12372-119">Permutation Feature Importance を使ってモデルの特徴の重要度を判断します。</span><span class="sxs-lookup"><span data-stu-id="12372-119">Determine the feature importance of models with Permutation Feature Importance.</span></span>](determine-global-feature-importance-in-model.md)

* [<span data-ttu-id="12372-120">モデルの説明可能性のために一般化加法モデルと形状関数を使います。</span><span class="sxs-lookup"><span data-stu-id="12372-120">Use Generalized Additive Models and shape functions for model explainability.</span></span>](use-gams-for-model-explainability.md)

### <a name="feature-engineering"></a><span data-ttu-id="12372-121">特徴エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="12372-121">Feature engineering</span></span>

* [<span data-ttu-id="12372-122">カテゴリ データに対するモデル トレーニングに特徴エンジニアリングを適用します。</span><span class="sxs-lookup"><span data-stu-id="12372-122">Apply feature engineering for model training on categorical data.</span></span>](train-model-categorical-ml-net.md)

* [<span data-ttu-id="12372-123">ML.NET を使ってテキスト データに対するモデル トレーニングに特徴エンジニアリングを適用します。</span><span class="sxs-lookup"><span data-stu-id="12372-123">Apply feature engineering for model training on textual data with ML.NET.</span></span>](train-model-textual-ml-net.md)

## <a name="run"></a><span data-ttu-id="12372-124">実行</span><span class="sxs-lookup"><span data-stu-id="12372-124">Run</span></span>

* [<span data-ttu-id="12372-125">ML.NET パイプライン処理中の中間データ値を検査します。</span><span class="sxs-lookup"><span data-stu-id="12372-125">Inspect intermediate data values during ML.NET pipeline processing.</span></span>](inspect-intermediate-data-ml-net.md)

* [<span data-ttu-id="12372-126">トレーニング済みの機械学習モデルをアプリで運用化します。</span><span class="sxs-lookup"><span data-stu-id="12372-126">Operationalize a trained machine learning model in apps.</span></span>](consuming-model-ml-net.md)

* [<span data-ttu-id="12372-127">PredictionFunction を使って一度に 1 つの予測を行います。</span><span class="sxs-lookup"><span data-stu-id="12372-127">Use the PredictionFunction to make one prediction at a time.</span></span>](single-predict-model-ml-net.md)

## <a name="probabilistic-infernet"></a><span data-ttu-id="12372-128">確率論的 (Infer.NET)</span><span class="sxs-lookup"><span data-stu-id="12372-128">Probabilistic (Infer.NET)</span></span>

* [<span data-ttu-id="12372-129">Infer.NET と確率論的プログラミングでゲーム対戦リスト アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="12372-129">Create a game match up list app with Infer.NET and probabilistic programming.</span></span>](matchup-app-infer-net.md)