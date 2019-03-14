---
title: ML.NET でのモデル トレーニングに関する基本的な概念
description: この記事では、ML.NET での "*モデル トレーニング*" シナリオに関する基本概念について説明します。 よりシンプルなシナリオである "*既存モデルでの予測*" と関係のない概念も含まれます。
ms.date: 03/05/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: 78554cfd1dfdb3dba82a325d47245aeb313bb6fe
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675564"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a><span data-ttu-id="81611-104">ML.NET でのモデル トレーニングに関する基本的な概念</span><span class="sxs-lookup"><span data-stu-id="81611-104">Basic concepts for model training in ML.NET</span></span>

<span data-ttu-id="81611-105">この記事では、ML.NET での "*モデル トレーニング*" シナリオに関する基本概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="81611-105">This article explains the basic concepts covering *model training* scenarios in ML.NET.</span></span> <span data-ttu-id="81611-106">よりシンプルなシナリオである "*既存モデルでの予測*" と関係のない概念も含まれます。</span><span class="sxs-lookup"><span data-stu-id="81611-106">Not all concepts are relevant to the more simple scenario of *prediction with an existing model*.</span></span>

<span data-ttu-id="81611-107">この記事と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="81611-107">This article and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="81611-108">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81611-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="model-training-concepts"></a><span data-ttu-id="81611-109">モデルのトレーニングの概念</span><span class="sxs-lookup"><span data-stu-id="81611-109">Model training concepts</span></span>

<span data-ttu-id="81611-110">このドキュメントでは、ML.NET でのモデルのトレーニングに関連する次の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="81611-110">This document covers the following concepts related to model training in ML.NET:</span></span>

