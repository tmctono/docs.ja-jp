---
title: 機械学習の用語集
description: ML.NET でカスタム モデルをビルドする際に役立つ機械学習の重要な用語の用語集。
ms.custom: seodec18
ms.topic: reference
ms.date: 07/31/2019
ms.openlocfilehash: 1c979d2c4567285146ab87f359116efb506815a1
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710536"
---
# <a name="machine-learning-glossary-of-important-terms"></a><span data-ttu-id="6b5be-103">機械学習の重要な用語の用語集</span><span class="sxs-lookup"><span data-stu-id="6b5be-103">Machine learning glossary of important terms</span></span>

<span data-ttu-id="6b5be-104">ML.NET でカスタム モデルをビルドする際に役立つ機械学習の重要な用語を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-104">The following list is a compilation of important machine learning terms that are useful as you build your custom models in ML.NET.</span></span>

## <a name="accuracy"></a><span data-ttu-id="6b5be-105">正確度</span><span class="sxs-lookup"><span data-stu-id="6b5be-105">Accuracy</span></span>

<span data-ttu-id="6b5be-106">[分類](#classification)における正確度は、正しく分類された項目の数をテスト セット内の項目の総数で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-106">In [classification](#classification), accuracy is the number of correctly classified items divided by the total number of items in the test set.</span></span> <span data-ttu-id="6b5be-107">0 (正確度が最も低い) ～ 1 (正確度が最も高い) の値になります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-107">Ranges from 0 (least accurate) to 1 (most accurate).</span></span> <span data-ttu-id="6b5be-108">正確度は、モデル パフォーマンスの評価メトリックの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-108">Accuracy is one of evaluation metrics of the model performance.</span></span> <span data-ttu-id="6b5be-109">[精度](#precision)、[再現率](#recall)、および [F 値](#f-score)と併せて考慮してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-109">Consider it in conjunction with [precision](#precision), [recall](#recall), and [F-score](#f-score).</span></span>

## <a name="area-under-the-curve-auc"></a><span data-ttu-id="6b5be-110">曲線下面積 (AUC)</span><span class="sxs-lookup"><span data-stu-id="6b5be-110">Area under the curve (AUC)</span></span>

<span data-ttu-id="6b5be-111">[二項分類](#binary-classification)における評価メトリックであり、偽陽性率 (x 軸上) に対する真陽性率 (y 軸上) を描画する曲線下面積の値です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-111">In [binary classification](#binary-classification), an evaluation metric that is the value of the area under the curve that plots the true positives rate (on the y-axis) against the false positives rate (on the x-axis).</span></span> <span data-ttu-id="6b5be-112">0\.5 (最低) ～ 1 (最高) の値になります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-112">Ranges from 0.5 (worst) to 1 (best).</span></span> <span data-ttu-id="6b5be-113">ROC 曲線 (受信者操作特性曲線) 下面積とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-113">Also known as the area under the ROC curve, i.e., receiver operating characteristic curve.</span></span> <span data-ttu-id="6b5be-114">詳しくは、Wikipedia の[受信者操作特性](https://en.wikipedia.org/wiki/Receiver_operating_characteristic)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-114">For more information, see the [Receiver operating characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) article on Wikipedia.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="6b5be-115">二項分類</span><span class="sxs-lookup"><span data-stu-id="6b5be-115">Binary classification</span></span>

<span data-ttu-id="6b5be-116">[ラベル](#label)が 2 つのクラスのうちの 1 つである[分類](#classification)です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-116">A [classification](#classification) case where the [label](#label) is only one out of two classes.</span></span> <span data-ttu-id="6b5be-117">詳細については、トピック「[機械学習のタスク](tasks.md)」のセクションの「[二項分類](tasks.md#binary-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-117">For more information, see the [Binary classification](tasks.md#binary-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="calibration"></a><span data-ttu-id="6b5be-118">調整</span><span class="sxs-lookup"><span data-stu-id="6b5be-118">Calibration</span></span>

<span data-ttu-id="6b5be-119">調整は、二項分類と多クラス分類のために、生のスコアをクラスのメンバーシップにマップするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-119">Calibration is the process of mapping a raw score onto a class membership, for binary and multiclass classification.</span></span> <span data-ttu-id="6b5be-120">一部 ML.NET トレーナーには `NonCalibrated` サフィックスがあります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-120">Some ML.NET trainers have a `NonCalibrated` suffix.</span></span> <span data-ttu-id="6b5be-121">これらのアルゴリズムからは、後でクラスの確率にマップする必要がある生のスコアが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-121">These algorithms produce a raw score that then must be mapped to a class probability.</span></span> 

## <a name="catalog"></a><span data-ttu-id="6b5be-122">Catalog</span><span class="sxs-lookup"><span data-stu-id="6b5be-122">Catalog</span></span> 

<span data-ttu-id="6b5be-123">ML.NET では、カタログは、共通の目的でグループ化された拡張機能のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-123">In ML.NET, a catalog is a collection of extension functions, grouped by a common purpose.</span></span>

<span data-ttu-id="6b5be-124">たとえば、各機械学習タスク (二項分類、回帰、ランキングなど) には、利用できる機械学習アルゴリズム (トレーナー) のカタログがあります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-124">For example, each machine learning task (binary classification, regression, ranking etc) has a catalog of available machine learning algorithms (trainers).</span></span> <span data-ttu-id="6b5be-125">二項分類トレーナー用のカタログは <xref:Microsoft.ML.BinaryClassificationCatalog.BinaryClassificationTrainers> です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-125">The catalog for the binary classification trainers is: <xref:Microsoft.ML.BinaryClassificationCatalog.BinaryClassificationTrainers>.</span></span>

## <a name="classification"></a><span data-ttu-id="6b5be-126">分類</span><span class="sxs-lookup"><span data-stu-id="6b5be-126">Classification</span></span>

<span data-ttu-id="6b5be-127">データを使用してカテゴリを予測する際、[教師あり機械学習](#supervised-machine-learning)タスクが分類と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-127">When the data is used to predict a category, [supervised machine learning](#supervised-machine-learning) task is called classification.</span></span> <span data-ttu-id="6b5be-128">[二項分類](#binary-classification)とは、2 つのカテゴリだけを予測する (たとえば、画像を猫または犬の写真として分類する) ことです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-128">[Binary classification](#binary-classification) refers to predicting only two categories (for example, classifying an image as a picture of either a 'cat' or a 'dog').</span></span> <span data-ttu-id="6b5be-129">[多クラス分類](#multiclass-classification)とは、複数のカテゴリを予測する (たとえば、画像を特定の犬種の写真として分類する) ことです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-129">[Multiclass classification](#multiclass-classification) refers to predicting multiple categories (for example, when classifying an image as a picture of a specific breed of dog).</span></span>

## <a name="coefficient-of-determination"></a><span data-ttu-id="6b5be-130">決定係数</span><span class="sxs-lookup"><span data-stu-id="6b5be-130">Coefficient of determination</span></span>

<span data-ttu-id="6b5be-131">[回帰](#regression)における評価メトリックであり、データがモデルにどの程度適合するかを示します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-131">In [regression](#regression), an evaluation metric that indicates how well data fits a model.</span></span> <span data-ttu-id="6b5be-132">0 ～ 1 の値になります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-132">Ranges from 0 to 1.</span></span> <span data-ttu-id="6b5be-133">値 0 は、データがランダムであるか、モデルに適合できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-133">A value of 0 means that the data is random or otherwise cannot be fit to the model.</span></span> <span data-ttu-id="6b5be-134">値 1 は、モデルがデータと完全に一致していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-134">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="6b5be-135">多くの場合、これは r<sup>2</sup>、R<sup>2</sup>、または r の 2 乗と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-135">This is often referred to as r<sup>2</sup>, R<sup>2</sup>, or r-squared.</span></span>

## <a name="data"></a><span data-ttu-id="6b5be-136">データ</span><span class="sxs-lookup"><span data-stu-id="6b5be-136">Data</span></span>

<span data-ttu-id="6b5be-137">データはあらゆる機械学習アプリケーションの中心です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-137">Data is central to any machine learning application.</span></span> <span data-ttu-id="6b5be-138">ML.NET では、データは <xref:Microsoft.ML.IDataView> オブジェクトで表されます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-138">In ML.NET data is represented by <xref:Microsoft.ML.IDataView> objects.</span></span> <span data-ttu-id="6b5be-139">データ ビュー オブジェクト:</span><span class="sxs-lookup"><span data-stu-id="6b5be-139">Data view objects:</span></span>
- <span data-ttu-id="6b5be-140">列と行で構成されています</span><span class="sxs-lookup"><span data-stu-id="6b5be-140">are made up of columns and rows</span></span>
- <span data-ttu-id="6b5be-141">遅延評価されます (つまり、操作によって要求されたときにのみデータが読み込まれます)</span><span class="sxs-lookup"><span data-stu-id="6b5be-141">are lazily evaluated, that is they only load data when an operation calls for it</span></span>
- <span data-ttu-id="6b5be-142">各列の型、形式、長さを定義するスキーマが含まれます</span><span class="sxs-lookup"><span data-stu-id="6b5be-142">contain a schema that defines the type, format and length of each column</span></span>

## <a name="estimator"></a><span data-ttu-id="6b5be-143">エスティメーター</span><span class="sxs-lookup"><span data-stu-id="6b5be-143">Estimator</span></span>

<span data-ttu-id="6b5be-144"><xref:Microsoft.ML.IEstimator%601> インターフェイスを実装する ML.NET のクラス。</span><span class="sxs-lookup"><span data-stu-id="6b5be-144">A class in ML.NET that implements the <xref:Microsoft.ML.IEstimator%601> interface.</span></span>

<span data-ttu-id="6b5be-145">エスティメーターは、変換 (データ準備変換と機械学習モデル トレーニング変換の両方) の仕様です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-145">An estimator is a specification of a transformation (both data preparation transformation and machine learning model training transformation).</span></span> <span data-ttu-id="6b5be-146">エスティメーターを連結して、変換のパイプラインにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-146">Estimators can be chained together into a pipeline of transformations.</span></span> <span data-ttu-id="6b5be-147">エスティメーターまたはエスティメーターのパイプラインのパラメーターは、<xref:Microsoft.ML.IEstimator`1.Fit*> が呼び出されたときに学習されます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-147">The parameters of an estimator or pipeline of estimators are learned when <xref:Microsoft.ML.IEstimator`1.Fit*> is called.</span></span> <span data-ttu-id="6b5be-148"><xref:Microsoft.ML.IEstimator`1.Fit*> の結果は[トランスフォーマー](#transformer)です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-148">The result of <xref:Microsoft.ML.IEstimator`1.Fit*> is a [Transformer](#transformer).</span></span>

## <a name="extension-method"></a><span data-ttu-id="6b5be-149">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-149">Extension method</span></span>

<span data-ttu-id="6b5be-150">クラスの一部ですが、クラスの外部で定義されている .NET メソッドです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-150">A .NET method that is part of a class but is defined outside of the class.</span></span> <span data-ttu-id="6b5be-151">拡張メソッドの最初のパラメーターは、その拡張メソッドが属するクラスへの静的な `this` 参照です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-151">The first parameter of an extension method is a static `this` reference to the class to which the extension method belongs.</span></span>

<span data-ttu-id="6b5be-152">拡張メソッドは、ML.NET で[エスティメーター](#estimator)のインスタンスを構築するために幅広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="6b5be-152">Extension methods are used extensively in ML.NET to construct instances of [estimators](#estimator).</span></span>

## <a name="feature"></a><span data-ttu-id="6b5be-153">機能</span><span class="sxs-lookup"><span data-stu-id="6b5be-153">Feature</span></span>

<span data-ttu-id="6b5be-154">測定対象となる事象の測定可能なプロパティです。通常は数 (倍精度) 値になります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-154">A measurable property of the phenomenon being measured, typically a numeric (double) value.</span></span> <span data-ttu-id="6b5be-155">複数の特徴は**特徴ベクトル**と呼ばれ、通常は `double[]` として格納されます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-155">Multiple features are referred to as a **Feature vector** and typically stored as `double[]`.</span></span> <span data-ttu-id="6b5be-156">特徴では、測定対象となる事象の重要な特性を定義します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-156">Features define the important characteristics of the phenomenon being measured.</span></span> <span data-ttu-id="6b5be-157">詳しくは、Wikipedia の[特徴](https://en.wikipedia.org/wiki/Feature_(machine_learning))の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-157">For more information, see the [Feature](https://en.wikipedia.org/wiki/Feature_(machine_learning)) article on Wikipedia.</span></span>

## <a name="feature-engineering"></a><span data-ttu-id="6b5be-158">特徴エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="6b5be-158">Feature engineering</span></span>

<span data-ttu-id="6b5be-159">特徴エンジニアリングは、一連の[特徴](#feature)の定義、および使用可能な事象データから特徴ベクトルを生成する (特徴抽出) ソフトウェアの開発を含むプロセスです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-159">Feature engineering is the process that involves defining a set of [features](#feature) and developing software that produces feature vectors from available phenomenon data, i.e., feature extraction.</span></span> <span data-ttu-id="6b5be-160">詳しくは、Wikipedia の[特徴エンジニアリング](https://en.wikipedia.org/wiki/Feature_engineering)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-160">For more information, see the [Feature engineering](https://en.wikipedia.org/wiki/Feature_engineering) article on Wikipedia.</span></span>

## <a name="f-score"></a><span data-ttu-id="6b5be-161">F 値</span><span class="sxs-lookup"><span data-stu-id="6b5be-161">F-score</span></span>

<span data-ttu-id="6b5be-162">[分類](#classification)における評価メトリックであり、[精度](#precision)と[再現率](#recall)の調和平均を取ります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-162">In [classification](#classification), an evaluation metric that balances [precision](#precision) and [recall](#recall).</span></span>

## <a name="hyperparameter"></a><span data-ttu-id="6b5be-163">ハイパーパラメーター</span><span class="sxs-lookup"><span data-stu-id="6b5be-163">Hyperparameter</span></span>

<span data-ttu-id="6b5be-164">機械学習アルゴリズムのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-164">A parameter of a machine learning algorithm.</span></span> <span data-ttu-id="6b5be-165">例として、デシジョン フォレストにおける学習するツリー数や勾配降下アルゴリズムにおけるステップ サイズなどがあります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-165">Examples include the number of trees to learn in a decision forest or the step size in a gradient descent algorithm.</span></span> <span data-ttu-id="6b5be-166">*ハイパーパラメーター*の値は、モデルのトレーニング前に設定され、予測関数のパラメーターを検出するプロセスを管理します。例として、デシジョン ツリーにおける比較ポイントや線形回帰モデルにおける重みなどがあります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-166">Values of *Hyperparameters* are set before training the model and govern the process of finding the parameters of the prediction function, for example, the comparison points in a decision tree or the weights in a linear regression model.</span></span> <span data-ttu-id="6b5be-167">詳しくは、Wikipedia の[ハイパーパラメーター](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning))の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-167">For more information, see the [Hyperparameter](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)) article on Wikipedia.</span></span>

## <a name="label"></a><span data-ttu-id="6b5be-168">group1</span><span class="sxs-lookup"><span data-stu-id="6b5be-168">Label</span></span>

<span data-ttu-id="6b5be-169">機械学習モデルで予測される要素です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-169">The element to be predicted with the machine learning model.</span></span> <span data-ttu-id="6b5be-170">たとえば、犬種や将来の株価などです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-170">For example, the breed of dog or a future stock price.</span></span>

## <a name="log-loss"></a><span data-ttu-id="6b5be-171">対数損失</span><span class="sxs-lookup"><span data-stu-id="6b5be-171">Log loss</span></span>

<span data-ttu-id="6b5be-172">[分類](#classification)における評価メトリックであり、分類子の正確度を示します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-172">In [classification](#classification), an evaluation metric that characterizes the accuracy of a classifier.</span></span> <span data-ttu-id="6b5be-173">対数損失が小さいほど、分類子の正確度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-173">The smaller log loss is, the more accurate a classifier is.</span></span>

## <a name="loss-function"></a><span data-ttu-id="6b5be-174">損失関数</span><span class="sxs-lookup"><span data-stu-id="6b5be-174">Loss function</span></span>

<span data-ttu-id="6b5be-175">損失関数は、トレーニング ラベル値とモデルによって行われた予測との差です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-175">A loss function is the difference between the training label values and the prediction made by the model.</span></span> <span data-ttu-id="6b5be-176">モデルのパラメーターは、損失関数を最小化することで推定されます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-176">The parameters of the model are estimated by minimizing the loss function.</span></span>

<span data-ttu-id="6b5be-177">さまざまな損失関数を使用してさまざまなトレーナーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-177">Different trainers can be configured with different loss functions.</span></span>

## <a name="mean-absolute-error-mae"></a><span data-ttu-id="6b5be-178">平均絶対誤差 (MAE)</span><span class="sxs-lookup"><span data-stu-id="6b5be-178">Mean absolute error (MAE)</span></span>

<span data-ttu-id="6b5be-179">[回帰](#regression)における評価メトリックであり、すべてのモデルの誤差の平均です。モデルの誤差とは、予測された[ラベル](#label)値と正確なラベル値の間の距離です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-179">In [regression](#regression), an evaluation metric that is the average of all the model errors, where model error is the distance between the predicted [label](#label) value and the correct label value.</span></span>

## <a name="model"></a><span data-ttu-id="6b5be-180">モデル</span><span class="sxs-lookup"><span data-stu-id="6b5be-180">Model</span></span>

<span data-ttu-id="6b5be-181">従来的に予測関数のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-181">Traditionally, the parameters for the prediction function.</span></span> <span data-ttu-id="6b5be-182">たとえば、線形回帰モデルにおける重みやデシジョン ツリーにおける分割ポイントなどがあります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-182">For example, the weights in a linear regression model or the split points in a decision tree.</span></span> <span data-ttu-id="6b5be-183">ML.NET では、ドメイン オブジェクト (画像、テキストなど) の[ラベル](#label)の予測に必要なすべての情報がモデルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-183">In ML.NET, a model contains all the information necessary to predict the [label](#label) of a domain object (for example, image or text).</span></span> <span data-ttu-id="6b5be-184">つまり、ML.NET モデルには、必要な特徴付けのステップと予測関数のパラメーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-184">This means that ML.NET models include the featurization steps necessary as well as the parameters for the prediction function.</span></span>

## <a name="multiclass-classification"></a><span data-ttu-id="6b5be-185">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="6b5be-185">Multiclass classification</span></span>

<span data-ttu-id="6b5be-186">[ラベル](#label)が 3 つ以上のクラスのうちの 1 つである[分類](#classification)です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-186">A [classification](#classification) case where the [label](#label) is one out of three or more classes.</span></span> <span data-ttu-id="6b5be-187">詳細については、トピック「[機械学習のタスク](tasks.md)」のセクション「[多クラス分類](tasks.md#multiclass-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-187">For more information, see the [Multiclass classification](tasks.md#multiclass-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="n-gram"></a><span data-ttu-id="6b5be-188">N グラム</span><span class="sxs-lookup"><span data-stu-id="6b5be-188">N-gram</span></span>

<span data-ttu-id="6b5be-189">テキスト データの特徴抽出スキームです。N 個の単語のシーケンスが[特徴](#feature)値になります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-189">A feature extraction scheme for text data: any sequence of N words turns into a [feature](#feature) value.</span></span>

## <a name="normalization"></a><span data-ttu-id="6b5be-190">正規化</span><span class="sxs-lookup"><span data-stu-id="6b5be-190">Normalization</span></span>

<span data-ttu-id="6b5be-191">正規化とは、浮動小数点データを 0 から 1 の間の値にスケーリングするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-191">Normalization is the process of scaling floating point data to values between 0 and 1.</span></span> <span data-ttu-id="6b5be-192">ML.NET で使用されるトレーニング アルゴリズムの多くで、入力機能データを正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-192">Many of the training algorithms used in ML.NET require input feature data to be normalized.</span></span> <span data-ttu-id="6b5be-193">ML.NET では、[正規化のために一連の変換](transforms.md#normalization-and-scaling)を提供します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-193">ML.NET provides a series of [transforms for normalization](transforms.md#normalization-and-scaling)</span></span>

## <a name="numerical-feature-vector"></a><span data-ttu-id="6b5be-194">数値特徴ベクトル</span><span class="sxs-lookup"><span data-stu-id="6b5be-194">Numerical feature vector</span></span>

<span data-ttu-id="6b5be-195">数値でのみ構成される[特徴](#feature)ベクトルです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-195">A [feature](#feature) vector consisting only of numerical values.</span></span> <span data-ttu-id="6b5be-196">これは `double[]` に似ています。</span><span class="sxs-lookup"><span data-stu-id="6b5be-196">This is similar to `double[]`.</span></span>

## <a name="pipeline"></a><span data-ttu-id="6b5be-197">パイプライン</span><span class="sxs-lookup"><span data-stu-id="6b5be-197">Pipeline</span></span>

<span data-ttu-id="6b5be-198">モデルをデータ セットに適合させるために必要なすべての操作です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-198">All of the operations needed to fit a model to a data set.</span></span> <span data-ttu-id="6b5be-199">パイプラインは、データのインポート、変換、特徴付け、および学習の各ステップで構成されます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-199">A pipeline consists of data import, transformation, featurization, and learning steps.</span></span> <span data-ttu-id="6b5be-200">トレーニングが完了したパイプラインがモデルになります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-200">Once a pipeline is trained, it turns into a model.</span></span>

## <a name="precision"></a><span data-ttu-id="6b5be-201">有効桁数</span><span class="sxs-lookup"><span data-stu-id="6b5be-201">Precision</span></span>

<span data-ttu-id="6b5be-202">[分類](#classification)におけるクラスの精度は、そのクラスに属していると正確に予測された項目の数を、クラスに属していると予測された項目の総数で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-202">In [classification](#classification), the precision for a class is the number of items correctly predicted as belonging to that class divided by the total number of items predicted as belonging to the class.</span></span>

## <a name="recall"></a><span data-ttu-id="6b5be-203">再現率</span><span class="sxs-lookup"><span data-stu-id="6b5be-203">Recall</span></span>

<span data-ttu-id="6b5be-204">[分類](#classification)におけるクラスの再現率は、そのクラスに属していると正確に予測された項目の数を、実際にクラスに属している項目の総数で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-204">In [classification](#classification), the recall for a class is the number of items correctly predicted as belonging to that class divided by the total number of items that actually belong to the class.</span></span>

## <a name="regularization"></a><span data-ttu-id="6b5be-205">正則化</span><span class="sxs-lookup"><span data-stu-id="6b5be-205">Regularization</span></span>

 <span data-ttu-id="6b5be-206">正則化は、複雑すぎるため、線形モデルには適していません。</span><span class="sxs-lookup"><span data-stu-id="6b5be-206">Regularization penalizes a linear model for being too complicated.</span></span> <span data-ttu-id="6b5be-207">正則化には 2 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-207">There are two types of regularization:</span></span>

- <span data-ttu-id="6b5be-208">$L_1$ の正則化では、重要でない特徴の重みが 0 になります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-208">$L_1$ regularization zeros weights for insignificant features.</span></span> <span data-ttu-id="6b5be-209">保存されるモデルのサイズは、この種類の正則化の後に小さくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-209">The size of the saved model may become smaller after this type of regularization.</span></span>
- <span data-ttu-id="6b5be-210">$L_2$ の正則化では、重要ではない機能の重み範囲が最小限に抑えられます。これはより一般的なプロセスであり、外れ値の影響をあまり受けません。</span><span class="sxs-lookup"><span data-stu-id="6b5be-210">$L_2$ regularization minimizes weight range for insignificant features, This is a more general process and is less sensitive to outliers.</span></span>

## <a name="regression"></a><span data-ttu-id="6b5be-211">回帰</span><span class="sxs-lookup"><span data-stu-id="6b5be-211">Regression</span></span>

<span data-ttu-id="6b5be-212">出力が実際の値 (たとえば、倍精度) である[教師あり機械学習](#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-212">A [supervised machine learning](#supervised-machine-learning) task where the output is a real value, for example, double.</span></span> <span data-ttu-id="6b5be-213">例として、株価の予測などがあります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-213">Examples include predicting stock prices.</span></span> <span data-ttu-id="6b5be-214">詳細については、トピック「[機械学習のタスク](tasks.md)」のセクション「[回帰](tasks.md#regression)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-214">For more information, see the [Regression](tasks.md#regression) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="relative-absolute-error"></a><span data-ttu-id="6b5be-215">相対絶対誤差</span><span class="sxs-lookup"><span data-stu-id="6b5be-215">Relative absolute error</span></span>

<span data-ttu-id="6b5be-216">[回帰](#regression)における評価メトリックであり、すべての絶対誤差の合計を、正確な[ラベル](#label)値とすべての正確なラベル値の平均との間の距離の合計で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-216">In [regression](#regression), an evaluation metric that is the sum of all absolute errors divided by the sum of distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="relative-squared-error"></a><span data-ttu-id="6b5be-217">相対平方誤差</span><span class="sxs-lookup"><span data-stu-id="6b5be-217">Relative squared error</span></span>

<span data-ttu-id="6b5be-218">[回帰](#regression)における評価メトリックであり、すべての平方絶対誤差の合計を、正確な[ラベル](#label)値とすべての正確なラベル値の平均との間の平方距離の合計で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-218">In [regression](#regression), an evaluation metric that is the sum of all squared absolute errors divided by the sum of squared distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="root-of-mean-squared-error-rmse"></a><span data-ttu-id="6b5be-219">平均平方誤差の平方根 (RMSE)</span><span class="sxs-lookup"><span data-stu-id="6b5be-219">Root of mean squared error (RMSE)</span></span>

<span data-ttu-id="6b5be-220">[回帰](#regression)における評価メトリックであり、誤差を 2 乗した値の平均値の平方根です。</span><span class="sxs-lookup"><span data-stu-id="6b5be-220">In [regression](#regression), an evaluation metric that is the square root of the average of the squares of the errors.</span></span>

## <a name="scoring"></a><span data-ttu-id="6b5be-221">スコア付け</span><span class="sxs-lookup"><span data-stu-id="6b5be-221">Scoring</span></span>

<span data-ttu-id="6b5be-222">スコアリングは、トレーニング済みの機械学習モデルに新しいデータを適用し、予測を生成するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-222">Scoring is the process of applying new data to a trained machine learning model, and generating predictions.</span></span> <span data-ttu-id="6b5be-223">スコアリングは推論とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-223">Scoring is also known as inferencing.</span></span> <span data-ttu-id="6b5be-224">モデルの種類に応じて、スコアは場合によって、未処理の値、確率、またはカテゴリになります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-224">Depending on the type of model, the score may be a raw value, a probability, or a category.</span></span>

## <a name="supervised-machine-learning"></a><span data-ttu-id="6b5be-225">教師あり機械学習</span><span class="sxs-lookup"><span data-stu-id="6b5be-225">Supervised machine learning</span></span>

<span data-ttu-id="6b5be-226">機械学習の 1 つの手法であり、目的となるモデルが未知のデータのラベルを予測します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-226">A subclass of machine learning in which a desired model predicts the label for yet-unseen data.</span></span> <span data-ttu-id="6b5be-227">例として、分類、回帰、構造化予測などがあります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-227">Examples include classification, regression, and structured prediction.</span></span> <span data-ttu-id="6b5be-228">詳しくは、Wikipedia の[教師あり学習](https://en.wikipedia.org/wiki/Supervised_learning)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-228">For more information, see the  [Supervised learning](https://en.wikipedia.org/wiki/Supervised_learning) article on Wikipedia.</span></span>

## <a name="training"></a><span data-ttu-id="6b5be-229">トレーニング</span><span class="sxs-lookup"><span data-stu-id="6b5be-229">Training</span></span>

<span data-ttu-id="6b5be-230">特定のトレーニング データ セットの[モデル](#model)を識別するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-230">The process of identifying a [model](#model) for a given training data set.</span></span> <span data-ttu-id="6b5be-231">線形モデルの場合、重みの検出を意味します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-231">For a linear model, this means finding the weights.</span></span> <span data-ttu-id="6b5be-232">ツリーの場合、分割ポイントの識別が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-232">For a tree, it involves identifying the split points.</span></span>

## <a name="transformer"></a><span data-ttu-id="6b5be-233">トランスフォーマー</span><span class="sxs-lookup"><span data-stu-id="6b5be-233">Transformer</span></span>

<span data-ttu-id="6b5be-234"><xref:Microsoft.ML.ITransformer> インターフェイスを実装する ML.NET クラス。</span><span class="sxs-lookup"><span data-stu-id="6b5be-234">An ML.NET class that implements the <xref:Microsoft.ML.ITransformer> interface.</span></span>

<span data-ttu-id="6b5be-235">トランスフォーマーでは、ある <xref:Microsoft.ML.IDataView> が別のものに変換されます。</span><span class="sxs-lookup"><span data-stu-id="6b5be-235">A transformer transforms one <xref:Microsoft.ML.IDataView> into another.</span></span> <span data-ttu-id="6b5be-236">トランスフォーマーを作成するには、[エスティメーター](#estimator)またはエスティメーター パイプラインをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="6b5be-236">A transformer is created by training an [estimator](#estimator), or an estimator pipeline.</span></span> 

## <a name="unsupervised-machine-learning"></a><span data-ttu-id="6b5be-237">教師なし機械学習</span><span class="sxs-lookup"><span data-stu-id="6b5be-237">Unsupervised machine learning</span></span>

<span data-ttu-id="6b5be-238">機械学習の 1 つの手法であり、目的となるモデルがデータの隠された (潜在的な) 構造を検出します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-238">A subclass of machine learning in which a desired model finds hidden (or latent) structure in data.</span></span> <span data-ttu-id="6b5be-239">例として、クラスタリング、トピック モデリング、次元削減などがあります。</span><span class="sxs-lookup"><span data-stu-id="6b5be-239">Examples include clustering, topic modeling, and dimensionality reduction.</span></span> <span data-ttu-id="6b5be-240">詳しくは、Wikipedia の[教師なし学習](https://en.wikipedia.org/wiki/Unsupervised_learning)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-240">For more information, see the [Unsupervised learning](https://en.wikipedia.org/wiki/Unsupervised_learning) article on Wikipedia.</span></span>
