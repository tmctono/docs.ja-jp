---
title: Linux コンテナーと AKS/Kubernetes クラスターにデプロイされた ASP.NET Core 2.1 アプリケーションを構築します。
description: Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/25/2019
ms.openlocfilehash: c6d778d345466b1b852d06bc01ce40ccfdebf964
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052756"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="94292-103">AKS/Kubernetes オーケストレーターに Linux コンテナーとして展開されている ASP.NET Core 2.1 アプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="94292-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="94292-104">Azure Kubernetes サービス (AKS) は、Azure の管理された Kubernetes オーケストレーション サービスをコンテナーのデプロイと管理を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="94292-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="94292-105">AKS の主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94292-105">AKS main features are:</span></span>

- <span data-ttu-id="94292-106">Azure でホストされるコントロール プレーンは、</span><span class="sxs-lookup"><span data-stu-id="94292-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="94292-107">自動アップグレード</span><span class="sxs-lookup"><span data-stu-id="94292-107">Automated upgrades</span></span>
- <span data-ttu-id="94292-108">自己復旧機能</span><span class="sxs-lookup"><span data-stu-id="94292-108">Self-healing</span></span>
- <span data-ttu-id="94292-109">ユーザー構成可能なスケーリング</span><span class="sxs-lookup"><span data-stu-id="94292-109">User configurable scaling</span></span>
- <span data-ttu-id="94292-110">開発者とクラスター オペレーターの両方に簡単なユーザー エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="94292-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="94292-111">次の例では、Linux で実行され、開発が完了、Azure では、AKS クラスターを展開する ASP.NET Core 2.1 アプリケーションの作成を探索する Visual Studio 2017 を使用します。</span><span class="sxs-lookup"><span data-stu-id="94292-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="94292-112">Visual Studio 2017 を使用して ASP.NET Core 2.1 のプロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="94292-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="94292-113">ASP.NET Core は、Microsoft と GitHub の .NET コミュニティによって管理される汎用的な開発プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="94292-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="94292-114">クロスプラット フォーム、Windows、macOS および Linux をサポートしていると、デバイス、クラウド、および埋め込み/iot のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="94292-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="94292-115">この例では、サンプルを作成する追加に関する知識は不要であるため、Visual Studio の Web API テンプレートに基づいている単純なプロジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="94292-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="94292-116">のみ、ASP.NET Core 2.1 のテクノロジを使用して、REST API を使用した小規模なプロジェクトを実行するすべての要素を含む標準のテンプレートを使用してプロジェクトを作成する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="94292-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![ASP.NET Core Web アプリケーションを選択すると、Visual Studio で新しいプロジェクト ウィンドウを追加します。](media/create-aspnet-core-application.png)

<span data-ttu-id="94292-118">**図 4 ~ 36**します。</span><span class="sxs-lookup"><span data-stu-id="94292-118">**Figure 4-36**.</span></span> <span data-ttu-id="94292-119">ASP.NET Core アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="94292-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="94292-120">Visual Studio でサンプル プロジェクトを作成するには、選択**ファイル** > **新規** > **プロジェクト**を選択、 **Web**プロジェクトの後に、左側のウィンドウで種類**ASP.NET Core Web アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="94292-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="94292-121">Visual Studio には、web プロジェクト用のテンプレートが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="94292-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="94292-122">たとえば、次のように選択します。 **API** ASP.NET Web API アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="94292-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="94292-123">ASP.NET Core 2.1 をフレームワークとして選択したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="94292-123">Verify that you've selected ASP.NET Core 2.1 as the framework.</span></span> <span data-ttu-id="94292-124">.NET core 2.1 Visual Studio 2017 の最新バージョンに含まれるとは自動的にインストールして構成する Visual Studio 2017 をインストールするときにします。</span><span class="sxs-lookup"><span data-stu-id="94292-124">.NET Core 2.1 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![API オプションを選択して、ASP.NET Core Web アプリケーションの種類を選択するための visual Studio のダイアログ。](media/create-web-api-application.png)

