---
title: クラウドネイティブサービスでのコンテナーとサーバーレスアプローチの組み合わせ
description: コンテナーと Kubernetes をサーバーレスアプローチと組み合わせる
ms.date: 04/23/2020
ms.openlocfilehash: a6ae17543c9075ca84126a4c19f9f51887f7fe9a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895647"
---
# <a name="combining-containers-and-serverless-approaches"></a><span data-ttu-id="452e8-103">コンテナーとサーバーレスの手法の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="452e8-103">Combining containers and serverless approaches</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="452e8-104">クラウドネイティブアプリケーションは、通常、コンテナーとオーケストレーションを活用するサービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="452e8-104">Cloud-native applications typically implement services leveraging containers and orchestration.</span></span> <span data-ttu-id="452e8-105">多くの場合、アプリケーションのサービスの一部を Azure Functions として公開する機会があります。</span><span class="sxs-lookup"><span data-stu-id="452e8-105">There are often opportunities to expose some of the application's services as Azure Functions.</span></span> <span data-ttu-id="452e8-106">ただし、Kubernetes にデプロイされたクラウドネイティブアプリでは、この同じツールセット内で Azure Functions を活用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="452e8-106">However, with a cloud-native app deployed to Kubernetes, it would be nice to leverage Azure Functions within this same toolset.</span></span> <span data-ttu-id="452e8-107">幸いにも、Docker コンテナー内で Azure Functions をラップして、Kubernetes ベースのアプリの他の部分と同じプロセスとツールを使用してデプロイすることができます。</span><span class="sxs-lookup"><span data-stu-id="452e8-107">Fortunately, you can wrap Azure Functions inside Docker containers and deploy them using the same processes and tools as the rest of your Kubernetes-based app.</span></span>

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a><span data-ttu-id="452e8-108">サーバーレスでコンテナーを使用することは、どのような場合に適していますか。</span><span class="sxs-lookup"><span data-stu-id="452e8-108">When does it make sense to use containers with serverless?</span></span>

<span data-ttu-id="452e8-109">Azure 関数は、デプロイされているプラットフォームについての情報を持っていません。</span><span class="sxs-lookup"><span data-stu-id="452e8-109">Your Azure Function has no knowledge of the platform on which it's deployed.</span></span> <span data-ttu-id="452e8-110">シナリオによっては、特定の要件があり、関数コードを実行する環境をカスタマイズする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="452e8-110">For some scenarios, you may have specific requirements and need to customize the environment on which your function code will run.</span></span> <span data-ttu-id="452e8-111">依存関係をサポートするカスタムイメージ、または既定のイメージでサポートされていない構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="452e8-111">You'll need a custom image that supports dependencies or a configuration not supported by the default image.</span></span> <span data-ttu-id="452e8-112">このような場合は、カスタム Docker コンテナーに関数をデプロイするのが理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="452e8-112">In these cases, it makes sense to deploy your function in a custom Docker container.</span></span>

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a><span data-ttu-id="452e8-113">Azure Functions でコンテナーを使用しない場合はどうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="452e8-113">When should you avoid using containers with Azure Functions?</span></span>

<span data-ttu-id="452e8-114">従量課金制を使用する場合は、コンテナーで関数を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="452e8-114">If you want to use consumption billing, you won't be able to run your function in a container.</span></span> <span data-ttu-id="452e8-115">さらに、関数を Kubernetes クラスターにデプロイした場合は、Azure Functions によって提供される組み込みのスケーリングを利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="452e8-115">What's more, if you deploy your function to a Kubernetes cluster, you'll no longer benefit from the built-in scaling provided by Azure Functions.</span></span> <span data-ttu-id="452e8-116">この章の前半で説明した Kubernetes のスケーリング機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="452e8-116">You'll need to use Kubernetes' scaling features, described earlier in this chapter.</span></span>

## <a name="how-to-combine-serverless-and-docker-containers"></a><span data-ttu-id="452e8-117">サーバーレスコンテナーと Docker コンテナーを結合する方法</span><span class="sxs-lookup"><span data-stu-id="452e8-117">How to combine serverless and Docker containers</span></span>

<span data-ttu-id="452e8-118">Docker コンテナーで Azure 関数をラップするには、 [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools)をインストールしてから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="452e8-118">To wrap an Azure Function in a Docker container, install the [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) and then run the following command:</span></span>

