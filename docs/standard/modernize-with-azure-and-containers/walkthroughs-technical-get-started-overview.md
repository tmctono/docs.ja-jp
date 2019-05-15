---
title: チュートリアルと技術的な概要
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |チュートリアルと技術的な概要します。
ms.date: 04/28/2018
ms.openlocfilehash: f5c1ca2b78d27b275845ada72d252450761f5091
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638967"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="37ac7-103">チュートリアルと技術的な概要</span><span class="sxs-lookup"><span data-stu-id="37ac7-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="37ac7-104">この電子ブックのサイズを制限するには、その他の技術ドキュメントと完全なチュートリアルで行われた使用可能な GitHub リポジトリ。</span><span class="sxs-lookup"><span data-stu-id="37ac7-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="37ac7-105">オンラインの一連のこの章で説明したチュートリアルでは、Windows コンテナー、および Azure へのデプロイに基づいて複数の環境のステップ バイ ステップのセットアップについて説明します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="37ac7-106">次のセクションでは、各チュートリアルでは、その目標と高度なビジョンを通知し、関連するタスクを次の図は、について説明します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="37ac7-107">自体のチュートリアルを入手できますで、 *eShopModernizing*でアプリの GitHub リポジトリ wiki<https://github.com/dotnet-architecture/eShopModernizing/wiki>します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="37ac7-108">技術チュートリアルの一覧</span><span class="sxs-lookup"><span data-stu-id="37ac7-108">Technical walkthrough list</span></span>

<span data-ttu-id="37ac7-109">次の概要チュートリアルでは、リフトとシフト、コンテナーを使用しておよび Azure で複数の展開のオプションを使用して、移動できるサンプル アプリの包括的な一貫性のあるの技術的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="37ac7-110">次のチュートリアルの各アプリで使用して、新しいサンプル eShopLegacy と eShopModernizing、GitHub で利用できる<https://github.com/dotnet-architecture/eShopModernizing>します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="37ac7-111">**EShop レガシ アプリ (現代化する基準アプリ) のツアー**</span><span class="sxs-lookup"><span data-stu-id="37ac7-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="37ac7-112">**Windows コンテナーで既存 ASP.NET web アプリ (WebForms および MVC) のコンテナー格納します。**</span><span class="sxs-lookup"><span data-stu-id="37ac7-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="37ac7-113">**Windows コンテナーで既存の WCF サービス (N 層アプリ) のコンテナー格納します。**</span><span class="sxs-lookup"><span data-stu-id="37ac7-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="37ac7-114">**Azure Vm への Windows コンテナー ベース アプリをデプロイします。**</span><span class="sxs-lookup"><span data-stu-id="37ac7-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="37ac7-115">**Windows コンテナー ベースのアプリを Azure Container Service で Kubernetes にデプロイします。**</span><span class="sxs-lookup"><span data-stu-id="37ac7-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="37ac7-116">**Azure Service Fabric への Windows コンテナー ベースのアプリをデプロイします。**</span><span class="sxs-lookup"><span data-stu-id="37ac7-116">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="37ac7-117">チュートリアル 1:EShop レガシ アプリケーションのツアー</span><span class="sxs-lookup"><span data-stu-id="37ac7-117">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="37ac7-118">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="37ac7-118">Technical walkthrough availability</span></span>

<span data-ttu-id="37ac7-119">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。</span><span class="sxs-lookup"><span data-stu-id="37ac7-119">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="37ac7-120">wiki のチュートリアルは eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="37ac7-120">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="37ac7-121">概要</span><span class="sxs-lookup"><span data-stu-id="37ac7-121">Overview</span></span>

