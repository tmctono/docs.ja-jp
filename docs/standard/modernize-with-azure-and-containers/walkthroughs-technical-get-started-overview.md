---
title: チュートリアルと技術的な概要
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |チュートリアルと技術的な概要します。
ms.date: 04/28/2018
ms.openlocfilehash: 1ae6f3c1e739184356b97fa96e74bab402bf1d2a
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832971"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="81266-103">チュートリアルと技術的な概要</span><span class="sxs-lookup"><span data-stu-id="81266-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="81266-104">この電子ブックのサイズを制限するには、その他の技術ドキュメントと完全なチュートリアルで行われた使用可能な GitHub リポジトリ。</span><span class="sxs-lookup"><span data-stu-id="81266-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="81266-105">オンラインの一連のこの章で説明したチュートリアルでは、Windows コンテナー、および Azure へのデプロイに基づいて複数の環境のステップ バイ ステップのセットアップについて説明します。</span><span class="sxs-lookup"><span data-stu-id="81266-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="81266-106">次のセクションでは、各チュートリアルでは、その目標と高度なビジョンを通知し、関連するタスクを次の図は、について説明します。</span><span class="sxs-lookup"><span data-stu-id="81266-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="81266-107">自体のチュートリアルを入手できますで、 *eShopModernizing*でアプリの GitHub リポジトリ wiki<https://github.com/dotnet-architecture/eShopModernizing/wiki>します。</span><span class="sxs-lookup"><span data-stu-id="81266-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="81266-108">技術チュートリアルの一覧</span><span class="sxs-lookup"><span data-stu-id="81266-108">Technical walkthrough list</span></span>

<span data-ttu-id="81266-109">次の概要チュートリアルでは、リフトとシフト、コンテナーを使用しておよび Azure で複数の展開のオプションを使用して、移動できるサンプル アプリの包括的な一貫性のあるの技術的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="81266-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="81266-110">次のチュートリアルの各アプリで使用して、新しいサンプル eShopLegacy と eShopModernizing、GitHub で利用できる<https://github.com/dotnet-architecture/eShopModernizing>します。</span><span class="sxs-lookup"><span data-stu-id="81266-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="81266-111">**EShop レガシ アプリ (現代化する基準アプリ) のツアー**</span><span class="sxs-lookup"><span data-stu-id="81266-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="81266-112">**Windows コンテナーで既存 ASP.NET web アプリ (WebForms および MVC) のコンテナー格納します。**</span><span class="sxs-lookup"><span data-stu-id="81266-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="81266-113">**Windows コンテナーで既存の WCF サービス (N 層アプリ) のコンテナー格納します。**</span><span class="sxs-lookup"><span data-stu-id="81266-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="81266-114">**Azure Vm への Windows コンテナー ベース アプリをデプロイします。**</span><span class="sxs-lookup"><span data-stu-id="81266-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="81266-115">**Windows コンテナー ベースのアプリを Azure Container Service で Kubernetes にデプロイします。**</span><span class="sxs-lookup"><span data-stu-id="81266-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="81266-116">チュートリアル 1:EShop レガシ アプリケーションのツアー</span><span class="sxs-lookup"><span data-stu-id="81266-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="81266-117">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="81266-117">Technical walkthrough availability</span></span>

<span data-ttu-id="81266-118">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。</span><span class="sxs-lookup"><span data-stu-id="81266-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="81266-119">wiki のチュートリアルは eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="81266-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="81266-120">概要</span><span class="sxs-lookup"><span data-stu-id="81266-120">Overview</span></span>