```console
func init ProjectName --worker-runtime dotnet --docker
```

<span data-ttu-id="452e8-119">プロジェクトが作成されると、Dockerfile とワーカーランタイムがに`dotnet`構成されます。</span><span class="sxs-lookup"><span data-stu-id="452e8-119">When the project is created, it will include a Dockerfile and the worker runtime configured to `dotnet`.</span></span> <span data-ttu-id="452e8-120">ここで、関数をローカルで作成してテストできます。</span><span class="sxs-lookup"><span data-stu-id="452e8-120">Now, you can create and test your function locally.</span></span> <span data-ttu-id="452e8-121">コマンド`docker build`と`docker run`コマンドを使用してビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="452e8-121">Build and run it using the  `docker build` and `docker run` commands.</span></span> <span data-ttu-id="452e8-122">Docker サポートを使用して Azure Functions の構築を開始する詳細な手順については、「[カスタムイメージを使用した Linux での関数の作成](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)」チュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="452e8-122">For detailed steps to get started building Azure Functions with Docker support, see the [Create a function on Linux using a custom image](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) tutorial.</span></span>

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a><span data-ttu-id="452e8-123">サーバーレスと Kubernetes を KEDA と組み合わせる方法</span><span class="sxs-lookup"><span data-stu-id="452e8-123">How to combine serverless and Kubernetes with KEDA</span></span>

<span data-ttu-id="452e8-124">この章では、Azure Functions のプラットフォームが需要に応じて自動的にスケールアウトされることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="452e8-124">In this chapter, you've seen that the Azure Functions' platform automatically scales out to meet demand.</span></span> <span data-ttu-id="452e8-125">ただし、コンテナー化された関数を AKS に配置する場合、組み込みのスケーリング機能は失われます。</span><span class="sxs-lookup"><span data-stu-id="452e8-125">When deploying containerized functions to AKS, however, you lose the built-in scaling functionality.</span></span> <span data-ttu-id="452e8-126">これには、 [Kubernetes ベースのイベントドリブン (KEDA)](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)が用意されています。</span><span class="sxs-lookup"><span data-stu-id="452e8-126">To the rescue comes [Kubernetes-based Event Driven (KEDA)](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span></span> <span data-ttu-id="452e8-127">これにより、コンテナー化さ`event-driven Kubernetes workloads,`れた関数を含めるための高度な自動スケールが可能になります。</span><span class="sxs-lookup"><span data-stu-id="452e8-127">It enables fine-grained autoscaling for `event-driven Kubernetes workloads,` including containerized functions.</span></span>

<span data-ttu-id="452e8-128">KEDA は、Docker コンテナー内の関数のランタイムにイベントドリブンスケーリング機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="452e8-128">KEDA provides event-driven scaling functionality to the Functions' runtime in a Docker container.</span></span> <span data-ttu-id="452e8-129">KEDA は、負荷に基づいて、ゼロのインスタンス (イベントが発生`n instances`していない場合) からまで拡張できます。</span><span class="sxs-lookup"><span data-stu-id="452e8-129">KEDA can scale from zero instances (when no events are occurring) out to `n instances`, based on load.</span></span> <span data-ttu-id="452e8-130">Kubernetes オートスケーラー (水平ポッドオートスケーラー) にカスタムメトリックを公開することによって、自動スケールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="452e8-130">It enables autoscaling by exposing custom metrics to the Kubernetes autoscaler (Horizontal Pod Autoscaler).</span></span> <span data-ttu-id="452e8-131">KEDA で Functions のコンテナーを使用すると、任意の Kubernetes クラスターにおいてサーバーレス関数の機能をレプリケートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="452e8-131">Using Functions containers with KEDA makes it possible to replicate serverless function capabilities in any Kubernetes cluster.</span></span>

<span data-ttu-id="452e8-132">KEDA プロジェクトは、Cloud Native Computing Foundation (CNCF) によって管理されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="452e8-132">It is worth noting that the KEDA project is now managed by the Cloud Native Computing Foundation (CNCF).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="452e8-133">[前へ](leverage-serverless-functions.md)
>[次へ](deploy-containers-azure.md)</span><span class="sxs-lookup"><span data-stu-id="452e8-133">[Previous](leverage-serverless-functions.md)
[Next](deploy-containers-azure.md)</span></span>
