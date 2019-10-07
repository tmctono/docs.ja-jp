---
title: ML.NET CLI を使用してセンチメントを分析する
description: サンプル データセットから ML モデルと関連する C# コードを自動的に生成する
author: cesardl
ms.author: cesardl
ms.date: 04/24/2019
ms.custom: mvc
ms.topic: tutorial
ms.openlocfilehash: 5b3b0af5b46774beff9fb7a2a86c37e5399c0dd2
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71957387"
---
# <a name="analyze-sentiment-using-the-mlnet-cli"></a><span data-ttu-id="954ef-103">ML.NET CLI を使用してセンチメントを分析する</span><span class="sxs-lookup"><span data-stu-id="954ef-103">Analyze sentiment using the ML.NET CLI</span></span>

<span data-ttu-id="954ef-104">ML.NET CLI を使用して ML.NET モデルと基礎となる C# コードを自動生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="954ef-104">Learn how to use ML.NET CLI to automatically generate an ML.NET model and underlying C# code.</span></span> <span data-ttu-id="954ef-105">データセットと実装する機械学習タスクを指定すると、CLI では、AutoML エンジンを使用してモデルの生成と展開のソース コードと、二項モデルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="954ef-105">You provide your dataset and the machine learning task you want to implement, and the CLI uses the AutoML engine to create model generation and deployment source code, as well as the binary model.</span></span>

<span data-ttu-id="954ef-106">このチュートリアルでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="954ef-106">In this tutorial, you will do the following steps:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="954ef-107">選択した機械学習タスク用にデータを準備する</span><span class="sxs-lookup"><span data-stu-id="954ef-107">Prepare your data for the selected machine learning task</span></span>
> - <span data-ttu-id="954ef-108">CLI から "mlnet auto-train" コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="954ef-108">Run the 'mlnet auto-train' command from the CLI</span></span>
> - <span data-ttu-id="954ef-109">品質メトリックの結果を確認する</span><span class="sxs-lookup"><span data-stu-id="954ef-109">Review the quality metric results</span></span>
> - <span data-ttu-id="954ef-110">アプリケーションでモデルを使用するために生成された C# コードを理解する</span><span class="sxs-lookup"><span data-stu-id="954ef-110">Understand the generated C# code to use the model in your application</span></span>
> - <span data-ttu-id="954ef-111">モデルのトレーニングに使用された生成済み C# コードを調べる</span><span class="sxs-lookup"><span data-stu-id="954ef-111">Explore the generated C# code that was used to train the model</span></span>

> [!NOTE]
> <span data-ttu-id="954ef-112">このトピックは、現在プレビュー段階の ML.NET CLI ツールについて述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="954ef-112">This topic refers to the ML.NET CLI tool, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="954ef-113">詳細については、[ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="954ef-113">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="954ef-114">ML.NET CLI は ML.NET の一部であり、その主な目的は、ML.NET を学習する .NET 開発者のために ML.NET を "民主化" することなので、始めるときにゼロからコードを書く必要はありません。</span><span class="sxs-lookup"><span data-stu-id="954ef-114">The ML.NET CLI is part of ML.NET and its main goal is to "democratize" ML.NET for .NET developers when learning ML.NET so you don't need to code from scratch to get started.</span></span>

<span data-ttu-id="954ef-115">ML.NET CLI は任意のコマンドプロンプト (Windows、Mac、または Linux) で実行して、指定するトレーニング データセットに基づいて高品質の ML.NET モデルとソース コードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="954ef-115">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) to generate good quality ML.NET models and source code based on training datasets you provide.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="954ef-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="954ef-116">Pre-requisites</span></span>

