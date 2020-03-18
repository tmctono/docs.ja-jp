---
title: ドッカー - WCF 開発者向け gRPC
description: コア gRPC アプリケーションASP.NET用の Docker イメージの作成
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148115"
---
# <a name="create-docker-images"></a><span data-ttu-id="94476-103">ドッカーイメージの作成</span><span class="sxs-lookup"><span data-stu-id="94476-103">Create Docker images</span></span>

<span data-ttu-id="94476-104">このセクションでは、Docker、Kubernetes、またはその他のコンテナー環境で実行できる、ASP.NETコア gRPC アプリケーション用の Docker イメージの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="94476-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="94476-105">ASP.NETコア MVC Web アプリと gRPC サービスで使用されるサンプル アプリケーションは、GitHub の[ドットネット アーキテクチャ/grpc-for-wcf 開発者](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample)リポジトリで利用できます。</span><span class="sxs-lookup"><span data-stu-id="94476-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="94476-106">ASP.NET コア アプリケーションのマイクロソフト ベース イメージ</span><span class="sxs-lookup"><span data-stu-id="94476-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="94476-107">マイクロソフトでは、.NET Core アプリケーションを構築および実行するためのさまざまな基本イメージを提供しています。</span><span class="sxs-lookup"><span data-stu-id="94476-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="94476-108">core 3.0 イメージASP.NET作成するには、次の 2 つの基本イメージを使用します。</span><span class="sxs-lookup"><span data-stu-id="94476-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="94476-109">アプリケーションをビルドして公開する SDK イメージ。</span><span class="sxs-lookup"><span data-stu-id="94476-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="94476-110">配置用のランタイム イメージ。</span><span class="sxs-lookup"><span data-stu-id="94476-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="94476-111">Image</span><span class="sxs-lookup"><span data-stu-id="94476-111">Image</span></span> | <span data-ttu-id="94476-112">説明</span><span class="sxs-lookup"><span data-stu-id="94476-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="94476-113">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="94476-113">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="94476-114">を使用してアプリケーション`docker build`を構築する場合</span><span class="sxs-lookup"><span data-stu-id="94476-114">For building applications with `docker build`.</span></span> <span data-ttu-id="94476-115">生産時には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="94476-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="94476-116">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="94476-116">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="94476-117">ランタイムおよびASP.NETコア依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="94476-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="94476-118">生産のため。</span><span class="sxs-lookup"><span data-stu-id="94476-118">For production.</span></span> |

<span data-ttu-id="94476-119">各イメージには、タグによって区別される、異なる Linux ディストリビューションに基づく 4 つのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="94476-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="94476-120">イメージ タグ</span><span class="sxs-lookup"><span data-stu-id="94476-120">Image tag(s)</span></span> | <span data-ttu-id="94476-121">Linux</span><span class="sxs-lookup"><span data-stu-id="94476-121">Linux</span></span> | <span data-ttu-id="94476-122">Notes</span><span class="sxs-lookup"><span data-stu-id="94476-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="94476-123">3.0バスター、3.0</span><span class="sxs-lookup"><span data-stu-id="94476-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="94476-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="94476-124">Debian 10</span></span> | <span data-ttu-id="94476-125">OS バリアントが指定されていない場合のデフォルトイメージ。</span><span class="sxs-lookup"><span data-stu-id="94476-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="94476-126">3.0-アルパイン</span><span class="sxs-lookup"><span data-stu-id="94476-126">3.0-alpine</span></span> | <span data-ttu-id="94476-127">アルパイン 3.9</span><span class="sxs-lookup"><span data-stu-id="94476-127">Alpine 3.9</span></span> | <span data-ttu-id="94476-128">アルパインベースイメージは Debian や Ubuntu のイメージよりはるかに小さいです。</span><span class="sxs-lookup"><span data-stu-id="94476-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="94476-129">3.0-ディスコ</span><span class="sxs-lookup"><span data-stu-id="94476-129">3.0-disco</span></span> | <span data-ttu-id="94476-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="94476-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="94476-131">3.0-バイオニック</span><span class="sxs-lookup"><span data-stu-id="94476-131">3.0-bionic</span></span> | <span data-ttu-id="94476-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="94476-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="94476-133">アルパインベースイメージは、Debian と Ubuntu のイメージの場合は 200 MB に対して約 100 MB です。</span><span class="sxs-lookup"><span data-stu-id="94476-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="94476-134">一部のソフトウェア パッケージまたはライブラリは、Alpine のパッケージ管理で使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="94476-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="94476-135">どのイメージを使えばいいのかわからない場合は、デフォルトの Debian を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94476-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94476-136">ビルドとランタイムに同じバージョンの Linux を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94476-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="94476-137">あるバリアントでビルドおよび発行されたアプリケーションは、別のバリアントでは動作しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="94476-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="94476-138">Docker イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="94476-138">Create a Docker image</span></span>

