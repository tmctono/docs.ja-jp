---
title: チュートリアルと技術的な概要
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |チュートリアルと技術入門概要
ms.date: 04/28/2018
ms.openlocfilehash: 190b33c4307b09bab0543d481e66ac9328074a0d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660884"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="c4df3-103">チュートリアルと技術的な概要</span><span class="sxs-lookup"><span data-stu-id="c4df3-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="c4df3-104">この電子書籍のサイズを制限するために、追加の技術ドキュメントと完全なチュートリアルは、GitHub リポジトリで入手できました。</span><span class="sxs-lookup"><span data-stu-id="c4df3-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="c4df3-105">この章で説明しているオンラインの一連のチュートリアルでは、Windows コンテナーに基づく複数の環境と Azure へのデプロイに関するステップバイステップのセットアップについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="c4df3-106">次のセクションでは、各チュートリアルの内容、その目的、および高度なビジョンについて説明し、関連するタスクの図を示します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="c4df3-107">チュートリアルは、「」の*eShopModernizing* apps GitHub リポジトリ wiki <https://github.com/dotnet-architecture/eShopModernizing/wiki>で入手できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="c4df3-108">技術的なチュートリアルの一覧</span><span class="sxs-lookup"><span data-stu-id="c4df3-108">Technical walkthrough list</span></span>

<span data-ttu-id="c4df3-109">次の入門チュートリアルでは、コンテナーを使用してリフトアンドシフトできるサンプルアプリについて、一貫性のある包括的な技術ガイダンスを提供し、Azure での複数のデプロイの選択肢を使用して移動することができます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="c4df3-110">次の各チュートリアルでは、GitHub <https://github.com/dotnet-architecture/eShopModernizing>ので入手できる新しいサンプル eShopLegacy と eShopModernizing アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="c4df3-111">**EShop レガシアプリのツアー (最新化するベースラインアプリ)**</span><span class="sxs-lookup"><span data-stu-id="c4df3-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="c4df3-112">**Windows コンテナーを使用した既存の ASP.NET web アプリ (WebForms & MVC) のコンテナー化**</span><span class="sxs-lookup"><span data-stu-id="c4df3-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="c4df3-113">**Windows コンテナーを使用した既存の WCF サービス (N 層アプリ) のコンテナー化**</span><span class="sxs-lookup"><span data-stu-id="c4df3-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="c4df3-114">**Windows コンテナーベースのアプリを Azure Vm にデプロイする**</span><span class="sxs-lookup"><span data-stu-id="c4df3-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="c4df3-115">**Windows コンテナーベースのアプリを Azure Container Service の Kubernetes に展開する**</span><span class="sxs-lookup"><span data-stu-id="c4df3-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="c4df3-116">チュートリアル 1:EShop レガシアプリのツアー</span><span class="sxs-lookup"><span data-stu-id="c4df3-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c4df3-117">テクニカルチュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="c4df3-117">Technical walkthrough availability</span></span>

<span data-ttu-id="c4df3-118">完全な技術チュートリアルについては、eShopModernizing GitHub リポジトリ wiki を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4df3-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="c4df3-119">eShopModernizing wiki のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="c4df3-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="c4df3-120">概要</span><span class="sxs-lookup"><span data-stu-id="c4df3-120">Overview</span></span>

<span data-ttu-id="c4df3-121">このチュートリアルでは、3つのサンプルレガシアプリケーションの初期実装について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="c4df3-122">最初の2つのサンプル web アプリはモノリシックアーキテクチャを備えており、従来の ASP.NET を使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="c4df3-123">1つのアプリケーションは ASP.NET 4.x MVC に基づいています。2番目のアプリケーションは、ASP.NET 4.x Web フォームに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="c4df3-124">3番目のアプリケーションは、クライアント WinForms アプリとサーバー側[Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md)サービスによって構成される3層アプリです。</span><span class="sxs-lookup"><span data-stu-id="c4df3-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="c4df3-125">これらのアプリケーションはすべて、 [EShopModernizing GitHub リポジトリ](https://github.com/dotnet-architecture/eShopModernizing)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="c4df3-126">目標</span><span class="sxs-lookup"><span data-stu-id="c4df3-126">Goals</span></span>

