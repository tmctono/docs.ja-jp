---
title: ML.NET を GitHub の問題の多クラス分類シナリオで使用する
description: GitHub の問題を分類し、それを特定の領域に割り当てるための多クラス分類シナリオで、ML.NET を使用する方法について説明します。
ms.date: 03/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: fc21a37fe585ed4b9880ec86ee26815e0668108c
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920988"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="420a3-103">チュートリアル: ML.NET を、GitHub の問題を分類する多クラス分類シナリオで使用する</span><span class="sxs-lookup"><span data-stu-id="420a3-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="420a3-104">このサンプル チュートリアルでは、Visual Studio 2017 で ML.NET を使用して、C# を使用する .NET Core コンソール アプリケーションから GitHub の問題を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="420a3-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="420a3-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="420a3-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="420a3-106">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="420a3-106">Understand the problem</span></span>
> * <span data-ttu-id="420a3-107">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="420a3-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="420a3-108">データを準備する</span><span class="sxs-lookup"><span data-stu-id="420a3-108">Prepare your data</span></span>
> * <span data-ttu-id="420a3-109">データを変換する</span><span class="sxs-lookup"><span data-stu-id="420a3-109">Transform the data</span></span>
> * <span data-ttu-id="420a3-110">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="420a3-110">Train the model</span></span>
> * <span data-ttu-id="420a3-111">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="420a3-111">Evaluate the model</span></span>
> * <span data-ttu-id="420a3-112">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="420a3-112">Predict with the trained model</span></span>
> * <span data-ttu-id="420a3-113">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="420a3-113">Deploy and Predict with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="420a3-114">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="420a3-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="420a3-115">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="420a3-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="420a3-116">このチュートリアルと関連サンプルでは、現時点では **ML.NET バージョン 0.11** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="420a3-116">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="420a3-117">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="420a3-117">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="420a3-118">GitHub の問題のサンプルの概要</span><span class="sxs-lookup"><span data-stu-id="420a3-118">GitHub issue sample overview</span></span>

<span data-ttu-id="420a3-119">このサンプルは ML.NET を使用するコンソール アプリケーションであり、GitHub の問題の区分ラベルを分類および予測するモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="420a3-119">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="420a3-120">また、高品質な分析のために、2 番目のデータ セットを使用してモデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="420a3-120">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="420a3-121">問題のデータセットは、dotnet/corefx GitHub リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="420a3-121">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="420a3-122">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="420a3-122">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="420a3-123">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="420a3-123">Prerequisites</span></span>

