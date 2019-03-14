---
title: トレーニング済みの機械学習モデルをアプリで運用化する - ML.NET
description: ML.NET を使用して、アプリケーションでトレーニングおよび評価された機械学習モデルを使用する方法について説明します
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: be6906c939b82d00067babaeebe809dae3de413a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675135"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a><span data-ttu-id="59f4f-103">トレーニング済みの機械学習モデルをアプリで運用化する - ML.NET</span><span class="sxs-lookup"><span data-stu-id="59f4f-103">Operationalize a trained machine learning model in apps - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="59f4f-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="59f4f-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="59f4f-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59f4f-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="59f4f-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="59f4f-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="59f4f-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59f4f-107">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="59f4f-108">モデルのメトリックに満足したら、次はモデルを "運用化" します。</span><span class="sxs-lookup"><span data-stu-id="59f4f-108">When the model metrics look good to you, it's time to 'operationalize' the model.</span></span> <span data-ttu-id="59f4f-109">構築した `model` オブジェクトは、トレーニング中に "学習" したものと同じ手順を適用して、さまざまな環境で使用、永続化、および再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="59f4f-109">The `model` object you built can be consumed, persisted, and reused in different environments, applying the same steps that it 'learned' during training.</span></span>

<span data-ttu-id="59f4f-110">モデルをファイルに保存し、(場合によっては別のコンテキストで) 再度読み込むには、次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="59f4f-110">To save the model to a file, and reload it (potentially in a different context), use the following example:</span></span>

```csharp
using (var stream = File.Create(modelPath))
{
    // Saving and loading happens to 'dynamic' models.
    mlContext.Model.Save(model, stream);
}

// Potentially, the lines below can be in a different process altogether.

// When you load the model, it's a transformer.
ITransformer loadedModel;
using (var stream = File.OpenRead(modelPath))
    loadedModel = mlContext.Model.Load(stream);
```
