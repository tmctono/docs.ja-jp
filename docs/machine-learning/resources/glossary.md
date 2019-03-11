---
title: 機械学習の用語集 - ML.NET
description: ML.NET でカスタム モデルをビルドする際に役立つ機械学習の重要な用語の用語集。
ms.custom: seodec18
ms.date: 03/05/2019
ms.openlocfilehash: 52f4aa7300edbbdabcc37d7710654dab455d27b0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498901"
---
# <a name="machine-learning-glossary-of-important-terms"></a><span data-ttu-id="a191a-103">機械学習の重要な用語の用語集</span><span class="sxs-lookup"><span data-stu-id="a191a-103">Machine learning glossary of important terms</span></span>

<span data-ttu-id="a191a-104">ML.NET でカスタム モデルをビルドする際に役立つ機械学習の重要な用語を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a191a-104">The following list is a compilation of important machine learning terms that are useful as you build your custom models in ML.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="a191a-105">このドキュメントでは ML.NET が参照されていますが、これは現在プレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="a191a-105">This documentation refers to ML.NET, which is currently in Preview.</span></span> <span data-ttu-id="a191a-106">内容は変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a191a-106">Material may be subject to change.</span></span> <span data-ttu-id="a191a-107">詳しくは、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a191a-107">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="accuracy"></a><span data-ttu-id="a191a-108">正確度</span><span class="sxs-lookup"><span data-stu-id="a191a-108">Accuracy</span></span>