<span data-ttu-id="37ac7-122">このチュートリアルでは、次の 3 つのサンプルのレガシ アプリケーションの最初の実装を確認できます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-122">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="37ac7-123">最初の 2 つのサンプル web アプリは、モノリシック アーキテクチャがあるし、従来の ASP.NET を使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="37ac7-123">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="37ac7-124">1 つのアプリケーション ベースは ASP.NET 4.x MVC;2 番目のアプリケーションは、ASP.NET 4.x Web フォームに基づきます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-124">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="37ac7-125">3 番目のアプリは、WinForms アプリをクライアントとサーバー側で構成されます 3 層アプリ[Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md)サービス。</span><span class="sxs-lookup"><span data-stu-id="37ac7-125">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="37ac7-126">これらすべてのアプリケーションは、 [eShopModernizing GitHub リポジトリ](https://github.com/dotnet-architecture/eShopModernizing)します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-126">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="37ac7-127">目的</span><span class="sxs-lookup"><span data-stu-id="37ac7-127">Goals</span></span>

<span data-ttu-id="37ac7-128">このチュートリアルの主な目的は、これらのアプリとそのコードと構成について詳しく理解することです。</span><span class="sxs-lookup"><span data-stu-id="37ac7-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="37ac7-129">生成およびテスト目的で、SQL database を使用せず、モックのデータを使用できるように、アプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="37ac7-130">このオプションの構成は、分離された方法で依存関係の挿入に基づいています。</span><span class="sxs-lookup"><span data-stu-id="37ac7-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="37ac7-131">シナリオ 1:ASP.NET Web アプリ</span><span class="sxs-lookup"><span data-stu-id="37ac7-131">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="37ac7-132">次の図は、元の従来の ASP.NET web アプリケーションの簡単なシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-132">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![元の従来の ASP.NET web アプリケーションのアーキテクチャの単純なシナリオ](./media/image5-1.png)

<span data-ttu-id="37ac7-134">ビジネス ドメインの観点から両方のアプリは管理機能に同じカタログを提供します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-134">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="37ac7-135">EShop エンタープライズ チームのメンバーでは、製品カタログの編集を表示したり、アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-135">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="37ac7-136">次の図は、最初のアプリのスクリーン ショットを示します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-136">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC と ASP.NET Web フォーム アプリケーション (既存の/レガシ テクノロジ)](./media/image5-2.png)

<span data-ttu-id="37ac7-138">依存関係 asp.net 4.x または以前のバージョン (MVC または Web フォームか) はこれらのアプリケーションは、ASP.NET Core MVC を使用してコードを書き直すが完全にしない限り、.NET Core で動作しません。</span><span class="sxs-lookup"><span data-stu-id="37ac7-138">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="37ac7-139">シナリオ 2:WCF サービスとクライアント アプリの WinForms (3 層アプリ)</span><span class="sxs-lookup"><span data-stu-id="37ac7-139">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="37ac7-140">次の図は、元の 3 層のレガシ アプリケーションの簡単なシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-140">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![WCF サービスと、元のレガシ 3 層アプリおよび WinForms クライアント アプリのアーキテクチャの単純なシナリオ](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="37ac7-142">利点</span><span class="sxs-lookup"><span data-stu-id="37ac7-142">Benefits</span></span>

<span data-ttu-id="37ac7-143">このチュートリアルの利点はシンプルです。コードと最初のアプリを使用して理解します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-143">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="37ac7-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="37ac7-144">Next steps</span></span>

<span data-ttu-id="37ac7-145">このコンテンツの詳細については、GitHub wiki 詳細します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-145">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="37ac7-146">ASP.NET MVC、ベースラインをツアーと Web フォーム「レガシ」アプリ</span><span class="sxs-lookup"><span data-stu-id="37ac7-146">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="37ac7-147">WCF サービスの基準と WinForms (3 層) の「レガシ」アプリのツアー</span><span class="sxs-lookup"><span data-stu-id="37ac7-147">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="37ac7-148">チュートリアル 2:Windows コンテナーで既存の .NET アプリケーションのコンテナー格納します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-148">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="37ac7-149">概要</span><span class="sxs-lookup"><span data-stu-id="37ac7-149">Overview</span></span>

<span data-ttu-id="37ac7-150">MVC、Web フォーム、または WCF では、運用、開発、およびテスト環境に基づくように、既存の .NET アプリケーションの展開を向上させるために Windows コンテナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-150">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="37ac7-151">目的</span><span class="sxs-lookup"><span data-stu-id="37ac7-151">Goals</span></span>

<span data-ttu-id="37ac7-152">このチュートリアルの目的では、既存の .NET Framework アプリケーションをコンテナー化のいくつかのオプションを説明します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-152">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="37ac7-153">次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-153">You can:</span></span>

- <span data-ttu-id="37ac7-154">使用して、アプリケーションをコンテナー化[Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 またはそれ以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="37ac7-154">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="37ac7-155">手動で追加することで、アプリケーションをコンテナー化、 [Dockerfile](https://docs.docker.com/engine/reference/builder/)、しを使用して、 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-155">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="37ac7-156">使用して、アプリケーションをコンテナー化、 [Img2Docker](https://github.com/docker/communitytools-image2docker-win)ツール (Docker からオープン ソース ツール)。</span><span class="sxs-lookup"><span data-stu-id="37ac7-156">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="37ac7-157">このチュートリアルは、Docker 方法は、Visual Studio 2017 Tools について重点的に取り上げます。 が、その他の 2 つのアプローチは Dockerfile を使用してに関して類似しています。</span><span class="sxs-lookup"><span data-stu-id="37ac7-157">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="37ac7-158">シナリオ 1:コンテナー化された ASP.NET web アプリ</span><span class="sxs-lookup"><span data-stu-id="37ac7-158">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="37ac7-159">次の図は、コンテナー化された eShop 従来の web アプリのアプリケーションのシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-159">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![簡素化されたアーキテクチャの図は、開発環境での ASP.NET アプリケーションをコンテナー化されました。](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="37ac7-161">シナリオ 2:コンテナー化された WCF サービス</span><span class="sxs-lookup"><span data-stu-id="37ac7-161">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="37ac7-162">次の図は、コンテナー化された WCF サービスと 3 層アプリケーションのシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-162">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![開発環境でコンテナー化された WCF サービスのアーキテクチャ図を簡略化](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="37ac7-164">利点</span><span class="sxs-lookup"><span data-stu-id="37ac7-164">Benefits</span></span>

<span data-ttu-id="37ac7-165">これには、コンテナーで、モノリシック アプリケーションを実行する利点があります。</span><span class="sxs-lookup"><span data-stu-id="37ac7-165">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="37ac7-166">最初に、アプリケーションのイメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-166">First, you create an image for the application.</span></span> <span data-ttu-id="37ac7-167">その時点からは、すべてのデプロイは、同じ環境内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-167">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="37ac7-168">すべてのコンテナーで、同じ OS バージョンを使用して、同じバージョンの依存関係のインストールが同じ .NET framework のバージョンを使用しておよびは同じプロセスを使用して構築されています。</span><span class="sxs-lookup"><span data-stu-id="37ac7-168">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="37ac7-169">基本的には、Docker イメージを使用して、アプリケーションの依存関係を制御します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-169">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="37ac7-170">依存関係は、コンテナーをデプロイするときに、アプリケーションと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-170">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="37ac7-171">その他の利点は、開発者が Windows のコンテナーによって提供される一貫した環境でアプリケーションを実行できることです。</span><span class="sxs-lookup"><span data-stu-id="37ac7-171">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="37ac7-172">特定のバージョンでのみ表示される問題は、ステージング環境または運用環境で表示することではなく、すぐに発見できます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-172">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="37ac7-173">開発チームのメンバーで使用される開発環境での相違点は問題のコンテナーでアプリケーションの実行時に小さいです。</span><span class="sxs-lookup"><span data-stu-id="37ac7-173">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="37ac7-174">コンテナー化されたアプリケーションでは、flatter スケール アウト曲線もあります。</span><span class="sxs-lookup"><span data-stu-id="37ac7-174">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="37ac7-175">コンテナー化されたアプリには、VM または物理マシンのマシンあたりの定期的なアプリケーション展開と比較する複数のアプリケーションとサービス インスタンスが (コンテナーに基づく) が有効にします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-175">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="37ac7-176">これにより、高密度、および必要な少なくリソース、Kubernetes や Service Fabric などのオーケストレーターを使用する場合に特にです。</span><span class="sxs-lookup"><span data-stu-id="37ac7-176">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="37ac7-177">コンテナリゼーションは、理想的な状況では、アプリケーション コードに変更を加える必要ありません (C\#)。</span><span class="sxs-lookup"><span data-stu-id="37ac7-177">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="37ac7-178">ほとんどのシナリオでは、Docker の展開のメタデータ ファイル (Dockerfile と Docker Compose ファイル) だけ必要です。</span><span class="sxs-lookup"><span data-stu-id="37ac7-178">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="37ac7-179">次の手順</span><span class="sxs-lookup"><span data-stu-id="37ac7-179">Next steps</span></span>

<span data-ttu-id="37ac7-180">このコンテンツの詳細については、GitHub wiki 詳細します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-180">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="37ac7-181">Windows コンテナーと Docker で .NET Framework web アプリをコンテナー化する方法</span><span class="sxs-lookup"><span data-stu-id="37ac7-181">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="37ac7-182">WCF サービスへの Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="37ac7-182">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="37ac7-183">チュートリアル 3:Azure Vm への Windows コンテナー ベース アプリをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-183">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="37ac7-184">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="37ac7-184">Technical walkthrough availability</span></span>

<span data-ttu-id="37ac7-185">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。 <https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="37ac7-185">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="37ac7-186">概要</span><span class="sxs-lookup"><span data-stu-id="37ac7-186">Overview</span></span>

<span data-ttu-id="37ac7-187">Azure で Windows Server 2016 仮想マシン (VM) 上の Docker ホストに展開するには、開発/テスト/ステージング環境をすばやくセットアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-187">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="37ac7-188">アプリを検証するには、テスト担当者またはビジネス ユーザーの一般的な場所も提供します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-188">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="37ac7-189">Vm は、サービス (IaaS) の実稼働環境として有効なインフラストラクチャをすることができます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-189">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="37ac7-190">目的</span><span class="sxs-lookup"><span data-stu-id="37ac7-190">Goals</span></span>

<span data-ttu-id="37ac7-191">このチュートリアルの目的では、Windows Server 2016 またはそれ以降のバージョンに基づいて Azure Vm を Windows コンテナーを展開する場合がある複数の代替手段を説明します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-191">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="37ac7-192">シナリオ</span><span class="sxs-lookup"><span data-stu-id="37ac7-192">Scenarios</span></span>

<span data-ttu-id="37ac7-193">このチュートリアルでは、いくつかのシナリオがについて説明します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-193">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="37ac7-194">シナリオ a:Docker エンジンの接続を介して開発用 PC から Azure VM へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-194">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Docker エンジンの接続を介して開発用 PC から Azure VM へのデプロイします。](./media/image5-4.png)

<span data-ttu-id="37ac7-196">**図 5-4**</span><span class="sxs-lookup"><span data-stu-id="37ac7-196">**Figure 5-4.**</span></span> <span data-ttu-id="37ac7-197">Docker エンジンの接続を介して開発用 PC から Azure VM へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-197">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="37ac7-198">シナリオ b:Docker レジストリを使用して Azure VM にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-198">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Docker レジストリを使用して Azure VM にデプロイします。](./media/image5-5.png)

<span data-ttu-id="37ac7-200">**図 5-5**</span><span class="sxs-lookup"><span data-stu-id="37ac7-200">**Figure 5-5.**</span></span> <span data-ttu-id="37ac7-201">Docker レジストリを使用して Azure VM にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-201">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="37ac7-202">C: のシナリオAzure DevOps Services で CI/CD パイプラインから Azure VM へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-202">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps Services で CI/CD パイプラインから Azure VM へのデプロイします。](./media/image5-6.png)

<span data-ttu-id="37ac7-204">**図 5-6**</span><span class="sxs-lookup"><span data-stu-id="37ac7-204">**Figure 5-6.**</span></span> <span data-ttu-id="37ac7-205">Azure DevOps Services で CI/CD パイプラインから Azure VM へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-205">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="37ac7-206">Windows コンテナー用の azure Vm</span><span class="sxs-lookup"><span data-stu-id="37ac7-206">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="37ac7-207">Windows コンテナーの azure Vm は Vm の Windows Server 2016、Windows 10、またはそれ以降のバージョンに基づいて、Docker エンジンの両方を設定します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-207">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="37ac7-208">ほとんどの場合は、Windows Server 2016 は Azure Vm で使用されます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-208">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="37ac7-209">Azure は、現在という名前の VM を提供します。 **Windows Server 2016 with Containers**します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-209">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="37ac7-210">この VM を使用すると、Windows Server Core または Windows Nano Server のいずれかで、新しい Windows Server コンテナー機能をお試しください。</span><span class="sxs-lookup"><span data-stu-id="37ac7-210">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="37ac7-211">コンテナー OS イメージがインストールされている場合、および Docker を使用する準備が VM でし。</span><span class="sxs-lookup"><span data-stu-id="37ac7-211">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="37ac7-212">利点</span><span class="sxs-lookup"><span data-stu-id="37ac7-212">Benefits</span></span>

<span data-ttu-id="37ac7-213">Windows コンテナーは、Azure にデプロイするときに、オンプレミス Windows Server 2016 の Vm を展開できますが、すぐに使用できる Windows Server コンテナーの Vm を開始する簡単な方法を取得します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-213">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="37ac7-214">テスト担当者、および自動のスケーラビリティを Azure の仮想マシン スケール セットにアクセスできる一般的なオンラインの場所も表示します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-214">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="37ac7-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="37ac7-215">Next steps</span></span>

<span data-ttu-id="37ac7-216">このコンテンツの詳細については、GitHub wiki 詳細します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-216">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="37ac7-217">チュートリアル 4:Azure Container Instances (ACI) への Windows コンテナー ベースのアプリをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-217">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="37ac7-218">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="37ac7-218">Technical walkthrough availability</span></span>

<span data-ttu-id="37ac7-219">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。</span><span class="sxs-lookup"><span data-stu-id="37ac7-219">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="37ac7-220">[ACI (Azure Container Instances) に、アプリを展開します。](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="37ac7-220">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="37ac7-221">概要</span><span class="sxs-lookup"><span data-stu-id="37ac7-221">Overview</span></span>

<span data-ttu-id="37ac7-222">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/)はコンテナーの 1 つのインスタンスをデプロイするコンテナーの開発/テスト/ステージング環境に最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="37ac7-222">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="37ac7-223">目的</span><span class="sxs-lookup"><span data-stu-id="37ac7-223">Goals</span></span>

<span data-ttu-id="37ac7-224">このチュートリアルでは、主なシナリオ Azure Container Instances (ACI) ACI に eShopModernizing アプリをデプロイする方法を Windows コンテナーをデプロイするときにします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-224">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="37ac7-225">シナリオ</span><span class="sxs-lookup"><span data-stu-id="37ac7-225">Scenarios</span></span>

<span data-ttu-id="37ac7-226">ACI に eShopModernizing アプリを展開する 1 つまたはすべてのアプリ (MVC アプリ、web フォーム アプリケーションまたは WCF サービス) の展開などについてのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="37ac7-226">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="37ac7-227">次のシナリオを次に示すことができます、コンテナーとして ACI (Azure Container Instances) に ASP.NET MVC アプリとこれらの両方に展開されている SQL Server のコンテナーを表示します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-227">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![開発環境から ACI へのデプロイします。](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="37ac7-229">利点</span><span class="sxs-lookup"><span data-stu-id="37ac7-229">Benefits</span></span>

<span data-ttu-id="37ac7-230">Azure Container Instances では、簡単に作成し、仮想マシンをプロビジョニングしたり、上位レベルのサービスを採用したりしなくても、Azure で Docker コンテナーを管理します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-230">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="37ac7-231">、ACI で直接 Azure で Windows コンテナーのデプロイし、への公開を完全修飾ドメイン名 (FQDN) を使用してインターネットに数秒 (Docker Hub や Azure コンテナーのような Docker レジストリで準備ができて、Windows コンテナー イメージがある場合にすることができますレジストリの場合)。</span><span class="sxs-lookup"><span data-stu-id="37ac7-231">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="37ac7-232">注意事項</span><span class="sxs-lookup"><span data-stu-id="37ac7-232">Considerations</span></span>

<span data-ttu-id="37ac7-233">いずれかの完全な .NET Framework と Windows コンテナーのデプロイ]、[ASP.NET または SQL Server Azure Container Instances (ACI) には、Docker イメージがあるためです (Windows コンテナーでの Windows Server 2016) などの通常の Docker ホストにデプロイする場合と非常に高速ではありません(Docker レジストリからプルされた) たびにダウンロードし、これは、独自の docker ホスト (永続的にオンラインを維持するよりもよりもコストは、SQL コンテナー イメージ (15.1 GB) と ASP.NET のコンテナー イメージ (13.9 GB) のサイズが非常に大きい場合、Azure で Windows コンテナーの VM で Windows Server 2016) することで、全体のオーケストレーターは、その一方で、運用環境のデプロイ用の優れた選択肢である Kubernetes (AKS/ACS) を Azure または Azure Service Fabric でのようにします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-233">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS/ACS) or Azure Service Fabric which are, on the other hand, great choices for production deployments.</span></span>

<span data-ttu-id="37ac7-234">メインの結論としては、Azure Container Instances を使用して開発/テスト シナリオの場合と CI/CD パイプラインの非常に魅力的なオプション。</span><span class="sxs-lookup"><span data-stu-id="37ac7-234">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="37ac7-235">次の手順</span><span class="sxs-lookup"><span data-stu-id="37ac7-235">Next steps</span></span>

<span data-ttu-id="37ac7-236">このコンテンツの詳細については、GitHub wiki 詳細します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-236">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="37ac7-237">チュートリアル 5:Windows コンテナー ベースのアプリを Azure Container Service で Kubernetes にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-237">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="37ac7-238">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="37ac7-238">Technical walkthrough availability</span></span>

<span data-ttu-id="37ac7-239">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。</span><span class="sxs-lookup"><span data-stu-id="37ac7-239">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)>

