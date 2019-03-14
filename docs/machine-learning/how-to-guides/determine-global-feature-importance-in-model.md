---
title: ML.NET の Permutation Feature Importance を使ってモデルの特徴の重要度を判断する
description: ML.NET の Permutation Feature Importance を使ってモデルの特徴の重要度を理解する
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b0457bc07168579403e5a00383864c5612e1d17f
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675551"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a><span data-ttu-id="5aa39-103">ML.NET の Permutation Feature Importance を使ってモデルの特徴の重要度を判断する</span><span class="sxs-lookup"><span data-stu-id="5aa39-103">Determine the feature importance of models with Permutation Feature Importance in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="5aa39-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5aa39-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="5aa39-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa39-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="5aa39-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="5aa39-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="5aa39-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa39-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="5aa39-108">機械学習モデルを作成するとき、予測を作成するだけでは十分でないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="5aa39-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="5aa39-109">多くの場合、機械学習の開発者、意思決定者、およびモデルによって影響を受ける担当者は、機械学習モデルがどのように決定を行うか、またそのパフォーマンスにどの特徴が関係するかを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aa39-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="5aa39-110">`Permutation Feature Importance` (PFI) はモデルについて説明するツールであり、機械学習開発者がモデルの特徴の重要性をよく理解できるように社内で使用されています。</span><span class="sxs-lookup"><span data-stu-id="5aa39-110">`Permutation Feature Importance` (PFI) is a model explainability tool that is used internally at Microsoft to help machine learning developers better understand the feature importance of models.</span></span>

<span data-ttu-id="5aa39-111">PFI は、トレーニングされた機械学習モデルの**グローバルな特徴の重要性**を判断する技術であり、Breiman 著[「Random Forests」論文、セクション 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) から刺激を受けたものです。</span><span class="sxs-lookup"><span data-stu-id="5aa39-111">PFI is a technique to determine **global feature importance** in a trained machine learning model, motivated by Breiman in the ["Random Forests" paper, section 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span></span> <span data-ttu-id="5aa39-112">PFI では、特徴の重要性を測定するために、"特徴の値がランダム\* 値に設定されたら、どのような影響がモデルに及ぼされるか?" と質問します。</span><span class="sxs-lookup"><span data-stu-id="5aa39-112">PFI measures feature importance by asking the question, "What would the effect on the model be if the values for a feature were set to a random\* value?".</span></span> <span data-ttu-id="5aa39-113">PFI 方法のメリットは、モデルに依存しない点です。評価することができるすべてのモデルに使用できます。また、特徴の重要性を計算するために、トレーニング セットだけでなく任意のデータセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5aa39-113">The advantage of the PFI method is that it is model agnostic — it works with any model that can be evaluated — and it can use any dataset, not just the training set, to compute feature importance.</span></span> <span data-ttu-id="5aa39-114">PFI を使用すると、このグラフのように特徴の重要性を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="5aa39-114">You can use PFI like so to produce feature importances like this graph:</span></span>

![Permutation Feature Importance グラフ](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model.LastTransformer, model.Transform(data), "MedianHomeValue");

// Get the feature names from the training set
var featureNames =
    data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Write out the feature names and their importance to the model's Mean R-squared value
for (int i = 0; i < featureNames.Length;i++)
{
    Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].RSquared.Mean:G4}");
}
```

<span data-ttu-id="5aa39-116">モデルの特徴の重要性を分析する PFI の使用例については、[dotnet/machinelearning GitHub リポジトリ](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5aa39-116">For a sample using PFI to analyze the feature importance of a model, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span></span>

<span data-ttu-id="5aa39-117">/\* 厳密にはランダムではありませんが、サンプルのセット全体で順序が変更されます。</span><span class="sxs-lookup"><span data-stu-id="5aa39-117">/\* Well, not random exactly, but permuted across the set of examples.</span></span>
