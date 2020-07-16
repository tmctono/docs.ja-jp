---
title: Azure .NET 開発者向けツール
description: Windows、Linux、Mac 環境から Azure .NET ライブラリを使い始めるためのツールを入手します。
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174835"
---
# <a name="azure-tools-for-developing-with-net"></a><span data-ttu-id="34a87-103">.NET で開発するための Azure ツール</span><span class="sxs-lookup"><span data-stu-id="34a87-103">Azure tools for developing with .NET</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="34a87-104">SDK のダウンロード</span><span class="sxs-lookup"><span data-stu-id="34a87-104">SDK downloads</span></span>

<span data-ttu-id="34a87-105">.NET 用 Azure ライブラリは [NuGet パッケージ](https://www.nuget.org/packages?q=windowsazureofficial)として実装されています。</span><span class="sxs-lookup"><span data-stu-id="34a87-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="34a87-106">Azure サービス別に整理されているリファレンス ドキュメントが必要であれば、[API リファレンス](/dotnet/api/overview/azure/?view=azure-dotnet)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34a87-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for reference documentation organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="34a87-107">開発ツール</span><span class="sxs-lookup"><span data-stu-id="34a87-107">Development tools</span></span>

<span data-ttu-id="34a87-108">Visual Studio には、Azure サービス向けの多くのツールが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="34a87-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="34a87-109">一部の Azure サービスでは、[Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/) などの追加のツールやエミュレーターが提供されています。</span><span class="sxs-lookup"><span data-stu-id="34a87-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="34a87-110">必要に応じて、その他のツールについては、Azure サービスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34a87-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="34a87-111">希望の開発環境を以下から選択します。</span><span class="sxs-lookup"><span data-stu-id="34a87-111">Select your preferred development environment below.</span></span>

## <a name="visual-studio-on-windows"></a>[<span data-ttu-id="34a87-112">Windows 上の Visual Studio</span><span class="sxs-lookup"><span data-stu-id="34a87-112">Visual Studio on Windows</span></span>](#tab/vs)

<span data-ttu-id="34a87-113">Visual Studio バージョン 2017 以降には、Azure 開発の組み込みサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="34a87-113">Visual Studio version 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="34a87-114">以下の手順では、Visual Studio での Azure 開発サポートの有効化について説明します。</span><span class="sxs-lookup"><span data-stu-id="34a87-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="34a87-115">Visual Studio 2015 以前の場合は、<a href="vs2015-install.md">これらの手順</a>に従います。</span><span class="sxs-lookup"><span data-stu-id="34a87-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="34a87-116">手順 1: Visual Studio 2019 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="34a87-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="34a87-117">Visual Studio 2019 を既にインストールしてある場合は省略できます。</span><span class="sxs-lookup"><span data-stu-id="34a87-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="34a87-118">Visual Studio 2019 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="34a87-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="34a87-119">手順 2: 2 つの Azure ワークロードをインストールする</span><span class="sxs-lookup"><span data-stu-id="34a87-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="34a87-120">Visual Studio インストーラーで、Visual Studio をインストールします (または既存のインストールを変更します)。</span><span class="sxs-lookup"><span data-stu-id="34a87-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="34a87-121">*Azure 開発*および *ASP.NET と Web 開発*ワークロードが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34a87-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="34a87-122">手順 3: Azure で .NET を使って開発する</span><span class="sxs-lookup"><span data-stu-id="34a87-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="34a87-123">まず、[最初の ASP.NET Core Web アプリを Azure App Service にデプロイ](/azure/app-service-web/app-service-web-get-started-dotnet)します。</span><span class="sxs-lookup"><span data-stu-id="34a87-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="visual-studio-code-cross-platform"></a>[<span data-ttu-id="34a87-124">Visual Studio Code (クロスプラットフォーム)</span><span class="sxs-lookup"><span data-stu-id="34a87-124">Visual Studio Code (cross-platform)</span></span>](#tab/vscode)

<span data-ttu-id="34a87-125">Visual Studio Code には、クロスプラットフォーム Azure での開発に必要なすべてのものが揃っています。</span><span class="sxs-lookup"><span data-stu-id="34a87-125">Visual Studio Code has everything you need for cross-platform Azure development.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="34a87-126">手順 1: .NET Core SDK をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="34a87-126">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="34a87-127">.NET Core アプリ用の SDK とコマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="34a87-127">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="34a87-128">.NET Core SDK をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="34a87-128">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="34a87-129">手順 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="34a87-129">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="34a87-130">任意のオペレーティング システム上で .NET Core アプリを編集し、デバッグします (Windows、Mac、Linux)。</span><span class="sxs-lookup"><span data-stu-id="34a87-130">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="34a87-131">Visual Studio Code をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="34a87-131">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a><span data-ttu-id="34a87-132">手順 3: Azure Tools 拡張機能</span><span class="sxs-lookup"><span data-stu-id="34a87-132">Step 3: Azure Tools extension</span></span>

<span data-ttu-id="34a87-133">Visual Studio Code で Azure Tools 拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="34a87-133">Install the Azure Tools extension in Visual Studio Code.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="34a87-134">Azure Tools 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="34a87-134">Install Azure Tools extension</span></span>](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a><span data-ttu-id="34a87-135">手順 4: Azure で .NET を使って開発する</span><span class="sxs-lookup"><span data-stu-id="34a87-135">Step 4: Develop with .NET on Azure</span></span>

<span data-ttu-id="34a87-136">まず、[最初の ASP.NET Core Web アプリを Azure App Service on Linux にデプロイ](/azure/app-service/containers/quickstart-dotnetcore)します。</span><span class="sxs-lookup"><span data-stu-id="34a87-136">Get started by [deploying your first ASP.NET Core web app on Azure App Service on Linux](/azure/app-service/containers/quickstart-dotnetcore).</span></span>

---
