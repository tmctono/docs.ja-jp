---
title: データ変換
description: ML.NET でサポートされている機能エンジニアリングのコンポーネントについて検証します。
author: natke
ms.author: nakersha
ms.date: 04/02/2019
ms.openlocfilehash: 7ea06e19b4651017079a6ae57136f033e0ce981c
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "65558013"
---
# <a name="data-transformations"></a><span data-ttu-id="395f8-103">データ変換</span><span class="sxs-lookup"><span data-stu-id="395f8-103">Data transformations</span></span>

<span data-ttu-id="395f8-104">データ変換は、モデルのトレーニング用データを準備するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="395f8-104">Data transformations are used to prepare data for model training.</span></span> <span data-ttu-id="395f8-105">このガイドの変換は、[IEstimator](xref:Microsoft.ML.IEstimator%601) インターフェイスを実装するクラスを返します。</span><span class="sxs-lookup"><span data-stu-id="395f8-105">The transformations in this guide return classes that implement the [IEstimator](xref:Microsoft.ML.IEstimator%601) interface.</span></span> <span data-ttu-id="395f8-106">データ変換はまとめて連結することができます。</span><span class="sxs-lookup"><span data-stu-id="395f8-106">Data transformations can be chained together.</span></span> <span data-ttu-id="395f8-107">各変換は、リンクされた参照ドキュメントで指定されている特定の種類および形式のデータを想定し、生成します。</span><span class="sxs-lookup"><span data-stu-id="395f8-107">Each transformation both expects and produces data of specific types and formats, which are specified in the linked reference documentation.</span></span>

<span data-ttu-id="395f8-108">一部のデータ変換には、そのパラメーターを計算するためにトレーニング データが必要です。</span><span class="sxs-lookup"><span data-stu-id="395f8-108">Some data transformations require training data to calculate their parameters.</span></span> <span data-ttu-id="395f8-109">たとえば、<xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> トランスフォーマーは、`Fit()` の操作中にトレーニング データの平均と分散を計算し、`Transform()` 操作でそのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="395f8-109">For example: the <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> transformer calculates the mean and variance of the training data during the `Fit()` operation, and uses those parameters in the `Transform()` operation.</span></span> 

<span data-ttu-id="395f8-110">他のデータ変換はトレーニング データを必要としません。</span><span class="sxs-lookup"><span data-stu-id="395f8-110">Other data transformations don't require training data.</span></span> <span data-ttu-id="395f8-111">たとえば、<xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> の変換は、`Fit()` の操作中にトレーニング データを確認せずに `Transform()` の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="395f8-111">For example: the <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> transformation can perform the `Transform()` operation without having seen any training data during the `Fit()` operation.</span></span>

## <a name="column-mapping-and-grouping"></a><span data-ttu-id="395f8-112">列のマップとグループ化</span><span class="sxs-lookup"><span data-stu-id="395f8-112">Column mapping and grouping</span></span>

| <span data-ttu-id="395f8-113">変換</span><span class="sxs-lookup"><span data-stu-id="395f8-113">Transform</span></span> | <span data-ttu-id="395f8-114">定義</span><span class="sxs-lookup"><span data-stu-id="395f8-114">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | <span data-ttu-id="395f8-115">1 つ以上の入力列を新しい出力列に連結します</span><span class="sxs-lookup"><span data-stu-id="395f8-115">Concatenate one or more input columns into a new output column</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | <span data-ttu-id="395f8-116">1 つ以上の入力列をコピーして名前を変更します</span><span class="sxs-lookup"><span data-stu-id="395f8-116">Copy and rename one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | <span data-ttu-id="395f8-117">1 つ以上の入力列をドロップします</span><span class="sxs-lookup"><span data-stu-id="395f8-117">Drop one or more input columns</span></span> |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | <span data-ttu-id="395f8-118">入力データから保持する 1 つ以上の列を選択します</span><span class="sxs-lookup"><span data-stu-id="395f8-118">Select one or more columns to keep from the input data</span></span> |

## <a name="normalization-and-scaling"></a><span data-ttu-id="395f8-119">正規化とスケーリング</span><span class="sxs-lookup"><span data-stu-id="395f8-119">Normalization and scaling</span></span>