### <a name="overview"></a><span data-ttu-id="37ac7-240">概要</span><span class="sxs-lookup"><span data-stu-id="37ac7-240">Overview</span></span>

<span data-ttu-id="37ac7-241">Windows コンテナーに基づいているアプリケーションはすばやく離れたから IaaS Vm の移動、さらに、プラットフォームを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ac7-241">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="37ac7-242">これを簡単に高いスケーラビリティを実現するために必要なよりスケーラビリティ、自動し、大幅に向上のデプロイとバージョン管理を自動化します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-242">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="37ac7-243">これらの目標を達成するには、orchestrator を使用して[Kubernetes](https://kubernetes.io/)で使用できる、 [Azure Container Services](https://azure.microsoft.com/services/container-service/)します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-243">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="37ac7-244">目的</span><span class="sxs-lookup"><span data-stu-id="37ac7-244">Goals</span></span>

<span data-ttu-id="37ac7-245">このチュートリアルの目標は Kubernetes への Windows コンテナー ベースのアプリケーションをデプロイする方法を理解する (とも呼ばれる*K8s*) で Azure Container Service。</span><span class="sxs-lookup"><span data-stu-id="37ac7-245">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="37ac7-246">ゼロからの Kubernetes にデプロイすると、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="37ac7-246">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="37ac7-247">Azure Container Service に Kubernetes クラスターをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-247">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="37ac7-248">Kubernetes クラスターに、アプリケーションと関連リソースをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-248">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="37ac7-249">シナリオ</span><span class="sxs-lookup"><span data-stu-id="37ac7-249">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="37ac7-250">シナリオ a:開発環境から Kubernetes クラスターに直接デプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-250">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![開発環境から Kubernetes クラスターに直接デプロイします。](./media/image5-7.png)

<span data-ttu-id="37ac7-252">**図 5-7**</span><span class="sxs-lookup"><span data-stu-id="37ac7-252">**Figure 5-7.**</span></span> <span data-ttu-id="37ac7-253">開発環境から Kubernetes クラスターに直接デプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-253">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="37ac7-254">シナリオ b:Azure DevOps Services で CI/CD パイプラインから Kubernetes クラスターにデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-254">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps Services で CI/CD パイプラインから Kubernetes クラスターにデプロイします。](./media/image5-8.png)

