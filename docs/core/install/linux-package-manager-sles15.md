---
title: SLES 15 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを SLES 15 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: f48c131b4250bd04fffc0d815a3500732caacb7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76921031"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="bed50-103">SLES 15 パッケージ マネージャー - .NET Core のインストール</span><span class="sxs-lookup"><span data-stu-id="bed50-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="bed50-104">この記事では、パッケージ マネージャーを使用して SLES 15 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bed50-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span> <span data-ttu-id="bed50-105">ランタイムをインストールする場合は、[ASP.NET Core ランタイム](#install-the-aspnet-core-runtime)をインストールすることをお勧めします。これには、.NET Core ランタイムと ASP.NET Core ランタイムの両方が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="bed50-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="bed50-106">Microsoft キーとフィードを登録する</span><span class="sxs-lookup"><span data-stu-id="bed50-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="bed50-107">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bed50-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="bed50-108">Microsoft キーを登録する。</span><span class="sxs-lookup"><span data-stu-id="bed50-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="bed50-109">製品リポジトリを登録する。</span><span class="sxs-lookup"><span data-stu-id="bed50-109">Register the product repository.</span></span>
- <span data-ttu-id="bed50-110">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="bed50-110">Install required dependencies.</span></span>

<span data-ttu-id="bed50-111">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="bed50-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="bed50-112">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bed50-112">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="bed50-113">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="bed50-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="bed50-114">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bed50-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="bed50-115">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bed50-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="bed50-116">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="bed50-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="bed50-117">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bed50-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="bed50-118">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bed50-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="bed50-119">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="bed50-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="bed50-120">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bed50-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="bed50-121">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bed50-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="bed50-122">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="bed50-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="bed50-123">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bed50-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="bed50-124">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bed50-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="bed50-125">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="bed50-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
