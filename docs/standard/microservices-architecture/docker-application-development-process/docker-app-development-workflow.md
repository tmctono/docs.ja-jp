---
title: Docker アプリの開発ワークフロー
description: Docker ベースのアプリケーションを開発するためのワークフローの詳細を理解します。 まず、段階的に見ていき、Dockerfile の最適化について詳しく確認し、最終的には Visual Studio を使用する際に利用できる簡略化されたワークフローを理解します。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: f23a2352d86d5c77d2f05af2a2452fb3c944e049
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613370"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="8b52e-104">Docker アプリの開発ワークフロー</span><span class="sxs-lookup"><span data-stu-id="8b52e-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="8b52e-105">アプリケーション開発のライフ サイクルは、開発者のコンピューターから始まります。そこで、開発者の好みの言語を使用してアプリケーションをコーディングし、ローカルでテストします。</span><span class="sxs-lookup"><span data-stu-id="8b52e-105">The application development life cycle starts at your computer, as a developer, where you code the application using your preferred language and test it locally.</span></span> <span data-ttu-id="8b52e-106">このワークフローでは、選択した言語、フレームワークおよびプラットフォームにかかわらず、常に Docker コンテナーをローカルで開発およびテストします。</span><span class="sxs-lookup"><span data-stu-id="8b52e-106">With this workflow, no matter which language, framework, and platform you choose, you're always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="8b52e-107">各コンテナー (Docker イメージのインスタンス) には、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-107">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="8b52e-108">選択したオペレーティング システム (Linux ディストリビューション、Windows Nano Server、Windows Server Core など)。</span><span class="sxs-lookup"><span data-stu-id="8b52e-108">An operating system selection, for example, a Linux distribution, Windows Nano Server, or Windows Server Core.</span></span>

- <span data-ttu-id="8b52e-109">開発時に追加したファイル (ソース コードおよびアプリケーション バイナリなど)。</span><span class="sxs-lookup"><span data-stu-id="8b52e-109">Files added during development, for example, source code and application binaries.</span></span>

- <span data-ttu-id="8b52e-110">構成情報 (環境の設定および依存関係など)。</span><span class="sxs-lookup"><span data-stu-id="8b52e-110">Configuration information, such as environment settings and dependencies.</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="8b52e-111">Docker のコンテナー ベースのアプリケーションを開発するためのワークフロー</span><span class="sxs-lookup"><span data-stu-id="8b52e-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="8b52e-112">このセクションでは、Docker のコンテナー ベースのアプリケーションの*内側のループ*の開発ワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="8b52e-113">内側のループのワークフローは、運用への展開まで含めることができる DevOps のより広範なワークフローを意味するのではなく、開発者のコンピューター上で実行される開発作業のみに重点が置かれています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-113">The inner-loop workflow means it's not considering the broader DevOps workflow, that can include up to production deployment, and just focuses on the development work done on the developer's computer.</span></span> <span data-ttu-id="8b52e-114">環境を設定する初期手順は、一度のみ実行されるものなので含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8b52e-114">The initial steps to set up the environment aren't included, since those steps are done only once.</span></span>

<span data-ttu-id="8b52e-115">アプリケーションは、自分のサービスと追加のライブラリ (依存関係) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="8b52e-116">Docker アプリケーションを構築するときの基本手順を次の図 5-1 に示します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![<span data-ttu-id="8b52e-117">Docker アプリの開発プロセス:1 - アプリをコーディングする、2- Dockerfile を書き込む、3 - Dockerfile で定義されているイメージを作成する、4 - (省略可能) docker-compose.yml ファイルにサービスを作成する、5 - コンテナーまたは docker-compose アプリを実行する、6 - アプリまたはマイクロサービスをテストする、7 - リポジトリにプッシュして繰り返す。</span><span class="sxs-lookup"><span data-stu-id="8b52e-117">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span> ](./media/image1.png)

<span data-ttu-id="8b52e-118">**図 5-1**</span><span class="sxs-lookup"><span data-stu-id="8b52e-118">**Figure 5-1.**</span></span> <span data-ttu-id="8b52e-119">Docker のコンテナー化されたアプリケーションを開発するための詳細なワークフロー</span><span class="sxs-lookup"><span data-stu-id="8b52e-119">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="8b52e-120">このセクションでは、このプロセス全体について詳細に記載されており、主要な各手順は、Visual Studio 環境に重点を置いて説明されています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-120">In this section, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="8b52e-121">エディター/CLI 開発アプローチ (Visual Studio Code と macOS または Windows 上の Docker CLI など) を使用する場合、Visual Studio を使用する場合よりも、通常はより詳細にすべての手順を把握している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-121">When you're using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you're using Visual Studio.</span></span> <span data-ttu-id="8b52e-122">CLI 環境での作業の詳細については、電子書籍「[Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/)」 (Microsoft のプラットフォームおよびツールとコンテナー化された Docker アプリケーションのライフサイクル) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b52e-122">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="8b52e-123">Visual Studio 2017 を使用している場合、これらの手順の多くは自動処理されるので、生産性が大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-123">When you're using Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="8b52e-124">これは、Visual Studio 2017 を使用しており、複数のコンテナー アプリケーションをターゲットとしている場合に特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-124">This is especially true when you're using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="8b52e-125">たとえば、マウスを 1 回クリックするだけで、Visual Studio では、アプリケーションに適した構成で Dockerfile と docker-compose.yml ファイルをプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-125">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="8b52e-126">そのアプリケーションを Visual Studio で実行すると、Docker イメージが構築され、Docker で直接マルチコンテナー アプリケーションが実行されます。また、一度に複数のコンテナーをデバッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-126">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="8b52e-127">これらの機能により、開発の速度が向上します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-127">These features will boost your development speed.</span></span>

<span data-ttu-id="8b52e-128">しかし、Visual Studio によって、これらの手順が自動化されるからといって、Docker の背後で何が起こっているのか知らなくてもよいというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="8b52e-128">However, just because Visual Studio makes those steps automatic doesn't mean that you don't need to know what's going on underneath with Docker.</span></span> <span data-ttu-id="8b52e-129">したがって、次のガイダンスではすべての手順について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-129">Therefore, the following guidance details every step.</span></span>

