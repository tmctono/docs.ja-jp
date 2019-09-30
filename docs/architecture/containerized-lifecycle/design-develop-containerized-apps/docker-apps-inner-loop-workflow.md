---
title: Docker アプリの内部ループ開発ワークフロー
description: Docker アプリケーションの開発の "内部ループ" ワークフローについて説明します。
ms.date: 02/15/2019
ms.openlocfilehash: 04e1b29e6a0cef89df05cc9124806c74a38b5249
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214360"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="fb748-103">Docker アプリの内部ループ開発ワークフロー</span><span class="sxs-lookup"><span data-stu-id="fb748-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="fb748-104">DevOps サイクル全体にまたがる外部ループ ワークフローをトリガーする前に、各内部ループが各開発者のコンピューターで開始され、アプリ自体をコード化し、希望する言語またはプラットフォームを使用し、ローカルでテストされます (図 4-21)。</span><span class="sxs-lookup"><span data-stu-id="fb748-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="fb748-105">ただし、すべての場合において、選択する言語、フレームワーク、プラットフォームに関係なく、共通する重要な点が 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="fb748-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="fb748-106">この特定のワークフローでは、常に Docker コンテナーを開発し、テストしますが、ローカルで行われます。</span><span class="sxs-lookup"><span data-stu-id="fb748-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![手順 1 - コード/実行/デバッグ](./media/image18.png)

<span data-ttu-id="fb748-108">**図 4-21**</span><span class="sxs-lookup"><span data-stu-id="fb748-108">**Figure 4-21**.</span></span> <span data-ttu-id="fb748-109">内部ループの開発コンテキスト</span><span class="sxs-lookup"><span data-stu-id="fb748-109">Inner-loop development context</span></span>

<span data-ttu-id="fb748-110">Docker イメージのコンテナーまたはインスタンスには、以下のコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fb748-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="fb748-111">選択したオペレーティング システム (Linux ディストリビューションや Windows など)</span><span class="sxs-lookup"><span data-stu-id="fb748-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="fb748-112">開発者が追加したファイル (アプリのバイナリなど)</span><span class="sxs-lookup"><span data-stu-id="fb748-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="fb748-113">構成 (環境の設定や依存関係など)</span><span class="sxs-lookup"><span data-stu-id="fb748-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="fb748-114">Docker でどのプロセスを実行するかに関する指示</span><span class="sxs-lookup"><span data-stu-id="fb748-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="fb748-115">Docker をプロセスとして活用する内部ループ開発ワークフローを設定できます (詳細は次のセクションにあります)。</span><span class="sxs-lookup"><span data-stu-id="fb748-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="fb748-116">環境設定の初回手順は含まれていません。それは一度だけ実行すれば良いからです。</span><span class="sxs-lookup"><span data-stu-id="fb748-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="fb748-117">Visual Studio Code と Docker CLI を使用し、Docker コンテナー内で 1 つのアプリをビルドする</span><span class="sxs-lookup"><span data-stu-id="fb748-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="fb748-118">アプリは自分のサービスと追加のライブラリ (依存関係) から構成されます。</span><span class="sxs-lookup"><span data-stu-id="fb748-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="fb748-119">図 4-22 では、Docker アプリをビルドするときに通常行う基本手順と各手順の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![ワークフローの概要:手順 1 - コード、手順 2 - Dockerfile を記述する、手順 3 - Dockerfile で定義されたイメージを作成する、手順 4 - docker-compose ファイルでサービスを定義する、手順 5 - コンテナーまたは作られたアプリを実行する、手順 6 - アプリをテストする、手順 7 - プッシュして外部ループを開始する (CI/CD パイプライン) か、開発を続ける](./media/image19.png)