<span data-ttu-id="c4df3-127">このチュートリアルの主な目的は、これらのアプリとそのコードと構成をよく理解することです。</span><span class="sxs-lookup"><span data-stu-id="c4df3-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="c4df3-128">テスト目的で、SQL database を使用せずに、モックデータを生成して使用するようにアプリを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="c4df3-129">このオプションの構成は、分離された方法で依存関係の挿入に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="c4df3-130">シナリオ 1:ASP.NET Web apps</span><span class="sxs-lookup"><span data-stu-id="c4df3-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="c4df3-131">次の図は、元のレガシ ASP.NET web アプリケーションの単純なシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![元のレガシ ASP.NET web アプリケーションの単純なアーキテクチャシナリオ](./media/image5-1.png)

<span data-ttu-id="c4df3-133">ビジネスドメインの観点から見ると、どちらのアプリも同じカタログ管理機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="c4df3-134">EShop enterprise チームのメンバーは、アプリを使用して、製品カタログを表示および編集します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="c4df3-135">次の図は、最初のアプリのスクリーンショットを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-135">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC と ASP.NET Web フォームアプリケーション (既存/レガシテクノロジ)](./media/image5-2.png)

<span data-ttu-id="c4df3-137">ASP.NET 4.x またはそれ以前のバージョンの依存関係 (MVC の場合または Web フォームの場合) は、ASP.NET Core MVC を使用してコードを完全に書き直す場合を除き、これらのアプリケーションが .NET Core で実行されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="c4df3-138">例 2:WCF サービスと WinForms クライアントアプリ (3 層アプリ)</span><span class="sxs-lookup"><span data-stu-id="c4df3-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="c4df3-139">次の図は、元の3層レガシアプリケーションの単純なシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![WCF サービスと WinForms クライアントアプリを使用した、元の従来の3層アプリのシンプルなアーキテクチャシナリオ](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="c4df3-141">利点</span><span class="sxs-lookup"><span data-stu-id="c4df3-141">Benefits</span></span>

<span data-ttu-id="c4df3-142">このチュートリアルの利点は単純です。コードと初期アプリについて理解を深めましょう。</span><span class="sxs-lookup"><span data-stu-id="c4df3-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="c4df3-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="c4df3-143">Next steps</span></span>

<span data-ttu-id="c4df3-144">このコンテンツについて詳しくは、GitHub wiki をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4df3-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="c4df3-145">ベースライン ASP.NET MVC と Web フォームの "レガシ" アプリに関するツアー</span><span class="sxs-lookup"><span data-stu-id="c4df3-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="c4df3-146">ベースライン WCF サービスと WinForms (3 層) "従来の" アプリのツアー</span><span class="sxs-lookup"><span data-stu-id="c4df3-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="c4df3-147">チュートリアル 2:既存の .NET アプリケーションを Windows コンテナーにコンテナー化</span><span class="sxs-lookup"><span data-stu-id="c4df3-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="c4df3-148">概要</span><span class="sxs-lookup"><span data-stu-id="c4df3-148">Overview</span></span>

<span data-ttu-id="c4df3-149">Windows コンテナーを使用すると、MVC、Web フォーム、WCF などの既存の .NET アプリケーションを、運用環境、開発環境、およびテスト環境に展開しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c4df3-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="c4df3-150">目標</span><span class="sxs-lookup"><span data-stu-id="c4df3-150">Goals</span></span>

<span data-ttu-id="c4df3-151">このチュートリアルの目的は、既存の .NET Framework アプリケーションをコンテナー化するためのいくつかのオプションについて説明することです。</span><span class="sxs-lookup"><span data-stu-id="c4df3-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="c4df3-152">次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-152">You can:</span></span>