- <span data-ttu-id="81611-111">`IDataView` インターフェイスとして表された "[*データ*](#data)"。</span><span class="sxs-lookup"><span data-stu-id="81611-111">[*Data*](#data) represented as an `IDataView` interface.</span></span>
  - <span data-ttu-id="81611-112">ML.NET では、データは SQL ビューに似ています。つまり、遅延評価で、不変で、カーソル可能で、異種で、スキーマ化されたデータセットです。</span><span class="sxs-lookup"><span data-stu-id="81611-112">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, immutable, cursorable, heterogenous, schematized dataset.</span></span> 
  - <span data-ttu-id="81611-113">データ インターフェイスに関する優れたドキュメントとしては、「[IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md)」(IDataView 設計原則) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="81611-113">An excellent document about the data interface is [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span></span>
- <span data-ttu-id="81611-114">`ITransformer` インターフェイスとして表された "[*トランスフォーマー*](#transformer)"。</span><span class="sxs-lookup"><span data-stu-id="81611-114">[*Transformer*](#transformer) represented as `ITransformer` interface.</span></span>
  - <span data-ttu-id="81611-115">トランスフォーマーは、データを受け取り、データに対して何らかの作業を行い、変換された新しいデータを返すコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="81611-115">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>
  - <span data-ttu-id="81611-116">たとえば、機械学習モデルは特徴を受け取って予測を返すトランスフォーマーと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="81611-116">For example, you can think of a machine learning model as a transformer that takes features and returns predictions.</span></span>
  - <span data-ttu-id="81611-117">別の例としては、テキスト トークナイザーは 1 つのテキスト列を受け取り、テキストから抽出された個々の単語を含むベクトル列を出力します。</span><span class="sxs-lookup"><span data-stu-id="81611-117">Another example, text tokenizer takes a single text column and outputs a vector column with individual words extracted out of the texts.</span></span>
- <span data-ttu-id="81611-118">`IDataReader<T>` インターフェイスとして表された "[*データ リーダー*](#data-reader)"。</span><span class="sxs-lookup"><span data-stu-id="81611-118">[*Data reader*](#data-reader) represented as an `IDataReader<T>` interface.</span></span>
  - <span data-ttu-id="81611-119">データ リーダーは、データを作成する ML.NET コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="81611-119">The data reader is ML.NET component to create data.</span></span> <span data-ttu-id="81611-120">`T` のインスタンスを受け取り、そのデータを返します。</span><span class="sxs-lookup"><span data-stu-id="81611-120">It takes an instance of `T` and returns data out of it.</span></span> 
  - <span data-ttu-id="81611-121">たとえば、*TextLoader* は `IDataReader<IMultiStreamSource>` です。</span><span class="sxs-lookup"><span data-stu-id="81611-121">For example, a *TextLoader* is an `IDataReader<IMultiStreamSource>`.</span></span> <span data-ttu-id="81611-122">これはソースを受け取って、データを生成します。</span><span class="sxs-lookup"><span data-stu-id="81611-122">It takes the source and produces data.</span></span> 
- <span data-ttu-id="81611-123">`IEstimator<T>` インターフェイスとして表された "[*エスティメーター*](#estimator)"。</span><span class="sxs-lookup"><span data-stu-id="81611-123">[*Estimator*](#estimator) represented as an `IEstimator<T>` interface.</span></span>
  - <span data-ttu-id="81611-124">これは、データから学習するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="81611-124">This is an object that learns from data.</span></span> <span data-ttu-id="81611-125">学習の結果は "*トランスフォーマー*" です。</span><span class="sxs-lookup"><span data-stu-id="81611-125">The result of the learning is a *transformer*.</span></span>
  - <span data-ttu-id="81611-126">機械学習の "*アルゴリズム*" は、データについて学習して機械学習の "*モデル*" を生成するエスティメーターと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="81611-126">You can think of a machine learning *algorithm* as an estimator that learns on data and produces a machine learning *model*.</span></span>
- <span data-ttu-id="81611-127">`PredictionEngine<TSrc, TDst>` クラスとして表された "[*予測関数*](#prediction-function)"。</span><span class="sxs-lookup"><span data-stu-id="81611-127">[*Prediction function*](#prediction-function) represented as a `PredictionEngine<TSrc, TDst>` class.</span></span>
  - <span data-ttu-id="81611-128">予測関数は、予測時などに 1 つの行に対してトランスフォーマーを適用するマシンと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="81611-128">The prediction function can be seen as a machine that applies a transformer to one row, such as at prediction time.</span></span>

## <a name="data"></a><span data-ttu-id="81611-129">データ</span><span class="sxs-lookup"><span data-stu-id="81611-129">Data</span></span>

<span data-ttu-id="81611-130">ML.NET では、データは SQL ビューに似ています。つまり、遅延評価で、カーソル可能で、異種で、スキーマ化されたデータセットです。</span><span class="sxs-lookup"><span data-stu-id="81611-130">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, cursorable, heterogenous, schematized dataset.</span></span>

- <span data-ttu-id="81611-131">データ ビューの列に関する情報を含む "*スキーマ*" (`ISchema` インターフェイスのインスタンス) を持っています。</span><span class="sxs-lookup"><span data-stu-id="81611-131">It has *Schema* (an instance of an `ISchema` interface) that contains the information about the data view's columns.</span></span>
  - <span data-ttu-id="81611-132">各列には、"*名前*"、"*型*"、および列に関連付けられた "*メタデータ*" の任意のセットがあります。</span><span class="sxs-lookup"><span data-stu-id="81611-132">Each column has a *Name*, a *Type*, and an arbitrary set of *metadata* associated with it.</span></span>
  - <span data-ttu-id="81611-133">列の "*メタデータ*" には、ベクトルの列のスロット名のような情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81611-133">The column's *metadata* contains information like slot names of a vector column and the like.</span></span> <span data-ttu-id="81611-134">メタデータ自体は、各列に固有の別の 1 つの行 "*データ*" として表されます。</span><span class="sxs-lookup"><span data-stu-id="81611-134">The metadata itself is represented as another one-row *data* that is unique to each column.</span></span>
  - <span data-ttu-id="81611-135">データ ビューは "*カーソル*" のソースです。</span><span class="sxs-lookup"><span data-stu-id="81611-135">The data view is a source of *cursors*.</span></span> <span data-ttu-id="81611-136">SQL のカーソルを考えてください。カーソルは、一度に 1 行ずつデータを反復処理するオブジェクトであり、使用可能なデータを表します。</span><span class="sxs-lookup"><span data-stu-id="81611-136">Think SQL cursors: A cursor is an object that iterates through the data, one row at a time, and presents the available data.</span></span>
  - <span data-ttu-id="81611-137">当然ながら、データには必要なだけいくつでもアクティブなカーソルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="81611-137">Naturally, data can have as many active cursors over it as needed.</span></span> <span data-ttu-id="81611-138">データ自体は変更不可能であるため、カーソルは完全に独立しています。</span><span class="sxs-lookup"><span data-stu-id="81611-138">Since data itself is immutable, cursors are truly independent.</span></span>
  - <span data-ttu-id="81611-139">通常、カーソルは列のサブセットにのみアクセスします。効率化するため、ML.NET ではカーソルで必要な列の値のみが計算されます。</span><span class="sxs-lookup"><span data-stu-id="81611-139">Cursors typically access only a subset of columns: For efficiency, ML.NET computes only the values of columns that are needed by the cursor.</span></span>

## <a name="transformer"></a><span data-ttu-id="81611-140">トランスフォーマー</span><span class="sxs-lookup"><span data-stu-id="81611-140">Transformer</span></span>

<span data-ttu-id="81611-141">トランスフォーマーは、データを受け取り、データに対して何らかの作業を行い、変換された新しいデータを返すコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="81611-141">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>

<span data-ttu-id="81611-142">ML.NET のほとんどのトランスフォーマーは、多くの場合、一度に 1 つの "*入力列*" を処理して、"*出力列*" を生成します。</span><span class="sxs-lookup"><span data-stu-id="81611-142">Most transformers in ML.NET tend to operate on one *input column* at a time, and produce the *output column*.</span></span> <span data-ttu-id="81611-143">たとえば、`new HashTransformer("bar", "foo")` は、"foo" 列から値を取得し、そのハッシュ値を計算して、"bar" 列に格納します。</span><span class="sxs-lookup"><span data-stu-id="81611-143">For example, a `new HashTransformer("bar", "foo")` takes the values from column "foo", hashes them, and puts them into column "bar".</span></span> 

<span data-ttu-id="81611-144">また、入力列と出力列は同じ名前であることが一般的です。</span><span class="sxs-lookup"><span data-stu-id="81611-144">It's also common that the input and output column names are the same.</span></span> <span data-ttu-id="81611-145">この場合、古い列は新しい列で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="81611-145">In this case, the old column is replaced with the new one.</span></span> <span data-ttu-id="81611-146">たとえば、`new HashTransformer("foo")` は、"foo" 列から値を取得し、そのハッシュ値を計算して、"foo" 列に戻します。</span><span class="sxs-lookup"><span data-stu-id="81611-146">For example, a `new HashTransformer("foo")` takes the values from column "foo", hashes them, and puts them back into "foo".</span></span> 

<span data-ttu-id="81611-147">`Transform` が呼び出されると、任意のトランスフォーマーによって新しいデータ ビューが生成されます。</span><span class="sxs-lookup"><span data-stu-id="81611-147">Any transformer, produces a new data view when `Transform` is called.</span></span> <span data-ttu-id="81611-148">データ ビューは不変であることを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="81611-148">Remember, data views are immutable.</span></span>

<span data-ttu-id="81611-149">もう 1 つの重要な考慮事項は、データは遅延評価されるため、"*トランスフォーマーも遅延である*" ということです。</span><span class="sxs-lookup"><span data-stu-id="81611-149">Another important consideration is that, because data is lazily evaluated, *transformers are lazy too*.</span></span> <span data-ttu-id="81611-150">基本的に、次の呼び出しの後で</span><span class="sxs-lookup"><span data-stu-id="81611-150">Essentially, after you call</span></span>

```csharp
var newData = transformer.Transform(oldData)
```

<span data-ttu-id="81611-151">実際の計算は行われません。</span><span class="sxs-lookup"><span data-stu-id="81611-151">no actual computation happens.</span></span> <span data-ttu-id="81611-152">`newData` からカーソルを取得し、値の使用を開始した後でのみ、`newData` によって `transformer` の変換ロジックが呼び出されます (ただし、これは、要求された列を生成するために対象の `transformer` が必要な場合にのみ行われます)。</span><span class="sxs-lookup"><span data-stu-id="81611-152">Only after you get a cursor from `newData` and start consuming the value does `newData` invoke the `transformer` transformation logic (and even then, it only happens if the `transformer` in question is needed to produce the requested columns).</span></span>

### <a name="transformer-chains"></a><span data-ttu-id="81611-153">トランスフォーマーのチェーン</span><span class="sxs-lookup"><span data-stu-id="81611-153">Transformer chains</span></span>

<span data-ttu-id="81611-154">トランスフォーマーの便利な性質は、"*トランスフォーマーのシーケンシャルな適用を別のトランスフォーマーでビルドできる*" というものです。</span><span class="sxs-lookup"><span data-stu-id="81611-154">A useful property of a transformer is that *you can build a sequential application of transformers as yet another transformer*:</span></span>

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

<span data-ttu-id="81611-155">この性質は ML.NET でよく使用されます。通常、トレーニング済みの ML.NET モデルはトランスフォーマーのチェーンであり、これはすべての意図と目的に対する 1 つの "*トランスフォーマー*" です。</span><span class="sxs-lookup"><span data-stu-id="81611-155">This property is commonly used in ML.NET: typically, the trained ML.NET model is a chain of transformers, which is, for all intents and purposes, a *transformer*.</span></span>

## <a name="data-reader"></a><span data-ttu-id="81611-156">データ リーダー</span><span class="sxs-lookup"><span data-stu-id="81611-156">Data reader</span></span>

<span data-ttu-id="81611-157">データ リーダーは、データを "作成する" ための ML.NET コンポーネントです。このコンポーネントでは、`T` のインスタンスが取得され、そのデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="81611-157">The data reader is an ML.NET component to 'create' data: it takes an instance of `T` and returns data out of it.</span></span>

<span data-ttu-id="81611-158">注意すべき興味深い性質は、既存のデータ リーダーにトランスフォーマーをアタッチすることにより、データ リーダーを作成できることです。</span><span class="sxs-lookup"><span data-stu-id="81611-158">An interesting property to note is that you can create a data reader by attaching a transformer to an existing data reader.</span></span> <span data-ttu-id="81611-159">このようにして、トランスフォーマーの動作が組み込まれたリーダーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="81611-159">This way you can have a reader with transformation behavior baked in:</span></span>

```csharp
var newReader = reader.Append(transformer1).Append(transformer2)
```

<span data-ttu-id="81611-160">トランスフォーマーと似ているもう 1 つの点は、データは遅延評価されるため、"*リーダーも遅延である*" ことです。`reader.Read()` を呼び出した時点では、実際の "読み取り" はまったく (または最小限でしか) 行われません。結果のデータでカーソルが要求されたときにのみ、リーダーは処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="81611-160">Another similarity to transformers is that, since data is lazily evaluated, *readers are lazy*: no (or minimal) actual 'reading' happens when you call `reader.Read()`: only when a cursor is requested on the resulting data does the reader begin to work.</span></span>

## <a name="estimator"></a><span data-ttu-id="81611-161">エスティメーター</span><span class="sxs-lookup"><span data-stu-id="81611-161">Estimator</span></span>

<span data-ttu-id="81611-162">"*エスティメーター*" は、データから学習するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="81611-162">The *estimator* is an object that learns from data.</span></span> <span data-ttu-id="81611-163">学習の結果は "*トランスフォーマー*" です。</span><span class="sxs-lookup"><span data-stu-id="81611-163">The result of the learning is a *transformer*.</span></span>

<span data-ttu-id="81611-164">ML.NET では、この特性を使用して、異なるエスティメーターを連結する学習パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="81611-164">In ML.NET, use this property to create learning pipelines that chain together different estimators:</span></span>

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = mlContext.Transforms.CopyColumns("Label","FareAmount")
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("VendorId"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("RateCode"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("PaymentType"))
    .Append(mlContext.Transforms.Concatenate("Features","VendorId","RateCode","PassengerCount","TripTime","TripDistance","PaymentType"))
    .Append(mlContext.Regression.Trainers.FastTree("Label","Features"));

var model = pipeline.Fit(dataView);
```

<span data-ttu-id="81611-165">エスティメーターの 1 つの重要な特性は、"*エスティメーターは遅延ではなく一括である*" ということです。`Fit` のすべての呼び出しによって学習が発生し、その操作には時間がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81611-165">One important property of estimators is that *estimators are eager, not lazy*: every call to `Fit` is causing learning to happen, which is potentially a time-consuming operation.</span></span>

## <a name="prediction-function"></a><span data-ttu-id="81611-166">予測関数</span><span class="sxs-lookup"><span data-stu-id="81611-166">Prediction function</span></span>

<span data-ttu-id="81611-167">予測関数は、1 つの行に対してトランスフォーマーを適用するコンポーネントと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="81611-167">The prediction function can be seen as a component that applies a transformer to one row.</span></span>

<span data-ttu-id="81611-168">モデルを取得した後は (`Fit()` によってトレーニングされたか、またはどこかから読み込まれた "*トランスフォーマー*")、それを使用して、`model.Transform(data)` の通常の呼び出しで予測を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="81611-168">Once you get the model (a *transformer* either trained via `Fit()`, or loaded from somewhere), you can use it to make predictions using the normal calls to `model.Transform(data)`.</span></span> <span data-ttu-id="81611-169">ただし、実際のシナリオでこのモデルを使用するときは、通常、予測に多くの例を使用しません。</span><span class="sxs-lookup"><span data-stu-id="81611-169">However, when you use this model in a real-life scenario, you often don't have many examples to predict on.</span></span> <span data-ttu-id="81611-170">代わりに、一度に 1 つの例を使用し、すぐに適切なタイミングで予測を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="81611-170">Instead, you have one example at a time, and you need to make timely predictions on them immediately.</span></span>

<span data-ttu-id="81611-171">もちろん、これをバッチ予測に軽減できます。</span><span class="sxs-lookup"><span data-stu-id="81611-171">Of course, you can reduce this to the batch prediction:</span></span>

- <span data-ttu-id="81611-172">厳密に 1 つの行でデータ ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="81611-172">Create a data view with exactly one row.</span></span>
- <span data-ttu-id="81611-173">`model.Transform(data)` を呼び出して、予測されたデータ ビューを取得します。</span><span class="sxs-lookup"><span data-stu-id="81611-173">Call `model.Transform(data)` to get the predicted data view.</span></span>
- <span data-ttu-id="81611-174">結果のデータに対するカーソルを取得します。</span><span class="sxs-lookup"><span data-stu-id="81611-174">Get a cursor over the resulting data.</span></span>
- <span data-ttu-id="81611-175">カーソルを 1 ステップ進めて、最初の (そして唯一の) 行を取得します。</span><span class="sxs-lookup"><span data-stu-id="81611-175">Advance the cursor one step to get to the first (and only) row.</span></span>
- <span data-ttu-id="81611-176">それから予測される値を抽出します。</span><span class="sxs-lookup"><span data-stu-id="81611-176">Extract the predicted values out of it.</span></span>

<span data-ttu-id="81611-177">前記のアルゴリズムは、次のように[スキーマの理解](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md)と 2 つのユーザー定義オブジェクト `InputExample` と `OutputPrediction` を使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="81611-177">The preceding algorithm can be implemented using the [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), with two user-defined objects `InputExample` and `OutputPrediction` as follows:</span></span>

```csharp
var inputData = mlContext.Data.ReadFromEnumerable(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = mlContext.CreateEnumerable<OutputPrediction>(outputData,reuseRowObject:false).First();
```

<span data-ttu-id="81611-178">ただし、これは面倒で、パフォーマンス コストがかかります。</span><span class="sxs-lookup"><span data-stu-id="81611-178">But this is cumbersome and incurs performance costs.</span></span> <span data-ttu-id="81611-179">代わりに、予測関数オブジェクトでは、拡張メソッド `CreatePredictionEngine` により同じ処理が、ただしもっと速く便利に行われます。</span><span class="sxs-lookup"><span data-stu-id="81611-179">Instead, a prediction function object performs the same work, but faster and more convenient, via an extension method `CreatePredictionEngine`:</span></span>

```csharp
var predictionEngine = model.CreatePredictionEngine<InputExample,OutputPrediction>(mlContext);
var prediction = predictionEngine.Predict(example);
```

<span data-ttu-id="81611-180">予測関数は "*再入可能/スレッド セーフではありません*"。</span><span class="sxs-lookup"><span data-stu-id="81611-180">The prediction function is *not re-entrant / thread-safe*.</span></span> <span data-ttu-id="81611-181">複数のスレッドで同時に予測を実行する場合は、スレッドごとに予測関数が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81611-181">If you want to conduct predictions simultaneously with multiple threads, you need to have a prediction function per thread.</span></span>
