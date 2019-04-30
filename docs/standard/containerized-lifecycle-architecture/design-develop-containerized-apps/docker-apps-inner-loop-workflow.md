---
title: Docker アプリの内部ループ開発ワークフロー
description: Docker アプリケーションの開発の「内部ループ」ワークフローをについて説明します。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 36fcf5769376375854c2a2631e26e8b136df0de6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050572"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="78f3c-103">Docker アプリの内部ループ開発ワークフロー</span><span class="sxs-lookup"><span data-stu-id="78f3c-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="78f3c-104">サイクル全体の DevOps のまたがりメモリ割り当て、外側のループのワークフローをトリガーする前に、各開発者のコンピューターで、アプリ自体のコーディングや、好みの言語またはプラットフォームを使用してローカルでテストして (図 4-21) すべてが開始されます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="78f3c-105">どのケースでも、必要があります、重要なポイントに共通言語、フレームワーク、またはプラットフォームを選んでもします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="78f3c-106">この特定のワークフローで常に開発してがローカルで Docker コンテナーをテストします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![手順 1 - コード/実行/デバッグ](./media/image18.png)

<span data-ttu-id="78f3c-108">**図 4-21**</span><span class="sxs-lookup"><span data-stu-id="78f3c-108">**Figure 4-21**.</span></span> <span data-ttu-id="78f3c-109">内部ループ開発コンテキスト</span><span class="sxs-lookup"><span data-stu-id="78f3c-109">Inner-loop development context</span></span>

<span data-ttu-id="78f3c-110">コンテナーまたは Docker イメージのインスタンスは、これらのコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-110">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="78f3c-111">(たとえば、Linux ディストリビューションまたは Windows)、オペレーティング システムの選択</span><span class="sxs-lookup"><span data-stu-id="78f3c-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="78f3c-112">(たとえば、アプリ バイナリ) の開発者によって追加されたファイル</span><span class="sxs-lookup"><span data-stu-id="78f3c-112">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="78f3c-113">構成 (たとえば、環境の設定との依存関係)</span><span class="sxs-lookup"><span data-stu-id="78f3c-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="78f3c-114">Docker で実行するどのようなプロセスの手順</span><span class="sxs-lookup"><span data-stu-id="78f3c-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="78f3c-115">(次のセクションで説明されている) プロセスとして Docker を使用する内部ループ開発ワークフローを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="78f3c-116">のみ、1 回行う必要があるため、環境を設定するには、最初の手順が含まれていないことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="78f3c-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="78f3c-117">Visual Studio Code と Docker CLI を使用して、Docker コンテナー内の 1 つのアプリの構築</span><span class="sxs-lookup"><span data-stu-id="78f3c-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="78f3c-118">アプリは、独自のサービスとその他のライブラリ (依存関係) から構成されます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="78f3c-119">図 4-22 は、通常は各手順の詳細な説明の後に、Docker アプリを構築するときに実行するために必要な基本手順を示します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![ワークフローの概要:手順 1 - コードでは、手順 2 - 手順 3 - の Dockerfile を記述 Dockerfile、手順 4 で定義されているイメージを作成する - 手順 5 - コンテナーの実行、docker-compose ファイルでサービスを定義または構成アプリ、手順 6 - テスト アプリ、手順 7 - が外側のループ (CI/CD パイプライン) を開始または続行 de にプッシュveloping します。](./media/image19.png)

<span data-ttu-id="78f3c-121">**図 4-22**</span><span class="sxs-lookup"><span data-stu-id="78f3c-121">**Figure 4-22**.</span></span> <span data-ttu-id="78f3c-122">Docker CLI を使用してコンテナー化された Docker アプリケーションのライフ サイクルの高度なワークフロー</span><span class="sxs-lookup"><span data-stu-id="78f3c-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="78f3c-123">手順 1: Visual Studio Code でコーディングを開始し、アプリやサービスの初期ベースラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="78f3c-124">アプリケーションを開発する方法は、Docker を使用しないことを行う方法に似ています。</span><span class="sxs-lookup"><span data-stu-id="78f3c-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="78f3c-125">違いは、開発中に、しているデプロイをテスト、アプリケーションまたは (Windows や Linux VM) など、ローカル環境で配置された Docker コンテナー内で実行されているサービスです。</span><span class="sxs-lookup"><span data-stu-id="78f3c-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="78f3c-126">**ローカル環境の設定**</span><span class="sxs-lookup"><span data-stu-id="78f3c-126">**Setting up your local environment**</span></span>

