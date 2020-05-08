---
title: Debian 10 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを Debian 10 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 038f5579f99f700ce47dc67be2fd344f01cf800c
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595621"
---
# <a name="debian-10-package-manager---install-net-core"></a><span data-ttu-id="3537f-103">Debian 10 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="3537f-103">Debian 10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="3537f-104">この記事では、パッケージ マネージャーを使用して Debian 10 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3537f-104">This article describes how to use a package manager to install .NET Core on Debian 10.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="3537f-105">Microsoft リポジトリ キーとフィードを追加する</span><span class="sxs-lookup"><span data-stu-id="3537f-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="3537f-106">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3537f-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="3537f-107">Microsoft パッケージ署名キーを信頼されたキーのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="3537f-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="3537f-108">リポジトリをパッケージ マネージャーに追加します。</span><span class="sxs-lookup"><span data-stu-id="3537f-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="3537f-109">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="3537f-109">Install required dependencies.</span></span>

<span data-ttu-id="3537f-110">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="3537f-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="3537f-111">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3537f-111">Open a terminal and run the following commands.</span></span>

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="3537f-112">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="3537f-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="3537f-113">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3537f-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="3537f-114">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3537f-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="3537f-115">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="3537f-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="3537f-116">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3537f-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="3537f-117">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3537f-117">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="3537f-118">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="3537f-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="3537f-119">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3537f-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="3537f-120">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3537f-120">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="3537f-121">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="3537f-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="3537f-122">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3537f-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="3537f-123">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3537f-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="3537f-124">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="3537f-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]