<span data-ttu-id="81266-121">このチュートリアルでは、次の 3 つのサンプルのレガシ アプリケーションの最初の実装を確認できます。</span><span class="sxs-lookup"><span data-stu-id="81266-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="81266-122">最初の 2 つのサンプル web アプリは、モノリシック アーキテクチャがあるし、従来の ASP.NET を使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="81266-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="81266-123">1 つのアプリケーション ベースは ASP.NET 4.x MVC;2 番目のアプリケーションは、ASP.NET 4.x Web フォームに基づきます。</span><span class="sxs-lookup"><span data-stu-id="81266-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="81266-124">3 番目のアプリは、WinForms アプリをクライアントとサーバー側で構成されます 3 層アプリ[Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md)サービス。</span><span class="sxs-lookup"><span data-stu-id="81266-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="81266-125">これらすべてのアプリケーションは、 [eShopModernizing GitHub リポジトリ](https://github.com/dotnet-architecture/eShopModernizing)します。</span><span class="sxs-lookup"><span data-stu-id="81266-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="81266-126">目的</span><span class="sxs-lookup"><span data-stu-id="81266-126">Goals</span></span>

<span data-ttu-id="81266-127">このチュートリアルの主な目的は、これらのアプリとそのコードと構成について詳しく理解することです。</span><span class="sxs-lookup"><span data-stu-id="81266-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="81266-128">生成およびテスト目的で、SQL database を使用せず、モックのデータを使用できるように、アプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="81266-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="81266-129">このオプションの構成は、分離された方法で依存関係の挿入に基づいています。</span><span class="sxs-lookup"><span data-stu-id="81266-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="81266-130">シナリオ 1:ASP.NET Web アプリ</span><span class="sxs-lookup"><span data-stu-id="81266-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="81266-131">次の図は、元の従来の ASP.NET web アプリケーションの簡単なシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="81266-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![元の従来の ASP.NET web アプリケーションのアーキテクチャの単純なシナリオ](./media/image5-1.png)

<span data-ttu-id="81266-133">ビジネス ドメインの観点から両方のアプリは管理機能に同じカタログを提供します。</span><span class="sxs-lookup"><span data-stu-id="81266-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="81266-134">EShop エンタープライズ チームのメンバーでは、製品カタログの編集を表示したり、アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="81266-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="81266-135">次の図は、最初のアプリのスクリーン ショットを示します。</span><span class="sxs-lookup"><span data-stu-id="81266-135">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC と ASP.NET Web フォーム アプリケーション (既存の/レガシ テクノロジ)](./media/image5-2.png)

<span data-ttu-id="81266-137">依存関係 asp.net 4.x または以前のバージョン (MVC または Web フォームか) はこれらのアプリケーションは、ASP.NET Core MVC を使用してコードを書き直すが完全にしない限り、.NET Core で動作しません。</span><span class="sxs-lookup"><span data-stu-id="81266-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="81266-138">シナリオ 2:WCF サービスとクライアント アプリの WinForms (3 層アプリ)</span><span class="sxs-lookup"><span data-stu-id="81266-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="81266-139">次の図は、元の 3 層のレガシ アプリケーションの簡単なシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="81266-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![WCF サービスと、元のレガシ 3 層アプリおよび WinForms クライアント アプリのアーキテクチャの単純なシナリオ](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="81266-141">利点</span><span class="sxs-lookup"><span data-stu-id="81266-141">Benefits</span></span>

<span data-ttu-id="81266-142">このチュートリアルの利点はシンプルです。コードと最初のアプリを使用して理解します。</span><span class="sxs-lookup"><span data-stu-id="81266-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="81266-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="81266-143">Next steps</span></span>

<span data-ttu-id="81266-144">このコンテンツの詳細については、GitHub wiki 詳細します。</span><span class="sxs-lookup"><span data-stu-id="81266-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="81266-145">ASP.NET MVC、ベースラインをツアーと Web フォーム「レガシ」アプリ</span><span class="sxs-lookup"><span data-stu-id="81266-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="81266-146">WCF サービスの基準と WinForms (3 層) の「レガシ」アプリのツアー</span><span class="sxs-lookup"><span data-stu-id="81266-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="81266-147">チュートリアル 2:Windows コンテナーで既存の .NET アプリケーションのコンテナー格納します。</span><span class="sxs-lookup"><span data-stu-id="81266-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="81266-148">概要</span><span class="sxs-lookup"><span data-stu-id="81266-148">Overview</span></span>

<span data-ttu-id="81266-149">MVC、Web フォーム、または WCF では、運用、開発、およびテスト環境に基づくように、既存の .NET アプリケーションの展開を向上させるために Windows コンテナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="81266-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="81266-150">目的</span><span class="sxs-lookup"><span data-stu-id="81266-150">Goals</span></span>

<span data-ttu-id="81266-151">このチュートリアルの目的では、既存の .NET Framework アプリケーションをコンテナー化のいくつかのオプションを説明します。</span><span class="sxs-lookup"><span data-stu-id="81266-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="81266-152">次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="81266-152">You can:</span></span>

