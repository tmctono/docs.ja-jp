---
title: Linux コンテナーとして AKS/Kubernetes クラスターにデプロイされる ASP.NET Core アプリケーションをビルドする
description: Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル
ms.date: 08/06/2020
ms.openlocfilehash: 4b04e5d56c73918c665ad6e2825205870aac9606
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916440"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="2fd06-103">Linux コンテナーとして AKS/Kubernetes オーケストレーターにデプロイされる ASP.NET Core アプリケーションをビルドする</span><span class="sxs-lookup"><span data-stu-id="2fd06-103">Build ASP.NET Core applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="2fd06-104">Azure Kubernetes Services (AKS) は、Azure のマネージド Kubernetes オーケストレーション サービスであり、コンテナーのデプロイと管理を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="2fd06-105">AKS の主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2fd06-105">AKS main features are:</span></span>

- <span data-ttu-id="2fd06-106">Azure でホストされるコントロール プレーン</span><span class="sxs-lookup"><span data-stu-id="2fd06-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="2fd06-107">自動アップグレード</span><span class="sxs-lookup"><span data-stu-id="2fd06-107">Automated upgrades</span></span>
- <span data-ttu-id="2fd06-108">自己復旧</span><span class="sxs-lookup"><span data-stu-id="2fd06-108">Self-healing</span></span>
- <span data-ttu-id="2fd06-109">ユーザーが構成可能なスケーリング</span><span class="sxs-lookup"><span data-stu-id="2fd06-109">User-configurable scaling</span></span>
- <span data-ttu-id="2fd06-110">開発者とクラスター オペレーターの両方のよりシンプルなユーザー エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="2fd06-110">Simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="2fd06-111">次の例では、Linux で実行され、Azure の AKS クラスターにデプロイされる、ASP.NET Core 3.1 アプリケーションの作成について確認しますが、開発は Visual Studio 2019 を使用して行われています。</span><span class="sxs-lookup"><span data-stu-id="2fd06-111">The following examples explore the creation of an ASP.NET Core 3.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2019.</span></span>

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a><span data-ttu-id="2fd06-112">Visual Studio 2019 を使用する ASP.NET Core プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="2fd06-112">Creating the ASP.NET Core Project using Visual Studio 2019</span></span>

<span data-ttu-id="2fd06-113">ASP.NET Core は、GitHub で Microsoft および .NET コミュニティによって管理される汎用開発プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="2fd06-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="2fd06-114">これはクロスプラットフォームであり、Windows、macOS、Linux がサポートされ、デバイス、クラウド、および埋め込み/IoT シナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="2fd06-115">この例では、Visual Studio テンプレートに基づくいくつかのシンプルなプロジェクトを使用します。したがって、サンプルを作成するための多くの追加の知識は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2fd06-115">This example uses a couple of simple projects based on Visual Studio templates, so you don't need much additional knowledge to create the sample.</span></span> <span data-ttu-id="2fd06-116">ASP.NET Core 3.1 テクノロジを使用し、Razor Pages で Web アプリおよび REST API で小さなプロジェクトを実行するための要素をすべて含む、標準テンプレートを使ってプロジェクトを作成するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API and a Web App with Razor pages, using ASP.NET Core 3.1 technology.</span></span>