<span data-ttu-id="94476-139">Docker イメージは Docker*ファイル*によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="94476-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="94476-140">これは、アプリケーションをビルドし、アプリケーションのビルドまたは実行に必要な依存関係をインストールするために必要なすべてのコマンドを含むテキスト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="94476-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="94476-141">次の例は、ASP.NET Core 3.0 アプリケーションの最も単純な Dockerfile を示しています。</span><span class="sxs-lookup"><span data-stu-id="94476-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="94476-142">Dockerfile には 2 つの部分があります:`sdk`最初の部分では、ベース イメージを使用してアプリケーションをビルドおよび発行します。2 番目の場合は、ベース`aspnet`からランタイム イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="94476-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="94476-143">これは、ランタイム`sdk`イメージの場合は約 200 MB のイメージに比べて約 900 MB であり、その内容のほとんどが実行時に不要であるためです。</span><span class="sxs-lookup"><span data-stu-id="94476-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="94476-144">ビルドステップ</span><span class="sxs-lookup"><span data-stu-id="94476-144">The build steps</span></span>

| <span data-ttu-id="94476-145">手順</span><span class="sxs-lookup"><span data-stu-id="94476-145">Step</span></span> | <span data-ttu-id="94476-146">説明</span><span class="sxs-lookup"><span data-stu-id="94476-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="94476-147">基本イメージを宣言し、エイリアスを`builder`割り当てます。</span><span class="sxs-lookup"><span data-stu-id="94476-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="94476-148">ディレクトリを`/src`作成し、現在の作業ディレクトリとして設定します。</span><span class="sxs-lookup"><span data-stu-id="94476-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="94476-149">ホスト上の現在のディレクトリの下にあるすべてのものを、イメージ上の現在のディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="94476-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="94476-150">外部パッケージを復元します (Core 3.0 フレームワークが SDK と共にプリインストールASP.NET)。</span><span class="sxs-lookup"><span data-stu-id="94476-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="94476-151">リリース ビルドをビルドして発行します。</span><span class="sxs-lookup"><span data-stu-id="94476-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="94476-152">フラグは`--runtime`必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="94476-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="94476-153">ランタイムイメージのステップ</span><span class="sxs-lookup"><span data-stu-id="94476-153">The runtime image steps</span></span>

| <span data-ttu-id="94476-154">手順</span><span class="sxs-lookup"><span data-stu-id="94476-154">Step</span></span> | <span data-ttu-id="94476-155">説明</span><span class="sxs-lookup"><span data-stu-id="94476-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="94476-156">新しい基本イメージを宣言します。</span><span class="sxs-lookup"><span data-stu-id="94476-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="94476-157">ディレクトリを`/app`作成し、現在の作業ディレクトリとして設定します。</span><span class="sxs-lookup"><span data-stu-id="94476-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="94476-158">最初`FROM`の行のエイリアスを使用して、公開されたアプリケーション`builder`を前のイメージからコピーします。</span><span class="sxs-lookup"><span data-stu-id="94476-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="94476-159">コンテナーの開始時に実行するコマンドを設定します。</span><span class="sxs-lookup"><span data-stu-id="94476-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="94476-160">ランタイム`dotnet`イメージのコマンドでは、DLL ファイルのみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="94476-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="94476-161">ドッカーの HTTPS</span><span class="sxs-lookup"><span data-stu-id="94476-161">HTTPS in Docker</span></span>

<span data-ttu-id="94476-162">Docker の Microsoft ベース`ASPNETCORE_URLS`イメージは`http://+:80`、環境変数を に設定し、Kestrel がそのポートで HTTPS なしで実行されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="94476-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="94476-163">カスタム証明書 ([自己ホスト型 gRPC アプリケーション](self-hosted.md)の説明) で HTTPS を使用している場合は、これをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94476-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="94476-164">Dockerfile のランタイム イメージ作成部分で環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="94476-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="94476-165">.docker無視ファイル</span><span class="sxs-lookup"><span data-stu-id="94476-165">The .dockerignore file</span></span>