- <span data-ttu-id="81266-153">使用して、アプリケーションをコンテナー化[Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 またはそれ以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="81266-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="81266-154">手動で追加することで、アプリケーションをコンテナー化、 [Dockerfile](https://docs.docker.com/engine/reference/builder/)、しを使用して、 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)します。</span><span class="sxs-lookup"><span data-stu-id="81266-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="81266-155">使用して、アプリケーションをコンテナー化、 [Img2Docker](https://github.com/docker/communitytools-image2docker-win)ツール (Docker からオープン ソース ツール)。</span><span class="sxs-lookup"><span data-stu-id="81266-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="81266-156">このチュートリアルは、Docker 方法は、Visual Studio 2017 Tools について重点的に取り上げます。 が、その他の 2 つのアプローチは Dockerfile を使用してに関して類似しています。</span><span class="sxs-lookup"><span data-stu-id="81266-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="81266-157">シナリオ 1:コンテナー化された ASP.NET web アプリ</span><span class="sxs-lookup"><span data-stu-id="81266-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="81266-158">次の図は、コンテナー化された eShop 従来の web アプリのアプリケーションのシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="81266-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![簡素化されたアーキテクチャの図は、開発環境での ASP.NET アプリケーションをコンテナー化されました。](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="81266-160">シナリオ 2:コンテナー化された WCF サービス</span><span class="sxs-lookup"><span data-stu-id="81266-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="81266-161">次の図は、コンテナー化された WCF サービスと 3 層アプリケーションのシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="81266-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![開発環境でコンテナー化された WCF サービスのアーキテクチャ図を簡略化](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="81266-163">利点</span><span class="sxs-lookup"><span data-stu-id="81266-163">Benefits</span></span>

<span data-ttu-id="81266-164">これには、コンテナーで、モノリシック アプリケーションを実行する利点があります。</span><span class="sxs-lookup"><span data-stu-id="81266-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="81266-165">最初に、アプリケーションのイメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="81266-165">First, you create an image for the application.</span></span> <span data-ttu-id="81266-166">その時点からは、すべてのデプロイは、同じ環境内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="81266-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="81266-167">すべてのコンテナーで、同じ OS バージョンを使用して、同じバージョンの依存関係のインストールが同じ .NET framework のバージョンを使用しておよびは同じプロセスを使用して構築されています。</span><span class="sxs-lookup"><span data-stu-id="81266-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="81266-168">基本的には、Docker イメージを使用して、アプリケーションの依存関係を制御します。</span><span class="sxs-lookup"><span data-stu-id="81266-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="81266-169">依存関係は、コンテナーをデプロイするときに、アプリケーションと共に移動します。</span><span class="sxs-lookup"><span data-stu-id="81266-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="81266-170">その他の利点は、開発者が Windows のコンテナーによって提供される一貫した環境でアプリケーションを実行できることです。</span><span class="sxs-lookup"><span data-stu-id="81266-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="81266-171">特定のバージョンでのみ表示される問題は、ステージング環境または運用環境で表示することではなく、すぐに発見できます。</span><span class="sxs-lookup"><span data-stu-id="81266-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="81266-172">開発チームのメンバーで使用される開発環境での相違点は問題のコンテナーでアプリケーションの実行時に小さいです。</span><span class="sxs-lookup"><span data-stu-id="81266-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="81266-173">コンテナー化されたアプリケーションでは、flatter スケール アウト曲線もあります。</span><span class="sxs-lookup"><span data-stu-id="81266-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="81266-174">コンテナー化されたアプリには、VM または物理マシンのマシンあたりの定期的なアプリケーション展開と比較する複数のアプリケーションとサービス インスタンスが (コンテナーに基づく) が有効にします。</span><span class="sxs-lookup"><span data-stu-id="81266-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="81266-175">これにより、高密度、および必要な少なくリソース、Kubernetes などのオーケストレーターを使用する場合に特にです。</span><span class="sxs-lookup"><span data-stu-id="81266-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="81266-176">コンテナリゼーションは、理想的な状況では、アプリケーション コードに変更を加える必要ありません (C\#)。</span><span class="sxs-lookup"><span data-stu-id="81266-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="81266-177">ほとんどのシナリオでは、Docker の展開のメタデータ ファイル (Dockerfile と Docker Compose ファイル) だけ必要です。</span><span class="sxs-lookup"><span data-stu-id="81266-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="81266-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="81266-178">Next steps</span></span>

<span data-ttu-id="81266-179">このコンテンツの詳細については、GitHub wiki 詳細します。</span><span class="sxs-lookup"><span data-stu-id="81266-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="81266-180">Windows コンテナーと Docker で .NET Framework web アプリをコンテナー化する方法</span><span class="sxs-lookup"><span data-stu-id="81266-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="81266-181">WCF サービスへの Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="81266-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="81266-182">チュートリアル 3:Azure Vm への Windows コンテナー ベース アプリをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="81266-183">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="81266-183">Technical walkthrough availability</span></span>

<span data-ttu-id="81266-184">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。 <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="81266-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="81266-185">概要</span><span class="sxs-lookup"><span data-stu-id="81266-185">Overview</span></span>

<span data-ttu-id="81266-186">Azure で Windows Server 2016 仮想マシン (VM) 上の Docker ホストに展開するには、開発/テスト/ステージング環境をすばやくセットアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="81266-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="81266-187">アプリを検証するには、テスト担当者またはビジネス ユーザーの一般的な場所も提供します。</span><span class="sxs-lookup"><span data-stu-id="81266-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="81266-188">Vm は、サービス (IaaS) の実稼働環境として有効なインフラストラクチャをすることができます。</span><span class="sxs-lookup"><span data-stu-id="81266-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="81266-189">目的</span><span class="sxs-lookup"><span data-stu-id="81266-189">Goals</span></span>

<span data-ttu-id="81266-190">このチュートリアルの目的では、Windows Server 2016 またはそれ以降のバージョンに基づいて Azure Vm を Windows コンテナーを展開する場合がある複数の代替手段を説明します。</span><span class="sxs-lookup"><span data-stu-id="81266-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="81266-191">シナリオ</span><span class="sxs-lookup"><span data-stu-id="81266-191">Scenarios</span></span>

<span data-ttu-id="81266-192">このチュートリアルでは、いくつかのシナリオがについて説明します。</span><span class="sxs-lookup"><span data-stu-id="81266-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="81266-193">シナリオ a:Docker エンジンの接続を介して開発用 PC から Azure VM へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Docker エンジンの接続を介して開発用 PC から Azure VM へのデプロイします。](./media/image5-4.png)

<span data-ttu-id="81266-195">**図 5-4**</span><span class="sxs-lookup"><span data-stu-id="81266-195">**Figure 5-4.**</span></span> <span data-ttu-id="81266-196">Docker エンジンの接続を介して開発用 PC から Azure VM へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="81266-197">シナリオ b:Docker レジストリを使用して Azure VM にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Docker レジストリを使用して Azure VM にデプロイします。](./media/image5-5.png)

<span data-ttu-id="81266-199">**図 5-5**</span><span class="sxs-lookup"><span data-stu-id="81266-199">**Figure 5-5.**</span></span> <span data-ttu-id="81266-200">Docker レジストリを使用して Azure VM にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="81266-201">C: のシナリオAzure DevOps Services で CI/CD パイプラインから Azure VM へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps Services で CI/CD パイプラインから Azure VM へのデプロイします。](./media/image5-6.png)

