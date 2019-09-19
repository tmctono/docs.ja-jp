---
title: .NET Core のガイド
description: .NET Core は、Windows、Linux、および Mac アプリを作成するためのモジュール型の高性能な .NET 実装です。 ここでは、.NET Core の概要について説明します。
author: richlander
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: a6112851a3d9b46f02c26313e6537170786df10b
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117075"
---
# <a name="net-core-guide"></a><span data-ttu-id="21399-104">.NET Core のガイド</span><span class="sxs-lookup"><span data-stu-id="21399-104">.NET Core Guide</span></span>

<span data-ttu-id="21399-105">[.NET Core](about.md) は、Microsoft および .NET コミュニティによって [GitHub](https://github.com/dotnet/core) 上で管理されている、[オープンソース](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)の汎用的な開発プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="21399-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="21399-106">クロスプラットフォーム (Windows、macOS、Linux をサポート) であり、デバイス、クラウド、および IoT アプリケーションを構築するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="21399-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="21399-107">特徴、サポートされる言語とフレームワーク、キー API など、.NET Core について詳しくは、「[About .NET Core](about.md)」(.NET Core について) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="21399-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="21399-108">「[.NET Core チュートリアル](tutorials/index.md)」では、単純な .NET Core アプリケーションを作成する方法を学習できます。</span><span class="sxs-lookup"><span data-stu-id="21399-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="21399-109">最初のアプリを、ほんの数分で起動および実行できます。</span><span class="sxs-lookup"><span data-stu-id="21399-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="21399-110">ブラウザーで .NET Core を使用してみる場合は、[C# における数値](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)に関するオンライン チュートリアルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="21399-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core-22"></a><span data-ttu-id="21399-111">.NET Core 2.2 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="21399-111">Download .NET Core 2.2</span></span>

<span data-ttu-id="21399-112">[.NET Core  2.2 SDK](https://dotnet.microsoft.com/download) をダウンロードして、Windows、macOS、または Linux マシンで .NET Core をお試しください。</span><span class="sxs-lookup"><span data-stu-id="21399-112">Download the [.NET Core  2.2 SDK](https://dotnet.microsoft.com/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="21399-113">Docker コンテナーを使用する方がよければ、[dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="21399-113">Visit [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) if you prefer to use Docker containers.</span></span>

<span data-ttu-id="21399-114">別の .NET Core バージョンを探している場合も、すべての .NET Core バージョンを [.NET Core のダウンロード](https://dotnet.microsoft.com/download/dotnet-core)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="21399-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-22"></a><span data-ttu-id="21399-115">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="21399-115">.NET Core 2.2</span></span>

<span data-ttu-id="21399-116">最新バージョンは [.NET Core 2.2](whats-new/dotnet-core-2-2.md) です。</span><span class="sxs-lookup"><span data-stu-id="21399-116">The latest version is [.NET Core 2.2](whats-new/dotnet-core-2-2.md).</span></span> <span data-ttu-id="21399-117">新機能には、フレームワーク依存の配置、スタートアップ フック、Azure SQL での AAD 認証、Windows ARM32 のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="21399-117">New features include: framework-dependent deployments, startup hooks, AAD authentication with Azure SQL, and support for Windows ARM32.</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="21399-118">最初のアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="21399-118">Create your first application</span></span>

<span data-ttu-id="21399-119">.NET Core SDK をインストールしたらコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="21399-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="21399-120">次の `dotnet` コマンドを入力し、C# アプリケーションを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="21399-120">Type the following `dotnet` commands to create and run a C# application.</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="21399-121">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21399-121">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="21399-122">サポート</span><span class="sxs-lookup"><span data-stu-id="21399-122">Support</span></span>

<span data-ttu-id="21399-123">.NET Core は、Microsoft Windows、macOS、Linux で[サポート](https://dotnet.microsoft.com/platform/support/policy)されています。</span><span class="sxs-lookup"><span data-stu-id="21399-123">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS and Linux.</span></span> <span data-ttu-id="21399-124">年に数回、通常は毎月、セキュリティと品質向上のために更新されます。</span><span class="sxs-lookup"><span data-stu-id="21399-124">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="21399-125">.NET Core のバイナリ形式の配布は、Azure 内のマイクロソフトが管理するサーバーで構築されてテストされ、他のすべてのマイクロソフト製品と同様にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="21399-125">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="21399-126">Red Hat Enterprise Linux (RHEL) では [.NET Core は Red Hat によってサポート](http://redhatloves.net/)されます。</span><span class="sxs-lookup"><span data-stu-id="21399-126">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="21399-127">Red Hat がソースから .NET Core をビルドして、[Red Hat ソフトウェア コレクション](https://developers.redhat.com/products/softwarecollections/overview/)で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="21399-127">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="21399-128">Red Hat とマイクロソフトが共同して、.NET Core が RHEL 上で適切に動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="21399-128">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