- <span data-ttu-id="c4df3-153">[Visual studio 2017 Tools For Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (visual studio 2017 またはそれ以降のバージョン) を使用してアプリケーションをコンテナー化します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="c4df3-154">手動で[Dockerfile](https://docs.docker.com/engine/reference/builder/)を追加し、 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)を使用して、アプリケーションをコンテナー化します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="c4df3-155">[Img2Docker](https://github.com/docker/communitytools-image2docker-win)ツール (Docker からオープンソースツール) を使用して、アプリケーションをコンテナー化します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="c4df3-156">このチュートリアルでは、Visual Studio 2017 Tools for Docker アプローチに焦点を当てていますが、Dockerfiles の使用に関しては、他の2つの方法は非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="c4df3-157">シナリオ 1:コンテナー化された ASP.NET web アプリ</span><span class="sxs-lookup"><span data-stu-id="c4df3-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="c4df3-158">次の図は、コンテナー化された eShop レガシ web apps アプリケーションのシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![開発環境でのコンテナー化された ASP.NET アプリケーションの簡略化されたアーキテクチャダイアグラム](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="c4df3-160">例 2:コンテナー化された WCF サービス</span><span class="sxs-lookup"><span data-stu-id="c4df3-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="c4df3-161">次の図は、コンテナー化された WCF サービスを使用した3層アプリケーションのシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![開発環境でのコンテナー化された WCF サービスの簡略化されたアーキテクチャダイアグラム](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="c4df3-163">利点</span><span class="sxs-lookup"><span data-stu-id="c4df3-163">Benefits</span></span>

<span data-ttu-id="c4df3-164">コンテナーでモノリシックアプリケーションを実行することには利点があります。</span><span class="sxs-lookup"><span data-stu-id="c4df3-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="c4df3-165">まず、アプリケーションのイメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-165">First, you create an image for the application.</span></span> <span data-ttu-id="c4df3-166">この時点から、すべての配置は同じ環境で実行されます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="c4df3-167">すべてのコンテナーは同じバージョンの OS を使用し、同じバージョンの依存関係をインストールし、同じ .NET framework バージョンを使用します。また、同じプロセスを使用してビルドされます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="c4df3-168">基本的には、Docker イメージを使用して、アプリケーションの依存関係を制御します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="c4df3-169">コンテナーをデプロイすると、依存関係はアプリケーションと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="c4df3-170">さらに、開発者は Windows コンテナーによって提供される一貫性のある環境でアプリケーションを実行できるという利点もあります。</span><span class="sxs-lookup"><span data-stu-id="c4df3-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="c4df3-171">特定のバージョンでのみ表示される問題は、ステージング環境または運用環境ではなく、すぐに発見できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="c4df3-172">開発チームのメンバーが使用する開発環境の違いは、アプリケーションがコンテナーで実行される場合にはあまり重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="c4df3-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="c4df3-173">コンテナー化されたアプリケーションには、flatter のスケールアウト曲線もあります。</span><span class="sxs-lookup"><span data-stu-id="c4df3-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="c4df3-174">コンテナー化されたアプリを使用すると、コンピューターごとの通常のアプリケーション展開と比較して、VM または物理マシンに、(コンテナーに基づく) より多くのアプリケーションとサービスインスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="c4df3-175">これにより、特に Kubernetes のようなオーケストレーター使用する場合に、より高密度で必要なリソースが減少します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="c4df3-176">コンテナー化は、理想的な状況では、アプリケーションコード (C\#) に変更を加える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c4df3-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="c4df3-177">ほとんどのシナリオでは、Docker 配置メタデータファイル (Dockerfiles および Docker Compose ファイル) が必要です。</span><span class="sxs-lookup"><span data-stu-id="c4df3-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="c4df3-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="c4df3-178">Next steps</span></span>

<span data-ttu-id="c4df3-179">このコンテンツについて詳しくは、GitHub wiki をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4df3-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="c4df3-180">Windows コンテナーと Docker を使用して .NET Framework web アプリをコンテナー化する方法</span><span class="sxs-lookup"><span data-stu-id="c4df3-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="c4df3-181">WCF サービスへの Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="c4df3-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="c4df3-182">チュートリアル 3:Windows コンテナーベースのアプリを Azure Vm にデプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c4df3-183">テクニカルチュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="c4df3-183">Technical walkthrough availability</span></span>

<span data-ttu-id="c4df3-184">完全な技術チュートリアルについては、eShopModernizing GitHub リポジトリ wiki を参照してください。<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="c4df3-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="c4df3-185">概要</span><span class="sxs-lookup"><span data-stu-id="c4df3-185">Overview</span></span>

<span data-ttu-id="c4df3-186">Azure の Windows Server 2016 仮想マシン (VM) 上の Docker ホストにデプロイすると、開発/テスト/ステージング環境をすばやく設定できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="c4df3-187">また、テスト担当者またはビジネスユーザーがアプリを検証するための一般的な場所も提供します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="c4df3-188">Vm は、サービスとしてのインフラストラクチャ (IaaS) 運用環境としても有効です。</span><span class="sxs-lookup"><span data-stu-id="c4df3-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="c4df3-189">目標</span><span class="sxs-lookup"><span data-stu-id="c4df3-189">Goals</span></span>

<span data-ttu-id="c4df3-190">このチュートリアルの目的は、windows Server 2016 以降のバージョンを基盤とする Azure Vm に Windows コンテナーを展開するときに、複数の選択肢を紹介することです。</span><span class="sxs-lookup"><span data-stu-id="c4df3-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="c4df3-191">シナリオ</span><span class="sxs-lookup"><span data-stu-id="c4df3-191">Scenarios</span></span>

<span data-ttu-id="c4df3-192">このチュートリアルでは、いくつかのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="c4df3-193">シナリオ A:Docker エンジン接続を介して開発用 PC から Azure VM にデプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Docker エンジン接続を使用して開発用 PC から Azure VM にデプロイする](./media/image5-4.png)

<span data-ttu-id="c4df3-195">**図 5-4**</span><span class="sxs-lookup"><span data-stu-id="c4df3-195">**Figure 5-4.**</span></span> <span data-ttu-id="c4df3-196">Docker エンジン接続を使用して開発用 PC から Azure VM にデプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="c4df3-197">シナリオ B:Docker レジストリを使用して Azure VM にデプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Docker レジストリを使用して Azure VM にデプロイする](./media/image5-5.png)

