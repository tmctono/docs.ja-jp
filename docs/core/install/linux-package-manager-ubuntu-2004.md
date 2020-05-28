---
title: Ubuntu 20.04 パッケージ マネージャーに .NET Core をインストールする - .NET Core
description: パッケージ マネージャーを使用して、Ubuntu 20.04 に .NET Core SDK とランタイムをインストールします。
author: thraka
ms.author: adegeo
ms.date: 05/13/2020
ms.openlocfilehash: 4d7d7ee9117314ef360097fee929f24943c7a7f2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83618871"
---
# <a name="ubuntu-2004-package-manager---install-net-core"></a><span data-ttu-id="bacfa-103">Ubuntu 20.04 パッケージ マネージャー - .NET Core のインストール</span><span class="sxs-lookup"><span data-stu-id="bacfa-103">Ubuntu 20.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="bacfa-104">この記事では、パッケージ マネージャーを使用して Ubuntu 20.04 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bacfa-104">This article describes how to use a package manager to install .NET Core on Ubuntu 20.04.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="bacfa-105">Microsoft リポジトリ キーとフィードを追加する</span><span class="sxs-lookup"><span data-stu-id="bacfa-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="bacfa-106">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bacfa-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="bacfa-107">Microsoft パッケージ署名キーを信頼されたキーのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="bacfa-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="bacfa-108">リポジトリをパッケージ マネージャーに追加します。</span><span class="sxs-lookup"><span data-stu-id="bacfa-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="bacfa-109">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="bacfa-109">Install required dependencies.</span></span>

<span data-ttu-id="bacfa-110">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="bacfa-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="bacfa-111">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bacfa-111">Open a terminal and run the following commands.</span></span>

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="bacfa-112">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="bacfa-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="bacfa-113">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bacfa-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="bacfa-114">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bacfa-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="bacfa-115">"**パッケージ dotnet-sdk-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bacfa-115">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="bacfa-116">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="bacfa-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="bacfa-117">インストール可能な製品を更新してから、ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bacfa-117">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="bacfa-118">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bacfa-118">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="bacfa-119">"**パッケージ aspnetcore-runtime-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bacfa-119">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="bacfa-120">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="bacfa-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="bacfa-121">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bacfa-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="bacfa-122">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bacfa-122">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="bacfa-123">"**パッケージ dotnet-runtime-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bacfa-123">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="bacfa-124">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="bacfa-124">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="bacfa-125">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bacfa-125">Troubleshoot the package manager</span></span>

<span data-ttu-id="bacfa-126">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bacfa-126">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="bacfa-127">見つからない</span><span class="sxs-lookup"><span data-stu-id="bacfa-127">Unable to locate</span></span>

<span data-ttu-id="bacfa-128">"**パッケージ <.NET Core パッケージ> が見つかりません**" のようなエラー メッセージが表示される場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bacfa-128">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="bacfa-129">それでも解決しない場合は、次のコマンドを使用して手動インストールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bacfa-129">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/20.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="bacfa-130">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="bacfa-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
