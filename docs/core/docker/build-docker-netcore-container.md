---
title: Docker を使用してアプリをコンテナー化するチュートリアル
description: このチュートリアルでは、Docker を使って .NET Core アプリケーションをコンテナー化する方法を学習します。
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 8255a901c706e55e143cdf23dda0eb9bc79d245d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58844965"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="e7fac-103">チュートリアル: NET Core アプリのコンテナー化</span><span class="sxs-lookup"><span data-stu-id="e7fac-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="e7fac-104">このチュートリアルでは、.NET Core アプリケーションを含む Docker イメージをビルドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="e7fac-105">そのイメージを使って、ローカル開発環境、プライベート クラウド、またはパブリック クラウド用にコンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="e7fac-106">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-106">In this tutorial you will learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="e7fac-107">Dockerfile を作成する</span><span class="sxs-lookup"><span data-stu-id="e7fac-107">Create a Dockerfile</span></span>
> * <span data-ttu-id="e7fac-108">Microsoft .NET Core Docker の基本イメージをプルする</span><span class="sxs-lookup"><span data-stu-id="e7fac-108">Pull a Microsoft .NET Core Docker base image</span></span>
> * <span data-ttu-id="e7fac-109">アプリをカスタマイズしてイメージにデプロイする</span><span class="sxs-lookup"><span data-stu-id="e7fac-109">Customize and deploy your app to the image</span></span>
> * <span data-ttu-id="e7fac-110">コンテナーを作成して実行する</span><span class="sxs-lookup"><span data-stu-id="e7fac-110">Create and run a container</span></span>
> * <span data-ttu-id="e7fac-111">Azure に配置する</span><span class="sxs-lookup"><span data-stu-id="e7fac-111">Deploy to Azure</span></span>