<span data-ttu-id="37ac7-256">**図 5-8**</span><span class="sxs-lookup"><span data-stu-id="37ac7-256">**Figure 5-8.**</span></span> <span data-ttu-id="37ac7-257">Azure DevOps Services で CI/CD パイプラインから Kubernetes クラスターにデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-257">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="37ac7-258">利点</span><span class="sxs-lookup"><span data-stu-id="37ac7-258">Benefits</span></span>

<span data-ttu-id="37ac7-259">Kubernetes でのクラスターにデプロイする多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="37ac7-259">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="37ac7-260">最大のメリットは (既存のノードでは内部スケーラビリティ) を使用して、クラスター (ノードまたは Vm の数に基づくコンテナー インスタンスの数に基づいて、アプリケーションをスケールすることができます、実稼働可能な環境を取得します。グローバルなスケーラビリティ、クラスターの)。</span><span class="sxs-lookup"><span data-stu-id="37ac7-260">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="37ac7-261">Azure Container Service では、Azure 向けに人気のあるオープン ソース ツールとテクノロジを最適化します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-261">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="37ac7-262">移植性、コンテナーと、アプリケーションの構成の両方を提供する、開いているソリューションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-262">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="37ac7-263">ホストの数、サイズを選択し、orchestrator ツール-コンテナーのサービスが他のすべてを処理します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-263">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="37ac7-264">Kubernetes で開発者を他のユーザーの間で、次の機能を容易にするコンテナーを中心としたインフラストラクチャの計画に物理および仮想マシン、考えたに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-264">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="37ac7-265">複数のコンテナーに基づくアプリケーション</span><span class="sxs-lookup"><span data-stu-id="37ac7-265">Applications based on multiple containers</span></span>