| <span data-ttu-id="395f8-120">変換</span><span class="sxs-lookup"><span data-stu-id="395f8-120">Transform</span></span> | <span data-ttu-id="395f8-121">定義</span><span class="sxs-lookup"><span data-stu-id="395f8-121">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | <span data-ttu-id="395f8-122">(トレーニング データの) 平均を引き、(トレーニング データの) 分散で割ります</span><span class="sxs-lookup"><span data-stu-id="395f8-122">Subtract the mean (of the training data) and divide by the variance (of the training data)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | <span data-ttu-id="395f8-123">トレーニング データの対数に基づいて正規化します</span><span class="sxs-lookup"><span data-stu-id="395f8-123">Normalize based on the logarithm of the training data</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | <span data-ttu-id="395f8-124">入力ベクターを [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions) でスケーリングします。この p は 1、2、または無限大です。</span><span class="sxs-lookup"><span data-stu-id="395f8-124">Scale input vectors by their [lp-norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), where p is 1, 2 or infinity.</span></span> <span data-ttu-id="395f8-125">既定値は l2 (ユークリッド距離) ノルムです</span><span class="sxs-lookup"><span data-stu-id="395f8-125">Defaults to the l2 (Euclidean distance) norm</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | <span data-ttu-id="395f8-126">行データの平均を減算して行の各値をスケーリングし、標準偏差または (行データの) l2-norm で除算し、構成可能なスケール係数 (既定値は 2) で乗算します</span><span class="sxs-lookup"><span data-stu-id="395f8-126">Scale each value in a row by subtracting the mean of the row data and divide by either the standard deviation or l2-norm (of the row data), and multiply by a configurable scale factor (default 2)</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | <span data-ttu-id="395f8-127">入力値をビンのインデックスに割り当て、ビンの数で除算して 0 から 1 の間の float 値を生成します。</span><span class="sxs-lookup"><span data-stu-id="395f8-127">Assign the input value to a bin index and divide by the number of bins to produce a float value between 0 and 1.</span></span> <span data-ttu-id="395f8-128">ビンの境界は、ビン全体にトレーニング データを均等に分散するように計算されます</span><span class="sxs-lookup"><span data-stu-id="395f8-128">The bin boundaries are calculated to evenly distribute the training data across bins</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | <span data-ttu-id="395f8-129">ラベル列との相関関係に基づいて入力値をビンに割り当てます</span><span class="sxs-lookup"><span data-stu-id="395f8-129">Assign the input value to a bin based on its correlation with label column</span></span> |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | <span data-ttu-id="395f8-130">トレーニング データの最小値と最大値の差で入力をスケーリングします</span><span class="sxs-lookup"><span data-stu-id="395f8-130">Scale the input by the difference between the minimum and maximum values in the training data</span></span> |

## <a name="conversions-between-data-types"></a><span data-ttu-id="395f8-131">データ型間の変換</span><span class="sxs-lookup"><span data-stu-id="395f8-131">Conversions between data types</span></span>

| <span data-ttu-id="395f8-132">変換</span><span class="sxs-lookup"><span data-stu-id="395f8-132">Transform</span></span> | <span data-ttu-id="395f8-133">定義</span><span class="sxs-lookup"><span data-stu-id="395f8-133">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | <span data-ttu-id="395f8-134">入力列の型を新しい型に変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-134">Convert the type of an input column to a new type</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue*> | <span data-ttu-id="395f8-135">指定されたマッピングのディクショナリに基づいて、値をキー (カテゴリ) にマップします。</span><span class="sxs-lookup"><span data-stu-id="395f8-135">Map values to keys (categories) based on the supplied dictionary of mappings</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey*> | <span data-ttu-id="395f8-136">入力データからマッピングを作成して値をキー (カテゴリ) にマップします</span><span class="sxs-lookup"><span data-stu-id="395f8-136">Map values to keys (categories) by creating the mapping from the input data</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue*> | <span data-ttu-id="395f8-137">キーを変換して元の値に戻します</span><span class="sxs-lookup"><span data-stu-id="395f8-137">Convert keys back to their original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector*> | <span data-ttu-id="395f8-138">キーを変換して元の値のベクターに戻します</span><span class="sxs-lookup"><span data-stu-id="395f8-138">Convert keys back to vectors of original values</span></span> |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector*> | <span data-ttu-id="395f8-139">キーを変換して元の値のバイナリ ベクターに戻します</span><span class="sxs-lookup"><span data-stu-id="395f8-139">Convert keys back to a binary vector of original values</span></span> |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash*> | <span data-ttu-id="395f8-140">入力列の値をハッシュします</span><span class="sxs-lookup"><span data-stu-id="395f8-140">Hash the value in the input column</span></span> |

