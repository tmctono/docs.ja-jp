---
title: Linux コンテナーとして AKS/Kubernetes クラスターにデプロイされる ASP.NET Core 2.2 アプリケーションをビルドする
description: Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル
ms.date: 02/25/2019
ms.openlocfilehash: 83d4d0a60db4bdc112bb35bfbf61c0396646ad31
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989026"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="565d8-103">Linux コンテナーとして AKS/Kubernetes オーケストレーターにデプロイされる ASP.NET Core 2.2 アプリケーションをビルドする</span><span class="sxs-lookup"><span data-stu-id="565d8-103">Build ASP.NET Core 2.2 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="565d8-104">Azure Kubernetes Services (AKS) は、Azure のマネージド Kubernetes オーケストレーション サービスであり、コンテナーのデプロイと管理を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="565d8-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="565d8-105">AKS の主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="565d8-105">AKS main features are:</span></span>

- <span data-ttu-id="565d8-106">Azure でホストされるコントロール プレーン</span><span class="sxs-lookup"><span data-stu-id="565d8-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="565d8-107">自動アップグレード</span><span class="sxs-lookup"><span data-stu-id="565d8-107">Automated upgrades</span></span>
- <span data-ttu-id="565d8-108">自己復旧</span><span class="sxs-lookup"><span data-stu-id="565d8-108">Self-healing</span></span>
- <span data-ttu-id="565d8-109">ユーザーが構成可能なスケーリング</span><span class="sxs-lookup"><span data-stu-id="565d8-109">User configurable scaling</span></span>
- <span data-ttu-id="565d8-110">開発者とクラスター オペレーターの両方のよりシンプルなユーザー エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="565d8-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="565d8-111">次の例では、Linux で実行され、Azure の AKS クラスターにデプロイされる、ASP.NET Core 2.2 アプリケーションの作成について確認しますが、開発は Visual Studio 2017 を使用して行われています。</span><span class="sxs-lookup"><span data-stu-id="565d8-111">The following examples explore the creation of an ASP.NET Core 2.2 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a><span data-ttu-id="565d8-112">Visual Studio 2017 を使用する ASP.NET Core 2.2 プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="565d8-112">Creating the ASP.NET Core 2.2 Project using Visual Studio 2017</span></span>

<span data-ttu-id="565d8-113">ASP.NET Core は、GitHub で Microsoft および .NET コミュニティによって管理される汎用開発プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="565d8-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="565d8-114">これはクロスプラットフォームであり、Windows、macOS、Linux がサポートされ、デバイス、クラウド、および埋め込み/IoT シナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="565d8-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="565d8-115">この例では、Visual Studio Web API テンプレートに基づくシンプルなプロジェクトを使用します。したがって、サンプルを作成するための追加の知識は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="565d8-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="565d8-116">ASP.NET Core 2.2 テクノロジを使用し、REST API で小さなプロジェクトを実行するための要素をすべて含む、標準テンプレートを使ってプロジェクトを作成するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="565d8-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.2 technology.</span></span>

![ASP.NET Core Web アプリケーションが選択されている、Visual Studio の新しいプロジェクトの追加ウィンドウ。](media/create-aspnet-core-application.png)

<span data-ttu-id="565d8-118">**図 4-36**.</span><span class="sxs-lookup"><span data-stu-id="565d8-118">**Figure 4-36**.</span></span> <span data-ttu-id="565d8-119">ASP.NET Core アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="565d8-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="565d8-120">Visual Studio でサンプル プロジェクトを作成するには、 **[ファイル]**  >  **[新規]**  >  **[プロジェクト]** の順に選択し、左側のウィンドウでプロジェクトの種類として **[Web]** を選び、その後に **[ASP.NET Core Web アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="565d8-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="565d8-121">Visual Studio に Web プロジェクト用のテンプレートがリストされます。</span><span class="sxs-lookup"><span data-stu-id="565d8-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="565d8-122">この例では、 **[API]** を選択して、ASP.NET Web API アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="565d8-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="565d8-123">ASP.NET Core 2.2 をフレームワークとして選択したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="565d8-123">Verify that you've selected ASP.NET Core 2.2 as the framework.</span></span> <span data-ttu-id="565d8-124">.NET Core 2.2 は最新バージョンの Visual Studio 2017 に含まれており、Visual Studio 2017 のインストール時に自動的にインストールされ、構成されます。</span><span class="sxs-lookup"><span data-stu-id="565d8-124">.NET Core 2.2 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![API オプションが選択された状態の、ASP.NET Core Web アプリケーションの種類を選択するための Visual Studio ダイアログ。](media/create-web-api-application.png)

