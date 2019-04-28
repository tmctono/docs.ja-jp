---
title: Docker について
description: Docker の理解に深く取得は、単純な例をここで役立つことがあります。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: fbb91466a86c7082e89d0ac4a3673ad83ab39b88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921476"
---
# <a name="what-is-docker"></a><span data-ttu-id="07e13-103">Docker について</span><span class="sxs-lookup"><span data-stu-id="07e13-103">What is Docker?</span></span>

<span data-ttu-id="07e13-104">[Docker](https://www.docker.com/) は、クラウドまたはオンプレミスで実行できる移植可能な自己完結型のコンテナーとしてアプリの展開を自動化する[オープン ソース プロジェクト](https://github.com/docker/docker)です。</span><span class="sxs-lookup"><span data-stu-id="07e13-104">[Docker](https://www.docker.com/) is an [open-source project](https://github.com/docker/docker) for automating the deployment of applications as portable, self-sufficient containers that can run on the cloud or on-premises.</span></span> <span data-ttu-id="07e13-105">Docker は、クラウド、Linux、および Windows ベンダー (Microsoft を含む) と協力し、このテクノロジを促進し、進化させている[企業](https://www.docker.com/)でもあります。</span><span class="sxs-lookup"><span data-stu-id="07e13-105">Docker is also a [company](https://www.docker.com/) that promotes and evolves this technology, working in collaboration with cloud, Linux, and Windows vendors, including Microsoft.</span></span>

![Docker コンテナーは、オンプレミスのカスタマー データセンター内、外部サービス プロバイダー内、Azure 上のクラウド内など、どこでも実行できます。](./media/image2.png)

<span data-ttu-id="07e13-107">**図 1-2**します。</span><span class="sxs-lookup"><span data-stu-id="07e13-107">**Figure 1-2**.</span></span> <span data-ttu-id="07e13-108">Docker は、ハイブリッド クラウドのすべてのレイヤーでコンテナーを展開します。</span><span class="sxs-lookup"><span data-stu-id="07e13-108">Docker deploys containers at all layers of the hybrid cloud</span></span>

<span data-ttu-id="07e13-109">Docker イメージ コンテナーは、Linux と Windows 上でネイティブに実行できます。</span><span class="sxs-lookup"><span data-stu-id="07e13-109">Docker image containers can run natively on Linux and Windows.</span></span> <span data-ttu-id="07e13-110">ただし、Windows イメージは Windows ホスト上でのみ実行でき、Linux イメージは (現在のところ Hyper-V Linux VM を使用して) Linux ホストと Windows ホスト上で実行できます (ここで言うホストとは、サーバーまたは VM です)。</span><span class="sxs-lookup"><span data-stu-id="07e13-110">However, Windows images can run only on Windows hosts and Linux images can run on Linux hosts and Windows hosts (using a Hyper-V Linux VM, so far), where host means a server or a VM.</span></span>

<span data-ttu-id="07e13-111">開発者は、Windows、Linux、または macOS 上の開発環境を使用できます。</span><span class="sxs-lookup"><span data-stu-id="07e13-111">Developers can use development environments on Windows, Linux, or macOS.</span></span> <span data-ttu-id="07e13-112">開発用コンピューターで、アプリとその依存関係を含む、Docker イメージが展開されている Docker ホストを実行します。</span><span class="sxs-lookup"><span data-stu-id="07e13-112">On the development computer, the developer runs a Docker host where Docker images are deployed, including the app and its dependencies.</span></span> <span data-ttu-id="07e13-113">Linux または mac で作業する開発者は、Linux ベースである Docker ホストを使用して、のみ Linux コンテナー用のイメージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="07e13-113">Developers who work on Linux or on the Mac, use a Docker host that's Linux-based, and they can only create images for Linux containers.</span></span> <span data-ttu-id="07e13-114">(Mac で作業する開発者はコードを編集したり、macOS から Docker コマンド ライン インターフェイス (CLI) を実行するが、この記事の執筆時点のコンテナーが macOS 上で直接実行しないでください)。Windows 上で開発する場合は、Linux または Windows コンテナーのいずれかのイメージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="07e13-114">(Developers working on the Mac can edit code or run the Docker command-line interface (CLI) from macOS, but as of this writing, containers don't run directly on macOS.) Developers who work on Windows can create images for either Linux or Windows Containers.</span></span>