<span data-ttu-id="81266-203">**図 5-6**</span><span class="sxs-lookup"><span data-stu-id="81266-203">**Figure 5-6.**</span></span> <span data-ttu-id="81266-204">Azure DevOps Services で CI/CD パイプラインから Azure VM へのデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="81266-205">Windows コンテナー用の azure Vm</span><span class="sxs-lookup"><span data-stu-id="81266-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="81266-206">Windows コンテナーの azure Vm は Vm の Windows Server 2016、Windows 10、またはそれ以降のバージョンに基づいて、Docker エンジンの両方を設定します。</span><span class="sxs-lookup"><span data-stu-id="81266-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="81266-207">ほとんどの場合は、Windows Server 2016 は Azure Vm で使用されます。</span><span class="sxs-lookup"><span data-stu-id="81266-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="81266-208">Azure は、現在という名前の VM を提供します。 **Windows Server 2016 with Containers**します。</span><span class="sxs-lookup"><span data-stu-id="81266-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="81266-209">この VM を使用すると、Windows Server Core または Windows Nano Server のいずれかで、新しい Windows Server コンテナー機能をお試しください。</span><span class="sxs-lookup"><span data-stu-id="81266-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="81266-210">コンテナー OS イメージがインストールされている場合、および Docker を使用する準備が VM でし。</span><span class="sxs-lookup"><span data-stu-id="81266-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="81266-211">利点</span><span class="sxs-lookup"><span data-stu-id="81266-211">Benefits</span></span>