<span data-ttu-id="78f3c-127">Mac および Windows 用 Docker の最新バージョンでは、これまでに、Docker アプリケーションの開発よりも簡単ですし、セットアップは簡単です。</span><span class="sxs-lookup"><span data-stu-id="78f3c-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!情報]
>
> <span data-ttu-id="78f3c-129">Docker for Windows の設定手順については、<https://docs.docker.com/docker-for-windows/>します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-129">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="78f3c-130">Docker for Mac の設定手順については、<https://docs.docker.com/docker-for-mac/>します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-130">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="78f3c-131">さらに、実際に Docker CLI を使用しているときにアプリケーションを開発することができるように、コード エディターが必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f3c-131">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="78f3c-132">Microsoft は、Visual Studio Code では、軽量なコード エディターは、Mac、Windows、および Linux でサポートされ、IntelliSense を提供しますです[多くの言語サポート](https://code.visualstudio.com/docs/languages/overview)(JavaScript、.NET、Go、Java、Ruby、Python、およびほとんど最新の言語の)[デバッグ](https://code.visualstudio.com/Docs/editor/debugging)、 [Git との統合](https://code.visualstudio.com/Docs/editor/versioncontrol)と[拡張機能のサポート](https://code.visualstudio.com/docs/extensions/overview)します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-132">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="78f3c-133">このエディターは、Mac および Linux の開発者に最適です。</span><span class="sxs-lookup"><span data-stu-id="78f3c-133">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="78f3c-134">Windows でもに完全な Visual Studio アプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-134">In Windows, you also can use the full Visual Studio application.</span></span>

> [!情報]
>
> <span data-ttu-id="78f3c-136">Visual Studio のコードを Windows、Mac、または Linux をインストールする方法の詳細についてを参照してください<https://code.visualstudio.com/docs/setup/setup-overview/>します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-136">For instructions on installing Visual Studio Code for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="78f3c-137">Docker for Mac の設定手順については、<https://docs.docker.com/docker-for-mac/>します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-137">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="78f3c-138">Docker CLI を使用して、コード エディターを使用してコードを記述できますが、Docker 拡張機能で Visual Studio Code を使用して簡単に作成者`Dockerfile`と`docker-compose.yml`ワークスペース内のファイル。</span><span class="sxs-lookup"><span data-stu-id="78f3c-138">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="78f3c-139">下にある Docker CLI を使用して Docker コマンドを実行する Visual Studio コード IDE から、タスクおよびスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-139">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="78f3c-140">VS Code 用 Docker 拡張機能は、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-140">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="78f3c-141">自動`Dockerfile`と`docker-compose.yml`ファイルの生成</span><span class="sxs-lookup"><span data-stu-id="78f3c-141">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="78f3c-142">構文の強調表示し、マウス ポインターのヒントの`docker-compose.yml`と`Dockerfile`ファイル</span><span class="sxs-lookup"><span data-stu-id="78f3c-142">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="78f3c-143">IntelliSense (入力候補)`Dockerfile`と`docker-compose.yml`ファイル</span><span class="sxs-lookup"><span data-stu-id="78f3c-143">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="78f3c-144">Lint 処理 (エラーと警告) の`Dockerfile`ファイル</span><span class="sxs-lookup"><span data-stu-id="78f3c-144">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="78f3c-145">最も一般的な Docker コマンドをコマンド パレット (F1) の統合</span><span class="sxs-lookup"><span data-stu-id="78f3c-145">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="78f3c-146">イメージとコンテナーを管理するためのエクスプ ローラーの統合</span><span class="sxs-lookup"><span data-stu-id="78f3c-146">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="78f3c-147">DockerHub と Azure コンテナー レジストリからイメージを Azure App Service へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-147">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="78f3c-148">Docker 拡張機能のインストールに Ctrl + Shift + P キーを押して`ext install`、Marketplace 拡張機能の一覧を表示する拡張機能のインストール コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-148">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="78f3c-149">次に、入力**docker**結果をフィルター処理し、図 4-23 で示すように、Docker サポートの拡張機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-149">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![VS Code 用 Docker 拡張機能のビュー。](./media/image20.png)