<span data-ttu-id="565d8-126">**図 4-37**.</span><span class="sxs-lookup"><span data-stu-id="565d8-126">**Figure 4-37**.</span></span> <span data-ttu-id="565d8-127">ASP.NET Core 2.2 と Web API プロジェクトの種類の選択</span><span class="sxs-lookup"><span data-stu-id="565d8-127">Selecting ASP.NET CORE 2.2 and Web API project type</span></span>

<span data-ttu-id="565d8-128">以前のバージョンの .NET Core をお持ちの場合は、<https://dotnet.microsoft.com/download> から 2.2 のバージョンをダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="565d8-128">If you have any previous version of .NET Core, you can download and install the 2.2 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="565d8-129">プロジェクトの作成時またはその後に、Docker サポートを追加できるため、いつでもプロジェクトを Docker でコンテナー化することができます。</span><span class="sxs-lookup"><span data-stu-id="565d8-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="565d8-130">プロジェクトの作成後に Docker サポートを追加するには、ソリューション エクスプローラーでプロジェクト ノードを右クリックし、コンテキスト メニューで **[追加]**  >  **[Docker サポート]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="565d8-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![既存のプロジェクトに Docker サポートを追加するためのコンテキスト メニュー オプション:(プロジェクトを) 右クリック > [追加] > [Docker サポート]。](media/add-docker-support-to-project.png)

<span data-ttu-id="565d8-132">**図 4-38**.</span><span class="sxs-lookup"><span data-stu-id="565d8-132">**Figure 4-38**.</span></span> <span data-ttu-id="565d8-133">既存のプロジェクトへの Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="565d8-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="565d8-134">Docker サポートの追加を完了するために、Windows または Linux を選択できます。</span><span class="sxs-lookup"><span data-stu-id="565d8-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="565d8-135">この場合は、 **[Linux]** を選択します。これは、AKS で Windows コンテナーがサポートされないためです (2018 年末時点)。</span><span class="sxs-lookup"><span data-stu-id="565d8-135">In this case, select **Linux**, because AKS doesn't support Windows Containers (as of late 2018).</span></span>

![Dockerfile のターゲット OS を選択するためのオプション ダイアログ。](media/select-linux-docker-support.png)

<span data-ttu-id="565d8-137">**図 4-39**.</span><span class="sxs-lookup"><span data-stu-id="565d8-137">**Figure 4-39**.</span></span> <span data-ttu-id="565d8-138">Linux コンテナーの選択。</span><span class="sxs-lookup"><span data-stu-id="565d8-138">Selecting Linux containers.</span></span>

<span data-ttu-id="565d8-139">これらのシンプルな手順では、Linux コンテナーで ASP.NET Core 2.2 アプリケーションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="565d8-139">With these simple steps, you have your ASP.NET Core 2.2 application running on a Linux container.</span></span>

<span data-ttu-id="565d8-140">おわかりのように、Visual Studio 2017 と Docker 間の統合は完全に開発者の生産性を重視して行われています。</span><span class="sxs-lookup"><span data-stu-id="565d8-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer's productivity.</span></span>

<span data-ttu-id="565d8-141">これで、**F5** キーまたは **[再生]** ボタンを使用して、アプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="565d8-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="565d8-142">プロジェクトを実行した後、`docker images` コマンドを使用してイメージをリストすることができます。</span><span class="sxs-lookup"><span data-stu-id="565d8-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="565d8-143">Visual Studio 2017 でのプロジェクトの自動デプロイによって作成された `mssampleapplication` イメージが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="565d8-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![docker images コマンドからのコンソール出力には、以下のものを含むリストが表示されます:リポジトリ、タグ、イメージ ID、作成 (日)、およびサイズ。](media/docker-images-command.png)

<span data-ttu-id="565d8-145">**図 4-40**.</span><span class="sxs-lookup"><span data-stu-id="565d8-145">**Figure 4-40**.</span></span> <span data-ttu-id="565d8-146">Docker イメージのビュー</span><span class="sxs-lookup"><span data-stu-id="565d8-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="565d8-147">Azure Container Registry にソリューションを登録する</span><span class="sxs-lookup"><span data-stu-id="565d8-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="565d8-148">[Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) や Docker Hub などの任意の Docker レジストリにイメージをアップロードし、イメージをそのレジストリから AKS クラスターにデプロイできるようにします。</span><span class="sxs-lookup"><span data-stu-id="565d8-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="565d8-149">この場合、イメージを Azure Container Registry にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="565d8-149">In this case, we're uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="565d8-150">リリース モードでイメージを作成する</span><span class="sxs-lookup"><span data-stu-id="565d8-150">Create the image in Release mode</span></span>

