---
title: ML.NET 使い方ガイド
description: カスタム AI ソリューションの作成と、.NET アプリケーションへの Machine Learning 統合を支援するための、特定のタスクを実行する方法について説明します。
ms.custom: seodec18
ms.date: 03/01/2019
ms.openlocfilehash: e2b4ff77c7f76282d70c06b5ef534306fe4e93a6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977111"
---
# <a name="net-machine-learning-how-to-guides"></a><span data-ttu-id="ae107-103">.NET の機械学習に関するハウツー ガイド</span><span class="sxs-lookup"><span data-stu-id="ae107-103">.NET Machine learning how-to guides</span></span>

<span data-ttu-id="ae107-104">ML.NET ガイドの方法に関するセクションには、よく寄せられる質問に対する簡単な回答が記載されています。</span><span class="sxs-lookup"><span data-stu-id="ae107-104">In the How to section of the ML.NET Guide, you can find quick answers to common questions.</span></span> <span data-ttu-id="ae107-105">場合によっては、見つけやすいように、記事が複数のセクションで表示されることもあります。</span><span class="sxs-lookup"><span data-stu-id="ae107-105">In some cases, articles may be listed in multiple sections to make them easy to find.</span></span>

## <a name="load-data"></a><span data-ttu-id="ae107-106">データの読み込み</span><span class="sxs-lookup"><span data-stu-id="ae107-106">Load data</span></span>

* [<span data-ttu-id="ae107-107">ファイルと SQL データベースからデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ae107-107">Load data from files and SQL databases.</span></span>](load-data-ml-net.md)

### <a name="prepare-the-data"></a><span data-ttu-id="ae107-108">データを準備する</span><span class="sxs-lookup"><span data-stu-id="ae107-108">Prepare the data</span></span>

* [<span data-ttu-id="ae107-109">データ処理で使うためにノーマライザーでトレーニング データを前処理します。</span><span class="sxs-lookup"><span data-stu-id="ae107-109">Preprocess training data with normalizers to use in data processing.</span></span>](normalizers-preprocess-data-ml-net.md)

## <a name="train-the-model"></a><span data-ttu-id="ae107-110">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="ae107-110">Train the model</span></span>

* [<span data-ttu-id="ae107-111">クロス検証を使って機械学習モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="ae107-111">Train a machine learning model using cross-validation.</span></span>](train-machine-learning-model-cross-validation-ml-net.md)

* [<span data-ttu-id="ae107-112">ML.NET を使って値を予測する回帰モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="ae107-112">Train a regression model to predict a value using ML.NET.</span></span>](train-machine-learning-model-ml-net.md)

### <a name="evaluate-the-model-quality"></a><span data-ttu-id="ae107-113">モデルの品質を評価する</span><span class="sxs-lookup"><span data-stu-id="ae107-113">Evaluate the model quality</span></span>

* [<span data-ttu-id="ae107-114">メトリックを計算してモデルの品質を評価します。</span><span class="sxs-lookup"><span data-stu-id="ae107-114">Calculate metrics to evaluate model quality.</span></span>](verify-model-quality-ml-net.md)

### <a name="model-explainability"></a><span data-ttu-id="ae107-115">モデルの説明可能性</span><span class="sxs-lookup"><span data-stu-id="ae107-115">Model explainability</span></span>

* [<span data-ttu-id="ae107-116">Permutation Feature Importance を使ってモデルの特徴の重要度を判断します。</span><span class="sxs-lookup"><span data-stu-id="ae107-116">Determine the feature importance of models with Permutation Feature Importance.</span></span>](explain-machine-learning-model-permutation-feature-importance-ml-net.md)

* [<span data-ttu-id="ae107-117">モデルの説明可能性のために一般化加法モデルと形状関数を使います。</span><span class="sxs-lookup"><span data-stu-id="ae107-117">Use Generalized Additive Models and shape functions for model explainability.</span></span>](use-gams-for-model-explainability.md)

## <a name="run"></a><span data-ttu-id="ae107-118">実行</span><span class="sxs-lookup"><span data-stu-id="ae107-118">Run</span></span>

* [<span data-ttu-id="ae107-119">ML.NET パイプライン処理中の中間データ値を検査します。</span><span class="sxs-lookup"><span data-stu-id="ae107-119">Inspect intermediate data values during ML.NET pipeline processing.</span></span>](inspect-intermediate-data-ml-net.md)

* [<span data-ttu-id="ae107-120">トレーニングされた機械学習モデルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ae107-120">Load a trained machine learning model.</span></span>](save-load-machine-learning-models-ml-net.md)

* [<span data-ttu-id="ae107-121">トレーニングされたモデルを使用して予測を行います。</span><span class="sxs-lookup"><span data-stu-id="ae107-121">Make predictions with a trained model.</span></span>](machine-learning-model-predictions-ml-net.md)

## <a name="probabilistic-infernet"></a><span data-ttu-id="ae107-122">確率論的 (Infer.NET)</span><span class="sxs-lookup"><span data-stu-id="ae107-122">Probabilistic (Infer.NET)</span></span>

* [<span data-ttu-id="ae107-123">Infer.NET と確率論的プログラミングでゲーム対戦リスト アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae107-123">Create a game match up list app with Infer.NET and probabilistic programming.</span></span>](matchup-app-infer-net.md)
