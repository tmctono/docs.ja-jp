---
title: データ変換
description: ML.NET でサポートされている機能エンジニアリングのコンポーネントについて検証します。
author: natke
ms.author: nakersha
ms.date: 04/02/2019
ms.openlocfilehash: cbcdef5b8f5f6334d5545f100976347ade9ee6fd
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671870"
---
# <a name="data-transformations"></a><span data-ttu-id="c9a91-103">データ変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-103">Data transformations</span></span>

<span data-ttu-id="c9a91-104">データ変換は次の操作を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9a91-104">Data transformations are used to:</span></span>
- <span data-ttu-id="c9a91-105">モデルのトレーニング用にデータを準備する</span><span class="sxs-lookup"><span data-stu-id="c9a91-105">prepare data for model training</span></span>
- <span data-ttu-id="c9a91-106">インポートされたモデルを TensorFlow または ONNX 形式に適用する</span><span class="sxs-lookup"><span data-stu-id="c9a91-106">apply an imported model in TensorFlow or ONNX format</span></span>
- <span data-ttu-id="c9a91-107">モデルから渡されたデータを後処理する</span><span class="sxs-lookup"><span data-stu-id="c9a91-107">post-process data after it has been passed through a model</span></span>

<span data-ttu-id="c9a91-108">このガイドの変換は、[IEstimator](xref:Microsoft.ML.IEstimator%601) インターフェイスを実装するクラスを返します。</span><span class="sxs-lookup"><span data-stu-id="c9a91-108">The transformations in this guide return classes that implement the [IEstimator](xref:Microsoft.ML.IEstimator%601) interface.</span></span> <span data-ttu-id="c9a91-109">データ変換はまとめて連結することができます。</span><span class="sxs-lookup"><span data-stu-id="c9a91-109">Data transformations can be chained together.</span></span> <span data-ttu-id="c9a91-110">各変換は、リンクされた参照ドキュメントで指定されている特定の種類および形式のデータを想定し、生成します。</span><span class="sxs-lookup"><span data-stu-id="c9a91-110">Each transformation both expects and produces data of specific types and formats, which are specified in the linked reference documentation.</span></span>

<span data-ttu-id="c9a91-111">一部のデータ変換には、そのパラメーターを計算するためにトレーニング データが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9a91-111">Some data transformations require training data to calculate their parameters.</span></span> <span data-ttu-id="c9a91-112">たとえば、<xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> トランスフォーマーは、`Fit()` の操作中にトレーニング データの平均と分散を計算し、`Transform()` 操作でそのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9a91-112">For example: the <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> transformer calculates the mean and variance of the training data during the `Fit()` operation, and uses those parameters in the `Transform()` operation.</span></span> 

<span data-ttu-id="c9a91-113">他のデータ変換はトレーニング データを必要としません。</span><span class="sxs-lookup"><span data-stu-id="c9a91-113">Other data transformations don't require training data.</span></span> <span data-ttu-id="c9a91-114">たとえば、<xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> の変換は、`Fit()` の操作中にトレーニング データを確認せずに `Transform()` の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9a91-114">For example: the <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> transformation can perform the `Transform()` operation without having seen any training data during the `Fit()` operation.</span></span>

## <a name="column-mapping-and-grouping"></a><span data-ttu-id="c9a91-115">列のマップとグループ化</span><span class="sxs-lookup"><span data-stu-id="c9a91-115">Column mapping and grouping</span></span>

| <span data-ttu-id="c9a91-116">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-116">Transform</span></span> | <span data-ttu-id="c9a91-117">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-117">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | <span data-ttu-id="c9a91-118">1 つ以上の入力列を新しい出力列に連結します</span><span class="sxs-lookup"><span data-stu-id="c9a91-118">Concatenate one or more input columns into a new output column</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | <span data-ttu-id="c9a91-119">1 つ以上の入力列をコピーして名前を変更します</span><span class="sxs-lookup"><span data-stu-id="c9a91-119">Copy and rename one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | <span data-ttu-id="c9a91-120">1 つ以上の入力列をドロップします</span><span class="sxs-lookup"><span data-stu-id="c9a91-120">Drop one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | <span data-ttu-id="c9a91-121">入力データから保持する 1 つ以上の列を選択します</span><span class="sxs-lookup"><span data-stu-id="c9a91-121">Select one or more columns to keep from the input data</span></span> |

## <a name="normalization-and-scaling"></a><span data-ttu-id="c9a91-122">正規化とスケーリング</span><span class="sxs-lookup"><span data-stu-id="c9a91-122">Normalization and scaling</span></span>

