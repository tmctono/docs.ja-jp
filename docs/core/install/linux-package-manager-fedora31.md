---
title: Fedora 31 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを Fedora 31 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 56e5789132af2aa1171ea51698ae55d1eea5d457
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645310"
---
# <a name="fedora-31-package-manager---install-net-core"></a><span data-ttu-id="f2589-103">Fedora 31 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="f2589-103">Fedora 31 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="f2589-104">この記事では、パッケージ マネージャーを使用して Fedora 31 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2589-104">This article describes how to use a package manager to install .NET Core on Fedora 31.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="f2589-105">Microsoft リポジトリ キーとフィードを追加する</span><span class="sxs-lookup"><span data-stu-id="f2589-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="f2589-106">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2589-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="f2589-107">Microsoft パッケージ署名キーを信頼されたキーのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="f2589-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="f2589-108">リポジトリをパッケージ マネージャーに追加します。</span><span class="sxs-lookup"><span data-stu-id="f2589-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="f2589-109">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="f2589-109">Install required dependencies.</span></span>

<span data-ttu-id="f2589-110">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="f2589-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="f2589-111">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2589-111">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="f2589-112">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="f2589-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="f2589-113">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f2589-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="f2589-114">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2589-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="f2589-115">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="f2589-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="f2589-116">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f2589-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="f2589-117">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2589-117">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="f2589-118">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="f2589-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="f2589-119">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f2589-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="f2589-120">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2589-120">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="f2589-121">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="f2589-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="f2589-122">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f2589-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="f2589-123">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f2589-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="f2589-124">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="f2589-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