- <span data-ttu-id="37ac7-266">Container instances と水平方向の自動スケールをレプリケートします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-266">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="37ac7-267">名前付けと (たとえば、内部 DNS) の検出</span><span class="sxs-lookup"><span data-stu-id="37ac7-267">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="37ac7-268">負荷を分散</span><span class="sxs-lookup"><span data-stu-id="37ac7-268">Balancing loads</span></span>

- <span data-ttu-id="37ac7-269">ローリング アップデート</span><span class="sxs-lookup"><span data-stu-id="37ac7-269">Rolling updates</span></span>

- <span data-ttu-id="37ac7-270">シークレットを配布します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-270">Distributing secrets</span></span>

- <span data-ttu-id="37ac7-271">アプリケーションの正常性チェック</span><span class="sxs-lookup"><span data-stu-id="37ac7-271">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="37ac7-272">次の手順</span><span class="sxs-lookup"><span data-stu-id="37ac7-272">Next steps</span></span>

<span data-ttu-id="37ac7-273">このコンテンツの詳細については、GitHub wiki 詳細します。 <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)></span><span class="sxs-lookup"><span data-stu-id="37ac7-273">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="37ac7-274">チュートリアル 6:Azure Service Fabric への Windows コンテナー ベースのアプリをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-274">Walkthrough 6: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="37ac7-275">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="37ac7-275">Technical walkthrough availability</span></span>

