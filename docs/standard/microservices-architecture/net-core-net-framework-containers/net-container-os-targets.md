---
title: .NET コンテナーで対象とする OS
description: '.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ | .NET コンテナーで対象とする OS'
ms.date: 01/07/2019
ms.openlocfilehash: 6f160aeba5257722490788271e6f89359342cc0d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639079"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="b5bcc-103">.NET コンテナーで対象とする OS</span><span class="sxs-lookup"><span data-stu-id="b5bcc-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="b5bcc-104">Docker でサポートされているオペレーティング システムの多様性と、.NET Framework と .NET Core の違いを考慮し、使用しているフレームワークに応じて特定の OS と特定のバージョンを対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="b5bcc-105">Windows の場合、Windows Server Core または Windows Nano Server を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="b5bcc-106">これらの Windows バージョンには、.NET Framework または .NET Core で必要になる可能性がある異なる特性 (Windows Server Core の IIS と Nest Server の Kestrel のような自己ホスト型 Web サーバー) があります。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="b5bcc-107">Linux の場合、複数のディストリビューションを利用できます。また、Linux は公式の .NET Docker イメージ (Debian など) でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="b5bcc-108">使用している .NET Framework に応じて使用できる OS のバージョンについては、図 3-1 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![.NET Framework のレガシー アプリケーションをデプロイする場合は、レガシー アプリと IIS と互換性があり、大きなイメージを持っている Windows Server Core をターゲットにする必要があります。](./media/image1.png)

<span data-ttu-id="b5bcc-113">**図 3-1.**</span><span class="sxs-lookup"><span data-stu-id="b5bcc-113">**Figure 3-1.**</span></span> <span data-ttu-id="b5bcc-114">.NET Framework のバージョンに応じて対象にすることができるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b5bcc-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="b5bcc-115">別の Linux ディストリビューションを使用したい場合や、Microsoft が提供していないバージョンのイメージが必要な場合は、独自の Docker イメージを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="b5bcc-116">たとえば、従来の .NET Framework と Windows Server Core 上で実行されている ASP.NET Core を使用してイメージを作成することができます (ただし、Docker の場合はあまり一般的ではないシナリオです)。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="b5bcc-117">Dockerfile ファイルにイメージ名を追加すると、次の例のように、使用するタグに応じてオペレーティング システムとバージョンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-117">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b5bcc-118">イメージ</span><span class="sxs-lookup"><span data-stu-id="b5bcc-118">Image</span></span></th>
<th><span data-ttu-id="b5bcc-119">コメント</span><span class="sxs-lookup"><span data-stu-id="b5bcc-119">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b5bcc-120">mcr.microsoft.com/dotnet/core/runtime:2.2</span><span class="sxs-lookup"><span data-stu-id="b5bcc-120">mcr.microsoft.com/dotnet/core/runtime:2.2</span></span></td>
<td><span data-ttu-id="b5bcc-121">.NET Core 2.2 マルチアーキテクチャ:Docker ホストに応じて、Linux と Windows Nano Server をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-121">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b5bcc-122">mcr.microsoft.com/dotnet/core/aspnet:2.2</span><span class="sxs-lookup"><span data-stu-id="b5bcc-122">mcr.microsoft.com/dotnet/core/aspnet:2.2</span></span></td>
<td><p><span data-ttu-id="b5bcc-123">ASP.NET Core 2.2 マルチアーキテクチャ:Docker ホストに応じて、Linux と Windows Nano Server をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-123">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></p>
<p><span data-ttu-id="b5bcc-124">aspnetcore イメージでは、ASP.NET Core 用に 少しの最適化が行われています。</span><span class="sxs-lookup"><span data-stu-id="b5bcc-124">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b5bcc-125">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span><span class="sxs-lookup"><span data-stu-id="b5bcc-125">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span></span></td>
<td><span data-ttu-id="b5bcc-126">Linux Alpine ディストリビューションでの .NET Core 2.2 ランタイムのみ</span><span class="sxs-lookup"><span data-stu-id="b5bcc-126">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b5bcc-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="b5bcc-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span></span></td>
<td><span data-ttu-id="b5bcc-128">Windows Nano Server (Windows Server バージョン 1803) では .NET Core 2.2 ランタイムのみ</span><span class="sxs-lookup"><span data-stu-id="b5bcc-128">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span></td>
</tr>
</tbody>
</table>

> [!div class="step-by-step"]
> <span data-ttu-id="b5bcc-129">[前へ](container-framework-choice-factors.md)
> [次へ](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="b5bcc-129">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