<span data-ttu-id="94476-166">ファイルを`.gitignore`ソース管理から除外するファイルと同様に、ファイルを`.dockerignore`使用して、ビルド中にファイルやディレクトリをイメージにコピーしないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="94476-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="94476-167">これはコピー時間を節約するだけでなく、PCの`obj`ディレクトリがイメージにコピーされるというエラーを回避できます。</span><span class="sxs-lookup"><span data-stu-id="94476-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="94476-168">少なくとも、ファイルのエントリと`bin``obj`ファイルにエントリを追加`.dockerignore`する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94476-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="94476-169">イメージをビルドする</span><span class="sxs-lookup"><span data-stu-id="94476-169">Build the image</span></span>

<span data-ttu-id="94476-170">単一のアプリケーション、つまり単一の Dockerfile を持つソリューションの場合、Dockerfile を基本ディレクトリに配置するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="94476-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="94476-171">つまり、ファイルと同じディレクトリに`.sln`置きます。</span><span class="sxs-lookup"><span data-stu-id="94476-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="94476-172">その場合、イメージをビルドするには、Dockerfile を`docker build`含むディレクトリから次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="94476-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="94476-173">紛らわしい名前`--tag`のフラグ ( に短縮できる`-t`) は、イメージの名前全体を指定します。</span><span class="sxs-lookup"><span data-stu-id="94476-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="94476-174">`.`最後に、ビルドが実行されるコンテキストを指定します。Dockerfile 内のコマンド`COPY`の現在の作業ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="94476-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="94476-175">1 つのソリューション内に複数のアプリケーションがある場合は、各アプリケーションの Dockerfile を、ファイルの横にある`.csproj`独自のフォルダーに保持できます。</span><span class="sxs-lookup"><span data-stu-id="94476-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="94476-176">ベース ディレクトリからコマンド`docker build`を実行して、ソリューションとすべてのプロジェクトがイメージにコピーされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94476-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="94476-177">(または`-f`) フラグを使用して、現在のディレクトリの`--file`下に Dockerfile を指定できます。</span><span class="sxs-lookup"><span data-stu-id="94476-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="94476-178">マシン上のコンテナでイメージを実行する</span><span class="sxs-lookup"><span data-stu-id="94476-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="94476-179">ローカル Docker インスタンスでイメージを実行するには、コマンド`docker run`を使用します。</span><span class="sxs-lookup"><span data-stu-id="94476-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="94476-180">この`-ti`フラグは、現在のターミナルをコンテナのターミナルに接続し、対話モードで実行します。</span><span class="sxs-lookup"><span data-stu-id="94476-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="94476-181">localhost ネットワーク インターフェイスのポート 5000 にコンテナー上の`-p 5000:80`パブリッシュ (リンク) ポート 80。</span><span class="sxs-lookup"><span data-stu-id="94476-181">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="94476-182">イメージをレジストリにプッシュする</span><span class="sxs-lookup"><span data-stu-id="94476-182">Push the image to a registry</span></span>

<span data-ttu-id="94476-183">イメージが動作することを確認したら、Docker レジストリにプッシュして他のシステムで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="94476-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="94476-184">内部ネットワークは、Docker レジストリをプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94476-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="94476-185">これは[Docker 独自`registry`のイメージ (Docker](https://docs.docker.com/registry/deploying/)レジストリーは Docker コンテナーで実行される) を実行するのと同じくらい簡単ですが、さまざまなより包括的なソリューションが利用できます。</span><span class="sxs-lookup"><span data-stu-id="94476-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="94476-186">外部共有およびクラウド使用の場合は[、Azure コンテナー レジストリ](https://docs.microsoft.com/azure/container-registry/)や[Docker Hub](https://docs.docker.com/docker-hub/repos/)など、さまざまなマネージ レジストリを利用できます。</span><span class="sxs-lookup"><span data-stu-id="94476-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="94476-187">Docker Hub にプッシュするには、イメージ名の前にユーザー名または組織名を付けます。</span><span class="sxs-lookup"><span data-stu-id="94476-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="94476-188">プライベート レジストリにプッシュするには、イメージ名の前にレジストリ ホスト名と組織名を付けます。</span><span class="sxs-lookup"><span data-stu-id="94476-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="94476-189">イメージがレジストリに格納された後、個々の Docker ホストまたは Kubernetes などのコンテナー オーケストレーション エンジンに展開できます。</span><span class="sxs-lookup"><span data-stu-id="94476-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="94476-190">[前次](self-hosted.md)
>[Next](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="94476-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
