---
title: 高いスケーラビリティと可用性のためにマイクロサービスと複数のコンテナー アプリケーションを調整する
description: Azure Kubernetes サービスを使用してアプリをデプロイする方法について説明します。
ms.date: 02/15/2019
ms.openlocfilehash: 88e76b4b0a3686f4227a6aee1b7fbd2bfe55fdcc
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644638"
---
# <a name="deploy-to-azure-kubernetes-service-aks"></a><span data-ttu-id="a2997-103">Azure Kubernetes Service (AKS) へのデプロイ</span><span class="sxs-lookup"><span data-stu-id="a2997-103">Deploy to Azure Kubernetes Service (AKS)</span></span>

<span data-ttu-id="a2997-104">推奨されるクライアント オペレーティング システムを使用する AKS と対話できます、ここ方法について説明しますで Microsoft Windows と埋め込みのバージョンでは、Windows、Ubuntu Linux の Bash コマンドを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a2997-104">You can interact with AKS using your preferred client operating system, here we show how to do it with Microsoft Windows and an embedded version of Ubuntu Linux in Windows, using Bash commands.</span></span>

<span data-ttu-id="a2997-105">AKS を使用する前に前提条件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2997-105">Prerequisites to have before using AKS are:</span></span>

- <span data-ttu-id="a2997-106">Linux または Mac の開発用コンピューター</span><span class="sxs-lookup"><span data-stu-id="a2997-106">Linux or Mac development machine</span></span>
- <span data-ttu-id="a2997-107">Windows 開発用コンピューター</span><span class="sxs-lookup"><span data-stu-id="a2997-107">Windows development machine</span></span>
  - <span data-ttu-id="a2997-108">Windows で有効になって、開発者モード</span><span class="sxs-lookup"><span data-stu-id="a2997-108">Developer Mode enabled on Windows</span></span>
  - <span data-ttu-id="a2997-109">Windows Subsystem for Linux</span><span class="sxs-lookup"><span data-stu-id="a2997-109">Windows Subsystem for Linux</span></span>