<span data-ttu-id="c4df3-199">**図 5-5**</span><span class="sxs-lookup"><span data-stu-id="c4df3-199">**Figure 5-5.**</span></span> <span data-ttu-id="c4df3-200">Docker レジストリを使用して Azure VM にデプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="c4df3-201">シナリオ C:Azure DevOps Services の CI/CD パイプラインから Azure VM にデプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps Services の CI/CD パイプラインから Azure VM にデプロイする](./media/image5-6.png)

<span data-ttu-id="c4df3-203">**図 5-6**</span><span class="sxs-lookup"><span data-stu-id="c4df3-203">**Figure 5-6.**</span></span> <span data-ttu-id="c4df3-204">Azure DevOps Services の CI/CD パイプラインから Azure VM にデプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="c4df3-205">Windows コンテナー用の Azure Vm</span><span class="sxs-lookup"><span data-stu-id="c4df3-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="c4df3-206">Windows コンテナー用の Azure Vm は、Docker エンジンがセットアップされている Windows Server 2016、Windows 10 以降のバージョンに基づく Vm です。</span><span class="sxs-lookup"><span data-stu-id="c4df3-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="c4df3-207">ほとんどの場合、Azure Vm では Windows Server 2016 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="c4df3-208">Azure では現在、 **Windows Server 2016**という名前の VM とコンテナーを提供しています。</span><span class="sxs-lookup"><span data-stu-id="c4df3-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="c4df3-209">この VM を使用して、windows Server Core または Windows Nano Server のいずれかを使用して、新しい Windows Server コンテナー機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="c4df3-210">コンテナー OS イメージがインストールされた後、VM を Docker で使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="c4df3-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="c4df3-211">利点</span><span class="sxs-lookup"><span data-stu-id="c4df3-211">Benefits</span></span>

<span data-ttu-id="c4df3-212">Windows コンテナーはオンプレミスの Windows Server 2016 Vm にデプロイできますが、Azure にデプロイすると、すぐに使い始めることができる Windows Server コンテナー Vm を使用して簡単に開始できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="c4df3-213">また、テスト担当者は、Azure 仮想マシンスケールセットを通じて自動的にスケーラビリティを利用できる、一般的なオンラインの場所も取得できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="c4df3-214">次の手順</span><span class="sxs-lookup"><span data-stu-id="c4df3-214">Next steps</span></span>

