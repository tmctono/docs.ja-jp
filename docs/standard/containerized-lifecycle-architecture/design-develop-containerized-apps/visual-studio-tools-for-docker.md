---
title: Windows 上の Visual Studio Tools for Docker
description: Visual Studio 2017 バージョン 15.7 以降で使用できる Docker ツールについて説明します。
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 2b6fdc33f9cf850cf9e52fca4a1a9754cd412567
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644701"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a><span data-ttu-id="6ecfb-103">Windows 上の Visual Studio 2017 で Docker ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="6ecfb-103">Use Docker Tools in Visual Studio 2017 on Windows</span></span>

<span data-ttu-id="6ecfb-104">Visual Studio 2017 バージョン 15.7 以降に含まれている Docker ツールを使用する場合の開発者ワークフローは、Visual Studio Code と Docker CLI の使用と似ています (実際、同じ Docker CLI に基づいています) が、より簡単に始めることができ、プロセスが簡単であり、ビルド、実行、および構成タスクの生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-104">The developer workflow when using the Docker Tools included in Visual Studio 2017 version 15.7 and later, is similar to using Visual Studio Code and Docker CLI (in fact, it's based on the same Docker CLI), but it's easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="6ecfb-105">また、Visual Studio の通常の `F5` キーと `Ctrl+F5` キーを使用してコンテナーを実行およびデバッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-105">It can also run and debug your containers via the usual `F5` and `Ctrl+F5` keys from Visual Studio.</span></span> <span data-ttu-id="6ecfb-106">コンテナーがソリューション レベルで同じ `docker-compose.yml` ファイルに定義されている場合は、ソリューション全体をデバッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-106">You can even debug a whole solution if its containers are defined in the same `docker-compose.yml` file at the solution level.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="6ecfb-107">ローカル環境を構成する</span><span class="sxs-lookup"><span data-stu-id="6ecfb-107">Configure your local environment</span></span>

<span data-ttu-id="6ecfb-108">Docker for Windows の最新バージョンでは、次の参考ドキュメントで説明されているように、設定が簡単なので、Docker アプリケーションの開発がこれまでよりも簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-108">With the latest versions of Docker for Windows, it's easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