<span data-ttu-id="37ac7-276">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。</span><span class="sxs-lookup"><span data-stu-id="37ac7-276">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="37ac7-277">概要</span><span class="sxs-lookup"><span data-stu-id="37ac7-277">Overview</span></span>

<span data-ttu-id="37ac7-278">Windows コンテナーをすばやくに基づいてアプリケーションでは、IaaS Vm から離れて移動、さらに、プラットフォームを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ac7-278">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="37ac7-279">これを簡単に高いスケーラビリティを実現するために必要なよりスケーラビリティ、自動し、大幅に向上のデプロイとバージョン管理を自動化します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-279">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="37ac7-280">Azure Service Fabric は、Azure のクラウドで使用できますが、オンプレミスでも実行できますが、オーケストレーターを使用して、または別のパブリック クラウドであっても、これらの目標を実現できます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-280">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="37ac7-281">目的</span><span class="sxs-lookup"><span data-stu-id="37ac7-281">Goals</span></span>

<span data-ttu-id="37ac7-282">このチュートリアルの目的では、Azure で Service Fabric クラスターに Windows コンテナー ベースのアプリケーションをデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-282">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="37ac7-283">最初からの Service Fabric にデプロイすると、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="37ac7-283">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1. <span data-ttu-id="37ac7-284">Azure (または、別の環境) は、Service Fabric クラスターをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-284">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2. <span data-ttu-id="37ac7-285">Service Fabric クラスターに、アプリケーションと関連リソースをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-285">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="37ac7-286">シナリオ</span><span class="sxs-lookup"><span data-stu-id="37ac7-286">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="37ac7-287">シナリオ a:開発環境から Service Fabric クラスターに直接デプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-287">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![開発環境から Service Fabric クラスターに直接デプロイします。](./media/image5-9.png)

