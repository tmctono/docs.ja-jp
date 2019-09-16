---
title: Azure の開発プロセス
description: ASP.NET Core および Azure での最新の Web アプリケーションの設計 | Azure の開発プロセス
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 830271d76e5a87ed782d81fa9491328c580f0f87
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849589"
---
# <a name="development-process-for-azure"></a><span data-ttu-id="f21dc-103">Azure の開発プロセス</span><span class="sxs-lookup"><span data-stu-id="f21dc-103">Development process for Azure</span></span>

> <span data-ttu-id="f21dc-104">_"クラウドを使用すれば、個人や小企業は指をパチンと鳴らすだけでエンタープライズ クラスのサービスをすぐにセットアップできます。"_</span><span class="sxs-lookup"><span data-stu-id="f21dc-104">_"With the cloud, individuals and small businesses can snap their fingers and instantly set up enterprise-class services."_</span></span>  
> <span data-ttu-id="f21dc-105">_- Roy Stephan_</span><span class="sxs-lookup"><span data-stu-id="f21dc-105">_- Roy Stephan_</span></span>

## <a name="vision"></a><span data-ttu-id="f21dc-106">ビジョン</span><span class="sxs-lookup"><span data-stu-id="f21dc-106">Vision</span></span>

> <span data-ttu-id="f21dc-107">*Visual Studio または dotnet CLI および Visual Studio Code または任意のエディターを使用して、好きな方法で適切に設計された ASP .NET Core アプリケーションを開発します。*</span><span class="sxs-lookup"><span data-stu-id="f21dc-107">*Develop well-designed ASP .NET Core applications the way you like, using Visual Studio or the dotnet CLI and Visual Studio Code or your editor of choice.*</span></span>

## <a name="development-environment-for-aspnet-core-apps"></a><span data-ttu-id="f21dc-108">ASP.NET Core アプリの開発環境</span><span class="sxs-lookup"><span data-stu-id="f21dc-108">Development environment for ASP.NET Core apps</span></span>

### <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="f21dc-109">開発ツールの選択:IDE またはエディター</span><span class="sxs-lookup"><span data-stu-id="f21dc-109">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="f21dc-110">完全で強力な IDE または軽量でアジャイルなエディターのどちらを選んでも、Microsoft は ASP.NET Core アプリケーションの開発に対応できます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-110">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when developing ASP.NET Core applications.</span></span>

<span data-ttu-id="f21dc-111">**Visual Studio 2017。**</span><span class="sxs-lookup"><span data-stu-id="f21dc-111">**Visual Studio 2017.**</span></span> <span data-ttu-id="f21dc-112">*Visual Studio 2017* を使用する場合、 *.NET Core クロスプラットフォームの開発* ワークロードがインストールされている限り、ASP.NET Core アプリケーションを構築できます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-112">If you're using *Visual Studio 2017* you can build ASP.NET Core applications as long as you have the *.NET Core cross-platform development* workload installed.</span></span> <span data-ttu-id="f21dc-113">図 10-1 には、Visual Studio 2017 の必要なワークロードのセットアップ ダイアログが示されています。</span><span class="sxs-lookup"><span data-stu-id="f21dc-113">Figure 10-1 shows the required workload in the Visual Studio 2017 setup dialog.</span></span>

![Visual Studio 2017 での .NET Core ワークロードのインストール](./media/image10-1.png)

<span data-ttu-id="f21dc-115">**図 10-1**</span><span class="sxs-lookup"><span data-stu-id="f21dc-115">**Figure 10-1.**</span></span> <span data-ttu-id="f21dc-116">Visual Studio 2017 での .NET Core ワークロードのインストール。</span><span class="sxs-lookup"><span data-stu-id="f21dc-116">Installing the .NET Core workload in Visual Studio 2017.</span></span>