<span data-ttu-id="fb748-121">**図 4-22**</span><span class="sxs-lookup"><span data-stu-id="fb748-121">**Figure 4-22**.</span></span> <span data-ttu-id="fb748-122">Docker CLI を利用し、Docker でコンテナー化されたアプリケーションのワークフローの概要</span><span class="sxs-lookup"><span data-stu-id="fb748-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="fb748-123">手順 1: Visual Studio Code でコーディングを開始し、初回アプリ/サービス ベースラインを作成する</span><span class="sxs-lookup"><span data-stu-id="fb748-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="fb748-124">アプリケーションの開発方法は、Docker を使用しない場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="fb748-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="fb748-125">違いは、開発中、ローカル環境 (Linux VM や Windows など) に配置されている Docker コンテナー内で実行されているアプリケーションやサービスを展開し、テストするということです。</span><span class="sxs-lookup"><span data-stu-id="fb748-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="fb748-126">**ローカル環境を設定する**</span><span class="sxs-lookup"><span data-stu-id="fb748-126">**Setting up your local environment**</span></span>

<span data-ttu-id="fb748-127">Mac または Windows 向けの最新版 Docker を使用すると、Docker アプリケーションをもっと簡単に開発できます。設定も簡単です。</span><span class="sxs-lookup"><span data-stu-id="fb748-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!TIP]
> <span data-ttu-id="fb748-128">Docker for Windows の設定方法については、<https://docs.docker.com/docker-for-windows/> にお進みください。</span><span class="sxs-lookup"><span data-stu-id="fb748-128">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="fb748-129">Docker for Mac の設定方法については、<https://docs.docker.com/docker-for-mac/> にお進みください。</span><span class="sxs-lookup"><span data-stu-id="fb748-129">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="fb748-130">また、Docker CLI の使用時、実際にアプリケーションを開発できるよう、コード エディターが必要です。</span><span class="sxs-lookup"><span data-stu-id="fb748-130">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="fb748-131">Microsoft からは Visual Studio Code が提供されます。これは Mac、Windows、Linux でサポートされている軽量のコード エディターであり、IntelliSense、[さまざまな言語のサポート](https://code.visualstudio.com/docs/languages/overview) (JavaScript、.NET、Go、Java、Ruby、Python、ほとんどの新しい言語)、[デバッグ](https://code.visualstudio.com/Docs/editor/debugging)、[Git との統合](https://code.visualstudio.com/Docs/editor/versioncontrol)、[拡張機能サポート](https://code.visualstudio.com/docs/extensions/overview)を提供します。</span><span class="sxs-lookup"><span data-stu-id="fb748-131">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="fb748-132">このエディターは、Mac および Linux の開発者に最適です。</span><span class="sxs-lookup"><span data-stu-id="fb748-132">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="fb748-133">Windows でも、完全な Visual Studio アプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-133">In Windows, you also can use the full Visual Studio application.</span></span>

> [!TIP]
> <span data-ttu-id="fb748-134">Windows、Mac、Linux 向けの Visual Studio Code をインストールする方法については、<https://code.visualstudio.com/docs/setup/setup-overview/> にお進みください。</span><span class="sxs-lookup"><span data-stu-id="fb748-134">For instructions on installing Visual Studio Code for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="fb748-135">Docker for Mac の設定方法については、<https://docs.docker.com/docker-for-mac/> にお進みください。</span><span class="sxs-lookup"><span data-stu-id="fb748-135">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="fb748-136">Docker CLI を使用して、あらゆるコード エディターでコードを記述できますが、Docker 拡張機能と共に Visual Studio Code を使用すると、ワークスペースで `Dockerfile` ファイルや `docker-compose.yml` ファイルを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-136">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="fb748-137">Visual Studio Code IDE からタスクやスクリプトを実行し、下部の Docker CLI を使用して Docker コマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb748-137">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="fb748-138">VS Code 用 Docker 拡張機能からは次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fb748-138">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="fb748-139">`Dockerfile` および `docker-compose.yml` ファイルの自動生成</span><span class="sxs-lookup"><span data-stu-id="fb748-139">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="fb748-140">`docker-compose.yml` および `Dockerfile` ファイルの構文強調表示とツールチップ</span><span class="sxs-lookup"><span data-stu-id="fb748-140">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="fb748-141">`Dockerfile` および `docker-compose.yml` ファイルの IntelliSense (入力候補)</span><span class="sxs-lookup"><span data-stu-id="fb748-141">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="fb748-142">`Dockerfile` ファイルの Lint 処理 (エラーと警告)</span><span class="sxs-lookup"><span data-stu-id="fb748-142">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="fb748-143">最も一般的な Docker コマンドのコマンド パレット (F1) 統合</span><span class="sxs-lookup"><span data-stu-id="fb748-143">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="fb748-144">イメージとコンテナーを管理するためのエクスプローラー統合</span><span class="sxs-lookup"><span data-stu-id="fb748-144">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="fb748-145">DockerHub と Azure Container Registry から Azure App Service へのイメージのデプロイ</span><span class="sxs-lookup"><span data-stu-id="fb748-145">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="fb748-146">Docker 拡張機能をインストールするには、Ctrl + Shift + P キーを押しながら、「`ext install`」と入力し、Install Extension コマンドを実行して Marketplace 拡張機能一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="fb748-146">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="fb748-147">次に、図 4-23 のように、「**docker**」と入力して結果にフィルターを適用し、Docker Support 拡張機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb748-147">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![VS Code 用 Docker 拡張機能の表示。](./media/image20.png)

