---
title: WCF 開発者向け Docker-gRPC
description: ASP.NET Core gRPC アプリケーション用の Docker イメージの作成
ms.date: 09/02/2019
ms.openlocfilehash: a5aceb4b5270cb828965e990a62db4147012adff
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967837"
---
# <a name="docker"></a><span data-ttu-id="b1967-103">Docker</span><span class="sxs-lookup"><span data-stu-id="b1967-103">Docker</span></span>

<span data-ttu-id="b1967-104">このセクションでは ASP.NET Core gRPC アプリケーション用の Docker イメージの作成について説明し、Docker、Kubernetes、またはその他のコンテナー環境で実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b1967-104">This section will cover the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="b1967-105">ASP.NET Core MVC web アプリおよび gRPC サービスと共に使用されるサンプルアプリケーションは、GitHub の[dotnet/grpc-wcf 開発者](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample)リポジトリで入手できます。</span><span class="sxs-lookup"><span data-stu-id="b1967-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="b1967-106">ASP.NET Core アプリケーション用の Microsoft 基本イメージ</span><span class="sxs-lookup"><span data-stu-id="b1967-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="b1967-107">Microsoft では、.NET Core アプリケーションをビルドして実行するためのさまざまな基本イメージを提供しています。</span><span class="sxs-lookup"><span data-stu-id="b1967-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="b1967-108">ASP.NET Core 3.0 イメージを作成するには、アプリケーションをビルドして発行するための SDK イメージと配置用のランタイムイメージという2つの基本イメージが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1967-108">To create an ASP.NET Core 3.0 image, two base images are used: an SDK image to build and publish the application, and a runtime image for deployment.</span></span>

