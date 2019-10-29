---
title: Docker コンテナー、イメージ、レジストリ
description: Docker のアプリケーションのデプロイ方法において、レジストリが全体的に果たす主な役割について説明します。
ms.date: 02/15/2019
ms.openlocfilehash: bfef21cab7be89abaf33b89366d7cff2115a7cc6
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72770930"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="d9250-103">Docker コンテナー、イメージ、レジストリ</span><span class="sxs-lookup"><span data-stu-id="d9250-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="d9250-104">Docker を使用する場合、アプリケーションやサービスを作成し、それとその依存関係をコンテナー イメージにパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="d9250-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="d9250-105">イメージとは、アプリケーションまたはサービスと、その構成と依存関係の静的な表現です。</span><span class="sxs-lookup"><span data-stu-id="d9250-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="d9250-106">アプリケーションまたはサービスを実行するために、アプリケーションのイメージはインスタンス化され、コンテナーが作成されます。このコンテナーが Docker ホスト上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d9250-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="d9250-107">コンテナーは、最初に開発環境または PC でテストされます。</span><span class="sxs-lookup"><span data-stu-id="d9250-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="d9250-108">イメージをレジストリに保存します。レジストリはイメージのライブラリとして機能します。</span><span class="sxs-lookup"><span data-stu-id="d9250-108">You store images in a registry that acts as a library of images.</span></span> <span data-ttu-id="d9250-109">実稼働環境のオーケストレーターにデプロイする場合にレジストリが必要です。</span><span class="sxs-lookup"><span data-stu-id="d9250-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="d9250-110">Docker は [Docker Hub](https://hub.docker.com/) 経由で公開レジストリを保守します。他のベンダーは、[Azure Container Registry](https://azure.microsoft.com/services/container-registry/)を含むさまざまなイメージのコレクション用のレジストリを用意しています。</span><span class="sxs-lookup"><span data-stu-id="d9250-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images, including [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span></span> <span data-ttu-id="d9250-111">また、企業は自社の Docker イメージ用に非公開のレジストリをオンプレミスに持つことができます。</span><span class="sxs-lookup"><span data-stu-id="d9250-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="d9250-112">図 1-4 は、Docker のイメージとレジストリが他のコンポーネントとどのように関係しているかを示しています。</span><span class="sxs-lookup"><span data-stu-id="d9250-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="d9250-113">また、ベンダーから提供される複数のレジストリも示しています。</span><span class="sxs-lookup"><span data-stu-id="d9250-113">It also shows the multiple registry offerings from vendors.</span></span>

![Docker の基本的な分類を示す図。](./media/docker-containers-images-and-registries/taxonomy-docker-terms-concepts.png)

<span data-ttu-id="d9250-115">**図 1-4**</span><span class="sxs-lookup"><span data-stu-id="d9250-115">**Figure 1-4**.</span></span> <span data-ttu-id="d9250-116">Docker の用語と概念の分類</span><span class="sxs-lookup"><span data-stu-id="d9250-116">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="d9250-117">レジストリはイメージが格納される本棚のようなものであり、サービスや Web アプリを実行するコンテナーを構築するためにプルして使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9250-117">The registry is like a bookshelf where images are stored and available to be pulled for building containers to run services or web apps.</span></span> <span data-ttu-id="d9250-118">オンプレミスとパブリック クラウド上にプライベート Docker レジストリがあります。</span><span class="sxs-lookup"><span data-stu-id="d9250-118">There are private Docker registries on-premises and on the public cloud.</span></span> <span data-ttu-id="d9250-119">Docker Hub はエンタープライズ級のソリューションである Docker Trusted Registry と共に Docker によって管理されるパブリック レジストリであり、Azure では Azure Container Registry を提供しています。</span><span class="sxs-lookup"><span data-stu-id="d9250-119">Docker Hub is a public registry maintained by Docker, along the Docker Trusted Registry an enterprise-grade solution, Azure offers the Azure Container Registry.</span></span> <span data-ttu-id="d9250-120">AWS や Google などにもコンテナー レジストリがあります。</span><span class="sxs-lookup"><span data-stu-id="d9250-120">AWS, Google and others also have container registries.</span></span>

<span data-ttu-id="d9250-121">レジストリにイメージを配置することによって、フレームワーク レベルで、すべての依存関係を含む静的で不変なアプリケーション ビットを格納できます。</span><span class="sxs-lookup"><span data-stu-id="d9250-121">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="d9250-122">それにより、複数の環境でイメージをバージョン管理し、デプロイできるため、一貫したデプロイ ユニットを提供できます。</span><span class="sxs-lookup"><span data-stu-id="d9250-122">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="d9250-123">オンプレミスまたはクラウドでホストされる非公開のイメージ レジストリは、次の場合に推奨されます。</span><span class="sxs-lookup"><span data-stu-id="d9250-123">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

- <span data-ttu-id="d9250-124">機密保持のためにイメージを一般公開して共有することができない場合。</span><span class="sxs-lookup"><span data-stu-id="d9250-124">Your images must not be shared publicly due to confidentiality.</span></span>

- <span data-ttu-id="d9250-125">イメージと選択した展開環境間のネットワーク待機時間を最小限に抑えたい場合。</span><span class="sxs-lookup"><span data-stu-id="d9250-125">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="d9250-126">たとえば、実稼働環境が Azure の場合は、[Azure Container Registry](https://azure.microsoft.com/services/container-registry/) にイメージを保存して、ネットワークの待機時間を最小限に抑える方法があります。</span><span class="sxs-lookup"><span data-stu-id="d9250-126">For example, if your production environment is Azure, you probably want to store your images in [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so that network latency is minimal.</span></span> <span data-ttu-id="d9250-127">同様に、実稼働環境がオンプレミスの場合は、同じローカル ネットワーク内でオンプレミスの Docker Trusted Registry を使用できるようにする方法があります。</span><span class="sxs-lookup"><span data-stu-id="d9250-127">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d9250-128">[前へ](docker-terminology.md)
>[次へ](road-to-modern-applications-based-on-containers.md)</span><span class="sxs-lookup"><span data-stu-id="d9250-128">[Previous](docker-terminology.md)
[Next](road-to-modern-applications-based-on-containers.md)</span></span>