<span data-ttu-id="fb748-149">**図 4-23**.</span><span class="sxs-lookup"><span data-stu-id="fb748-149">**Figure 4-23**.</span></span> <span data-ttu-id="fb748-150">Visual Studio Code で Docker 拡張機能をインストールする</span><span class="sxs-lookup"><span data-stu-id="fb748-150">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="fb748-151">手順 2: 既存のイメージ (プレーンな OS か、.NET Core、Node.js、Ruby などの開発環境) に関連する DockerFile を作成する</span><span class="sxs-lookup"><span data-stu-id="fb748-151">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="fb748-152">ビルドするカスタム イメージごとと、展開するコンテナーごとに `DockerFile` が必要になります。</span><span class="sxs-lookup"><span data-stu-id="fb748-152">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="fb748-153">アプリが 1 つのカスタム サービスで構成される場合、`DockerFile` が 1 つ必要になります。</span><span class="sxs-lookup"><span data-stu-id="fb748-153">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="fb748-154">ただし、(マイクロサービス アーキテクチャの場合のように) アプリが複数のサービスで構成される場合、サービスごとに `Dockerfile` が 1 つ必要になります。</span><span class="sxs-lookup"><span data-stu-id="fb748-154">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="fb748-155">`DockerFile` は通常、アプリまたはサービスのルート フォルダーに配置され、そのアプリまたはサービスを設定し、実行する方法を Docker に認識させるための必須のコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fb748-155">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="fb748-156">`DockerFile` を作成し、コード (node.js や .NET Core など) とともにプロジェクトに追加できます。この環境が初めての場合、次のヒントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fb748-156">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="fb748-157">Docker コンテナーに関連する `Dockerfile` および `docker-compose.yml` ファイルを使用するとき、Docker 拡張機能を利用してガイドを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="fb748-157">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="fb748-158">最終的には、このツールなしでこの種類のファイルを記述することになるでしょうが、Docker 拡張機能の使用は学習曲線を加速するので、開始点として推奨されます。</span><span class="sxs-lookup"><span data-stu-id="fb748-158">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="fb748-159">図 4-24 では、VS Code 用 Docker 拡張機能で docker-compose ファイルが追加される様子を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-159">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![VS Code 用 Docker 拡張機能のコンソール表示。](./media/image24.png)

