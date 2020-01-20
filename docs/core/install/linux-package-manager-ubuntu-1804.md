---
title: Ubuntu 18.04 パッケージ マネージャーに .NET Core をインストールする - .NET Core
description: パッケージ マネージャーを使用して、Ubuntu 18.04 に .NET Core SDK とランタイムをインストールします。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: a8e92cab30302c5636d23f098eb60637141545ca
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740625"
---
# <a name="ubuntu-1804-package-manager---install-net-core"></a><span data-ttu-id="76ef3-103">Ubuntu 18.04 パッケージ マネージャー - .NET Core のインストール</span><span class="sxs-lookup"><span data-stu-id="76ef3-103">Ubuntu 18.04 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="76ef3-104">この記事では、パッケージ マネージャーを使用して Ubuntu 18.04 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="76ef3-104">This article describes how to use a package manager to install .NET Core on Ubuntu 18.04.</span></span> <span data-ttu-id="76ef3-105">ランタイムをインストールする場合は、[ASP.NET Core ランタイム](#install-the-aspnet-core-runtime)をインストールすることをお勧めします。これには、.NET Core ランタイムと ASP.NET Core ランタイムの両方が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="76ef3-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="76ef3-106">Microsoft キーとフィードを登録する</span><span class="sxs-lookup"><span data-stu-id="76ef3-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="76ef3-107">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="76ef3-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="76ef3-108">Microsoft キーを登録する。</span><span class="sxs-lookup"><span data-stu-id="76ef3-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="76ef3-109">製品リポジトリを登録する。</span><span class="sxs-lookup"><span data-stu-id="76ef3-109">Register the product repository.</span></span>
- <span data-ttu-id="76ef3-110">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="76ef3-110">Install required dependencies.</span></span>

<span data-ttu-id="76ef3-111">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="76ef3-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="76ef3-112">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="76ef3-112">Open a terminal and run the following commands.</span></span>

```bash
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="76ef3-113">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="76ef3-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="76ef3-114">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="76ef3-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="76ef3-115">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="76ef3-115">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="76ef3-116">"**パッケージ dotnet-sdk-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76ef3-116">If you receive an error message similar to **Unable to locate package dotnet-sdk-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="76ef3-117">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="76ef3-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="76ef3-118">インストール可能な製品を更新してから、ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="76ef3-118">Update the products available for installation, then install the ASP.NET Core runtime.</span></span> <span data-ttu-id="76ef3-119">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="76ef3-119">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="76ef3-120">"**パッケージ aspnetcore-runtime-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76ef3-120">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="76ef3-121">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="76ef3-121">Install the .NET Core runtime</span></span>

<span data-ttu-id="76ef3-122">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="76ef3-122">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="76ef3-123">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="76ef3-123">In your terminal, run the following commands.</span></span>

```bash
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="76ef3-124">"**パッケージ dotnet-runtime-3.1 が見つかりません**" のようなエラー メッセージが表示される場合は、「[パッケージ マネージャーのトラブルシューティング](#troubleshoot-the-package-manager)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76ef3-124">If you receive an error message similar to **Unable to locate package dotnet-runtime-3.1**, see the [Troubleshoot the package manager](#troubleshoot-the-package-manager) section.</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="76ef3-125">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="76ef3-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="76ef3-126">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="76ef3-126">Troubleshoot the package manager</span></span>

<span data-ttu-id="76ef3-127">"**パッケージ <.NET Core パッケージ> が見つかりません**" のようなエラー メッセージが表示される場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="76ef3-127">If you receive an error message similar to **Unable to locate package {the .NET Core package}**, run the following commands.</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

<span data-ttu-id="76ef3-128">それでも解決しない場合は、次のコマンドを使用して手動インストールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="76ef3-128">If that doesn't work, you can run a manual install with the following commands.</span></span>

```bash
sudo apt-get install -y gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/ubuntu/18.04/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```