| <span data-ttu-id="c9a91-123">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-123">Transform</span></span> | <span data-ttu-id="c9a91-124">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-124">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | <span data-ttu-id="c9a91-125">(トレーニング データの) 平均を引き、(トレーニング データの) 分散で割ります</span><span class="sxs-lookup"><span data-stu-id="c9a91-125">Subtract the mean (of the training data) and divide by the variance (of the training data)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | <span data-ttu-id="c9a91-126">トレーニング データの対数に基づいて正規化します</span><span class="sxs-lookup"><span data-stu-id="c9a91-126">Normalize based on the logarithm of the training data</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | <span data-ttu-id="c9a91-127">入力ベクターを [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions) でスケーリングします。この p は 1、2、または無限大です。</span><span class="sxs-lookup"><span data-stu-id="c9a91-127">Scale input vectors by their [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), where p is 1, 2 or infinity.</span></span> <span data-ttu-id="c9a91-128">既定値は l2 (ユークリッド距離) ノルムです</span><span class="sxs-lookup"><span data-stu-id="c9a91-128">Defaults to the l2 (Euclidean distance) norm</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | <span data-ttu-id="c9a91-129">行データの平均を減算して行の各値をスケーリングし、標準偏差または (行データの) l2-norm で除算し、構成可能なスケール係数 (既定値は 2) で乗算します</span><span class="sxs-lookup"><span data-stu-id="c9a91-129">Scale each value in a row by subtracting the mean of the row data and divide by either the standard deviation or l2-norm (of the row data), and multiply by a configurable scale factor (default 2)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | <span data-ttu-id="c9a91-130">入力値をビンのインデックスに割り当て、ビンの数で除算して 0 から 1 の間の float 値を生成します。</span><span class="sxs-lookup"><span data-stu-id="c9a91-130">Assign the input value to a bin index and divide by the number of bins to produce a float value between 0 and 1.</span></span> <span data-ttu-id="c9a91-131">ビンの境界は、ビン全体にトレーニング データを均等に分散するように計算されます</span><span class="sxs-lookup"><span data-stu-id="c9a91-131">The bin boundaries are calculated to evenly distribute the training data across bins</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | <span data-ttu-id="c9a91-132">ラベル列との相関関係に基づいて入力値をビンに割り当てます</span><span class="sxs-lookup"><span data-stu-id="c9a91-132">Assign the input value to a bin based on its correlation with label column</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | <span data-ttu-id="c9a91-133">トレーニング データの最小値と最大値の差で入力をスケーリングします</span><span class="sxs-lookup"><span data-stu-id="c9a91-133">Scale the input by the difference between the minimum and maximum values in the training data</span></span> |

## <a name="conversions-between-data-types"></a><span data-ttu-id="c9a91-134">データ型間の変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-134">Conversions between data types</span></span>

| <span data-ttu-id="c9a91-135">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-135">Transform</span></span> | <span data-ttu-id="c9a91-136">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-136">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | <span data-ttu-id="c9a91-137">入力列の型を新しい型に変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-137">Convert the type of an input column to a new type</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue*> | <span data-ttu-id="c9a91-138">指定されたマッピングのディクショナリに基づいて、値をキー (カテゴリ) にマップします。</span><span class="sxs-lookup"><span data-stu-id="c9a91-138">Map values to keys (categories) based on the supplied dictionary of mappings</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*> | <span data-ttu-id="c9a91-139">入力データからマッピングを作成して値をキー (カテゴリ) にマップします</span><span class="sxs-lookup"><span data-stu-id="c9a91-139">Map values to keys (categories) by creating the mapping from the input data</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue*> | <span data-ttu-id="c9a91-140">キーを変換して元の値に戻します</span><span class="sxs-lookup"><span data-stu-id="c9a91-140">Convert keys back to their original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector*> | <span data-ttu-id="c9a91-141">キーを変換して元の値のベクターに戻します</span><span class="sxs-lookup"><span data-stu-id="c9a91-141">Convert keys back to vectors of original values</span></span> |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector*> | <span data-ttu-id="c9a91-142">キーを変換して元の値のバイナリ ベクターに戻します</span><span class="sxs-lookup"><span data-stu-id="c9a91-142">Convert keys back to a binary vector of original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash*> | <span data-ttu-id="c9a91-143">入力列の値をハッシュします</span><span class="sxs-lookup"><span data-stu-id="c9a91-143">Hash the value in the input column</span></span> |

## <a name="text-transformations"></a><span data-ttu-id="c9a91-144">テキスト変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-144">Text transformations</span></span>