<span data-ttu-id="94292-126">**図 4-37**します。</span><span class="sxs-lookup"><span data-stu-id="94292-126">**Figure 4-37**.</span></span> <span data-ttu-id="94292-127">ASP.NET CORE 2.1 を選択し、Web API プロジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="94292-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="94292-128">以前のバージョンの .NET Core を使っている場合は、ダウンロードしてからバージョン 2.1 のインストール<https://www.microsoft.com/net/download/core#/sdk>します。</span><span class="sxs-lookup"><span data-stu-id="94292-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="94292-129">Docker サポートを追加するには、プロジェクトの作成時またはその後、ようにすることができます「docker 化」、プロジェクト、いつでもできます。</span><span class="sxs-lookup"><span data-stu-id="94292-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="94292-130">プロジェクトの作成後に、Docker サポートを追加するには、ソリューション エクスプ ローラーでプロジェクト ノードを右クリックして**追加** > **Docker サポート**コンテキスト メニュー。</span><span class="sxs-lookup"><span data-stu-id="94292-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![既存のプロジェクトに Docker サポートを追加するコンテキスト メニュー オプション:(プロジェクト) を右クリックして > 追加 > Docker のサポート。](media/add-docker-support-to-project.png)

<span data-ttu-id="94292-132">**図 4-38**します。</span><span class="sxs-lookup"><span data-stu-id="94292-132">**Figure 4-38**.</span></span> <span data-ttu-id="94292-133">既存のプロジェクトに Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="94292-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="94292-134">Docker のサポートを追加を完了するには、Windows または Linux を選択できます。</span><span class="sxs-lookup"><span data-stu-id="94292-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="94292-135">この場合は、選択**Linux**AKS は (2018 年末) としての Windows コンテナーをサポートしないためです。</span><span class="sxs-lookup"><span data-stu-id="94292-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Dockerfile のターゲット OS を選択するオプションのダイアログ。](media/select-linux-docker-support.png)

<span data-ttu-id="94292-137">**図 4-39**します。</span><span class="sxs-lookup"><span data-stu-id="94292-137">**Figure 4-39**.</span></span> <span data-ttu-id="94292-138">Linux コンテナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="94292-138">Selecting Linux containers.</span></span>

<span data-ttu-id="94292-139">簡単な手順では、Linux コンテナーで実行されている ASP.NET Core 2.1 アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="94292-139">With these simple steps, you have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="94292-140">ご覧のように、Visual Studio 2017 と Docker の統合は完全に達成するため、開発者の生産性です。</span><span class="sxs-lookup"><span data-stu-id="94292-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="94292-141">使用してアプリケーションを実行するようになりました、 **F5**キーまたはを使用して、**再生**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94292-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="94292-142">使用してイメージを一覧表示、プロジェクトを実行した後、`docker images`コマンド。</span><span class="sxs-lookup"><span data-stu-id="94292-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="94292-143">表示する必要があります、`mssampleapplication`イメージは、プロジェクトを Visual Studio 2017 での自動配置によって作成します。</span><span class="sxs-lookup"><span data-stu-id="94292-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Docker images コマンドをからの出力をコンソールには、一覧が表示されます。リポジトリ、タグ、イメージ ID、作成済み (日)、およびサイズ。](media/docker-images-command.png)

<span data-ttu-id="94292-145">**図 4-40**します。</span><span class="sxs-lookup"><span data-stu-id="94292-145">**Figure 4-40**.</span></span> <span data-ttu-id="94292-146">Docker イメージの表示</span><span class="sxs-lookup"><span data-stu-id="94292-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="94292-147">Azure Container registry のソリューションを登録します。</span><span class="sxs-lookup"><span data-stu-id="94292-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="94292-148">このような任意の Docker レジストリにイメージをアップロード[Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/)または Docker Hub、イメージは、そのレジストリから AKS クラスターにデプロイできるようにします。</span><span class="sxs-lookup"><span data-stu-id="94292-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="94292-149">ここでは、Azure Container Registry にイメージをアップロードしています。</span><span class="sxs-lookup"><span data-stu-id="94292-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="94292-150">リリース モードでイメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="94292-150">Create the image in Release mode</span></span>