<span data-ttu-id="a191a-109">[分類](#classification)における正確度は、正しく分類された項目の数をテスト セット内の項目の総数で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="a191a-109">In [classification](#classification), accuracy is the number of correctly classified items divided by the total number of items in the test set.</span></span> <span data-ttu-id="a191a-110">0 (正確度が最も低い) ～ 1 (正確度が最も高い) の値になります。</span><span class="sxs-lookup"><span data-stu-id="a191a-110">Ranges from 0 (least accurate) to 1 (most accurate).</span></span> <span data-ttu-id="a191a-111">正確度は、モデル パフォーマンスの評価メトリックの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="a191a-111">Accuracy is one of evaluation metrics of the model performance.</span></span> <span data-ttu-id="a191a-112">[精度](#precision)、[再現率](#recall)、および [F 値](#f-score)と併せて考慮してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-112">Consider it in conjunction with [precision](#precision), [recall](#recall), and [F-score](#f-score).</span></span>

## <a name="area-under-the-curve-auc"></a><span data-ttu-id="a191a-113">曲線下面積 (AUC)</span><span class="sxs-lookup"><span data-stu-id="a191a-113">Area under the curve (AUC)</span></span>

<span data-ttu-id="a191a-114">[二項分類](#binary-classification)における評価メトリックであり、偽陽性率 (x 軸上) に対する真陽性率 (y 軸上) を描画する曲線下面積の値です。</span><span class="sxs-lookup"><span data-stu-id="a191a-114">In [binary classification](#binary-classification), an evaluation metric that is the value of the area under the curve that plots the true positives rate (on the y-axis) against the false positives rate (on the x-axis).</span></span> <span data-ttu-id="a191a-115">0.5 (最低) ～ 1 (最高) の値になります。</span><span class="sxs-lookup"><span data-stu-id="a191a-115">Ranges from 0.5 (worst) to 1 (best).</span></span> <span data-ttu-id="a191a-116">ROC 曲線 (受信者操作特性曲線) 下面積とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a191a-116">Also known as the area under the ROC curve, i.e., receiver operating characteristic curve.</span></span> <span data-ttu-id="a191a-117">詳しくは、Wikipedia の[受信者操作特性](https://en.wikipedia.org/wiki/Receiver_operating_characteristic)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-117">For more information, see the [Receiver operating characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) article on Wikipedia.</span></span>

## <a name="binary-classification"></a><span data-ttu-id="a191a-118">二項分類</span><span class="sxs-lookup"><span data-stu-id="a191a-118">Binary classification</span></span>

<span data-ttu-id="a191a-119">[ラベル](#label)が 2 つのクラスのうちの 1 つである[分類](#classification)です。</span><span class="sxs-lookup"><span data-stu-id="a191a-119">A [classification](#classification) case where the [label](#label) is only one out of two classes.</span></span> <span data-ttu-id="a191a-120">詳細については、トピック「[機械学習のタスク](tasks.md)」のセクションの「[二項分類](tasks.md#binary-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-120">For more information, see the [Binary classification](tasks.md#binary-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="classification"></a><span data-ttu-id="a191a-121">分類</span><span class="sxs-lookup"><span data-stu-id="a191a-121">Classification</span></span>

<span data-ttu-id="a191a-122">データを使用してカテゴリを予測する際、[教師あり機械学習](#supervised-machine-learning)タスクが分類と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a191a-122">When the data is used to predict a category, [supervised machine learning](#supervised-machine-learning) task is called classification.</span></span> <span data-ttu-id="a191a-123">[二項分類](#binary-classification)とは、2 つのカテゴリだけを予測する (たとえば、画像を猫または犬の写真として分類する) ことです。</span><span class="sxs-lookup"><span data-stu-id="a191a-123">[Binary classification](#binary-classification) refers to predicting only two categories (for example, classifying an image as a picture of either a 'cat' or a 'dog').</span></span> <span data-ttu-id="a191a-124">[多クラス分類](#multiclass-classification)とは、複数のカテゴリを予測する (たとえば、画像を特定の犬種の写真として分類する) ことです。</span><span class="sxs-lookup"><span data-stu-id="a191a-124">[Multiclass classification](#multiclass-classification) refers to predicting multiple categories (for example, when classifying an image as a picture of a specific breed of dog).</span></span>

## <a name="coefficient-of-determination"></a><span data-ttu-id="a191a-125">決定係数</span><span class="sxs-lookup"><span data-stu-id="a191a-125">Coefficient of determination</span></span>

<span data-ttu-id="a191a-126">[回帰](#regression)における評価メトリックであり、データがモデルにどの程度適合するかを示します。</span><span class="sxs-lookup"><span data-stu-id="a191a-126">In [regression](#regression), an evaluation metric that indicates how well data fits a model.</span></span> <span data-ttu-id="a191a-127">0 ～ 1 の値になります。</span><span class="sxs-lookup"><span data-stu-id="a191a-127">Ranges from 0 to 1.</span></span> <span data-ttu-id="a191a-128">値 0 は、データがランダムであるか、モデルに適合できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a191a-128">A value of 0 means that the data is random or otherwise cannot be fit to the model.</span></span> <span data-ttu-id="a191a-129">値 1 は、モデルがデータと完全に一致していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a191a-129">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="a191a-130">多くの場合、これは r<sup>2</sup>、R<sup>2</sup>、または r の 2 乗と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a191a-130">This is often referred to as r<sup>2</sup>, R<sup>2</sup>, or r-squared.</span></span>

## <a name="feature"></a><span data-ttu-id="a191a-131">機能</span><span class="sxs-lookup"><span data-stu-id="a191a-131">Feature</span></span>

<span data-ttu-id="a191a-132">測定対象となる事象の測定可能なプロパティです。通常は数 (倍精度) 値になります。</span><span class="sxs-lookup"><span data-stu-id="a191a-132">A measurable property of the phenomenon being measured, typically a numeric (double) value.</span></span> <span data-ttu-id="a191a-133">複数の特徴は**特徴ベクトル**と呼ばれ、通常は `double[]` として格納されます。</span><span class="sxs-lookup"><span data-stu-id="a191a-133">Multiple features are referred to as a **Feature vector** and typically stored as `double[]`.</span></span> <span data-ttu-id="a191a-134">特徴では、測定対象となる事象の重要な特性を定義します。</span><span class="sxs-lookup"><span data-stu-id="a191a-134">Features define the important characteristics of the phenomenon being measured.</span></span> <span data-ttu-id="a191a-135">詳しくは、Wikipedia の[特徴](https://en.wikipedia.org/wiki/Feature_(machine_learning))の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-135">For more information, see the [Feature](https://en.wikipedia.org/wiki/Feature_(machine_learning)) article on Wikipedia.</span></span>

## <a name="feature-engineering"></a><span data-ttu-id="a191a-136">特徴エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="a191a-136">Feature engineering</span></span>

<span data-ttu-id="a191a-137">特徴エンジニアリングは、一連の[特徴](#feature)の定義、および使用可能な事象データから特徴ベクトルを生成する (特徴抽出) ソフトウェアの開発を含むプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a191a-137">Feature engineering is the process that involves defining a set of [features](#feature) and developing software that produces feature vectors from available phenomenon data, i.e., feature extraction.</span></span> <span data-ttu-id="a191a-138">詳しくは、Wikipedia の[特徴エンジニアリング](https://en.wikipedia.org/wiki/Feature_engineering)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-138">For more information, see the [Feature engineering](https://en.wikipedia.org/wiki/Feature_engineering) article on Wikipedia.</span></span>

## <a name="f-score"></a><span data-ttu-id="a191a-139">F 値</span><span class="sxs-lookup"><span data-stu-id="a191a-139">F-score</span></span>

<span data-ttu-id="a191a-140">[分類](#classification)における評価メトリックであり、[精度](#precision)と[再現率](#recall)の調和平均を取ります。</span><span class="sxs-lookup"><span data-stu-id="a191a-140">In [classification](#classification), an evaluation metric that balances [precision](#precision) and [recall](#recall).</span></span>

## <a name="hyperparameter"></a><span data-ttu-id="a191a-141">ハイパーパラメーター</span><span class="sxs-lookup"><span data-stu-id="a191a-141">Hyperparameter</span></span>

<span data-ttu-id="a191a-142">機械学習アルゴリズムのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a191a-142">A parameter of a machine learning algorithm.</span></span> <span data-ttu-id="a191a-143">例として、デシジョン フォレストにおける学習するツリー数や勾配降下アルゴリズムにおけるステップ サイズなどがあります。</span><span class="sxs-lookup"><span data-stu-id="a191a-143">Examples include the number of trees to learn in a decision forest or the step size in a gradient descent algorithm.</span></span> <span data-ttu-id="a191a-144">*ハイパーパラメーター*の値は、モデルのトレーニング前に設定され、予測関数のパラメーターを検出するプロセスを管理します。例として、デシジョン ツリーにおける比較ポイントや線形回帰モデルにおける重みなどがあります。</span><span class="sxs-lookup"><span data-stu-id="a191a-144">Values of *Hyperparameters* are set before training the model and govern the process of finding the parameters of the prediction function, for example, the comparison points in a decision tree or the weights in a linear regression model.</span></span> <span data-ttu-id="a191a-145">詳しくは、Wikipedia の[ハイパーパラメーター](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning))の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-145">For more information, see the [Hyperparameter](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)) article on Wikipedia.</span></span>

## <a name="label"></a><span data-ttu-id="a191a-146">group1</span><span class="sxs-lookup"><span data-stu-id="a191a-146">Label</span></span>

<span data-ttu-id="a191a-147">機械学習モデルで予測される要素です。</span><span class="sxs-lookup"><span data-stu-id="a191a-147">The element to be predicted with the machine learning model.</span></span> <span data-ttu-id="a191a-148">たとえば、犬種や将来の株価などです。</span><span class="sxs-lookup"><span data-stu-id="a191a-148">For example, the breed of dog or a future stock price.</span></span>

## <a name="log-loss"></a><span data-ttu-id="a191a-149">対数損失</span><span class="sxs-lookup"><span data-stu-id="a191a-149">Log loss</span></span>

<span data-ttu-id="a191a-150">[分類](#classification)における評価メトリックであり、分類子の正確度を示します。</span><span class="sxs-lookup"><span data-stu-id="a191a-150">In [classification](#classification), an evaluation metric that characterizes the accuracy of a classifier.</span></span> <span data-ttu-id="a191a-151">対数損失が小さいほど、分類子の正確度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="a191a-151">The smaller log loss is, the more accurate a classifier is.</span></span>

## <a name="mean-absolute-error-mae"></a><span data-ttu-id="a191a-152">平均絶対誤差 (MAE)</span><span class="sxs-lookup"><span data-stu-id="a191a-152">Mean absolute error (MAE)</span></span>

<span data-ttu-id="a191a-153">[回帰](#regression)における評価メトリックであり、すべてのモデルの誤差の平均です。モデルの誤差とは、予測された[ラベル](#label)値と正確なラベル値の間の距離です。</span><span class="sxs-lookup"><span data-stu-id="a191a-153">In [regression](#regression), an evaluation metric that is the average of all the model errors, where model error is the distance between the predicted [label](#label) value and the correct label value.</span></span>

## <a name="model"></a><span data-ttu-id="a191a-154">モデル</span><span class="sxs-lookup"><span data-stu-id="a191a-154">Model</span></span>

<span data-ttu-id="a191a-155">従来的に予測関数のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a191a-155">Traditionally, the parameters for the prediction function.</span></span> <span data-ttu-id="a191a-156">たとえば、線形回帰モデルにおける重みやデシジョン ツリーにおける分割ポイントなどがあります。</span><span class="sxs-lookup"><span data-stu-id="a191a-156">For example, the weights in a linear regression model or the split points in a decision tree.</span></span> <span data-ttu-id="a191a-157">ML.NET では、ドメイン オブジェクト (画像、テキストなど) の[ラベル](#label)の予測に必要なすべての情報がモデルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a191a-157">In ML.NET, a model contains all the information necessary to predict the [label](#label) of a domain object (for example, image or text).</span></span> <span data-ttu-id="a191a-158">つまり、ML.NET モデルには、必要な特徴付けのステップと予測関数のパラメーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a191a-158">This means that ML.NET models include the featurization steps necessary as well as the parameters for the prediction function.</span></span>

## <a name="multiclass-classification"></a><span data-ttu-id="a191a-159">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="a191a-159">Multiclass classification</span></span>

<span data-ttu-id="a191a-160">[ラベル](#label)が 3 つ以上のクラスのうちの 1 つである[分類](#classification)です。</span><span class="sxs-lookup"><span data-stu-id="a191a-160">A [classification](#classification) case where the [label](#label) is one out of three or more classes.</span></span> <span data-ttu-id="a191a-161">詳細については、トピック「[機械学習のタスク](tasks.md)」のセクション「[多クラス分類](tasks.md#multiclass-classification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-161">For more information, see the [Multiclass classification](tasks.md#multiclass-classification) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="n-gram"></a><span data-ttu-id="a191a-162">N グラム</span><span class="sxs-lookup"><span data-stu-id="a191a-162">N-gram</span></span>

<span data-ttu-id="a191a-163">テキスト データの特徴抽出スキームです。N 個の単語のシーケンスが[特徴](#feature)値になります。</span><span class="sxs-lookup"><span data-stu-id="a191a-163">A feature extraction scheme for text data: any sequence of N words turns into a [feature](#feature) value.</span></span>

## <a name="numerical-feature-vector"></a><span data-ttu-id="a191a-164">数値特徴ベクトル</span><span class="sxs-lookup"><span data-stu-id="a191a-164">Numerical feature vector</span></span>

<span data-ttu-id="a191a-165">数値でのみ構成される[特徴](#feature)ベクトルです。</span><span class="sxs-lookup"><span data-stu-id="a191a-165">A [feature](#feature) vector consisting only of numerical values.</span></span> <span data-ttu-id="a191a-166">これは `double[]` に似ています。</span><span class="sxs-lookup"><span data-stu-id="a191a-166">This is similar to `double[]`.</span></span>

## <a name="pipeline"></a><span data-ttu-id="a191a-167">パイプライン</span><span class="sxs-lookup"><span data-stu-id="a191a-167">Pipeline</span></span>

<span data-ttu-id="a191a-168">モデルをデータ セットに適合させるために必要なすべての操作です。</span><span class="sxs-lookup"><span data-stu-id="a191a-168">All of the operations needed to fit a model to a data set.</span></span> <span data-ttu-id="a191a-169">パイプラインは、データのインポート、変換、特徴付け、および学習の各ステップで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a191a-169">A pipeline consists of data import, transformation, featurization, and learning steps.</span></span> <span data-ttu-id="a191a-170">トレーニングが完了したパイプラインがモデルになります。</span><span class="sxs-lookup"><span data-stu-id="a191a-170">Once a pipeline is trained, it turns into a model.</span></span>

## <a name="precision"></a><span data-ttu-id="a191a-171">有効桁数</span><span class="sxs-lookup"><span data-stu-id="a191a-171">Precision</span></span>

<span data-ttu-id="a191a-172">[分類](#classification)におけるクラスの精度は、そのクラスに属していると正確に予測された項目の数を、クラスに属していると予測された項目の総数で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="a191a-172">In [classification](#classification), the precision for a class is the number of items correctly predicted as belonging to that class divided by the total number of items predicted as belonging to the class.</span></span>

## <a name="recall"></a><span data-ttu-id="a191a-173">再現率</span><span class="sxs-lookup"><span data-stu-id="a191a-173">Recall</span></span>

<span data-ttu-id="a191a-174">[分類](#classification)におけるクラスの再現率は、そのクラスに属していると正確に予測された項目の数を、実際にクラスに属している項目の総数で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="a191a-174">In [classification](#classification), the recall for a class is the number of items correctly predicted as belonging to that class divided by the total number of items that actually belong to the class.</span></span>

## <a name="regression"></a><span data-ttu-id="a191a-175">回帰</span><span class="sxs-lookup"><span data-stu-id="a191a-175">Regression</span></span>

<span data-ttu-id="a191a-176">出力が実際の値 (たとえば、倍精度) である[教師あり機械学習](#supervised-machine-learning)タスクです。</span><span class="sxs-lookup"><span data-stu-id="a191a-176">A [supervised machine learning](#supervised-machine-learning) task where the output is a real value, for example, double.</span></span> <span data-ttu-id="a191a-177">例として、株価の予測などがあります。</span><span class="sxs-lookup"><span data-stu-id="a191a-177">Examples include predicting stock prices.</span></span> <span data-ttu-id="a191a-178">詳細については、トピック「[機械学習のタスク](tasks.md)」のセクション「[回帰](tasks.md#regression)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-178">For more information, see the [Regression](tasks.md#regression) section of the [Machine learning tasks](tasks.md) topic.</span></span>

## <a name="relative-absolute-error"></a><span data-ttu-id="a191a-179">相対絶対誤差</span><span class="sxs-lookup"><span data-stu-id="a191a-179">Relative absolute error</span></span>

<span data-ttu-id="a191a-180">[回帰](#regression)における評価メトリックであり、すべての絶対誤差の合計を、正確な[ラベル](#label)値とすべての正確なラベル値の平均との間の距離の合計で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="a191a-180">In [regression](#regression), an evaluation metric that is the sum of all absolute errors divided by the sum of distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="relative-squared-error"></a><span data-ttu-id="a191a-181">相対平方誤差</span><span class="sxs-lookup"><span data-stu-id="a191a-181">Relative squared error</span></span>

<span data-ttu-id="a191a-182">[回帰](#regression)における評価メトリックであり、すべての平方絶対誤差の合計を、正確な[ラベル](#label)値とすべての正確なラベル値の平均との間の平方距離の合計で割ったものです。</span><span class="sxs-lookup"><span data-stu-id="a191a-182">In [regression](#regression), an evaluation metric that is the sum of all squared absolute errors divided by the sum of squared distances between correct [label](#label) values and the average of all correct label values.</span></span>

## <a name="root-of-mean-squared-error-rmse"></a><span data-ttu-id="a191a-183">平均平方誤差の平方根 (RMSE)</span><span class="sxs-lookup"><span data-stu-id="a191a-183">Root of mean squared error (RMSE)</span></span>

<span data-ttu-id="a191a-184">[回帰](#regression)における評価メトリックであり、誤差を 2 乗した値の平均値の平方根です。</span><span class="sxs-lookup"><span data-stu-id="a191a-184">In [regression](#regression), an evaluation metric that is the square root of the average of the squares of the errors.</span></span>

## <a name="supervised-machine-learning"></a><span data-ttu-id="a191a-185">教師あり機械学習</span><span class="sxs-lookup"><span data-stu-id="a191a-185">Supervised machine learning</span></span>

<span data-ttu-id="a191a-186">機械学習の 1 つの手法であり、目的となるモデルが未知のデータのラベルを予測します。</span><span class="sxs-lookup"><span data-stu-id="a191a-186">A subclass of machine learning in which a desired model predicts the label for yet-unseen data.</span></span> <span data-ttu-id="a191a-187">例として、分類、回帰、構造化予測などがあります。</span><span class="sxs-lookup"><span data-stu-id="a191a-187">Examples include classification, regression, and structured prediction.</span></span> <span data-ttu-id="a191a-188">詳しくは、Wikipedia の[教師あり学習](https://en.wikipedia.org/wiki/Supervised_learning)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-188">For more information, see the  [Supervised learning](https://en.wikipedia.org/wiki/Supervised_learning) article on Wikipedia.</span></span>

## <a name="training"></a><span data-ttu-id="a191a-189">トレーニング</span><span class="sxs-lookup"><span data-stu-id="a191a-189">Training</span></span>

<span data-ttu-id="a191a-190">特定のトレーニング データ セットの[モデル](#model)を識別するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a191a-190">The process of identifying a [model](#model) for a given training data set.</span></span> <span data-ttu-id="a191a-191">線形モデルの場合、重みの検出を意味します。</span><span class="sxs-lookup"><span data-stu-id="a191a-191">For a linear model, this means finding the weights.</span></span> <span data-ttu-id="a191a-192">ツリーの場合、分割ポイントの識別が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a191a-192">For a tree, it involves the identifying the split points.</span></span>

## <a name="transform"></a><span data-ttu-id="a191a-193">変換</span><span class="sxs-lookup"><span data-stu-id="a191a-193">Transform</span></span>

<span data-ttu-id="a191a-194">データを変換する[パイプライン](#pipeline) コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a191a-194">A [pipeline](#pipeline) component that transforms data.</span></span> <span data-ttu-id="a191a-195">たとえば、数字のテキストからベクトルへの変換などです。</span><span class="sxs-lookup"><span data-stu-id="a191a-195">For example, from text to vector of numbers.</span></span>

## <a name="unsupervised-machine-learning"></a><span data-ttu-id="a191a-196">教師なし機械学習</span><span class="sxs-lookup"><span data-stu-id="a191a-196">Unsupervised machine learning</span></span>

<span data-ttu-id="a191a-197">機械学習の 1 つの手法であり、目的となるモデルがデータの隠された (潜在的な) 構造を検出します。</span><span class="sxs-lookup"><span data-stu-id="a191a-197">A subclass of machine learning in which a desired model finds hidden (or latent) structure in data.</span></span> <span data-ttu-id="a191a-198">例として、クラスタリング、トピック モデリング、次元削減などがあります。</span><span class="sxs-lookup"><span data-stu-id="a191a-198">Examples include clustering, topic modeling, and dimensionality reduction.</span></span> <span data-ttu-id="a191a-199">詳しくは、Wikipedia の[教師なし学習](https://en.wikipedia.org/wiki/Unsupervised_learning)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a191a-199">For more information, see the [Unsupervised learning](https://en.wikipedia.org/wiki/Unsupervised_learning) article on Wikipedia.</span></span>
