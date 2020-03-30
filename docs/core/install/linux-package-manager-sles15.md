---
title: SLES 15 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを SLES 15 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: b86b97bf17165f2f7a70e80ff581750ba39be375
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134173"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="45867-103">SLES 15 パッケージ マネージャー - .NET Core のインストール</span><span class="sxs-lookup"><span data-stu-id="45867-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="45867-104">この記事では、パッケージ マネージャーを使用して SLES 15 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="45867-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="45867-105">Microsoft キーとフィードを登録する</span><span class="sxs-lookup"><span data-stu-id="45867-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="45867-106">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="45867-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="45867-107">Microsoft キーを登録する。</span><span class="sxs-lookup"><span data-stu-id="45867-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="45867-108">製品リポジトリを登録する。</span><span class="sxs-lookup"><span data-stu-id="45867-108">Register the product repository.</span></span>
- <span data-ttu-id="45867-109">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="45867-109">Install required dependencies.</span></span>

<span data-ttu-id="45867-110">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="45867-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="45867-111">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="45867-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="45867-112">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="45867-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="45867-113">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="45867-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="45867-114">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="45867-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="45867-115">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="45867-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="45867-116">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="45867-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="45867-117">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="45867-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="45867-118">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="45867-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="45867-119">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="45867-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="45867-120">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="45867-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="45867-121">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="45867-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="45867-122">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="45867-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="45867-123">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="45867-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="45867-124">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="45867-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
