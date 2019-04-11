---
title: ML.NET コンテンツ ガイド
description: ML.NET を使用してカスタム AI ソリューションを構築し、これを .NET アプリケーションに統合する方法について説明します。
ms.date: 04/05/2019
ms.custom: seodec18
ms.openlocfilehash: de681daea5a29a121d350271ced4ccc2c0b1b533
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231332"
---
# <a name="mlnet-content-guide"></a><span data-ttu-id="12fc0-103">ML.NET コンテンツ ガイド</span><span class="sxs-lookup"><span data-stu-id="12fc0-103">ML.NET Content Guide</span></span>

<span data-ttu-id="12fc0-104">このガイドでは、基本的な概念について説明し、ML.NET を使って作業するためのチュートリアルと API リファレンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-104">This guide explains basic concepts and provides tutorials and an API reference for working with ML.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="12fc0-105">このドキュメントでは ML.NET が参照されていますが、これは現在プレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="12fc0-105">This documentation refers to ML.NET, which is currently in Preview.</span></span> <span data-ttu-id="12fc0-106">内容は変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="12fc0-106">Material may be subject to change.</span></span> <span data-ttu-id="12fc0-107">詳しくは、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12fc0-107">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="get-started"></a><span data-ttu-id="12fc0-108">作業開始</span><span class="sxs-lookup"><span data-stu-id="12fc0-108">Get started</span></span>

<span data-ttu-id="12fc0-109">ML.NET をインストールして構築を開始するには、[入門チュートリアル](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial)に従います。</span><span class="sxs-lookup"><span data-stu-id="12fc0-109">To install and start building in ML.NET, follow the [Get started tutorial](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span></span>

<span data-ttu-id="12fc0-110">ML.NET について学習するには、[ML.NET とは何か](what-is-mldotnet.md)を説明しているページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12fc0-110">To learn about ML.NET, see [What is ML.NET?](what-is-mldotnet.md)</span></span>

<span data-ttu-id="12fc0-111">基本を理解するには、「[Basic concepts for model training in ML.NET](basic-concepts-model-training-in-mldotnet.md)」(ML.NET でのモデル トレーニングに関する基本的な概念) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12fc0-111">To understand basics, see [Basic concepts for model training in ML.NET](basic-concepts-model-training-in-mldotnet.md).</span></span>

## <a name="tutorials"></a><span data-ttu-id="12fc0-112">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="12fc0-112">Tutorials</span></span>

<span data-ttu-id="12fc0-113">[バイナリ分類モデルを使ったセンチメント分析](./tutorials/sentiment-analysis.md)に関するページでは、センチメントが正であるか負であるかを判断するアプリの構築方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-113">[Analyze sentiment using a binary classification model](./tutorials/sentiment-analysis.md) shows you how to build an app that determines whether sentiment is positive or negative.</span></span>

<span data-ttu-id="12fc0-114">[多クラス分類モデルを使った GitHub の問題の分類](./tutorials/github-issue-classification.md)に関するページでは、GitHub の問題に対する区分のラベルを判断するアプリを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-114">[Classify GitHub issues using a multiclass classification model](./tutorials/github-issue-classification.md) shows you how to build an app that determines the Area label for a GitHub issue.</span></span>

<span data-ttu-id="12fc0-115">[回帰モデルを使った料金の予測](./tutorials/taxi-fare.md)に関するページでは、履歴データの多数の要因を使って回答を決定する、予測的なアプリの構築方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-115">[Predict prices using a regression model](./tutorials/taxi-fare.md) shows you how to build a predictive app that uses many factors from historical data to determine the answer.</span></span>

<span data-ttu-id="12fc0-116">[特徴によるアヤメの花の分類](./tutorials/iris-clustering.md)に関するページでは、クラスタ リング モデルを使ってアヤメのデータセットを分析する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-116">[Classify iris flowers by features](./tutorials/iris-clustering.md) shows you how to use a clustering model to analyze the iris data set.</span></span>

<span data-ttu-id="12fc0-117">[ML.NET を使った映画の推奨システムの作成](./tutorials/movie-recommmendation.md)に関するページでは、ユーザーの履歴に基づいて映画を推奨する推奨アプリを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-117">[Create a Movie Recommender with ML.NET](./tutorials/movie-recommmendation.md) shows you how to build a recommendation app to recommend movies to users based on their history.</span></span>

<span data-ttu-id="12fc0-118">[TensorFlow を使った ML.NET のカスタム画像分類アプリの構築](./tutorials/image-classification.md)に関するページでは、既存の Tensorflow モデルを再トレーニングし、ML.NET を使ってカスタム画像分類アプリを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-118">[Build an ML.NET custom image classifier with TensorFlow](./tutorials/image-classification.md): demonstrates how to retrain an existing Tensorflow model to create a custom image classifier using ML.NET.</span></span>

## <a name="how-to-guide"></a><span data-ttu-id="12fc0-119">ハウツー ガイド</span><span class="sxs-lookup"><span data-stu-id="12fc0-119">How to guide</span></span>

<span data-ttu-id="12fc0-120">[Infer.NET と確率論的プログラミングを使ったゲーム対戦リスト アプリの構築](./how-to-guides/matchup-app-infer-net.md)に関するページでは、Xbox のゲームに見られるような対戦アプリの簡略化バージョンを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-120">[Build a game match-up list app with Infer.NET and probabilistic programming](./how-to-guides/matchup-app-infer-net.md) shows you how to build a simplified version of a match-up app like you'd see in an Xbox game.</span></span>

## <a name="resources"></a><span data-ttu-id="12fc0-121">リソース</span><span class="sxs-lookup"><span data-stu-id="12fc0-121">Resources</span></span>

<span data-ttu-id="12fc0-122">「[機械学習の用語集](./resources/glossary.md)」には主要な用語の定義があります。</span><span class="sxs-lookup"><span data-stu-id="12fc0-122">[Machine learning glossary](./resources/glossary.md) defines key terminology.</span></span>

<span data-ttu-id="12fc0-123">「[機械学習のタスク](./resources/tasks.md)」では、分類や異常検出などのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-123">[Machine learning tasks](./resources/tasks.md) describes tasks, such as classification and anomaly detection.</span></span> 

<span data-ttu-id="12fc0-124">「[データ変換](./resources/transforms.md)」では、ML.NET におけるデータ準備機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-124">[Data transforms](./resources/transforms.md) describes data preparation capabilities in ML.NET.</span></span>

## <a name="api-reference"></a><span data-ttu-id="12fc0-125">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="12fc0-125">API reference</span></span>

<span data-ttu-id="12fc0-126">[ML.NET API リファレンス](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)に関するページでは、使用できる API の全容について説明します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-126">[ML.NET API Reference](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) describes the breadth of APIs available.</span></span>