> <span data-ttu-id="37ac7-289">**図 5-9**</span><span class="sxs-lookup"><span data-stu-id="37ac7-289">**Figure 5-9.**</span></span> <span data-ttu-id="37ac7-290">開発環境から Service Fabric クラスターに直接デプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-290">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="37ac7-291">シナリオ b:Azure DevOps Services で CI/CD パイプラインから Service Fabric クラスターにデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-291">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps Services で CI/CD パイプラインから Service Fabric クラスターにデプロイします。](./media/image5-10.png)

<span data-ttu-id="37ac7-293">**図 5-10**</span><span class="sxs-lookup"><span data-stu-id="37ac7-293">**Figure 5-10.**</span></span> <span data-ttu-id="37ac7-294">Azure DevOps Services で CI/CD パイプラインから Service Fabric クラスターにデプロイします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-294">Deploy to a Service Fabric cluster from CI/CD pipelines in Azure DevOps Services</span></span>

## <a name="benefits"></a><span data-ttu-id="37ac7-295">利点</span><span class="sxs-lookup"><span data-stu-id="37ac7-295">Benefits</span></span>

<span data-ttu-id="37ac7-296">Service fabric クラスターへのデプロイの利点は、Kubernetes を使用する利点と似ています。</span><span class="sxs-lookup"><span data-stu-id="37ac7-296">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="37ac7-297">1 つの違いは、Service Fabric には、さらに成熟した運用環境と比較する Kubernetes バージョン 1.9 で Windows コンテナーのベータ フェーズでは、Kubernetes と Windows アプリケーション (2017 年 12 月)。</span><span class="sxs-lookup"><span data-stu-id="37ac7-297">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="37ac7-298">Kubernetes は、Linux のさらに成熟した環境です。</span><span class="sxs-lookup"><span data-stu-id="37ac7-298">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="37ac7-299">Azure Service Fabric を使用する主な利点は、(既存のノードでは内部スケーラビリティ) を使用して数に基づいてするコンテナー インスタンスの数に基づいて、アプリケーションをスケールすることができます、実稼働可能な環境を取得します。ノードまたはクラスター (クラスターのグローバルなスケーラビリティ) 内の Vm。</span><span class="sxs-lookup"><span data-stu-id="37ac7-299">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="37ac7-300">Azure Service Fabric では、移植性をコンテナーと、アプリケーションの構成の両方を提供します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-300">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="37ac7-301">Azure では、クラスター化または独自のデータ センターに、オンプレミス インストールに Service Fabric ことができます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-301">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="37ac7-302">このようなでも別のクラウドでこの Service Fabric クラスターをインストールすることができます[Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/)します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-302">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="37ac7-303">Service Fabric を使用開発者を他のユーザーの間で、次の機能を容易にするコンテナーを中心としたインフラストラクチャの計画に考えた物理および仮想マシンに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="37ac7-303">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="37ac7-304">複数のコンテナーに基づくアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="37ac7-304">Applications based on multiple containers.</span></span>

