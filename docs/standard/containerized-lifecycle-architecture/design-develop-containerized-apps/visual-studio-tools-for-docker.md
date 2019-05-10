---
title: Visual Studio Tools for Windows 上の Docker
description: Visual Studio 2017 バージョン 15.7 以降で使用可能な Docker ツールの説明を取得します。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: d361b0c471402c097dfac799eb58ef08209d4343
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664350"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a><span data-ttu-id="1e269-103">Windows 上の Visual Studio 2017 での Docker ツールの使用</span><span class="sxs-lookup"><span data-stu-id="1e269-103">Use Docker Tools in Visual Studio 2017 on Windows</span></span>

<span data-ttu-id="1e269-104">Visual Studio 2017 バージョン 15.7 以降に含まれる Docker ツールを使用する場合、開発者のワークフローは Visual Studio Code と Docker CLI を使用すると似ています (実際には、その同じ Docker CLI) に基づいてが容易に開始、プロセスを簡略化し、生産性の向上は、ビルド、実行、およびタスクを構成します。</span><span class="sxs-lookup"><span data-stu-id="1e269-104">The developer workflow when using the Docker Tools included in Visual Studio 2017 version 15.7 and later, is similar to using Visual Studio Code and Docker CLI (in fact, it's based on the same Docker CLI), but it's easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="1e269-105">実行して、通常を使用してコンテナーをデバッグ`F5`と`Ctrl+F5`Visual Studio からのキー。</span><span class="sxs-lookup"><span data-stu-id="1e269-105">It can also run and debug your containers via the usual `F5` and `Ctrl+F5` keys from Visual Studio.</span></span> <span data-ttu-id="1e269-106">そのコンテナーが同じで定義されている場合でも、ソリューション全体をデバッグできます`docker-compose.yml`ソリューション レベルでのファイル。</span><span class="sxs-lookup"><span data-stu-id="1e269-106">You can even debug a whole solution if its containers are defined in the same `docker-compose.yml` file at the solution level.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="1e269-107">ローカル環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="1e269-107">Configure your local environment</span></span>

<span data-ttu-id="1e269-108">Docker for Windows の最新バージョンでは、これまでにアプリケーションを開発 Docker、次の参照で説明したように、セットアップは簡単なためより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="1e269-108">With the latest versions of Docker for Windows, it's easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

> [!TIP]
> <span data-ttu-id="1e269-109">Docker for Windows をインストールする方法の詳細については、するには (<https://docs.docker.com/docker-for-windows/>)。</span><span class="sxs-lookup"><span data-stu-id="1e269-109">To learn more about installing Docker for Windows, go to (<https://docs.docker.com/docker-for-windows/>).</span></span>

## <a name="docker-support-in-visual-studio-2017"></a><span data-ttu-id="1e269-110">Visual Studio 2017 での docker サポート</span><span class="sxs-lookup"><span data-stu-id="1e269-110">Docker support in Visual Studio 2017</span></span>

<span data-ttu-id="1e269-111">Docker のサポートをプロジェクトに追加することの 2 つのレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="1e269-111">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="1e269-112">ASP.NET Core プロジェクトで、追加、 `Dockerfile` Docker サポートを有効にすると、プロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="1e269-112">In ASP.NET Core projects, you can just add a `Dockerfile` file to the project by enabling Docker support.</span></span> <span data-ttu-id="1e269-113">次のレベルは、追加コンテナー オーケストレーションのサポート、 `Dockerfile` (まだ存在しない) 場合は、プロジェクトに、`docker-compose.yml`ソリューション レベルでのファイル。</span><span class="sxs-lookup"><span data-stu-id="1e269-113">The next level is container orchestration support, which adds a `Dockerfile` to the project (if it doesn't already exist) and a `docker-compose.yml` file at the solution level.</span></span> <span data-ttu-id="1e269-114">Visual Studio 2017 バージョン 15.0 を 15.7 で既定で、Docker Compose を使用して、コンテナー オーケストレーションのサポートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="1e269-114">Container orchestration support, via Docker Compose, is added by default in Visual Studio 2017 versions 15.0 to 15.7.</span></span> <span data-ttu-id="1e269-115">コンテナー オーケストレーションのサポートは、15.8 またはそれ以降の Visual Studio 2017 バージョンにオプトイン機能です。</span><span class="sxs-lookup"><span data-stu-id="1e269-115">Container orchestration support is an opt-in feature in Visual Studio 2017 versions 15.8 or later.</span></span> <span data-ttu-id="1e269-116">後で、バージョン 15.8 Docker Compose と Service Fabric のサポートします。</span><span class="sxs-lookup"><span data-stu-id="1e269-116">Version 15.8 an later support Docker Compose and Service Fabric.</span></span>

<span data-ttu-id="1e269-117">**追加 > Docker サポート**と**追加 > コンテナー オーケストレーター サポート**コマンドにある ASP.NET Core プロジェクトのプロジェクト ノードの右クリック メニュー (またはコンテキスト メニュー) で**ソリューション エクスプ ローラー**ように、図 4-31。</span><span class="sxs-lookup"><span data-stu-id="1e269-117">The **Add > Docker Support** and **Add > Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for an ASP.NET Core project in **Solution Explorer**, as shown in Figure 4-31:</span></span>

![Visual Studio の Docker サポートの追加メニュー オプション](./media/add-docker-support-menu.png)

<span data-ttu-id="1e269-119">**図 4-31**。</span><span class="sxs-lookup"><span data-stu-id="1e269-119">**Figure 4-31**.</span></span> <span data-ttu-id="1e269-120">Visual Studio 2017 のプロジェクトに Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="1e269-120">Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="1e269-121">Docker サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="1e269-121">Add Docker support</span></span>

<span data-ttu-id="1e269-122">選択して、既存の ASP.NET Core プロジェクトに Docker サポートを追加することができます**追加** > **Docker サポート**で**ソリューション エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="1e269-122">You can add Docker support to an existing ASP.NET Core project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="1e269-123">選択して、プロジェクトの作成時に Docker サポートを有効することも**Docker サポートを有効にする**で、**新しい ASP.NET Core Web アプリケーション**クリックした後に表示されたダイアログ ボックス**ok**で、**新しいプロジェクト** ダイアログ ボックスで、図 4-32 を示すようにします。</span><span class="sxs-lookup"><span data-stu-id="1e269-123">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-32.</span></span>

![Visual Studio で新しい ASP.NET Core Web アプリの Docker サポートを有効にする](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="1e269-125">**図 4-32**。</span><span class="sxs-lookup"><span data-stu-id="1e269-125">**Figure 4-32**.</span></span> <span data-ttu-id="1e269-126">Visual Studio 2017 でプロジェクトの作成時に Docker サポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1e269-126">Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="1e269-127">Docker サポートを有効にすると、Visual Studio の追加、 *Dockerfile*ファイルをプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="1e269-127">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="1e269-128">図 4-33 に示すように ASP.NET プロジェクト (.NET Framework、.NET Core プロジェクトではなく) プロジェクトの作成時に Docker Compose のサポートが有効、コンテナー オーケストレーションのサポートも追加されます。</span><span class="sxs-lookup"><span data-stu-id="1e269-128">When you enable Docker Compose support during project creation for a ASP.NET project (.NET Framework, not a .NET Core project) as shown in Figure 4-33, container orchestration support is also added.</span></span>

![ASP.NET プロジェクトで Docker 構成のサポートを有効にする](media/enable-docker-compose-support.png)

<span data-ttu-id="1e269-130">**図 4-33**。</span><span class="sxs-lookup"><span data-stu-id="1e269-130">**Figure 4-33**.</span></span> <span data-ttu-id="1e269-131">Visual Studio 2017 での ASP.NET プロジェクトの Docker Compose のサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1e269-131">Enabling Docker Compose support for an ASP.NET project in Visual Studio 2017</span></span>

### <a name="add-container-orchestration-support"></a><span data-ttu-id="1e269-132">コンテナー オーケストレーションのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="1e269-132">Add container orchestration support</span></span>

<span data-ttu-id="1e269-133">マルチ コンテナー ソリューションを作成する場合は、コンテナー オーケストレーションのサポートをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="1e269-133">When you want to compose a multi-container solution, add container orchestration support to your projects.</span></span> <span data-ttu-id="1e269-134">これにより、実行およびで同じ定義している場合、コンテナー (ソリューション全体) のグループを同時にデバッグ*docker compose.yml*ファイル。</span><span class="sxs-lookup"><span data-stu-id="1e269-134">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span>

<span data-ttu-id="1e269-135">コンテナー オーケストレーションのサポートを追加するには、ソリューションまたはプロジェクトのノードを右クリックし**ソリューション エクスプ ローラー**、選択**追加 > コンテナー オーケストレーション サポート**します。</span><span class="sxs-lookup"><span data-stu-id="1e269-135">To add container orchestration support, right-click on the solution or project node in **Solution Explorer**, and choose **Add > Container Orchestration Support**.</span></span> <span data-ttu-id="1e269-136">クリックして**Docker Compose**または**Service Fabric**コンテナーを管理します。</span><span class="sxs-lookup"><span data-stu-id="1e269-136">Then choose **Docker Compose** or **Service Fabric** to manage the containers.</span></span>

<span data-ttu-id="1e269-137">プロジェクトに追加の Dockerfile を参照してくださいコンテナー オーケストレーションのサポートをプロジェクトに追加した後、 **docker compose**でソリューションに追加されたフォルダー**ソリューション エクスプ ローラー**ように、図 4-34。</span><span class="sxs-lookup"><span data-stu-id="1e269-137">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-34:</span></span>

![Visual Studio のソリューション エクスプローラーの Docker ファイル](media/docker-support-solution-explorer.png)

<span data-ttu-id="1e269-139">**図 4-34**します。</span><span class="sxs-lookup"><span data-stu-id="1e269-139">**Figure 4-34**.</span></span> <span data-ttu-id="1e269-140">Visual Studio 2017 でのソリューション エクスプ ローラーでの docker ファイル</span><span class="sxs-lookup"><span data-stu-id="1e269-140">Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="1e269-141">*docker-compose.yml* が既に存在する場合、Visual Studio により、構成コードの必要な行が単にそれに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1e269-141">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

## <a name="configure-docker-tools"></a><span data-ttu-id="1e269-142">Docker ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="1e269-142">Configure Docker tools</span></span>

<span data-ttu-id="1e269-143">メイン メニューで、次のように選択します。**ツール > オプション**、展開と**コンテナー ツール > 設定**します。</span><span class="sxs-lookup"><span data-stu-id="1e269-143">From the main menu, choose **Tools > Options**, and expand **Container Tools > Settings**.</span></span> <span data-ttu-id="1e269-144">コンテナーのツールの設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e269-144">The container tools settings appear.</span></span>

![Visual Studio Docker ツールの表示オプション。プロジェクトの読み込みに必要な Docker イメージを自動的にプル、コンテナーをバック グラウンドで自動的に起動、ソリューションを閉じるには、上のコンテナーを自動的に強制終了および SSL 証明書を信頼する側の入力を促しません。](./media/visual-studio-docker-tools-options.png)

<span data-ttu-id="1e269-146">**図 4-35**します。</span><span class="sxs-lookup"><span data-stu-id="1e269-146">**Figure 4-35**.</span></span> <span data-ttu-id="1e269-147">Docker Tools のオプション</span><span class="sxs-lookup"><span data-stu-id="1e269-147">Docker Tools Options</span></span>

<span data-ttu-id="1e269-148">次の表は、これらのオプションを設定する方法を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1e269-148">The following table might help you decide how to set these options.</span></span>

| <span data-ttu-id="1e269-149">名前</span><span class="sxs-lookup"><span data-stu-id="1e269-149">Name</span></span> | <span data-ttu-id="1e269-150">既定の設定</span><span class="sxs-lookup"><span data-stu-id="1e269-150">Default Setting</span></span> | <span data-ttu-id="1e269-151">対象</span><span class="sxs-lookup"><span data-stu-id="1e269-151">Applies To</span></span> | <span data-ttu-id="1e269-152">説明</span><span class="sxs-lookup"><span data-stu-id="1e269-152">Description</span></span> |
| -----|:---------------:|:----------:| ----------- |
| <span data-ttu-id="1e269-153">プロジェクトの読み込みで必要な Docker イメージを自動的にプルします。</span><span class="sxs-lookup"><span data-stu-id="1e269-153">Automatically pull required Docker images on project load</span></span> | <span data-ttu-id="1e269-154">オン</span><span class="sxs-lookup"><span data-stu-id="1e269-154">On</span></span> | <span data-ttu-id="1e269-155">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="1e269-155">Docker Compose</span></span> | <span data-ttu-id="1e269-156">プロジェクトを読み込むときのパフォーマンスを高める Visual Studio は、イメージが既にダウンロードしてコードを実行する準備ができたら、ダウンロード処理中にまたは、バック グラウンドで Docker プルの操作が開始されます。</span><span class="sxs-lookup"><span data-stu-id="1e269-156">For increased performance when loading projects, Visual Studio will start a Docker pull operation in the background so that when you're ready to run your code, the image is already downloaded or in the process of downloading.</span></span> <span data-ttu-id="1e269-157">プロジェクトをロードする場合だけ、コードを参照するには、これをオフにできます必要はありません、コンテナー イメージをダウンロードしないようにする場合。</span><span class="sxs-lookup"><span data-stu-id="1e269-157">If you're just loading projects and browsing code, you can turn this off to avoid downloading container images you don't need.</span></span> |
| <span data-ttu-id="1e269-158">コンテナーをバック グラウンドで自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="1e269-158">Automatically start containers in background</span></span> | <span data-ttu-id="1e269-159">オン</span><span class="sxs-lookup"><span data-stu-id="1e269-159">On</span></span> | <span data-ttu-id="1e269-160">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="1e269-160">Docker Compose</span></span> | <span data-ttu-id="1e269-161">もう一度パフォーマンスを向上させる Visual Studio によりコンテナーとボリューム マウント ビルドおよびコンテナーを実行する場合に対応。</span><span class="sxs-lookup"><span data-stu-id="1e269-161">Again for increased performance, Visual Studio creates a container with volume mounts ready for when you build and run your container.</span></span> <span data-ttu-id="1e269-162">コンテナーが作成されたときを制御するには、これをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1e269-162">If you want to control when your container is created, turn this off.</span></span> |
| <span data-ttu-id="1e269-163">自動的に強制終了のコンテナー ソリューションを閉じる</span><span class="sxs-lookup"><span data-stu-id="1e269-163">Automatically kill containers on solution close</span></span> | <span data-ttu-id="1e269-164">オン</span><span class="sxs-lookup"><span data-stu-id="1e269-164">On</span></span> | <span data-ttu-id="1e269-165">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="1e269-165">Docker Compose</span></span> | <span data-ttu-id="1e269-166">コンテナー ソリューションを閉じるか、Visual Studio の終了後も引き続き実行に、ソリューションが希望される場合は、これをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1e269-166">Turn this off if you would like containers for your solution to continue to run after closing the solution or closing Visual Studio.</span></span> |
| <span data-ttu-id="1e269-167">Localhost SSL 証明書を信頼する側は表示しません</span><span class="sxs-lookup"><span data-stu-id="1e269-167">Do not prompt for trusting localhost SSL certificate</span></span> | <span data-ttu-id="1e269-168">オフ</span><span class="sxs-lookup"><span data-stu-id="1e269-168">Off</span></span> | <span data-ttu-id="1e269-169">ASP.NET Core 2.2 プロジェクト</span><span class="sxs-lookup"><span data-stu-id="1e269-169">ASP.NET Core 2.2 projects</span></span> | <span data-ttu-id="1e269-170">Localhost SSL 証明書が信頼されていない場合は、Visual Studio は必要ない限り、このチェック ボックスをオンになって、プロジェクトを実行するたびと求められます。</span><span class="sxs-lookup"><span data-stu-id="1e269-170">If the localhost SSL certificate is not trusted, Visual Studio will prompt every time you run your project, unless this checkbox is checked.</span></span> |

> [!WARNING]
> <span data-ttu-id="1e269-171">Localhost SSL 証明書は信頼されず、プロンプトを抑制するボックスをチェックする場合は、アプリまたはサービスの実行時に HTTPS web 要求が失敗します。</span><span class="sxs-lookup"><span data-stu-id="1e269-171">If the localhost SSL certificate is not trusted, and you check the box to suppress prompting, then HTTPS web requests might fail at runtime in your app or service.</span></span> <span data-ttu-id="1e269-172">その場合は、オフにして、**を求めない** チェック ボックスは、プロジェクトを実行し、プロンプトでの信頼関係を示します。</span><span class="sxs-lookup"><span data-stu-id="1e269-172">In that case, uncheck the **Do not prompt** checkbox, run your project, and indicate trust at the prompt.</span></span>

> [!TIP]
> <span data-ttu-id="1e269-173">サービスの実装と Visual Studio tools for Docker の使用の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e269-173">For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>
>
><span data-ttu-id="1e269-174">ローカル Docker コンテナーでアプリをデバッグするには。 <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span><span class="sxs-lookup"><span data-stu-id="1e269-174">Debugging apps in a local Docker container: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span></span>
>
><span data-ttu-id="1e269-175">Visual Studio を使用してコンテナー レジストリに ASP.NET コンテナーをデプロイします。 <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span><span class="sxs-lookup"><span data-stu-id="1e269-175">Deploy an ASP.NET container to a container registry using Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1e269-176">[前へ](docker-apps-inner-loop-workflow.md)
>[次へ](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1e269-176">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>