> [!TIP]
> <span data-ttu-id="6ecfb-109">Docker for Windows のインストールの詳細については、(<https://docs.docker.com/docker-for-windows/>) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-109">To learn more about installing Docker for Windows, go to (<https://docs.docker.com/docker-for-windows/>).</span></span>

## <a name="docker-support-in-visual-studio-2017"></a><span data-ttu-id="6ecfb-110">Visual Studio 2017 での Docker サポート</span><span class="sxs-lookup"><span data-stu-id="6ecfb-110">Docker support in Visual Studio 2017</span></span>

<span data-ttu-id="6ecfb-111">プロジェクトに追加できる Docker サポートには 2 つのレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-111">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="6ecfb-112">ASP.NET Core プロジェクトでは、Docker サポートを有効にしてプロジェクトに `Dockerfile` ファイルを追加するだけです。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-112">In ASP.NET Core projects, you can just add a `Dockerfile` file to the project by enabling Docker support.</span></span> <span data-ttu-id="6ecfb-113">次のレベルはコンテナー オーケストレーションのサポートです。(まだ存在しない場合は) `Dockerfile` をプロジェクトに追加し、ソリューション レベルで `docker-compose.yml` ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-113">The next level is container orchestration support, which adds a `Dockerfile` to the project (if it doesn't already exist) and a `docker-compose.yml` file at the solution level.</span></span> <span data-ttu-id="6ecfb-114">Docker Compose によるコンテナー オーケストレーションのサポートは、Visual Studio 2017 バージョン 15.0 から 15.7 で既定で追加されています。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-114">Container orchestration support, via Docker Compose, is added by default in Visual Studio 2017 versions 15.0 to 15.7.</span></span> <span data-ttu-id="6ecfb-115">コンテナー オーケストレーションのサポートは、Visual Studio 2017 バージョン 15.8 以降のオプトイン機能です。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-115">Container orchestration support is an opt-in feature in Visual Studio 2017 versions 15.8 or later.</span></span> <span data-ttu-id="6ecfb-116">バージョン 15.8 以降では、Docker Compose と Service Fabric をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-116">Version 15.8 an later support Docker Compose and Service Fabric.</span></span>

<span data-ttu-id="6ecfb-117">**[追加] > [Docker のサポート]** と **[追加] > [コンテナー オーケストレーター サポート]** コマンドは、**ソリューション エクスプローラー**の ASP.NET Core プロジェクトのプロジェクト ノードの右クリック メニュー (またはコンテキスト メニュー) にあります。図 4-31 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-117">The **Add > Docker Support** and **Add > Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for an ASP.NET Core project in **Solution Explorer**, as shown in Figure 4-31:</span></span>

![Visual Studio の Docker サポートの追加メニュー オプション](./media/add-docker-support-menu.png)

<span data-ttu-id="6ecfb-119">**図 4-31**。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-119">**Figure 4-31**.</span></span> <span data-ttu-id="6ecfb-120">Visual Studio 2017 プロジェクトに Docker サポートを追加する</span><span class="sxs-lookup"><span data-stu-id="6ecfb-120">Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="6ecfb-121">Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="6ecfb-121">Add Docker support</span></span>

<span data-ttu-id="6ecfb-122">既存の ASP.NET Core プロジェクトに Docker サポートを追加するには、**ソリューション エクスプローラー**で **[追加]**  >  **[Docker のサポート]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-122">You can add Docker support to an existing ASP.NET Core project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="6ecfb-123">プロジェクトの作成中に Docker サポートを有効にするには、図 4-32 に示すように、 **[新しいプロジェクト]** ダイアログ ボックスで **[OK]** をクリックすると開く **[新しい ASP.NET Core Web アプリケーション]** ダイアログ ボックスで、 **[Docker サポートを有効にする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-123">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-32.</span></span>

![Visual Studio で新しい ASP.NET Core Web アプリの Docker サポートを有効にする](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="6ecfb-125">**図 4-32**。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-125">**Figure 4-32**.</span></span> <span data-ttu-id="6ecfb-126">Visual Studio 2017 でプロジェクトの作成中に Docker サポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="6ecfb-126">Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="6ecfb-127">Docker サポートを追加または有効にすると、Visual Studio によって *Dockerfile* ファイルがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-127">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="6ecfb-128">図 4-33 に示すように、ASP.NET プロジェクト (.NET Framework .NET Core プロジェクトではありません) 用のプロジェクトの作成中に Docker Compose のサポートを有効にすると、コンテナー オーケストレーションのサポートも追加されます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-128">When you enable Docker Compose support during project creation for a ASP.NET project (.NET Framework, not a .NET Core project) as shown in Figure 4-33, container orchestration support is also added.</span></span>

![ASP.NET プロジェクトで Docker 構成のサポートを有効にする](media/enable-docker-compose-support.png)

<span data-ttu-id="6ecfb-130">**図 4-33**。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-130">**Figure 4-33**.</span></span> <span data-ttu-id="6ecfb-131">Visual Studio 2017 で ASP.NET プロジェクトに対する Docker Compose のサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="6ecfb-131">Enabling Docker Compose support for an ASP.NET project in Visual Studio 2017</span></span>

### <a name="add-container-orchestration-support"></a><span data-ttu-id="6ecfb-132">コンテナー オーケストレーションのサポートを追加する</span><span class="sxs-lookup"><span data-stu-id="6ecfb-132">Add container orchestration support</span></span>

<span data-ttu-id="6ecfb-133">複数コンテナーのソリューションを構成する場合は、コンテナー オーケストレーションのサポートをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-133">When you want to compose a multi-container solution, add container orchestration support to your projects.</span></span> <span data-ttu-id="6ecfb-134">これにより、コンテナーのグループ (ソリューション全体) が同じ *docker-compose.yml* ファイル内で定義されている場合、それらを同時に実行およびデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-134">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span>

<span data-ttu-id="6ecfb-135">コンテナー オーケストレーションのサポートを追加するには、**ソリューション エクスプローラー**でソリューションまたはプロジェクトのノードを右クリックし、 **[追加] > [Container Orchestration Support]\(コンテナー オーケストレーション サポート\)** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-135">To add container orchestration support, right-click on the solution or project node in **Solution Explorer**, and choose **Add > Container Orchestration Support**.</span></span> <span data-ttu-id="6ecfb-136">次に、 **[Docker Compose]** または **[Service Fabric]** を選択してコンテナーを管理します。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-136">Then choose **Docker Compose** or **Service Fabric** to manage the containers.</span></span>

<span data-ttu-id="6ecfb-137">プロジェクトにコンテナー オーケストレーションのサポートを追加すると、図 4-34 に示すように、プロジェクトに Dockerfile が追加され、**ソリューション エクスプローラー**内のソリューションに **docker-compose** フォルダーが追加されるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-137">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-34:</span></span>

![Visual Studio のソリューション エクスプローラーの Docker ファイル](media/docker-support-solution-explorer.png)

<span data-ttu-id="6ecfb-139">**図 4-34**.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-139">**Figure 4-34**.</span></span> <span data-ttu-id="6ecfb-140">Visual Studio 2017 のソリューション エクスプローラーの Docker ファイル</span><span class="sxs-lookup"><span data-stu-id="6ecfb-140">Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="6ecfb-141">*docker-compose.yml* が既に存在する場合、Visual Studio により、構成コードの必要な行が単にそれに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-141">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

## <a name="configure-docker-tools"></a><span data-ttu-id="6ecfb-142">Docker ツールを構成する</span><span class="sxs-lookup"><span data-stu-id="6ecfb-142">Configure Docker tools</span></span>

<span data-ttu-id="6ecfb-143">メイン メニューから **[ツール] > [オプション]** を選択し、 **[コンテナー ツール] > [設定]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-143">From the main menu, choose **Tools > Options**, and expand **Container Tools > Settings**.</span></span> <span data-ttu-id="6ecfb-144">コンテナー ツールの設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-144">The container tools settings appear.</span></span>

![次が表示されている Visual Studio Docker ツールのオプション。[必要な Docker イメージをプロジェクト読み込み時に自動的にプルする]、[コンテナーをバックグラウンドで自動的に開始する]、[ソリューションを閉じる際に、コンテナーを自動的に強制終了します]、[localhost SSL 証明書を信頼するためのメッセージを表示しない]。](./media/visual-studio-docker-tools-options.png)

<span data-ttu-id="6ecfb-146">**図 4-35**.</span><span class="sxs-lookup"><span data-stu-id="6ecfb-146">**Figure 4-35**.</span></span> <span data-ttu-id="6ecfb-147">Docker ツールのオプション</span><span class="sxs-lookup"><span data-stu-id="6ecfb-147">Docker Tools Options</span></span>

<span data-ttu-id="6ecfb-148">これらのオプションの設定方法を判断する際に、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-148">The following table might help you decide how to set these options.</span></span>

| <span data-ttu-id="6ecfb-149">name</span><span class="sxs-lookup"><span data-stu-id="6ecfb-149">Name</span></span> | <span data-ttu-id="6ecfb-150">既定の設定</span><span class="sxs-lookup"><span data-stu-id="6ecfb-150">Default Setting</span></span> | <span data-ttu-id="6ecfb-151">対象</span><span class="sxs-lookup"><span data-stu-id="6ecfb-151">Applies To</span></span> | <span data-ttu-id="6ecfb-152">説明</span><span class="sxs-lookup"><span data-stu-id="6ecfb-152">Description</span></span> |
| -----|:---------------:|:----------:| ----------- |
| <span data-ttu-id="6ecfb-153">必要な Docker イメージをプロジェクト読み込み時に自動的にプルする</span><span class="sxs-lookup"><span data-stu-id="6ecfb-153">Automatically pull required Docker images on project load</span></span> | <span data-ttu-id="6ecfb-154">オン</span><span class="sxs-lookup"><span data-stu-id="6ecfb-154">On</span></span> | <span data-ttu-id="6ecfb-155">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="6ecfb-155">Docker Compose</span></span> | <span data-ttu-id="6ecfb-156">プロジェクトを読み込むときのパフォーマンスを向上するために、Visual Studio ではバックグラウンドで Docker のプル操作が開始されます。そのため、コードを実行する準備ができたら、イメージは既にダウンロードされているかダウンロード中です。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-156">For increased performance when loading projects, Visual Studio will start a Docker pull operation in the background so that when you're ready to run your code, the image is already downloaded or in the process of downloading.</span></span> <span data-ttu-id="6ecfb-157">プロジェクトを読み込んでコードを参照するだけの場合は、これをオフにして不要なコンテナー イメージをダウンロードしないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-157">If you're just loading projects and browsing code, you can turn this off to avoid downloading container images you don't need.</span></span> |
| <span data-ttu-id="6ecfb-158">コンテナーをバックグラウンドで自動的に開始する</span><span class="sxs-lookup"><span data-stu-id="6ecfb-158">Automatically start containers in background</span></span> | <span data-ttu-id="6ecfb-159">オン</span><span class="sxs-lookup"><span data-stu-id="6ecfb-159">On</span></span> | <span data-ttu-id="6ecfb-160">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="6ecfb-160">Docker Compose</span></span> | <span data-ttu-id="6ecfb-161">また、パフォーマンスを向上するために、Visual Studio では、ユーザーがコンテナーを作成して実行するときに備えてボリュームのマウントを使用してコンテナーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-161">Again for increased performance, Visual Studio creates a container with volume mounts ready for when you build and run your container.</span></span> <span data-ttu-id="6ecfb-162">コンテナーを作成するタイミングを制御する場合は、これをオフにします。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-162">If you want to control when your container is created, turn this off.</span></span> |
| <span data-ttu-id="6ecfb-163">ソリューションを閉じる際に、コンテナーを自動的に強制終了します</span><span class="sxs-lookup"><span data-stu-id="6ecfb-163">Automatically kill containers on solution close</span></span> | <span data-ttu-id="6ecfb-164">オン</span><span class="sxs-lookup"><span data-stu-id="6ecfb-164">On</span></span> | <span data-ttu-id="6ecfb-165">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="6ecfb-165">Docker Compose</span></span> | <span data-ttu-id="6ecfb-166">ソリューションを閉じた後または Visual Studio を終了した後もソリューションのコンテナーを実行し続ける場合は、これをオフにします。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-166">Turn this off if you would like containers for your solution to continue to run after closing the solution or closing Visual Studio.</span></span> |
| <span data-ttu-id="6ecfb-167">localhost SSL 証明書を信頼するためのメッセージを表示しない</span><span class="sxs-lookup"><span data-stu-id="6ecfb-167">Do not prompt for trusting localhost SSL certificate</span></span> | <span data-ttu-id="6ecfb-168">オフ</span><span class="sxs-lookup"><span data-stu-id="6ecfb-168">Off</span></span> | <span data-ttu-id="6ecfb-169">ASP.NET Core 2.2 プロジェクト</span><span class="sxs-lookup"><span data-stu-id="6ecfb-169">ASP.NET Core 2.2 projects</span></span> | <span data-ttu-id="6ecfb-170">localhost SSL 証明書が信頼されていない場合、このチェックボックスがオンになっていない限り、プロジェクトを実行するたびに Visual Studio によって確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-170">If the localhost SSL certificate is not trusted, Visual Studio will prompt every time you run your project, unless this checkbox is checked.</span></span> |

> [!WARNING]
> <span data-ttu-id="6ecfb-171">localhost SSL 証明書が信頼されていない場合に、プロンプトが表示されないようにチェックボックスをオンにすると、HTTPS Web 要求はアプリまたはサービスの実行時に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-171">If the localhost SSL certificate is not trusted, and you check the box to suppress prompting, then HTTPS web requests might fail at runtime in your app or service.</span></span> <span data-ttu-id="6ecfb-172">その場合は、 **[メッセージを表示しない]** チェックボックスをオフにしてプロジェクトを実行し、プロンプトで信頼を示します。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-172">In that case, uncheck the **Do not prompt** checkbox, run your project, and indicate trust at the prompt.</span></span>

> [!TIP]
> <span data-ttu-id="6ecfb-173">サービスの実装と、Visual Studio Tools for Docker の使用方法の詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ecfb-173">For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>
>
><span data-ttu-id="6ecfb-174">ローカルの Docker コンテナーでのアプリのデバッグ: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span><span class="sxs-lookup"><span data-stu-id="6ecfb-174">Debugging apps in a local Docker container: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span></span>
>
><span data-ttu-id="6ecfb-175">Visual Studio を使用して ASP.NET Docker コンテナーをコンテナー レジストリにデプロイする: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span><span class="sxs-lookup"><span data-stu-id="6ecfb-175">Deploy an ASP.NET container to a container registry using Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6ecfb-176">[前へ](docker-apps-inner-loop-workflow.md)
>[次へ](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="6ecfb-176">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>