| <span data-ttu-id="b1967-109">イメージ</span><span class="sxs-lookup"><span data-stu-id="b1967-109">Image</span></span> | <span data-ttu-id="b1967-110">説明</span><span class="sxs-lookup"><span data-stu-id="b1967-110">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="b1967-111">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="b1967-111">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="b1967-112">`docker build`を使用してアプリケーションをビルドする場合。</span><span class="sxs-lookup"><span data-stu-id="b1967-112">For building applications with `docker build`.</span></span> <span data-ttu-id="b1967-113">運用環境では使用されません。</span><span class="sxs-lookup"><span data-stu-id="b1967-113">Not to be used in production.</span></span> |
| [<span data-ttu-id="b1967-114">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="b1967-114">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="b1967-115">ランタイムと ASP.NET Core の依存関係を含みます。</span><span class="sxs-lookup"><span data-stu-id="b1967-115">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="b1967-116">運用環境の場合。</span><span class="sxs-lookup"><span data-stu-id="b1967-116">For production.</span></span> |

<span data-ttu-id="b1967-117">各イメージには、タグによって識別される、異なる Linux ディストリビューションに基づく4つのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="b1967-117">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="b1967-118">イメージタグ</span><span class="sxs-lookup"><span data-stu-id="b1967-118">Image tag(s)</span></span> | <span data-ttu-id="b1967-119">Linux</span><span class="sxs-lookup"><span data-stu-id="b1967-119">Linux</span></span> | <span data-ttu-id="b1967-120">説明</span><span class="sxs-lookup"><span data-stu-id="b1967-120">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="b1967-121">3.0-buster、3.0</span><span class="sxs-lookup"><span data-stu-id="b1967-121">3.0-buster, 3.0</span></span> | <span data-ttu-id="b1967-122">Debian 10</span><span class="sxs-lookup"><span data-stu-id="b1967-122">Debian 10</span></span> | <span data-ttu-id="b1967-123">OS バリアントが指定されていない場合の既定のイメージ。</span><span class="sxs-lookup"><span data-stu-id="b1967-123">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="b1967-124">3.0-アルペン</span><span class="sxs-lookup"><span data-stu-id="b1967-124">3.0-alpine</span></span> | <span data-ttu-id="b1967-125">Alpine 3.9</span><span class="sxs-lookup"><span data-stu-id="b1967-125">Alpine 3.9</span></span> | <span data-ttu-id="b1967-126">Alpine base イメージは Debian または Ubuntu よりもはるかに小さいものです。</span><span class="sxs-lookup"><span data-stu-id="b1967-126">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="b1967-127">3.0-disco</span><span class="sxs-lookup"><span data-stu-id="b1967-127">3.0-disco</span></span> | <span data-ttu-id="b1967-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="b1967-128">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="b1967-129">3.0-bionic</span><span class="sxs-lookup"><span data-stu-id="b1967-129">3.0-bionic</span></span> | <span data-ttu-id="b1967-130">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="b1967-130">Ubuntu 18.04</span></span> | |

<span data-ttu-id="b1967-131">Alpine base イメージは約 100 MB であり、Debian および Ubuntu イメージでは 200 MB と比較していますが、一部のソフトウェアパッケージまたはライブラリは Alpine のパッケージ管理では利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1967-131">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images, but some software packages or libraries may not be available in Alpine's package management.</span></span> <span data-ttu-id="b1967-132">使用するイメージがわからない場合は、別のディストリビューションを使用する必要がある場合を除き、既定の Debian にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1967-132">If you're not sure which image to use, it's best to stick to the default Debian unless you have a compelling need to use a different distro.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1967-133">ビルドとランタイムに同じ形式の Linux を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1967-133">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="b1967-134">あるバリアントでビルドおよび発行されたアプリケーションは、別のバリアントでは機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1967-134">Applications built and published on one variant may not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="b1967-135">Docker イメージを作成する</span><span class="sxs-lookup"><span data-stu-id="b1967-135">Create a Docker image</span></span>

<span data-ttu-id="b1967-136">Docker イメージは、 *Dockerfile*(アプリケーションのビルドに必要なすべてのコマンドを含むテキストファイル) と、アプリケーションをビルドまたは実行するために必要な依存関係をインストールするために定義されます。</span><span class="sxs-lookup"><span data-stu-id="b1967-136">A Docker image is defined by a *Dockerfile*, a text file that contains all the commands that are needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="b1967-137">次の例は、ASP.NET Core 3.0 アプリケーションの最も単純な Dockerfile を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1967-137">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

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

<span data-ttu-id="b1967-138">Dockerfile は2つの部分で構成されています。最初の部分では、アプリケーションをビルドして発行するために `sdk` 基本イメージを使用します。2つ目は、`aspnet` ベースからランタイムイメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1967-138">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="b1967-139">これは、`sdk` のイメージは、ランタイムイメージの約 200 MB と比較して約 900 MB であり、その内容のほとんどは実行時には不要であるためです。</span><span class="sxs-lookup"><span data-stu-id="b1967-139">This is because the `sdk` image is around 900 MB compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="b1967-140">ビルドステップ</span><span class="sxs-lookup"><span data-stu-id="b1967-140">The build steps</span></span>

| <span data-ttu-id="b1967-141">手順</span><span class="sxs-lookup"><span data-stu-id="b1967-141">Step</span></span> | <span data-ttu-id="b1967-142">説明</span><span class="sxs-lookup"><span data-stu-id="b1967-142">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="b1967-143">基本イメージを宣言し、`builder` エイリアスを割り当てます (説明については、次のセクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b1967-143">Declares the base image and assigns the `builder` alias (see next section for explanation).</span></span> |
| `WORKDIR /src` | <span data-ttu-id="b1967-144">`/src` ディレクトリを作成し、現在の作業ディレクトリとして設定します。</span><span class="sxs-lookup"><span data-stu-id="b1967-144">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="b1967-145">ホスト上の現在のディレクトリの下にあるものをすべて、イメージの現在のディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b1967-145">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="b1967-146">外部パッケージを復元します (ASP.NET Core 3.0 framework は SDK と共にプレインストールされています)。</span><span class="sxs-lookup"><span data-stu-id="b1967-146">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="b1967-147">リリースビルドをビルドして発行します。</span><span class="sxs-lookup"><span data-stu-id="b1967-147">Builds and publishes a Release build.</span></span> <span data-ttu-id="b1967-148">`--runtime` フラグは必須ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b1967-148">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="b1967-149">ランタイムイメージの手順</span><span class="sxs-lookup"><span data-stu-id="b1967-149">The runtime image steps</span></span>

| <span data-ttu-id="b1967-150">手順</span><span class="sxs-lookup"><span data-stu-id="b1967-150">Step</span></span> | <span data-ttu-id="b1967-151">説明</span><span class="sxs-lookup"><span data-stu-id="b1967-151">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="b1967-152">新しい基本イメージを宣言します。</span><span class="sxs-lookup"><span data-stu-id="b1967-152">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="b1967-153">`/app` ディレクトリを作成し、現在の作業ディレクトリとして設定します。</span><span class="sxs-lookup"><span data-stu-id="b1967-153">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="b1967-154">最初の `FROM` 行の `builder` エイリアスを使用して、発行されたアプリケーションを前のイメージからコピーします。</span><span class="sxs-lookup"><span data-stu-id="b1967-154">Copies the published application from the previous image, using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="b1967-155">コンテナーの起動時に実行するコマンドを設定します。</span><span class="sxs-lookup"><span data-stu-id="b1967-155">Sets the command to run when the container starts.</span></span> <span data-ttu-id="b1967-156">ランタイムイメージの `dotnet` コマンドは、DLL ファイルのみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1967-156">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="b1967-157">Docker での HTTPS</span><span class="sxs-lookup"><span data-stu-id="b1967-157">HTTPS in Docker</span></span>

<span data-ttu-id="b1967-158">Docker 用の Microsoft の基本イメージは、`ASPNETCORE_URLS` 環境変数を `http://+:80`に設定します。これは、Kestrel がそのポートで HTTPS を使用せずに実行されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b1967-158">Microsoft's base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel will run without HTTPS on that port.</span></span> <span data-ttu-id="b1967-159">([前のセクション](self-hosted.md)で説明したように) カスタム証明書と共に HTTPS を使用している場合は、Dockerfile の**ランタイムイメージ作成部分で**環境変数を設定することにより、これをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1967-159">If you're using HTTPS with a custom certificate (as described in [the previous section](self-hosted.md)), you should override this by setting the environment variable **in the runtime image creation part** of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="b1967-160">Dockerignore ファイル</span><span class="sxs-lookup"><span data-stu-id="b1967-160">The .dockerignore file</span></span>

<span data-ttu-id="b1967-161">ソース管理から特定のファイルやディレクトリを除外する `.gitignore` ファイルと同様に、`.dockerignore` ファイルを使用して、ビルド時にファイルやディレクトリをイメージにコピーしないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b1967-161">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="b1967-162">これにより、コピー時間が短縮されるだけでなく、PC からの `obj` ディレクトリがイメージにコピーされたことによって発生する混乱したエラーを回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1967-162">This not only saves time copying, but can also avoid some confusing errors that arise from having (particularly) the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="b1967-163">少なくとも `bin` のエントリを追加し、`.dockerignore` ファイルに `obj` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1967-163">You should add at least entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="b1967-164">イメージのビルド</span><span class="sxs-lookup"><span data-stu-id="b1967-164">Build the image</span></span>

<span data-ttu-id="b1967-165">単一のアプリケーションと1つの Dockerfile を持つソリューションでは、Dockerfile を基本ディレクトリに配置するのが最も簡単です。つまり、`.sln` ファイルと同じディレクトリになります。</span><span class="sxs-lookup"><span data-stu-id="b1967-165">For a solution with a single application, and thus a single Dockerfile, it is simplest to put the Dockerfile in the base directory; that is, the same directory as the `.sln` file.</span></span> <span data-ttu-id="b1967-166">その場合は、イメージをビルドするために、Dockerfile が格納されているディレクトリから次の `docker build` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1967-166">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="b1967-167">紛らわしいという名前の `--tag` フラグ (`-t`に短縮できます) は、指定されている場合は、実際のタグを*含む*イメージの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1967-167">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, *including* the actual tag if specified.</span></span> <span data-ttu-id="b1967-168">最後の `.` は、ビルドが実行される*コンテキスト*を指定します。Dockerfile 内の `COPY` コマンドの現在の作業ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="b1967-168">The `.` at the end specifies the *context* in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="b1967-169">1つのソリューション内に複数のアプリケーションがある場合は、各アプリケーションの Dockerfile を `.csproj` ファイルの隣にある独自のフォルダーに保持できますが、ソリューションとすべてのプロジェクトがイメージにコピーされるようにするには、ベースディレクトリから `docker build` コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1967-169">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file, but you should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="b1967-170">`--file` (または `-f`) フラグを使用して、現在のディレクトリの下に Dockerfile を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b1967-170">You can specify a Dockerfile below the current directory using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="b1967-171">コンピューターのコンテナーでイメージを実行する</span><span class="sxs-lookup"><span data-stu-id="b1967-171">Run the image in a container on your machine</span></span>

<span data-ttu-id="b1967-172">ローカルの Docker インスタンスでイメージを実行するには、`docker run` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1967-172">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="b1967-173">`-ti` フラグは、現在のターミナルをコンテナーのターミナルに接続し、対話モードで実行します。</span><span class="sxs-lookup"><span data-stu-id="b1967-173">The `-ti` flag connects your current terminal to the container's terminal and runs in interactive mode.</span></span> <span data-ttu-id="b1967-174">`-p 5000:80` は、コンテナー上のポート80を localhost ネットワークインターフェイスのポート80に発行 (リンク) します。</span><span class="sxs-lookup"><span data-stu-id="b1967-174">The `-p 5000:80` publishes (links) port 80 on the container to port 80 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="b1967-175">レジストリにイメージをプッシュする</span><span class="sxs-lookup"><span data-stu-id="b1967-175">Push the image to a registry</span></span>

<span data-ttu-id="b1967-176">イメージが動作することを確認したら、それを Docker レジストリにプッシュして、他のシステムで使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1967-176">Once you've verified that the image works, you need to push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="b1967-177">内部ネットワークでは、Docker レジストリをプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1967-177">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="b1967-178">これは、 [docker 独自の `registry` イメージ](https://docs.docker.com/registry/deploying/)(つまり、docker レジストリは docker コンテナーで実行されます) を実行するのと同じように簡単ですが、さまざまな包括的なソリューションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b1967-178">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (that's right, the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="b1967-179">外部共有とクラウド使用については、 [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/)や[Docker Hub](https://docs.docker.com/docker-hub/repos/)などのさまざまな管理対象レジストリを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b1967-179">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="b1967-180">Docker Hub にプッシュするには、イメージ名の前にユーザー名または組織名を付けます。</span><span class="sxs-lookup"><span data-stu-id="b1967-180">To push to the Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="b1967-181">プライベートレジストリにプッシュするには、イメージ名の前にレジストリのホスト名と組織名を付けます。</span><span class="sxs-lookup"><span data-stu-id="b1967-181">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="b1967-182">イメージがレジストリに登録されたら、それを個々の Docker ホストまたは Kubernetes のようなコンテナーオーケストレーションエンジンに展開できます。</span><span class="sxs-lookup"><span data-stu-id="b1967-182">Once the image is in a registry, you can deploy it to individual Docker hosts or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b1967-183">[前へ](self-hosted.md)
>[次へ](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="b1967-183">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