<span data-ttu-id="78f3c-151">**図 4-23**. </span><span class="sxs-lookup"><span data-stu-id="78f3c-151">**Figure 4-23**.</span></span> <span data-ttu-id="78f3c-152">Visual Studio Code での Docker 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="78f3c-152">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="78f3c-153">手順 2: 既存のイメージ (プレーンな OS または .NET Core、Node.js、Ruby などの開発環境) に関連する DockerFile を作成します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-153">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="78f3c-154">必要があります、`DockerFile`カスタム イメージを構築およびデプロイするコンテナーごと。</span><span class="sxs-lookup"><span data-stu-id="78f3c-154">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="78f3c-155">1 つのカスタム サービスのアプリが構成されている場合は、1 つ必要があります`DockerFile`します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-155">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="78f3c-156">場合、アプリが (マイクロ サービス アーキテクチャ) のように複数のサービスで構成される必要がありますいずれかが`Dockerfile`サービスあたり。</span><span class="sxs-lookup"><span data-stu-id="78f3c-156">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="78f3c-157">`DockerFile`よくアプリまたはサービスのルート フォルダーに配置され、Docker を設定して、そのアプリやサービスを実行する方法を認識できるように、必要なコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="78f3c-157">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="78f3c-158">作成することができます、`DockerFile`コードと共にプロジェクトに追加し、(node.js、.NET Core など)、または、環境に新しい場合は、次のヒントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78f3c-158">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
>
> <span data-ttu-id="78f3c-159">使用しているときに、Docker 拡張機能を使用することができます、`Dockerfile`と`docker-compose.yml`ファイルは、Docker コンテナーに関連します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-159">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="78f3c-160">最終的には、この種のこのツールは、せずにファイルを作成する可能性がありますが、学習曲線を加速する適切な開始点は、Docker 拡張機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-160">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="78f3c-161">図 4-24 に、docker の方法を確認できます-compose ファイルは、VS Code 用 Docker 拡張機能を使用して追加されます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-161">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![VS Code 用 Docker 拡張機能のコンソール ビュー。](./media/image24.png)

