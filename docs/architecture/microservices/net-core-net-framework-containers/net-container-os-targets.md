---
title: .NET コンテナーで対象とする OS
description: '.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ | .NET コンテナーで対象とする OS'
ms.date: 01/07/2019
ms.openlocfilehash: 8bcfa0212f84c575a63f76e05edec1e511cadc36
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72772003"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="20de0-103">.NET コンテナーで対象とする OS</span><span class="sxs-lookup"><span data-stu-id="20de0-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="20de0-104">Docker でサポートされているオペレーティング システムの多様性と、.NET Framework と .NET Core の違いを考慮し、使用しているフレームワークに応じて特定の OS と特定のバージョンを対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20de0-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="20de0-105">Windows の場合、Windows Server Core または Windows Nano Server を使用できます。</span><span class="sxs-lookup"><span data-stu-id="20de0-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="20de0-106">これらの Windows バージョンには、.NET Framework または .NET Core で必要になる可能性がある異なる特性 (Windows Server Core の IIS と Nest Server の Kestrel のような自己ホスト型 Web サーバー) があります。</span><span class="sxs-lookup"><span data-stu-id="20de0-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="20de0-107">Linux の場合、複数のディストリビューションを利用できます。また、Linux は公式の .NET Docker イメージ (Debian など) でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="20de0-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="20de0-108">使用している .NET Framework に応じて使用できる OS のバージョンについては、図 3-1 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20de0-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![.NET Framework のレガシー アプリケーションをデプロイする場合は、レガシー アプリと IIS と互換性があり、大きなイメージを持っている Windows Server Core をターゲットにする必要があります。](./media/image1.png)

<span data-ttu-id="20de0-113">**図 3-1.**</span><span class="sxs-lookup"><span data-stu-id="20de0-113">**Figure 3-1.**</span></span> <span data-ttu-id="20de0-114">.NET Framework のバージョンに応じて対象にすることができるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="20de0-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="20de0-115">別の Linux ディストリビューションを使用したい場合や、Microsoft が提供していないバージョンのイメージが必要な場合は、独自の Docker イメージを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="20de0-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="20de0-116">たとえば、従来の .NET Framework と Windows Server Core 上で実行されている ASP.NET Core を使用してイメージを作成することができます (ただし、Docker の場合はあまり一般的ではないシナリオです)。</span><span class="sxs-lookup"><span data-stu-id="20de0-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20de0-117">Windows Server Core イメージを使用する場合、完全な Windows イメージと比較すると、一部の DLL が不足している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20de0-117">When using Windows Server Core images, you might find that some DLLs are missing, when compared to full Windows images.</span></span> <span data-ttu-id="20de0-118">この [GitHub コメント](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448)に記載されているように、カスタムの Server Core イメージを作成し、不足しているファイルをイメージのビルド時に追加することで、この問題を解決できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="20de0-118">You might be able to solve this problem by creating a custom Server Core image, adding the missing files at image build time, as mentioned in this [GitHub comment](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).</span></span>

<span data-ttu-id="20de0-119">Dockerfile ファイルにイメージ名を追加すると、次の例のように、使用するタグに応じてオペレーティング システムとバージョンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="20de0-119">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

| <span data-ttu-id="20de0-120">イメージ</span><span class="sxs-lookup"><span data-stu-id="20de0-120">Image</span></span> | <span data-ttu-id="20de0-121">コメント</span><span class="sxs-lookup"><span data-stu-id="20de0-121">Comments</span></span> |
|-------|----------|
| <span data-ttu-id="20de0-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span><span class="sxs-lookup"><span data-stu-id="20de0-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span></span> | <span data-ttu-id="20de0-123">.NET Core 2.2 マルチアーキテクチャ:Docker ホストに応じて、Linux と Windows Nano Server をサポートします。</span><span class="sxs-lookup"><span data-stu-id="20de0-123">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> |
| <span data-ttu-id="20de0-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span><span class="sxs-lookup"><span data-stu-id="20de0-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span></span> | <span data-ttu-id="20de0-125">ASP.NET Core 2.2 マルチアーキテクチャ:Docker ホストに応じて、Linux と Windows Nano Server をサポートします。</span><span class="sxs-lookup"><span data-stu-id="20de0-125">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> <br/> <span data-ttu-id="20de0-126">aspnetcore イメージでは、ASP.NET Core 用に 少しの最適化が行われています。</span><span class="sxs-lookup"><span data-stu-id="20de0-126">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span> |
| <span data-ttu-id="20de0-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span><span class="sxs-lookup"><span data-stu-id="20de0-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span></span> | <span data-ttu-id="20de0-128">Linux Alpine ディストリビューションでの .NET Core 2.2 ランタイムのみ</span><span class="sxs-lookup"><span data-stu-id="20de0-128">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span> |
| <span data-ttu-id="20de0-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="20de0-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span></span> | <span data-ttu-id="20de0-130">Windows Nano Server (Windows Server バージョン 1803) では .NET Core 2.2 ランタイムのみ</span><span class="sxs-lookup"><span data-stu-id="20de0-130">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="20de0-131">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="20de0-131">Additional resources</span></span>

- <span data-ttu-id="20de0-132">**WindowsCodecsExt.dll が見つからないため、BitmapDecoder が失敗する (GitHub の問題)**</span><span class="sxs-lookup"><span data-stu-id="20de0-132">**BitmapDecoder fails due to missing WindowsCodecsExt.dll (GitHub issue)**</span></span>  
  <https://github.com/microsoft/dotnet-framework-docker/issues/299>

> [!div class="step-by-step"]
> <span data-ttu-id="20de0-133">[前へ](container-framework-choice-factors.md)
> [次へ](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="20de0-133">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