- <span data-ttu-id="37ac7-305">Container instances と水平方向の自動スケールをレプリケートします。</span><span class="sxs-lookup"><span data-stu-id="37ac7-305">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="37ac7-306">名前付けと (たとえば、内部 DNS) を検出します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-306">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="37ac7-307">負荷を分散します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-307">Balancing loads.</span></span>

- <span data-ttu-id="37ac7-308">ローリング更新。</span><span class="sxs-lookup"><span data-stu-id="37ac7-308">Rolling updates.</span></span>

- <span data-ttu-id="37ac7-309">シークレットを配布します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-309">Distributing secrets.</span></span>

- <span data-ttu-id="37ac7-310">アプリケーションの正常性を確認します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-310">Application health checks.</span></span>

<span data-ttu-id="37ac7-311">次の機能では、(他のオーケストレーターとの比較)、Service Fabric で排他的です。</span><span class="sxs-lookup"><span data-stu-id="37ac7-311">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="37ac7-312">ステートフル サービスの機能は、Reliable Services アプリケーションのモデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-312">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="37ac7-313">アクター パターン、Reliable Actors アプリケーション モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-313">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="37ac7-314">Windows または Linux のコンテナーに加え、ベア ボーン プロセスを展開します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-314">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="37ac7-315">高度なローリング アップデートと正常性チェック</span><span class="sxs-lookup"><span data-stu-id="37ac7-315">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="37ac7-316">次の手順</span><span class="sxs-lookup"><span data-stu-id="37ac7-316">Next steps</span></span>

<span data-ttu-id="37ac7-317">このコンテンツの詳細については、GitHub wiki 詳細します。</span><span class="sxs-lookup"><span data-stu-id="37ac7-317">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)>

> [!div class="step-by-step"]
> <span data-ttu-id="37ac7-318">[前へ](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [次へ](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="37ac7-318">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