<span data-ttu-id="565d8-151">ここでは、図 4-41 に示すように、 **[リリース]** に変更し、前と同じようにアプリケーションを実行して、**リリース**モード (運用環境の準備ができている) でイメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="565d8-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![リリース モードでビルドするための VS のツール バー オプション。](media/select-release-mode.png)

<span data-ttu-id="565d8-153">**図 4-41**.</span><span class="sxs-lookup"><span data-stu-id="565d8-153">**Figure 4-41**.</span></span> <span data-ttu-id="565d8-154">リリース モードの選択</span><span class="sxs-lookup"><span data-stu-id="565d8-154">Selecting Release Mode</span></span>

<span data-ttu-id="565d8-155">`docker image` コマンドを実行すると、作成された両方のイメージが表示されます。1 つは `debug` 用で、もう 1 つは `release` モード用です。</span><span class="sxs-lookup"><span data-stu-id="565d8-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="565d8-156">イメージの新しいタグを作成する</span><span class="sxs-lookup"><span data-stu-id="565d8-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="565d8-157">各コンテナー イメージは、レジストリの名前 `loginServer` でタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="565d8-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="565d8-158">このタグは、イメージ レジストリにコンテナー イメージをプッシュするときに、ルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="565d8-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="565d8-159">Azure Container Registry から情報を取得し、Azure portal から `loginServer` という名前を表示できます</span><span class="sxs-lookup"><span data-stu-id="565d8-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![右上に Azure Container Registry の名前が示されているブラウザー ビュー。](media/loginServer-name.png)

<span data-ttu-id="565d8-161">**図 4-42**.</span><span class="sxs-lookup"><span data-stu-id="565d8-161">**Figure 4-42**.</span></span> <span data-ttu-id="565d8-162">レジストリの名前のビュー</span><span class="sxs-lookup"><span data-stu-id="565d8-162">View of the name of the Registry</span></span>

<span data-ttu-id="565d8-163">または、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="565d8-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![上記のコマンドからのコンソール出力。](media/az-cli-loginServer-name.png)

<span data-ttu-id="565d8-165">**図 4-43**.</span><span class="sxs-lookup"><span data-stu-id="565d8-165">**Figure 4-43**.</span></span> <span data-ttu-id="565d8-166">PowerShell を使用してレジストリの名前を取得する</span><span class="sxs-lookup"><span data-stu-id="565d8-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="565d8-167">いずれの場合も、名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="565d8-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="565d8-168">この例では、`mssampleacr.azurecr.io` です。</span><span class="sxs-lookup"><span data-stu-id="565d8-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="565d8-169">これで、コマンドを使用し、最新のイメージ (リリース イメージ) を取得して、イメージにタグを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="565d8-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="565d8-170">`docker tag` コマンドを実行した後、`docker images` コマンドを使ってイメージをリストすると、新しいタグが付いたイメージが表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="565d8-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![docker images コマンドからのコンソール出力。](media/tagged-docker-images-list.png)

<span data-ttu-id="565d8-172">**図 4-44**.</span><span class="sxs-lookup"><span data-stu-id="565d8-172">**Figure 4-44**.</span></span> <span data-ttu-id="565d8-173">タグが付けられたイメージのビュー</span><span class="sxs-lookup"><span data-stu-id="565d8-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="565d8-174">Azure ACR にイメージをプッシュする</span><span class="sxs-lookup"><span data-stu-id="565d8-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="565d8-175">Azure Container Registry にログインします</span><span class="sxs-lookup"><span data-stu-id="565d8-175">Log in to the Azure Container Registry</span></span>

```console
az acr login --name mssampleacr
```

<span data-ttu-id="565d8-176">次のコマンドを使用して、Azure ACR にイメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="565d8-176">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="565d8-177">このコマンドでのイメージのアップロードにはしばらく時間がかかりますが、プロセス時にフィードバックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="565d8-177">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![docker push コマンドからのコンソール出力: レイヤーごとの文字ベースの進行状況が示されています。](media/uploading-image-to-acr.png)