<span data-ttu-id="81266-212">Windows コンテナーは、Azure にデプロイするときに、オンプレミス Windows Server 2016 の Vm を展開できますが、すぐに使用できる Windows Server コンテナーの Vm を開始する簡単な方法を取得します。</span><span class="sxs-lookup"><span data-stu-id="81266-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="81266-213">テスト担当者、および自動のスケーラビリティを Azure の仮想マシン スケール セットにアクセスできる一般的なオンラインの場所も表示します。</span><span class="sxs-lookup"><span data-stu-id="81266-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="81266-214">次の手順</span><span class="sxs-lookup"><span data-stu-id="81266-214">Next steps</span></span>

<span data-ttu-id="81266-215">このコンテンツの詳細については、GitHub wiki 詳細します。</span><span class="sxs-lookup"><span data-stu-id="81266-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="81266-216">チュートリアル 4:Azure Container Instances (ACI) への Windows コンテナー ベースのアプリをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="81266-217">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="81266-217">Technical walkthrough availability</span></span>

<span data-ttu-id="81266-218">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。</span><span class="sxs-lookup"><span data-stu-id="81266-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="81266-219">[ACI (Azure Container Instances) に、アプリを展開します。](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="81266-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="81266-220">概要</span><span class="sxs-lookup"><span data-stu-id="81266-220">Overview</span></span>

<span data-ttu-id="81266-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/)はコンテナーの 1 つのインスタンスをデプロイするコンテナーの開発/テスト/ステージング環境に最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="81266-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="81266-222">目的</span><span class="sxs-lookup"><span data-stu-id="81266-222">Goals</span></span>

<span data-ttu-id="81266-223">このチュートリアルでは、主なシナリオ Azure Container Instances (ACI) ACI に eShopModernizing アプリをデプロイする方法を Windows コンテナーをデプロイするときにします。</span><span class="sxs-lookup"><span data-stu-id="81266-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="81266-224">シナリオ</span><span class="sxs-lookup"><span data-stu-id="81266-224">Scenarios</span></span>

