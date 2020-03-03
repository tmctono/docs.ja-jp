---
title: モデル ビルダーの Azure トレーニング リソース
description: Azure Machine Learning のリソース ガイド
ms.topic: reference
ms.date: 02/27/2020
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 866fd5a90d13f85f2f8a1aa45ff0e1efb0096642
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159300"
---
# <a name="model-builder-azure-training-resources"></a><span data-ttu-id="47984-103">モデル ビルダーの Azure トレーニング リソース</span><span class="sxs-lookup"><span data-stu-id="47984-103">Model Builder Azure Training Resources</span></span>

<span data-ttu-id="47984-104">次に、Azure でモデル ビルダーを使用してモデルをトレーニングするときに、使用できるリソースを説明します。</span><span class="sxs-lookup"><span data-stu-id="47984-104">The following is a guide to help you learn more about resources used to train models in Azure with Model Builder.</span></span>

## <a name="what-is-an-azure-machine-learning-experiment"></a><span data-ttu-id="47984-105">Azure Machine Learning の実験とは</span><span class="sxs-lookup"><span data-stu-id="47984-105">What is an Azure Machine Learning experiment?</span></span>

<span data-ttu-id="47984-106">Azure Machine Learning の実験とは、Azure でモデル ビルダーのトレーニングを実行する前に作成する必要があるリソースです。</span><span class="sxs-lookup"><span data-stu-id="47984-106">An Azure Machine Learning experiment is a resource that needs to be created before running Model Builder training on Azure.</span></span>

<span data-ttu-id="47984-107">実験には、1 回以上の機械学習のトレーニングの実行の構成と結果がカプセル化されます。</span><span class="sxs-lookup"><span data-stu-id="47984-107">The experiment encapsulates the configuration and results for one or more machine learning training runs.</span></span> <span data-ttu-id="47984-108">実験は特定のワークスペースに属します。</span><span class="sxs-lookup"><span data-stu-id="47984-108">Experiments belong to a specific workspace.</span></span> <span data-ttu-id="47984-109">ワークスペースの名前は、実験の初回作成時に登録されます。</span><span class="sxs-lookup"><span data-stu-id="47984-109">The first time an experiment is created, its name is registered in the workspace.</span></span> <span data-ttu-id="47984-110">それ以降同じ実験名を使用した場合、実行は同じ実験の一部としてログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="47984-110">Any subsequent runs - if the same experiment name is used - are logged as part of the same experiment.</span></span> <span data-ttu-id="47984-111">そうでない場合は、新しい実験が作成されます。</span><span class="sxs-lookup"><span data-stu-id="47984-111">Otherwise, a new experiment is created.</span></span>

## <a name="what-is-an-azure-machine-learning-workspace"></a><span data-ttu-id="47984-112">Azure Machine Learning ワークスペースとは</span><span class="sxs-lookup"><span data-stu-id="47984-112">What is an Azure Machine Learning workspace?</span></span>

<span data-ttu-id="47984-113">ワークスペースとは、トレーニングの実行の一貫で作成された Azure Machine Learning のすべてのリソースと成果物の一元的な場所である Azure Machine Learning のリソースです。</span><span class="sxs-lookup"><span data-stu-id="47984-113">A workspace is an Azure Machine Learning resource that provides a central place for all Azure Machine Learning resources and artifacts created as part of training run.</span></span>

<span data-ttu-id="47984-114">Azure Machine Learning ワークスペースの作成には、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="47984-114">To create an Azure Machine Learning workspace, the following are required:</span></span>

- <span data-ttu-id="47984-115">名前:3 から 33 文字のお使いのワークスペースの名前。</span><span class="sxs-lookup"><span data-stu-id="47984-115">Name: A name for your workspace between 3-33 characters.</span></span> <span data-ttu-id="47984-116">名前には、英数字とハイフンのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="47984-116">Names may only contain alphanumeric characters and hyphens.</span></span> 
- <span data-ttu-id="47984-117">リージョン:お使いのワークスペースとリソースがデプロイされているデータ センターの地理的な場所。</span><span class="sxs-lookup"><span data-stu-id="47984-117">Region: The geographic location of the data center where your workspace and resources are deployed to.</span></span> <span data-ttu-id="47984-118">ご自分またはお客様に近い場所を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="47984-118">It is recommended that you choose a location close to where you or your customers are.</span></span>
- <span data-ttu-id="47984-119">リソース グループ: Azure ソリューションの関連するリソースをすべて保持するコンテナー。</span><span class="sxs-lookup"><span data-stu-id="47984-119">Resource group: A container that contains all related resources for an Azure solution.</span></span>