| <span data-ttu-id="c9a91-145">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-145">Transform</span></span> | <span data-ttu-id="c9a91-146">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-146">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText*> | <span data-ttu-id="c9a91-147">テキスト列を正規化された ngram と char-gram のカウントの float 配列に変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-147">Transform a text column into a float array of normalized ngrams and char-grams counts</span></span> | 
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords*> | <span data-ttu-id="c9a91-148">1 つ以上のテキスト列を個々の単語に分割します</span><span class="sxs-lookup"><span data-stu-id="c9a91-148">Split one or more text columns into individual words</span></span> |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys*> | <span data-ttu-id="c9a91-149">1 つ以上のテキスト列を一連のトピックに関する個々の文字 float に分割します</span><span class="sxs-lookup"><span data-stu-id="c9a91-149">Split one or more text columns into individual characters floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.NormalizeText*> | <span data-ttu-id="c9a91-150">大文字と小文字の変更、分音記号、句読点、数字の削除を行います</span><span class="sxs-lookup"><span data-stu-id="c9a91-150">Change case, remove diacritical marks, punctuation marks, and numbers</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams*> | <span data-ttu-id="c9a91-151">テキスト列を ngram のカウント (連続する単語のシーケンス) バッグに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-151">Transform text column into a bag of counts of ngrams (sequences of consecutive words)</span></span>|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags*> | <span data-ttu-id="c9a91-152">テキスト列を ngram ベクターのバッグに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-152">Transform text column into a bag of counts of ngrams vector</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams*> | <span data-ttu-id="c9a91-153">テキスト列をハッシュされた ngram のカウントのベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-153">Transform text column into a vector of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags*> | <span data-ttu-id="c9a91-154">テキスト列をハッシュされた ngram のカウントのバッグに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-154">Transform text column into a bag of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords*>  | <span data-ttu-id="c9a91-155">指定された言語の既定のストップ ワードを入力列から削除します</span><span class="sxs-lookup"><span data-stu-id="c9a91-155">Remove default stop words for the specified language from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords*> | <span data-ttu-id="c9a91-156">入力列から指定されたストップ ワードを削除します</span><span class="sxs-lookup"><span data-stu-id="c9a91-156">Removes specified stop words from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation*> | <span data-ttu-id="c9a91-157">一連のトピックにわたって、ドキュメント (float のベクターとして表されます) を float のベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-157">Transform a document (represented as a vector of floats) into a vector of floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding*> | <span data-ttu-id="c9a91-158">レーニング済みのモデルを使用して、テキスト トークンを文のベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-158">Convert vectors of text tokens into sentence vectors using a pre-trained model</span></span> |

## <a name="image-transformations"></a><span data-ttu-id="c9a91-159">画像変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-159">Image transformations</span></span>

| <span data-ttu-id="c9a91-160">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-160">Transform</span></span> | <span data-ttu-id="c9a91-161">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-161">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> | <span data-ttu-id="c9a91-162">画像をグレースケールに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-162">Convert an image to grayscale</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage*> | <span data-ttu-id="c9a91-163">ピクセルのベクターを <xref:Microsoft.ML.Transforms.Image.ImageDataViewType> に変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-163">Convert a vector of pixels to <xref:Microsoft.ML.Transforms.Image.ImageDataViewType></span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*> | <span data-ttu-id="c9a91-164">入力画像のピクセルを数値のベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-164">Convert pixels from input image into a vector of numbers</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*> | <span data-ttu-id="c9a91-165">フォルダーの画像をメモリに読み込みます</span><span class="sxs-lookup"><span data-stu-id="c9a91-165">Load images from a folder into memory</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*> | <span data-ttu-id="c9a91-166">イメージのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="c9a91-166">Resize images</span></span> |
| <xref:Microsoft.ML.OnnxCatalog.DnnFeaturizeImage*> | <span data-ttu-id="c9a91-167">事前トレーニング済みのディープ ニューラル ネットワーク (DNN) モデルを適用して、入力イメージを特徴ベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-167">Applies a pre-trained deep neural network (DNN) model to transform an input image into a feature vector</span></span> |

## <a name="categorical-data-transformations"></a><span data-ttu-id="c9a91-168">分類データの変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-168">Categorical data transformations</span></span>

