---
title: SLES 15 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを SLES 15 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: be5a21db8c3942bfe8827dfbce41bcf88aec342a
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595618"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="17838-103">SLES 15 パッケージ マネージャー - .NET Core のインストール</span><span class="sxs-lookup"><span data-stu-id="17838-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="17838-104">この記事では、パッケージ マネージャーを使用して SLES 15 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="17838-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="17838-105">Microsoft リポジトリ キーとフィードを追加する</span><span class="sxs-lookup"><span data-stu-id="17838-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="17838-106">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="17838-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="17838-107">Microsoft パッケージ署名キーを信頼されたキーのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="17838-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="17838-108">リポジトリをパッケージ マネージャーに追加します。</span><span class="sxs-lookup"><span data-stu-id="17838-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="17838-109">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="17838-109">Install required dependencies.</span></span>

<span data-ttu-id="17838-110">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="17838-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="17838-111">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="17838-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="17838-112">現時点では、SLES 15 Microsoft リポジトリ セットアップ パッケージによって "*microsoft-prod.repo*" ファイルが間違ったディレクトリにインストールされるため、zypper が .NET Core パッケージを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="17838-112">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="17838-113">この問題を解決するには、正しいディレクトリにシンボリックリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="17838-113">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="17838-114">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="17838-114">Install the .NET Core SDK</span></span>

<span data-ttu-id="17838-115">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="17838-115">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="17838-116">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="17838-116">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="17838-117">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="17838-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="17838-118">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="17838-118">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="17838-119">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="17838-119">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="17838-120">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="17838-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="17838-121">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="17838-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="17838-122">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="17838-122">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="17838-123">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="17838-123">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="17838-124">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="17838-124">Troubleshoot the package manager</span></span>

<span data-ttu-id="17838-125">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="17838-125">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="17838-126">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="17838-126">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]