## <a name="text-transformations"></a><span data-ttu-id="395f8-141">テキスト変換</span><span class="sxs-lookup"><span data-stu-id="395f8-141">Text transformations</span></span>

| <span data-ttu-id="395f8-142">変換</span><span class="sxs-lookup"><span data-stu-id="395f8-142">Transform</span></span> | <span data-ttu-id="395f8-143">定義</span><span class="sxs-lookup"><span data-stu-id="395f8-143">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText*> | <span data-ttu-id="395f8-144">テキスト列を正規化された ngram と char-gram のカウントの float 配列に変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-144">Transform a text column into a float array of normalized ngrams and char-grams counts</span></span> | 
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords*> | <span data-ttu-id="395f8-145">1 つ以上のテキスト列を個々の単語に分割します</span><span class="sxs-lookup"><span data-stu-id="395f8-145">Split one or more text columns into individual words</span></span> |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys*> | <span data-ttu-id="395f8-146">1 つ以上のテキスト列を一連のトピックに関する個々の文字 float に分割します</span><span class="sxs-lookup"><span data-stu-id="395f8-146">Split one or more text columns into individual characters floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.NormalizeText*> | <span data-ttu-id="395f8-147">大文字と小文字の変更、分音記号、句読点、および数字の削除</span><span class="sxs-lookup"><span data-stu-id="395f8-147">Change case, remove diacritical marks, punctuation marks and numbers</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams*> | <span data-ttu-id="395f8-148">テキスト列を ngram のカウント (連続する単語のシーケンス) バッグに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-148">Transform text column into a bag of counts of ngrams (sequences of consecutive words)</span></span>|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags*> | <span data-ttu-id="395f8-149">テキスト列を ngram ベクターのバッグに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-149">Transform text column into a bag of counts of ngrams vector</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams*> | <span data-ttu-id="395f8-150">テキスト列をハッシュされた ngram のカウントのベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-150">Transform text column into a vector of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags*> | <span data-ttu-id="395f8-151">テキスト列をハッシュされた ngram のカウントのバッグに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-151">Transform text column into a bag of hashed ngram counts</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords*>  | <span data-ttu-id="395f8-152">指定された言語の既定のストップ ワードを入力列から削除します</span><span class="sxs-lookup"><span data-stu-id="395f8-152">Remove default stop words for the specified language from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords*> | <span data-ttu-id="395f8-153">入力列から指定されたストップ ワードを削除します</span><span class="sxs-lookup"><span data-stu-id="395f8-153">Removes specified stop words from input columns</span></span> |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation*> | <span data-ttu-id="395f8-154">一連のトピックにわたって、ドキュメント (float のベクターとして表されます) を float のベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-154">Transform a document (represented as a vector of floats) into a vector of floats over a set of topics</span></span> |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding*> | <span data-ttu-id="395f8-155">レーニング済みのモデルを使用して、テキスト トークンを文のベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-155">Convert vectors of text tokens into sentence vectors using a pre-trained model</span></span> |

## <a name="image-transformations"></a><span data-ttu-id="395f8-156">画像変換</span><span class="sxs-lookup"><span data-stu-id="395f8-156">Image transformations</span></span>

| <span data-ttu-id="395f8-157">変換</span><span class="sxs-lookup"><span data-stu-id="395f8-157">Transform</span></span> | <span data-ttu-id="395f8-158">定義</span><span class="sxs-lookup"><span data-stu-id="395f8-158">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale*> | <span data-ttu-id="395f8-159">画像をグレースケールに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-159">Convert an image to grayscale</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage*> | <span data-ttu-id="395f8-160">ピクセルのベクターを <xref:Microsoft.ML.Transforms.Image.ImageDataViewType> に変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-160">Convert a vector of pixels to <xref:Microsoft.ML.Transforms.Image.ImageDataViewType></span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels*> | <span data-ttu-id="395f8-161">入力画像のピクセルを数値のベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-161">Convert pixels from input image into a vector of numbers</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages*> | <span data-ttu-id="395f8-162">フォルダーの画像をメモリに読み込みます</span><span class="sxs-lookup"><span data-stu-id="395f8-162">Load images from a folder into memory</span></span> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages*> | <span data-ttu-id="395f8-163">イメージのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="395f8-163">Resize images</span></span> |