<span data-ttu-id="94292-151">今すぐにイメージを作成します**リリース**モード (実稼働の準備) を変更することで**リリース**図 4-41、およびアプリケーションを実行する前に行ったように示すようにします。</span><span class="sxs-lookup"><span data-stu-id="94292-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![VS でオプションをリリース モードでビルドするツールバーです。](media/select-release-mode.png)

<span data-ttu-id="94292-153">**図 4-41**します。</span><span class="sxs-lookup"><span data-stu-id="94292-153">**Figure 4-41**.</span></span> <span data-ttu-id="94292-154">リリース モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="94292-154">Selecting Release Mode</span></span>

<span data-ttu-id="94292-155">実行する場合、`docker image`コマンドを作成するには、1 つの両方のイメージが表示されます`debug`およびその他の`release`モード。</span><span class="sxs-lookup"><span data-stu-id="94292-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="94292-156">イメージの新しいタグを作成します。</span><span class="sxs-lookup"><span data-stu-id="94292-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="94292-157">各コンテナー イメージをタグが付けられる必要があります、`loginServer`レジストリの名前。</span><span class="sxs-lookup"><span data-stu-id="94292-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="94292-158">このタグは、ルーティング、イメージ レジストリにコンテナー イメージをプッシュするときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="94292-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="94292-159">表示することができます、 `loginServer` Azure Container Registry からの情報を受け取り、Azure portal から名前</span><span class="sxs-lookup"><span data-stu-id="94292-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![右上の Azure コンテナー レジストリ名のブラウザー ビュー。](media/loginServer-name.png)

<span data-ttu-id="94292-161">**図 4-42**します。</span><span class="sxs-lookup"><span data-stu-id="94292-161">**Figure 4-42**.</span></span> <span data-ttu-id="94292-162">レジストリの名前のビュー</span><span class="sxs-lookup"><span data-stu-id="94292-162">View of the name of the Registry</span></span>

<span data-ttu-id="94292-163">または、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="94292-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![上記のコマンドから出力コンソール。](media/az-cli-loginServer-name.png)

<span data-ttu-id="94292-165">**図 4-43**します。</span><span class="sxs-lookup"><span data-stu-id="94292-165">**Figure 4-43**.</span></span> <span data-ttu-id="94292-166">PowerShell を使用して、レジストリの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="94292-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="94292-167">どちらの場合は、名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="94292-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="94292-168">この例では`mssampleacr.azurecr.io`します。</span><span class="sxs-lookup"><span data-stu-id="94292-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="94292-169">ようになりましたことができますタグを付けること、イメージを最新のイメージ (リリース イメージ) の場合は、コマンドを使用。</span><span class="sxs-lookup"><span data-stu-id="94292-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="94292-170">実行後、`docker tag`コマンドでのイメージを一覧表示、`docker images`コマンドを新しいタグを持つイメージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="94292-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Docker イメージのコマンドからの出力をコンソール。](media/tagged-docker-images-list.png)

<span data-ttu-id="94292-172">**図 4-44**します。</span><span class="sxs-lookup"><span data-stu-id="94292-172">**Figure 4-44**.</span></span> <span data-ttu-id="94292-173">タグが付けられたイメージの表示</span><span class="sxs-lookup"><span data-stu-id="94292-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="94292-174">Azure の ACR にイメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="94292-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="94292-175">次のコマンドを使用して、Azure の ACR にイメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="94292-175">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="94292-176">このコマンドがかかるイメージのアップロード プロセスでフィードバックが用意されています。</span><span class="sxs-lookup"><span data-stu-id="94292-176">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Docker push コマンドからの出力をコンソール: 各レイヤーの文字ベースの進行状況バーが表示されます。](media/uploading-image-to-acr.png)

