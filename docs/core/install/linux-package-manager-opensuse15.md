---
title: openSUSE 15 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを openSUSE 15 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 0ea232438aa4c61e2064d0323dc706dffac15039
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998937"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="774be-103">openSUSE 15 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="774be-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="774be-104">この記事では、パッケージ マネージャーを使用して、openSUSE 15 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="774be-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="774be-105">ランタイムをインストールする場合は、[ASP.NET Core ランタイム](#install-the-aspnet-core-runtime)をインストールすることをお勧めします。これには、.NET Core ランタイムと ASP.NET Core ランタイムの両方が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="774be-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="774be-106">Microsoft キーとフィードを登録する</span><span class="sxs-lookup"><span data-stu-id="774be-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="774be-107">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="774be-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="774be-108">Microsoft キーを登録する</span><span class="sxs-lookup"><span data-stu-id="774be-108">Register the Microsoft key</span></span>
- <span data-ttu-id="774be-109">製品リポジトリを登録する</span><span class="sxs-lookup"><span data-stu-id="774be-109">register the product repository</span></span>
- <span data-ttu-id="774be-110">必要な依存関係をインストールする</span><span class="sxs-lookup"><span data-stu-id="774be-110">Install required dependencies</span></span>

<span data-ttu-id="774be-111">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="774be-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="774be-112">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="774be-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="774be-113">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="774be-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="774be-114">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="774be-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="774be-115">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="774be-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="774be-116">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="774be-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="774be-117">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="774be-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="774be-118">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="774be-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="774be-119">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="774be-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="774be-120">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="774be-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="774be-121">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="774be-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="774be-122">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="774be-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