<span data-ttu-id="81266-225">ACI に eShopModernizing アプリを展開する 1 つまたはすべてのアプリ (MVC アプリ、web フォーム アプリケーションまたは WCF サービス) の展開などについてのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="81266-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="81266-226">次のシナリオを次に示すことができます、コンテナーとして ACI (Azure Container Instances) に ASP.NET MVC アプリとこれらの両方に展開されている SQL Server のコンテナーを表示します。</span><span class="sxs-lookup"><span data-stu-id="81266-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![開発環境から ACI へのデプロイします。](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="81266-228">利点</span><span class="sxs-lookup"><span data-stu-id="81266-228">Benefits</span></span>

<span data-ttu-id="81266-229">Azure Container Instances では、簡単に作成し、仮想マシンをプロビジョニングしたり、上位レベルのサービスを採用したりしなくても、Azure で Docker コンテナーを管理します。</span><span class="sxs-lookup"><span data-stu-id="81266-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="81266-230">、ACI で直接 Azure で Windows コンテナーのデプロイし、への公開を完全修飾ドメイン名 (FQDN) を使用してインターネットに数秒 (Docker Hub や Azure コンテナーのような Docker レジストリで準備ができて、Windows コンテナー イメージがある場合にすることができますレジストリの場合)。</span><span class="sxs-lookup"><span data-stu-id="81266-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="81266-231">注意事項</span><span class="sxs-lookup"><span data-stu-id="81266-231">Considerations</span></span>

<span data-ttu-id="81266-232">いずれかの完全な .NET Framework と Windows コンテナーのデプロイ]、[ASP.NET または SQL Server Azure Container Instances (ACI) には、Docker イメージがあるためです (Windows コンテナーでの Windows Server 2016) などの通常の Docker ホストにデプロイする場合と非常に高速ではありません(Docker レジストリからプルされた) たびにダウンロードし、これは、独自の docker ホスト (永続的にオンラインを維持するよりもよりもコストは、SQL コンテナー イメージ (15.1 GB) と ASP.NET のコンテナー イメージ (13.9 GB) のサイズが非常に大きい場合、Azure で Windows コンテナーの VM で Windows Server 2016) することで、全体のオーケストレーター Kubernetes Azure (AKS) では、その一方で、運用環境のデプロイに最適のようにします。</span><span class="sxs-lookup"><span data-stu-id="81266-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="81266-233">メインの結論としては、Azure Container Instances を使用して開発/テスト シナリオの場合と CI/CD パイプラインの非常に魅力的なオプション。</span><span class="sxs-lookup"><span data-stu-id="81266-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="81266-234">次の手順</span><span class="sxs-lookup"><span data-stu-id="81266-234">Next steps</span></span>

<span data-ttu-id="81266-235">このコンテンツの詳細については、GitHub wiki 詳細します。</span><span class="sxs-lookup"><span data-stu-id="81266-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="81266-236">チュートリアル 5:Windows コンテナー ベースのアプリを Azure Container Service で Kubernetes にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="81266-237">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="81266-237">Technical walkthrough availability</span></span>

<span data-ttu-id="81266-238">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。</span><span class="sxs-lookup"><span data-stu-id="81266-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="81266-239">概要</span><span class="sxs-lookup"><span data-stu-id="81266-239">Overview</span></span>

<span data-ttu-id="81266-240">Windows コンテナーに基づいているアプリケーションはすばやく離れたから IaaS Vm の移動、さらに、プラットフォームを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81266-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="81266-241">これを簡単に高いスケーラビリティを実現するために必要なよりスケーラビリティ、自動し、大幅に向上のデプロイとバージョン管理を自動化します。</span><span class="sxs-lookup"><span data-stu-id="81266-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="81266-242">これらの目標を達成するには、orchestrator を使用して[Kubernetes](https://kubernetes.io/)で使用できる、 [Azure Container Services](https://azure.microsoft.com/services/container-service/)します。</span><span class="sxs-lookup"><span data-stu-id="81266-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="81266-243">目的</span><span class="sxs-lookup"><span data-stu-id="81266-243">Goals</span></span>

<span data-ttu-id="81266-244">このチュートリアルの目標は Kubernetes への Windows コンテナー ベースのアプリケーションをデプロイする方法を理解する (とも呼ばれる*K8s*) で Azure Container Service。</span><span class="sxs-lookup"><span data-stu-id="81266-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="81266-245">ゼロからの Kubernetes にデプロイすると、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="81266-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="81266-246">Azure Container Service に Kubernetes クラスターをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="81266-247">Kubernetes クラスターに、アプリケーションと関連リソースをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="81266-248">シナリオ</span><span class="sxs-lookup"><span data-stu-id="81266-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="81266-249">シナリオ a:開発環境から Kubernetes クラスターに直接デプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![開発環境から Kubernetes クラスターに直接デプロイします。](./media/image5-7.png)

<span data-ttu-id="81266-251">**図 5-7**</span><span class="sxs-lookup"><span data-stu-id="81266-251">**Figure 5-7.**</span></span> <span data-ttu-id="81266-252">開発環境から Kubernetes クラスターに直接デプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="81266-253">シナリオ b:Azure DevOps Services で CI/CD パイプラインから Kubernetes クラスターにデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Azure DevOps Services で CI/CD パイプラインから Kubernetes クラスターにデプロイします。](./media/image5-8.png)

<span data-ttu-id="81266-255">**図 5-8**</span><span class="sxs-lookup"><span data-stu-id="81266-255">**Figure 5-8.**</span></span> <span data-ttu-id="81266-256">Azure DevOps Services で CI/CD パイプラインから Kubernetes クラスターにデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="81266-257">利点</span><span class="sxs-lookup"><span data-stu-id="81266-257">Benefits</span></span>