<span data-ttu-id="fb748-161">**図 4-24**</span><span class="sxs-lookup"><span data-stu-id="fb748-161">**Figure 4-24**.</span></span> <span data-ttu-id="fb748-162">**Add Docker files to Workspace コマンド**で追加された Docker ファイル</span><span class="sxs-lookup"><span data-stu-id="fb748-162">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="fb748-163">DockerFile を追加するとき、(`FROM mcr.microsoft.com/dotnet/core/aspnet` を使用するなどして) 使用する基本の Docker イメージを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb748-163">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="fb748-164">通常、[Docker Hub レジストリ](https://hub.docker.com/)にある公式リポジトリから得られる基本イメージ ([.NET Core 用のイメージ](https://hub.docker.com/_/microsoft-dotnet-core/)や [Node.js 用のイメージ](https://hub.docker.com/_/node/)など) を基礎にしてカスタム イメージをビルドします。</span><span class="sxs-lookup"><span data-stu-id="fb748-164">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="fb748-165">***既存の公式 Docker イメージを使用する***</span><span class="sxs-lookup"><span data-stu-id="fb748-165">***Use an existing official Docker image***</span></span>

<span data-ttu-id="fb748-166">バージョン番号を持つ言語スタックの公式イメージ リポジトリを使うと、同じ言語機能が (開発、テスト、運用環境など) すべてのコンピューターで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fb748-166">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="fb748-167">次は .NET Core コンテナー向けサンプル DockerFile です。</span><span class="sxs-lookup"><span data-stu-id="fb748-167">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="fb748-168">この場合、イメージは、`FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` の行から、公式の ASP.NET Core Docker イメージ (Linux および Windows 用マルチアーキテクチャ) のバージョン 2.2 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="fb748-168">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="fb748-169">(このトピックの詳細については、[ASP.NET Core Docker イメージ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)に関するページと [.NET Core Docker イメージ](https://hub.docker.com/_/microsoft-dotnet-core/)に関するページを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="fb748-169">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="fb748-170">DockerFile では、実行時に使用する TCP ポートをリッスンするように Docker に指示することもできます (ポート 80 など)。</span><span class="sxs-lookup"><span data-stu-id="fb748-170">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="fb748-171">使用している言語とフレームワークによっては、Dockerfile に別の構成設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-171">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="fb748-172">たとえば、`["dotnet", "MySingleContainerWebApp.dll"]` を含む `ENTRYPOINT` 行では、.NET Core アプリケーションを実行するように Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="fb748-172">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="fb748-173">SDK と .NET Core CLI (`dotnet CLI`) を使用して .NET アプリケーションをビルドし、実行する場合、この設定は異なるものになります。</span><span class="sxs-lookup"><span data-stu-id="fb748-173">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="fb748-174">ここで重要なことは、ENTRYPOINT 行とその他の設定はアプリケーションに選択した言語とプラットフォームに依存するということです。</span><span class="sxs-lookup"><span data-stu-id="fb748-174">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!TIP]
> <span data-ttu-id="fb748-175">.NET Core アプリケーション向け Docker イメージのビルド方法については、<https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images> にお進みください。</span><span class="sxs-lookup"><span data-stu-id="fb748-175">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="fb748-176">独自のイメージをビルドする方法については、<https://docs.docker.com/engine/tutorials/dockerimages/> にお進みください。</span><span class="sxs-lookup"><span data-stu-id="fb748-176">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="fb748-177">**マルチアーキテクチャ イメージ リポジトリを使用する**</span><span class="sxs-lookup"><span data-stu-id="fb748-177">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="fb748-178">リポジトリの単一のイメージ名には、Linux イメージや Windows イメージなどのプラットフォーム バリアントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fb748-178">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="fb748-179">この機能では、Microsoft (基本イメージの作成者) などのベンダーが、複数のプラットフォーム (つまり、Linux および Windows) に対応できるリポジトリを 1 つ作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-179">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="fb748-180">たとえば、Docker Hub レジストリにある [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) リポジトリでは、同じイメージ名を使用して Linux および Windows Nano Server をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fb748-180">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="fb748-181">Windows ホストから [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) イメージをプルした場合、Windows バリアントがプルされ、同じイメージ名が Linux ホストからプルされた場合、Linux バリアントがプルされます。</span><span class="sxs-lookup"><span data-stu-id="fb748-181">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="fb748-182">***基本イメージを一から作成する***</span><span class="sxs-lookup"><span data-stu-id="fb748-182">***Create your base image from scratch***</span></span>

