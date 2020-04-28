---
title: クラウドネイティブサービスでのコンテナーとサーバーレスアプローチの組み合わせ
description: コンテナーと Kubernetes をサーバーレスアプローチと組み合わせる
ms.date: 04/23/2020
ms.openlocfilehash: fe9e9fd5d07132971d64bc6433a762fb7bd22048
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199665"
---
# <a name="combining-containers-and-serverless-approaches"></a><span data-ttu-id="af204-103">コンテナーとサーバーレスの手法の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="af204-103">Combining containers and serverless approaches</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="af204-104">クラウドネイティブアプリケーションは、通常、コンテナーとオーケストレーションを活用するサービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="af204-104">Cloud-native applications typically implement services leveraging containers and orchestration.</span></span> <span data-ttu-id="af204-105">多くの場合、アプリケーションのサービスの一部を Azure Functions として公開する機会があります。</span><span class="sxs-lookup"><span data-stu-id="af204-105">There are often opportunities to expose some of the application's services as Azure Functions.</span></span> <span data-ttu-id="af204-106">ただし、Kubernetes にデプロイされたクラウドネイティブアプリでは、この同じツールセット内で Azure Functions を活用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="af204-106">However, with a cloud-native app deployed to Kubernetes, it would be nice to leverage Azure Functions within this same toolset.</span></span> <span data-ttu-id="af204-107">幸いにも、Docker コンテナー内で Azure Functions をラップして、Kubernetes ベースのアプリの他の部分と同じプロセスとツールを使用してデプロイすることができます。</span><span class="sxs-lookup"><span data-stu-id="af204-107">Fortunately, you can wrap Azure Functions inside Docker containers and deploy them using the same processes and tools as the rest of your Kubernetes-based app.</span></span>

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a><span data-ttu-id="af204-108">サーバーレスでコンテナーを使用することは、どのような場合に適していますか。</span><span class="sxs-lookup"><span data-stu-id="af204-108">When does it make sense to use containers with serverless?</span></span>

<span data-ttu-id="af204-109">Azure 関数は、デプロイされているプラットフォームについての情報を持っていません。</span><span class="sxs-lookup"><span data-stu-id="af204-109">Your Azure Function has no knowledge of the platform on which it's deployed.</span></span> <span data-ttu-id="af204-110">シナリオによっては、特定の要件があり、関数コードを実行する環境をカスタマイズする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="af204-110">For some scenarios, you may have specific requirements and need to customize the environment on which your function code will run.</span></span> <span data-ttu-id="af204-111">依存関係をサポートするカスタムイメージ、または既定のイメージでサポートされていない構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="af204-111">You'll need a custom image that supports dependencies or a configuration not supported by the default image.</span></span> <span data-ttu-id="af204-112">このような場合は、カスタム Docker コンテナーに関数をデプロイするのが理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="af204-112">In these cases, it makes sense to deploy your function in a custom Docker container.</span></span>

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a><span data-ttu-id="af204-113">Azure Functions でコンテナーを使用しない場合はどうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="af204-113">When should you avoid using containers with Azure Functions?</span></span>

<span data-ttu-id="af204-114">従量課金制を使用する場合は、コンテナーで関数を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="af204-114">If you want to use consumption billing, you won't be able to run your function in a container.</span></span> <span data-ttu-id="af204-115">さらに、関数を Kubernetes クラスターにデプロイした場合は、Azure Functions によって提供される組み込みのスケーリングを利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="af204-115">What's more, if you deploy your function to a Kubernetes cluster, you'll no longer benefit from the built-in scaling provided by Azure Functions.</span></span> <span data-ttu-id="af204-116">この章の前半で説明した Kubernetes のスケーリング機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af204-116">You'll need to use Kubernetes' scaling features, described earlier in this chapter.</span></span>

## <a name="how-to-combine-serverless-and-docker-containers"></a><span data-ttu-id="af204-117">サーバーレスコンテナーと Docker コンテナーを結合する方法</span><span class="sxs-lookup"><span data-stu-id="af204-117">How to combine serverless and Docker containers</span></span>

<span data-ttu-id="af204-118">Docker コンテナーで Azure 関数をラップするには、 [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools)をインストールしてから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af204-118">To wrap an Azure Function in a Docker container, install the [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) and then run the following command:</span></span>

```console
func init ProjectName --worker-runtime dotnet --docker
```

<span data-ttu-id="af204-119">プロジェクトが作成されると、Dockerfile とワーカーランタイムがに`dotnet`構成されます。</span><span class="sxs-lookup"><span data-stu-id="af204-119">When the project is created, it will include a Dockerfile and the worker runtime configured to `dotnet`.</span></span> <span data-ttu-id="af204-120">ここで、関数をローカルで作成してテストできます。</span><span class="sxs-lookup"><span data-stu-id="af204-120">Now, you can create and test your function locally.</span></span> <span data-ttu-id="af204-121">コマンド`docker build`と`docker run`コマンドを使用してビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="af204-121">Build and run it using the  `docker build` and `docker run` commands.</span></span> <span data-ttu-id="af204-122">Docker サポートを使用して Azure Functions の構築を開始する詳細な手順については、「[カスタムイメージを使用した Linux での関数の作成](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)」チュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af204-122">For detailed steps to get started building Azure Functions with Docker support, see the [Create a function on Linux using a custom image](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) tutorial.</span></span>

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a><span data-ttu-id="af204-123">サーバーレスと Kubernetes を KEDA と組み合わせる方法</span><span class="sxs-lookup"><span data-stu-id="af204-123">How to combine serverless and Kubernetes with KEDA</span></span>

<span data-ttu-id="af204-124">Azure functions は、対象とするイベントの割合に基づいて、需要に合わせて自動的にスケールします。</span><span class="sxs-lookup"><span data-stu-id="af204-124">Azure functions scale automatically to meet demand based on the rate of events that are targeting it.</span></span> <span data-ttu-id="af204-125">いつでも AKS を利用して関数をホストし、Kubernetes ベースのイベントドリブン自動スケール (KEDA) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="af204-125">You can always leverage AKS to host your functions and use Kubernetes-based Event Driven Autoscaling, or KEDA.</span></span> <span data-ttu-id="af204-126">イベントが発生していない場合、KEDA はゼロインスタンスにスケールダウンできます。</span><span class="sxs-lookup"><span data-stu-id="af204-126">When no events are occurring, KEDA can scale down to zero instances.</span></span> <span data-ttu-id="af204-127">[詳細については、KEDA での Azure functions のスケーリングに関するページを参照して](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)ください。</span><span class="sxs-lookup"><span data-stu-id="af204-127">[Learn more about scaling Azure functions with KEDA](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="af204-128">[前へ](leverage-serverless-functions.md)
>[次へ](deploy-containers-azure.md)</span><span class="sxs-lookup"><span data-stu-id="af204-128">[Previous](leverage-serverless-functions.md)
[Next](deploy-containers-azure.md)</span></span>