<span data-ttu-id="565d8-179">**図 4-45**.</span><span class="sxs-lookup"><span data-stu-id="565d8-179">**Figure 4-45**.</span></span> <span data-ttu-id="565d8-180">ACR へのイメージのアップロード</span><span class="sxs-lookup"><span data-stu-id="565d8-180">Uploading the image to the ACR</span></span>

<span data-ttu-id="565d8-181">プロセスの完了時に示される結果は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="565d8-181">You can see below the result you should get when the process completes:</span></span>

![docker push コマンドからのコンソール出力。すべてのレイヤーまたはノードで完了したことが示されています。](media/uploading-docker-images-complete.png)

<span data-ttu-id="565d8-183">**図 4-46**.</span><span class="sxs-lookup"><span data-stu-id="565d8-183">**Figure 4-46**.</span></span> <span data-ttu-id="565d8-184">ノードのビュー</span><span class="sxs-lookup"><span data-stu-id="565d8-184">View of nodes</span></span>

<span data-ttu-id="565d8-185">次の手順では、AKS Kubernetes クラスターにコンテナーをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="565d8-185">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="565d8-186">そのためには、以下を含むファイル ( **.yml デプロイ ファイル**) が必要です。</span><span class="sxs-lookup"><span data-stu-id="565d8-186">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - name: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> <span data-ttu-id="565d8-187">Kubernetes を使用するデプロイの詳細については、<https://kubernetes.io/docs/reference/kubectl/cheatsheet/> を参照してください</span><span class="sxs-lookup"><span data-stu-id="565d8-187">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="565d8-188">これで、**Kubectl** を使用してデプロイする準備がほぼ整いましたが、最初にこのコマンドを使用して、AKS クラスターに対する資格情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="565d8-188">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![上記のコマンドからのコンソール出力:Merged "MSSampleK8Cluster as current context in  /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="565d8-190">**図 4-47**.</span><span class="sxs-lookup"><span data-stu-id="565d8-190">**Figure 4-47**.</span></span> <span data-ttu-id="565d8-191">資格情報の取得</span><span class="sxs-lookup"><span data-stu-id="565d8-191">getting credentials</span></span>

<span data-ttu-id="565d8-192">次に、`kubectl create` コマンドを使用して、デプロイを起動します。</span><span class="sxs-lookup"><span data-stu-id="565d8-192">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![上記のコマンドからのコンソール出力: deployment "mssamplesbook" created。](media/kubectl-create-command.png)

<span data-ttu-id="565d8-195">**図 4-48**.</span><span class="sxs-lookup"><span data-stu-id="565d8-195">**Figure 4-48**.</span></span> <span data-ttu-id="565d8-196">Kubernetes へのデプロイ</span><span class="sxs-lookup"><span data-stu-id="565d8-196">Deploy to Kubernetes</span></span>

<span data-ttu-id="565d8-197">デプロイが完了したら、次のコマンドで、一時的にアクセスできるローカル プロキシを使用して Kubernetes コンソールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="565d8-197">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="565d8-198">その後、URL `http://127.0.0.1:8001` にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="565d8-198">And accessing the url `http://127.0.0.1:8001`.</span></span>

![デプロイ、ポッド、レプリカ セット、サービスを示す、Kubernetes ダッシュボードのブラウザー ビュー。](media/kubernetes-cluster-information.png)

<span data-ttu-id="565d8-200">**図 4-49**.</span><span class="sxs-lookup"><span data-stu-id="565d8-200">**Figure 4-49**.</span></span> <span data-ttu-id="565d8-201">Kubernetes クラスターの情報を表示する</span><span class="sxs-lookup"><span data-stu-id="565d8-201">View Kubernetes cluster information</span></span>

<span data-ttu-id="565d8-202">これで、Linux コンテナーと AKS Kubernetes クラスターを使用して、Azure にアプリケーションをデプロイしました。</span><span class="sxs-lookup"><span data-stu-id="565d8-202">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="565d8-203">Azure portal から取得できる、サービスのパブリック IP を参照するアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="565d8-203">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="565d8-204">このガイドの「[**Azure Kubernetes Service (AKS) へのデプロイ**](deploy-azure-kubernetes-service.md)」セクションで、このサンプル用の AKS クラスターを作成する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="565d8-204">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="565d8-205">[前へ](set-up-windows-containers-with-powershell.md)
>[次へ](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="565d8-205">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
