---
title: Azure .NET および .NET Core 開発者向けツール
description: Windows、Linux、Mac 環境から Azure .NET ライブラリを使い始めるためのツールを入手します。
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433164"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="f64f3-103">.NET および .NET Core Azure 開発者向けツール</span><span class="sxs-lookup"><span data-stu-id="f64f3-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="f64f3-104">SDK のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f64f3-104">SDK downloads</span></span>

<span data-ttu-id="f64f3-105">.NET 用 Azure ライブラリは [NuGet パッケージ](https://www.nuget.org/packages?q=windowsazureofficial)として実装されています。</span><span class="sxs-lookup"><span data-stu-id="f64f3-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="f64f3-106">Azure サービス別のインストール手順については、[API リファレンス](/dotnet/api/overview/azure/?view=azure-dotnet)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f64f3-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="f64f3-107">開発ツール</span><span class="sxs-lookup"><span data-stu-id="f64f3-107">Development tools</span></span>

<span data-ttu-id="f64f3-108">Visual Studio には、Azure サービス向けの多くのツールが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="f64f3-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="f64f3-109">一部の Azure サービスでは、[Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/) などの追加のツールやエミュレーターが提供されています。</span><span class="sxs-lookup"><span data-stu-id="f64f3-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="f64f3-110">必要に応じて、その他のツールについては、Azure サービスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f64f3-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="f64f3-111">これらの手順では、お使いのオペレーティン グシステムで推奨される最初の開発環境をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f64f3-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="f64f3-112">Windows</span><span class="sxs-lookup"><span data-stu-id="f64f3-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="f64f3-113">Visual Studio バージョン 2017 以降には、Azure 開発の組み込みサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="f64f3-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="f64f3-114">以下の手順では、Visual Studio での Azure 開発サポートの有効化について説明します。</span><span class="sxs-lookup"><span data-stu-id="f64f3-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="f64f3-115">Visual Studio 2015 以前の場合は、<a href="vs2015-install.md">これらの手順</a>に従います。</span><span class="sxs-lookup"><span data-stu-id="f64f3-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="f64f3-116">手順 1: Visual Studio 2019 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f64f3-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="f64f3-117">Visual Studio 2019 を既にインストールしてある場合は省略できます。</span><span class="sxs-lookup"><span data-stu-id="f64f3-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f64f3-118">Visual Studio 2019 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f64f3-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="f64f3-119">手順 2: 2 つの Azure ワークロードをインストールする</span><span class="sxs-lookup"><span data-stu-id="f64f3-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="f64f3-120">Visual Studio インストーラーで、Visual Studio をインストールします (または既存のインストールを変更します)。</span><span class="sxs-lookup"><span data-stu-id="f64f3-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="f64f3-121">*Azure 開発*および *ASP.NET と Web 開発*ワークロードが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f64f3-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="f64f3-122">手順 3: Azure で .NET を使って開発する</span><span class="sxs-lookup"><span data-stu-id="f64f3-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="f64f3-123">まず、[最初の ASP.NET Core Web アプリを Azure App Service にデプロイ](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet)します。</span><span class="sxs-lookup"><span data-stu-id="f64f3-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="f64f3-124">macOS</span><span class="sxs-lookup"><span data-stu-id="f64f3-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="f64f3-125">Visual Studio for Mac には、Azure での開発に必要なすべてのものが揃っています。</span><span class="sxs-lookup"><span data-stu-id="f64f3-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="f64f3-126">手順 1: Visual Studio for Mac をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f64f3-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f64f3-127">Visual Studio for Mac をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f64f3-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="f64f3-128">インストール中に、Azure ツールが既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="f64f3-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="f64f3-129">Linux</span><span class="sxs-lookup"><span data-stu-id="f64f3-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="f64f3-130">Visual Studio Code には、Linux における Azure での開発に必要なすべてのものが揃っています。</span><span class="sxs-lookup"><span data-stu-id="f64f3-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="f64f3-131">手順 1: .NET Core SDK をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f64f3-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="f64f3-132">.NET Core アプリ用の SDK とコマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="f64f3-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f64f3-133">.NET Core SDK をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f64f3-133">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="f64f3-134">手順 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f64f3-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="f64f3-135">任意のオペレーティング システム上で .NET Core アプリを編集し、デバッグします (Windows、Mac、Linux)。</span><span class="sxs-lookup"><span data-stu-id="f64f3-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f64f3-136">Visual Studio Code をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f64f3-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
