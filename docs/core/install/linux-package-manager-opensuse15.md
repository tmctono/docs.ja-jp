---
title: openSUSE 15 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを openSUSE 15 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: fc4c9e30ddb0cfd3e6fe79fa4f78206f4700eeee
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645665"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="62550-103">openSUSE 15 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="62550-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="62550-104">この記事では、パッケージ マネージャーを使用して、openSUSE 15 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62550-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="62550-105">Microsoft リポジトリ キーとフィードを追加する</span><span class="sxs-lookup"><span data-stu-id="62550-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="62550-106">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="62550-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="62550-107">Microsoft パッケージ署名キーを信頼されたキーのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="62550-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="62550-108">リポジトリをパッケージ マネージャーに追加します。</span><span class="sxs-lookup"><span data-stu-id="62550-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="62550-109">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="62550-109">Install required dependencies.</span></span>

<span data-ttu-id="62550-110">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="62550-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="62550-111">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="62550-111">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="62550-112">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="62550-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="62550-113">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="62550-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="62550-114">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="62550-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="62550-115">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="62550-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="62550-116">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="62550-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="62550-117">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="62550-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="62550-118">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="62550-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="62550-119">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="62550-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="62550-120">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="62550-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="62550-121">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="62550-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="62550-122">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="62550-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="62550-123">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="62550-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="62550-124">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="62550-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
