---
title: Docker について
description: Docker について、もう少し理解を深めます。ここに示す簡単な例えが役立つ場合があります。
ms.date: 02/15/2019
ms.openlocfilehash: e3b3685f2fc6d5a9d33bb176d04ca910f0289344
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919875"
---
# <a name="what-is-docker"></a><span data-ttu-id="e2e4c-103">Docker について</span><span class="sxs-lookup"><span data-stu-id="e2e4c-103">What is Docker?</span></span>

<span data-ttu-id="e2e4c-104">[Docker](https://www.docker.com/) は、クラウドまたはオンプレミスで実行できる移植可能な自己完結型のコンテナーとしてアプリの展開を自動化する[オープン ソース プロジェクト](https://github.com/docker/docker)です。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-104">[Docker](https://www.docker.com/) is an [open-source project](https://github.com/docker/docker) for automating the deployment of applications as portable, self-sufficient containers that can run on the cloud or on-premises.</span></span> <span data-ttu-id="e2e4c-105">Docker は、クラウド、Linux、および Windows ベンダー (Microsoft を含む) と協力し、このテクノロジを促進し、進化させている[企業](https://www.docker.com/)でもあります。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-105">Docker is also a [company](https://www.docker.com/) that promotes and evolves this technology, working in collaboration with cloud, Linux, and Windows vendors, including Microsoft.</span></span>

![Docker コンテナーを実行できる場所を示す図。](./media/what-is-docker/docker-containers-run-anywhere.png)

<span data-ttu-id="e2e4c-107">**図 1-2**.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-107">**Figure 1-2**.</span></span> <span data-ttu-id="e2e4c-108">Docker は、ハイブリッド クラウドのすべてのレイヤーでコンテナーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-108">Docker deploys containers at all layers of the hybrid cloud</span></span>

<span data-ttu-id="e2e4c-109">上の図が示すように、Docker コンテナーは、オンプレミスのカスタマー データセンター内、外部サービス プロバイダー内、Azure 上のクラウド内など、どこでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-109">As shown in the above diagram, Docker containers can run anywhere, on-premises in the customer datacenter, in an external service provider or in the cloud, on Azure.</span></span> <span data-ttu-id="e2e4c-110">また、Docker イメージ コンテナーは、Linux と Windows 上でネイティブに実行できます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-110">Docker image containers can also run natively on Linux and Windows.</span></span> <span data-ttu-id="e2e4c-111">ただし、Windows イメージは Windows ホスト上でのみ実行でき、Linux イメージは (現在のところ Hyper-V Linux VM を使用して) Linux ホストと Windows ホスト上で実行できます (ここで言うホストとは、サーバーまたは VM です)。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-111">However, Windows images can run only on Windows hosts and Linux images can run on Linux hosts and Windows hosts (using a Hyper-V Linux VM, so far), where host means a server or a VM.</span></span>

<span data-ttu-id="e2e4c-112">開発者は、Windows、Linux、または macOS 上の開発環境を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-112">Developers can use development environments on Windows, Linux, or macOS.</span></span> <span data-ttu-id="e2e4c-113">開発用コンピューターで、アプリとその依存関係を含む、Docker イメージが展開されている Docker ホストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-113">On the development computer, the developer runs a Docker host where Docker images are deployed, including the app and its dependencies.</span></span> <span data-ttu-id="e2e4c-114">Linux または Mac 上で開発する場合は、Linux ベースの Docker ホストを使用し、Linux コンテナー用のイメージのみを作成できます</span><span class="sxs-lookup"><span data-stu-id="e2e4c-114">Developers who work on Linux or on the Mac, use a Docker host that's Linux-based, and they can only create images for Linux containers.</span></span> <span data-ttu-id="e2e4c-115">(Mac 上で開発する場合は、macOS からコードを編集したり Docker CLI を実行したりできますが、この記事の執筆時点では、macOS 上でコンテナーを直接実行することはできません)。Windows 上で開発する場合は、Linux または Windows コンテナーのいずれかのイメージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-115">(Developers working on the Mac can edit code or run the Docker CLI from macOS, but as of this writing, containers don't run directly on macOS.) Developers who work on Windows can create images for either Linux or Windows Containers.</span></span>