| <span data-ttu-id="c9a91-169">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-169">Transform</span></span> | <span data-ttu-id="c9a91-170">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-170">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*> | <span data-ttu-id="c9a91-171">1 つ以上のテキスト列を [one-hot](https://en.wikipedia.org/wiki/One-hot) エンコード済みベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-171">Convert one or more text columns into [one-hot](https://en.wikipedia.org/wiki/One-hot) encoded vectors</span></span> |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding*> | <span data-ttu-id="c9a91-172">1 つまたは複数のテキスト列をハッシュベースの one-hot エンコード済みベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-172">Convert one or more text columns into hash-based one-hot encoded vectors</span></span> |

## <a name="time-series-data-transformations"></a><span data-ttu-id="c9a91-173">時系列データの変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-173">Time series data transformations</span></span>

| <span data-ttu-id="c9a91-174">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-174">Transform</span></span> | <span data-ttu-id="c9a91-175">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-175">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectAnomalyBySrCnn*> | <span data-ttu-id="c9a91-176">Spectral Residual (SR) アルゴリズムを使用して、時系列入力データの異常を検出します</span><span class="sxs-lookup"><span data-stu-id="c9a91-176">Detect anomalies in the input time series data using the Spectral Residual (SR) algorithm</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectChangePointBySsa*> | <span data-ttu-id="c9a91-177">単一のスペクトラム分析 (SSA) を使用して、時系列データの変化点を検出します</span><span class="sxs-lookup"><span data-stu-id="c9a91-177">Detect change points in time series data using singular spectrum analysis (SSA)</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidChangePoint*> | <span data-ttu-id="c9a91-178">アダプティブ カーネル密度見積もりとマルチンゲール スコアを使用して、独立同分布 (IID) の時系列データ内の変化点を検出します</span><span class="sxs-lookup"><span data-stu-id="c9a91-178">Detect change points in independent and identically distributed (IID) time series data using adaptive kernel density estimations and martingale scores</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa*> | <span data-ttu-id="c9a91-179">単一のスペクトラム分析 (SSA) を使用して、時系列データを予測します</span><span class="sxs-lookup"><span data-stu-id="c9a91-179">Forecast time series data using singular spectrum analysis (SSA)</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectSpikeBySsa*> | <span data-ttu-id="c9a91-180">単一のスペクトラム分析 (SSA) を使用して、時系列データのスパイクを検出します</span><span class="sxs-lookup"><span data-stu-id="c9a91-180">Detect spikes in time series data using singular spectrum analysis (SSA)</span></span> |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidSpike*> | <span data-ttu-id="c9a91-181">アダプティブ カーネル密度見積もりとマルチンゲール スコアを使用して、独立同分布 (IID) の時系列データのスパイクを検出します</span><span class="sxs-lookup"><span data-stu-id="c9a91-181">Detect spikes in independent and identically distributed (IID) time series data using adaptive kernel density estimations and martingale scores</span></span> |

## <a name="missing-values"></a><span data-ttu-id="c9a91-182">欠損値</span><span class="sxs-lookup"><span data-stu-id="c9a91-182">Missing values</span></span>

| <span data-ttu-id="c9a91-183">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-183">Transform</span></span> | <span data-ttu-id="c9a91-184">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-184">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues*> | <span data-ttu-id="c9a91-185">新しいブール出力列を作成します。入力列の値が欠落している場合、その値は true です。</span><span class="sxs-lookup"><span data-stu-id="c9a91-185">Create a new boolean output column, the value of which is true when the value in the input column is missing</span></span> |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*> | <span data-ttu-id="c9a91-186">新しい出力列を作成します。値が入力列にない場合は値が既定値に設定され、それ以外の場合は入力値が設定されます</span><span class="sxs-lookup"><span data-stu-id="c9a91-186">Create a new output column, the value of which is set to a default value if the value is missing from the input column, and the input value otherwise</span></span> |

## <a name="feature-selection"></a><span data-ttu-id="c9a91-187">フィーチャーの選択</span><span class="sxs-lookup"><span data-stu-id="c9a91-187">Feature selection</span></span>

| <span data-ttu-id="c9a91-188">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-188">Transform</span></span> | <span data-ttu-id="c9a91-189">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-189">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount*> | <span data-ttu-id="c9a91-190">既定以外の値がしきい値より大きい特徴を選択します</span><span class="sxs-lookup"><span data-stu-id="c9a91-190">Select features whose non-default values are greater than a threshold</span></span> |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation*> | <span data-ttu-id="c9a91-191">ラベル列のデータが最も依存している特徴を選択します</span><span class="sxs-lookup"><span data-stu-id="c9a91-191">Select the features on which the data in the label column is most dependent</span></span> |

## <a name="feature-transformations"></a><span data-ttu-id="c9a91-192">特徴の変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-192">Feature transformations</span></span>

| <span data-ttu-id="c9a91-193">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-193">Transform</span></span> | <span data-ttu-id="c9a91-194">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-194">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.KernelExpansionCatalog.ApproximatedKernelMap*> | <span data-ttu-id="c9a91-195">各入力ベクターを下位次元の特徴空間にマップします。ここでは、線形アルゴリズムへの入力として特徴を使用できるように、内部製品でカーネル関数が概算されます</span><span class="sxs-lookup"><span data-stu-id="c9a91-195">Map each input vector onto a lower dimensional feature space, where inner products approximate a kernel function, so that the features can be used as inputs to the linear algorithms</span></span> |
| <xref:Microsoft.ML.PcaCatalog.ProjectToPrincipalComponents*> | <span data-ttu-id="c9a91-196">プリンシパル コンポーネント分析アルゴリズムを適用して、入力特徴ベクトルの次元を減らします</span><span class="sxs-lookup"><span data-stu-id="c9a91-196">Reduce the dimensions of the input feature vector by applying the Principal Component Analysis algorithm</span></span> |

## <a name="explainability-transformations"></a><span data-ttu-id="c9a91-197">説明可能性の変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-197">Explainability transformations</span></span>

| <span data-ttu-id="c9a91-198">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-198">Transform</span></span> | <span data-ttu-id="c9a91-199">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-199">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ExplainabilityCatalog.CalculateFeatureContribution*> | <span data-ttu-id="c9a91-200">特徴ベクターの要素ごとにコントリビューション スコアを計算します</span><span class="sxs-lookup"><span data-stu-id="c9a91-200">Calculate contribution scores for each element of a feature vector</span></span> |

## <a name="calibration-transformations"></a><span data-ttu-id="c9a91-201">調整の変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-201">Calibration transformations</span></span>

| <span data-ttu-id="c9a91-202">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-202">Transform</span></span> | <span data-ttu-id="c9a91-203">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-203">Definition</span></span> |
| --- | --- |
|<xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.String%2CSystem.String%2CSystem.String%29> | <span data-ttu-id="c9a91-204">トレーニング データを使用して予測されるパラメーターと共にロジスティック回帰を使用し、二項分類子の生スコアをクラスの確率に変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-204">Transforms a binary classifier raw score into a class probability using logistic regression with parameters estimated using the training data</span></span> |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.Double%2CSystem.Double%2CSystem.String%29> | <span data-ttu-id="c9a91-205">固定パラメーターと共にロジスティック回帰を使用して、二項分類子の生スコアをクラスの確率に変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-205">Transforms a binary classifier raw score into a class probability using logistic regression with fixed parameters</span></span> |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Naive*> | <span data-ttu-id="c9a91-206">スコアをビンに割り当て、ビン間の分布に基づいて確率を計算して、二項分類子の生スコアをクラスの確率に変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-206">Transforms a binary classifier raw score into a class probability by assigning scores to bins, and calculating the probability based on the distribution among the bins</span></span> |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Isotonic*> | <span data-ttu-id="c9a91-207">スコアをビンに割り当てて、二項分類子の生スコアをクラスの確率に変換します。このとき、境界の位置とビンのサイズは、トレーニング データを使用して推定されます</span><span class="sxs-lookup"><span data-stu-id="c9a91-207">Transforms a binary classifier raw score into a class probability by assigning scores to bins, where the position of boundaries and the size of bins are estimated using the training data</span></span>  |

## <a name="deep-learning-transformations"></a><span data-ttu-id="c9a91-208">ディープ ラーニングの変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-208">Deep learning transformations</span></span>

| <span data-ttu-id="c9a91-209">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-209">Transform</span></span> | <span data-ttu-id="c9a91-210">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-210">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel*> | <span data-ttu-id="c9a91-211">インポートされた ONNX モデルを使用して入力データを変換する</span><span class="sxs-lookup"><span data-stu-id="c9a91-211">Transform the input data with an imported ONNX model</span></span> |
| <xref:Microsoft.ML.TensorflowCatalog.LoadTensorFlowModel*> | <span data-ttu-id="c9a91-212">インポートされた TensorFlow モデルを使用して入力データを変換する</span><span class="sxs-lookup"><span data-stu-id="c9a91-212">Transform the input data with an imported TensorFlow model</span></span> |

## <a name="custom-transformations"></a><span data-ttu-id="c9a91-213">カスタム変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-213">Custom transformations</span></span>

| <span data-ttu-id="c9a91-214">変換</span><span class="sxs-lookup"><span data-stu-id="c9a91-214">Transform</span></span> | <span data-ttu-id="c9a91-215">定義</span><span class="sxs-lookup"><span data-stu-id="c9a91-215">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping*> | <span data-ttu-id="c9a91-216">ユーザー定義マッピングを使用して既存の列を新しい列に変換します</span><span class="sxs-lookup"><span data-stu-id="c9a91-216">Transform existing columns onto new ones with a user-defined mapping</span></span> |