<span data-ttu-id="94292-178">**図 4-45**します。</span><span class="sxs-lookup"><span data-stu-id="94292-178">**Figure 4-45**.</span></span> <span data-ttu-id="94292-179">ACR にイメージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="94292-179">Uploading the image to the ACR</span></span>

<span data-ttu-id="94292-180">後述する結果が完了すると、プロセスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94292-180">You can see below the result you should get when the process completes:</span></span>

![完了したら、すべてのレイヤーまたはノードを示す docker push コマンドから出力コンソール。](media/uploading-docker-images-complete.png)

<span data-ttu-id="94292-182">**図 4-46**します。</span><span class="sxs-lookup"><span data-stu-id="94292-182">**Figure 4-46**.</span></span> <span data-ttu-id="94292-183">ノードのビュー</span><span class="sxs-lookup"><span data-stu-id="94292-183">View of nodes</span></span>

<span data-ttu-id="94292-184">次の手順では、AKS の Kubernetes クラスターにコンテナーをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="94292-184">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="94292-185">そのためには、ファイルが必要です。 (**.yml ファイルをデプロイする**)、次を含みます。</span><span class="sxs-lookup"><span data-stu-id="94292-185">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

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
        - mane: mssample-services-app
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
> <span data-ttu-id="94292-186">Kubernetes を使用した展開の詳細については、次を参照してください。 <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="94292-186">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="94292-187">これで、使用してデプロイする準備はほとんど**Kubectl**、まず、このコマンドを使用して AKS クラスターに資格情報を取得する必要がありますが。</span><span class="sxs-lookup"><span data-stu-id="94292-187">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![上記のコマンドから出力コンソール:現在のコンテキストで/root/.kube/config としてマージ"MSSampleK8Cluster](media/getting-aks-credentials.png)

<span data-ttu-id="94292-189">**図 4-47**します。</span><span class="sxs-lookup"><span data-stu-id="94292-189">**Figure 4-47**.</span></span> <span data-ttu-id="94292-190">資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="94292-190">getting credentials</span></span>

<span data-ttu-id="94292-191">次に、使用、`kubectl create`展開を起動するコマンド。</span><span class="sxs-lookup"><span data-stu-id="94292-191">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![上記のコマンドからの出力をコンソール: 展開"mssamplesbook"を作成します。](media/kubectl-create-command.png)

<span data-ttu-id="94292-194">**図 4-48**します。</span><span class="sxs-lookup"><span data-stu-id="94292-194">**Figure 4-48**.</span></span> <span data-ttu-id="94292-195">Kubernetes へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="94292-195">Deploy to Kubernetes</span></span>

<span data-ttu-id="94292-196">デプロイが完了したら、次のコマンドで一時的にアクセスできるローカル プロキシを使用した Kubernetes コンソールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="94292-196">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="94292-197">Url にアクセスして`http://127.0.0.1:8001`します。</span><span class="sxs-lookup"><span data-stu-id="94292-197">And accessing the url `http://127.0.0.1:8001`.</span></span>

![展開、ポッド、レプリカ セット、およびサービスを表示、Kubernetes ダッシュ ボードのブラウザー ビュー。](media/kubernetes-cluster-information.png)

<span data-ttu-id="94292-199">**図 4 ~ 49**します。</span><span class="sxs-lookup"><span data-stu-id="94292-199">**Figure 4-49**.</span></span> <span data-ttu-id="94292-200">Kubernetes クラスターの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="94292-200">View Kubernetes cluster information</span></span>

<span data-ttu-id="94292-201">Linux コンテナーと AKS の Kubernetes クラスターを使用して Azure にデプロイされたアプリケーションをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94292-201">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="94292-202">Azure portal から取得できるサービスのパブリック IP を参照するアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="94292-202">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="94292-203">セクションでこのサンプルの AKS クラスターを作成する方法を確認できます[ **Deploy Azure Kubernetes Service (AKS) を**](deploy-azure-kubernetes-service.md)このガイドにします。</span><span class="sxs-lookup"><span data-stu-id="94292-203">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="94292-204">[前へ](set-up-windows-containers-with-powershell.md)
>[次へ](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="94292-204">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