- <span data-ttu-id="954ef-117">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) 以降</span><span class="sxs-lookup"><span data-stu-id="954ef-117">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) or later</span></span>
- <span data-ttu-id="954ef-118">(省略可能) [Visual Studio 2017 または 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="954ef-118">(Optional) [Visual Studio 2017 or 2019](https://visualstudio.microsoft.com/vs/)</span></span>
- [<span data-ttu-id="954ef-119">ML.NET CLI</span><span class="sxs-lookup"><span data-stu-id="954ef-119">ML.NET CLI</span></span>](../how-to-guides/install-ml-net-cli.md)

<span data-ttu-id="954ef-120">生成された C# コード プロジェクトは、Visual Studio から、または `dotnet run` (.NET Core CLI) を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="954ef-120">You can either run the generated C# code projects from Visual Studio or with `dotnet run` (.NET Core CLI).</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="954ef-121">データを準備する</span><span class="sxs-lookup"><span data-stu-id="954ef-121">Prepare your data</span></span>

<span data-ttu-id="954ef-122">ここでは、二項分類機械学習タスクである "感情分析" シナリオに使用されている既存のデータセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="954ef-122">We are going to use an existing dataset used for a 'Sentiment Analysis' scenario, which is a binary classification machine learning task.</span></span> <span data-ttu-id="954ef-123">お持ちのデータセットを同様の方法で使用して、モデルとコードを自動的に生成することができます。</span><span class="sxs-lookup"><span data-stu-id="954ef-123">You can use your own dataset in a similar way, and the model and code will be generated for you.</span></span>

1. <span data-ttu-id="954ef-124">[UCI Sentiment Labeled Sentences データセット zip ファイル (次の注の引用を参照してください)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) をダウンロードし、任意のフォルダーに展開します。</span><span class="sxs-lookup"><span data-stu-id="954ef-124">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip it on any folder you choose.</span></span>

    > [!NOTE]
    > <span data-ttu-id="954ef-125">このチュートリアルで使用されるデータセットでは、「From Group to Individual Labels using Deep Features」 (Kotzias 他</span><span class="sxs-lookup"><span data-stu-id="954ef-125">The datasets this tutorial uses a dataset from the 'From Group to Individual Labels using Deep Features', Kotzias et al,.</span></span> <span data-ttu-id="954ef-126">KDD 2015) のものであり、UCI 機械学習リポジトリ (Dua, D. and Karra Taniskidou, E.(2017)) でホストされています。</span><span class="sxs-lookup"><span data-stu-id="954ef-126">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="954ef-127">UCI 機械学習リポジトリ [http://archive.ics.uci.edu/ml ]。</span><span class="sxs-lookup"><span data-stu-id="954ef-127">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="954ef-128">カリフォルニア州アーバイン: カリフォルニア大学情報コンピュータサイエンス学部。</span><span class="sxs-lookup"><span data-stu-id="954ef-128">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

2. <span data-ttu-id="954ef-129">`yelp_labelled.txt` ファイルを以前に作成した任意のフォルダー (`/cli-test` など) にコピーします。</span><span class="sxs-lookup"><span data-stu-id="954ef-129">Copy the `yelp_labelled.txt` file into any folder you previously created (such as `/cli-test`).</span></span>

3. <span data-ttu-id="954ef-130">任意のコマンド プロンプトを開き、データセット ファイルをコピーしたフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="954ef-130">Open your preferred command prompt and move to the folder where you copied the dataset file.</span></span> <span data-ttu-id="954ef-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="954ef-131">For example:</span></span>

    ```console
    > cd /cli-test
    ```

    <span data-ttu-id="954ef-132">Visual Studio Code などの任意のテキスト エディターを使用して、`yelp_labelled.txt` データセット ファイルを開き、調べることができます。</span><span class="sxs-lookup"><span data-stu-id="954ef-132">Using any text editor such as Visual Studio Code, you can open, and explore the `yelp_labelled.txt` dataset file.</span></span> <span data-ttu-id="954ef-133">次のような構造であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="954ef-133">You can see that the structure is:</span></span>

    - <span data-ttu-id="954ef-134">このファイルにヘッダーはありません。</span><span class="sxs-lookup"><span data-stu-id="954ef-134">The file has no header.</span></span> <span data-ttu-id="954ef-135">列のインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="954ef-135">You will use the column's index.</span></span>

    - <span data-ttu-id="954ef-136">列は 2 つしかありません。</span><span class="sxs-lookup"><span data-stu-id="954ef-136">There are just two columns:</span></span>

        | <span data-ttu-id="954ef-137">テキスト (列インデックス 0)</span><span class="sxs-lookup"><span data-stu-id="954ef-137">Text (Column index 0)</span></span> | <span data-ttu-id="954ef-138">ラベル (列インデックス 1)</span><span class="sxs-lookup"><span data-stu-id="954ef-138">Label (Column index 1)</span></span>|
        |--------------------------|-------|
        | <span data-ttu-id="954ef-139">Wow...Loved this place.</span><span class="sxs-lookup"><span data-stu-id="954ef-139">Wow... Loved this place.</span></span> | <span data-ttu-id="954ef-140">1</span><span class="sxs-lookup"><span data-stu-id="954ef-140">1</span></span> |
        | <span data-ttu-id="954ef-141">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="954ef-141">Crust is not good.</span></span> | <span data-ttu-id="954ef-142">0</span><span class="sxs-lookup"><span data-stu-id="954ef-142">0</span></span> |
        | <span data-ttu-id="954ef-143">Not tasty and the texture was just nasty.</span><span class="sxs-lookup"><span data-stu-id="954ef-143">Not tasty and the texture was just nasty.</span></span> | <span data-ttu-id="954ef-144">0</span><span class="sxs-lookup"><span data-stu-id="954ef-144">0</span></span> |
        | <span data-ttu-id="954ef-145">...その他のテキスト行...</span><span class="sxs-lookup"><span data-stu-id="954ef-145">...MANY MORE TEXT ROWS...</span></span> | <span data-ttu-id="954ef-146">...(1 または 0)...</span><span class="sxs-lookup"><span data-stu-id="954ef-146">...(1 or 0)...</span></span> |

    <span data-ttu-id="954ef-147">データセット ファイルはエディターから必ず閉じてください。</span><span class="sxs-lookup"><span data-stu-id="954ef-147">Make sure you close the dataset file from the editor.</span></span>

    <span data-ttu-id="954ef-148">これで、この "感情分析" シナリオに CLI を使用する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="954ef-148">Now, you are ready to start using the CLI for this 'Sentiment Analysis' scenario.</span></span>

    > [!NOTE]
    > <span data-ttu-id="954ef-149">このチュートリアルを完了した後は、現在 ML.NET CLI プレビューでサポートされているいずれかの ML タスク ( *"二項分類"、"多クラス分類"、"回帰"* ) に使用する準備ができていれば、お持ちのデータセットで試すこともできます。</span><span class="sxs-lookup"><span data-stu-id="954ef-149">After finishing this tutorial you can also try with your own datasets as long as they are ready to be used for any of the ML tasks currently supported by the ML.NET CLI Preview which are *'Binary Classification', 'Multi-class Classification' and 'Regression'*).</span></span>

## <a name="run-the-mlnet-auto-train-command"></a><span data-ttu-id="954ef-150">"mlnet auto-train" コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="954ef-150">Run the 'mlnet auto-train' command</span></span>

1. <span data-ttu-id="954ef-151">次の ML.NET CLI コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="954ef-151">Run the following ML.NET CLI command:</span></span>

    ```console
    > mlnet auto-train --task binary-classification --dataset "yelp_labelled.txt" --label-column-index 1 --has-header false --max-exploration-time 10
    ```

    <span data-ttu-id="954ef-152">このコマンドによって **`mlnet auto-train` コマンド** が次のように実行されます。</span><span class="sxs-lookup"><span data-stu-id="954ef-152">This command runs the **`mlnet auto-train` command**:</span></span>
    - <span data-ttu-id="954ef-153">種類が **`binary-classification`** の **ML タスク**に対して</span><span class="sxs-lookup"><span data-stu-id="954ef-153">for an **ML task** of type **`binary-classification`**</span></span>
    - <span data-ttu-id="954ef-154">**データセット ファイル `yelp_labelled.txt`** をトレーニングおよびテスト データセットとして使用します (内部的には、CLI によってクロス検証が使用されるか、トレーニング用に 1 つとテスト用に 1 つという 2 つのデータセットに分割されます)。</span><span class="sxs-lookup"><span data-stu-id="954ef-154">uses the **dataset file `yelp_labelled.txt`** as training and testing dataset (internally the CLI will either use cross-validation or split it in two datasets, one for training and one for testing)</span></span>
    - <span data-ttu-id="954ef-155">この予測する**目的列/ターゲット列** (一般的に **"ラベル"** と呼ばれます) は、**インデックス 1 の列**です (インデックスは 0 ベースなので、これは 2 列目です)。</span><span class="sxs-lookup"><span data-stu-id="954ef-155">where the **objective/target column** you want to predict (commonly called **'label'**) is the **column with index 1** (that is the second column, since the index is zero-based)</span></span>
    - <span data-ttu-id="954ef-156">この特定のデータセット ファイルにはヘッダーがないため、列名を含む**ファイル ヘッダーは使用しません**。</span><span class="sxs-lookup"><span data-stu-id="954ef-156">does **not use a file header** with column names since this particular dataset file doesn't have a header</span></span>
    - <span data-ttu-id="954ef-157">実験の**目標探索時間**は **10 秒**です</span><span class="sxs-lookup"><span data-stu-id="954ef-157">the **targeted exploration time** for the experiment is **10 seconds**</span></span>

    <span data-ttu-id="954ef-158">CLI からの出力が次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="954ef-158">You will see output from the CLI, similar to:</span></span>

    <!-- markdownlint-disable MD023 MD025 -->

    # <a name="windowstabwindows"></a>[<span data-ttu-id="954ef-159">Windows</span><span class="sxs-lookup"><span data-stu-id="954ef-159">Windows</span></span>](#tab/windows)

    ![PowerShell 上の ML.NET CLI の auto-train](./media/mlnet-cli/mlnet-auto-train-binary-classification-powershell.gif)

    # <a name="macos-bashtabmacosbash"></a>[<span data-ttu-id="954ef-161">macOS Bash</span><span class="sxs-lookup"><span data-stu-id="954ef-161">macOS Bash</span></span>](#tab/macosbash)

    ![PowerShell 上の ML.NET CLI の auto-train](./media/mlnet-cli/mlnet-auto-train-binary-classification-bash.gif)

    <span data-ttu-id="954ef-163">この特定のケースでは、CLI ツールでは、わずか 10 秒の間に指定した小さなデータセットに対してかなりの回数の反復処理を実行できました。つまり、内部データ変換とアルゴリズムのハイパーパラメーターが異なるさまざまなアルゴリズム/構成の組み合わせに基づいて、複数回のトレーニングを行いました。</span><span class="sxs-lookup"><span data-stu-id="954ef-163">In this particular case, in only 10 seconds and with the small dataset provided, the CLI tool was able to run quite a few iterations, meaning training multiple times based on different combinations of algorithms/configuration with different internal data transformations and algorithm's hyper-parameters.</span></span> 

    <span data-ttu-id="954ef-164">最後に、10 秒間で検出された "最高品質" のモデルは、何らかの特定の構成を持つ特定のトレーナー/アルゴリズムを使用するモデルです。</span><span class="sxs-lookup"><span data-stu-id="954ef-164">Finally, the "best quality" model found in 10 seconds is a model using a particular trainer/algorithm with any specific configuration.</span></span> <span data-ttu-id="954ef-165">探索時間によっては、コマンドから異なる結果が生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="954ef-165">Depending on the exploration time, the command can produce a different result.</span></span> <span data-ttu-id="954ef-166">選択は、`Accuracy` など、表示されている複数のメトリックに基づいています。</span><span class="sxs-lookup"><span data-stu-id="954ef-166">The selection is based on the multiple metrics shown, such as `Accuracy`.</span></span>

    <span data-ttu-id="954ef-167">**モデルの品質メトリックを理解する**</span><span class="sxs-lookup"><span data-stu-id="954ef-167">**Understanding the model's quality metrics**</span></span>

    <span data-ttu-id="954ef-168">二項分類モデルを評価する最初で最も簡単なメトリックは正確度です。これは簡単に理解できます。</span><span class="sxs-lookup"><span data-stu-id="954ef-168">The first and easiest metric to evaluate a binary-classification model is the accuracy, which is simple to understand.</span></span> <span data-ttu-id="954ef-169">"正確度は、テスト データ セットでの正しい予測の割合です"。</span><span class="sxs-lookup"><span data-stu-id="954ef-169">"Accuracy is the proportion of correct predictions with a test data set.".</span></span> <span data-ttu-id="954ef-170">100% (1.00) に近いほど優れています。</span><span class="sxs-lookup"><span data-stu-id="954ef-170">The closer to 100% (1.00), the better.</span></span>

    <span data-ttu-id="954ef-171">ただし、正確度メトリックを使用して測定するだけでは不十分な場合があります。特に、テスト データセットでラベル (この場合は 0 と 1) のバランスが取れていない場合です。</span><span class="sxs-lookup"><span data-stu-id="954ef-171">However, there are cases where just measuring with the Accuracy metric is not enough, especially when the label (0 and 1 in this case) is unbalanced in the test dataset.</span></span>

    <span data-ttu-id="954ef-172">追加のメトリックや、さまざまなモデルの評価に使用される**メトリックに関するより詳細な情報** (正確度、AUC、AUCPR、F1 スコアなど) については、[ML.NET のメトリックの概要](../resources/metrics.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="954ef-172">For additional metrics and more **detailed information about the metrics** such as Accuracy, AUC, AUCPR, F1-score used to evaluate the different models, you can read [Understanding ML.NET metrics](../resources/metrics.md)</span></span>

    > [!NOTE]
    > <span data-ttu-id="954ef-173">これと同じデータセットを試し、`--max-exploration-time` に数分間 (たとえば 180 秒を指定するので 3 分間) を指定すると、このデータセット (かなり小規模で 1,000 行) に対して、トレーニング パイプライン構成が異なる優れた "最適なモデル" が自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="954ef-173">You can try this very same dataset and specify a few minutes for `--max-exploration-time` (for instance three minutes so you specify 180 seconds) which will find a better "best model" for you with a different training pipeline configuration for this dataset (which is pretty small, 1000 rows).</span></span> 
        
    <span data-ttu-id="954ef-174">大規模なデータセットを対象とした "運用環境対応モデル" である "最高/高品質" なモデルを見つけるには、通常、データセットのサイズに応じて、はるかに長い探索時間を指定して、CLI を使用した実験を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="954ef-174">In order to find a "best/good quality" model that is a "production-ready model" targeting larger datasets, you should make experiments with the CLI usually specifying much more exploration time depending on the size of the dataset.</span></span> <span data-ttu-id="954ef-175">実際のところ、多くの場合、特に行と列のデータセットが大きいと、数時間の探索時間が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="954ef-175">In fact, in many cases you might require multiple hours of exploration time especially if the dataset is large on rows and columns.</span></span> 

1. <span data-ttu-id="954ef-176">前のコマンド実行により、以下の資産が生成されました。</span><span class="sxs-lookup"><span data-stu-id="954ef-176">The previous command execution has generated the following assets:</span></span>

    - <span data-ttu-id="954ef-177">すぐに使用できるシリアル化されたモデル .zip ("最適なモデル")。</span><span class="sxs-lookup"><span data-stu-id="954ef-177">A serialized model .zip ("best model") ready to use.</span></span> 
    - <span data-ttu-id="954ef-178">その生成されたモデルを実行/スコア付けする C# コード (そのモデルを使用してエンドユーザー アプリで予測を行うため)。</span><span class="sxs-lookup"><span data-stu-id="954ef-178">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
    - <span data-ttu-id="954ef-179">そのモデルを生成に使用される C# トレーニング コード (学習目的)。</span><span class="sxs-lookup"><span data-stu-id="954ef-179">C# training code used to generate that model (Learning purposes).</span></span>
    - <span data-ttu-id="954ef-180">ハイパーパラメーターとデータ変換の組み合わせを使用して各アルゴリズムに関する具体的な詳細情報を試し、すべての反復処理が探索されたログ ファイル。</span><span class="sxs-lookup"><span data-stu-id="954ef-180">A log file with all the iterations explored having specific detailed information about each algorithm tried with its combination of hyper-parameters and data transformations.</span></span> 

    <span data-ttu-id="954ef-181">最初の 2 つの資産 (.ZIP ファイル モデルと、そのモデルを実行する C# コード) は、その生成された ML モデルを使用して予測を行うために、エンドユーザー アプリ (ASP.NET Core Web アプリ、サービス、デスクトップ アプリなど) で直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="954ef-181">The first two assets (.ZIP file model and C# code to run that model) can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

    <span data-ttu-id="954ef-182">3 つ目の資産のトレーニング コードは、生成されたモデルをトレーニングするために CLI によって使用された ML.NET API コードを示しています。そのため、CLI によって選択された特定のトレーナー/アルゴリズムとハイパーパラメーターを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="954ef-182">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-parameters were selected by the CLI.</span></span>

<span data-ttu-id="954ef-183">これらの列挙した資産については、チュートリアルの次の手順で説明します。</span><span class="sxs-lookup"><span data-stu-id="954ef-183">Those enumerated assets are explained in the following steps of the tutorial.</span></span>

## <a name="explore-the-generated-c-code-to-use-for-running-the-model-to-make-predictions"></a><span data-ttu-id="954ef-184">生成された C# コードを調べて予測するモデルの実行に使用する</span><span class="sxs-lookup"><span data-stu-id="954ef-184">Explore the generated C# code to use for running the model to make predictions</span></span>

1. <span data-ttu-id="954ef-185">Visual Studio (2017 または 2019) で、元の保存先フォルダー内の `SampleBinaryClassification` という名前のフォルダーに生成されたソリューションを開きます (このチュートリアルでは `/cli-test` という名前でした)。</span><span class="sxs-lookup"><span data-stu-id="954ef-185">In Visual Studio (2017 or 2019) open the solution generated in the folder named `SampleBinaryClassification` within your original destination folder (in the tutorial was named `/cli-test`).</span></span> <span data-ttu-id="954ef-186">次のようなソリューションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="954ef-186">You should see a solution similar to:</span></span>

    > [!NOTE]
    > <span data-ttu-id="954ef-187">このチュートリアルでは Visual Studio を使用することをお勧めしますが、生成された C# コード (2 つのプロジェクト) を任意のテキスト エディターで調べ、生成されたコンソール アプリを macOS、Linux または Windows マシン上で `dotnet CLI` を使用して実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="954ef-187">In the tutorial we suggest to use Visual Studio, but you can also explore the generated C# code (two projects) with any text editor and run the generated console app with the `dotnet CLI` on macOS, Linux or Windows machine.</span></span>

    ![CLI によって生成された VS ソリューション](./media/mlnet-cli/generated-csharp-solution-detailed.png)

    - <span data-ttu-id="954ef-189">シリアル化された ML モデル (.zip ファイル) とデータ クラス (データ モデル) を含む、生成された**クラス ライブラリ**は、エンドユーザー アプリケーションで直接使用できます。さらに、そのクラス ライブラリを直接参照する (または必要に応じてコードを移動する) こともできます。</span><span class="sxs-lookup"><span data-stu-id="954ef-189">The generated **class library** containing the serialized ML model (.zip file) and the data classes (data models) is something you can directly use in your end-user application, even by directly referencing that class library (or moving the code, as you prefer).</span></span>
    - <span data-ttu-id="954ef-190">生成された**コンソール アプリ**には、確認する必要がある実行コードが含まれているので、通常、単純なコード (わずか数行) を予測を行うエンドユーザー アプリケーションに移動することで、"スコア付けコード" (予測する ML モデルを実行するコード) を再利用します。</span><span class="sxs-lookup"><span data-stu-id="954ef-190">The generated **console app** contains execution code that you must review and then you usually reuse the 'scoring code' (code that runs the ML model to make predictions) by moving that simple code (just a few lines) to your end-user application where you want to make the predictions.</span></span> 

1. <span data-ttu-id="954ef-191">クラス ライブラリ プロジェクト内の **ModelInput.cs** および **ModelOutput.cs** クラス ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="954ef-191">Open the **ModelInput.cs** and **ModelOutput.cs** class files within the class library project.</span></span> <span data-ttu-id="954ef-192">これらのクラスは、データの保持に使用される "データ クラス" つまり POCO クラスであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="954ef-192">You will see that these classes are 'data classes' or POCO classes used to hold data.</span></span> <span data-ttu-id="954ef-193">これは "定型コード" ですが、データセットに数十列から数百列がある場合に生成すると便利です。</span><span class="sxs-lookup"><span data-stu-id="954ef-193">It is 'boilerplate code' but useful to have it generated if your dataset has tens or even hundreds of columns.</span></span> 
    - <span data-ttu-id="954ef-194">`ModelInput` クラスはデータセットからデータを読み取るときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="954ef-194">The `ModelInput` class is used when reading data from the dataset.</span></span> 
    - <span data-ttu-id="954ef-195">`ModelOutput` クラスは、予測結果 (予測データ) を取得するために使用します。</span><span class="sxs-lookup"><span data-stu-id="954ef-195">The `ModelOutput` class is used to get the prediction result (prediction data).</span></span>

1. <span data-ttu-id="954ef-196">Program.cs ファイルを開き、コードを調べます。</span><span class="sxs-lookup"><span data-stu-id="954ef-196">Open the Program.cs file and explore the code.</span></span> <span data-ttu-id="954ef-197">わずか数行で、モデルを実行し、サンプル予測を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="954ef-197">In just a few lines, you are able to run the model and make a sample prediction.</span></span>

    ```csharp
    static void Main(string[] args)
    {
        MLContext mlContext = new MLContext();

        // Training code used by ML.NET CLI and AutoML to generate the model
        //ModelBuilder.CreateModel();

        ITransformer mlModel = mlContext.Model.Load(MODEL_FILEPATH, out DataViewSchema inputSchema);
        var predEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // Create sample data to do a single prediction with it 
        ModelInput sampleData = CreateSingleDataSample(mlContext, DATA_FILEPATH);

        // Try a single prediction
        ModelOutput predictionResult = predEngine.Predict(sampleData);

        Console.WriteLine($"Single Prediction --> Actual value: {sampleData.Label} | Predicted value: {predictionResult.Prediction}");
    }
    ```

- <span data-ttu-id="954ef-198">コードの最初の行では、ML.NET コードを実行するたびに、必要な `MLContext` オブジェクトを作成するだけです。</span><span class="sxs-lookup"><span data-stu-id="954ef-198">The first line of code simply creates an `MLContext` object needed whenever you run ML.NET code.</span></span> 

- <span data-ttu-id="954ef-199">2 行目のコードはコメント化されています。なぜなら、モデルは既に CLI ツールによってトレーニングされ、モデルのシリアル化された .ZIP ファイルに保存されているので、モデルをトレーニングする必要がないからです。</span><span class="sxs-lookup"><span data-stu-id="954ef-199">The second line of code is commented because you don't need to train the model since it was already trained for you by the CLI tool and saved into the model's serialized .ZIP file.</span></span> <span data-ttu-id="954ef-200">ただし、CLI による *"モデルのトレーニング方法"* を確認するには、その行をコメント解除し、その特定の ML モデルに使用されるトレーニング コードを実行/デバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="954ef-200">But if you want to see *"how the model was trained"* by the CLI, you could uncomment that line and run/debug the training code used for that particular ML model.</span></span>

- <span data-ttu-id="954ef-201">3 行目のコードでは、シリアル化されたモデルの .ZIP ファイルからそのモデルを読むために、そのモデルの .ZIP ファイルのパスを指定して `mlContext.Model.Load()` API を使用します。</span><span class="sxs-lookup"><span data-stu-id="954ef-201">In the third line of code, you load the model from the serialized model .ZIP file with the `mlContext.Model.Load()` API by providing the path to that model .ZIP file.</span></span>

- <span data-ttu-id="954ef-202">4 行目のコードでは、`mlContext.Model.CreatePredictionEngine<TSrc,TDst>(ITransformer mlModel)` API を使用して `PredictionEngine` オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="954ef-202">In the fourth line of code you load create the `PredictionEngine` object with the `mlContext.Model.CreatePredictionEngine<TSrc,TDst>(ITransformer mlModel)` API.</span></span> <span data-ttu-id="954ef-203">1 つのデータ サンプル (この場合は、センチメントを予測するための 1 つのテキスト) をターゲットにして予測する場合は、常に `PredictionEngine` オブジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="954ef-203">You need the `PredictionEngine` object whenever you want to make a prediction targeting a single sample of data (In this case, a single piece of text to predict its sentiment).</span></span>

- <span data-ttu-id="954ef-204">コードの 5 行目では、関数 `CreateSingleDataSample()` を呼び出して、予測に使用するその *1 つのサンプル データ*を作成します。</span><span class="sxs-lookup"><span data-stu-id="954ef-204">The fifth line of code is where you create that *single sample data* to be used for the prediction by calling the function `CreateSingleDataSample()`.</span></span> <span data-ttu-id="954ef-205">CLI ツールでは、使用するサンプル データの種類が認識されないので、この関数内ではデータセットの最初の行が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="954ef-205">Since the CLI tool doesn't know what kind of sample data to use, within that function it is loading the first row of the dataset.</span></span> <span data-ttu-id="954ef-206">ただし、この場合は、その関数を実装してこの簡単なコードを更新することで、現在の `CreateSingleDataSample()` 関数の実装ではなく独自の "ハードコーディングされた" データを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="954ef-206">However, for this case you can also create you own 'hard-coded' data instead of the current implementation of the `CreateSingleDataSample()` function by updating this simpler code implementing that function:</span></span>

    ```csharp
    private static ModelInput CreateSingleDataSample()
    {
        ModelInput sampleForPrediction = new ModelInput() { Col0 = "The ML.NET CLI is great for getting started. Very cool!", Label = true };
        return sampleForPrediction;
    }
    ```

1. <span data-ttu-id="954ef-207">プロジェクトを実行するには、データセットの最初の行から読み込まれた元のサンプル データを使用するか、ハードコーディングされた独自のカスタム サンプル データを指定します。</span><span class="sxs-lookup"><span data-stu-id="954ef-207">Run the project, either using the original sample data loaded from the first row of the dataset or by providing your own custom hard-coded sample data.</span></span> <span data-ttu-id="954ef-208">次のような予測が得られます。</span><span class="sxs-lookup"><span data-stu-id="954ef-208">You should get a prediction comparable to:</span></span>

    # <a name="windowstabwindows"></a>[<span data-ttu-id="954ef-209">Windows</span><span class="sxs-lookup"><span data-stu-id="954ef-209">Windows</span></span>](#tab/windows)

    <span data-ttu-id="954ef-210">Visual Studio から F5 キー ([再生] ボタン) を押してコンソール アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="954ef-210">Run the console app from Visual Studio by hitting F5 (Play button):</span></span>

    ![PowerShell 上の ML.NET CLI の auto-train](./media/mlnet-cli/sample-cli-prediction-execution.png)<span data-ttu-id="954ef-212">)</span><span class="sxs-lookup"><span data-stu-id="954ef-212">)</span></span>

    # <a name="macos-bashtabmacosbash"></a>[<span data-ttu-id="954ef-213">macOS Bash</span><span class="sxs-lookup"><span data-stu-id="954ef-213">macOS Bash</span></span>](#tab/macosbash)

    <span data-ttu-id="954ef-214">次のコマンドを入力して、コマンドプロンプトからコンソール アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="954ef-214">Run the console app from the command-prompt by typing the following commands:</span></span>

     ```bash
     > cd SampleBinaryClassification
     > cd SampleBinaryClassification.ConsoleApp

     > dotnet run
     ```

    ![PowerShell 上の ML.NET CLI の auto-train](./media/mlnet-cli/sample-cli-prediction-execution-bash.png)<span data-ttu-id="954ef-216">)</span><span class="sxs-lookup"><span data-stu-id="954ef-216">)</span></span>

    ---

