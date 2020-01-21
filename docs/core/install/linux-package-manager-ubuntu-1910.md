---
title: Ubuntu 19.10 パッケージ マネージャーに .NET Core をインストールする - .NET Core
description: パッケージ マネージャーを使用して、Ubuntu 19.10 に .NET Core SDK とランタイムをインストールします。
author: thraka
ms.author: adegeo
ms.date: 01/16/2020
ms.openlocfilehash: afba761e2237ed84528157841e538a9b44d9a966
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164070"
---
# <a name="ubuntu-1910-package-manager---install-net-core"></a><span data-ttu-id="67589-103">Ubuntu 19.10 パッケージ マネージャー - .NET Core のインストール</span><span class="sxs-lookup"><span data-stu-id="67589-103">Ubuntu 19.10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="67589-104">この記事では、パッケージ マネージャーを使用して Ubuntu 19.10 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67589-104">This article describes how to use a package manager to install .NET Core on Ubuntu 19.10.</span></span> <span data-ttu-id="67589-105">ランタイムをインストールする場合は、[ASP.NET Core ランタイム](#install-the-aspnet-core-runtime)をインストールすることをお勧めします。これには、.NET Core ランタイムと ASP.NET Core ランタイムの両方が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="67589-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="67589-106">Microsoft キーとフィードを登録する</span><span class="sxs-lookup"><span data-stu-id="67589-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="67589-107">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="67589-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="67589-108">Microsoft キーを登録する。</span><span class="sxs-lookup"><span data-stu-id="67589-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="67589-109">製品リポジトリを登録する。</span><span class="sxs-lookup"><span data-stu-id="67589-109">Register the product repository.</span></span>
- <span data-ttu-id="67589-110">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="67589-110">Install required dependencies.</span></span>

<span data-ttu-id="67589-111">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="67589-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="67589-112">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67589-112">Open a terminal and run the following commands.</span></span>

```bash
wget -q https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="67589-113">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="67589-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="67589-114">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="67589-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="67589-115">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67589-115">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="67589-116">"**パッケージ dotnet-sdk-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67589-116">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="67589-117">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="67589-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="67589-118">インストール可能な製品を更新してから、ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="67589-118">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="67589-119">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67589-119">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="67589-120">"**パッケージ aspnetcore-runtime-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67589-120">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="67589-121">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="67589-121">Install the .NET Core runtime</span></span>

<span data-ttu-id="67589-122">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="67589-122">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="67589-123">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67589-123">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="67589-124">"**パッケージ dotnet-runtime-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67589-124">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="67589-125">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="67589-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="67589-126">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="67589-126">Troubleshoot the package manager</span></span>

<span data-ttu-id="67589-127">"**パッケージ <.NET Core パッケージ> が見つかりません**" のようなエラー メッセージが表示される場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="67589-127">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="67589-128">それでも解決しない場合は、次のコマンドを使用して手動インストールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="67589-128">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/ubuntu/19.10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```
