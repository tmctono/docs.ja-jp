---
title: ML.NET コンテンツ ガイド
description: ML.NET を使用してカスタム AI ソリューションを構築し、これを .NET アプリケーションに統合する方法について説明します。
ms.date: 01/18/2019
ms.custom: seodec18
ms.openlocfilehash: fe9129fd6975ba9176ccce025b06f03734803155
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920767"
---
# <a name="mlnet-content-guide"></a><span data-ttu-id="a311b-103">ML.NET コンテンツ ガイド</span><span class="sxs-lookup"><span data-stu-id="a311b-103">ML.NET Content Guide</span></span>

<span data-ttu-id="a311b-104">このガイドでは、基本的な概念について説明し、ML.NET を使って作業するためのチュートリアルと API リファレンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a311b-104">This guide explains basic concepts and provides tutorials and an API reference for working with ML.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="a311b-105">このドキュメントでは ML.NET が参照されていますが、これは現在プレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="a311b-105">This documentation refers to ML.NET, which is currently in Preview.</span></span> <span data-ttu-id="a311b-106">内容は変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a311b-106">Material may be subject to change.</span></span> <span data-ttu-id="a311b-107">詳しくは、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a311b-107">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="get-started"></a><span data-ttu-id="a311b-108">作業開始</span><span class="sxs-lookup"><span data-stu-id="a311b-108">Get started</span></span>

<span data-ttu-id="a311b-109">ML.NET をインストールして構築を開始するには、[入門チュートリアル](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial)に従います。</span><span class="sxs-lookup"><span data-stu-id="a311b-109">To install and start building in ML.NET, follow the [Get started tutorial](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span></span>

<span data-ttu-id="a311b-110">ML.NET について学習するには、[ML.NET とは何か](what-is-mldotnet.md)を説明しているページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a311b-110">To learn about ML.NET, see [What is ML.NET?](what-is-mldotnet.md)</span></span>

<span data-ttu-id="a311b-111">基本を理解するには、「[Basic concepts for model training in ML.NET](basic-concepts-model-training-in-mldotnet.md)」(ML.NET でのモデル トレーニングに関する基本的な概念) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a311b-111">To understand basics, see [Basic concepts for model training in ML.NET](basic-concepts-model-training-in-mldotnet.md).</span></span>

## <a name="tutorials"></a><span data-ttu-id="a311b-112">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="a311b-112">Tutorials</span></span>

<span data-ttu-id="a311b-113">[バイナリ分類モデルを使ったセンチメント分析](./tutorials/sentiment-analysis.md)に関するページでは、センチメントが正であるか負であるかを判断するアプリの構築方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a311b-113">[Analyze sentiment using a binary classification model](./tutorials/sentiment-analysis.md) shows you how to build an app that determines whether sentiment is positive or negative.</span></span>

<span data-ttu-id="a311b-114">[多クラス分類モデルを使った GitHub の問題の分類](./tutorials/github-issue-classification.md)に関するページでは、GitHub の問題に対する区分のラベルを判断するアプリを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a311b-114">[Classify GitHub issues using a multiclass classification model](./tutorials/github-issue-classification.md) shows you how to build an app that determines the Area label for a GitHub issue.</span></span>

<span data-ttu-id="a311b-115">[回帰モデルを使った料金の予測](./tutorials/taxi-fare.md)に関するページでは、履歴データの多数の要因を使って回答を決定する、予測的なアプリの構築方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a311b-115">[Predict prices using a regression model](./tutorials/taxi-fare.md) shows you how to build a predictive app that uses many factors from historical data to determine the answer.</span></span>

<span data-ttu-id="a311b-116">[特徴によるアヤメの花の分類](./tutorials/iris-clustering.md)に関するページでは、クラスタ リング モデルを使ってアヤメのデータセットを分析する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a311b-116">[Classify iris flowers by features](./tutorials/iris-clustering.md) shows you how to use a clustering model to analyze the iris data set.</span></span> 

## <a name="how-to-guide"></a><span data-ttu-id="a311b-117">ハウツー ガイド</span><span class="sxs-lookup"><span data-stu-id="a311b-117">How to guide</span></span>

<span data-ttu-id="a311b-118">[Infer.NET と確率論的プログラミングを使ったゲーム対戦リスト アプリの構築](./how-to-guides/matchup-app-infer-net.md)に関するページでは、Xbox のゲームに見られるような対戦アプリの簡略化バージョンを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a311b-118">[Build a game match-up list app with Infer.NET and probabilistic programming](./how-to-guides/matchup-app-infer-net.md) shows you how to build a simplified version of a match-up app like you'd see in an Xbox game.</span></span>

## <a name="resources"></a><span data-ttu-id="a311b-119">リソース</span><span class="sxs-lookup"><span data-stu-id="a311b-119">Resources</span></span>

<span data-ttu-id="a311b-120">「[機械学習の用語集](./resources/glossary.md)」には主要な用語の定義があります。</span><span class="sxs-lookup"><span data-stu-id="a311b-120">[Machine learning glossary](./resources/glossary.md) defines key terminology.</span></span>

<span data-ttu-id="a311b-121">「[機械学習のタスク](./resources/tasks.md)」では、分類や異常検出などのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a311b-121">[Machine learning tasks](./resources/tasks.md) describes tasks, such as classification and anomaly detection.</span></span> 

<span data-ttu-id="a311b-122">「[データ変換](./resources/transforms.md)」では、ML.NET におけるデータ準備機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a311b-122">[Data transforms](./resources/transforms.md) describes data preparation capabilities in ML.NET.</span></span>


## <a name="api-reference"></a><span data-ttu-id="a311b-123">API リファレンス</span><span class="sxs-lookup"><span data-stu-id="a311b-123">API reference</span></span>

<span data-ttu-id="a311b-124">[ML.NET API リファレンス](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)に関するページでは、使用できる API の全容について説明します。</span><span class="sxs-lookup"><span data-stu-id="a311b-124">[ML.NET API Reference](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) describes the breadth of APIs available.</span></span>