1. <span data-ttu-id="954ef-217">ハードコーディングされたサンプル データをセンチメントが異なる他の文に変更して、モデルがどのように肯定的センチメントまたは否定的センチメントを予測するかを確認してみてください。</span><span class="sxs-lookup"><span data-stu-id="954ef-217">Try changing the hard-coded sample data to other sentences with different sentiment and see how the model predicts positive or negative sentiment.</span></span> 

## <a name="infuse-your-end-user-applications-with-ml-model-predictions"></a><span data-ttu-id="954ef-218">エンドユーザー アプリケーションに ML モデルの予測を組み込む</span><span class="sxs-lookup"><span data-stu-id="954ef-218">Infuse your end-user applications with ML model predictions</span></span>

<span data-ttu-id="954ef-219">同様の "ML モデル スコア付けコード" を使用して、エンドユーザー アプリケーションでモデルを実行し、予測することができます。</span><span class="sxs-lookup"><span data-stu-id="954ef-219">You can use similar 'ML model scoring code' to run the model in your end-user application and make predictions.</span></span> 

<span data-ttu-id="954ef-220">たとえば、そのコードを **WPF** や **WinForms** などの任意の Windows デスクトップ アプリケーションに直接移動して、コンソール アプリで実行したときと同じ方法でモデルを実行できます。</span><span class="sxs-lookup"><span data-stu-id="954ef-220">For instance, you could directly move that code to any Windows desktop application such as **WPF** and **WinForms** and run the model in the same way than it was done in the console app.</span></span>