- <span data-ttu-id="a2997-110">Azure CLI にインストールされている[Windows、Mac または Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span><span class="sxs-lookup"><span data-stu-id="a2997-110">Azure-CLI installed on [Windows, Mac or Linux](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)</span></span>

> [!NOTE]
> <span data-ttu-id="a2997-111">完全な情報の検索について。</span><span class="sxs-lookup"><span data-stu-id="a2997-111">To find complete information about:</span></span>
>
> <span data-ttu-id="a2997-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span><span class="sxs-lookup"><span data-stu-id="a2997-112">Azure-CLI: <https://docs.microsoft.com/cli/azure/index?view=azure-cli-latest></span></span>
>
> <span data-ttu-id="a2997-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span><span class="sxs-lookup"><span data-stu-id="a2997-113">Windows Subsystem for Linux: <https://docs.microsoft.com/windows/wsl/about></span></span>

## <a name="create-the-aks-environment-in-azure"></a><span data-ttu-id="a2997-114">Azure での AKS 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="a2997-114">Create the AKS environment in Azure</span></span>

<span data-ttu-id="a2997-115">AKS の環境を作成するいくつかの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="a2997-115">There are several ways to create the AKS Environment.</span></span> <span data-ttu-id="a2997-116">これは、Azure CLI コマンドを使用して、または Azure portal を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2997-116">It can be done by using Azure-CLI commands or by using the Azure portal.</span></span>

<span data-ttu-id="a2997-117">ここで、Azure CLI を使用して、クラスターと、結果を確認する、Azure ポータルを作成する例をいくつかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="a2997-117">Here you can explore some examples using the Azure-CLI to create the cluster and the Azure portal to review the results.</span></span> <span data-ttu-id="a2997-118">また、Kubectl と Docker 開発用コンピューターにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2997-118">You also need to have Kubectl and Docker in your development machine.</span></span>  

## <a name="create-the-aks-cluster"></a><span data-ttu-id="a2997-119">AKS クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2997-119">Create the AKS cluster</span></span>

<span data-ttu-id="a2997-120">このコマンドを使用して AKS クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2997-120">Create the AKS cluster using this command:</span></span>

```console
az aks create --resource-group MSSampleResourceGroup --name MSSampleClusterK801 --agent-count 1 --generate-ssh-keys --location westus2
```

<span data-ttu-id="a2997-121">作成ジョブが完了したら後、は、Azure portal で作成された AKS を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a2997-121">After the creation job finishes, you can see the AKS created in the Azure portal:</span></span>

<span data-ttu-id="a2997-122">リソース グループ:</span><span class="sxs-lookup"><span data-stu-id="a2997-122">The resource group:</span></span>

![Azure AKS リソース グループのブラウザー ビュー。](media/aks-resource-group-view.png)

<span data-ttu-id="a2997-124">**図 4-17**. </span><span class="sxs-lookup"><span data-stu-id="a2997-124">**Figure 4-17**.</span></span> <span data-ttu-id="a2997-125">Azure から AKS リソース グループ ビュー。</span><span class="sxs-lookup"><span data-stu-id="a2997-125">AKS Resource Group view from Azure.</span></span>

<span data-ttu-id="a2997-126">AKS クラスター:</span><span class="sxs-lookup"><span data-stu-id="a2997-126">The AKS cluster:</span></span>

![AKS リソース グループのブラウザー ビュー。](media/aks-cluster-view.png)

<span data-ttu-id="a2997-128">**図 4-18**.</span><span class="sxs-lookup"><span data-stu-id="a2997-128">**Figure 4-18**.</span></span> <span data-ttu-id="a2997-129">AKS は、Azure から表示します。</span><span class="sxs-lookup"><span data-stu-id="a2997-129">AKS view from Azure.</span></span>

<span data-ttu-id="a2997-130">使用して作成されたノードを表示することもできます。`Azure-CLI`と`Kubectl`します。</span><span class="sxs-lookup"><span data-stu-id="a2997-130">You can also view the node created using `Azure-CLI` and `Kubectl`.</span></span>

<span data-ttu-id="a2997-131">最初に、資格情報の取得。</span><span class="sxs-lookup"><span data-stu-id="a2997-131">First, getting the credentials:</span></span>

```console
az aks get-credentials --resource-group MSSampleK8ClusterRG --name MSSampleK8Cluster
```

![上記のコマンドから出力コンソール:マージされた"MsSampleK8Cluster/root/.kube/config で現在のコンテキストとして選択します。](media/get-credentials-command-result.png)

<span data-ttu-id="a2997-133">**図 4-19**</span><span class="sxs-lookup"><span data-stu-id="a2997-133">**Figure 4-19**.</span></span> <span data-ttu-id="a2997-134">`aks get-credentials` コマンドの結果。</span><span class="sxs-lookup"><span data-stu-id="a2997-134">`aks get-credentials` command result.</span></span>

<span data-ttu-id="a2997-135">その後、Kubectl からノードを取得する:</span><span class="sxs-lookup"><span data-stu-id="a2997-135">And then, getting nodes from Kubectl:</span></span>

```console
kubectl get nodes
```

![コンソールは、上記のコマンドの出力:状態、経過時間 (時間実行されている)、およびバージョンを持つノードの一覧](media/kubectl-get-nodes-command-result.png)

<span data-ttu-id="a2997-137">**図 4-20**</span><span class="sxs-lookup"><span data-stu-id="a2997-137">**Figure 4-20**.</span></span> <span data-ttu-id="a2997-138">`kubectl get nodes` コマンドの結果。</span><span class="sxs-lookup"><span data-stu-id="a2997-138">`kubectl get nodes` command result.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a2997-139">[前へ](orchestrate-high-scalability-availability.md)
>[次へ](docker-apps-development-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a2997-139">[Previous](orchestrate-high-scalability-availability.md)
[Next](docker-apps-development-environment.md)</span></span>
