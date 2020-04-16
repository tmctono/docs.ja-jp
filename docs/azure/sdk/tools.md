---
title: Azure .NET および .NET Core 開発者向けツール
description: Windows、Linux、Mac 環境から Azure .NET ライブラリを使い始めるためのツールを入手します。
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433164"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a><span data-ttu-id="167bf-103">.NET および .NET Core Azure 開発者向けツール</span><span class="sxs-lookup"><span data-stu-id="167bf-103">Tools for .NET and .NET Core Azure developers</span></span>

## <a name="sdk-downloads"></a><span data-ttu-id="167bf-104">SDK ダウンロード</span><span class="sxs-lookup"><span data-stu-id="167bf-104">SDK downloads</span></span>

<span data-ttu-id="167bf-105">NET 用の Azure ライブラリは[、NuGet パッケージ](https://www.nuget.org/packages?q=windowsazureofficial)として実装されます。</span><span class="sxs-lookup"><span data-stu-id="167bf-105">Azure libraries for .NET are implemented as [NuGet packages](https://www.nuget.org/packages?q=windowsazureofficial).</span></span> <span data-ttu-id="167bf-106">Azure サービスで整理されたインストール手順については[、「API リファレンス」を参照](/dotnet/api/overview/azure/?view=azure-dotnet)してください。</span><span class="sxs-lookup"><span data-stu-id="167bf-106">See the [API Reference](/dotnet/api/overview/azure/?view=azure-dotnet) for installation instructions organized by Azure service.</span></span>

## <a name="development-tools"></a><span data-ttu-id="167bf-107">開発ツール</span><span class="sxs-lookup"><span data-stu-id="167bf-107">Development tools</span></span>

<span data-ttu-id="167bf-108">Visual Studio には、多くの Azure サービスに組み込まれているツールがあります。</span><span class="sxs-lookup"><span data-stu-id="167bf-108">Visual Studio has tooling for many Azure services built-in.</span></span> <span data-ttu-id="167bf-109">Azure サービスによっては、Azure[ストレージ エクスプローラー](https://azure.microsoft.com/features/storage-explorer/)などの追加のツールやエミュレーターを利用できます。</span><span class="sxs-lookup"><span data-stu-id="167bf-109">Some Azure services have additional tools or emulators available, such as [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span> <span data-ttu-id="167bf-110">必要に応じて、その他のツールについては、Azure サービスのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="167bf-110">See the documentation for your Azure service for any additional tools, if necessary.</span></span>

<span data-ttu-id="167bf-111">以下の手順では、オペレーティング・システムに推奨される開始開発環境をインストールします。</span><span class="sxs-lookup"><span data-stu-id="167bf-111">These instructions install the recommended starting development environment for your operating system.</span></span>

## <a name="windows"></a>[<span data-ttu-id="167bf-112">Windows</span><span class="sxs-lookup"><span data-stu-id="167bf-112">Windows</span></span>](#tab/windows)

<span data-ttu-id="167bf-113">Visual Studio バージョン 2017 以降では、Azure 開発のサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="167bf-113">Visual Studio versions 2017 and later have built-in support for Azure development.</span></span> <span data-ttu-id="167bf-114">以下の手順では、Visual Studio で Azure 開発サポートを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="167bf-114">The below steps describe enabling Azure development support in Visual Studio.</span></span>

<span data-ttu-id="167bf-115">Visual Studio 2015 以前のバージョンでは、<a href="vs2015-install.md">次の手順に従ってください</a>。</span><span class="sxs-lookup"><span data-stu-id="167bf-115">For Visual Studio 2015 and earlier, <a href="vs2015-install.md">follow these instructions</a>.</span></span>

### <a name="step-1-download-visual-studio-2019"></a><span data-ttu-id="167bf-116">ステップ 1: ダウンロード Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="167bf-116">Step 1: Download Visual Studio 2019</span></span>

<span data-ttu-id="167bf-117">既に Visual Studio 2019 がインストールされている場合は、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="167bf-117">You can skip this step if you already have Visual Studio 2019 installed.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="167bf-118">Visual Studio 2019 をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="167bf-118">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a><span data-ttu-id="167bf-119">ステップ 2: 2 つの Azure ワークロードをインストールする</span><span class="sxs-lookup"><span data-stu-id="167bf-119">Step 2: Install the two Azure workloads</span></span>

<span data-ttu-id="167bf-120">Visual Studio インストーラーで、Visual Studio をインストールします (または既存のインストールを変更します)。</span><span class="sxs-lookup"><span data-stu-id="167bf-120">In the Visual Studio installer, install Visual Studio (or modify an existing installation).</span></span> <span data-ttu-id="167bf-121">*Azure*開発ワークロードと*ASP.NETワークロード、および Web 開発*ワークロードが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="167bf-121">Make sure the *Azure development* and *ASP.NET and web development* workloads are selected.</span></span>

### <a name="step-3-develop-with-net-on-azure"></a><span data-ttu-id="167bf-122">ステップ 3: Azure で .NET を使って開発する</span><span class="sxs-lookup"><span data-stu-id="167bf-122">Step 3: Develop with .NET on Azure</span></span>

<span data-ttu-id="167bf-123">まず、[最初の ASP.NET Core Web アプリを Azure App Service にデプロイ](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet)します。</span><span class="sxs-lookup"><span data-stu-id="167bf-123">Get started by [deploying your first ASP.NET Core web app on Azure App Service](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet).</span></span>

## <a name="macos"></a>[<span data-ttu-id="167bf-124">macOS</span><span class="sxs-lookup"><span data-stu-id="167bf-124">macOS</span></span>](#tab/macos)

<span data-ttu-id="167bf-125">Visual Studio for Mac には、Azure での開発に必要なすべてのものが揃っています。</span><span class="sxs-lookup"><span data-stu-id="167bf-125">Visual Studio for Mac has everything you need for Azure development.</span></span>

### <a name="step-1-download-visual-studio-for-mac"></a><span data-ttu-id="167bf-126">ステップ 1: Visual Studio for Mac をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="167bf-126">Step 1: Download Visual Studio for Mac</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="167bf-127">Visual Studio for Mac をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="167bf-127">Download Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="167bf-128">インストール時に、Azure ツールが既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="167bf-128">During installation, Azure tools are selected by default.</span></span>

## <a name="linux"></a>[<span data-ttu-id="167bf-129">Linux</span><span class="sxs-lookup"><span data-stu-id="167bf-129">Linux</span></span>](#tab/linux)

<span data-ttu-id="167bf-130">Visual Studio Code には、Linux における Azure での開発に必要なすべてのものが揃っています。</span><span class="sxs-lookup"><span data-stu-id="167bf-130">Visual Studio Code has everything you need for Azure development on Linux.</span></span>

### <a name="step-1-download-the-net-core-sdk"></a><span data-ttu-id="167bf-131">ステップ 1: .NET Core SDK をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="167bf-131">Step 1: Download the .NET Core SDK</span></span>

<span data-ttu-id="167bf-132">.NET Core アプリ用の SDK とコマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="167bf-132">The SDK and command-line tools for .NET Core apps.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="167bf-133">.NET Core SDK をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="167bf-133">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a><span data-ttu-id="167bf-134">ステップ 2: Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="167bf-134">Step 2: Visual Studio Code</span></span>

<span data-ttu-id="167bf-135">任意のオペレーティング システム (Windows、Mac、Linux) 上で .NET Core アプリを編集し、デバッグします。</span><span class="sxs-lookup"><span data-stu-id="167bf-135">Edit and debug .NET Core apps on any operating system: Windows, Mac, and Linux.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="167bf-136">Visual Studio Code をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="167bf-136">Download Visual Studio Code</span></span>](https://code.visualstudio.com)

---