![1 - アプリをコーディングする](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="8b52e-131">手順 1.</span><span class="sxs-lookup"><span data-stu-id="8b52e-131">Step 1.</span></span> <span data-ttu-id="8b52e-132">コーディングを開始して、初期アプリケーションまたはサービス ベースラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-132">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="8b52e-133">Docker アプリケーションの開発方法は、Docker を使用しないアプリケーションの開発方法と似ています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-133">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="8b52e-134">違いは、Docker 用の開発中に、ローカル環境において Docker コンテナー内で実行するアプリケーションまたはサービスを展開およびテストするということです (Docker による Linux VM のセットアップ、または Windows コンテナーを使用する場合は直接 Windows で)。</span><span class="sxs-lookup"><span data-stu-id="8b52e-134">The difference is that while developing for Docker, you're deploying and testing your application or services running within Docker containers in your local environment (either a Linux VM setup by Docker or directly Windows if using Windows Containers).</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="8b52e-135">Visual Studio でのローカル環境のセットアップ</span><span class="sxs-lookup"><span data-stu-id="8b52e-135">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="8b52e-136">最初に、次の手順で説明する、Windows 用の [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-136">To begin, make sure you have [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) for Windows installed, as explained in the following instructions:</span></span>

<span data-ttu-id="8b52e-137">[Get started with Docker CE for Windows](https://docs.docker.com/docker-for-windows/) (Windows 用の Docker CE の概要)</span><span class="sxs-lookup"><span data-stu-id="8b52e-137">[Get started with Docker CE for Windows](https://docs.docker.com/docker-for-windows/)</span></span>

<span data-ttu-id="8b52e-138">さらに、図 5-2 に示すように、**.NET Core クロスプラットフォーム開発**ワークロードがインストールされた、Visual Studio 2017 バージョン 15.7 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-138">In addition, you need Visual Studio 2017 version 15.7 or later, with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![Visual Studio のインストール時での、.NET Core クロスプラットフォーム開発ワークロードの選択。](./media/image3.png)

<span data-ttu-id="8b52e-140">**図 5-2**</span><span class="sxs-lookup"><span data-stu-id="8b52e-140">**Figure 5-2**.</span></span> <span data-ttu-id="8b52e-141">Visual Studio 2017 のセットアップ時での **.NET Core クロスプラットフォーム開発**ワークロードの選択</span><span class="sxs-lookup"><span data-stu-id="8b52e-141">Selecting the **.NET Core cross-platform development** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="8b52e-142">アプリケーションのコーディングは、アプリケーションで Docker を有効にし、Docker で展開してテストする前から、単純な .NET で開始することができます (コンテナーを使用する計画がある場合、通常は .NET Core で)。</span><span class="sxs-lookup"><span data-stu-id="8b52e-142">You can start coding your application in plain .NET (usually in .NET Core if you're planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="8b52e-143">ただし、実際の環境となることに加え、問題が早く検出されるため、できるだけ早く Docker で作業を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8b52e-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="8b52e-144">Docker は、Visual Studio では、ほとんど透過的で、使用しやすくなっているため、このようにすることが推奨されます。この最良の例は、Visual Studio からのマルチコンテナー アプリケーションのデバッグです。</span><span class="sxs-lookup"><span data-stu-id="8b52e-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="8b52e-145">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8b52e-145">Additional resources</span></span>

- <span data-ttu-id="8b52e-146">**Windows 用の Docker CE の概要** \\</span><span class="sxs-lookup"><span data-stu-id="8b52e-146">**Get started with Docker CE for Windows** \\</span></span>
  <https://docs.docker.com/docker-for-windows/>

- <span data-ttu-id="8b52e-147">**Visual Studio 2017** \\</span><span class="sxs-lookup"><span data-stu-id="8b52e-147">**Visual Studio 2017** \\</span></span>
  [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)

![2 - Dockerfile を作成する](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="8b52e-149">手順 2.</span><span class="sxs-lookup"><span data-stu-id="8b52e-149">Step 2.</span></span> <span data-ttu-id="8b52e-150">既存の .NET 基本イメージに関連する Dockerfile を作成します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-150">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="8b52e-151">Dockerfile は、構築するカスタム イメージごとに必要です。また、Visual Studio から自動的に展開する場合も、Docker CLI (docker run および docker-compose コマンド) を使用して手動で展開する場合も、展開するコンテナーごとに Dockerfile が必要です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-151">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="8b52e-152">アプリケーションにカスタム サービスが 1 つ含まれている場合、Dockerfile が 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-152">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="8b52e-153">(マイクロサービス アーキテクチャの場合のように) アプリケーションに複数のサービスが含まれる場合、サービスごとに Dockerfile が 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-153">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="8b52e-154">Dockerfile は、アプリケーションまたはサービスのルート フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-154">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="8b52e-155">これには、コンテナーでアプリケーションまたはサービスを設定して実行する方法を Docker に指示するコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-155">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="8b52e-156">手動でコードに Dockerfile を作成し、.NET の依存関係と共にプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-156">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="8b52e-157">Visual Studio と Docker 用のツールでは、このタスクはマウスを何度かクリックするのみで実行できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-157">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="8b52e-158">Visual Studio 2017 で新しいプロジェクトを作成する場合、図 5-3 に示すように、**[Enable Docker Support]\(Docker サポートを有効にする\)** というオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-158">When you create a new project in Visual Studio 2017, there's an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![Visual Studio 2017 で新しい ASP.NET Core プロジェクトを作成するときの [Enable Docker Support]\(Docker サポートを有効にする) チェック ボックス](./media/image5.png)

<span data-ttu-id="8b52e-160">**図 5-3**</span><span class="sxs-lookup"><span data-stu-id="8b52e-160">**Figure 5-3**.</span></span> <span data-ttu-id="8b52e-161">Visual Studio 2017 で新しい ASP.NET Core プロジェクトを作成するときの Docker サポートの有効化</span><span class="sxs-lookup"><span data-stu-id="8b52e-161">Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2017</span></span>

<span data-ttu-id="8b52e-162">また、図 5-4 に示すように、**ソリューション エクスプローラー**でプロジェクトを右クリックし、**[追加]** > **[Docker サポート]** を選択することで、既存の ASP.NET Core Web アプリ プロジェクトに対して Docker サポートを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-162">You can also enable Docker support on an existing ASP.NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support**, as shown in Figure 5-4.</span></span>

![Visual Studio の Docker サポートの追加メニュー オプション](./media/image6.png)

<span data-ttu-id="8b52e-164">**図 5-4**</span><span class="sxs-lookup"><span data-stu-id="8b52e-164">**Figure 5-4**.</span></span> <span data-ttu-id="8b52e-165">既存の Visual Studio 2017 プロジェクトでの Docker サポートの有効化</span><span class="sxs-lookup"><span data-stu-id="8b52e-165">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="8b52e-166">この操作で、必要な構成のプロジェクトに *Dockerfile* が追加され、ASP.NET Core プロジェクトでのみ使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-166">This action adds a *Dockerfile* to the project with the required configuration, and is only available on ASP.NET Core projects.</span></span>

<span data-ttu-id="8b52e-167">同じように、Visual Studio で **[追加] > [Container Orchestrator Support]\(コンテナー オーケストレーターのサポート\)** オプションを使用して、ソリューション全体の docker-compose.yml ファイルを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-167">In a similar fashion, Visual Studio can also add a docker-compose.yml file for the whole solution with the option **Add > Container Orchestrator Support**.</span></span> <span data-ttu-id="8b52e-168">手順 4 で、このオプションについてさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-168">In step 4, we'll explore this option in greater detail.</span></span>

### <a name="using-an-existing-official-net-docker-image"></a><span data-ttu-id="8b52e-169">既存の公式の .NET Docker イメージの使用</span><span class="sxs-lookup"><span data-stu-id="8b52e-169">Using an existing official .NET Docker image</span></span>

<span data-ttu-id="8b52e-170">通常、[Docker Hub](https://hub.docker.com/) レジストリなどの公式のリポジトリから取得する基本イメージ上に、コンテナーのカスタム イメージをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8b52e-170">You usually build a custom image for your container on top of a base image you get from an official repository like the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="8b52e-171">Visual Studio で Docker のサポートを有効にした場合、背後ではこれがまさに発生します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-171">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="8b52e-172">Dockerfile では、既存の `aspnetcore` イメージを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-172">Your Dockerfile will use an existing `aspnetcore` image.</span></span>

<span data-ttu-id="8b52e-173">選択した OS とフレームワークによって、使用できる Docker イメージとリポジトリについては、既に説明しています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-173">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="8b52e-174">たとえば、ASP.NET Core (Linux または Windows) を使用したい場合は、`mcr.microsoft.com/dotnet/core/aspnet:2.2` のイメージを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-174">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is `mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="8b52e-175">この場合は、コンテナーに使用する基本の Docker イメージのみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-175">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="8b52e-176">これは、`FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` を Dockerfile に追加することで行います。</span><span class="sxs-lookup"><span data-stu-id="8b52e-176">You do that by adding `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` to your Dockerfile.</span></span> <span data-ttu-id="8b52e-177">これは、Visual Studio が自動的に実行しますが、バージョンを更新する場合は、この値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-177">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="8b52e-178">バージョン番号を使用して Docker Hub の公式の .NET イメージ リポジトリを使うと、同じ言語機能が (開発、テスト、および実稼働環境などの) すべてのコンピューターで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-178">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="8b52e-179">次の例では、ASP.NET Core コンテナー用のサンプルの Dockerfile を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-179">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="8b52e-180">この場合、イメージは、公式の ASP.NET Core Docker イメージ (Linux および Windows 用マルチアーキテクチャ) のバージョン 2.2 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-180">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="8b52e-181">この設定は、`FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-181">This is the setting `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="8b52e-182">(この基本イメージの詳細については、「[.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/)」 (.NET Core Docker イメージ) ページを参照してください)。Dockerfile では、実行時に使用する、リッスンする TCP ポートを、Docker に指示する必要があります (ここでは、EXPOSE 設定で構成したポート 80)。</span><span class="sxs-lookup"><span data-stu-id="8b52e-182">(For more information about this base image, see the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="8b52e-183">使用している言語とフレームワークによっては、Dockerfile に別の構成設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-183">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="8b52e-184">たとえば、`["dotnet", "MySingleContainerWebApp.dll"]` の ENTRYPOINT 行では、.NET Core アプリケーションを実行するように Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-184">For instance, the ENTRYPOINT line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="8b52e-185">SDK と .NET Core CLI (dotnet CLI) を使用して、.NET アプリケーションをビルドおよび実行している場合、この設定は異なります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-185">If you're using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="8b52e-186">つまり、アプリケーションに選択した言語とプラットフォームにより、ENTRYPOINT 行とその他の設定は別になります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-186">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="8b52e-187">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8b52e-187">Additional resources</span></span>

- <span data-ttu-id="8b52e-188">**.NET Core アプリケーションの Docker イメージのビルド** \\</span><span class="sxs-lookup"><span data-stu-id="8b52e-188">**Building Docker Images for .NET Core Applications** \\</span></span>
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](../../../core/docker/building-net-docker-images.md)

- <span data-ttu-id="8b52e-189">**Build your own image (独自のイメージのビルド)**。</span><span class="sxs-lookup"><span data-stu-id="8b52e-189">**Build your own image**.</span></span> <span data-ttu-id="8b52e-190">Docker の公式なドキュメント内にあります。\\</span><span class="sxs-lookup"><span data-stu-id="8b52e-190">In the official Docker documentation.\\</span></span>
  <https://docs.docker.com/engine/tutorials/dockerimages/>

- <span data-ttu-id="8b52e-191">**.NET コンテナー イメージを最新の状態に保つ** \\</span><span class="sxs-lookup"><span data-stu-id="8b52e-191">**Staying up-to-date with .NET Container Images** \\</span></span>
  <https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>

- <span data-ttu-id="8b52e-192">**.NET と Docker を組み合わせて使用する - DockerCon 2018 の更新** \\</span><span class="sxs-lookup"><span data-stu-id="8b52e-192">**Using .NET and Docker Together - DockerCon 2018 Update** \\</span></span>
  <https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="8b52e-193">マルチアーキテクチャ イメージ リポジトリの使用</span><span class="sxs-lookup"><span data-stu-id="8b52e-193">Using multi-arch image repositories</span></span>

<span data-ttu-id="8b52e-194">単一のリポジトリには、Linux イメージや Windows イメージなどのプラットフォーム バリアントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-194">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="8b52e-195">この機能では、Microsoft (基本イメージの作成者) などのベンダーが、複数のプラットフォーム (つまり、Linux および Windows) に対応できるリポジトリを 1 つ作成できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-195">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="8b52e-196">たとえば、Docker Hub レジストリにある [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) リポジトリでは、同じリポジトリ名を使用して Linux および Windows Nano Server をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-196">For example, the [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="8b52e-197">タグを指定する場合、次の場合のように、明示的にプラットフォームを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-197">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim` \
  <span data-ttu-id="8b52e-198">ターゲット: Linux の .NET Core 2.2 ランタイムのみ</span><span class="sxs-lookup"><span data-stu-id="8b52e-198">Targets: .NET Core 2.2 runtime-only on Linux</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1809` \
  <span data-ttu-id="8b52e-199">ターゲット: Windows Nano Server の .NET Core 2.2 ランタイムのみ</span><span class="sxs-lookup"><span data-stu-id="8b52e-199">Targets: .NET Core 2.2 runtime-only on Windows Nano Server</span></span>

<span data-ttu-id="8b52e-200">しかし、同じイメージ名を指定した場合、タグが同じでも、次の例に示すように、マルチアーキテクチャ イメージ (`aspnetcore` イメージなど) では、展開する Docker ホスト OS に応じて、Linux または Windows バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-200">But, if you specify the same image name, even with the same tag, the multi-arch images (like the `aspnetcore` image) will use the Linux or Windows version depending on the Docker host OS you're deploying, as shown in the following example:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime` \
  <span data-ttu-id="8b52e-201">マルチアーキテクチャ: Docker ホスト OS に応じて、Linux または Windows Nano Server の .NET Core 2.2 ランタイムのみ</span><span class="sxs-lookup"><span data-stu-id="8b52e-201">Multi-arch: .NET Core 2.2 runtime-only on Linux or Windows Nano Server depending on the Docker host OS</span></span>

<span data-ttu-id="8b52e-202">この場合、Windows ホストからイメージをプルした場合、Windows バリアントがプルされ、同じイメージ名が Linux ホストからプルされた場合、Linux バリアントがプルされます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-202">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="multi-stage-builds-in-dockerfile"></a><span data-ttu-id="8b52e-203">Dockerfile のマルチステージ ビルド</span><span class="sxs-lookup"><span data-stu-id="8b52e-203">Multi-stage builds in Dockerfile</span></span>

<span data-ttu-id="8b52e-204">Dockerfile はバッチ スクリプトに似ています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-204">The Dockerfile is similar to a batch script.</span></span> <span data-ttu-id="8b52e-205">コマンド ラインからコンピューターを設定する必要があった場合に行う操作と似ています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-205">Similar to what you would do if you had to set up the machine from the command line.</span></span>

<span data-ttu-id="8b52e-206">これは初期コンテキストを設定する基本イメージから始まり、ホスト OS 上にある、スタートアップ ファイル システムのようなものです。</span><span class="sxs-lookup"><span data-stu-id="8b52e-206">It starts with a base image that sets up the initial context, it's like the startup filesystem, that sits on top of the host OS.</span></span> <span data-ttu-id="8b52e-207">これは OS ではありませんが、コンテナー内の OS "のようなもの" と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-207">It's not an OS, but you can think of if like "the" OS inside the container.</span></span>

<span data-ttu-id="8b52e-208">コマンド ラインを実行するたびに、以前のものからの変更が適用された新しいレイヤーがファイル システムに作成されるため、コンパイル時に結果のファイル システムが生成されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-208">The execution of every command line creates a new layer on the filesystem with the changes from the previous one, so that, when combined, produce the resulting filesystem.</span></span>

<span data-ttu-id="8b52e-209">新しいすべてのレイヤーは以前のものの上に "配置され"、コマンドが実行されるたびに結果のイメージのサイズが増えるため、イメージにアプリケーションのビルドと発行に必要な SDK などを含める必要がある場合、そのイメージが非常に大きくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-209">Since every new layer "rests" on top of the previous one and the resulting image size increases with every command, images can get very large if they have to include, for example, the SDK needed to build and publish an application.</span></span>

<span data-ttu-id="8b52e-210">ここで、マルチステージ ビルドの (Docker 17.05 以降の) プロットに入り、その機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-210">This is where multi-stage builds get into the plot (from Docker 17.05 and higher) to do their magic.</span></span>

<span data-ttu-id="8b52e-211">核となる概念は、Dockerfile の実行プロセスを複数のステージに分けられることです。ステージは後に 1 つ以上のコマンドが続く初期イメージで、最後のステージで最終イメージのサイズが決定されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-211">The core idea is that you can separate the Dockerfile execution process in stages, where a stage is an initial image followed by one or more commands, and the last stage determines the final image size.</span></span>

<span data-ttu-id="8b52e-212">つまり、マルチステージ ビルドでは、作成作業を異なる "フェーズ" に分割し、中間ステージから関連するディレクトリのみを取得する最終イメージを組み立てることができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-212">In short, multi-stage builds allow splitting the creation in different "phases" and then assemble the final image taking only the relevant directories from the intermediate stages.</span></span> <span data-ttu-id="8b52e-213">この機能を使用する一般的な戦略は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8b52e-213">The general strategy to use this feature is:</span></span>

1. <span data-ttu-id="8b52e-214">アプリケーションをビルドし、フォルダーに発行するために必要なすべてのものを含む、基本的な SDK イメージ (大きさに関係なく) を使用します</span><span class="sxs-lookup"><span data-stu-id="8b52e-214">Use a base SDK image (doesn't matter how large), with everything needed to build and publish the application to a folder and then</span></span>

2. <span data-ttu-id="8b52e-215">その後、基本的な小さいランタイムのみのイメージを使用し、前のステージから発行フォルダーをコピーして、小さな最終イメージを生成します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-215">Use a base, small, runtime-only image and copy the publishing folder from the previous stage to produce a small final image.</span></span>

<span data-ttu-id="8b52e-216">マルチステージを理解する最善の方法はおそらく、Dockerfile を詳しく見ていくことであるため、Docker サポートをプロジェクトに追加するときに Visual Studio によって作成される初期の Dockerfile から始め、後でいくつかの最適化について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-216">Probably the best way to understand multi-stage is going through a Dockerfile in detail, line by line, so let's begin with the initial Dockerfile created by Visual Studio when adding Docker support to a project and will get into some optimizations later.</span></span>

<span data-ttu-id="8b52e-217">初期の Dockerfile は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-217">The initial Dockerfile might look something like this:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks … 
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -o /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -o /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app .
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

<span data-ttu-id="8b52e-218">行ごとの詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8b52e-218">And these are the details, line by line:</span></span>

1. <span data-ttu-id="8b52e-219">"小さな" ランタイムのみの基本イメージを使用するステージを開始します。参照用にこれを**基本**と呼びます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-219">Begin a stage with a "small" runtime-only base image, call it **base** for reference.</span></span>
2. <span data-ttu-id="8b52e-220">イメージに **/app** ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-220">Create **/app** directory in the image.</span></span>
3. <span data-ttu-id="8b52e-221">ポート **80** を公開します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-221">Expose port **80**.</span></span>
<!-- skip -->
5. <span data-ttu-id="8b52e-222">ビルド/発行用の "大きな" イメージを使用する新しいステージを開始します。参照用にこれを**ビルド**と呼びます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-222">Begin a new stage with "large" image for building/publishing, call it **build** for reference.</span></span>
6. <span data-ttu-id="8b52e-223">イメージに **/src** ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-223">Create directory **/src** in the image.</span></span>
7. <span data-ttu-id="8b52e-224">16 行目まで、参照プロジェクトの **.csproj** ファイルをコピーし、後でパッケージを復元できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8b52e-224">Up to line 16, copy referenced projects **.csproj** files, to be able to restore packages later.</span></span>
<!-- skip -->
17. <span data-ttu-id="8b52e-225">**Catalog.API** プロジェクトと参照プロジェクト用のパッケージを復元します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-225">Restore packages for the **Catalog.API** project and the referenced projects.</span></span>
18. <span data-ttu-id="8b52e-226">イメージの **/src** に対する (**.dockerignore** ファイルに含まれているファイルとディレクトリを除く) **ソリューションのすべてのディレクトリ ツリー**をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8b52e-226">Copy **all directory tree for the solution** (except the files/directories included in the **.dockerignore** file) from to the **/src** directory in the image.</span></span>
19. <span data-ttu-id="8b52e-227">現在のフォルダーを **Catalog.API** プロジェクトに変更します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-227">Change current folder to **Catalog.API** project.</span></span>
20. <span data-ttu-id="8b52e-228">プロジェクト (およびその他のプロジェクトの依存関係) をビルドし、イメージの **/app** ディレクトリに出力します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-228">Build project (and other project dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
22. <span data-ttu-id="8b52e-229">ビルドに続き、新しいステージを開始します。参照用にこれを**発行**と呼びます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-229">Begin a new stage continuing from build, call it **publish** for reference.</span></span>
23. <span data-ttu-id="8b52e-230">プロジェクト (および依存関係) を発行し、イメージの **/app** ディレクトリに出力します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-230">Publish project (and dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
25. <span data-ttu-id="8b52e-231">**基本**に続き、新しいステージを開始し、これを**最終**と呼びます</span><span class="sxs-lookup"><span data-stu-id="8b52e-231">Begin a new stage continuing from **base** and call it **final**</span></span>
26. <span data-ttu-id="8b52e-232">現在のディレクトリを **/app** に変更します</span><span class="sxs-lookup"><span data-stu-id="8b52e-232">Change current directory to **/app**</span></span>
27. <span data-ttu-id="8b52e-233">**/app** ディレクトリを、**発行**ステージから現在のディレクトリにコピーします</span><span class="sxs-lookup"><span data-stu-id="8b52e-233">Copy the **/app** directory from stage **publish** to the current directory</span></span>
28. <span data-ttu-id="8b52e-234">コンテナーの開始時に実行するコマンドを定義します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-234">Define the command to run when the container is started.</span></span>

<span data-ttu-id="8b52e-235">次は、プロセス全体のパフォーマンスを向上させるための最適化についていくつか見ていきます。eShopOnContainers の場合、Linux コンテナーの完全なソリューションをビルドするには約 22 分以上かかることになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-235">Now let's explore some optimizations to improve the whole process performance that, in the case of eShopOnContainers, means about 22 minutes or more to build the complete solution in Linux containers.</span></span>

<span data-ttu-id="8b52e-236">非常にシンプルな Docker のレイヤー キャッシュ機能を利用します。基本イメージとコマンドが、前に実行したいくつかと同じである場合は、結果のレイヤーを使用するだけで済みます。コマンドを実行する必要はないため、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-236">You'll take advantage of Docker's layer cache feature, which is quite simple: if the base image and the commands are the same as some previously executed, it can just use the resulting layer without the need to execute the commands, thus saving some time.</span></span>

<span data-ttu-id="8b52e-237">次は、**ビルド** ステージについて詳しく見ていきます。5 行目から 6 行目まではほとんど同じですが、eShopOnContainers からのすべてのサービスについては、7 行目から 17 行目までが異なります。したがって、毎回実行する必要があります。しかし、7 行目から 16 行目を次のように変更したとします。</span><span class="sxs-lookup"><span data-stu-id="8b52e-237">So, let's focus on the **build** stage, lines 5-6 are mostly the same, but lines 7-17 are different for every service from eShopOnContainers, so they have to execute every single time, however if you changed lines 7-16 to:</span></span>

```
COPY . .
```

<span data-ttu-id="8b52e-238">その場合、すべてのサービスについてまったく同じになり、ソリューション全体がコピーされ、大きなレイヤーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-238">Then it would be just the same for every service, it would copy the whole solution and would create a larger layer but:</span></span>

1) <span data-ttu-id="8b52e-239">しかし、初回時 (およびファイルが変更された場合は、再ビルド時) にのみ、コピー プロセスが実行され、他のすべてのサービスではキャッシュが使用されます</span><span class="sxs-lookup"><span data-stu-id="8b52e-239">The copy process would only be executed the first time (and when rebuilding if a file is changed) and would use the cache for all other services and</span></span>

2) <span data-ttu-id="8b52e-240">中間ステージでより大きなイメージが使用されるため、最終イメージ サイズには影響しません。</span><span class="sxs-lookup"><span data-stu-id="8b52e-240">Since the larger image occurs in an intermediate stage it, doesn't affect the final image size.</span></span>

<span data-ttu-id="8b52e-241">次の大幅な最適化は、17 行目で実行される `restore` コマンドに関係します。これも、eShopOnContainers のすべてサービスについて異なります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-241">The next significant optimization involves the `restore` command executed in line 17, which is also different for every service of eShopOnContainers.</span></span> <span data-ttu-id="8b52e-242">その行を次のように変更したとします。</span><span class="sxs-lookup"><span data-stu-id="8b52e-242">If you change that line to just:</span></span>

```console
RUN dotnet restore
```

<span data-ttu-id="8b52e-243">その場合、ソリューション全体のパッケージが復元されます。しかし、ここでも、現在の方法では 15 回ではなく、1 回だけ行われます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-243">It would restore the packages for the whole solution, but then again, it would do it just once, instead of the 15 times with the current strategy.</span></span>

<span data-ttu-id="8b52e-244">しかし、フォルダーに 1 つのプロジェクトまたはソリューション ファイルがある場合にのみ、`dotnet restore` が実行されるため、これを実現するのは少し複雑になります。これを解決するための方法を簡単に説明すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-244">However, `dotnet restore` only runs if there's a single project or solution file in the folder, so achieving this is a bit more complicated and the way to solve it, without getting into too many details, is this:</span></span>

1) <span data-ttu-id="8b52e-245">次の行を **.dockerignore** に追加します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-245">Add the following lines to **.dockerignore**:</span></span>

   - <span data-ttu-id="8b52e-246">`*.sln`。メイン フォルダー ツリーのすべてのソリューション ファイルを無視します</span><span class="sxs-lookup"><span data-stu-id="8b52e-246">`*.sln`, to ignore all solution files in the main folder tree</span></span>

   - <span data-ttu-id="8b52e-247">`!eShopOnContainers-ServicesAndWebApps.sln`。このソリューション ファイルのみを含めます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-247">`!eShopOnContainers-ServicesAndWebApps.sln`, to include only this solution file.</span></span>

2) <span data-ttu-id="8b52e-248">`dotnet restore` への `/ignoreprojectextensions:.dcproj` 引数を含めます。したがって、docker-compose プロジェクトも無視され、eShopOnContainers-ServicesAndWebApps ソリューションのパッケージのみが復元されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-248">Include the `/ignoreprojectextensions:.dcproj` argument to `dotnet restore`, so it also ignores the docker-compose project and only restores the packages for the eShopOnContainers-ServicesAndWebApps solution.</span></span>

<span data-ttu-id="8b52e-249">最終的な最適化では、20 行目が余分になります。23 行目でもアプリケーションがビルドされ、本質的には 20 行目のすぐ後に続くため、別のコマンドで時間がかかることになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-249">For the final optimization, it just happens that line 20 is redundant, as line 23 also builds the application and comes, in essence, right after line 20, so there goes another time-consuming command.</span></span>

<span data-ttu-id="8b52e-250">結果のファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-250">The resulting file is then:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a><span data-ttu-id="8b52e-251">一からの基本イメージの作成</span><span class="sxs-lookup"><span data-stu-id="8b52e-251">Creating your base image from scratch</span></span>

<span data-ttu-id="8b52e-252">独自の Docker 基本イメージを一から作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-252">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="8b52e-253">このシナリオは、Docker を初めて使用するユーザーには推奨されませんが、独自の基本イメージの特定のビットを設定したい場合にそれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-253">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="8b52e-254">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8b52e-254">Additional resources</span></span>

- <span data-ttu-id="8b52e-255">**マルチアーキテクチャの .NET Core イメージ**。\\</span><span class="sxs-lookup"><span data-stu-id="8b52e-255">**Multi-arch .NET Core images**.\\</span></span>
  <https://github.com/dotnet/announcements/issues/14>

- <span data-ttu-id="8b52e-256">**Create a base image** (基本イメージを作成する)</span><span class="sxs-lookup"><span data-stu-id="8b52e-256">**Create a base image**.</span></span> <span data-ttu-id="8b52e-257">Docker の公式なドキュメント。\\</span><span class="sxs-lookup"><span data-stu-id="8b52e-257">Official Docker documentation.\\</span></span>
  <https://docs.docker.com/develop/develop-images/baseimages/>

![3 - Dockerfile で定義されているイメージを作成する](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="8b52e-259">手順 3.</span><span class="sxs-lookup"><span data-stu-id="8b52e-259">Step 3.</span></span> <span data-ttu-id="8b52e-260">カスタマイズした Docker イメージを作成し、それにアプリケーションまたはサービスを埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-260">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="8b52e-261">アプリケーションの各サービスには、関連イメージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-261">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="8b52e-262">アプリケーションが 1 つのサービスまたは Web アプリケーションで構成されている場合、イメージは 1 つのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-262">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="8b52e-263">Docker イメージは、Visual Studio が自動的に構築することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8b52e-263">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="8b52e-264">次の手順は、エディター/CLI ワークフローにのみ必要であり、背後で何が起こっているのか説明するために示しています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-264">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="8b52e-265">開発者は、完全な機能をプッシュできるか、(GitHub などの) ソース管理システムに変更するまで、ローカルで開発およびテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-265">You, as a developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="8b52e-266">つまり、Docker イメージを作成してローカルの Docker ホスト (Windows または Linux VM) にコンテナーを展開し、それらのローカルのコンテナーに対して実行、テスト、およびデバッグをする必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-266">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="8b52e-267">Docker CLI と Dockerfile を使用して、ローカルの環境にカスタム イメージを作成するには、図 5-5 のとおり、docker build コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-267">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Docker イメージのビルドの進行状況を示す画面](./media/image8.png)

<span data-ttu-id="8b52e-269">**図 5-5**</span><span class="sxs-lookup"><span data-stu-id="8b52e-269">**Figure 5-5**.</span></span> <span data-ttu-id="8b52e-270">カスタム Docker イメージの作成</span><span class="sxs-lookup"><span data-stu-id="8b52e-270">Creating a custom Docker image</span></span>

<span data-ttu-id="8b52e-271">必要に応じて、プロジェクト フォルダーから docker build を直接実行する代わりに、`dotnet publish` を実行して必要な .NET ライブラリとバイナリを使用して、展開可能なフォルダーをまず生成してから、`docker build` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-271">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running `dotnet publish`, and then use the `docker build` command.</span></span>

<span data-ttu-id="8b52e-272">これで、`cesardl/netcore-webapi-microservice-docker:first` という名前の Docker イメージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-272">This will create a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first`.</span></span> <span data-ttu-id="8b52e-273">このとき、:first は特定のバージョンを表すタグです。</span><span class="sxs-lookup"><span data-stu-id="8b52e-273">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="8b52e-274">この手順は、構成した Docker アプリケーション用に作成する必要のある各カスタム イメージで繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-274">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="8b52e-275">アプリケーションが複数のコンテナーで構成されている場合 (つまり、マルチコンテナー アプリケーションの場合)、`docker-compose up --build` コマンドを使って、関連する docker-compose.yml ファイルで公開されているメタデータを使用して、1 つのコマンドですべての関連イメージをビルドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-275">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the `docker-compose up --build` command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="8b52e-276">図 5-6 の docker images コマンドを使用すると、ローカル リポジトリの既存のイメージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-276">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![docker images コマンドでリストされるイメージの画面表示](./media/image9.png)

<span data-ttu-id="8b52e-278">**図 5-6**</span><span class="sxs-lookup"><span data-stu-id="8b52e-278">**Figure 5-6.**</span></span> <span data-ttu-id="8b52e-279">docker images コマンドを使用した既存のイメージの表示</span><span class="sxs-lookup"><span data-stu-id="8b52e-279">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="8b52e-280">Visual Studio での Docker イメージの作成</span><span class="sxs-lookup"><span data-stu-id="8b52e-280">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="8b52e-281">Visual Studio を使用して、Docker のサポートでプロジェクトを作成する場合、イメージは明示的には作成されません。</span><span class="sxs-lookup"><span data-stu-id="8b52e-281">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="8b52e-282">代わりに、**F5** (または **Ctrl + F5**) キーを押し、Docker でコンテナー化されたアプリケーションまたはサービスを実行することによって、イメージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-282">Instead, the image is created for you when you press **F5** (or **Ctrl-F5**) to run the dockerized application or service.</span></span> <span data-ttu-id="8b52e-283">この手順は Visual Studio で自動的に実行されるので、処理内容を見ることはできませんが、内部の処理内容を知ることは重要です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-283">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![4 - (省略可能) docker-compose.yml ファイルでサービスを作成する](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="8b52e-285">手順 4.</span><span class="sxs-lookup"><span data-stu-id="8b52e-285">Step 4.</span></span> <span data-ttu-id="8b52e-286">マルチ コンテナー Docker アプリケーションを構築するときの docker-compose.yml へのサービスの定義</span><span class="sxs-lookup"><span data-stu-id="8b52e-286">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="8b52e-287">[docker-compose.yml](https://docs.docker.com/compose/compose-file/) ファイルでは、展開用のコマンドを使用して構成済みのアプリケーションとして関連サービスのセットを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-287">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span> <span data-ttu-id="8b52e-288">また、その依存関係と実行時の構成が行われます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-288">It also configures its dependency relations and run-time configuration.</span></span>

<span data-ttu-id="8b52e-289">docker-compose.yml ファイルを使用する場合、メインまたはルート ソリューション フォルダーに、次の例と類似した内容でファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-289">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3.4'

services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Port=1433;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="8b52e-290">この docker-compose.yml ファイルは、簡略化され、結合されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="8b52e-290">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="8b52e-291">これには、常に必要な (カスタム イメージ名などの) 各コンテナー用の静的な構成データと、展開環境によっては異なる場合のある、接続文字列などの構成情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-291">It contains static configuration data for each container (like the name of the custom image), which is always required, and configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="8b52e-292">後半のセクションでは、複数の docker-compose ファイルに docker-compose.yml 構成を分割し、環境と実行の種類 (デバッグまたはリリース) に応じて、値をオーバーライドする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-292">In later sections, you will learn how to split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="8b52e-293">docker-compose.yml ファイルの例では、`webmvc` サービス (Web アプリケーション)、2 つのマイクロサービス (`ordering.api` と `basket.api`)、および 1 つのデータ ソース コンテナー (コンテナーとして実行される Linux 用 SQL Server に基づく `sql.data`) というの 4 つのサービスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-293">The docker-compose.yml file example defines four services: the `webmvc` service (a web application), two microservices (`ordering.api` and `basket.api`), and one data source container, `sql.data`, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="8b52e-294">各サービスはコンテナーとして展開されるので、それぞれに Docker イメージが必要です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-294">Each service will be deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="8b52e-295">docker-compose.yml ファイルでは、どのコンテナーが使用されているかのみでなく、それらがどのように個々に構成されるかが指定されています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-295">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="8b52e-296">たとえば、.yml ファイルの `webmvc` コンテナーの定義は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-296">For instance, the `webmvc` container definition in the .yml file:</span></span>

- <span data-ttu-id="8b52e-297">ビルド済みの `eshop/web:latest` イメージを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-297">Uses a pre-built `eshop/web:latest` image.</span></span> <span data-ttu-id="8b52e-298">ただし、docker-compose の実行の一部として、docker-compose ファイルの build: セクションの追加構成を加え、イメージがビルドされるように構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-298">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="8b52e-299">2 つの環境変数 (CatalogUrl および OrderingUrl) を初期化します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-299">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="8b52e-300">コンテナー上の公開されているポート 80 を、ホスト コンピューター上の外部ポート 80 に転送します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-300">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="8b52e-301">depends_on 設定を使用して、カタログと順序付けサービスに Web アプリをリンクします。</span><span class="sxs-lookup"><span data-stu-id="8b52e-301">Links the web app to the catalog and ordering service with the depends_on setting.</span></span> <span data-ttu-id="8b52e-302">これにより、サービスは、それらのサービスが開始されるまで待機するようになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-302">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="8b52e-303">docker-compose.yml ファイルについては、マイクロサービスとマルチコンテナー アプリを実装する方法について説明する後のセクションで、再確認します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-303">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="8b52e-304">Visual Studio 2017 での docker-compose.yml の操作</span><span class="sxs-lookup"><span data-stu-id="8b52e-304">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="8b52e-305">Dockerfile をプロジェクトに追加するだけでなく、前述のとおり、Visual Studio 2017 (15.8 以降) では、ソリューションに Docker Compose のオーケストレーター サポートを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-305">Besides adding a Dockerfile to a project, as we mentioned before, Visual Studio 2017 (from 15.8 on) can add orchestrator support for Docker Compose to a solution.</span></span>

<span data-ttu-id="8b52e-306">図 5-7 に示すように、コンテナー オーケストレーターのサポートを最初に追加するときに、Visual Studio でプロジェクト用の Dockerfile が作成され、いくつかのグローバル `docker-compose*.yml` ファイルを含むソリューションに新しい (サービス セクション) プロジェクトが作成されてから、それらのファイルにプロジェクトが追加されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-306">When you add container orchestrator support, as shown in Figure 5-7, for the first time, Visual Studio creates the Dockerfile for the project and creates a new (service section) project in your solution with several global `docker-compose*.yml` files, and then adds the project to those files.</span></span> <span data-ttu-id="8b52e-307">その後、docker-compose.yml ファイルを開き、追加機能で更新することができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-307">You can then open the docker-compose.yml files and update them with additional features.</span></span>

<span data-ttu-id="8b52e-308">docker-compose.yml ファイルに含めるプロジェクトごとに、この操作フォームを繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-308">You have to repeat this operation form every project you want to include in the docker-compose.yml file.</span></span>

<span data-ttu-id="8b52e-309">この記事の執筆時点では、Visual Studio で Docker Compose および Service Fabric オーケストレーターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-309">At the time of this writing, Visual Studio supports Docker Compose and Service Fabric orchestrators.</span></span>

![オーケストレーターのサポートを ASP.NET Core プロジェクトに追加するためのコンテキスト メニュー オプション](./media/image21.png)

<span data-ttu-id="8b52e-311">**図 5-7**</span><span class="sxs-lookup"><span data-stu-id="8b52e-311">**Figure 5-7**.</span></span> <span data-ttu-id="8b52e-312">Visual Studio 2017 への ASP.NET Core プロジェクトの右クリックでの Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="8b52e-312">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="8b52e-313">Visual Studio でソリューションにオーケストレーター サポートを追加すると、図 5-8 のとおり、追加された docker-compose.yml ファイルが含まれた新しいノード (`docker-compose.dcproj` プロジェクト ファイル) もソリューション エクスプローラーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-313">After you add orchestrator support to your solution in Visual Studio, you will also see a new node (in the `docker-compose.dcproj` project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![ソリューション エクスプローラーの docker-compose ノード](./media/image11.png)

<span data-ttu-id="8b52e-315">**図 5-8**.</span><span class="sxs-lookup"><span data-stu-id="8b52e-315">**Figure 5-8**.</span></span> <span data-ttu-id="8b52e-316">Visual Studio 2017 のソリューション エクスプローラーに追加された **docker-compose** ツリー ノード</span><span class="sxs-lookup"><span data-stu-id="8b52e-316">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="8b52e-317">`docker-compose up` コマンドを使用すると、1 つの docker-compose.yml ファイルで、マルチコンテナー アプリケーションを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-317">You could deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span> <span data-ttu-id="8b52e-318">しかし、Visual Studio でそれらのグループが追加されるため、環境 (開発または運用) と実行の種類 (リリースまたはデバッグ) に応じて、値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-318">However, Visual Studio adds a group of them so you can override values depending on the environment (development or production) and execution type (release or debug).</span></span> <span data-ttu-id="8b52e-319">この機能は、後のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-319">This capability will be explained in later sections.</span></span>

![5 - コンテナーまたは作成されたアプリを実行する](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="8b52e-321">手順 5.</span><span class="sxs-lookup"><span data-stu-id="8b52e-321">Step 5.</span></span> <span data-ttu-id="8b52e-322">Docker アプリケーションのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="8b52e-322">Build and run your Docker application</span></span>

<span data-ttu-id="8b52e-323">アプリケーションにコンテナーが 1 つしかない場合、Docker ホスト (仮想マシンまたは物理サーバー) に展開して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-323">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="8b52e-324">ただし、アプリケーションに複数のサービスが含まれている場合、単一の CLI コマンド (docker-compose up) を使用するか、背後でそのコマンドを使用する Visual Studio を使用して、構成されたアプリケーションとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-324">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="8b52e-325">別のオプションを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="8b52e-325">Let's look at the different options.</span></span>

### <a name="option-a-running-a-single-container-application"></a><span data-ttu-id="8b52e-326">オプション A:単一コンテナー アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="8b52e-326">Option A: Running a single-container application</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="8b52e-327">Docker CLI の使用</span><span class="sxs-lookup"><span data-stu-id="8b52e-327">Using Docker CLI</span></span>

<span data-ttu-id="8b52e-328">図 5-9 に示すように、`docker run` コマンドを使用して Docker コンテナーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-328">You can run a Docker container using the `docker run` command, as shown in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="8b52e-329">上記のコマンドでは、実行されるたびに、指定されたイメージから新しいコンテナー インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-329">The above command will create a new container instance from the specified image, every time it's run.</span></span> <span data-ttu-id="8b52e-330">`--name` パラメーターを使用して、コンテナーに名前を付けてから、`docker start {name}` (またはコンテナー ID あるいは自動名) を使って、既存のコンテナー インスタンスを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-330">You can use the `--name` parameter to give a name to the container and then use `docker start {name}` (or use the container id or automatic name) to run an existing container instance.</span></span>

![docker run コマンドを使用して Docker コンテナーを実行する場合の画面表示](./media/image13.png)

<span data-ttu-id="8b52e-332">**図 5-9**</span><span class="sxs-lookup"><span data-stu-id="8b52e-332">**Figure 5-9**.</span></span> <span data-ttu-id="8b52e-333">docker run コマンドを使用した Docker コンテナーの実行</span><span class="sxs-lookup"><span data-stu-id="8b52e-333">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="8b52e-334">この場合、このコマンドによって、コンテナーの内部ポート 5000 がホスト コンピューターのポート 80 にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-334">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="8b52e-335">つまり、ホストはポート 80 をリッスンし、コンテナーのポート 5000 に転送することを意味します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-335">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

<span data-ttu-id="8b52e-336">表示されるハッシュはコンテナー ID であり、`--name` オプションが使用されていない場合はランダムな読み取り可能な名前も割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-336">The hash shown is the container id and it’s also assigned a random readable name if the `--name` option is not used.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="8b52e-337">Visual Studio の使用</span><span class="sxs-lookup"><span data-stu-id="8b52e-337">Using Visual Studio</span></span>

<span data-ttu-id="8b52e-338">コンテナー オーケストレーターのサポートを追加していない場合は、Visual Studio で **Ctrl + F5** キーを押して単一コンテナー アプリを実行することもできます。また、**F5** キーを使用して、コンテナー内でアプリケーションをデバッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-338">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **Ctrl-F5** and you can also use **F5** to debug the application within the container.</span></span> <span data-ttu-id="8b52e-339">コンテナーは、docker run を使用してローカルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-339">The container runs locally using docker run.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="8b52e-340">オプション B:マルチコンテナー アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="8b52e-340">Option B: Running a multi-container application</span></span>

<span data-ttu-id="8b52e-341">多くのエンタープライズ シナリオでは、Docker アプリケーションは複数のサービスで構成されています。つまり、図 5-10 のようにマルチコンテナーのアプリケーションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-341">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![いくつかの Docker コンテナーを含む VM](./media/image14.png)

<span data-ttu-id="8b52e-343">**図 5-10**</span><span class="sxs-lookup"><span data-stu-id="8b52e-343">**Figure 5-10**.</span></span> <span data-ttu-id="8b52e-344">Docker コンテナーが展開された VM</span><span class="sxs-lookup"><span data-stu-id="8b52e-344">VM with Docker containers deployed</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="8b52e-345">Docker CLI の使用</span><span class="sxs-lookup"><span data-stu-id="8b52e-345">Using Docker CLI</span></span>

<span data-ttu-id="8b52e-346">Docker CLI を使用してマルチコンテナー アプリケーションを実行するには、`docker-compose up` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-346">To run a multi-container application with the Docker CLI, you use the `docker-compose up` command.</span></span> <span data-ttu-id="8b52e-347">このコマンドでは、マルチコンテナー アプリケーションを展開するためにソリューション レベルにある **docker compose.yml** ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-347">This command uses the **docker-compose.yml** file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="8b52e-348">図 5-11 は、docker-compose.yml ファイルを含む、メイン ソリューション ディレクトリからコマンドを実行した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-348">Figure 5-11 shows the results when running the command from your main solution directory, which contains the docker-compose.yml file.</span></span>

![docker-compose up コマンドの実行時の画面表示](./media/image15.png)

<span data-ttu-id="8b52e-350">**図 5-11**</span><span class="sxs-lookup"><span data-stu-id="8b52e-350">**Figure 5-11**.</span></span> <span data-ttu-id="8b52e-351">docker-compose up コマンドの実行結果の例</span><span class="sxs-lookup"><span data-stu-id="8b52e-351">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="8b52e-352">docker-compose up コマンドを実行すると、図 5-10 に示すように、アプリケーションとその関連コンテナーが Docker ホストに展開されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-352">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as depicted in Figure 5-10.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="8b52e-353">Visual Studio の使用</span><span class="sxs-lookup"><span data-stu-id="8b52e-353">Using Visual Studio</span></span>

<span data-ttu-id="8b52e-354">Visual Studio 2017 を使用したマルチコンテナー アプリケーションの実行は非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-354">Running a multi-container application using Visual Studio 2017 can't get any simpler.</span></span> <span data-ttu-id="8b52e-355">**Ctrl + F5** キーを押して実行するか、**F5** キーを押してデバッグするだけです。その場合、通常どおり、**docker-compose** をスタートアップ プロジェクトとして設定します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-355">You just press **Ctrl-F5** to run or **F5** to debug, as usual, setting up the **docker-compose** project as the startup project.</span></span>  <span data-ttu-id="8b52e-356">必要なすべてのセットアップは Visual Studio によって処理されるため、通常どおりブレークポイントを作成し、このように、最終的に "リモート サーバー" で実行される独立したプロセスになるものをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-356">Visual Studio handles all needed setup, so you can create breakpoints as usual and debug what finally become independent processes running in "remote servers", just like that.</span></span>

<span data-ttu-id="8b52e-357">既に説明したとおり、ソリューション内のプロジェクトに Docker ソリューションのサポートを追加するたびに、そのプロジェクトは、グローバル (ソリューション レベル) docker-compose.yml ファイルに構成され、一度にソリューション全体を実行またはデバッグできるようになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-357">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="8b52e-358">Visual Studio では、Docker ソリューションのサポートが有効になっているプロジェクトごとに 1 つのコンテナーが起動され、内部のすべての手順をユーザーのために実行してくれます (dotnet publish、docker build など)。</span><span class="sxs-lookup"><span data-stu-id="8b52e-358">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="8b52e-359">面倒な作業をすべて見てみる場合は、以下のファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-359">If you want to take a peek at all the drudgery, take a look at the file:</span></span>

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

<span data-ttu-id="8b52e-360">ここで重要なのは、図 5-12 のとおり、Visual Studio 2017 には、F5 のアクション用に追加の **Docker** コマンドがあることです。</span><span class="sxs-lookup"><span data-stu-id="8b52e-360">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="8b52e-361">このオプションでは、ソリューション レベルで docker-compose.yml ファイルに定義されているすべてのコンテナーを実行して、マルチコンテナー アプリケーションを実行またはデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-361">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="8b52e-362">マルチコンテナー ソリューションをデバッグできるということは、異なるプロジェクト (コンテナー) にそれぞれブレークポイントを設定でき (いくつかブレークポイントを設定でき)、Visual Studio でデバッグする際、別のプロジェクトに定義され、別のコンテナーで実行されているブレークポイントで停止されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-362">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![docker-compose プロジェクトを実行している Visual Studio デバッグ ツール バー](./media/image16.png)

<span data-ttu-id="8b52e-364">**図 5-12**</span><span class="sxs-lookup"><span data-stu-id="8b52e-364">**Figure 5-12**.</span></span> <span data-ttu-id="8b52e-365">Visual Studio 2017 でのマルチコンテナー アプリの実行</span><span class="sxs-lookup"><span data-stu-id="8b52e-365">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="8b52e-366">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8b52e-366">Additional resources</span></span>

- <span data-ttu-id="8b52e-367">**リモート Docker ホストに ASP.NET コンテナーを配置する** \\</span><span class="sxs-lookup"><span data-stu-id="8b52e-367">**Deploy an ASP.NET container to a remote Docker host** \\</span></span>
  <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="8b52e-368">オーケストレーターを使用したテストと展開に関する注意事項</span><span class="sxs-lookup"><span data-stu-id="8b52e-368">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="8b52e-369">docker-compose up および docker run コマンド (または Visual Studio でのコンテナーの実行およびデバッグ) を使用して、開発環境でコンテナーを十分にテストできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-369">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="8b52e-370">しかし、[Kubernetes](https://kubernetes.io/) や [Service Fabric](https://azure.microsoft.com/services/service-fabric/) などのオーケストレーターをターゲットにする必要がある、運用での展開にはこの方法を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="8b52e-370">But you should not use this approach for production deployments, where you should target orchestrators like [Kubernetes](https://kubernetes.io/) or [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span></span> <span data-ttu-id="8b52e-371">Kubernetes を使用している場合は、[ポッド](https://kubernetes.io/docs/concepts/workloads/pods/pod/)を使ってコンテナーと[サービス](https://kubernetes.io/docs/concepts/services-networking/service/)を整理し、ネットワーク接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-371">If you're using Kubernetes you have to use [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) to organize containers and [services](https://kubernetes.io/docs/concepts/services-networking/service/) to network them.</span></span> <span data-ttu-id="8b52e-372">[展開](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)を使用して、ポッドの作成と変更を整理することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-372">You also use [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to organize pod creation and modification.</span></span>

![6 - アプリまたはマイクロサービスをテストする](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="8b52e-374">手順 6.</span><span class="sxs-lookup"><span data-stu-id="8b52e-374">Step 6.</span></span> <span data-ttu-id="8b52e-375">ローカル Docker ホストを使用した Docker アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="8b52e-375">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="8b52e-376">この手順は、アプリケーションで何が実行されているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-376">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="8b52e-377">単一のコンテナーやサービスとして展開された単純な .NET Core Web アプリケーションでは、図 5-13 に示すように、Docker ホストでブラウザーを開き、サイトに移動して、サービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-377">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="8b52e-378">(Dockerfile の構成で、コンテナーがホストの 80 以外のポートにマップされる場合、この URL にホスト ポストを含めます。)</span><span class="sxs-lookup"><span data-stu-id="8b52e-378">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![API エンドポイント応答のブラウザー ビュー](./media/image18.png)

<span data-ttu-id="8b52e-380">**図 5-13**</span><span class="sxs-lookup"><span data-stu-id="8b52e-380">**Figure 5-13**.</span></span> <span data-ttu-id="8b52e-381">localhost を使用したローカルでの Docker アプリケーションのテスト例</span><span class="sxs-lookup"><span data-stu-id="8b52e-381">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="8b52e-382">localhost が Docker ホスト IP をポイントしていない場合 (Docker CE を使用している場合、既定では、ポイントしている必要があります)、サービスに移動するには、コンピューターのネットワーク カードの IP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-382">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine's network card.</span></span>

<span data-ttu-id="8b52e-383">なお、ブラウザーのこの URL では、説明している特定のコンテナーの例に、ポート 80 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-383">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="8b52e-384">ただし、前の手順で説明したとおり、docker run コマンドで展開されたとおり、要求は内部でポート 5000 にリダイレクトされています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-384">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="8b52e-385">図 5-14 のとおり、ターミナルからカールを使用して、アプリケーションをテストすることも可能です。</span><span class="sxs-lookup"><span data-stu-id="8b52e-385">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="8b52e-386">Windows の Docker インストールでは、既定の Docker ホスト IP は常に、コンピューターの実際の IP アドレスに 10.0.75.1 を加えたものとなります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-386">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine's actual IP address.</span></span>

![curl での API エンドポイント応答の画面表示](./media/image19.png)

<span data-ttu-id="8b52e-388">**図 5-14**</span><span class="sxs-lookup"><span data-stu-id="8b52e-388">**Figure 5-14**.</span></span> <span data-ttu-id="8b52e-389">カールを使用したローカルでの Docker アプリケーションのテスト例</span><span class="sxs-lookup"><span data-stu-id="8b52e-389">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="8b52e-390">Visual Studio 2017 を使用したコンテナーのテストおよびデバッグ</span><span class="sxs-lookup"><span data-stu-id="8b52e-390">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="8b52e-391">Visual Studio 2017 でコンテナーを実行またはデバッグする場合、.NET アプリケーションのデバッグは、コンテナーを使用しないでデバッグするのとほぼ同じ方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-391">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="8b52e-392">Visual Studio を使用しないデバッグおよびテスト</span><span class="sxs-lookup"><span data-stu-id="8b52e-392">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="8b52e-393">エディター/CLI アプローチを使用して開発する場合、コンテナーのデバッグはより難しくなるため、トレースを生成してデバッグした方がよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="8b52e-393">If you're developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="8b52e-394">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8b52e-394">Additional resources</span></span>

- <span data-ttu-id="8b52e-395">**ローカルの Docker コンテナーでのアプリのデバッグ** \\</span><span class="sxs-lookup"><span data-stu-id="8b52e-395">**Debugging apps in a local Docker container** \\</span></span>
  [https://docs.microsoft.com/visualstudio/containers/edit-and-refresh](/visualstudio/containers/edit-and-refresh)

- <span data-ttu-id="8b52e-396">**作成者: Steve Lasker。Docker を使用した ASP.NET Core アプリのビルド、デバッグおよび展開。**</span><span class="sxs-lookup"><span data-stu-id="8b52e-396">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="8b52e-397">ビデオ。</span><span class="sxs-lookup"><span data-stu-id="8b52e-397">Video.</span></span> \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115>

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="8b52e-398">Visual Studio でのコンテナー開発の簡略ワークフロー</span><span class="sxs-lookup"><span data-stu-id="8b52e-398">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="8b52e-399">Visual Studio を使用するワークフローは、エディター/CLI アプローチを使用するワークフローよりも、実際はるかに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-399">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="8b52e-400">Dockerfile と docker-compose.yml ファイルに関係する Docker で必要な多くの手順は、図 5-15 のとおり、Visual Studio では背後で実行されるか、簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-400">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![Visual Studio による簡略化されたコンテナー開発ワークフロー:1 - アプリをコーディングする、2 - Docker サポートをプロジェクトに追加する (一度のみ)、3 - コンテナーまたは docker-compose アプリを実行する、4 - アプリまたはマイクロサービスをテストする、5 - リポジトリにプッシュして繰り返す。](./media/image20.png)

<span data-ttu-id="8b52e-402">**図 5-15**。</span><span class="sxs-lookup"><span data-stu-id="8b52e-402">**Figure 5-15**.</span></span> <span data-ttu-id="8b52e-403">Visual Studio での開発の簡略ワークフロー</span><span class="sxs-lookup"><span data-stu-id="8b52e-403">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="8b52e-404">これに加え、(プロジェクトに Docker のサポートを追加する) 手順 2 を、一度のみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-404">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="8b52e-405">つまり、ワークフローは、他の任意の開発に .NET を使用する場合の通常の開発タスクと似たものになります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-405">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="8b52e-406">背後で何が起こっているのか (イメージのビルド プロセス、使用している基本イメージ、コンテナーの展開など) を理解しておく必要があり、動作をカスタマイズするのに Dockerfile または docker-compose.yml ファイルを編集する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8b52e-406">You need to know what is going on under the covers (the image build process, what base images you're using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="8b52e-407">しかし、多くの作業は Visual Studio を使用することで大幅に簡略化され、ユーザーの生産性を向上させます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-407">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="8b52e-408">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8b52e-408">Additional resources</span></span>

- <span data-ttu-id="8b52e-409">**作成者: Steve Lasker。Visual Studio 2017 を使用した .NET Docker の開発** \\</span><span class="sxs-lookup"><span data-stu-id="8b52e-409">**Steve Lasker. .NET Docker Development with Visual Studio 2017** \\</span></span>
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="8b52e-410">Windows コンテナーを設定するための PowerShell コマンドの使用</span><span class="sxs-lookup"><span data-stu-id="8b52e-410">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="8b52e-411">[Windows コンテナー](https://docs.microsoft.com/virtualization/windowscontainers/about/index)は、既存の Windows アプリケーションを Docker イメージに変換して、Docker エコシステムの残りと同じツールで展開できます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-411">[Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/index) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="8b52e-412">Windows コンテナーを使用するには、次の例のように、Dockerfile で PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b52e-412">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="8b52e-413">この場合は、Windows Server Core 基本イメージ (FROM 設定) を使用して、PowerShell コマンド (RUN 設定) で IIS をインストールしています。</span><span class="sxs-lookup"><span data-stu-id="8b52e-413">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="8b52e-414">同様に、PowerShell コマンドを使用して、ASP.NET 4.x、.NET 4.6、またはその他の任意の Windows ソフトウェアなどの追加コンポーネントを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-414">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="8b52e-415">たとえば、Dockerfile の次のコマンドでは、ASP.NET 4.5 が設定されます。</span><span class="sxs-lookup"><span data-stu-id="8b52e-415">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="8b52e-416">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8b52e-416">Additional resources</span></span>

- <span data-ttu-id="8b52e-417">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="8b52e-417">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="8b52e-418">Windows の機能を含めるために dockerfile から実行する PowerShell コマンドの例。\\</span><span class="sxs-lookup"><span data-stu-id="8b52e-418">Example PowerShell commands to run from dockerfiles to include Windows features.\\</span></span>
  <https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile>

>[!div class="step-by-step"]
><span data-ttu-id="8b52e-419">[前へ](index.md)
>[次へ](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="8b52e-419">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