## <a name="what-is-an-azure-machine-learning-compute"></a><span data-ttu-id="47984-120">Azure Machine Learning コンピューティングとは</span><span class="sxs-lookup"><span data-stu-id="47984-120">What is an Azure Machine Learning compute?</span></span>

<span data-ttu-id="47984-121">Azure Machine Learning コンピューティングとは、トレーニングに使用するクラウドベースの Linux VM です。</span><span class="sxs-lookup"><span data-stu-id="47984-121">An Azure Machine Learning compute is a cloud-based Linux VM used for training.</span></span>

<span data-ttu-id="47984-122">Azure Machine Learning ワークスペースの作成には、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="47984-122">To create an Azure Machine Learning workspace, the following are required:</span></span>

- <span data-ttu-id="47984-123">名前:2 から 16 文字のお使いのワークスペースの名前。</span><span class="sxs-lookup"><span data-stu-id="47984-123">Name: A name for your workspace between 2-16 characters.</span></span> <span data-ttu-id="47984-124">名前には、英数字とハイフンのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="47984-124">Names may only contain alphanumeric characters and hyphens.</span></span>
- <span data-ttu-id="47984-125">コンピューティング サイズ</span><span class="sxs-lookup"><span data-stu-id="47984-125">Compute size</span></span>

    <span data-ttu-id="47984-126">モデル ビルダーでは、GPU に最適化された次のいずれかのコンピューティングの種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="47984-126">Model Builder can use one of the following GPU-optimized compute types:</span></span>

    | <span data-ttu-id="47984-127">サイズ</span><span class="sxs-lookup"><span data-stu-id="47984-127">Size</span></span> | <span data-ttu-id="47984-128">vCPU</span><span class="sxs-lookup"><span data-stu-id="47984-128">vCPU</span></span> | <span data-ttu-id="47984-129">メモリ:GiB</span><span class="sxs-lookup"><span data-stu-id="47984-129">Memory: GiB</span></span> | <span data-ttu-id="47984-130">一時ストレージ (SSD) GiB</span><span class="sxs-lookup"><span data-stu-id="47984-130">Temp storage (SSD) GiB</span></span> | <span data-ttu-id="47984-131">GPU</span><span class="sxs-lookup"><span data-stu-id="47984-131">GPU</span></span> | <span data-ttu-id="47984-132">GPU メモリ: GiB</span><span class="sxs-lookup"><span data-stu-id="47984-132">GPU memory: GiB</span></span> | <span data-ttu-id="47984-133">最大データ ディスク数</span><span class="sxs-lookup"><span data-stu-id="47984-133">Max data disks</span></span> | <span data-ttu-id="47984-134">最大 NIC 数</span><span class="sxs-lookup"><span data-stu-id="47984-134">Max NICs</span></span> |
    |---|---|---|---|---|---|---|---|
    | <span data-ttu-id="47984-135">Standard_NC12</span><span class="sxs-lookup"><span data-stu-id="47984-135">Standard_NC12</span></span>   | <span data-ttu-id="47984-136">12</span><span class="sxs-lookup"><span data-stu-id="47984-136">12</span></span> | <span data-ttu-id="47984-137">112</span><span class="sxs-lookup"><span data-stu-id="47984-137">112</span></span> | <span data-ttu-id="47984-138">680</span><span class="sxs-lookup"><span data-stu-id="47984-138">680</span></span>  | <span data-ttu-id="47984-139">2</span><span class="sxs-lookup"><span data-stu-id="47984-139">2</span></span> | <span data-ttu-id="47984-140">24</span><span class="sxs-lookup"><span data-stu-id="47984-140">24</span></span> | <span data-ttu-id="47984-141">48</span><span class="sxs-lookup"><span data-stu-id="47984-141">48</span></span> | <span data-ttu-id="47984-142">2</span><span class="sxs-lookup"><span data-stu-id="47984-142">2</span></span> |
    | <span data-ttu-id="47984-143">Standard_NC24</span><span class="sxs-lookup"><span data-stu-id="47984-143">Standard_NC24</span></span>   | <span data-ttu-id="47984-144">24</span><span class="sxs-lookup"><span data-stu-id="47984-144">24</span></span> | <span data-ttu-id="47984-145">224</span><span class="sxs-lookup"><span data-stu-id="47984-145">224</span></span> | <span data-ttu-id="47984-146">1440</span><span class="sxs-lookup"><span data-stu-id="47984-146">1440</span></span> | <span data-ttu-id="47984-147">4</span><span class="sxs-lookup"><span data-stu-id="47984-147">4</span></span> | <span data-ttu-id="47984-148">48</span><span class="sxs-lookup"><span data-stu-id="47984-148">48</span></span> | <span data-ttu-id="47984-149">64</span><span class="sxs-lookup"><span data-stu-id="47984-149">64</span></span> | <span data-ttu-id="47984-150">4</span><span class="sxs-lookup"><span data-stu-id="47984-150">4</span></span> |

    <span data-ttu-id="47984-151">GPU に最適化されたコンピューティングの種類の詳細については、[NC シリーズの Linux VM のドキュメント](https://docs.microsoft.com/azure/virtual-machines/nc-series?toc=/azure/virtual-machines/linux/toc.json&bc=/azure/virtual-machines/linux/breadcrumb/toc.json)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47984-151">Visit the [NC-series Linux VM documentation](https://docs.microsoft.com/azure/virtual-machines/nc-series?toc=/azure/virtual-machines/linux/toc.json&bc=/azure/virtual-machines/linux/breadcrumb/toc.json) for more details on GPU optimized compute types.</span></span>

## <a name="training"></a><span data-ttu-id="47984-152">トレーニング</span><span class="sxs-lookup"><span data-stu-id="47984-152">Training</span></span>

<span data-ttu-id="47984-153">Azure でのトレーニングは、モデル ビルダーの画像分類のシナリオのみを用意しています。</span><span class="sxs-lookup"><span data-stu-id="47984-153">Training on Azure is only available for the Model Builder image classification scenario.</span></span> <span data-ttu-id="47984-154">これらのモデルのトレーニングに使用されるアルゴリズムは、ResNet50 アーキテクチャに基づくディープ ニューラル ネットワークです。</span><span class="sxs-lookup"><span data-stu-id="47984-154">The algorithm used to train these models is a Deep Neural Network based on the ResNet50 architecture.</span></span> <span data-ttu-id="47984-155">トレーニングには時間がかかり、この時間は選択したコンピューティングのサイズやデータ量によって変わります。</span><span class="sxs-lookup"><span data-stu-id="47984-155">The training process takes some time and the amount of time may vary depending on the size of compute selected as well as amount of data.</span></span> <span data-ttu-id="47984-156">モデルの初回トレーニング時は、リソースのプロビジョニングのためにトレーニング時間が若干長くなります。</span><span class="sxs-lookup"><span data-stu-id="47984-156">The first time a model is trained, you can expect a slightly longer training time because resources have to be provisioned.</span></span> <span data-ttu-id="47984-157">Visual Studio で [Monitor current run in Azure portal]\(Azure portal で現在の実行の監視\) リンクを選択すると、ご自分の実行の進行状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="47984-157">You can track the progress of your runs by selecting the "Monitor current run in Azure portal" link in Visual Studio.</span></span>

## <a name="results"></a><span data-ttu-id="47984-158">結果</span><span class="sxs-lookup"><span data-stu-id="47984-158">Results</span></span>

<span data-ttu-id="47984-159">トレーニングが完了すると、次のサフィックスが使用された 2 つのプロジェクトがお使いのソリューションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="47984-159">Once training is complete, two projects are added to your solution with the following suffixes:</span></span>

- <span data-ttu-id="47984-160">*ConsoleApp*:予測パイプラインの構築と予測を行うスタート コードの提供を行う C# の .NET Core コンソール アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="47984-160">*ConsoleApp*: A C# .NET Core console application that provides starter code to build the prediction pipeline and make predictions.</span></span>
- <span data-ttu-id="47984-161">*モデル*:入力および出力モデル データのスキーマと、次の資産を定義するデータ モデルを含む C# .NET Standard アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="47984-161">*Model*: A C# .NET Standard application that contains the data models that define the schema of input and output model data as well as the following assets:</span></span>

  - <span data-ttu-id="47984-162">bestModel.onnx:モデルの Open Neural Network Exchange (ONNX) 形式でのシリアル化されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="47984-162">bestModel.onnx: A serialized version of the model in Open Neural Network Exchange (ONNX) format.</span></span> <span data-ttu-id="47984-163">ONNX は、ML.NET、PyTorch、および TensorFlow などのフレームワーク間で相互運用を可能にする、オープンソースの AI モデル用の形式です。</span><span class="sxs-lookup"><span data-stu-id="47984-163">ONNX is an open source format for AI models that supports interoperability between frameworks like ML.NET, PyTorch and TensorFlow.</span></span>
  - <span data-ttu-id="47984-164">bestModelMap.json:モデルの出力をテキストのカテゴリにマップする、予測に使用するカテゴリの一覧。</span><span class="sxs-lookup"><span data-stu-id="47984-164">bestModelMap.json: A list of categories used when making predictions to map the model output to a text category.</span></span>
  - <span data-ttu-id="47984-165">MLModel.zip:`bestModelMap.json` ファイルを使用して予測を行い、出力をマップする、モデル *bestModel.onnx* のシリアル化されたバージョンを使用する ML.NET 予測パイプラインのシリアル化されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="47984-165">MLModel.zip: A serialized version of the ML.NET prediction pipeline that uses the serialized version of the model *bestModel.onnx* to make predictions and maps outputs using the `bestModelMap.json` file.</span></span>

## <a name="use-the-machine-learning-model"></a><span data-ttu-id="47984-166">機械学習モデルの使用</span><span class="sxs-lookup"><span data-stu-id="47984-166">Use the machine learning model</span></span>

<span data-ttu-id="47984-167">*モデル* プロジェクトの `ModelInput` クラスと `ModelOutput` クラスでは、モデルで期待される入力と出力のスキーマをそれぞれ定義します。</span><span class="sxs-lookup"><span data-stu-id="47984-167">The `ModelInput` and `ModelOutput` classes in the *Model* project define the schema of the model's expected input and output respectively.</span></span>

<span data-ttu-id="47984-168">`ModelInput` には、画像の分類シナリオの場合、2 つ列があります。</span><span class="sxs-lookup"><span data-stu-id="47984-168">In an image classification scenario, the `ModelInput` contains two columns:</span></span>

- <span data-ttu-id="47984-169">`ImageSource`:文字列での画像の場所のパス。</span><span class="sxs-lookup"><span data-stu-id="47984-169">`ImageSource`: The string path of the image location.</span></span>
- <span data-ttu-id="47984-170">`Label`:画像が属する実際のカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="47984-170">`Label`: The actual category the image belongs to.</span></span> <span data-ttu-id="47984-171">`Label` は、トレーニング時に入力としてのみ使用され、予測を行うときに指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="47984-171">`Label` is only used as an input when training and does not need to be provided when making predictions.</span></span>

<span data-ttu-id="47984-172">`ModelOutput` には、列が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="47984-172">The `ModelOutput` contains two columns:</span></span>

- <span data-ttu-id="47984-173">`Prediction`:画像の予想されるカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="47984-173">`Prediction`: The image's predicted category.</span></span>
- <span data-ttu-id="47984-174">`Score`:すべてのカテゴリの可能性の一覧 (最高値は `Prediction`)。</span><span class="sxs-lookup"><span data-stu-id="47984-174">`Score`: The list of probabilities for all categories (the highest belongs to the `Prediction`).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="47984-175">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="47984-175">Troubleshooting</span></span>

### <a name="cannot-create-compute"></a><span data-ttu-id="47984-176">コンピューティングを作成できない</span><span class="sxs-lookup"><span data-stu-id="47984-176">Cannot create compute</span></span>

<span data-ttu-id="47984-177">Azure Machine Learning でコンピューティングの作成中にエラーが発生した場合、エラー状態でコンピューティング リソースが存在し続ける場合があります。</span><span class="sxs-lookup"><span data-stu-id="47984-177">If an error occurs during Azure Machine Learning compute creation, the compute resource may still exist, in an errored state.</span></span> <span data-ttu-id="47984-178">同じ名前でコンピューティング リソースを再作成しようとすると、その操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="47984-178">If you try to re-create the compute resource with the same name, the operation fails.</span></span> <span data-ttu-id="47984-179">このエラーを修正するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="47984-179">To fix this error, either:</span></span>

- <span data-ttu-id="47984-180">新しいコンピューティングを別名で作成します</span><span class="sxs-lookup"><span data-stu-id="47984-180">Create the new compute with a different name</span></span>
- <span data-ttu-id="47984-181">Azure portal に移動し、元のコンピューティング リソースを削除します</span><span class="sxs-lookup"><span data-stu-id="47984-181">Go to the Azure portal, and remove the original compute resource</span></span>
