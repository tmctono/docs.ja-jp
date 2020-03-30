---
title: Ubuntu 19.10 パッケージ マネージャーに .NET Core をインストールする - .NET Core
description: パッケージ マネージャーを使用して、Ubuntu 19.10 に .NET Core SDK とランタイムをインストールします。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: aac63ba74a8bfaba63e9d23882c9350a7d3d84f3
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134126"
---
# <a name="ubuntu-1910-package-manager---install-net-core"></a><span data-ttu-id="9e17c-103">Ubuntu 19.10 パッケージ マネージャー - .NET Core のインストール</span><span class="sxs-lookup"><span data-stu-id="9e17c-103">Ubuntu 19.10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="9e17c-104">この記事では、パッケージ マネージャーを使用して Ubuntu 19.10 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e17c-104">This article describes how to use a package manager to install .NET Core on Ubuntu 19.10.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="9e17c-105">Microsoft キーとフィードを登録する</span><span class="sxs-lookup"><span data-stu-id="9e17c-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="9e17c-106">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e17c-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="9e17c-107">Microsoft キーを登録する。</span><span class="sxs-lookup"><span data-stu-id="9e17c-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="9e17c-108">製品リポジトリを登録する。</span><span class="sxs-lookup"><span data-stu-id="9e17c-108">Register the product repository.</span></span>
- <span data-ttu-id="9e17c-109">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="9e17c-109">Install required dependencies.</span></span>

<span data-ttu-id="9e17c-110">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="9e17c-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="9e17c-111">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e17c-111">Open a terminal and run the following commands.</span></span>

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="9e17c-112">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="9e17c-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="9e17c-113">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9e17c-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="9e17c-114">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e17c-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9e17c-115">"**パッケージ dotnet-sdk-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e17c-115">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="9e17c-116">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="9e17c-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="9e17c-117">インストール可能な製品を更新してから、ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9e17c-117">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="9e17c-118">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e17c-118">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9e17c-119">"**パッケージ aspnetcore-runtime-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e17c-119">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="9e17c-120">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="9e17c-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="9e17c-121">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9e17c-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="9e17c-122">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e17c-122">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="9e17c-123">"**パッケージ dotnet-runtime-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e17c-123">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="9e17c-124">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="9e17c-124">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="9e17c-125">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9e17c-125">Troubleshoot the package manager</span></span>

<span data-ttu-id="9e17c-126">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9e17c-126">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="9e17c-127">見つからない</span><span class="sxs-lookup"><span data-stu-id="9e17c-127">Unable to locate</span></span>

<span data-ttu-id="9e17c-128">"**パッケージ <.NET Core パッケージ> が見つかりません**" のようなエラー メッセージが表示される場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e17c-128">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="9e17c-129">それでも解決しない場合は、次のコマンドを使用して手動インストールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9e17c-129">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/19.10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="9e17c-130">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="9e17c-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
