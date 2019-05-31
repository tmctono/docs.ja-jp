---
title: ML.NET による自動機械学習
description: 自動モデル選択およびトレーニングの概要
author: natke
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
ms.openlocfilehash: e6654718f174c9d8b628b05d85d74952c222eb66
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452733"
---
# <a name="automated-machine-learning-with-mlnet"></a><span data-ttu-id="60c48-103">ML.NET による自動機械学習</span><span class="sxs-lookup"><span data-stu-id="60c48-103">Automated machine learning with ML.NET</span></span>

<span data-ttu-id="60c48-104">自動機械学習は、自動モデル選択およびトレーニングを実行する ML.NET の機能です。</span><span class="sxs-lookup"><span data-stu-id="60c48-104">Automated machine learning is a feature of ML.NET that performs automatic model selection and training.</span></span> <span data-ttu-id="60c48-105">機械学習タスクを指定し、データセットを指定すると、自動 ML によって最適なメトリックのモデルが選択されます。</span><span class="sxs-lookup"><span data-stu-id="60c48-105">You specify the machine learning task and supply a dataset, and automated ML chooses the model with the best metrics.</span></span> <span data-ttu-id="60c48-106">出力内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="60c48-106">It outputs:</span></span>
- <span data-ttu-id="60c48-107">予測アプリケーションに読み込むことができるモデル ファイル</span><span class="sxs-lookup"><span data-stu-id="60c48-107">a model file that can be loaded into your prediction application</span></span>
- <span data-ttu-id="60c48-108">予測を行うアプリケーション コード</span><span class="sxs-lookup"><span data-stu-id="60c48-108">application code to make predictions</span></span>
- <span data-ttu-id="60c48-109">(モデルを理解するために) 特徴の選択とモデルのトレーニングに使用されるソース コード</span><span class="sxs-lookup"><span data-stu-id="60c48-109">the source code used for feature selection and model training (to understand the model)</span></span>

> [!NOTE]
> <span data-ttu-id="60c48-110">この機能は現在プレビュー段階であり、資料は変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="60c48-110">This feature is currently in Preview, and material may be subject to change.</span></span> 

<span data-ttu-id="60c48-111">現在、自動 ML は二項分類、多クラス分類、回帰の機械学習[タスク](resources/tasks.md)に限定されています。</span><span class="sxs-lookup"><span data-stu-id="60c48-111">Automated ML is currently limited to the machine learning [tasks](resources/tasks.md) of binary classification, multiclass classification, and regression.</span></span> <span data-ttu-id="60c48-112">他の機械学習タスクが今後のリリースでサポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="60c48-112">The other machine learning tasks will be supported in future releases.</span></span>

<span data-ttu-id="60c48-113">自動 ML を使用する方法は 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="60c48-113">There are three ways to use automated ML:</span></span>
1. <span data-ttu-id="60c48-114">コマンド ライン上で [ML.NET CLI](automate-training-with-cli.md) を使用する</span><span class="sxs-lookup"><span data-stu-id="60c48-114">On the command line, with the [ML.NET CLI](automate-training-with-cli.md)</span></span>
1. <span data-ttu-id="60c48-115">アプリケーションを介して[自動 ML API](how-to-guides/how-to-use-the-automl-api.md) を使用する</span><span class="sxs-lookup"><span data-stu-id="60c48-115">Via an application, with the [automated ML API](how-to-guides/how-to-use-the-automl-api.md)</span></span>
1. <span data-ttu-id="60c48-116">ML.NET Model Builder でグラフィカル ユーザー インターフェイスを使用する</span><span class="sxs-lookup"><span data-stu-id="60c48-116">With a graphical user interface, with the the ML.NET Model Builder</span></span>