<span data-ttu-id="954ef-221">ただし、ML モデルを実行するこれらのコード行を実装する方法は、最適化して (つまり、モデルの .zip ファイルをキャッシュし、読み込みが 1 回になるようにして)、要求ごとに作成するのではなくシングルトン オブジェクトを持つようにします。次のセクションで説明するように、Web アプリケーションや分散サービスなど、アプリケーションをスケーラブルにする必要がある場合は特にそうです。</span><span class="sxs-lookup"><span data-stu-id="954ef-221">However, the way you implement those lines of code to run an ML model should be optimized (that is, cache the model .zip file and load it once) and have singleton objects instead of creating them on every request, especially if your application needs to be scalable such as a web application or distributed service, as explained in the following section.</span></span>

### <a name="running-mlnet-models-in-scalable-aspnet-core-web-apps-and-services-multi-threaded-apps"></a><span data-ttu-id="954ef-222">スケーラブルな ASP.NET Core Web アプリケーションおよびサービス (マルチスレッド アプリ) で ML.NET モデルを実行する</span><span class="sxs-lookup"><span data-stu-id="954ef-222">Running ML.NET models in scalable ASP.NET Core web apps and services (multi-threaded apps)</span></span>

<span data-ttu-id="954ef-223">モデル オブジェクト (モデルの .zip ファイルから読み込まれた `ITransformer`) と `PredictionEngine` オブジェクトの作成は、最適化するようにします。特に、スケーラブルな Web アプリと分散サービスに対して実行する場合は特にそうです。</span><span class="sxs-lookup"><span data-stu-id="954ef-223">The creation of the model object (`ITransformer` loaded from a model's .zip file) and the `PredictionEngine` object should be optimized especially when running on scalable web apps and distributed services.</span></span> <span data-ttu-id="954ef-224">最初のケースでは、モデル オブジェクト (`ITransformer`) の最適化は簡単です。</span><span class="sxs-lookup"><span data-stu-id="954ef-224">For the first case, the model object (`ITransformer`) the optimization is straightforward.</span></span> <span data-ttu-id="954ef-225">`ITransformer` オブジェクトはスレッドセーフなので、オブジェクトをシングルトン オブジェクトまたは静的オブジェクトとしてキャッシュして、モデルの読み込みを 1 回にすることができます。</span><span class="sxs-lookup"><span data-stu-id="954ef-225">Since the `ITransformer` object is thread-safe, you can cache the object as a singleton or static object so you load the model once.</span></span>

<span data-ttu-id="954ef-226">2 つ目のオブジェクトの `PredictionEngine` オブジェクトはそれほど簡単ではありません。`PredictionEngine` オブジェクトはスレッドセーフではないので、ASP.NET Core アプリでこのオブジェクトをシングルトン オブジェクトまたは静的オブジェクトとしてインスタンス化することができないからです。</span><span class="sxs-lookup"><span data-stu-id="954ef-226">For the second object, the `PredictionEngine` object, it is not so easy because the `PredictionEngine` object is not thread-safe, therefore you cannot instantiate this object as singleton or static object in an ASP.NET Core app.</span></span> <span data-ttu-id="954ef-227">このスレッド セーフとスケーラビリティの問題については、この[ブログ記事](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/)で詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="954ef-227">This thread-safe and scalability problem is deeply discussed in this [Blog Post](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span> 

<span data-ttu-id="954ef-228">ただし、状況はこのブログ記事で説明されているよりもはるかに簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="954ef-228">However, things got a lot easier for you than what's explained in that blog post.</span></span> <span data-ttu-id="954ef-229">Microsoft はより簡単なアプローチに取り組み、優れた **".NET Core 統合パッケージ"** を作成しました。アプリケーションの DI サービス (Dependency Injection サービス) に登録することで ASP.NET Core アプリおよびサービスで簡単に使用できます。また、その後はコードから直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="954ef-229">We worked on a simpler approach for you and have created a nice **'.NET Core Integration Package'** that you can  easily use in your ASP.NET Core apps and services by registering it in the application DI services (Dependency Injection services) and then directly use it from your code.</span></span> <span data-ttu-id="954ef-230">その実行方法については、次のチュートリアルと例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="954ef-230">Check the following tutorial and example for doing that:</span></span>

- [<span data-ttu-id="954ef-231">チュートリアル: スケーラブルな ASP.NET Core Web アプリと WebAPI 上の ML.NET モデルの実行</span><span class="sxs-lookup"><span data-stu-id="954ef-231">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [<span data-ttu-id="954ef-232">サンプル: ASP.NET Core WebAPI 上のスケーラブルな ML.NET モデル</span><span class="sxs-lookup"><span data-stu-id="954ef-232">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)

## <a name="explore-the-generated-c-code-that-was-used-to-train-the-best-quality-model"></a><span data-ttu-id="954ef-233">"最高品質" のモデルのトレーニングに使用された生成済み C# コードを調べる</span><span class="sxs-lookup"><span data-stu-id="954ef-233">Explore the generated C# code that was used to train the "best quality" model</span></span> 

<span data-ttu-id="954ef-234">より高度な学習目的のために、生成済みモデルのトレーニングに CLI ツールによって使用された生成済み C# コードを調べることもできます。</span><span class="sxs-lookup"><span data-stu-id="954ef-234">For more advanced learning purposes, you can also explore the generated C# code that was used by the CLI tool to train the generated model.</span></span>

<span data-ttu-id="954ef-235">その "トレーニング モデル コード" は、現在、`ModelBuilder` という名前で生成されたカスタム クラスに生成されているので、そのトレーニング コードを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="954ef-235">That 'training model code' is currently generated in the custom class generated named `ModelBuilder` so you can investigate that training code.</span></span>

<span data-ttu-id="954ef-236">さらに重要な点は、この特定のシナリオ (感情分析モデル) の場合、その生成済みトレーニング コードを次のチュートリアルで説明されているコードと比較することもできることです。</span><span class="sxs-lookup"><span data-stu-id="954ef-236">More importantly, for this particular scenario (Sentiment Analysis model) you can also compare that generated training code with the code explained in the following tutorial:</span></span>

- <span data-ttu-id="954ef-237">比較:[チュートリアル: センチメント分析のバイナリ分類のシナリオで ML.NET を使用する](sentiment-analysis.md)</span><span class="sxs-lookup"><span data-stu-id="954ef-237">Compare: [Tutorial: Use ML.NET in a sentiment analysis binary classification scenario](sentiment-analysis.md).</span></span>

<span data-ttu-id="954ef-238">チュートリアルで選択したアルゴリズムとパイプラインの構成を CLI ツールによって生成されたコードと比較するのは興味深いことです。</span><span class="sxs-lookup"><span data-stu-id="954ef-238">It is interesting to compare the chosen algorithm and pipeline configuration in the tutorial with the code generated by the CLI tool.</span></span> <span data-ttu-id="954ef-239">より良いモデルのために反復処理と検索に使う時間に応じて、選択されるアルゴリズムと、その特定のハイパーパラメーターとパイプラインの構成は変わることがあります。</span><span class="sxs-lookup"><span data-stu-id="954ef-239">Depending on how much time you spend iterating and searching for better models, the chosen algorithm might be different along with its particular hyper-parameters and pipeline configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="954ef-240">関連項目</span><span class="sxs-lookup"><span data-stu-id="954ef-240">See also</span></span>

- [<span data-ttu-id="954ef-241">ML.NET CLI を使用してモデルのトレーニングを自動化する</span><span class="sxs-lookup"><span data-stu-id="954ef-241">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="954ef-242">チュートリアル: スケーラブルな ASP.NET Core Web アプリと WebAPI 上の ML.NET モデルの実行</span><span class="sxs-lookup"><span data-stu-id="954ef-242">Tutorial: Running ML.NET models on scalable ASP.NET Core web apps and WebAPIs</span></span>](https://aka.ms/mlnet-tutorial-netcoreintegrationpkg)
- [<span data-ttu-id="954ef-243">サンプル: ASP.NET Core WebAPI 上のスケーラブルな ML.NET モデル</span><span class="sxs-lookup"><span data-stu-id="954ef-243">Sample: Scalable ML.NET model on ASP.NET Core WebAPI</span></span>](https://aka.ms/mlnet-sample-netcoreintegrationpkg)
- [<span data-ttu-id="954ef-244">ML.NET CLI auto-train コマンド リファレンス ガイド</span><span class="sxs-lookup"><span data-stu-id="954ef-244">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md) 
- [<span data-ttu-id="954ef-245">ML.NET コマンドライン インターフェイス (CLI) ツールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="954ef-245">How to install the ML.NET Command-Line Interface (CLI) tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="954ef-246">ML.NET CLI のテレメトリ</span><span class="sxs-lookup"><span data-stu-id="954ef-246">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

## <a name="next-steps"></a><span data-ttu-id="954ef-247">次の手順</span><span class="sxs-lookup"><span data-stu-id="954ef-247">Next steps</span></span>

<span data-ttu-id="954ef-248">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="954ef-248">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="954ef-249">選択した ML タスク (解決する問題) 用のデータを準備する</span><span class="sxs-lookup"><span data-stu-id="954ef-249">Prepare your data for the selected ML task (problem to solve)</span></span>
> - <span data-ttu-id="954ef-250">CLI ツールで "mlnet auto-train" コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="954ef-250">Run the 'mlnet auto-train' command in the CLI tool</span></span>
> - <span data-ttu-id="954ef-251">品質メトリックの結果を確認する</span><span class="sxs-lookup"><span data-stu-id="954ef-251">Review the quality metric results</span></span>
> - <span data-ttu-id="954ef-252">モデルを実行するために生成された C# コード (エンドユーザー アプリで使用するコード) を理解する</span><span class="sxs-lookup"><span data-stu-id="954ef-252">Understand the generated C# code to run the model (Code to use in your end-user app)</span></span>
> - <span data-ttu-id="954ef-253">"最高品質" のモデルのトレーニングに使用された生成済み C# コードを調べる (学習目的)</span><span class="sxs-lookup"><span data-stu-id="954ef-253">Explore the generated C# code that was used to train the "best quality" model (Learning purposes)</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="954ef-254">ML.NET CLI を使用してモデルのトレーニングを自動化する</span><span class="sxs-lookup"><span data-stu-id="954ef-254">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
