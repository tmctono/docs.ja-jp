---
title: コンテナーとサーバーレスの手法の組み合わせ
description: コンテナーと Kubernetes をサーバーレスアプローチと組み合わせる
ms.date: 06/30/2019
ms.openlocfilehash: 58aff43adbdd2e629370cc685f32c7b61c25f85e
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840593"
---
# <a name="combining-containers-and-serverless-approaches"></a><span data-ttu-id="c272b-103">コンテナーとサーバーレスの手法の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="c272b-103">Combining containers and serverless approaches</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c272b-104">多くの場合、マイクロサービスベースのアプリケーションは、ノード間の通信のために、コンテナー、オーケストレーション、およびメッセージパッシングに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="c272b-104">Frequently, microservices-based applications rely heavily on containers, orchestration, and message-passing for communication between nodes.</span></span> <span data-ttu-id="c272b-105">このメッセージングは Azure Functions にとって理想的なタスクですが、Kubernetes と関連ツールを使用して構成および展開されたアプリケーションの残りの部分では、この同じツールセット内で Azure Functions を利用できるようになると便利です。</span><span class="sxs-lookup"><span data-stu-id="c272b-105">This messaging is an ideal task for Azure Functions, but with the rest of the application configured and deployed using Kubernetes and related tools, it would be nice to be able to leverage Azure Functions within this same toolset.</span></span> <span data-ttu-id="c272b-106">幸い、Kubernetes ベースのアプリの他の部分と同じプロセスとツールを使用して、Docker コンテナーに Azure Functions をラップしてデプロイすることができます。</span><span class="sxs-lookup"><span data-stu-id="c272b-106">Fortunately, you can wrap Azure Functions in Docker containers and deploy them using the same processes and tools as the rest of your Kubernetes-based app.</span></span>

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a><span data-ttu-id="c272b-107">サーバーレスでコンテナーを使用することは、どのような場合に適していますか。</span><span class="sxs-lookup"><span data-stu-id="c272b-107">When does it make sense to use containers with serverless?</span></span>

<span data-ttu-id="c272b-108">既定では、サーバーレス関数は、実行されるプラットフォームについての知識がありません。</span><span class="sxs-lookup"><span data-stu-id="c272b-108">By default, your serverless functions have no knowledge of the platform on which they'll run.</span></span> <span data-ttu-id="c272b-109">ただし、場合によっては、コードを実行するコンテナーイメージをカスタマイズするために重要な特定の要件がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c272b-109">However, in some cases you may have specific requirements that make it important for you to customize the container image in which your code will run.</span></span> <span data-ttu-id="c272b-110">関数が特定の言語バージョンに依存しているか、既定のイメージでサポートされていない依存関係または構成要件を持っているため、カスタムイメージを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c272b-110">You may want to use a custom image because your function relies on a specific language version or has dependencies or configuration requirements that aren't supported by the default image.</span></span> <span data-ttu-id="c272b-111">このような場合は、独自のコンテナーをカスタマイズして、カスタム Docker コンテナーに関数をデプロイすることが理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="c272b-111">In these cases, it may make sense to customize your own container and deploy your function in a custom Docker container.</span></span>

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a><span data-ttu-id="c272b-112">Azure Functions でコンテナーを使用しない場合はどうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="c272b-112">When should you avoid using containers with Azure Functions?</span></span>

<span data-ttu-id="c272b-113">関数の従量課金プランの課金を利用することが予想される場合は、独自のコンテナーを使用している場合は、これを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="c272b-113">If you're expecting to benefit from the consumption plan billing for your function, you won't be able to do so if you're using your own container.</span></span> <span data-ttu-id="c272b-114">さらに、Docker コンテナーを使用するだけでなく、独自の Kubernetes クラスターに関数をデプロイした場合でも、Azure Functions によって提供される組み込みのスケーリングを利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c272b-114">What's more, if you go beyond just using a Docker container and deploy your functions to your own Kubernetes cluster, you'll no longer benefit from the built-in scaling provided by Azure Functions.</span></span> <span data-ttu-id="c272b-115">次に説明する Kubernetes のスケーリング機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c272b-115">You'll need to use Kubernetes' scaling features, described below.</span></span>

## <a name="how-to-combine-serverless-and-docker-containers"></a><span data-ttu-id="c272b-116">サーバーレスコンテナーと Docker コンテナーを結合する方法</span><span class="sxs-lookup"><span data-stu-id="c272b-116">How to combine serverless and Docker containers</span></span>