[<span data-ttu-id="f21dc-117">Visual Studio 2017 をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f21dc-117">Download Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

<span data-ttu-id="f21dc-118">**Visual Studio Code と dotnet CLI** (Mac、Linux および Windows 用のクロスプラット フォーム ツール)。</span><span class="sxs-lookup"><span data-stu-id="f21dc-118">**Visual Studio Code and dotnet CLI** (Cross-Platform Tools for Mac, Linux and Windows).</span></span> <span data-ttu-id="f21dc-119">任意の開発言語をサポートする軽量なクロスプラットフォーム エディターを選択すると、Microsoft Visual Studio Code と dotnet CLI を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-119">If you prefer a lightweight and cross-platform editor supporting any development language, you can use Microsoft Visual Studio Code and the dotnet CLI.</span></span> <span data-ttu-id="f21dc-120">これらの製品は、開発者のワークフローを効率化する、簡単かつ堅牢性の高いエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f21dc-120">These products provide a simple yet robust experience that streamlines the developer workflow.</span></span> <span data-ttu-id="f21dc-121">さらに、Visual Studio Code は C\# および Web 開発の拡張機能をサポートし、エディター内での IntelliSense およびショートカット タスクを提供します。</span><span class="sxs-lookup"><span data-stu-id="f21dc-121">Additionally, Visual Studio Code supports extensions for C\# and web development, providing intellisense and shortcut-tasks within the editor.</span></span>

[<span data-ttu-id="f21dc-122">.NET Core SDK をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f21dc-122">Download the .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

[<span data-ttu-id="f21dc-123">Visual Studio Code をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f21dc-123">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)

## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a><span data-ttu-id="f21dc-124">Azure でホストされる ASP.NET Core アプリの開発ワークフロー</span><span class="sxs-lookup"><span data-stu-id="f21dc-124">Development workflow for Azure-hosted ASP.NET Core apps</span></span>

<span data-ttu-id="f21dc-125">アプリケーション開発のライフサイクルは、各開発者のコンピューターで開始されます。その場合、アプリは開発者の好みの言語でコーディングされ、ローカルでテストされます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-125">The application development lifecycle starts from each developer's machine, coding the app using their preferred language and testing it locally.</span></span> <span data-ttu-id="f21dc-126">開発者は好みのソース管理システムを選択できます。また、ビルド サーバーを使用するか、組み込みの Azure 機能に基づいて、継続的インテグレーション (CI) および/または継続的デリバリー/デプロイ (CD) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-126">Developers may choose their preferred source control system and can configure Continuous Integration (CI) and/or Continuous Delivery/Deployment (CD) using a build server or based on built-in Azure features.</span></span>

<span data-ttu-id="f21dc-127">CI/CD を使用して ASP.NET Core アプリケーションの開発を開始する場合は、Azure DevOps Services または組織独自の Team Foundation Server (TFS) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-127">To get started with developing an ASP.NET Core application using CI/CD, you can use Azure DevOps Services or your organization's own Team Foundation Server (TFS).</span></span>

### <a name="initial-setup"></a><span data-ttu-id="f21dc-128">初期セットアップ</span><span class="sxs-lookup"><span data-stu-id="f21dc-128">Initial setup</span></span>

<span data-ttu-id="f21dc-129">アプリのリリース パイプラインを作成するには、ソース管理でアプリケーション コードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f21dc-129">To create a release pipeline for your app, you need to have your application code in source control.</span></span> <span data-ttu-id="f21dc-130">ローカル リポジトリをセットアップし、それをチーム プロジェクトのリモート リポジトリに接続します。</span><span class="sxs-lookup"><span data-stu-id="f21dc-130">Set up a local repository and connect it to a remote repository in a team project.</span></span> <span data-ttu-id="f21dc-131">次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f21dc-131">Follow these instructions:</span></span>

- <span data-ttu-id="f21dc-132">[Git と Visual Studio でコードを共有する](https://docs.microsoft.com/azure/devops/git/share-your-code-in-git-vs)、または</span><span class="sxs-lookup"><span data-stu-id="f21dc-132">[Share your code with Git and Visual Studio](https://docs.microsoft.com/azure/devops/git/share-your-code-in-git-vs) or</span></span>

- [<span data-ttu-id="f21dc-133">TFVC と Visual Studio でコードを共有する</span><span class="sxs-lookup"><span data-stu-id="f21dc-133">Share your code with TFVC and Visual Studio</span></span>](https://docs.microsoft.com/azure/devops/tfvc/share-your-code-in-tfvc-vs)

<span data-ttu-id="f21dc-134">アプリケーションをデプロイする Azure App Service を作成します。</span><span class="sxs-lookup"><span data-stu-id="f21dc-134">Create an Azure App Service where you'll deploy your application.</span></span> <span data-ttu-id="f21dc-135">Azure Portal の App Services ブレードに移動して、Web アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f21dc-135">Create a Web App by going to the App Services blade on the Azure portal.</span></span> <span data-ttu-id="f21dc-136">[+追加] をクリックして Web アプリ テンプレートを選択し、[作成] をクリックして名前とその他の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="f21dc-136">Click +Add, select the Web App template, click Create, and provide a name and other details.</span></span> <span data-ttu-id="f21dc-137">Web アプリは {name}.azurewebsites.net からアクセス可能になります。</span><span class="sxs-lookup"><span data-stu-id="f21dc-137">The web app will be accessible from {name}.azurewebsites.net.</span></span>

![AzureWebApp](./media/image10-2.png)

<span data-ttu-id="f21dc-139">**図 10-2**</span><span class="sxs-lookup"><span data-stu-id="f21dc-139">**Figure 10-2.**</span></span> <span data-ttu-id="f21dc-140">Azure Portal での新しい Azure App Service Web アプリの作成。</span><span class="sxs-lookup"><span data-stu-id="f21dc-140">Creating a new Azure App Service Web App in the Azure Portal.</span></span>

<span data-ttu-id="f21dc-141">CI ビルド プロセスでは、新しいコードがプロジェクトのソース管理リポジトリにコミットされるたびに自動ビルドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-141">Your CI build process will perform an automated build whenever new code is committed to the project's source control repository.</span></span> <span data-ttu-id="f21dc-142">これにより、コードがビルドし (理想的には、自動テストに合格し)、デプロイされる可能性のあるフィードバックがすぐに返されます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-142">This gives you immediate feedback that the code builds (and, ideally, passes automated tests) and can potentially be deployed.</span></span> <span data-ttu-id="f21dc-143">この CI ビルドでは Web デプロイ パッケージ成果物が生成され、CD プロセスで使用するために公開されます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-143">This CI build will produce a web deploy package artifact and publish it for consumption by your CD process.</span></span>

[<span data-ttu-id="f21dc-144">CI ビルド プロセスを定義する</span><span class="sxs-lookup"><span data-stu-id="f21dc-144">Define your CI build process</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#ci)

<span data-ttu-id="f21dc-145">自分のチームのメンバーが新しいコードをコミットするたびにシステムによってビルドがキューに入れられるように、必ず、継続的インテグレーションを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="f21dc-145">Be sure to enable continuous integration so the system will queue a build whenever someone on your team commits new code.</span></span> <span data-ttu-id="f21dc-146">ビルドをテストし、成果物の 1 つとして Web デプロイ パッケージが生成されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f21dc-146">Test the build and verify that it is producing a web deploy package as one of its artifacts.</span></span>

<span data-ttu-id="f21dc-147">ビルドに成功すると、CD プロセスでは CI ビルドの結果が Azure Web アプリにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-147">When a build succeeds, your CD process will deploy the results of your CI build to your Azure web app.</span></span> <span data-ttu-id="f21dc-148">これを構成するには、*リリース*を作成して構成します。これは、Azure App Service にデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-148">To configure this, you create and configure a *Release*, which will deploy to your Azure App Service.</span></span>

[<span data-ttu-id="f21dc-149">CD リリース プロセスを定義する</span><span class="sxs-lookup"><span data-stu-id="f21dc-149">Define your CD release process</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#cd)

<span data-ttu-id="f21dc-150">CI/CD パイプラインが構成されたら、Web アプリを更新して、それをソース管理にコミットしてデプロイするだけです。</span><span class="sxs-lookup"><span data-stu-id="f21dc-150">Once your CI/CD pipeline is configured, you can simply make updates to your web app and commit them to source control to have them deployed.</span></span>

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a><span data-ttu-id="f21dc-151">Azure でホストされる ASP.NET Core アプリケーションの開発ワークフロー</span><span class="sxs-lookup"><span data-stu-id="f21dc-151">Workflow for developing Azure-hosted ASP.NET Core applications</span></span>

<span data-ttu-id="f21dc-152">Azure アカウントと CI/CD プロセスを構成したら、Azure でホストされる ASP.NET Core アプリケーションの開発は簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-152">Once you have configured your Azure account and your CI/CD process, developing Azure-hosted ASP.NET Core applications is simple.</span></span> <span data-ttu-id="f21dc-153">以下の図 10-3 に示されているように、Web アプリとして Azure App Service でホストされる、ASP.NET Core アプリを構築する場合に通常行う基本的な手順があります。</span><span class="sxs-lookup"><span data-stu-id="f21dc-153">The following are the basic steps you usually take when building an ASP.NET Core app, hosted in Azure App Service as a Web App, as illustrated in Figure 10-3.</span></span>

![EndToEndDevDeployWorkflow](./media/image10-3.png)

<span data-ttu-id="f21dc-155">**図 10-3**</span><span class="sxs-lookup"><span data-stu-id="f21dc-155">**Figure 10-3.**</span></span> <span data-ttu-id="f21dc-156">ASP.NET Core アプリを構築して Azure でホストするステップ バイ ステップのワークフロー</span><span class="sxs-lookup"><span data-stu-id="f21dc-156">Step-by-step workflow for building ASP.NET Core apps and hosting them in Azure</span></span>

#### <a name="step-1-local-dev-environment-inner-loop"></a><span data-ttu-id="f21dc-157">手順 1.</span><span class="sxs-lookup"><span data-stu-id="f21dc-157">Step 1.</span></span> <span data-ttu-id="f21dc-158">ローカル開発環境の内側のループ</span><span class="sxs-lookup"><span data-stu-id="f21dc-158">Local dev environment inner loop</span></span>

<span data-ttu-id="f21dc-159">Azure にデプロイする場合の ASP.NET Core アプリケーションの開発と、それ以外の場合のアプリケーションの開発は同じです。</span><span class="sxs-lookup"><span data-stu-id="f21dc-159">Developing your ASP.NET Core application for deployment to Azure is no different from developing your application otherwise.</span></span> <span data-ttu-id="f21dc-160">使い慣れたローカル開発環境を使用します。つまり、Visual Studio 2017 または dotnet CLI および Visual Studio Code または好みのエディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-160">Use the local development environment you're comfortable with, whether that's Visual Studio 2017 or the dotnet CLI and Visual Studio Code or your preferred editor.</span></span> <span data-ttu-id="f21dc-161">コードを記述し、変更を実行してデバッグし、自動テストを実行し、変更を共有ソース管理リポジトリにプッシュできるようになるまで、ソース管理へのローカル コミットを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-161">You can write code, run and debug your changes, run automated tests, and make local commits to source control until you're ready to push your changes to your shared source control repository.</span></span>

#### <a name="step-2-application-code-repository"></a><span data-ttu-id="f21dc-162">手順 2.</span><span class="sxs-lookup"><span data-stu-id="f21dc-162">Step 2.</span></span> <span data-ttu-id="f21dc-163">アプリケーション コード リポジトリ</span><span class="sxs-lookup"><span data-stu-id="f21dc-163">Application code repository</span></span>

<span data-ttu-id="f21dc-164">チームでコードを共有できるようになった場合は、常にローカル ソース リポジトリからチームの共有ソース リポジトリに変更をプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f21dc-164">Whenever you're ready to share your code with your team, you should push your changes from your local source repository to your team's shared source repository.</span></span> <span data-ttu-id="f21dc-165">カスタム ブランチで作業をしていた場合、この手順では通常、(たとえば、[pull request](https://docs.microsoft.com/azure/devops/git/pull-requests)を使用して) コードを共有ブランチにマージします。</span><span class="sxs-lookup"><span data-stu-id="f21dc-165">If you've been working in a custom branch, this step usually involves merging your code into a shared branch (perhaps by means of a [pull request](https://docs.microsoft.com/azure/devops/git/pull-requests)).</span></span>

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a><span data-ttu-id="f21dc-166">手順 3.</span><span class="sxs-lookup"><span data-stu-id="f21dc-166">Step 3.</span></span> <span data-ttu-id="f21dc-167">ビルド サーバー:継続的インテグレーション。</span><span class="sxs-lookup"><span data-stu-id="f21dc-167">Build Server: Continuous integration.</span></span> <span data-ttu-id="f21dc-168">ビルド、テスト、パッケージ</span><span class="sxs-lookup"><span data-stu-id="f21dc-168">build, test, package</span></span>

<span data-ttu-id="f21dc-169">共有アプリケーション コード リポジトリに新しいコミットが行われるたびに、ビルド サーバーで新しいビルドがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-169">A new build is triggered on the build server whenever a new commit is made to the shared application code repository.</span></span> <span data-ttu-id="f21dc-170">CI プロセスの一部として、このビルドで完全にアプリケーションをコンパイルし、自動テストを実行して、すべて予期したとおりに動作していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f21dc-170">As part of the CI process, this build should fully compile the application and run automated tests to confirm everything is working as expected.</span></span> <span data-ttu-id="f21dc-171">CI プロセスの最終結果は、デプロイの準備ができている、パッケージ化されたバージョンの Web アプリである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f21dc-171">The end result of the CI process should be a packaged version of the web app, ready for deployment.</span></span>

#### <a name="step-4-build-server-continuous-delivery"></a><span data-ttu-id="f21dc-172">手順 4.</span><span class="sxs-lookup"><span data-stu-id="f21dc-172">Step 4.</span></span> <span data-ttu-id="f21dc-173">ビルド サーバー:継続的デリバリー</span><span class="sxs-lookup"><span data-stu-id="f21dc-173">Build Server: Continuous delivery</span></span>

<span data-ttu-id="f21dc-174">ビルドが成功すると、CD プロセスは生成されたビルド成果物を選択します。</span><span class="sxs-lookup"><span data-stu-id="f21dc-174">Once a build has succeeded, the CD process will pick up the build artifacts produced.</span></span> <span data-ttu-id="f21dc-175">これには、Web デプロイ パッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-175">This will include a web deploy package.</span></span> <span data-ttu-id="f21dc-176">ビルド サーバーは Azure App Service にこのパッケージをデプロイして、既存のサービスを新しく作成されたものに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-176">The build server will deploy this package to Azure App Service, replacing any existing service with the newly created one.</span></span> <span data-ttu-id="f21dc-177">通常、この手順の対象はステージング環境ですが、一部のアプリケーションは CD プロセスを通じて運用環境に直接デプロイします。</span><span class="sxs-lookup"><span data-stu-id="f21dc-177">Typically this step targets a staging environment, but some applications deploy directly to production through a CD process.</span></span>

#### <a name="step-5-azure-app-service-web-app"></a><span data-ttu-id="f21dc-178">手順 5.</span><span class="sxs-lookup"><span data-stu-id="f21dc-178">Step 5.</span></span> <span data-ttu-id="f21dc-179">Azure App Service Web アプリ</span><span class="sxs-lookup"><span data-stu-id="f21dc-179">Azure App Service Web App</span></span>

<span data-ttu-id="f21dc-180">デプロイ後、ASP.NET Core アプリケーションは Azure App Service Web アプリのコンテキスト内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-180">Once deployed, the ASP.NET Core application runs within the context of an Azure App Service Web App.</span></span> <span data-ttu-id="f21dc-181">この Web アプリは、Azure Portal を使用して監視でき、さらに構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-181">This Web App can be monitored and further configured using the Azure Portal.</span></span>

#### <a name="step-6-production-monitoring-and-diagnostics"></a><span data-ttu-id="f21dc-182">手順 6.</span><span class="sxs-lookup"><span data-stu-id="f21dc-182">Step 6.</span></span> <span data-ttu-id="f21dc-183">運用の監視と診断</span><span class="sxs-lookup"><span data-stu-id="f21dc-183">Production monitoring and diagnostics</span></span>

<span data-ttu-id="f21dc-184">Web アプリの実行中に、アプリケーションの正常性を監視し、診断およびユーザー動作のデータを収集することができます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-184">While the Web App is running, you can monitor the health of the application and collect diagnostics and user behavior data.</span></span> <span data-ttu-id="f21dc-185">Application Insights は Visual Studio に含まれており、ASP.NET アプリの自動実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="f21dc-185">Application Insights is included in Visual Studio, and offers automatic instrumentation for ASP.NET apps.</span></span> <span data-ttu-id="f21dc-186">使用状況、例外、要求、パフォーマンス、およびログに関する情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="f21dc-186">It can provide you with information on usage, exceptions, requests, performance, and logs.</span></span>

## <a name="references"></a><span data-ttu-id="f21dc-187">参照</span><span class="sxs-lookup"><span data-stu-id="f21dc-187">References</span></span>

<span data-ttu-id="f21dc-188">**ASP.NET Core アプリを構築して Azure にデプロイする**</span><span class="sxs-lookup"><span data-stu-id="f21dc-188">**Build and Deploy Your ASP.NET Core App to Azure**</span></span>  
<https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core>

>[!div class="step-by-step"]
><span data-ttu-id="f21dc-189">[前へ](test-asp-net-core-mvc-apps.md)
>[次へ](azure-hosting-recommendations-for-asp-net-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="f21dc-189">[Previous](test-asp-net-core-mvc-apps.md)
[Next](azure-hosting-recommendations-for-asp-net-web-apps.md)</span></span>