<span data-ttu-id="78f3c-163">**図 4-24**</span><span class="sxs-lookup"><span data-stu-id="78f3c-163">**Figure 4-24**.</span></span> <span data-ttu-id="78f3c-164">使用して追加された docker ファイル、**ワークスペース コマンドに追加の Docker ファイル**</span><span class="sxs-lookup"><span data-stu-id="78f3c-164">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="78f3c-165">使用する基本の Docker イメージを指定する DockerFile を追加する場合 (などを使用して`FROM mcr.microsoft.com/dotnet/core/aspnet`)。</span><span class="sxs-lookup"><span data-stu-id="78f3c-165">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="78f3c-166">通常は、公式のリポジトリでから取得した基本イメージ上にカスタム イメージを構築します、 [Docker Hub レジストリ](https://hub.docker.com/)(など、 [.NET Core のイメージ](https://hub.docker.com/_/microsoft-dotnet-core/)または[for Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="78f3c-166">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="78f3c-167">***既存の公式 Docker イメージを使用して、***</span><span class="sxs-lookup"><span data-stu-id="78f3c-167">***Use an existing official Docker image***</span></span>

<span data-ttu-id="78f3c-168">バージョン番号を持つ言語のスタックの公式のリポジトリを使用してにより、同じ言語機能が (開発、テスト、および運用環境を含む) すべてのコンピューターで使用できます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-168">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="78f3c-169">.NET Core コンテナー用のサンプル DockerFile を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-169">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.1
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="78f3c-170">この場合、イメージが、行に従って公式の ASP.NET Core Docker イメージ (Linux および Windows 用マルチ アーキテクチャ) の version 2.1 に基づきます。`FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-170">In this case, the image is based on version 2.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`.</span></span> <span data-ttu-id="78f3c-171">(詳細については、このトピックでは、次を参照してください。、 [ASP.NET Core Docker イメージ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)ページと[.NET Core Docker イメージ](https://hub.docker.com/_/microsoft-dotnet-core/)ページ)。</span><span class="sxs-lookup"><span data-stu-id="78f3c-171">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="78f3c-172">DockerFile では、(ポート 80) などの実行時に使用する TCP ポートをリッスンするように Docker を指示することもできます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-172">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="78f3c-173">使用している言語とフレームワークによっては、Dockerfile に別の構成設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-173">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="78f3c-174">たとえば、`ENTRYPOINT`線`["dotnet", "MySingleContainerWebApp.dll"]`.NET Core アプリケーションを実行する Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-174">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="78f3c-175">SDK と .NET Core CLI を使用しているかどうか (`dotnet CLI`) をビルドする .NET アプリケーションを実行し、この設定が異なる場合がします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-175">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="78f3c-176">ここで重要な点は、ENTRYPOINT 行とその他の設定が、アプリケーション用に選択した言語とプラットフォームに依存するです。</span><span class="sxs-lookup"><span data-stu-id="78f3c-176">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!情報]
>
> <span data-ttu-id="78f3c-178">.NET Core アプリケーション用の Docker イメージの構築に関する詳細についてを参照してください<https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-178">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="78f3c-179">詳細については、独自のイメージを構築するには<https://docs.docker.com/engine/tutorials/dockerimages/>します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-179">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="78f3c-180">**マルチ アーキテクチャ イメージ リポジトリを使用します。**</span><span class="sxs-lookup"><span data-stu-id="78f3c-180">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="78f3c-181">リポジトリ内の 1 つのイメージ名には、Linux イメージと Windows イメージなどのプラットフォーム バリアントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-181">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="78f3c-182">この機能は、複数のプラットフォーム (Linux および Windows) をカバーする 1 つのリポジトリを作成する Microsoft (基本イメージの作成者) のようなベンダーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-182">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="78f3c-183">たとえば、 [dotnet/コア/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Docker Hub レジストリで利用可能なリポジトリは、同じイメージ名を使用して Linux および Windows Nano Server のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-183">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="78f3c-184">プル、 [dotnet/コア/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Linux バリアントがプル Linux ホストから同じイメージ名を取得する一方、Windows ホストからのイメージのプルを Windows バリアント。</span><span class="sxs-lookup"><span data-stu-id="78f3c-184">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="78f3c-185">***最初から基本イメージを作成します。***</span><span class="sxs-lookup"><span data-stu-id="78f3c-185">***Create your base image from scratch***</span></span>

<span data-ttu-id="78f3c-186">これで説明したように、最初から、独自の Docker 基本イメージを作成することができます[記事](https://docs.docker.com/engine/userguide/eng-image/baseimages/)Docker から。</span><span class="sxs-lookup"><span data-stu-id="78f3c-186">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="78f3c-187">このシナリオは、docker、始めようとしているが、基本イメージの特定のビットを設定する場合は、行うことができます、最適ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78f3c-187">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="78f3c-188">手順 3: これで、サービスを埋め込み、カスタム Docker イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-188">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="78f3c-189">サービスごとにカスタム アプリを構成するには、関連するイメージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f3c-189">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="78f3c-190">1 つのサービスまたは web アプリのアプリが構成されている場合は、1 つのイメージを必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f3c-190">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
>
> <span data-ttu-id="78f3c-191">「外側のループ DevOps ワークフロー」を考慮に入れてと、プッシュするたびに、ソース コードを Git リポジトリ (継続的インテグレーション) に、イメージはグローバル環境で作成できるようにから、自動化されたビルド プロセスによって、イメージを作成、ソース コードです。</span><span class="sxs-lookup"><span data-stu-id="78f3c-191">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="78f3c-192">その外側のループのルートに、検討する前に、Docker アプリケーションが実際に正しく動作するソース管理システム (Git など) が正しく動作しないコードをプッシュしないようにすることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f3c-192">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="78f3c-193">したがって、各開発者をローカルでテストし、完全な機能をプッシュするか、ソース管理システムに変更するまでの開発を続ける全体の内側のループ処理を行う最初が必要です。</span><span class="sxs-lookup"><span data-stu-id="78f3c-193">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="78f3c-194">図 4-25 に示すよう、ローカル環境と DockerFile を使用して、イメージを作成する docker ビルド コマンドを使用することができます (を実行することも`docker-compose up --build`アプリケーションがいくつかのコンテナー/サービスで構成されます)。</span><span class="sxs-lookup"><span data-stu-id="78f3c-194">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![進行状況をダウンロードする画像を表示、docker-compose build のコンソール出力。](./media/image25.png)

<span data-ttu-id="78f3c-196">**図 4-25**</span><span class="sxs-lookup"><span data-stu-id="78f3c-196">**Figure 4-25**.</span></span> <span data-ttu-id="78f3c-197">Docker のビルドを実行しています。</span><span class="sxs-lookup"><span data-stu-id="78f3c-197">Running docker build</span></span>

<span data-ttu-id="78f3c-198">直接実行しているのではなく、必要に応じて、 `docker build` 、プロジェクト フォルダーから最初に生成できます展開可能なフォルダー、実行を使用して、必要な .NET ライブラリと`dotnet publish`コマンドを使用し、実行`docker build`します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-198">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="78f3c-199">この例では、Docker イメージを作成、名前を持つ`cesardl/netcore-webapi-microservice-docker:first`(`:first`は特定のバージョンのように、タグです)。</span><span class="sxs-lookup"><span data-stu-id="78f3c-199">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="78f3c-200">複数のコンテナーで、構成した Docker アプリケーションを作成する必要がある各カスタム イメージでは、この手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-200">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="78f3c-201">既存のイメージで見つかりますローカル リポジトリ (開発用コンピューター)、docker を使用してイメージのコマンドを図 4-26 に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-201">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![コンソール コマンドの docker イメージを既存のイメージの表示から出力します。](./media/image26.png)

<span data-ttu-id="78f3c-203">**図 4-26**</span><span class="sxs-lookup"><span data-stu-id="78f3c-203">**Figure 4-26**.</span></span> <span data-ttu-id="78f3c-204">Docker イメージを使用して既存のイメージを表示します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-204">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="78f3c-205">手順 4: 複数のサービスで構成された Docker アプリを構築するときに docker compose.yml で、サービスを定義します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-205">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="78f3c-206">`docker-compose.yml`ファイル、一連の手順の次のセクションで説明されている展開コマンドを使用して、構成されたアプリケーションとしてデプロイ関連のサービスを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-206">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="78f3c-207">そのファイルでメインまたはルート ソリューション フォルダーを作成します。このようなコンテンツが`docker-compose.yml`ファイル。</span><span class="sxs-lookup"><span data-stu-id="78f3c-207">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

```yml
version: '3.4'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

<span data-ttu-id="78f3c-208">このケースでこのファイルは 2 つのサービスを定義します。 web サービス (カスタム サービス) と、redis サービス (一般的なキャッシュ サービス)。</span><span class="sxs-lookup"><span data-stu-id="78f3c-208">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="78f3c-209">各サービスは、各具象の Docker イメージを使用する必要があります、コンテナーとしてデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-209">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="78f3c-210">この特定の web サービスのイメージは、以下を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f3c-210">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="78f3c-211">現在のディレクトリに DockerFile からビルドします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-211">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="78f3c-212">公開されているポート 80 をコンテナー ホスト コンピューター上でポート 81 上での転送します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-212">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="78f3c-213">イメージを再構築することがなく、コードを変更することができるので、コンテナー内で指定するホスト上のプロジェクト ディレクトリをマウントします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-213">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="78f3c-214">Redis サービスに web サービスをリンクします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-214">Link the web service to the redis service</span></span>

<span data-ttu-id="78f3c-215">Redis サービスの使用、[最新のパブリック redis イメージ](https://hub.docker.com/_/redis/)Docker Hub レジストリからプルします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-215">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="78f3c-216">[redis](https://redis.io/)はサーバー側アプリケーションの人気のあるキャッシュ システムです。</span><span class="sxs-lookup"><span data-stu-id="78f3c-216">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="78f3c-217">手順 5: ビルドして Docker アプリの実行</span><span class="sxs-lookup"><span data-stu-id="78f3c-217">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="78f3c-218">アプリに 1 つのコンテナーのみがある場合だけ、Docker ホスト (VM または物理サーバー) にデプロイして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f3c-218">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="78f3c-219">ただし、複数のサービス、アプリが構成されている場合をする必要があります*組み立てること*もします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-219">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="78f3c-220">さまざまなオプションを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="78f3c-220">Let's see the different options.</span></span>

<span data-ttu-id="78f3c-221">***オプション a:1 つのコンテナーまたはサービスを実行します。***</span><span class="sxs-lookup"><span data-stu-id="78f3c-221">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="78f3c-222">次に示すように docker run コマンドを使用して、Docker イメージを実行できます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-222">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="78f3c-223">この特定の展開の私たち 要求をリダイレクトする内部ポート 5000 をポート 80 に送信します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-223">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="78f3c-224">外部ポート 80、ホスト レベルで、アプリケーションがリッスンしているようになりました。</span><span class="sxs-lookup"><span data-stu-id="78f3c-224">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="78f3c-225">***オプション b:構成して複数コンテナー アプリケーションの実行***</span><span class="sxs-lookup"><span data-stu-id="78f3c-225">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="78f3c-226">ほとんどのエンタープライズ シナリオでは、Docker アプリケーションを複数のサービスはから構成します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-226">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="78f3c-227">このような場合は、実行することができます、`docker-compose up`が以前に作成した docker compose.yml ファイルを使用するコマンド (図 4-27)、します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-227">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="78f3c-228">このコマンドを実行するには、すべての関連するコンテナーの構成済みのアプリケーションはデプロイします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-228">Running this command deploys a composed application with all of its related containers.</span></span>

![コンソール出力から、docker-compose up コマンド。](./media/image27.png)

<span data-ttu-id="78f3c-230">**図 4-27**</span><span class="sxs-lookup"><span data-stu-id="78f3c-230">**Figure 4-27**.</span></span> <span data-ttu-id="78f3c-231">"、Docker-compose up"コマンドの実行結果</span><span class="sxs-lookup"><span data-stu-id="78f3c-231">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="78f3c-232">実行した後`docker-compose up`、展開すると、アプリケーションとその関連コンテナー、Docker ホストに VM の表記で図 4-28 に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-232">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![複数コンテナー アプリケーションを実行している VM。](./media/image28.png)

<span data-ttu-id="78f3c-234">**図 4-28**</span><span class="sxs-lookup"><span data-stu-id="78f3c-234">**Figure 4-28**.</span></span> <span data-ttu-id="78f3c-235">Docker コンテナーが展開された VM</span><span class="sxs-lookup"><span data-stu-id="78f3c-235">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="78f3c-236">手順 6: (ローカル CD VM) では、ローカルで Docker アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-236">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="78f3c-237">この手順は、アプリの実行内容によって異なります。</span><span class="sxs-lookup"><span data-stu-id="78f3c-237">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="78f3c-238">シンプルな .NET Core Web API"Hello World"を 1 つのコンテナーまたはサービスとしてデプロイされている、DockerFile で指定された TCP ポートを提供することで、サービスにアクセスするとだけです。</span><span class="sxs-lookup"><span data-stu-id="78f3c-238">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="78f3c-239">サービスに移動する localhost が有効でない場合は、このコマンドを使用して、マシンの IP アドレスを検索します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-239">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="78f3c-240">Docker ホストでは、ブラウザーを開いて、そのサイトに移動します図 4-29 に示すようにアプリ/サービスを実行して、参照してください必要があります。</span><span class="sxs-lookup"><span data-stu-id="78f3c-240">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Localhost/API/値からの応答のブラウザー ビュー。](./media/image29.png)

<span data-ttu-id="78f3c-242">**図 4-29**</span><span class="sxs-lookup"><span data-stu-id="78f3c-242">**Figure 4-29**.</span></span> <span data-ttu-id="78f3c-243">Localhost を使用してローカルで Docker アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="78f3c-243">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="78f3c-244">方法で展開されているため、ポート 80 を使用していますが、ポート 5000 に内部的にリダイレクトされていることに注意してください`docker run`、前述のようです。</span><span class="sxs-lookup"><span data-stu-id="78f3c-244">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="78f3c-245">これは、CURL を使用して、ターミナルから、テストできます。</span><span class="sxs-lookup"><span data-stu-id="78f3c-245">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="78f3c-246">図 4-30 で示すように、Windows で Docker のインストールでは、既定の IP、10.0.75.1、です。</span><span class="sxs-lookup"><span data-stu-id="78f3c-246">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![コンソール出力の取得から、 http://10.0.75.1/API/valuesと curl](./media/image30.png)

<span data-ttu-id="78f3c-248">**図 4-30**</span><span class="sxs-lookup"><span data-stu-id="78f3c-248">**Figure 4-30**.</span></span> <span data-ttu-id="78f3c-249">CURL を使用してローカルの Docker アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="78f3c-249">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="78f3c-250">**Docker で実行されているコンテナーのデバッグ**</span><span class="sxs-lookup"><span data-stu-id="78f3c-250">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="78f3c-251">Visual Studio Code は、Node.js と .NET Core コンテナーなどの他のプラットフォームを使用している場合に、Docker のデバッグをサポートします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-251">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="78f3c-252">デバッグすることもできます Docker でコンテナーを .NET Core または .NET Framework Visual Studio の Windows または Mac で使用する場合、次のセクションで説明されているとします。</span><span class="sxs-lookup"><span data-stu-id="78f3c-252">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!情報]
>
> <span data-ttu-id="78f3c-254">Node.js の Docker コンテナーのデバッグに関する詳細については、するには<https://blog.docker.com/2016/07/live-debugging-docker/>と<https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>します。</span><span class="sxs-lookup"><span data-stu-id="78f3c-254">To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="78f3c-255">[前へ](docker-apps-development-environment.md)
>[次へ](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="78f3c-255">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