<span data-ttu-id="81266-258">Kubernetes でのクラスターにデプロイする多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="81266-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="81266-259">最大のメリットは (既存のノードでは内部スケーラビリティ) を使用して、クラスター (ノードまたは Vm の数に基づくコンテナー インスタンスの数に基づいて、アプリケーションをスケールすることができます、実稼働可能な環境を取得します。グローバルなスケーラビリティ、クラスターの)。</span><span class="sxs-lookup"><span data-stu-id="81266-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="81266-260">Azure Container Service では、Azure 向けに人気のあるオープン ソース ツールとテクノロジを最適化します。</span><span class="sxs-lookup"><span data-stu-id="81266-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="81266-261">移植性、コンテナーと、アプリケーションの構成の両方を提供する、開いているソリューションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81266-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="81266-262">ホストの数、サイズを選択し、orchestrator ツール-コンテナーのサービスが他のすべてを処理します。</span><span class="sxs-lookup"><span data-stu-id="81266-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="81266-263">Kubernetes で開発者を他のユーザーの間で、次の機能を容易にするコンテナーを中心としたインフラストラクチャの計画に物理および仮想マシン、考えたに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="81266-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="81266-264">複数のコンテナーに基づくアプリケーション</span><span class="sxs-lookup"><span data-stu-id="81266-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="81266-265">Container instances と水平方向の自動スケールをレプリケートします。</span><span class="sxs-lookup"><span data-stu-id="81266-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="81266-266">名前付けと (たとえば、内部 DNS) の検出</span><span class="sxs-lookup"><span data-stu-id="81266-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="81266-267">負荷を分散</span><span class="sxs-lookup"><span data-stu-id="81266-267">Balancing loads</span></span>

- <span data-ttu-id="81266-268">ローリング アップデート</span><span class="sxs-lookup"><span data-stu-id="81266-268">Rolling updates</span></span>

- <span data-ttu-id="81266-269">シークレットを配布します。</span><span class="sxs-lookup"><span data-stu-id="81266-269">Distributing secrets</span></span>

- <span data-ttu-id="81266-270">アプリケーションの正常性チェック</span><span class="sxs-lookup"><span data-stu-id="81266-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="81266-271">次の手順</span><span class="sxs-lookup"><span data-stu-id="81266-271">Next steps</span></span>

<span data-ttu-id="81266-272">このコンテンツの詳細については、GitHub wiki 詳細します。 <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="81266-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="81266-273">チュートリアル 6:コンテナー用の Azure App Service への Windows コンテナー ベースのアプリをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="81266-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="81266-274">テクニカル チュートリアルの可用性</span><span class="sxs-lookup"><span data-stu-id="81266-274">Technical walkthrough availability</span></span>

<span data-ttu-id="81266-275">完全な技術チュートリアル、eShopModernizing GitHub リポジトリ wiki で提供されています。</span><span class="sxs-lookup"><span data-stu-id="81266-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="81266-276">概要</span><span class="sxs-lookup"><span data-stu-id="81266-276">Overview</span></span>

<span data-ttu-id="81266-277">Windows コンテナーを使用して単純なコンテナー化されたアプリケーションは、コンテナーの Azure App Service に簡単にデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="81266-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="81266-278">これは、ほとんどの Windows コンテナー ベースのアプリケーションの推奨されるアプローチです。</span><span class="sxs-lookup"><span data-stu-id="81266-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="81266-279">目的</span><span class="sxs-lookup"><span data-stu-id="81266-279">Goals</span></span>

<span data-ttu-id="81266-280">このチュートリアルの目的では、(Docker Hub または Azure Container Registry) のレジストリからコンテナーを Azure App Service に Windows コンテナー ベース アプリケーションを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="81266-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="81266-281">シナリオ</span><span class="sxs-lookup"><span data-stu-id="81266-281">Scenario</span></span>

![Windows コンテナー ベースのアプリのコンテナーの Azure App Service をデプロイします。](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="81266-283">利点</span><span class="sxs-lookup"><span data-stu-id="81266-283">Benefits</span></span>

<span data-ttu-id="81266-284">Azure App Service の PaaS の特典と組み合わせて使用するコンテナーのメリットを提供するコンテナー用の Azure App Service に展開します。</span><span class="sxs-lookup"><span data-stu-id="81266-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="81266-285">App service では、垂直方向および水平方向に簡単にスケールできるし、変化する需要に合わせて自動スケールするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="81266-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="81266-286">ダウンタイムなしで更新プログラムを実行できるし、レジストリから継続的なデプロイの構成は簡単にも構成します。</span><span class="sxs-lookup"><span data-stu-id="81266-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

## <a name="next-steps"></a><span data-ttu-id="81266-287">次の手順</span><span class="sxs-lookup"><span data-stu-id="81266-287">Next steps</span></span>

<span data-ttu-id="81266-288">このコンテンツの詳細については、GitHub wiki 詳細します。 <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span><span class="sxs-lookup"><span data-stu-id="81266-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="81266-289">[前へ](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [次へ](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="81266-289">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