## <a name="categorical-data-transformations"></a><span data-ttu-id="395f8-164">分類データの変換</span><span class="sxs-lookup"><span data-stu-id="395f8-164">Categorical data transformations</span></span>

| <span data-ttu-id="395f8-165">変換</span><span class="sxs-lookup"><span data-stu-id="395f8-165">Transform</span></span> | <span data-ttu-id="395f8-166">定義</span><span class="sxs-lookup"><span data-stu-id="395f8-166">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*> | <span data-ttu-id="395f8-167">1 つ以上のテキスト列を [one-hot](https://en.wikipedia.org/wiki/One-hot) エンコード済みベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-167">Convert one or more text columns into [one-hot](https://en.wikipedia.org/wiki/One-hot) encoded vectors</span></span> |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding*> | <span data-ttu-id="395f8-168">もう 1 つのテキスト列をハッシュベースの one-hot エンコード済みベクターに変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-168">Convert one more text columns into hash-based one-hot encoded vectors</span></span> |

## <a name="missing-values"></a><span data-ttu-id="395f8-169">欠損値</span><span class="sxs-lookup"><span data-stu-id="395f8-169">Missing values</span></span>

| <span data-ttu-id="395f8-170">変換</span><span class="sxs-lookup"><span data-stu-id="395f8-170">Transform</span></span> | <span data-ttu-id="395f8-171">定義</span><span class="sxs-lookup"><span data-stu-id="395f8-171">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues*> | <span data-ttu-id="395f8-172">新しいブール出力列を作成します。入力列の値が欠落している場合、その値は true です。</span><span class="sxs-lookup"><span data-stu-id="395f8-172">Create a new boolean output column, the value of which is true when the value in the input column is missing</span></span> |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*> | <span data-ttu-id="395f8-173">新しい出力列を作成します。値が入力列にない場合は値が既定値に設定され、それ以外の場合は入力値が設定されます</span><span class="sxs-lookup"><span data-stu-id="395f8-173">Create a new output column, the value of which is set to a default value if the value is missing from the input column, and the input value otherwise</span></span> |

## <a name="feature-selection"></a><span data-ttu-id="395f8-174">フィーチャーの選択</span><span class="sxs-lookup"><span data-stu-id="395f8-174">Feature selection</span></span>

| <span data-ttu-id="395f8-175">変換</span><span class="sxs-lookup"><span data-stu-id="395f8-175">Transform</span></span> | <span data-ttu-id="395f8-176">定義</span><span class="sxs-lookup"><span data-stu-id="395f8-176">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount*> | <span data-ttu-id="395f8-177">既定以外の値がしきい値より大きい特徴を選択します</span><span class="sxs-lookup"><span data-stu-id="395f8-177">Select features whose non-default values are greater than a threshold</span></span> |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation*> | <span data-ttu-id="395f8-178">ラベル列のデータが最も依存している特徴を選択します</span><span class="sxs-lookup"><span data-stu-id="395f8-178">Select the features on which the data in the label column is most dependent</span></span> |

## <a name="custom-transformations"></a><span data-ttu-id="395f8-179">カスタム変換</span><span class="sxs-lookup"><span data-stu-id="395f8-179">Custom transformations</span></span>

| <span data-ttu-id="395f8-180">変換</span><span class="sxs-lookup"><span data-stu-id="395f8-180">Transform</span></span> | <span data-ttu-id="395f8-181">定義</span><span class="sxs-lookup"><span data-stu-id="395f8-181">Definition</span></span> |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping*> | <span data-ttu-id="395f8-182">ユーザー定義マッピングを使用して既存の列を新しい列に変換します</span><span class="sxs-lookup"><span data-stu-id="395f8-182">Transform existing columns onto new ones with a user-defined mapping</span></span> |
