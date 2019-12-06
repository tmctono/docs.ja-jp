---
title: .NET Core のガイド
description: .NET Core は、Windows、Linux、および Mac アプリを作成するためのモジュール型の高性能な .NET 実装です。 ここでは、.NET Core の概要について説明します。
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: b2622dba53d64c9dcf58e852d57de117fe79eb2e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837013"
---
# <a name="net-core-guide"></a><span data-ttu-id="c722f-104">.NET Core のガイド</span><span class="sxs-lookup"><span data-stu-id="c722f-104">.NET Core Guide</span></span>

<span data-ttu-id="c722f-105">[.NET Core](about.md) は、Microsoft および .NET コミュニティによって [GitHub](https://github.com/dotnet/core) 上で管理されている、[オープンソース](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)の汎用的な開発プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="c722f-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="c722f-106">クロスプラットフォーム (Windows、macOS、Linux をサポート) であり、デバイス、クラウド、および IoT アプリケーションを構築するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c722f-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="c722f-107">特徴、サポートされる言語とフレームワーク、キー API など、.NET Core について詳しくは、「[.NET Core について](about.md)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c722f-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="c722f-108">「[.NET Core チュートリアル](tutorials/index.md)」では、単純な .NET Core アプリケーションを作成する方法を学習できます。</span><span class="sxs-lookup"><span data-stu-id="c722f-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="c722f-109">最初のアプリを、ほんの数分で起動および実行できます。</span><span class="sxs-lookup"><span data-stu-id="c722f-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="c722f-110">ブラウザーで .NET Core を使用してみる場合は、[C# における数値](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)に関するオンライン チュートリアルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c722f-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="c722f-111">.NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="c722f-111">Download .NET Core</span></span>

<span data-ttu-id="c722f-112">[.NET Core SDK](https://www.microsoft.com/net/download) をダウンロードして、お使いの Windows、macOS、または Linux コンピューター上で .NET Core をお試しください。</span><span class="sxs-lookup"><span data-stu-id="c722f-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="c722f-113">また、Docker コンテナーを使用する場合は、[.NET Core の Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="c722f-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="c722f-114">別の .NET Core バージョンを探している場合も、すべての .NET Core バージョンを [.NET Core のダウンロード](https://dotnet.microsoft.com/download/dotnet-core)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="c722f-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-31"></a><span data-ttu-id="c722f-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c722f-115">.NET Core 3.1</span></span>

<span data-ttu-id="c722f-116">最新バージョンは .NET Core 3.1 です。</span><span class="sxs-lookup"><span data-stu-id="c722f-116">The latest version is .NET Core 3.1.</span></span> <span data-ttu-id="c722f-117">.NET Core 3.0 に対する軽微な機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c722f-117">Which includes minor improvements over .NET Core 3.0.</span></span> <span data-ttu-id="c722f-118">ただし、.NET Core 3.1 は長期的にサポートされるリリースです。</span><span class="sxs-lookup"><span data-stu-id="c722f-118">However, .NET Core 3.1 is a long-term supported release.</span></span> <span data-ttu-id="c722f-119">.NET Core 3.1 リリースの詳細については、[.NET Core 3.1 の新機能](./whats-new/dotnet-core-3-1.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c722f-119">For more information about the .NET Core 3.1 release, see [What's new in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="c722f-120">最初のアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="c722f-120">Create your first application</span></span>

<span data-ttu-id="c722f-121">.NET Core SDK をインストールしたらコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c722f-121">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="c722f-122">次の `dotnet` コマンドを入力し、C# アプリケーションを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="c722f-122">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="c722f-123">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c722f-123">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="c722f-124">サポート</span><span class="sxs-lookup"><span data-stu-id="c722f-124">Support</span></span>

<span data-ttu-id="c722f-125">.NET Core は、[Microsoft によって](https://dotnet.microsoft.com/platform/support/policy)、Windows、macOS、Linux 上でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c722f-125">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="c722f-126">年に数回、通常は毎月、セキュリティと品質向上のために更新されます。</span><span class="sxs-lookup"><span data-stu-id="c722f-126">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="c722f-127">.NET Core のバイナリ形式の配布は、Azure 内のマイクロソフトが管理するサーバーで構築されてテストされ、他のすべてのマイクロソフト製品と同様にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c722f-127">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="c722f-128">Red Hat Enterprise Linux (RHEL) では [.NET Core は Red Hat によってサポート](http://redhatloves.net/)されます。</span><span class="sxs-lookup"><span data-stu-id="c722f-128">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="c722f-129">Red Hat がソースから .NET Core をビルドして、[Red Hat ソフトウェア コレクション](https://developers.redhat.com/products/softwarecollections/overview/)で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c722f-129">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="c722f-130">Red Hat とマイクロソフトが共同して、.NET Core が RHEL 上で適切に動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="c722f-130">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
