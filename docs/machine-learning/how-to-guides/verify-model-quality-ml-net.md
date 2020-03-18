---
title: 機械学習モデルの品質を評価するメトリックを計算する
description: ML.NET を使用して機械学習モデルの品質を評価および検証するメトリックを計算する方法について説明します。
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: d6409307cd283ae67d7546c4dc6e19e6089a0766
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73975839"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="a78fd-103">機械学習モデルの品質を評価するメトリックを計算する</span><span class="sxs-lookup"><span data-stu-id="a78fd-103">Calculate metrics to evaluate machine learning model quality</span></span>

> [!NOTE]
> <span data-ttu-id="a78fd-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a78fd-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="a78fd-105">詳細については、[ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a78fd-105">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="a78fd-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="a78fd-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="a78fd-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a78fd-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="a78fd-108">モデルをトレーニングした後はどのように品質を評価すればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="a78fd-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="a78fd-109">各機械学習タスクは品質評価用のメトリックを公開しています。</span><span class="sxs-lookup"><span data-stu-id="a78fd-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="a78fd-110">次の例のように、タスクの対応する 'コンテキスト' を使用してモデルを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="a78fd-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
