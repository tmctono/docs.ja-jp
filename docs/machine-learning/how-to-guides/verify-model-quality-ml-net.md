---
title: 機械学習モデルの品質を評価するメトリックを計算する
description: ML.NET を使用して機械学習モデルの品質を評価および検証するメトリックを計算する方法について説明します。
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2c7749205b862a42f42b857972057c441ab84364
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641092"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="1d08d-103">機械学習モデルの品質を評価するメトリックを計算する</span><span class="sxs-lookup"><span data-stu-id="1d08d-103">Calculate metrics to evaluate machine learning model quality</span></span> 

> [!NOTE]
> <span data-ttu-id="1d08d-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d08d-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="1d08d-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d08d-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="1d08d-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="1d08d-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="1d08d-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d08d-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="1d08d-108">モデルをトレーニングした後はどのように品質を評価すればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1d08d-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="1d08d-109">各機械学習タスクは品質評価用のメトリックを公開しています。</span><span class="sxs-lookup"><span data-stu-id="1d08d-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="1d08d-110">次の例のように、タスクの対応する 'コンテキスト' を使用してモデルを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="1d08d-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