<span data-ttu-id="fb748-183">Docker の[この記事](https://docs.docker.com/engine/userguide/eng-image/baseimages/)で説明されているように、独自の Docker 基本イメージを一から作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-183">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="fb748-184">Docker を初めて使用するユーザーにはおそらく推奨されませんが、独自の基本イメージを設定するならそれは可能です。</span><span class="sxs-lookup"><span data-stu-id="fb748-184">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="fb748-185">手順 3: カスタム Docker イメージを作成し、それにサービスを埋め込む</span><span class="sxs-lookup"><span data-stu-id="fb748-185">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="fb748-186">アプリを構成するカスタム サービスごとに、関連イメージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb748-186">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="fb748-187">アプリが 1 つのサービスまたは Web アプリで構成されている場合、イメージは 1 つのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="fb748-187">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="fb748-188">"外部ループ DevOps ワークフロー" を考慮すると、イメージがソース コードからそのグローバル環境で作成されるよう、ソース コードを Git リポジトリにプッシュするたびに (継続的インテグレーション)、自動化されたビルド プロセスによってイメージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fb748-188">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="fb748-189">ただし、その外部ループ ルートに進むことを検討する前に、正しく動作しないコードがソース コントロール システム (Git など) にプッシュされることがないよう、Docker アプリケーションが実際に正しく動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb748-189">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="fb748-190">そのため、各開発者はまず、内部ループ プロセス全体を行ってローカル テストし、それから、完全な機能または変更をソース コントロール システムにプッシュするまで開発を続けます。</span><span class="sxs-lookup"><span data-stu-id="fb748-190">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="fb748-191">DockerFile を使用し、ローカル環境でイメージを作成するには、図 4-25 にあるように、docker build コマンドを使用できます (いくつかのコンテナー/サービスで構成されるアプリケーションに `docker-compose up --build` を実行することもできます)。</span><span class="sxs-lookup"><span data-stu-id="fb748-191">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![docker-compose ビルドのコンソール出力。ダウンロード進捗状況を確認できます。](./media/image25.png)

<span data-ttu-id="fb748-193">**図 4-25**</span><span class="sxs-lookup"><span data-stu-id="fb748-193">**Figure 4-25**.</span></span> <span data-ttu-id="fb748-194">docker build の実行</span><span class="sxs-lookup"><span data-stu-id="fb748-194">Running docker build</span></span>

<span data-ttu-id="fb748-195">任意で、プロジェクト フォルダーから `docker build` を直接実行する代わりに、`dotnet publish` 実行コマンドを使用し、それから `docker build` を実行することで、まず、必要な .NET ライブラリで展開可能なフォルダーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-195">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="fb748-196">この例では、`cesardl/netcore-webapi-microservice-docker:first` という名前で Docker イメージが作成されます (`:first` は特定のバージョンのようなタグです)。</span><span class="sxs-lookup"><span data-stu-id="fb748-196">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="fb748-197">いくつかのコンテナーで作成した Docker アプリケーション用に作成する必要のあるカスタム イメージごとにこの手順を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb748-197">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="fb748-198">図 4-26 にあるように、docker images コマンドを使用し、ローカル リポジトリ (開発コンピューター) の既存のイメージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-198">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![コマンド docker イメージからのコンソール出力。既存のイメージを確認できます。](./media/image26.png)

<span data-ttu-id="fb748-200">**図 4-26**</span><span class="sxs-lookup"><span data-stu-id="fb748-200">**Figure 4-26**.</span></span> <span data-ttu-id="fb748-201">docker images を使用した既存のイメージの表示</span><span class="sxs-lookup"><span data-stu-id="fb748-201">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="fb748-202">手順 4: 複数のサービスで Docker アプリケーションを構築するときに docker-compose.yml でサービスを定義する</span><span class="sxs-lookup"><span data-stu-id="fb748-202">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="fb748-203">`docker-compose.yml` ファイルを利用すると、次のセクションで説明するように、展開コマンドで構成済みアプリケーションとして展開する一連の関連サービスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-203">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="fb748-204">メインまたはルート ソリューション フォルダーでそのファイルを作成します。この `docker-compose.yml` ファイルで確認できるものと同様のコンテンツが含まれているはずです。</span><span class="sxs-lookup"><span data-stu-id="fb748-204">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

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

<span data-ttu-id="fb748-205">この特定のケースでは、このファイルにより、Web サービス (カスタム サービス) と redis サービス (人気のキャッシュ サービス) という 2 つのサービスが定義されます。</span><span class="sxs-lookup"><span data-stu-id="fb748-205">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="fb748-206">各サービスはコンテナーとして展開されます。そのため、それぞれに具体的な Docker イメージを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb748-206">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="fb748-207">この特定の Web サービスの場合、イメージでは次を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb748-207">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="fb748-208">現在のディレクトリで DockerFile からビルドする</span><span class="sxs-lookup"><span data-stu-id="fb748-208">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="fb748-209">コンテナー上の公開されているポート 80 をホスト コンピューター上の外部ポート 81 に転送する</span><span class="sxs-lookup"><span data-stu-id="fb748-209">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="fb748-210">コンテナー内の /code にホストのプロジェクト ディレクトリをマウントする (イメージを再ビルドしなくてもコードを変更できるようになります)</span><span class="sxs-lookup"><span data-stu-id="fb748-210">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="fb748-211">Web サービスと redis サービスをリンクする</span><span class="sxs-lookup"><span data-stu-id="fb748-211">Link the web service to the redis service</span></span>

<span data-ttu-id="fb748-212">redis サービスでは、Docker Hub レジストリからプルされた[最新のパブリック redis イメージ](https://hub.docker.com/_/redis/)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb748-212">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="fb748-213">[redis](https://redis.io/) はサーバー側アプリケーションとして人気のキャッシュ システムです。</span><span class="sxs-lookup"><span data-stu-id="fb748-213">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="fb748-214">手順 5: Docker アプリをビルドし、実行する</span><span class="sxs-lookup"><span data-stu-id="fb748-214">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="fb748-215">アプリにコンテナーが 1 つしかない場合、必要な作業は Docker ホスト (VM または物理サーバー) にそれを展開して実行することだけになります。</span><span class="sxs-lookup"><span data-stu-id="fb748-215">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="fb748-216">ただし、アプリが複数のサービスで構成されている場合、*それを作成する*必要もあります。</span><span class="sxs-lookup"><span data-stu-id="fb748-216">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="fb748-217">別のオプションを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="fb748-217">Let's see the different options.</span></span>

<span data-ttu-id="fb748-218">***オプション A: 1 つのコンテナーまたはサービスを実行する***</span><span class="sxs-lookup"><span data-stu-id="fb748-218">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="fb748-219">次に示すように docker run コマンドを使用し、Docker イメージを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fb748-219">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="fb748-220">この特定の展開の場合、ポート 80 に送信された要求を内部ポート 5000 にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="fb748-220">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="fb748-221">これでアプリケーションは、ホスト レベルで外部ポート 80 をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="fb748-221">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="fb748-222">***オプション B: 複数コンテナー アプリケーションを作成し、実行する***</span><span class="sxs-lookup"><span data-stu-id="fb748-222">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="fb748-223">ほとんどの企業のシナリオでは、Docker アプリケーションは複数のサービスから構成されます。</span><span class="sxs-lookup"><span data-stu-id="fb748-223">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="fb748-224">そのとき、`docker-compose up` コマンドを実行できますが (図 4-27)、このコマンドでは、前に作成した docker-compose.yml ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb748-224">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="fb748-225">このコマンドを実行すると、作成されたアプリケーションがそのすべての関連コンテナーと共に展開されます。</span><span class="sxs-lookup"><span data-stu-id="fb748-225">Running this command deploys a composed application with all of its related containers.</span></span>

![docker-compose up コマンドからのコンソール出力。](./media/image27.png)

<span data-ttu-id="fb748-227">**図 4-27**</span><span class="sxs-lookup"><span data-stu-id="fb748-227">**Figure 4-27**.</span></span> <span data-ttu-id="fb748-228">"docker-compose up" コマンドの実行結果</span><span class="sxs-lookup"><span data-stu-id="fb748-228">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="fb748-229">VM を表現する図 4-28 で示すように、`docker-compose up` の実行後、Docker ホストにアプリケーションとその関連コンテナーを展開します。</span><span class="sxs-lookup"><span data-stu-id="fb748-229">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![マルチコンテナー アプリケーションを実行する VM](./media/image28.png)

<span data-ttu-id="fb748-231">**図 4-28**</span><span class="sxs-lookup"><span data-stu-id="fb748-231">**Figure 4-28**.</span></span> <span data-ttu-id="fb748-232">Docker コンテナーが展開された VM</span><span class="sxs-lookup"><span data-stu-id="fb748-232">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="fb748-233">手順 6: Docker アプリケーションをローカル テストする (ローカル、CD VM で)</span><span class="sxs-lookup"><span data-stu-id="fb748-233">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="fb748-234">この手順は、アプリで何が実行されているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fb748-234">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="fb748-235">1 つのコンテナーまたはサービスとして展開される単純な .NET Core Web API "Hello World" の場合、DockerFile に指定されている TCP ポートを指定し、サービスにアクセスするだけです。</span><span class="sxs-lookup"><span data-stu-id="fb748-235">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="fb748-236">localhost がオンになっていない場合、サービスに移動し、次のコマンドを使用してコンピューターの IP アドレスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="fb748-236">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="fb748-237">Docker ホストでブラウザーを開き、そのサイトに移動します。図 4-29 に示すように、アプリ/サービスが実行中であることを確認できるはずです。</span><span class="sxs-lookup"><span data-stu-id="fb748-237">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![ブラウザーに表示される localhost/API/values からの応答](./media/image29.png)

<span data-ttu-id="fb748-239">**図 4-29**</span><span class="sxs-lookup"><span data-stu-id="fb748-239">**Figure 4-29**.</span></span> <span data-ttu-id="fb748-240">localhost を使用し、Docker アプリケーションをローカル テストする</span><span class="sxs-lookup"><span data-stu-id="fb748-240">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="fb748-241">ポート 80 を使用していますが、内部ではポート 5000 にリダイレクトされていることにご注意ください。これは、前に説明したように、`docker run` でこのように展開されたためです。</span><span class="sxs-lookup"><span data-stu-id="fb748-241">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="fb748-242">ターミナルから CURL を使用することでこれをテストできます。</span><span class="sxs-lookup"><span data-stu-id="fb748-242">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="fb748-243">Windows への Docker インストールの場合、図 4-30 に示すように、既定の IP は 10.0.75.1 です。</span><span class="sxs-lookup"><span data-stu-id="fb748-243">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![CURL で http://10.0.75.1/API/values を取得したときのコンソール出力](./media/image30.png)

<span data-ttu-id="fb748-245">**図 4-30**</span><span class="sxs-lookup"><span data-stu-id="fb748-245">**Figure 4-30**.</span></span> <span data-ttu-id="fb748-246">CURL を使用した Docker アプリケーションのローカル テスト</span><span class="sxs-lookup"><span data-stu-id="fb748-246">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="fb748-247">**Docker で実行されているコンテナーをデバッグする**</span><span class="sxs-lookup"><span data-stu-id="fb748-247">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="fb748-248">Visual Studio Code では、Node.js かその他のプラットフォーム (.NET Core コンテナーなど) を使用している場合、Docker をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="fb748-248">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="fb748-249">次のセクションで説明するように、Windows または Mac 向けの Visual Studio の使用時、Docker で .NET Core または .NET Framework コンテナーをデバッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fb748-249">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!情報]
>
> <span data-ttu-id="fb748-251">Node.js Docker コンテナーのデバッグに関する詳細については、<https://blog.docker.com/2016/07/live-debugging-docker/> と <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/> にお進みください。</span><span class="sxs-lookup"><span data-stu-id="fb748-251">To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fb748-252">[前へ](docker-apps-development-environment.md)
>[次へ](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="fb748-252">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