<span data-ttu-id="c4df3-215">このコンテンツについて詳しくは、GitHub wiki をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4df3-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="c4df3-216">チュートリアル 4:Windows コンテナーベースのアプリを Azure Container Instances (ACI) に展開する</span><span class="sxs-lookup"><span data-stu-id="c4df3-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c4df3-217">テクニカルチュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="c4df3-217">Technical walkthrough availability</span></span>

<span data-ttu-id="c4df3-218">完全な技術チュートリアルについては、eShopModernizing GitHub リポジトリ wiki を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4df3-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="c4df3-219">[ACI へのアプリの展開 (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="c4df3-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="c4df3-220">概要</span><span class="sxs-lookup"><span data-stu-id="c4df3-220">Overview</span></span>

<span data-ttu-id="c4df3-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/)は、コンテナーの開発/テスト/ステージング環境を作成するための最も簡単な方法です。コンテナーの1つのインスタンスをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="c4df3-222">目標</span><span class="sxs-lookup"><span data-stu-id="c4df3-222">Goals</span></span>

<span data-ttu-id="c4df3-223">このチュートリアルでは、Azure Container Instances (ACI) に Windows コンテナーを展開する主なシナリオと、eShopModernizing アプリを ACI に展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="c4df3-224">シナリオ</span><span class="sxs-lookup"><span data-stu-id="c4df3-224">Scenarios</span></span>

<span data-ttu-id="c4df3-225">1つまたはすべてのアプリ (MVC アプリ、WebForms app、または WCF サービス) をデプロイするなど、eShopModernizing アプリを ACI にデプロイすることにはさまざまなバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="c4df3-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="c4df3-226">次に示すシナリオでは、ASP.NET MVC アプリと SQL Server コンテナーの両方が、コンテナーとして ACI (Azure Container Instances) に展開されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![開発環境から ACI にデプロイする](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="c4df3-228">利点</span><span class="sxs-lookup"><span data-stu-id="c4df3-228">Benefits</span></span>

<span data-ttu-id="c4df3-229">Azure Container Instances を使用すると、仮想マシンをプロビジョニングしたり、より高いレベルのサービスを採用したりしなくても、Azure で Docker コンテナーの作成と管理を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="c4df3-230">ACI を使用すると、Windows コンテナーを Azure に直接デプロイし、数秒で完全修飾ドメイン名 (FQDN) を使用してインターネットに公開することができます (Docker Hub や Azure Container などの Docker レジストリで Windows コンテナーイメージを準備している場合)。レジストリ)。</span><span class="sxs-lookup"><span data-stu-id="c4df3-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="c4df3-231">考慮事項</span><span class="sxs-lookup"><span data-stu-id="c4df3-231">Considerations</span></span>

<span data-ttu-id="c4df3-232">完全 .NET Framework/ASP.NET または SQL Server を使用した Windows コンテナーの展開は Azure Container Instances (ACI) ではありません。 Docker イメージは、次のように、通常の Docker ホストに展開するのと同じくらい高速ではありません (windows コンテナーを使用した Windows Server 2016 など)。SQL コンテナーイメージ (15.1 GB) と ASP.NET container image (13.9 GB) のサイズは、毎回 (Docker レジストリからプルされて) ダウンロードされますが、独自の Docker ホストを維持するよりもはるかにコストがかかります (完全にオンラインAzure の Windows コンテナー VM を使用した windows Server 2016) は、一方で、運用環境のデプロイに最適な選択肢である Azure の Kubernetes (AKS) のような orchestrator 全体を示すものではありません。</span><span class="sxs-lookup"><span data-stu-id="c4df3-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="c4df3-233">主要な結論として、Azure Container Instances を使用することは、開発/テストシナリオおよび CI/CD パイプラインの非常に説得力のあるオプションです。</span><span class="sxs-lookup"><span data-stu-id="c4df3-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4df3-234">次の手順</span><span class="sxs-lookup"><span data-stu-id="c4df3-234">Next steps</span></span>

<span data-ttu-id="c4df3-235">このコンテンツについて詳しくは、GitHub wiki をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4df3-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="c4df3-236">チュートリアル 5:Windows コンテナーベースのアプリを Azure Container Service の Kubernetes に展開する</span><span class="sxs-lookup"><span data-stu-id="c4df3-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c4df3-237">テクニカルチュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="c4df3-237">Technical walkthrough availability</span></span>

<span data-ttu-id="c4df3-238">完全な技術チュートリアルについては、eShopModernizing GitHub リポジトリ wiki を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4df3-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="c4df3-239">概要</span><span class="sxs-lookup"><span data-stu-id="c4df3-239">Overview</span></span>

<span data-ttu-id="c4df3-240">Windows コンテナーに基づくアプリケーションでは、IaaS Vm からさらに離れた場所でも、プラットフォームをすばやく使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4df3-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="c4df3-241">これは、高いスケーラビリティと自動化されたスケーラビリティを簡単に実現するために必要であり、自動化された配置とバージョン管理の大幅な改善にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="c4df3-242">これらの目標は、 [Azure Container Services](https://azure.microsoft.com/services/container-service/)で利用できる orchestrator [Kubernetes](https://kubernetes.io/)を使用して実現できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="c4df3-243">目標</span><span class="sxs-lookup"><span data-stu-id="c4df3-243">Goals</span></span>

<span data-ttu-id="c4df3-244">このチュートリアルの目的は、Azure Container Service で Windows コンテナーベースのアプリケーションを Kubernetes ( *K8s*とも呼ばれます) に展開する方法について説明することです。</span><span class="sxs-lookup"><span data-stu-id="c4df3-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="c4df3-245">最初から Kubernetes への配置は、次の2段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c4df3-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="c4df3-246">Azure Container Service に Kubernetes クラスターをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="c4df3-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="c4df3-247">アプリケーションと関連リソースを Kubernetes クラスターにデプロイします。</span><span class="sxs-lookup"><span data-stu-id="c4df3-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="c4df3-248">シナリオ</span><span class="sxs-lookup"><span data-stu-id="c4df3-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="c4df3-249">シナリオ A:開発環境から Kubernetes クラスターに直接デプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![開発環境から Kubernetes クラスターに直接デプロイする](./media/image5-7.png)

<span data-ttu-id="c4df3-251">**図 5-7**</span><span class="sxs-lookup"><span data-stu-id="c4df3-251">**Figure 5-7.**</span></span> <span data-ttu-id="c4df3-252">開発環境から Kubernetes クラスターに直接デプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="c4df3-253">シナリオ B:Azure DevOps Services の CI/CD パイプラインから Kubernetes クラスターにデプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps Services の CI/CD パイプラインから Kubernetes クラスターにデプロイする](./media/image5-8.png)

<span data-ttu-id="c4df3-255">**図 5-8**</span><span class="sxs-lookup"><span data-stu-id="c4df3-255">**Figure 5-8.**</span></span> <span data-ttu-id="c4df3-256">Azure DevOps Services の CI/CD パイプラインから Kubernetes クラスターにデプロイする</span><span class="sxs-lookup"><span data-stu-id="c4df3-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="c4df3-257">利点</span><span class="sxs-lookup"><span data-stu-id="c4df3-257">Benefits</span></span>

<span data-ttu-id="c4df3-258">Kubernetes でクラスターにデプロイすることには多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="c4df3-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="c4df3-259">最大の利点は、使用するコンテナーインスタンスの数 (既存のノードの内部スケーラビリティ) に基づいてアプリケーションをスケールアウトし、クラスター内のノードまたは Vm の数に基づいて、運用環境に対応した環境を実現できることです (クラスターのグローバルなスケーラビリティ)。</span><span class="sxs-lookup"><span data-stu-id="c4df3-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="c4df3-260">Azure Container Service は、Azure 専用の広く普及しているオープンソースのツールとテクノロジを最適化します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="c4df3-261">コンテナーとアプリケーションの構成の両方について、移植性を提供するオープンソリューションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="c4df3-262">サイズ、ホスト数、および orchestrator ツールを選択します。コンテナーサービスは、他のすべてを処理します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="c4df3-263">Kubernetes を使用すると、開発者は物理マシンと仮想マシンについて考えることができ、次のような機能を容易にするコンテナー中心のインフラストラクチャを計画することができます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="c4df3-264">複数のコンテナーに基づくアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c4df3-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="c4df3-265">コンテナーインスタンスと水平方向の自動スケールのレプリケート</span><span class="sxs-lookup"><span data-stu-id="c4df3-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="c4df3-266">名前付けと検出 (例、内部 DNS)</span><span class="sxs-lookup"><span data-stu-id="c4df3-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="c4df3-267">負荷分散</span><span class="sxs-lookup"><span data-stu-id="c4df3-267">Balancing loads</span></span>

- <span data-ttu-id="c4df3-268">ローリングアップデート</span><span class="sxs-lookup"><span data-stu-id="c4df3-268">Rolling updates</span></span>

- <span data-ttu-id="c4df3-269">シークレットの配布</span><span class="sxs-lookup"><span data-stu-id="c4df3-269">Distributing secrets</span></span>

- <span data-ttu-id="c4df3-270">アプリケーションの正常性チェック</span><span class="sxs-lookup"><span data-stu-id="c4df3-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4df3-271">次の手順</span><span class="sxs-lookup"><span data-stu-id="c4df3-271">Next steps</span></span>

<span data-ttu-id="c4df3-272">このコンテンツについて詳しくは、GitHub wiki をご覧ください。<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="c4df3-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="c4df3-273">チュートリアル 6:コンテナー用の Azure App Service に Windows コンテナーベースのアプリを展開する</span><span class="sxs-lookup"><span data-stu-id="c4df3-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c4df3-274">テクニカルチュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="c4df3-274">Technical walkthrough availability</span></span>

<span data-ttu-id="c4df3-275">完全な技術チュートリアルについては、eShopModernizing GitHub リポジトリ wiki を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4df3-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="c4df3-276">概要</span><span class="sxs-lookup"><span data-stu-id="c4df3-276">Overview</span></span>

<span data-ttu-id="c4df3-277">Windows コンテナーを使用する単純なコンテナー化されたアプリケーションは、コンテナーの Azure App Service に簡単にデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="c4df3-278">これは、ほとんどの Windows コンテナーベースのアプリケーションで推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="c4df3-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="c4df3-279">目標</span><span class="sxs-lookup"><span data-stu-id="c4df3-279">Goals</span></span>

<span data-ttu-id="c4df3-280">このチュートリアルの目的は、Windows コンテナーベースのアプリケーションを展開して、レジストリ (Docker Hub または Azure Container Registry) からコンテナーを Azure App Service する方法について説明することです。</span><span class="sxs-lookup"><span data-stu-id="c4df3-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="c4df3-281">シナリオ</span><span class="sxs-lookup"><span data-stu-id="c4df3-281">Scenario</span></span>

![コンテナーの Azure App Service に Windows コンテナーベースのアプリを展開する](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="c4df3-283">利点</span><span class="sxs-lookup"><span data-stu-id="c4df3-283">Benefits</span></span>

<span data-ttu-id="c4df3-284">コンテナーの Azure App Service にデプロイすると、コンテナーの利点と Azure App Service の PaaS の利点との組み合わせが実現します。</span><span class="sxs-lookup"><span data-stu-id="c4df3-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="c4df3-285">App service は、垂直方向と水平方向の両方で簡単にスケーリングでき、変化する需要に合わせて自動スケールするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="c4df3-286">更新はダウンタイムなしで実行でき、レジストリからの継続的な展開の構成も簡単に構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4df3-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4df3-287">次の手順</span><span class="sxs-lookup"><span data-stu-id="c4df3-287">Next steps</span></span>

<span data-ttu-id="c4df3-288">このコンテンツについて詳しくは、GitHub wiki をご覧ください。<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span><span class="sxs-lookup"><span data-stu-id="c4df3-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="c4df3-289">[前へ](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [次へ](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="c4df3-289">[Previous](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span> <!-- Next Chapter -->