<span data-ttu-id="c272b-117">Docker コンテナーで Azure 関数をラップするには、Azure Functions Core Tools をインストールしてから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c272b-117">To wrap an Azure Function in a Docker container, install the Azure Functions Core Tools and then run the following command:</span></span>

```console
func init ProjectName --docker
```

<span data-ttu-id="c272b-118">次のオプションから、必要なワーカーランタイムを選択します。</span><span class="sxs-lookup"><span data-stu-id="c272b-118">Choose which worker runtime you want from the following options:</span></span>

- <span data-ttu-id="c272b-119">`dotnet` (C#)</span><span class="sxs-lookup"><span data-stu-id="c272b-119">`dotnet` (C#)</span></span>
- <span data-ttu-id="c272b-120">`node` (JavaScript)</span><span class="sxs-lookup"><span data-stu-id="c272b-120">`node` (JavaScript)</span></span>
- `python`

<span data-ttu-id="c272b-121">プロジェクトが作成されると、Dockerfile が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c272b-121">When the project is created, it will include a Dockerfile.</span></span> <span data-ttu-id="c272b-122">ここで、関数をローカルで作成してテストできます。</span><span class="sxs-lookup"><span data-stu-id="c272b-122">Now, you can create and test your function locally.</span></span> <span data-ttu-id="c272b-123">`docker build` と `docker run` のコマンドを使用してビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="c272b-123">Build and run it using the  `docker build` and `docker run` commands.</span></span> <span data-ttu-id="c272b-124">Docker サポートを使用して Azure Functions の構築を開始する詳細な手順については、「[カスタムイメージを使用した Linux での関数の作成](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)」チュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c272b-124">For detailed steps to get started building Azure Functions with Docker support, see the [Create a function on Linux using a custom image](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) tutorial.</span></span>

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a><span data-ttu-id="c272b-125">サーバーレスと Kubernetes を KEDA と組み合わせる方法</span><span class="sxs-lookup"><span data-stu-id="c272b-125">How to combine serverless and Kubernetes with KEDA</span></span>

<span data-ttu-id="c272b-126">Azure functions は、特定の関数を対象とするイベントの割合に基づいて、需要に合わせて自動的にスケールします。</span><span class="sxs-lookup"><span data-stu-id="c272b-126">Azure functions scale automatically to meet demand based on the rate of events that are targeting a given function.</span></span> <span data-ttu-id="c272b-127">さらに、Kubernetes を利用して関数をホストし、Kubernetes ベースのイベントドリブン自動スケール (KEDA) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c272b-127">Additionally, you can leverage Kubernetes to host your functions and use Kubernetes-based Event Driven Autoscaling, or KEDA.</span></span> <span data-ttu-id="c272b-128">イベントが発生していない場合、KEDA は0インスタンスにスケールダウンでき、イベントに応答して、水平ポッドオートスケーラーを使用して要求を満たすためにコンテナーの数をスケールアップできます。</span><span class="sxs-lookup"><span data-stu-id="c272b-128">When no events are occurring, KEDA can scale down to 0 instances, and then in response to events it can scale up the number of containers to meet the demand using its horizontal pod autoscaler.</span></span> <span data-ttu-id="c272b-129">[詳細については、KEDA での Azure functions のスケーリングに関するページを参照して](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)ください。</span><span class="sxs-lookup"><span data-stu-id="c272b-129">[Learn more about scaling Azure functions with KEDA](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).</span></span>

## <a name="references"></a><span data-ttu-id="c272b-130">参照</span><span class="sxs-lookup"><span data-stu-id="c272b-130">References</span></span>

- [<span data-ttu-id="c272b-131">Docker コンテナーで Azure Functions を実行する</span><span class="sxs-lookup"><span data-stu-id="c272b-131">Run Azure Functions in a Docker Container</span></span>](https://markheath.net/post/azure-functions-docker)
- [<span data-ttu-id="c272b-132">カスタムイメージを使用して Linux で関数を作成する</span><span class="sxs-lookup"><span data-stu-id="c272b-132">Create a function on Linux using a custom image</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [<span data-ttu-id="c272b-133">Kubernetes イベントドリブン自動スケールを使用した Azure Functions</span><span class="sxs-lookup"><span data-stu-id="c272b-133">Azure Functions with Kubernetes Event Driven Autoscaling</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)

>[!div class="step-by-step"]
><span data-ttu-id="c272b-134">[前へ](leverage-serverless-functions.md)
>[次へ](deploy-containers-azure.md)</span><span class="sxs-lookup"><span data-stu-id="c272b-134">[Previous](leverage-serverless-functions.md)
[Next](deploy-containers-azure.md)</span></span>