<span data-ttu-id="e7fac-112">このチュートリアルでは、Docker コンテナー ビルドと .NET Core アプリケーションの展開タスクについて学習します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-112">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="e7fac-113">[Docker プラットフォーム](https://docs.docker.com/engine/docker-overview/#the-docker-platform)では [Docker エンジン](https://docs.docker.com/engine/docker-overview/#docker-engine)を使用してアプリを簡単にビルドし、[Docker イメージ](https://docs.docker.com/glossary/?term=image)としてパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-113">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="e7fac-114">これらのイメージは [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 形式で記述され、[階層型コンテナー](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)に展開され、実行されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-114">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>



## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="e7fac-115">.NET Core:入門として最も簡単な方法</span><span class="sxs-lookup"><span data-stu-id="e7fac-115">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="e7fac-116">Docker イメージを作成する前に、コンテナー化するアプリケーションを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7fac-116">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="e7fac-117">それは Linux、MacOS、Windows で作成できます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-117">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="e7fac-118">これを行う最も迅速かつ簡単な方法は、.NET Core を利用することです。</span><span class="sxs-lookup"><span data-stu-id="e7fac-118">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="e7fac-119">.NET Core CLI ツールセットに慣れていない場合は、「[.NET Core SDK overview](../tools/index.md)」(.NET Core SDK の概要) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7fac-119">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="e7fac-120">Windows コンテナーと Linux コンテナーの両方を[マルチアーキテクチャ ベース タグ](https://github.com/dotnet/announcements/issues/14)でビルドできます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-120">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="e7fac-121">初めての .NET Core Docker アプリ</span><span class="sxs-lookup"><span data-stu-id="e7fac-121">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e7fac-122">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7fac-122">Prerequisites</span></span>

<span data-ttu-id="e7fac-123">このチュートリアルを完了するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="e7fac-123">To complete this tutorial:</span></span>

#### <a name="net-core-sdk"></a><span data-ttu-id="e7fac-124">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="e7fac-124">.NET Core SDK</span></span>

* <span data-ttu-id="e7fac-125">[.NET Core 2.1 SDK](https://www.microsoft.com/net/download) 以降をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e7fac-125">Install [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) or later.</span></span>

<span data-ttu-id="e7fac-126">.NET Core 2.1 がサポートされているオペレーティング システムの完全なリスト、サポートが終了した OS、およびライフサイクル ポリシーのリンクについては、「[.NET Core 2.1 - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」 (.NET Core 2.1 - サポートされる OS のバージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7fac-126">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="e7fac-127">コード エディターをまだインストールしていなければ、お気に入りのエディターをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="e7fac-127">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="e7fac-128">コード エディターをインストールする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="e7fac-128">Need to install a code editor?</span></span> <span data-ttu-id="e7fac-129">[Visual Studio Code](https://code.visualstudio.com/download) を試してください。</span><span class="sxs-lookup"><span data-stu-id="e7fac-129">Try [Visual Studio Code](https://code.visualstudio.com/download)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="e7fac-130">Docker クライアントをインストールする</span><span class="sxs-lookup"><span data-stu-id="e7fac-130">Installing Docker Client</span></span>

<span data-ttu-id="e7fac-131">[Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) 以降の Docker クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e7fac-131">Install [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="e7fac-132">Docker クライアントがインストール可能な OS:</span><span class="sxs-lookup"><span data-stu-id="e7fac-132">The Docker client can be installed in:</span></span>

* <span data-ttu-id="e7fac-133">Linux ディストリビューション</span><span class="sxs-lookup"><span data-stu-id="e7fac-133">Linux distributions</span></span>

   * [<span data-ttu-id="e7fac-134">CentOS</span><span class="sxs-lookup"><span data-stu-id="e7fac-134">CentOS</span></span>](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [<span data-ttu-id="e7fac-135">Debian</span><span class="sxs-lookup"><span data-stu-id="e7fac-135">Debian</span></span>](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [<span data-ttu-id="e7fac-136">Fedora</span><span class="sxs-lookup"><span data-stu-id="e7fac-136">Fedora</span></span>](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [<span data-ttu-id="e7fac-137">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="e7fac-137">Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [<span data-ttu-id="e7fac-138">macOS</span><span class="sxs-lookup"><span data-stu-id="e7fac-138">macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)

* <span data-ttu-id="e7fac-139">[Windows](https://docs.docker.com/docker-for-windows/install/)</span><span class="sxs-lookup"><span data-stu-id="e7fac-139">[Windows](https://docs.docker.com/docker-for-windows/install/).</span></span>

### <a name="create-a-net-core-21-console-app-for-dockerization"></a><span data-ttu-id="e7fac-140">Docker で動作させるために .NET Core 2.1 コンソール アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="e7fac-140">Create a .NET Core 2.1 console app for Dockerization</span></span>

<span data-ttu-id="e7fac-141">コマンド プロンプトを開き、*Hello* という名前のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-141">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="e7fac-142">作成したフォルダーに移動し、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-142">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="e7fac-143">簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-143">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="e7fac-144">[`dotnet new`](../tools/dotnet-new.md) は、コンソール アプリのビルドに必要な依存関係を含む最新の `Hello.csproj` プロジェクト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-144">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="e7fac-145">また、アプリケーションのエントリ ポイントを含む基本的なファイルである `Program.cs` も作成します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-145">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="e7fac-146">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="e7fac-146">`Hello.csproj`:</span></span>

   <span data-ttu-id="e7fac-147">プロジェクト ファイルでは、依存関係を復元し、プログラムをビルドするために必要なすべてのものを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-147">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="e7fac-148">`OutputType` タグは、実行可能ファイル (つまり、コンソール アプリケーション) をビルドすることを示します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-148">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="e7fac-149">`TargetFramework` タグは、対象の .NET 実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-149">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="e7fac-150">高度なシナリオでは、複数の対象フレームワークを指定し、1 回の操作で指定したフレームワークにビルドできます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-150">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="e7fac-151">このチュートリアルでは、.NET Core 2.1 のためにビルドします。</span><span class="sxs-lookup"><span data-stu-id="e7fac-151">In this tutorial, we build for .NET Core 2.1.</span></span>

   <span data-ttu-id="e7fac-152">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="e7fac-152">`Program.cs`:</span></span>

   <span data-ttu-id="e7fac-153">プログラムは `using System` で始まります。</span><span class="sxs-lookup"><span data-stu-id="e7fac-153">The program starts by `using System`.</span></span> <span data-ttu-id="e7fac-154">これは、"`System` 名前空間のすべてがこのファイルのスコープになる" こと意味します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-154">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="e7fac-155">`System` 名前空間には、`string` などの基本的な構造、または数値型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-155">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="e7fac-156">次に、`Hello` という名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-156">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="e7fac-157">名前空間は必要なものに変更できます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-157">You can change namespace to anything you want.</span></span> <span data-ttu-id="e7fac-158">`Program` という名前のクラスは、引数として文字列配列を使用する `Main` メソッドで、その名前空間内に定義されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-158">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="e7fac-159">この配列には、コンパイル済みプログラムの呼び出し時に渡される引数のリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-159">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="e7fac-160">今回の例では、"Hello World!" とだけ記述されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-160">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="e7fac-161">記述するだけです。</span><span class="sxs-lookup"><span data-stu-id="e7fac-161">to the console.</span></span>

   <span data-ttu-id="e7fac-162">**dotnet new** で [`dotnet restore`](../tools/dotnet-restore.md) コマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-162">**dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="e7fac-163">**dotnet restore** は [NuGet](https://www.nuget.org/) (.NET パッケージ マネージャー) 呼び出しによって依存関係ツリーを復元します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-163">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="e7fac-164">NuGet は次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-164">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="e7fac-165">*Hello.csproj* ファイルを分析します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-165">analyzes the *Hello.csproj* file.</span></span>
   * <span data-ttu-id="e7fac-166">ファイルの依存関係をダウンロードします (またはコンピューター キャッシュから取得します)。</span><span class="sxs-lookup"><span data-stu-id="e7fac-166">downloads the file dependencies (or grabs from your machine cache).</span></span>
   * <span data-ttu-id="e7fac-167">*obj/project.assets.json* ファイルを記述します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-167">writes the *obj/project.assets.json* file.</span></span>

   <span data-ttu-id="e7fac-168">*project.assets.json* ファイルは、NuGet の依存関係グラフ、バインディング解決、その他のアプリ メタデータをすべて揃えたものです。</span><span class="sxs-lookup"><span data-stu-id="e7fac-168">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="e7fac-169">この必須ファイルは、ソース コードを正しく処理するために、[`dotnet build`](../tools/dotnet-build.md) や [`dotnet run`](../tools/dotnet-run.md) など、他のツールで使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-169">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>

2. `$ dotnet run`

   <span data-ttu-id="e7fac-170">[`dotnet run`](../tools/dotnet-run.md) は [`dotnet build`](../tools/dotnet-build.md) を呼び出してビルドの成功を確認し、それから `dotnet <assembly.dll>` を呼び出してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-170">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>

    ```console
    $ dotnet run

    Hello World!
    ```

    <span data-ttu-id="e7fac-171">高度なシナリオについては、「[.NET Core アプリケーション展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7fac-171">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="e7fac-172">.NET Core アプリケーションを Docker で動作させる</span><span class="sxs-lookup"><span data-stu-id="e7fac-172">Dockerize the .NET Core application</span></span>

<span data-ttu-id="e7fac-173">Hello .NET Core コンソール アプリがローカルで正常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-173">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="e7fac-174">それでは先に進み、アプリをビルドし、Docker で実行します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-174">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="e7fac-175">初めての Dockerfile</span><span class="sxs-lookup"><span data-stu-id="e7fac-175">Your first Dockerfile</span></span>

<span data-ttu-id="e7fac-176">テキスト エディターを開き、始めましょう。</span><span class="sxs-lookup"><span data-stu-id="e7fac-176">Open your text editor and let's get started!</span></span> <span data-ttu-id="e7fac-177">引き続き、アプリをビルドした Hello ディレクトリから作業します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-177">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="e7fac-178">Linux コンテナーまたは [Windows コンテナー](https://docs.microsoft.com/virtualization/windowscontainers/about/)の次の Docker 命令を新しいファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-178">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="e7fac-179">完了したら、Hello ディレクトリのルートに **Dockerfile** として保存します。拡張子は付けません。場合によっては、ファイルの種類を `All types (*.*)` か、それと同様のものに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7fac-179">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="e7fac-180">Dockerfile ファイルには、順次実行される Docker ビルド命令が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7fac-180">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="e7fac-181">最初の命令は [**FROM**](https://docs.docker.com/engine/reference/builder/#from) のはずです。</span><span class="sxs-lookup"><span data-stu-id="e7fac-181">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="e7fac-182">この命令は新しいビルド ステージを初期化し、残りの命令のベース イメージを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-182">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="e7fac-183">マルチアーキテクチャ タグは、Docker for Windows [コンテナー モード](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers)に基づき、Windows コンテナーまたは Linux コンテナーをプルします。</span><span class="sxs-lookup"><span data-stu-id="e7fac-183">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="e7fac-184">今回の例のベース イメージは microsoft/dotnet リポジトリの 2.1-sdk イメージです。</span><span class="sxs-lookup"><span data-stu-id="e7fac-184">The Base Image for our sample is the 2.1-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

<span data-ttu-id="e7fac-185">[**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) 命令は残りの命令、RUN、CMD、ENTRYPOINT、COPY、ADD Dockerfile の作業ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-185">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="e7fac-186">ディレクトリが存在しなければ、作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-186">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="e7fac-187">今回、WORKDIR がアプリ ディレクトリに設定されています。</span><span class="sxs-lookup"><span data-stu-id="e7fac-187">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="e7fac-188">[**COPY**](https://docs.docker.com/engine/reference/builder/#copy) 命令はソース パスから新しいファイルまたはディレクトリをコピーし、それをターゲットのコンテナー ファイルシステムに追加します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-188">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="e7fac-189">この命令により、C# プロジェクトがコンテナーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-189">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="e7fac-190">[**RUN**](https://docs.docker.com/engine/reference/builder/#run) 命令は現在のイメージに加えて新しい層でコマンドを実行し、結果をコミットします。</span><span class="sxs-lookup"><span data-stu-id="e7fac-190">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="e7fac-191">結果のコミットされたイメージは、Dockerfile の次の手順に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-191">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="e7fac-192">**dotnet restore** を実行し、C# プロジェクト ファイルの必要な依存関係を取得します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-192">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span>

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="e7fac-193">この **COPY** 命令は、コンテナーの残りのファイルを新しい[層](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)にコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7fac-193">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="e7fac-194">この **RUN** 命令でアプリが公開されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-194">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="e7fac-195">[**dotnet publish**](../tools/dotnet-publish.md) コマンドはアプリケーションをコンパイルし、プロジェクト ファイルに指定されているその依存関係を読み通し、結果的に生成された一連のファイルをディレクトリに公開します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-195">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="e7fac-196">今回のアプリは **Release** 構成で公開され、既定のディレクトリに出力されます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-196">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="e7fac-197">[**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) 命令では、コンテナーを実行可能ファイルとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7fac-197">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="e7fac-198">これで次のような Dockerfile が用意されました。</span><span class="sxs-lookup"><span data-stu-id="e7fac-198">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="e7fac-199">アプリをイメージにコピーする</span><span class="sxs-lookup"><span data-stu-id="e7fac-199">copies your app to the image</span></span>
* <span data-ttu-id="e7fac-200">アプリの依存関係をイメージにコピーする</span><span class="sxs-lookup"><span data-stu-id="e7fac-200">your app's dependencies to the image</span></span>
* <span data-ttu-id="e7fac-201">実行可能ファイルとして実行できるようにアプリをビルドする</span><span class="sxs-lookup"><span data-stu-id="e7fac-201">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-app"></a><span data-ttu-id="e7fac-202">Hello .NET Core アプリをビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="e7fac-202">Build and run the Hello .NET Core app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="e7fac-203">基本的 Docker コマンド</span><span class="sxs-lookup"><span data-stu-id="e7fac-203">Essential Docker commands</span></span>

<span data-ttu-id="e7fac-204">次の Docker コマンドは不可欠です。</span><span class="sxs-lookup"><span data-stu-id="e7fac-204">These Docker commands are essential:</span></span>

* [<span data-ttu-id="e7fac-205">docker build</span><span class="sxs-lookup"><span data-stu-id="e7fac-205">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="e7fac-206">docker run</span><span class="sxs-lookup"><span data-stu-id="e7fac-206">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="e7fac-207">docker ps</span><span class="sxs-lookup"><span data-stu-id="e7fac-207">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="e7fac-208">docker stop</span><span class="sxs-lookup"><span data-stu-id="e7fac-208">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="e7fac-209">docker rm</span><span class="sxs-lookup"><span data-stu-id="e7fac-209">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="e7fac-210">docker rmi</span><span class="sxs-lookup"><span data-stu-id="e7fac-210">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="e7fac-211">docker image</span><span class="sxs-lookup"><span data-stu-id="e7fac-211">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="e7fac-212">ビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="e7fac-212">Build and run</span></span>

<span data-ttu-id="e7fac-213">Dockerfile を記述しました。これで、Docker はアプリをビルドし、コンテナーを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7fac-213">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="e7fac-214">`docker build` コマンドからの出力は、次のコンソール出力と同じようなものになります。</span><span class="sxs-lookup"><span data-stu-id="e7fac-214">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="e7fac-215">この出力からわかるように、Docker エンジンは Dockerfile を利用してコンテナーをビルドしました。</span><span class="sxs-lookup"><span data-stu-id="e7fac-215">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="e7fac-216">`docker run` コマンドからの出力は、次のコンソール出力と同じようなものになります。</span><span class="sxs-lookup"><span data-stu-id="e7fac-216">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="e7fac-217">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="e7fac-217">Congratulations!</span></span> <span data-ttu-id="e7fac-218">今回の成果:</span><span class="sxs-lookup"><span data-stu-id="e7fac-218">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="e7fac-219">ローカル .NET Core アプリを作成しました</span><span class="sxs-lookup"><span data-stu-id="e7fac-219">Created a local .NET Core app</span></span>
> * <span data-ttu-id="e7fac-220">Dockerfile を作成し、最初のコンテナーをビルドしました</span><span class="sxs-lookup"><span data-stu-id="e7fac-220">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="e7fac-221">Docker で動作させるアプリをビルドし、実行しました</span><span class="sxs-lookup"><span data-stu-id="e7fac-221">Built and ran your Dockerized app</span></span>

## <a name="next-steps"></a><span data-ttu-id="e7fac-222">次の手順</span><span class="sxs-lookup"><span data-stu-id="e7fac-222">Next steps</span></span>

<span data-ttu-id="e7fac-223">次の手順としては以下のものを用意しています。</span><span class="sxs-lookup"><span data-stu-id="e7fac-223">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="e7fac-224">.NET Docker イメージの入門動画</span><span class="sxs-lookup"><span data-stu-id="e7fac-224">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="e7fac-225">Visual Studio、Docker、Azure コンテナーのインスタンスの併用の利点</span><span class="sxs-lookup"><span data-stu-id="e7fac-225">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)
* [<span data-ttu-id="e7fac-226">Docker for Azure クイックスタート</span><span class="sxs-lookup"><span data-stu-id="e7fac-226">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="e7fac-227">Docker for Azure でアプリをデプロイする</span><span class="sxs-lookup"><span data-stu-id="e7fac-227">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!NOTE]
> <span data-ttu-id="e7fac-228">Azure サブスクリプションをお持ちでない場合は、[今すぐサインアップ](https://azure.microsoft.com/free/?b=16.48)して 30 日間の無料アカウントと 200 ドル分の Azure クレジットを取得し、お好きな Azure サービスの組み合わせを試しましょう。</span><span class="sxs-lookup"><span data-stu-id="e7fac-228">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="e7fac-229">このサンプルで使用されている Docker イメージ</span><span class="sxs-lookup"><span data-stu-id="e7fac-229">Docker Images used in this sample</span></span>

<span data-ttu-id="e7fac-230">次の Docker イメージはこのサンプルで使用されています</span><span class="sxs-lookup"><span data-stu-id="e7fac-230">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="e7fac-231">関連資料</span><span class="sxs-lookup"><span data-stu-id="e7fac-231">Related resources</span></span>

* [<span data-ttu-id="e7fac-232">.NET Core Docker サンプル</span><span class="sxs-lookup"><span data-stu-id="e7fac-232">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [<span data-ttu-id="e7fac-233">Windows コンテナー上の Dockerfile</span><span class="sxs-lookup"><span data-stu-id="e7fac-233">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="e7fac-234">.NET Framework Docker サンプル</span><span class="sxs-lookup"><span data-stu-id="e7fac-234">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="e7fac-235">DockerHub の ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e7fac-235">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="e7fac-236">.NET Core アプリケーションを Docker で動作させる - Docker チュートリアル</span><span class="sxs-lookup"><span data-stu-id="e7fac-236">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="e7fac-237">Visual Studio Docker ツールの使用</span><span class="sxs-lookup"><span data-stu-id="e7fac-237">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="e7fac-238">Azure Container Registry から Azure Container Instances に Docker イメージを配置する</span><span class="sxs-lookup"><span data-stu-id="e7fac-238">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)