* <span data-ttu-id="420a3-124">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="420a3-124">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="420a3-125">[Github の問題のタブ区切りのファイル (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv)。</span><span class="sxs-lookup"><span data-stu-id="420a3-125">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="420a3-126">[Github の問題のテスト タブ区切りのファイル (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv)。</span><span class="sxs-lookup"><span data-stu-id="420a3-126">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="420a3-127">機械学習ワークフロー</span><span class="sxs-lookup"><span data-stu-id="420a3-127">Machine learning workflow</span></span>

<span data-ttu-id="420a3-128">このチュートリアルでは、プロセスを順序立てて進められるようにする機械学習ワークフローに従います。</span><span class="sxs-lookup"><span data-stu-id="420a3-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="420a3-129">このワークフローには次のフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="420a3-129">The workflow phases are as follows:</span></span>

1. **<span data-ttu-id="420a3-130">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="420a3-130">Understand the problem</span></span>**
2. **<span data-ttu-id="420a3-131">データを準備する</span><span class="sxs-lookup"><span data-stu-id="420a3-131">Prepare your data</span></span>**
   * **<span data-ttu-id="420a3-132">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="420a3-132">Load the data</span></span>**
   * **<span data-ttu-id="420a3-133">特徴を抽出する (データを変換する)</span><span class="sxs-lookup"><span data-stu-id="420a3-133">Extract features (Transform your data)</span></span>**
3. **<span data-ttu-id="420a3-134">ビルドしてトレーニングする</span><span class="sxs-lookup"><span data-stu-id="420a3-134">Build and train</span></span>** 
   * **<span data-ttu-id="420a3-135">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="420a3-135">Train the model</span></span>**
   * **<span data-ttu-id="420a3-136">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="420a3-136">Evaluate the model</span></span>**
4. **<span data-ttu-id="420a3-137">モデルの配置</span><span class="sxs-lookup"><span data-stu-id="420a3-137">Deploy Model</span></span>**
   * **<span data-ttu-id="420a3-138">モデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="420a3-138">Use the Model to predict</span></span>**

### <a name="understand-the-problem"></a><span data-ttu-id="420a3-139">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="420a3-139">Understand the problem</span></span>

<span data-ttu-id="420a3-140">まず、問題を把握して、モデルのビルドおよびトレーニングに使用できるパーツに分ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="420a3-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="420a3-141">問題を分けることで、結果の予測および評価ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="420a3-141">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="420a3-142">このチュートリアルでの問題は、優先順位付けとスケジューリングを行うための正しいラベル付けのために、受け取った GitHub の問題がどの区分に属するかを理解することです。</span><span class="sxs-lookup"><span data-stu-id="420a3-142">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="420a3-143">問題は次の部分に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="420a3-143">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="420a3-144">問題のタイトル テキスト</span><span class="sxs-lookup"><span data-stu-id="420a3-144">the issue title text</span></span>
* <span data-ttu-id="420a3-145">問題の説明テキスト</span><span class="sxs-lookup"><span data-stu-id="420a3-145">the issue description text</span></span>
* <span data-ttu-id="420a3-146">モデルのトレーニング データの区分値</span><span class="sxs-lookup"><span data-stu-id="420a3-146">an area value for the model training data</span></span>
* <span data-ttu-id="420a3-147">評価して操作で使用できる予測される区分値</span><span class="sxs-lookup"><span data-stu-id="420a3-147">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="420a3-148">次に、区分を**決定**する必要があります。これは機械学習タスクを選択するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="420a3-148">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="420a3-149">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="420a3-149">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="420a3-150">この問題に関してわかっていることは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="420a3-150">With this problem, you know the following facts:</span></span>

<span data-ttu-id="420a3-151">トレーニング データ:</span><span class="sxs-lookup"><span data-stu-id="420a3-151">Training data:</span></span>

<span data-ttu-id="420a3-152">GitHub の問題は、次の例のようないくつかの領域 (**区分**) にラベル分けできます。</span><span class="sxs-lookup"><span data-stu-id="420a3-152">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="420a3-153">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="420a3-153">area-System.Numerics</span></span>
* <span data-ttu-id="420a3-154">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="420a3-154">area-System.Xml</span></span>
* <span data-ttu-id="420a3-155">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="420a3-155">area-Infrastructure</span></span>
* <span data-ttu-id="420a3-156">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="420a3-156">area-System.Linq</span></span>
* <span data-ttu-id="420a3-157">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="420a3-157">area-System.IO</span></span>

<span data-ttu-id="420a3-158">次の例のように、新しい GitHub の問題の**区分**を予測します。</span><span class="sxs-lookup"><span data-stu-id="420a3-158">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="420a3-159">Contract.Assert 対 Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="420a3-159">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="420a3-160">System.Xml のフィールドを読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="420a3-160">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="420a3-161">このシナリオには、分類機械学習アルゴリズムが適しています。</span><span class="sxs-lookup"><span data-stu-id="420a3-161">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="420a3-162">分類学習アルゴリズムについて</span><span class="sxs-lookup"><span data-stu-id="420a3-162">About the classification learning algorithm</span></span>

<span data-ttu-id="420a3-163">分類は、データを使用して項目またはデータ行のカテゴリ、型、クラスを**判断**する機械学習アルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="420a3-163">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="420a3-164">分類はたとえば、次のような目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="420a3-164">For example, you can use classification to:</span></span>

* <span data-ttu-id="420a3-165">センチメントが肯定的か否定的かを判断する。</span><span class="sxs-lookup"><span data-stu-id="420a3-165">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="420a3-166">電子メールをスパム、迷惑メール、正常なメールに分類する。</span><span class="sxs-lookup"><span data-stu-id="420a3-166">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="420a3-167">患者の検体が癌性かどうかを判断する。</span><span class="sxs-lookup"><span data-stu-id="420a3-167">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="420a3-168">顧客を販売キャンペーンへの反応性で分類する。</span><span class="sxs-lookup"><span data-stu-id="420a3-168">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="420a3-169">多くの場合、分類学習アルゴリズムは次のいずれかの種類です。</span><span class="sxs-lookup"><span data-stu-id="420a3-169">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="420a3-170">バイナリ: A か B のいずれかである。</span><span class="sxs-lookup"><span data-stu-id="420a3-170">Binary: either A or B.</span></span>
* <span data-ttu-id="420a3-171">多クラス: 1 つのモデルを使用して予測できるカテゴリが多数ある。</span><span class="sxs-lookup"><span data-stu-id="420a3-171">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="420a3-172">この種の問題では、問題カテゴリの予測が 2 つだけ (バイナリ) ではなく複数のカテゴリの 1 つ (多クラス) なので、多クラス分類学習アルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="420a3-172">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="420a3-173">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="420a3-173">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="420a3-174">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="420a3-174">Create a project</span></span>

1. <span data-ttu-id="420a3-175">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="420a3-175">Open Visual Studio 2017.</span></span> <span data-ttu-id="420a3-176">**[ファイル]** > **[新規作成]** > **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-176">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="420a3-177">**[新しいプロジェクト]** ダイアログで、**[Visual C#]** ノードを選択し、**[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-177">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="420a3-178">次に、**[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-178">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="420a3-179">**[名前]** テキスト ボックスに「GitHubIssueClassification」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-179">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="420a3-180">プロジェクトに *Data* という名前のディレクトリを作成して、データ セット ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="420a3-180">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="420a3-181">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-181">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="420a3-182">「Data」と入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="420a3-182">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="420a3-183">プロジェクトに *Models* という名前のディレクトリを作成して、モデルを保存します。</span><span class="sxs-lookup"><span data-stu-id="420a3-183">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="420a3-184">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-184">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="420a3-185">「Models」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="420a3-185">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="420a3-186">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="420a3-186">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="420a3-187">ソリューション エクスプローラーで、プロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-187">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="420a3-188">[パッケージ ソース] として "nuget.org" を選択し、[参照] タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-188">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="420a3-189">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、**[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-189">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="420a3-190">データを準備する</span><span class="sxs-lookup"><span data-stu-id="420a3-190">Prepare your data</span></span>

1. <span data-ttu-id="420a3-191">[issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) データ セットと [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) データ セットをダウンロードして、それらを作成済みの *Data* フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="420a3-191">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="420a3-192">1 番目のデータ セットでは機械学習モデルをトレーニングし、2 番目のデータ セットはモデルの精度を評価するために使用します。</span><span class="sxs-lookup"><span data-stu-id="420a3-192">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="420a3-193">ソリューション エクスプローラーで、各 \*.tsv ファイルを右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-193">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="420a3-194">**[詳細設定]** で、**[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="420a3-194">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="420a3-195">クラスを作成してパスを定義する</span><span class="sxs-lookup"><span data-stu-id="420a3-195">Create classes and define paths</span></span>

<span data-ttu-id="420a3-196">次に示す追加の `using` ステートメントを *Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-196">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="420a3-197">最近ダウンロードしたファイルのパスを保存する 3 つのグローバル フィールドと、`MLContext`、`DataView`、`PredictionEngine`、`TextLoader` のためのグローバル変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-197">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* `_trainDataPath` <span data-ttu-id="420a3-198">には、モデルのトレーニングに使用するデータ セットのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="420a3-198">has the path to the dataset used to train the model.</span></span>
* `_testDataPath` <span data-ttu-id="420a3-199">には、モデルの評価に使用するデータ セットのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="420a3-199">has the path to the dataset used to evaluate the model.</span></span>
* `_modelPath` <span data-ttu-id="420a3-200">には、トレーニング済みのモデルを保存するパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="420a3-200">has the path where the trained model is saved.</span></span>
* `_mlContext` <span data-ttu-id="420a3-201">は処理コンテキストを提供する <xref:Microsoft.ML.MLContext> です。</span><span class="sxs-lookup"><span data-stu-id="420a3-201">is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* `_trainingDataView` <span data-ttu-id="420a3-202">は、トレーニング データセットを処理するために使用される <xref:Microsoft.Data.DataView.IDataView> です。</span><span class="sxs-lookup"><span data-stu-id="420a3-202">is the <xref:Microsoft.Data.DataView.IDataView> used to process the training dataset.</span></span>
* `_predEngine` <span data-ttu-id="420a3-203">は、1 つの予測に使用される <xref:Microsoft.ML.PredictionEngine%602> です。</span><span class="sxs-lookup"><span data-stu-id="420a3-203">is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* `_reader` <span data-ttu-id="420a3-204">は、データセットの読み込みと変換に使用される <xref:Microsoft.ML.Data.TextLoader> です。</span><span class="sxs-lookup"><span data-stu-id="420a3-204">is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="420a3-205">`Main` メソッドのすぐ上にある行に次のコードを追加して、それらのパスとその他の変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="420a3-205">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="420a3-206">入力データと予測のために、いくつかのクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-206">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="420a3-207">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-207">Add a new class to your project:</span></span>

1. <span data-ttu-id="420a3-208">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-208">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="420a3-209">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを「*GitHubIssueData.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="420a3-209">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="420a3-210">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="420a3-210">Then, select the **Add** button.</span></span>

    <span data-ttu-id="420a3-211">コード エディターで *GitHubIssueData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="420a3-211">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="420a3-212">*GitHubIssueData.cs* の先頭に次の `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-212">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="420a3-213">既存のクラス定義を削除し、`GitHubIssue` と `IssuePrediction` の 2 つのクラスを含む次のコードを *GitHubIssueData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-213">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

`GitHubIssue` <span data-ttu-id="420a3-214">は、入力データセット クラスで、次の <xref:System.String> フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="420a3-214">is the input dataset class and has the following <xref:System.String> fields:</span></span>

* `ID` <span data-ttu-id="420a3-215">には GitHub の問題の ID 値が含まれます</span><span class="sxs-lookup"><span data-stu-id="420a3-215">contains a value for the GitHub issue ID</span></span>
* `Area` <span data-ttu-id="420a3-216">には、`Area` ラベルの値が含まれます</span><span class="sxs-lookup"><span data-stu-id="420a3-216">contains a value for the `Area` label</span></span>
* `Title` <span data-ttu-id="420a3-217">には GitHub の問題のタイトルが含まれます</span><span class="sxs-lookup"><span data-stu-id="420a3-217">contains the GitHub issue title</span></span>
* `Description` <span data-ttu-id="420a3-218">には GitHub の問題の説明が含まれます</span><span class="sxs-lookup"><span data-stu-id="420a3-218">contains the GitHub issue description</span></span>

`IssuePrediction` <span data-ttu-id="420a3-219">は、モデルがトレーニングされた後に、予測に使用されるクラスです。</span><span class="sxs-lookup"><span data-stu-id="420a3-219">is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="420a3-220">これは、1 つの `string` (`Area`) と、`PredictedLabel` `ColumnName` 属性があります。</span><span class="sxs-lookup"><span data-stu-id="420a3-220">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="420a3-221">`Label` はモデルを作成してトレーニングするために使用され、2 番目のデータ セットでもモデルを評価するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-221">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="420a3-222">`PredictedLabel` は予測と評価の際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-222">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="420a3-223">評価では、トレーニング データを含む入力、予測された値、およびモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-223">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="420a3-224">ML.NET を使用してモデルをビルドするときは、まず <xref:Microsoft.ML.MLContext> を作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-224">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> `MLContext` <span data-ttu-id="420a3-225">は、概念的には Entity Framework での `DbContext` の使用に相当します。</span><span class="sxs-lookup"><span data-stu-id="420a3-225">is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="420a3-226">環境によって、例外の追跡とログ記録に使用できる ML ジョブのコンテキストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-226">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="420a3-227">Main で変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="420a3-227">Initialize variables in Main</span></span>

<span data-ttu-id="420a3-228">複数のトレーニング間で反復可能な決定論的結果を得るために、`_mlContext` グローバル変数をランダム シード (`seed: 0`) を使用して `MLContext` の新しいインスタンスで初期化します。</span><span class="sxs-lookup"><span data-stu-id="420a3-228">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="420a3-229">`Main` メソッドの `Console.WriteLine("Hello World!")` 行を、次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="420a3-229">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="420a3-230">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="420a3-230">Load the data</span></span>

<span data-ttu-id="420a3-231">次いで、`_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> グローバル変数を初期化して、`_trainDataPath` パラメーターを使用してデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="420a3-231">Next, initialize the `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="420a3-232">[`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer) の入力および出力として、`DataView` は基本的なデータ パイプラインの種類であり、`LINQ` の `IEnumerable` と同等です。</span><span class="sxs-lookup"><span data-stu-id="420a3-232">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="420a3-233">ML.NET ではデータは `SQL view` に似ています。</span><span class="sxs-lookup"><span data-stu-id="420a3-233">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="420a3-234">つまり、遅延評価、体系的、異種です。</span><span class="sxs-lookup"><span data-stu-id="420a3-234">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="420a3-235">オブジェクトはパイプラインの最初の部分であり、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="420a3-235">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="420a3-236">このチュートリアルでは、問題のタイトル、説明、および対応する区分 GitHub ラベルを使用してデータセットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="420a3-236">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="420a3-237">モデルの作成とトレーニングには、`DataView` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-237">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="420a3-238">以前に作成した `GitHubIssue` データ モデルの種類がデータセット スキーマと一致するため、初期化、マッピング、およびデータセットの読み込みを 1 行のコードに組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="420a3-238">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="420a3-239">[LoadFromTextFile メソッド](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) の `MLContext.Data.LoadFromTextFile` ラッパーを使用して、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="420a3-239">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="420a3-240">`GitHubIssue` データ モデルの種類からデータセット スキーマを推論し、データセット ヘッダーを使用する <xref:Microsoft.Data.DataView.IDataView> が返されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-240">It returns a <xref:Microsoft.Data.DataView.IDataView> which infers the dataset schema from the `GitHubIssue` data model type and uses the dataset header.</span></span> 

<span data-ttu-id="420a3-241">データ スキーマは、`GitHubIssue` クラスを作成したときに既に定義しています。</span><span class="sxs-lookup"><span data-stu-id="420a3-241">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="420a3-242">スキーマでは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="420a3-242">For your schema:</span></span>

* <span data-ttu-id="420a3-243">最初の列 `ID` (GitHub 問題 ID)</span><span class="sxs-lookup"><span data-stu-id="420a3-243">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="420a3-244">2 番目の列 `Area` (トレーニングの予測)</span><span class="sxs-lookup"><span data-stu-id="420a3-244">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="420a3-245">3 番目の列 `Title` (GitHub の問題のタイトル) は、次の予測に使用される最初の[特徴](../resources/glossary.md##feature)です: </span><span class="sxs-lookup"><span data-stu-id="420a3-245">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the</span></span> `Area`
* <span data-ttu-id="420a3-246">第 4 列 `Description` は、の予測に使用される 2 番目の特徴です: </span><span class="sxs-lookup"><span data-stu-id="420a3-246">the fourth column  `Description` is the second feature used for predicting the</span></span> `Area`

<span data-ttu-id="420a3-247">パイプラインで利用するために `_trainingDataView` グローバル変数を初期化して読み込むには、`mlContext` 初期化の後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-247">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]

<span data-ttu-id="420a3-248">`Main` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-248">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="420a3-249">`ProcessData` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="420a3-249">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="420a3-250">データを抽出して変換します。</span><span class="sxs-lookup"><span data-stu-id="420a3-250">Extracts and transforms the data.</span></span>
* <span data-ttu-id="420a3-251">処理パイプラインを返します。</span><span class="sxs-lookup"><span data-stu-id="420a3-251">Returns the processing pipeline.</span></span>

<span data-ttu-id="420a3-252">`Main` メソッドの直後に、次のコードを使用して `ProcessData` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-252">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="420a3-253">特徴を抽出してデータを変換する</span><span class="sxs-lookup"><span data-stu-id="420a3-253">Extract Features and transform the data</span></span>

<span data-ttu-id="420a3-254">データの前処理とクリーニングは、機械学習でデータ セットを効果的に使用する前に発生する重要なタスクです。</span><span class="sxs-lookup"><span data-stu-id="420a3-254">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="420a3-255">多くの場合、生データはノイズが多くて信頼性が低く、値が欠落している可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="420a3-255">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="420a3-256">これらのモデル化タスクを行わずにデータを使用すると、誤解を招く結果が生じるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="420a3-256">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="420a3-257">ML.NET の変換パイプラインによって、トレーニングまたはテストの前にデータに適用されるカスタムの `transforms` セットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-257">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="420a3-258">この変換の主な目的は、データの[特徴付け](../resources/glossary.md#feature-engineering)です。</span><span class="sxs-lookup"><span data-stu-id="420a3-258">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="420a3-259">機械学習アルゴリズムによって理解されるのは、[特徴付け](../resources/glossary.md#feature)されたデータです。したがって、次の手順では、テキスト データを ML アルゴリズムが認識できる形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="420a3-259">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="420a3-260">その形式は、[数値ベクトル](../resources/glossary.md#numerical-feature-vector)です。</span><span class="sxs-lookup"><span data-stu-id="420a3-260">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="420a3-261">次の手順では、`GitHubIssue` クラス内で定義された名前によって列を参照します。</span><span class="sxs-lookup"><span data-stu-id="420a3-261">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="420a3-262">モデルのトレーニングと評価が行われるとき、既定では、**Label** 列内の値が予測される適切な値と見なされます。</span><span class="sxs-lookup"><span data-stu-id="420a3-262">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="420a3-263">`GitHubIssue` の区分 GitHub ラベルを予測したいので、`Area` 列を **Label** 列にコピーします。</span><span class="sxs-lookup"><span data-stu-id="420a3-263">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="420a3-264">これを行うには、<xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> 変換クラスのラッパーである `MLContext.Transforms.Conversion.MapValueToKey` を使用します。</span><span class="sxs-lookup"><span data-stu-id="420a3-264">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="420a3-265">`MapValueToKey` は、実質的にパイプラインになる <xref:Microsoft.ML.Data.EstimatorChain%601> を返します。</span><span class="sxs-lookup"><span data-stu-id="420a3-265">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="420a3-266">後でトレーナーを `EstimatorChain` に付加するときに、この `pipeline` を指定します。</span><span class="sxs-lookup"><span data-stu-id="420a3-266">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="420a3-267">次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-267">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="420a3-268">特徴付けによって、各列内のさまざまな値に異なる数値が割り当てられ、機械学習のアルゴリズムで使用されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-268">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="420a3-269">次に、`mlContext.Transforms.Text.FeaturizeText` を呼び出します。これによってテキスト列 (`Title` および `Description`) が特徴付けされ、それぞれ `TitleFeaturized` および `DescriptionFeaturized` と呼ばれる数値ベクトルになります。</span><span class="sxs-lookup"><span data-stu-id="420a3-269">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="420a3-270">次のコードを使用して、両列の特徴付けをパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-270">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> <span data-ttu-id="420a3-271">ML.NET バージョン 0.10 では、変換パラメーターの順序が変更されました。</span><span class="sxs-lookup"><span data-stu-id="420a3-271">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="420a3-272">これについては、ビルドするまでエラーが出力されません。</span><span class="sxs-lookup"><span data-stu-id="420a3-272">This will not error out until you build.</span></span> <span data-ttu-id="420a3-273">変換パラメーターの名前を上記のコード スニペットに示すように使用してください。</span><span class="sxs-lookup"><span data-stu-id="420a3-273">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="420a3-274">データの準備の最後の手順では、`Concatenate` 変換クラスを使用して、すべての特徴列を **Features** 列に結合します。</span><span class="sxs-lookup"><span data-stu-id="420a3-274">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="420a3-275">既定では、学習アルゴリズムは **Features** 列の特徴のみを処理します。</span><span class="sxs-lookup"><span data-stu-id="420a3-275">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="420a3-276">次のコードを使用してパイプラインに、この変換を追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-276">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="420a3-277">次に、DataView をキャッシュするために <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> を追加します。つまり、次のコードでキャッシュを使用してデータが複数回反復されると、パフォーマンスが向上する場合があります。</span><span class="sxs-lookup"><span data-stu-id="420a3-277">Next, append a <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="420a3-278">小/中規模のデータセットの場合は、AppendCacheCheckpoint を使用して、トレーニング時間を短くします。</span><span class="sxs-lookup"><span data-stu-id="420a3-278">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="420a3-279">非常に大きいデータセットを処理するときは、使用しないでください (.AppendCacheCheckpoint() を削除します)。</span><span class="sxs-lookup"><span data-stu-id="420a3-279">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="420a3-280">`ProcessData` メソッドの最後で、パイプラインが返されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-280">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="420a3-281">この手順で前処理と特徴付けが処理されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-281">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="420a3-282">ML.NET に用意されているその他のコンポーネントを使用すると、モデルでより良い結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="420a3-282">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="420a3-283">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="420a3-283">Build and train the model</span></span>

<span data-ttu-id="420a3-284">`Main` メソッドの次のコード行として、`BuildAndTrainModel` メソッドに次の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-284">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="420a3-285">`BuildAndTrainModel` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="420a3-285">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="420a3-286">トレーニング アルゴリズムのクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-286">Creates the training algorithm class.</span></span>
* <span data-ttu-id="420a3-287">モデルをトレーニングする。</span><span class="sxs-lookup"><span data-stu-id="420a3-287">Trains the model.</span></span>
* <span data-ttu-id="420a3-288">トレーニング データに基づいて区分を予測します。</span><span class="sxs-lookup"><span data-stu-id="420a3-288">Predicts area based on training data.</span></span>
* <span data-ttu-id="420a3-289">モデルを `.zip` ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="420a3-289">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="420a3-290">モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="420a3-290">Returns the model.</span></span>

<span data-ttu-id="420a3-291">`Main` メソッドの直後に、次のコードを使用して `BuildAndTrainModel` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-291">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

<span data-ttu-id="420a3-292">これでトレーニング データセット (`trainingDataView`) 用の `IDataView` と、ProcessData (`pipeline`) で作成された処理用パイプライン用の <xref:Microsoft.ML.Data.EstimatorChain%601> の 2 つのパラメーターが BuildAndTrainModel メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-292">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="420a3-293">`BuildAndTrainModel` メソッドの最初の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-293">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="420a3-294">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="420a3-294">Choose a learning algorithm</span></span>

<span data-ttu-id="420a3-295">学習アルゴリズムを追加するには、<xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> オブジェクトを返す `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` ラッパー メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="420a3-295">To add the learning algorithm, call the `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="420a3-296">`SdcaMultiClassTrainer` が `pipeline` に追加されます。これは、特徴付けされた `Title` と `Description` (`Features`) と `Label` 入力パラメーターを受け入れて、履歴データから学習します。</span><span class="sxs-lookup"><span data-stu-id="420a3-296">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span> <span data-ttu-id="420a3-297">元の読み取り可能な状態に戻すために、値にラベルもマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="420a3-297">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="420a3-298">これらの両アクションは、次のコードを使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="420a3-298">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="420a3-299">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="420a3-299">Train the model</span></span>

<span data-ttu-id="420a3-300">読み込まれて変換されたデータ セットに基づいて、モデル <xref:Microsoft.ML.Data.TransformerChain%601> をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="420a3-300">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="420a3-301">推定器が定義されたら、既に読み込まれたトレーニング データを提供しながら、<xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> を使用してモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="420a3-301">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="420a3-302">このメソッドにより、予測で使用されるモデルが返されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-302">This  method returns a model to use for predictions.</span></span> `trainingPipeline.Fit()` <span data-ttu-id="420a3-303">でパイプラインをトレーニングし、`DataView` に基づいて `Transformer` を返します。</span><span class="sxs-lookup"><span data-stu-id="420a3-303">trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="420a3-304">`.Fit()` メソッドが実行されるまで、実験は実行されません。</span><span class="sxs-lookup"><span data-stu-id="420a3-304">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="420a3-305">`BuildAndTrainModel` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-305">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="420a3-306">`model` は多数のデータ行を操作する `transformer` ですが、個々の例に対する予測のニーズは、よくある運用シナリオです。</span><span class="sxs-lookup"><span data-stu-id="420a3-306">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="420a3-307"><xref:Microsoft.ML.PredictionEngine%602> は、`CreatePredictionEngine` メソッドから返されるラッパーです。</span><span class="sxs-lookup"><span data-stu-id="420a3-307">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="420a3-308">次の行を追加して、`PredictionEngine` を `BuildAndTrainModel` メソッドの次の行として作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="420a3-308">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="420a3-309">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="420a3-309">Predict with the trained model</span></span>

<span data-ttu-id="420a3-310">GitHub の問題を追加して、`Predict` メソッドでトレーニングされたモデルの予測をテストします。これには `GitHubIssue` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-310">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="420a3-311">これを使用して、問題のデータの 1 インスタンスの `Area` レベルを予測できます。</span><span class="sxs-lookup"><span data-stu-id="420a3-311">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="420a3-312">予測を取得するには、データに対して <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="420a3-312">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="420a3-313">入力データは文字列で、モデルには特徴付けが含まれます。</span><span class="sxs-lookup"><span data-stu-id="420a3-313">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="420a3-314">トレーニングと予測の間は、パイプラインが同期されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-314">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="420a3-315">予測のために前処理/特徴付けのコードを特別に記述する必要はなく、同じ API によってバッチと 1 回限りの予測の両方が処理されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-315">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="420a3-316">モデルの使用: 予測結果</span><span class="sxs-lookup"><span data-stu-id="420a3-316">Using the model: prediction results</span></span>

<span data-ttu-id="420a3-317">結果を共有し、それに応じたアクションを実行するために、`GitHubIssue` および対応する `Area` ラベル予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="420a3-317">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="420a3-318">次の <xref:System.Console.WriteLine?displayProperty=nameWithType> コードを使用して、結果の表示を作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-318">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="420a3-319">評価に使用する、トレーニング済みのモデルを返す</span><span class="sxs-lookup"><span data-stu-id="420a3-319">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="420a3-320">`BuildAndTrainModel` メソッドの最後で、モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="420a3-320">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="420a3-321">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="420a3-321">Evaluate the model</span></span>

<span data-ttu-id="420a3-322">これでモデルの作成とトレーニングが完了したので、品質保証と検証のために、別のデータ セットを使用してモデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="420a3-322">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="420a3-323">`Evaluate` メソッドでは、`BuildAndTrainModel` で作成されたモデルが渡されて評価されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-323">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="420a3-324">`BuildAndTrainModel` の直後に、次のコードに示すように `Evaluate` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-324">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="420a3-325">`Evaluate` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="420a3-325">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="420a3-326">テスト データ セットを読み込む。</span><span class="sxs-lookup"><span data-stu-id="420a3-326">Loads the test dataset.</span></span>
* <span data-ttu-id="420a3-327">多クラス評価器を作成する。</span><span class="sxs-lookup"><span data-stu-id="420a3-327">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="420a3-328">モデルを評価し、メトリックを作成する。</span><span class="sxs-lookup"><span data-stu-id="420a3-328">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="420a3-329">メトリックを表示する。</span><span class="sxs-lookup"><span data-stu-id="420a3-329">Displays the metrics.</span></span>

<span data-ttu-id="420a3-330">`BuildAndTrainModel` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-330">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="420a3-331">既にトレーニング データセットで行ったように、初期化、マッピング、テスト データの読み込みを 1 行のコードに結合できます。</span><span class="sxs-lookup"><span data-stu-id="420a3-331">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="420a3-332">このデータ セットを品質チェックとして使用して、モデルを評価できます。</span><span class="sxs-lookup"><span data-stu-id="420a3-332">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="420a3-333">`Evaluate` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-333">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="420a3-334">`MulticlassClassificationContext.Evaluate` は、指定されたデータセットを使用してモデルの品質メトリックを計算する <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> メソッドのラッパーです。</span><span class="sxs-lookup"><span data-stu-id="420a3-334">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="420a3-335">これによって返される <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> オブジェクトには、多クラス分類評価器によって計算されるメトリック全体が含まれます。</span><span class="sxs-lookup"><span data-stu-id="420a3-335">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="420a3-336">メトリックを表示してモデルの品質を判定するには、最初にメトリックを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="420a3-336">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="420a3-337">特徴を入力し、予測を戻す、機械学習の `_trainedModel` グローバル変数 (変換器) の `Transform` メソッドの使用法に注目してください。</span><span class="sxs-lookup"><span data-stu-id="420a3-337">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="420a3-338">`Evaluate` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-338">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="420a3-339">多クラス分類では、次のメトリックが評価されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-339">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="420a3-340">マイクロ精度: すべてのサンプルとクラスのペアが、精度メトリックに均等に作用します。</span><span class="sxs-lookup"><span data-stu-id="420a3-340">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="420a3-341">マイクロ精度は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="420a3-341">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="420a3-342">マクロ精度: すべてのクラスが、精度メトリックに均等に作用します。</span><span class="sxs-lookup"><span data-stu-id="420a3-342">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="420a3-343">少数派のクラスは、大規模なクラスと同じ重みが与えられています。</span><span class="sxs-lookup"><span data-stu-id="420a3-343">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="420a3-344">マクロ精度は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="420a3-344">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="420a3-345">対数損失: [対数損失](../resources/glossary.md#log-loss)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="420a3-345">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="420a3-346">対数損失は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="420a3-346">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="420a3-347">対数損失還元: 範囲は [-inf, 100] です。ここで、100 は完璧な予測で、0 は平均の予測です。</span><span class="sxs-lookup"><span data-stu-id="420a3-347">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="420a3-348">対数損失還元は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="420a3-348">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="420a3-349">モデル検証のためのメトリックを表示する</span><span class="sxs-lookup"><span data-stu-id="420a3-349">Displaying the metrics for model validation</span></span>

<span data-ttu-id="420a3-350">次のコードを使用してメトリックを表示し、結果を共有し、それに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="420a3-350">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="420a3-351">トレーニング済みの評価されたモデルを保存する</span><span class="sxs-lookup"><span data-stu-id="420a3-351">Save the trained and evaluated model</span></span>

<span data-ttu-id="420a3-352">この時点で、既存または新規のどの .NET アプリケーションにも統合できる、型が <xref:Microsoft.ML.Data.TransformerChain%601> のモデルができました。</span><span class="sxs-lookup"><span data-stu-id="420a3-352">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="420a3-353">トレーニングしたモデルを .zip ファイルに保存するには、`BuildAndTrainModel` の次の行で `SaveModelAsFile` メソッドを呼び出すために次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-353">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="420a3-354">モデルを .zip ファイルとして保存する</span><span class="sxs-lookup"><span data-stu-id="420a3-354">Save the model as a .zip file</span></span>

<span data-ttu-id="420a3-355">`Evaluate` メソッドの直後に、次のコードを使用して `SaveModelAsFile` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-355">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="420a3-356">`SaveModelAsFile` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="420a3-356">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="420a3-357">モデルを .zip ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="420a3-357">Saves the model as a .zip file.</span></span>

<span data-ttu-id="420a3-358">次に、モデルを再利用して他のアプリケーションで使用できるようにモデルを保存するメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-358">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="420a3-359">`ITransformer` には <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> メソッドがあり、`_modelPath` グローバル フィールドと <xref:System.IO.Stream> を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="420a3-359">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="420a3-360">モデルを ZIP ファイルとして保存するには、`FileStream` を作成した直後に `SaveTo` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="420a3-360">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="420a3-361">`SaveModelAsFile` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-361">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="420a3-362">`_modelPath` を使用してコンソール メッセージを記述することで、ファイルが書き込まれた場所も表示できるようになります。これには次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="420a3-362">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="420a3-363">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="420a3-363">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="420a3-364">`Evaluate` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-364">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="420a3-365">`Evaluate` メソッドの直後 (および `SaveModelAsFile` メソッドの直前) に、次のコードを使用して `PredictIssue` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-365">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="420a3-366">`PredictIssue` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="420a3-366">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="420a3-367">テスト データの問題を 1 つ作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-367">Creates a single issue of test data.</span></span>
* <span data-ttu-id="420a3-368">テスト データに基づいて区分を予測します。</span><span class="sxs-lookup"><span data-stu-id="420a3-368">Predicts Area based on test data.</span></span>
* <span data-ttu-id="420a3-369">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="420a3-369">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="420a3-370">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="420a3-370">Displays the predicted results.</span></span>

<span data-ttu-id="420a3-371">まず、次のコードを使用して、先ほど保存したモデルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="420a3-371">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="420a3-372">GitHub の問題を追加して、`Predict` メソッドでトレーニングされたモデルの予測をテストします。これには `GitHubIssue` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-372">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="420a3-373">これでモデルがあるので、それを使用して GitHub の問題データの 1 インスタンスの区分 GitHub ラベルを予測できます。</span><span class="sxs-lookup"><span data-stu-id="420a3-373">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="420a3-374">予測を取得するには、データに対して <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="420a3-374">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="420a3-375">入力データは文字列で、モデルには特徴付けが含まれます。</span><span class="sxs-lookup"><span data-stu-id="420a3-375">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="420a3-376">トレーニングと予測の間は、パイプラインが同期されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-376">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="420a3-377">予測のために前処理/特徴付けのコードを特別に記述する必要はなく、同じ API によってバッチと 1 回限りの予測の両方が処理されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-377">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="420a3-378">予測のために `PredictIssue` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="420a3-378">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="420a3-379">予測のために読み込み済みのモデルを使用する</span><span class="sxs-lookup"><span data-stu-id="420a3-379">Using the loaded model for prediction</span></span>

<span data-ttu-id="420a3-380">問題を分類し、それに応じて処理するために `Area` を表示します。</span><span class="sxs-lookup"><span data-stu-id="420a3-380">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="420a3-381">次の <xref:System.Console.WriteLine?displayProperty=nameWithType> コードを使用して、結果の表示を作成します。</span><span class="sxs-lookup"><span data-stu-id="420a3-381">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="420a3-382">結果</span><span class="sxs-lookup"><span data-stu-id="420a3-382">Results</span></span>

<span data-ttu-id="420a3-383">結果は以下のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="420a3-383">Your results should be similar to the following.</span></span> <span data-ttu-id="420a3-384">パイプラインが処理されると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="420a3-384">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="420a3-385">警告または処理メッセージが表示されることがありますが、</span><span class="sxs-lookup"><span data-stu-id="420a3-385">You may see warnings, or processing messages.</span></span> <span data-ttu-id="420a3-386">わかりやすくするために、これらのメッセージは次の結果から削除してあります。</span><span class="sxs-lookup"><span data-stu-id="420a3-386">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="420a3-387">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="420a3-387">Congratulations!</span></span> <span data-ttu-id="420a3-388">これで、GitHub の問題用の区分ラベルを分類および予測するための機械学習モデルをビルドできました。</span><span class="sxs-lookup"><span data-stu-id="420a3-388">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="420a3-389">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="420a3-389">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="420a3-390">次の手順</span><span class="sxs-lookup"><span data-stu-id="420a3-390">Next steps</span></span>

<span data-ttu-id="420a3-391">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="420a3-391">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="420a3-392">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="420a3-392">Understand the problem</span></span>
> * <span data-ttu-id="420a3-393">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="420a3-393">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="420a3-394">データを準備する</span><span class="sxs-lookup"><span data-stu-id="420a3-394">Prepare your data</span></span>
> * <span data-ttu-id="420a3-395">データを変換する</span><span class="sxs-lookup"><span data-stu-id="420a3-395">Transform the data</span></span>
> * <span data-ttu-id="420a3-396">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="420a3-396">Train the model</span></span>
> * <span data-ttu-id="420a3-397">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="420a3-397">Evaluate the model</span></span>
> * <span data-ttu-id="420a3-398">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="420a3-398">Predict with the trained model</span></span>
> * <span data-ttu-id="420a3-399">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="420a3-399">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="420a3-400">さらに詳しく学習するには、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="420a3-400">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="420a3-401">タクシー代予測</span><span class="sxs-lookup"><span data-stu-id="420a3-401">Taxi Fare Predictor</span></span>](taxi-fare.md)
