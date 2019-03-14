---
title: テキスト ファイルではないデータで機械学習モデルをトレーニングする - ML.NET
description: ML.NET を使用して、機械学習モデルのトレーニングのために非ファイル トレーニング データを予測パイプラインの一部として読み込む方法について説明します。
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 27b327a63cb55b7fce0f4ff7facd3ee7c4a1c85c
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678616"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a><span data-ttu-id="2350c-103">テキスト ファイルではないデータで機械学習モデルをトレーニングする - ML.NET</span><span class="sxs-lookup"><span data-stu-id="2350c-103">Train a machine learning model with data that's not in a text file - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="2350c-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="2350c-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="2350c-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2350c-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="2350c-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="2350c-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="2350c-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2350c-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="2350c-108">ML.NET で一般的に実証されているユース ケースは、`TextLoader` を使ってファイルからトレーニング データを読み取る方法です。</span><span class="sxs-lookup"><span data-stu-id="2350c-108">The commonly demonstrated use case for ML.NET is use the `TextLoader` to read the training data from a file.</span></span>
<span data-ttu-id="2350c-109">ただし、実際のトレーニングのシナリオでは、データは次のようなそれ以外の場所にある場合があります。</span><span class="sxs-lookup"><span data-stu-id="2350c-109">However, in real-time training scenarios the data can be elsewhere, such as:</span></span>

* <span data-ttu-id="2350c-110">SQL テーブル</span><span class="sxs-lookup"><span data-stu-id="2350c-110">in SQL tables</span></span>
* <span data-ttu-id="2350c-111">ログ ファイルから抽出</span><span class="sxs-lookup"><span data-stu-id="2350c-111">extracted from log files</span></span>
* <span data-ttu-id="2350c-112">その場で生成</span><span class="sxs-lookup"><span data-stu-id="2350c-112">generated on the fly</span></span>

<span data-ttu-id="2350c-113">[スキーマの理解](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md)を使って、既存の C# `IEnumerable` を `DataView` として ML.NET に取り込みます。</span><span class="sxs-lookup"><span data-stu-id="2350c-113">Use [schema comprehension](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) to bring an existing C# `IEnumerable` into ML.NET as a `DataView`.</span></span>

<span data-ttu-id="2350c-114">この例では、顧客チャーン予測モデルを構築し、実稼動システムから次の機能を抽出します。</span><span class="sxs-lookup"><span data-stu-id="2350c-114">For this example, you'll build the customer churn prediction model, and extract the following features from your production system:</span></span>

* <span data-ttu-id="2350c-115">顧客の ID (モデルでは無視されます)</span><span class="sxs-lookup"><span data-stu-id="2350c-115">Customer ID (ignored by the model)</span></span>
* <span data-ttu-id="2350c-116">顧客が解約済みかどうか (ターゲット 'ラベル')</span><span class="sxs-lookup"><span data-stu-id="2350c-116">Whether the customer has churned (the target 'label')</span></span>
* <span data-ttu-id="2350c-117">'人口統計カテゴリ' ('ヤング アダルト' のような 1 つの文字列)</span><span class="sxs-lookup"><span data-stu-id="2350c-117">The 'demographic category' (one string, like 'young adult' etc.)</span></span>
* <span data-ttu-id="2350c-118">過去 5 日間のアクセス数</span><span class="sxs-lookup"><span data-stu-id="2350c-118">The number of visits from the last 5 days.</span></span>

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

<span data-ttu-id="2350c-119">このデータを `DataView` に読み込み、次のコードを使用して、モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="2350c-119">Load this data into the `DataView` and train the model, using the following code:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.Data.ReadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
