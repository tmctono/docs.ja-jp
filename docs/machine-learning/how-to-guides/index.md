---
title: ML.NET 使い方ガイド
description: カスタム AI ソリューションの作成と、.NET アプリケーションへの Machine Learning 統合を支援するための、特定のタスクを実行する方法について説明します。
ms.date: 03/01/2019
ms.openlocfilehash: 4ce2de77c35062aa19449e3ba6bb3d5abd003d60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715665"
---
# <a name="net-machine-learning-how-to-guides"></a><span data-ttu-id="c54f2-103">.NET の機械学習に関するハウツー ガイド</span><span class="sxs-lookup"><span data-stu-id="c54f2-103">.NET Machine learning how-to guides</span></span>

<span data-ttu-id="c54f2-104">ML.NET ガイドの方法に関するセクションには、よく寄せられる質問に対する簡単な回答が記載されています。</span><span class="sxs-lookup"><span data-stu-id="c54f2-104">In the How to section of the ML.NET Guide, you can find quick answers to common questions.</span></span> <span data-ttu-id="c54f2-105">場合によっては、見つけやすいように、記事が複数のセクションで表示されることもあります。</span><span class="sxs-lookup"><span data-stu-id="c54f2-105">In some cases, articles may be listed in multiple sections to make them easy to find.</span></span>

## <a name="load-data"></a><span data-ttu-id="c54f2-106">データの読み込み</span><span class="sxs-lookup"><span data-stu-id="c54f2-106">Load data</span></span>

* [<span data-ttu-id="c54f2-107">ファイルと SQL データベースからデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c54f2-107">Load data from files and SQL databases.</span></span>](load-data-ml-net.md)

### <a name="prepare-the-data"></a><span data-ttu-id="c54f2-108">データを準備する</span><span class="sxs-lookup"><span data-stu-id="c54f2-108">Prepare the data</span></span>

* [<span data-ttu-id="c54f2-109">データ処理で使うためにノーマライザーでトレーニング データを前処理します。</span><span class="sxs-lookup"><span data-stu-id="c54f2-109">Preprocess training data with normalizers to use in data processing.</span></span>](normalizers-preprocess-data-ml-net.md)

## <a name="train-the-model"></a><span data-ttu-id="c54f2-110">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="c54f2-110">Train the model</span></span>

* [<span data-ttu-id="c54f2-111">クロス検証を使って機械学習モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="c54f2-111">Train a machine learning model using cross-validation.</span></span>](train-machine-learning-model-cross-validation-ml-net.md)

* [<span data-ttu-id="c54f2-112">ML.NET を使って値を予測する回帰モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="c54f2-112">Train a regression model to predict a value using ML.NET.</span></span>](train-machine-learning-model-ml-net.md)

### <a name="evaluate-the-model-quality"></a><span data-ttu-id="c54f2-113">モデルの品質を評価する</span><span class="sxs-lookup"><span data-stu-id="c54f2-113">Evaluate the model quality</span></span>

* [<span data-ttu-id="c54f2-114">メトリックを計算してモデルの品質を評価します。</span><span class="sxs-lookup"><span data-stu-id="c54f2-114">Calculate metrics to evaluate model quality.</span></span>](verify-model-quality-ml-net.md)

### <a name="model-explainability"></a><span data-ttu-id="c54f2-115">モデル説明</span><span class="sxs-lookup"><span data-stu-id="c54f2-115">Model explainability</span></span>

* [<span data-ttu-id="c54f2-116">Permutation Feature Importance を使ってモデルの特徴の重要度を判断します。</span><span class="sxs-lookup"><span data-stu-id="c54f2-116">Determine the feature importance of models with Permutation Feature Importance.</span></span>](explain-machine-learning-model-permutation-feature-importance-ml-net.md)

* [<span data-ttu-id="c54f2-117">モデルの説明可能性のために一般化加法モデルと形状関数を使います。</span><span class="sxs-lookup"><span data-stu-id="c54f2-117">Use Generalized Additive Models and shape functions for model explainability.</span></span>](use-gams-for-model-explainability.md)

## <a name="run"></a><span data-ttu-id="c54f2-118">ラン</span><span class="sxs-lookup"><span data-stu-id="c54f2-118">Run</span></span>

* [<span data-ttu-id="c54f2-119">ML.NET パイプライン処理中の中間データ値を検査します。</span><span class="sxs-lookup"><span data-stu-id="c54f2-119">Inspect intermediate data values during ML.NET pipeline processing.</span></span>](inspect-intermediate-data-ml-net.md)

* [<span data-ttu-id="c54f2-120">トレーニングされた機械学習モデルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c54f2-120">Load a trained machine learning model.</span></span>](save-load-machine-learning-models-ml-net.md)

* [<span data-ttu-id="c54f2-121">トレーニングされたモデルを使用して予測を行います。</span><span class="sxs-lookup"><span data-stu-id="c54f2-121">Make predictions with a trained model.</span></span>](machine-learning-model-predictions-ml-net.md)

## <a name="probabilistic-infernet"></a><span data-ttu-id="c54f2-122">確率論的 (Infer.NET)</span><span class="sxs-lookup"><span data-stu-id="c54f2-122">Probabilistic (Infer.NET)</span></span>

* [<span data-ttu-id="c54f2-123">Infer.NET と確率論的プログラミングでゲーム対戦リスト アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c54f2-123">Create a game match up list app with Infer.NET and probabilistic programming.</span></span>](matchup-app-infer-net.md)
