---
title: Fedora 29 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを Fedora 29 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 1cd761e323467ef34fdad58de7385c1ca7b2c14a
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998931"
---
# <a name="fedora-29-package-manager---install-net-core"></a><span data-ttu-id="fce3f-103">Fedora 29 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="fce3f-103">Fedora 29 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="fce3f-104">この記事では、パッケージ マネージャーを使用して Fedora 29 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fce3f-104">This article describes how to use a package manager to install .NET Core on Fedora 29.</span></span> <span data-ttu-id="fce3f-105">ランタイムをインストールする場合は、[ASP.NET Core ランタイム](#install-the-aspnet-core-runtime)をインストールすることをお勧めします。これには、.NET Core ランタイムと ASP.NET Core ランタイムの両方が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="fce3f-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="fce3f-106">Microsoft キーとフィードを登録する</span><span class="sxs-lookup"><span data-stu-id="fce3f-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="fce3f-107">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fce3f-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="fce3f-108">Microsoft キーを登録する</span><span class="sxs-lookup"><span data-stu-id="fce3f-108">Register the Microsoft key</span></span>
- <span data-ttu-id="fce3f-109">製品リポジトリを登録する</span><span class="sxs-lookup"><span data-stu-id="fce3f-109">register the product repository</span></span>
- <span data-ttu-id="fce3f-110">必要な依存関係をインストールする</span><span class="sxs-lookup"><span data-stu-id="fce3f-110">Install required dependencies</span></span>

<span data-ttu-id="fce3f-111">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="fce3f-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="fce3f-112">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fce3f-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="fce3f-113">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="fce3f-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="fce3f-114">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="fce3f-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="fce3f-115">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fce3f-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="fce3f-116">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="fce3f-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="fce3f-117">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fce3f-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="fce3f-118">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fce3f-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="fce3f-119">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="fce3f-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="fce3f-120">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fce3f-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="fce3f-121">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fce3f-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="fce3f-122">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="fce3f-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