<span data-ttu-id="e2e4c-116">開発環境でコンテナーをホストし、開発ツールを追加するために、Docker は Windows 用または macOS 用の [Docker Community Edition (CE)](https://www.docker.com/community-edition) をリリースしています。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-116">To host containers in development environments and provide additional developer tools, Docker ships [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows or for macOS.</span></span> <span data-ttu-id="e2e4c-117">これらの製品で、コンテナーをホストするために必要な VM (Docker ホスト) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-117">These products install the necessary VM (the Docker host) to host the containers.</span></span> <span data-ttu-id="e2e4c-118">Docker は [Docker Enterprise Edition (EE) ](https://www.docker.com/enterprise-edition) もリリースしています。エンタープライズ開発向けに設計されており、大規模なビジネスクリティカル アプリケーションをビルドし、リリースし、運用環境で実行する IT チームに使用されています。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-118">Docker also makes available [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), which is designed for enterprise development and is used by IT teams who build, ship, and run large business-critical applications in production.</span></span>

<span data-ttu-id="e2e4c-119">[Windows コンテナー](/virtualization/windowscontainers/about/)を実行するには、次の 2 つの種類のランタイムがあります。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-119">To run [Windows Containers](/virtualization/windowscontainers/about/), there are two types of runtimes:</span></span>

- <span data-ttu-id="e2e4c-120">**Windows Server コンテナー**では、プロセスと名前空間の分離テクノロジを使用してアプリケーションの分離を提供します。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-120">**Windows Server Containers** provide application isolation through process and namespace isolation technology.</span></span> <span data-ttu-id="e2e4c-121">Windows Server コンテナーは、コンテナー ホストおよびホストで実行されているすべてのコンテナーとカーネルを共有します。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-121">A Windows Server Container shares a kernel with the container host and with all containers running on the host.</span></span>

- <span data-ttu-id="e2e4c-122">**Hyper-V コンテナー**では、各コンテナーを高度に最適化された仮想マシンで実行することで、Windows Server コンテナーによって提供される分離を拡張します。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-122">**Hyper-V Containers** expand on the isolation provided by Windows Server Containers by running each container in a highly optimized virtual machine.</span></span> <span data-ttu-id="e2e4c-123">この構成では、コンテナー ホストのカーネルは Hyper-V コンテナーと共有されないため、分離性に優れています。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-123">In this configuration, the kernel of the container host isn't shared with the Hyper-V Containers, providing better isolation.</span></span>

<span data-ttu-id="e2e4c-124">これらのコンテナーのイメージは、まったく同じように作成され、機能します。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-124">The images for these containers are created and work just the same way.</span></span> <span data-ttu-id="e2e4c-125">違いは、Hyper-V コンテナーを実行しているイメージからコンテナーを作成する方法で、追加のパラメーターが必要な点です。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-125">The difference is in how the container is created from the image—running a Hyper-V Container requires an extra parameter.</span></span> <span data-ttu-id="e2e4c-126">詳細については、「[Hyper-V コンテナー](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-126">For details, see [Hyper-V Containers](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container).</span></span>

## <a name="comparing-docker-containers-with-virtual-machines"></a><span data-ttu-id="e2e4c-127">Docker コンテナーと仮想マシンの比較</span><span class="sxs-lookup"><span data-stu-id="e2e4c-127">Comparing Docker containers with virtual machines</span></span>

<span data-ttu-id="e2e4c-128">図 1-3 は、VM と Docker コンテナーの比較を示しています。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-128">Figure 1-3 shows a comparison between VMs and Docker containers.</span></span>

![VM 環境とコンテナー環境の比較を示す図。](./media/what-is-docker/comparison-vms-docker-conatiners.png)

<span data-ttu-id="e2e4c-130">**図 1-3**.</span><span class="sxs-lookup"><span data-stu-id="e2e4c-130">**Figure 1-3**.</span></span> <span data-ttu-id="e2e4c-131">従来の仮想マシンと Docker コンテナーの比較</span><span class="sxs-lookup"><span data-stu-id="e2e4c-131">Comparison of traditional virtual machines to Docker containers</span></span>

<span data-ttu-id="e2e4c-132">上の図に示すように、VM の場合、ホスト サーバーには 3 つの基本レイヤーがあります。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-132">As shown in the above diagram, for VMs, there are three base layers in the host server.</span></span> <span data-ttu-id="e2e4c-133">下から順に、インフラストラクチャ、ホスト オペレーティング システム、ハイパーバイザーです。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-133">From the bottom-up: Infrastructure, Host Operating System, and a Hypervisor.</span></span> <span data-ttu-id="e2e4c-134">さらに、各 VM には独自の OS と必要なすべてのライブラリがあります。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-134">On top of all that, each VM has its own OS and all necessary libraries.</span></span> <span data-ttu-id="e2e4c-135">一方、Docker の場合、ホスト サーバーにはインフラストラクチャと OS のみがあります。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-135">On the other hand, for Docker, the host server only has the Infrastructure and the OS.</span></span> <span data-ttu-id="e2e4c-136">その上、コンテナー エンジンにより、コンテナーの分離は維持されますが、1 つのベース OS のサービスを共有できます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-136">On top of that, the container engine keeps containers isolated, but lets them share the single base OS's services.</span></span>

<span data-ttu-id="e2e4c-137">コンテナーに必要なリソースははるかに少ないため (たとえば、完全な OS は必要ありません)、導入が簡単で、すぐに開始することができます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-137">Because containers require far fewer resources (for example, they don't need a full OS), they're easy to deploy and they start fast.</span></span> <span data-ttu-id="e2e4c-138">そのため、密度を高めることができます。つまり、同じハードウェア ユニットでより多くのサービスを実行できるため、コストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-138">This allows you to have higher density, meaning that it allows you to run more services on the same hardware unit, thereby reducing costs.</span></span>

<span data-ttu-id="e2e4c-139">同じカーネル上で実行することの副作用として、VM よりも分離度が低くなります。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-139">As a side effect of running on the same kernel, you get less isolation than VMs.</span></span>

<span data-ttu-id="e2e4c-140">イメージの主な目的は、確実に異なるデプロイ間で同じ環境 (依存関係) にすることです。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-140">The main goal of an image is to ensure the same environment (dependencies) across different deployments.</span></span> <span data-ttu-id="e2e4c-141">つまり、自分のコンピューターでデバッグし、同じ環境が保証されている別のコンピューターにデプロイすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-141">This means that you can debug it on your machine and then deploy it to another machine, the same environment guaranteed.</span></span>

<span data-ttu-id="e2e4c-142">コンテナー イメージは、アプリやサービスをパッケージ化し、信頼性が高く、再現可能な方法で展開する方法です。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-142">A container image is a way to package an app or service and deploy it in a reliable and reproducible way.</span></span> <span data-ttu-id="e2e4c-143">Docker はテクノロジであるだけでなく、哲学やプロセスとも言うことができます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-143">You could say that Docker isn't only a technology but also a philosophy and a process.</span></span>

<span data-ttu-id="e2e4c-144">Docker を使用すると、「自分のマシンでは動作するのに運用環境で動作しないのはなぜだ」と言う開発者の言葉を聞くことはありません。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-144">When using Docker, you won't hear developers say, "It works on my machine, why not in production?"</span></span> <span data-ttu-id="e2e4c-145">単に "Docker で動作する" と言うことができます。これは、パッケージ化された Docker アプリケーションはサポートされている任意の Docker 環境で実行でき、すべてのデプロイ ターゲット (開発、QA、ステージング、運用など) 上で意図したとおりに実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-145">They can just say, "It runs on Docker", because the packaged Docker application can be executed on any supported Docker environment, and it runs the way it was intended to on all deployment targets (such as Dev, QA, staging, and production).</span></span>

## <a name="a-simple-analogy"></a><span data-ttu-id="e2e4c-146">簡単な例え</span><span class="sxs-lookup"><span data-stu-id="e2e4c-146">A simple analogy</span></span>

<span data-ttu-id="e2e4c-147">おそらく、簡単な例えで Docker の中核となる概念を理解できます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-147">Perhaps a simple analogy can help getting the grasp of the core concept of Docker.</span></span>

<span data-ttu-id="e2e4c-148">少しの間、1950 年代を振り返ってみましょう。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-148">Let's go back in time to the 1950s for a moment.</span></span> <span data-ttu-id="e2e4c-149">ワード プロセッサはなく、(ほぼ) あらゆる場所でコピー機が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-149">There were no word processors, and the photocopiers were used everywhere (well, kind of).</span></span>

<span data-ttu-id="e2e4c-150">たとえば、必要に応じて多数の手紙を迅速に発行し、顧客に郵送する業務を担当しているとします。実際の紙と封筒を使用して、各顧客の住所に物理的に送付する業務です (当時、電子メールはありませんでした)。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-150">Imagine you're responsible for quickly issuing batches of letters as required, to mail them to customers, using real paper and envelopes, to be delivered physically to each customer's address (there was no email back then).</span></span>

<span data-ttu-id="e2e4c-151">あるとき、手紙は、多数の段落の単なる組み合わせであることに気づきます。手紙の目的に従って、必要に応じて段落は選択され、配置されます。そこで、大幅な昇級を期待して、短時間で手紙を発行できるシステムを考案することにしました。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-151">At some point, you realize the letters are just a composition of a large set of paragraphs, which are picked and arranged as needed, according to the purpose of the letter, so you devise a system to issue letters quickly, expecting to get a hefty raise.</span></span>

<span data-ttu-id="e2e4c-152">システムは単純です。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-152">The system is simple:</span></span>

1. <span data-ttu-id="e2e4c-153">まず 1 枚に 1 つの段落が記載された透明なシートのデッキを用意します。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-153">You begin with a deck of transparent sheets containing one paragraph each.</span></span>

2. <span data-ttu-id="e2e4c-154">手紙のセットを発行するには、必要な段落が記載されたシートを選択し、見た目がよく、読みやすいように積み重ねて配置します。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-154">To issue a set of letters, you pick the sheets with the paragraphs you need, then you stack and align them so they look and read fine.</span></span>

3. <span data-ttu-id="e2e4c-155">最後に、そのセットをコピー機に置き、開始ボタンを押して必要な数の手紙を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-155">Finally, you place the set in the photocopier and press start to produce as many letters as required.</span></span>

<span data-ttu-id="e2e4c-156">簡単に言うと、これが Docker の中核となるアイデアです。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-156">So, simplifying, that's the core idea of Docker.</span></span>

<span data-ttu-id="e2e4c-157">Docker の各レイヤーは、プログラムのインストールなどのコマンドを実行した後に、結果としてファイルシステムに加えられる変更のセットです。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-157">In Docker, each layer is the resulting set of changes that happen to the filesystem after executing a command, such as, installing a program.</span></span>

<span data-ttu-id="e2e4c-158">そのため、レイヤーがコピーされた後にファイルシステムを "見る" と、プログラムのインストール時にレイヤーに追加されたすべてのファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-158">So, when you "look" at the filesystem after the layer has been copied, you see all the files, included the layer when the program was installed.</span></span>

<span data-ttu-id="e2e4c-159">イメージは、オペレーティング システムが既にインストールされている "コンピューター" にインストールすることができる、補助的な読み取り専用ハード ディスクと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-159">You can think of an image as an auxiliary read-only hard disk ready to be installed in a "computer" where the operating system is already installed.</span></span>

<span data-ttu-id="e2e4c-160">同様に、コンテナーは、イメージ ハード ディスクがインストールされている "コンピューター" と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-160">Similarly, you can think of a container as the "computer" with the image hard disk installed.</span></span> <span data-ttu-id="e2e4c-161">コンテナーは、コンピューターと同様に、電源をオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-161">The container, just like a computer, can be powered on or off.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e2e4c-162">[前へ](index.md)
>[次へ](docker-terminology.md)</span><span class="sxs-lookup"><span data-stu-id="e2e4c-162">[Previous](index.md)
[Next](docker-terminology.md)</span></span>
