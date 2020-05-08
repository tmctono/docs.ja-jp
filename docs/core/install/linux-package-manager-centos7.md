---
title: CentOS 7 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを CentOS 7 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: f8c4115b9d85edc36809f0daed5f6825149c8411
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645403"
---
# <a name="centos-7-package-manager---install-net-core"></a><span data-ttu-id="c5724-103">CentOS 7 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="c5724-103">CentOS 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="c5724-104">この記事では、パッケージ マネージャーを使用して CentOS 7 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5724-104">This article describes how to use a package manager to install .NET Core on CentOS 7.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="c5724-105">Microsoft リポジトリ キーとフィードを追加する</span><span class="sxs-lookup"><span data-stu-id="c5724-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="c5724-106">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5724-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="c5724-107">Microsoft パッケージ署名キーを信頼されたキーのリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="c5724-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="c5724-108">リポジトリをパッケージ マネージャーに追加します。</span><span class="sxs-lookup"><span data-stu-id="c5724-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="c5724-109">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="c5724-109">Install required dependencies.</span></span>

<span data-ttu-id="c5724-110">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="c5724-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="c5724-111">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5724-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="c5724-112">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="c5724-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="c5724-113">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c5724-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="c5724-114">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5724-114">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="c5724-115">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="c5724-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="c5724-116">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c5724-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="c5724-117">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5724-117">In your terminal, run the following command.</span></span>

```bash
sudo yum install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="c5724-118">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="c5724-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="c5724-119">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c5724-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="c5724-120">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5724-120">In your terminal, run the following command.</span></span>

```bash
sudo yum install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="c5724-121">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="c5724-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="c5724-122">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c5724-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="c5724-123">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c5724-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="c5724-124">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="c5724-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