<span data-ttu-id="07e13-115">開発環境でコンテナーをホストし、開発ツールを追加するために、Docker は Windows 用または macOS 用の [Docker Community Edition (CE)](https://www.docker.com/community-edition) をリリースしています。</span><span class="sxs-lookup"><span data-stu-id="07e13-115">To host containers in development environments and provide additional developer tools, Docker ships [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows or for macOS.</span></span> <span data-ttu-id="07e13-116">これらの製品で、コンテナーをホストするために必要な VM (Docker ホスト) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="07e13-116">These products install the necessary VM (the Docker host) to host the containers.</span></span> <span data-ttu-id="07e13-117">Docker は [Docker Enterprise Edition (EE) ](https://www.docker.com/enterprise-edition) もリリースしています。エンタープライズ開発向けに設計されており、大規模なビジネスクリティカル アプリケーションをビルドし、リリースし、運用環境で実行する IT チームに使用されています。</span><span class="sxs-lookup"><span data-stu-id="07e13-117">Docker also makes available [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), which is designed for enterprise development and is used by IT teams who build, ship, and run large business-critical applications in production.</span></span>

<span data-ttu-id="07e13-118">[Windows コンテナー](/virtualization/windowscontainers/about/)を実行するには、次の 2 つの種類のランタイムがあります。</span><span class="sxs-lookup"><span data-stu-id="07e13-118">To run [Windows Containers](/virtualization/windowscontainers/about/), there are two types of runtimes:</span></span>

- <span data-ttu-id="07e13-119">**Windows Server Containers**プロセスと名前空間の分離テクノロジを使用してアプリケーションを分離します。</span><span class="sxs-lookup"><span data-stu-id="07e13-119">**Windows Server Containers** provide application isolation through process and namespace isolation technology.</span></span> <span data-ttu-id="07e13-120">Windows Server コンテナーは、コンテナー ホストおよびホストで実行されているすべてのコンテナーとカーネルを共有します。</span><span class="sxs-lookup"><span data-stu-id="07e13-120">A Windows Server Container shares a kernel with the container host and with all containers running on the host.</span></span>

- <span data-ttu-id="07e13-121">**HYPER-V コンテナー**大幅に最適化された仮想マシンで各コンテナーを実行して、Windows Server コンテナーによって提供される分離を展開します。</span><span class="sxs-lookup"><span data-stu-id="07e13-121">**Hyper-V Containers** expand on the isolation provided by Windows Server Containers by running each container in a highly optimized virtual machine.</span></span> <span data-ttu-id="07e13-122">この構成では、コンテナー ホストのカーネルは Hyper-V コンテナーと共有されないため、分離性に優れています。</span><span class="sxs-lookup"><span data-stu-id="07e13-122">In this configuration, the kernel of the container host isn't shared with the Hyper-V Containers, providing better isolation.</span></span>

<span data-ttu-id="07e13-123">これらのコンテナー イメージが作成され、まったく同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="07e13-123">The images for these containers are created and work just the same way.</span></span> <span data-ttu-id="07e13-124">違いは、イメージからコンテナーを作成する方法、HYPER-V コンテナーを実行するには、追加のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="07e13-124">The difference is in how the container is created from the image—running a Hyper-V Container requires an extra parameter.</span></span> <span data-ttu-id="07e13-125">詳細については、「[Hyper-V コンテナー](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e13-125">For details, see [Hyper-V Containers](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container).</span></span>

## <a name="comparing-docker-containers-with-virtual-machines"></a><span data-ttu-id="07e13-126">Docker コンテナーと仮想マシンの比較</span><span class="sxs-lookup"><span data-stu-id="07e13-126">Comparing Docker containers with virtual machines</span></span>

<span data-ttu-id="07e13-127">図 1-3 は、Vm と Docker の比較を示しています。 コンテナー。</span><span class="sxs-lookup"><span data-stu-id="07e13-127">Figure 1-3 shows a comparison between VMs and Docker containers.</span></span>

![VM の場合、ホスト サーバーに 3 つの基本レイヤーがあります。下からインフラストラクチャ、ホスト オペレーティング システム、ハイパーバイザーです。また、それらすべての上位には、各 VM の OS とすべての必要なライブラリがあります。](./media/image3.png)

<span data-ttu-id="07e13-130">**図 1-3**します。</span><span class="sxs-lookup"><span data-stu-id="07e13-130">**Figure 1-3**.</span></span> <span data-ttu-id="07e13-131">従来の仮想マシンと Docker コンテナーの比較</span><span class="sxs-lookup"><span data-stu-id="07e13-131">Comparison of traditional virtual machines to Docker containers</span></span>

<span data-ttu-id="07e13-132">コンテナーに必要なリソースははるかに少ないため (たとえば、完全な OS は必要ありません)、導入が簡単で、すぐに開始することができます。</span><span class="sxs-lookup"><span data-stu-id="07e13-132">Because containers require far fewer resources (for example, they don't need a full OS), they're easy to deploy and they start fast.</span></span> <span data-ttu-id="07e13-133">そのため、密度を高めることができます。つまり、同じハードウェア ユニットでより多くのサービスを実行できるため、コストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="07e13-133">This allows you to have higher density, meaning that it allows you to run more services on the same hardware unit, thereby reducing costs.</span></span>

<span data-ttu-id="07e13-134">同じカーネル上で実行することの副作用として、VM よりも分離度が低くなります。</span><span class="sxs-lookup"><span data-stu-id="07e13-134">As a side effect of running on the same kernel, you get less isolation than VMs.</span></span>

<span data-ttu-id="07e13-135">イメージの主な目的では、異なる展開間で同じ環境 (依存関係) を確認します。</span><span class="sxs-lookup"><span data-stu-id="07e13-135">The main goal of an image is to ensure the same environment (dependencies) across different deployments.</span></span> <span data-ttu-id="07e13-136">つまり、コンピューターでデバッグし、保証される同じ環境内の別のコンピューターに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="07e13-136">This means that you can debug it on your machine and then deploy it to another machine, the same environment guaranteed.</span></span>

<span data-ttu-id="07e13-137">コンテナー イメージは、アプリやサービスをパッケージ化し、信頼性が高く、再現可能な方法で展開する方法です。</span><span class="sxs-lookup"><span data-stu-id="07e13-137">A container image is a way to package an app or service and deploy it in a reliable and reproducible way.</span></span> <span data-ttu-id="07e13-138">Docker はテクノロジであるだけでなく、哲学やプロセスとも言うことができます。</span><span class="sxs-lookup"><span data-stu-id="07e13-138">You could say that Docker isn't only a technology but also a philosophy and a process.</span></span>

<span data-ttu-id="07e13-139">Docker を使用すると、「自分のマシンでは動作するのに運用環境で動作しないのはなぜだ」と言う開発者の言葉を聞くことはありません。</span><span class="sxs-lookup"><span data-stu-id="07e13-139">When using Docker, you won't hear developers say, "It works on my machine, why not in production?"</span></span> <span data-ttu-id="07e13-140">よう指示できますが「Docker で実行」のパッケージ化された Docker アプリケーションを実行できるため、Docker 環境では、サポートされているし、する方法は、すべてのデプロイ ターゲットで実行されます (など、開発、QA、ステージング、および運用)。</span><span class="sxs-lookup"><span data-stu-id="07e13-140">They can just say, "It runs on Docker", because the packaged Docker application can be executed on any supported Docker environment, and it runs the way it was intended to on all deployment targets (such as Dev, QA, staging, and production).</span></span>

## <a name="a-simple-analogy"></a><span data-ttu-id="07e13-141">簡単な例え</span><span class="sxs-lookup"><span data-stu-id="07e13-141">A simple analogy</span></span>

<span data-ttu-id="07e13-142">おそらく、簡単な例えで Docker の中核となる概念を理解できます。</span><span class="sxs-lookup"><span data-stu-id="07e13-142">Perhaps a simple analogy can help getting the grasp of the core concept of Docker.</span></span>

<span data-ttu-id="07e13-143">少しの間、1950 年代を振り返ってみましょう。</span><span class="sxs-lookup"><span data-stu-id="07e13-143">Let's go back in time to the 1950s for a moment.</span></span> <span data-ttu-id="07e13-144">Word のプロセッサがないと、複写機がすべての場所で使用された (機能しています)。</span><span class="sxs-lookup"><span data-stu-id="07e13-144">There were no word processors, and the photocopiers were used everywhere (well, kind of).</span></span>

<span data-ttu-id="07e13-145">たとえば、必要に応じて多数の手紙を迅速に発行し、顧客に郵送する業務を担当しているとします。実際の紙と封筒を使用して、各顧客の住所に物理的に送付する業務です (当時、電子メールはありませんでした)。</span><span class="sxs-lookup"><span data-stu-id="07e13-145">Imagine you're responsible for quickly issuing batches of letters as required, to mail them to customers, using real paper and envelopes, to be delivered physically to each customer's address (there was no email back then).</span></span>

<span data-ttu-id="07e13-146">あるとき、手紙は、多数の段落の単なる組み合わせであることに気づきます。手紙の目的に従って、必要に応じて段落は選択され、配置されます。そこで、大幅な昇級を期待して、短時間で手紙を発行できるシステムを考案することにしました。</span><span class="sxs-lookup"><span data-stu-id="07e13-146">At some point, you realize the letters are just a composition of a large set of paragraphs, which are picked and arranged as needed, according to the purpose of the letter, so you devise a system to issue letters quickly, expecting to get a hefty raise.</span></span>

<span data-ttu-id="07e13-147">システムは単純です。</span><span class="sxs-lookup"><span data-stu-id="07e13-147">The system is simple:</span></span>

1. <span data-ttu-id="07e13-148">まず 1 枚に 1 つの段落が記載された透明なシートのデッキを用意します。</span><span class="sxs-lookup"><span data-stu-id="07e13-148">You begin with a deck of transparent sheets containing one paragraph each.</span></span>

2. <span data-ttu-id="07e13-149">手紙のセットを発行するには、必要な段落が記載されたシートを選択し、見た目がよく、読みやすいように積み重ねて配置します。</span><span class="sxs-lookup"><span data-stu-id="07e13-149">To issue a set of letters, you pick the sheets with the paragraphs you need, then you stack and align them so they look and read fine.</span></span>

3. <span data-ttu-id="07e13-150">最後に、そのセットをコピー機に置き、開始ボタンを押して必要な数の手紙を作成します。</span><span class="sxs-lookup"><span data-stu-id="07e13-150">Finally, you place the set in the photocopier and press start to produce as many letters as required.</span></span>

<span data-ttu-id="07e13-151">簡単に言うと、これが Docker の中核となるアイデアです。</span><span class="sxs-lookup"><span data-stu-id="07e13-151">So, simplifying, that's the core idea of Docker.</span></span>

<span data-ttu-id="07e13-152">Docker の各レイヤーは、プログラムのインストールなどのコマンドを実行した後に、結果としてファイルシステムに加えられる変更のセットです。</span><span class="sxs-lookup"><span data-stu-id="07e13-152">In Docker, each layer is the resulting set of changes that happen to the filesystem after executing a command, such as, installing a program.</span></span>

<span data-ttu-id="07e13-153">そのため、レイヤーがコピーされた後にファイルシステムを "見る" と、プログラムのインストール時にレイヤーに追加されたすべてのファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07e13-153">So, when you "look" at the filesystem after the layer has been copied, you see all the files, included the layer when the program was installed.</span></span>

<span data-ttu-id="07e13-154">イメージは、オペレーティング システムが既にインストールされている "コンピューター" にインストールすることができる、補助的な読み取り専用ハード ディスクと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="07e13-154">You can think of an image as an auxiliary read-only hard disk ready to be installed in a "computer" where the operating system is already installed.</span></span>

<span data-ttu-id="07e13-155">同様に、コンテナーは、イメージ ハード ディスクがインストールされている "コンピューター" と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="07e13-155">Similarly, you can think of a container as the "computer" with the image hard disk installed.</span></span> <span data-ttu-id="07e13-156">コンテナーは、コンピューターと同様に、電源をオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="07e13-156">The container, just like a computer, can be powered on or off.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="07e13-157">[前へ](index.md)
>[次へ](docker-terminology.md)</span><span class="sxs-lookup"><span data-stu-id="07e13-157">[Previous](index.md)
[Next](docker-terminology.md)</span></span>