![ASP.NET Core Web アプリケーションが選択されている、Visual Studio の新しいプロジェクトの追加ウィンドウ。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

<span data-ttu-id="2fd06-118">**図 4-35**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-118">**Figure 4-35**.</span></span> <span data-ttu-id="2fd06-119">Visual Studio 2019 での ASP.NET Core Web アプリケーションの作成。</span><span class="sxs-lookup"><span data-stu-id="2fd06-119">Creating an ASP.NET Core Web Application in Visual Studio 2019.</span></span>

<span data-ttu-id="2fd06-120">Visual Studio でサンプル プロジェクトを作成するには、 **[ファイル]**  >  **[新規]**  >  **[プロジェクト]** の順に選択し、プロジェクトの種類として **[Web]** を選んでから **[ASP.NET Core Web アプリケーション]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project type and then the **ASP.NET Core Web Application** template.</span></span> <span data-ttu-id="2fd06-121">必要に応じて、テンプレートを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-121">You can also search for the template if you need it.</span></span>

<span data-ttu-id="2fd06-122">その後、次の図に示すように、アプリケーションの名前と場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-122">Then enter the application name and location as shown in the next image.</span></span>

![プロジェクト名と場所を入力する。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

<span data-ttu-id="2fd06-124">**図 4-36**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-124">**Figure 4-36**.</span></span> <span data-ttu-id="2fd06-125">Visual Studio 2019 でプロジェクト名と場所を入力する。</span><span class="sxs-lookup"><span data-stu-id="2fd06-125">Enter the project name and location in Visual Studio 2019.</span></span>

<span data-ttu-id="2fd06-126">ASP.NET Core 3.1 をフレームワークとして選択したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-126">Verify that you've selected ASP.NET Core 3.1 as the framework.</span></span> <span data-ttu-id="2fd06-127">.NET Core 3.1 は最新リリースの Visual Studio 2019 に含まれており、Visual Studio のインストール時に自動的にインストールされ、構成されます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-127">.NET Core 3.1 is included in the latest release of Visual Studio 2019 and is automatically installed and configured for you when you install Visual Studio.</span></span>

![API オプションが選択された状態の、ASP.NET Core Web アプリケーションの種類を選択するための Visual Studio ダイアログ。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

<span data-ttu-id="2fd06-129">**図 4-37**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-129">**Figure 4-37**.</span></span> <span data-ttu-id="2fd06-130">ASP.NET Core 3.1 と Web API プロジェクトの種類の選択</span><span class="sxs-lookup"><span data-stu-id="2fd06-130">Selecting ASP.NET CORE 3.1 and Web API project type</span></span>

<span data-ttu-id="2fd06-131">現在、Docker のサポートが有効になっておらず、単にプロジェクトの作成後に実行できることが示されていることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="2fd06-131">Notice Docker support is not enabled now, just to show it can be done after project creation.</span></span>

<span data-ttu-id="2fd06-132">以前のバージョンの .NET Core をお持ちの場合は、<https://dotnet.microsoft.com/download> から 3.1 のバージョンをダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-132">If you have any previous version of .NET Core, you can download and install the 3.1 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="2fd06-133">いつでもプロジェクトを "Docker でコンテナー化" できることを示すには、ここで Docker サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-133">To show you can "Dockerize" your project at any time, you'll add Docker support now.</span></span> <span data-ttu-id="2fd06-134">したがって、ソリューション エクスプローラーでプロジェクト ノードを右クリックし、コンテキスト メニューで **[追加]**  >  **[Docker サポート]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-134">So right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![既存のプロジェクトに Docker サポートを追加するためのコンテキスト メニュー オプション:(プロジェクトを) 右クリック > [追加] > [Docker サポート]。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

<span data-ttu-id="2fd06-136">**図 4-38**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-136">**Figure 4-38**.</span></span> <span data-ttu-id="2fd06-137">既存のプロジェクトへの Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="2fd06-137">Adding Docker support to an existing project</span></span>

<span data-ttu-id="2fd06-138">Docker サポートの追加を完了するために、Windows または Linux を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-138">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="2fd06-139">この場合は、 **[Linux]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-139">In this case, select **Linux**.</span></span>

![Dockerfile のターゲット OS を選択するためのオプション ダイアログ。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

<span data-ttu-id="2fd06-141">**図 4-39**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-141">**Figure 4-39**.</span></span> <span data-ttu-id="2fd06-142">Linux コンテナーの選択。</span><span class="sxs-lookup"><span data-stu-id="2fd06-142">Selecting Linux containers.</span></span>

<span data-ttu-id="2fd06-143">これらのシンプルな手順では、Linux コンテナーで実行される ASP.NET Core 3.1 アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-143">With these simple steps, you have your ASP.NET Core 3.1 application running on a Linux container.</span></span>

<span data-ttu-id="2fd06-144">同様に、Web API エンドポイントを使用するために、非常にシンプルな **WebApp** プロジェクトを追加することもできます (図 4-40)。しかし、詳細についてはここでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="2fd06-144">In a similar way, you can also add a very simple **WebApp** project (Figure 4-40) to consume the web API endpoint, although the details are not discussed here.</span></span>

<span data-ttu-id="2fd06-145">その後、次の図 4-40 に示すように、**WebApi** プロジェクトのオーケストレーター サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-145">After that, you add orchestrator support for your **WebApi** project as shown next, in image 4-40.</span></span>

![WebApi プロジェクトへのオーケストレーター サポートの追加](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

<span data-ttu-id="2fd06-147">**図 4-40**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-147">**Figure 4-40**.</span></span> <span data-ttu-id="2fd06-148">*WebApi* プロジェクトへのオーケストレーター サポートの追加。</span><span class="sxs-lookup"><span data-stu-id="2fd06-148">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="2fd06-149">ローカル開発に適している、`Docker Compose` オプションを選ぶと、図 4-41 に示すように、Visual Studio によって、docker-compose ファイルを含む docker-compose プロジェクトが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-149">When you choose the `Docker Compose` option, which is fine for local development, Visual Studio adds the docker-compose project, with the docker-compose files as shown in image 4-41.</span></span>

![ソリューションに追加された docker-compose](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

<span data-ttu-id="2fd06-151">**図 4-41**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-151">**Figure 4-41**.</span></span> <span data-ttu-id="2fd06-152">*WebApi* プロジェクトへのオーケストレーター サポートの追加。</span><span class="sxs-lookup"><span data-stu-id="2fd06-152">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="2fd06-153">追加される初期ファイルはこのようなものです。</span><span class="sxs-lookup"><span data-stu-id="2fd06-153">The initial files added are similar to these ones:</span></span>

`docker-compose.yml`

```yml
version: "3.4"

services:
  webapi:
    image: ${DOCKER_REGISTRY-}webapi
    build:
      context: .
      dockerfile: WebApi/Dockerfile

  webapp:
    image: ${DOCKER_REGISTRY-}webapp
    build:
      context: .
      dockerfile: WebApp/Dockerfile
```

`docker-compose.override.yml`

```yml
version: "3.4"

services:
  webapi:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
  webapp:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
```

<span data-ttu-id="2fd06-154">Docker Compose でアプリを実行する場合は、`docker-compose.override.yml` に対して微調整をいくつか行うだけで済みます</span><span class="sxs-lookup"><span data-stu-id="2fd06-154">To have you app running with Docker Compose you just have to make a few tweaks to `docker-compose.override.yml`</span></span>

```yml
services:
  webapi:
    #...
    ports:
      - "51080:80"
      - "51443:443"
    #...
  webapp:
    environment:
      #...
      - WebApiBaseAddress=http://webapi
    ports:
      - "50080:80"
      - "50443:443"
    #...
```

<span data-ttu-id="2fd06-155">これで、**F5** キーで、または図 4-42 に示すように **[再生]** ボタン、あるいは **Ctrl + F5** キーを使用して、docker-compose プロジェクトを選択し、アプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-155">Now you can run your application with **F5** key, or by using the **Play** button, or the **Ctrl+F5** key, selecting the docker-compose project, as shown in image 4-42.</span></span>

![Visual Studio での docker-compose プロジェクトの実行](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

<span data-ttu-id="2fd06-157">**図 4-42**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-157">**Figure 4-42**.</span></span> <span data-ttu-id="2fd06-158">*WebApi* プロジェクトへのオーケストレーター サポートの追加。</span><span class="sxs-lookup"><span data-stu-id="2fd06-158">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="2fd06-159">説明に従って docker-compose アプリケーションを実行すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2fd06-159">When running the docker-compose application as explained, you get:</span></span>

1. <span data-ttu-id="2fd06-160">docker-compose ファイルに従って、イメージがビルドされ、コンテナーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-160">The images built and containers created as per the docker-compose file.</span></span>
2. <span data-ttu-id="2fd06-161">`docker-compose` プロジェクトの [プロパティ] ダイアログで構成されたアドレスで、ブラウザーが開きます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-161">The browser open in the address configured in the "Properties" dialog for the `docker-compose` project.</span></span>
3. <span data-ttu-id="2fd06-162">(Visual Studio 2019 バージョン 16.4 以降で) **[コンテナー]** ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-162">The **Container** window open (in Visual Studio 2019 version 16.4 and later).</span></span>
4. <span data-ttu-id="2fd06-163">次の図に示すように、ソリューション内のすべてのプロジェクトに対してデバッガーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-163">Debugger support for all projects in the solution, as shown in the following images.</span></span>

<span data-ttu-id="2fd06-164">開かれたブラウザー:</span><span class="sxs-lookup"><span data-stu-id="2fd06-164">Browser opened:</span></span>

![実行されている Web アプリを示すブラウザー ビュー](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

<span data-ttu-id="2fd06-166">**図 4-43**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-166">**Figure 4-43**.</span></span> <span data-ttu-id="2fd06-167">複数のコンテナーで実行されるアプリケーションを示すブラウザー ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2fd06-167">Browser window with an application running on multiple containers.</span></span>

<span data-ttu-id="2fd06-168">[コンテナー] ウィンドウ:</span><span class="sxs-lookup"><span data-stu-id="2fd06-168">Containers window:</span></span>

![Visual Studio の [コンテナー] ウィンドウ](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

<span data-ttu-id="2fd06-170">**図 4-44**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-170">**Figure 4-44**.</span></span> <span data-ttu-id="2fd06-171">Visual Studio の [コンテナー] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="2fd06-171">Visual Studio "Containers" window</span></span>

<span data-ttu-id="2fd06-172">**[コンテナー]** ウィンドウを使用すれば、実行中のコンテナーの表示、使用可能なイメージの参照、環境変数、ログ、およびポート マッピングの表示、ファイルシステムの検査、デバッガーのアタッチを行ったり、コンテナー環境内でターミナル ウィンドウを開いたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-172">The **Containers** window lets you view running containers, browse available images, view environment variables, logs, and port mappings, inspect the filesystem, attach a debugger, or open a terminal window inside the container environment.</span></span>

<span data-ttu-id="2fd06-173">おわかりのように、Visual Studio 2019 と Docker 間の統合は完全に開発者の生産性を重視して行われています。</span><span class="sxs-lookup"><span data-stu-id="2fd06-173">As you can see, the integration between Visual Studio 2019 and Docker is completely oriented to the developer's productivity.</span></span>

<span data-ttu-id="2fd06-174">もちろん、`docker images` コマンドを使用してイメージを一覧表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-174">Of course, you can also list the images using the `docker images` command.</span></span> <span data-ttu-id="2fd06-175">Visual Studio 2019 でのプロジェクトの自動デプロイによって作成された、タグが `dev` の `webapi` および `webapp` イメージが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="2fd06-175">You should see the `webapi` and `webapp` images with the `dev` tags created by the automatic deployment of our project with Visual Studio 2019.</span></span>

```console
docker images
```

![docker images コマンドからのコンソール出力には、以下のものを含むリストが表示されます:リポジトリ、タグ、イメージ ID、作成 (日)、およびサイズ。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

<span data-ttu-id="2fd06-177">**図 4-45**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-177">**Figure 4-45**.</span></span> <span data-ttu-id="2fd06-178">Docker イメージのビュー</span><span class="sxs-lookup"><span data-stu-id="2fd06-178">View of Docker images</span></span>

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a><span data-ttu-id="2fd06-179">Azure Container Registry (ACR) にソリューションを登録する</span><span class="sxs-lookup"><span data-stu-id="2fd06-179">Register the Solution in an Azure Container Registry (ACR)</span></span>

<span data-ttu-id="2fd06-180">[Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) にイメージをアップロードできますが、Docker Hub またはその他のレジストリを使用して、イメージをそのレジストリから AKS クラスターにデプロイすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-180">You can upload the images to the [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/), but you could also use Docker Hub or any other registry, so the images can be deployed to the AKS cluster from that registry.</span></span>

### <a name="create-an-acr-instance"></a><span data-ttu-id="2fd06-181">ACR インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="2fd06-181">Create an ACR instance</span></span>

<span data-ttu-id="2fd06-182">**az cli** から、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-182">Run the following command from the **az cli**:</span></span>

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="2fd06-183">リリース モードでイメージを作成する</span><span class="sxs-lookup"><span data-stu-id="2fd06-183">Create the image in Release mode</span></span>

<span data-ttu-id="2fd06-184">ここでは、図 4-46 に示すように、 **[リリース]** に変更し、前と同じようにアプリケーションを実行して、**リリース** モード (運用環境の準備ができている) でイメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-184">You'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-46, and running the application as you did before.</span></span>

![リリース モードでビルドするための VS のツール バー オプション。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

<span data-ttu-id="2fd06-186">**図 4-46**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-186">**Figure 4-46**.</span></span> <span data-ttu-id="2fd06-187">リリース モードの選択</span><span class="sxs-lookup"><span data-stu-id="2fd06-187">Selecting Release Mode</span></span>

<span data-ttu-id="2fd06-188">`docker images` コマンドを実行すると、作成された両方のイメージが表示されます。1 つは `debug` (**開発**) 用で、もう 1 つは `release` (**最新**) モード用です。</span><span class="sxs-lookup"><span data-stu-id="2fd06-188">If you execute the `docker images` command, you'll see both images created, one for `debug` (**dev**) and the other for `release` (**latest**) mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="2fd06-189">イメージの新しいタグを作成する</span><span class="sxs-lookup"><span data-stu-id="2fd06-189">Create a new Tag for the Image</span></span>

<span data-ttu-id="2fd06-190">各コンテナー イメージは、レジストリの名前 `loginServer` でタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fd06-190">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="2fd06-191">このタグは、イメージ レジストリにコンテナー イメージをプッシュするときに、ルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-191">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="2fd06-192">Azure Container Registry から情報を取得し、Azure portal から `loginServer` という名前を表示できます</span><span class="sxs-lookup"><span data-stu-id="2fd06-192">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![右上に Azure Container Registry の名前が示されているブラウザー ビュー。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

<span data-ttu-id="2fd06-194">**図 4-47**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-194">**Figure 4-47**.</span></span> <span data-ttu-id="2fd06-195">レジストリの名前のビュー</span><span class="sxs-lookup"><span data-stu-id="2fd06-195">View of the name of the Registry</span></span>

<span data-ttu-id="2fd06-196">または、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-196">Or by running the following command:</span></span>

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![上記のコマンドからのコンソール出力。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

<span data-ttu-id="2fd06-198">**図 4-48**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-198">**Figure 4-48**.</span></span> <span data-ttu-id="2fd06-199">**az cli** を使用してレジストリの名前を取得する</span><span class="sxs-lookup"><span data-stu-id="2fd06-199">Get the name of the registry using **az cli**</span></span>

<span data-ttu-id="2fd06-200">いずれの場合も、名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-200">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="2fd06-201">この例では、`exploredocker.azurecr.io` です。</span><span class="sxs-lookup"><span data-stu-id="2fd06-201">In our example, `exploredocker.azurecr.io`.</span></span>

<span data-ttu-id="2fd06-202">これで、コマンドを使用し、最新のイメージ (リリース イメージ) を取得して、イメージにタグを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-202">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

<span data-ttu-id="2fd06-203">`docker tag` コマンドを実行した後、`docker images` コマンドを使ってイメージをリストすると、新しいタグが付いたイメージが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="2fd06-203">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![docker images コマンドからのコンソール出力。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

<span data-ttu-id="2fd06-205">**図 4-49**.</span><span class="sxs-lookup"><span data-stu-id="2fd06-205">**Figure 4-49**.</span></span> <span data-ttu-id="2fd06-206">タグが付けられたイメージのビュー</span><span class="sxs-lookup"><span data-stu-id="2fd06-206">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="2fd06-207">Azure ACR にイメージをプッシュする</span><span class="sxs-lookup"><span data-stu-id="2fd06-207">Push the image into the Azure ACR</span></span>

<span data-ttu-id="2fd06-208">Azure Container Registry にログインします</span><span class="sxs-lookup"><span data-stu-id="2fd06-208">Log in to the Azure Container Registry</span></span>

```console
az acr login --name exploredocker
```

<span data-ttu-id="2fd06-209">次のコマンドを使用して、Azure ACR にイメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="2fd06-209">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push <login-server-name>/<image-name>:v1
```

<span data-ttu-id="2fd06-210">このコマンドでのイメージのアップロードにはしばらく時間がかかりますが、プロセス時にフィードバックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-210">This command takes a while uploading the images but gives you feedback in the process.</span></span> <span data-ttu-id="2fd06-211">次の図から、1 つのイメージからの出力が完了しており、もう 1 つは進行中であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2fd06-211">In the following image you can see the output from one image completed and another in progress.</span></span>

![docker push コマンドからのコンソール出力。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

<span data-ttu-id="2fd06-213">**図 4-50**</span><span class="sxs-lookup"><span data-stu-id="2fd06-213">**Figure 4-50**.</span></span> <span data-ttu-id="2fd06-214">push コマンドからのコンソール出力。</span><span class="sxs-lookup"><span data-stu-id="2fd06-214">Console output from the push command.</span></span>

<span data-ttu-id="2fd06-215">複数コンテナー アプリを AKS クラスターにデプロイするには、`docker-compose.yml` および `docker-compose.override.yml` ファイルから取得されたほとんどのプロパティを含む、マニフェスト `.yaml` ファイルがいくつか必要です。</span><span class="sxs-lookup"><span data-stu-id="2fd06-215">To deploy your multi-container app into your AKS cluster you need some manifest `.yaml` files that have, most of the properties taken from the `docker-compose.yml` and `docker-compose.override.yml` files.</span></span>

#### `deploy-webapi.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapi
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapi
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapi
    spec:
      containers:
        - name: webapi
          image: exploredocker.azurecr.io/webapi:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
---
apiVersion: v1
kind: Service
metadata:
  name: webapi
  labels:
    app: weather-forecast
    service: webapi
spec:
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapi
```

#### `deploy-webapp.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapp
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapp
    spec:
      containers:
        - name: webapp
          image: exploredocker.azurecr.io/webapp:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
            - name: WebApiBaseAddress
              value: http://webapi
---
apiVersion: v1
kind: Service
metadata:
  name: webapp
  labels:
    app: weather-forecast
    service: webapp
spec:
  type: LoadBalancer
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapp
```

> [!NOTE]
> <span data-ttu-id="2fd06-216">上記の `.yml` ファイルの場合、`ASPNETCORE_URLS` パラメーターが使用され、`HTTP` ポートのみが有効になり、サンプル アプリの証明書の欠落に関する問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-216">The previous `.yml` files only enable the `HTTP` ports, using the `ASPNETCORE_URLS` parameter, to avoid issues with the missing certificate in the sample app.</span></span>

> [!TIP]
> <span data-ttu-id="2fd06-217">このガイドの「[**Azure Kubernetes Service (AKS) へのデプロイ**](deploy-azure-kubernetes-service.md)」セクションで、このサンプル用の AKS クラスターを作成する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-217">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

<span data-ttu-id="2fd06-218">これで、**kubectl** を使用してデプロイする準備がほぼ整いましたが、最初にこのコマンドを使用して、AKS クラスターから資格情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fd06-218">Now you're almost ready to deploy using **kubectl**, but first you must get the credentials from the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![上記のコマンドからのコンソール出力:C:\Users\Miguel.kube\config の現在のコンテキストとしてマージされた "explore-docker-aks"](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

<span data-ttu-id="2fd06-220">**図 4-51**</span><span class="sxs-lookup"><span data-stu-id="2fd06-220">**Figure 4-51**.</span></span> <span data-ttu-id="2fd06-221">AKS から kubectl 環境への資格情報の取得。</span><span class="sxs-lookup"><span data-stu-id="2fd06-221">Getting credentials from AKS into the kubectl environment.</span></span>

<span data-ttu-id="2fd06-222">また、このコマンドを使用して、AKS クラスターで ACR からイメージをプルできるようにする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="2fd06-222">You also have to allow the AKS cluster to pull images from the ACR, using this command:</span></span>

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

<span data-ttu-id="2fd06-223">上記のコマンドの実行には数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2fd06-223">The previous command might take a couple of minutes to complete.</span></span> <span data-ttu-id="2fd06-224">その後、`kubectl apply` コマンドを使用してデプロイを起動してから、`kubectl get all` を使用してクラスター オブジェクトの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-224">Then, use the `kubectl apply` command to launch the deployments, and then `kubectl get all` get list the cluster objects.</span></span>

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![上記のコマンドからのコンソール出力: 適用されたデプロイ。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

<span data-ttu-id="2fd06-227">**図 4-52**</span><span class="sxs-lookup"><span data-stu-id="2fd06-227">**Figure 4-52**.</span></span> <span data-ttu-id="2fd06-228">Kubernetes へのデプロイ</span><span class="sxs-lookup"><span data-stu-id="2fd06-228">Deployment to Kubernetes</span></span>

<span data-ttu-id="2fd06-229">ロード バランサーによって外部 IP が取得され、`kubectl get services` で確認されるまでしばらく待機する必要があります。その後、次の図に示すように、そのアドレスでアプリケーションを使用できるはずです。</span><span class="sxs-lookup"><span data-stu-id="2fd06-229">You'll have to wait a while until the load balancer gets the external IP, checking with `kubectl get services`, and then the application should be available at that address, as shown in the next image:</span></span>

![AKS にデプロイされたアプリケーションのブラウザー ビュー](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

<span data-ttu-id="2fd06-231">**図 4-53**</span><span class="sxs-lookup"><span data-stu-id="2fd06-231">**Figure 4-53**.</span></span> <span data-ttu-id="2fd06-232">Kubernetes へのデプロイ</span><span class="sxs-lookup"><span data-stu-id="2fd06-232">Deployment to Kubernetes</span></span>

<span data-ttu-id="2fd06-233">デプロイが完了したら、ssh トンネルを使用して、ローカル プロキシで [Kubernetes Web UI](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2fd06-233">When the deployment completes, you can access the [Kubernetes Web UI](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) with a local proxy, using an ssh tunnel.</span></span>

<span data-ttu-id="2fd06-234">まず、次のコマンドを使用して ClusterRoleBinding を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fd06-234">First you must create a ClusterRoleBinding with the following command:</span></span>

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

<span data-ttu-id="2fd06-235">その後、このコマンドを実行してプロキシを開始します。</span><span class="sxs-lookup"><span data-stu-id="2fd06-235">And then this command to start the proxy:</span></span>

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

<span data-ttu-id="2fd06-236">ブラウザー ウィンドウが `http://127.0.0.1:8001` で開き、このようなビューが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="2fd06-236">A browser window should open at `http://127.0.0.1:8001` with a view similar to this one:</span></span>

![デプロイ、ポッド、レプリカ セット、サービスを示す、Kubernetes ダッシュボードのブラウザー ビュー。](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

<span data-ttu-id="2fd06-238">**図 4-54**</span><span class="sxs-lookup"><span data-stu-id="2fd06-238">**Figure 4-54**.</span></span> <span data-ttu-id="2fd06-239">Kubernetes クラスターの情報を表示する</span><span class="sxs-lookup"><span data-stu-id="2fd06-239">View Kubernetes cluster information</span></span>

<span data-ttu-id="2fd06-240">これで、Linux コンテナーで実行される ASP.NET Core アプリケーションが作成され、Azure 上の AKS クラスターにデプロイされました。</span><span class="sxs-lookup"><span data-stu-id="2fd06-240">Now you have your ASP.NET Core application, running in Linux containers, and deployed to an AKS cluster on Azure.</span></span>

> [!NOTE]
> <span data-ttu-id="2fd06-241">Kubernetes を使用するデプロイの詳細については、<https://kubernetes.io/docs/reference/kubectl/cheatsheet/> を参照してください</span><span class="sxs-lookup"><span data-stu-id="2fd06-241">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="2fd06-242">[前へ](set-up-windows-containers-with-powershell.md)
> [次へ](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="2fd06-242">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
