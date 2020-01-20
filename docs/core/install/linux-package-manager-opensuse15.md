---
title: openSUSE 15 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを openSUSE 15 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740673"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="7a1ce-103">openSUSE 15 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="7a1ce-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="7a1ce-104">この記事では、パッケージ マネージャーを使用して、openSUSE 15 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="7a1ce-105">ランタイムをインストールする場合は、[ASP.NET Core ランタイム](#install-the-aspnet-core-runtime)をインストールすることをお勧めします。これには、.NET Core ランタイムと ASP.NET Core ランタイムの両方が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="7a1ce-106">Microsoft キーとフィードを登録する</span><span class="sxs-lookup"><span data-stu-id="7a1ce-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="7a1ce-107">.NET をインストールする前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="7a1ce-108">Microsoft キーを登録する。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="7a1ce-109">製品リポジトリを登録する。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-109">Register the product repository.</span></span>
- <span data-ttu-id="7a1ce-110">必要な依存関係をインストールする。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-110">Install required dependencies.</span></span>

<span data-ttu-id="7a1ce-111">これは、コンピューターごとに 1 回実行する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="7a1ce-112">ターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a><span data-ttu-id="7a1ce-113">.NET Core 3.1 での依存関係エラー</span><span class="sxs-lookup"><span data-stu-id="7a1ce-113">Dependency error with .NET Core 3.1</span></span>

<span data-ttu-id="7a1ce-114">openSUSE 用の .NET Core 3.1 パッケージ フィードには、**krb5** 依存関係の問題があります。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-114">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="7a1ce-115">.NET Core 3.1 または ASP.NET Core 3.1 をインストールする前に、次のコマンドを使用して適切な依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-115">Use the following command to install the correct dependencies prior to installing .NET Core 3.1 or ASP.NET Core 3.1.</span></span>

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="7a1ce-116">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="7a1ce-116">Install the .NET Core SDK</span></span>

<span data-ttu-id="7a1ce-117">インストール可能な製品を更新してから、.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-117">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="7a1ce-118">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="7a1ce-119">openSUSE 用の .NET Core 3.1 パッケージ フィードには、**krb5** 依存関係の問題があります。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-119">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="7a1ce-120">次のコマンドを使用して適切な依存関係をインストールしてから、.NET Core 3.1 SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-120">Use the following command to install the correct dependencies, then install the .NET Core 3.1 SDK.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="7a1ce-121">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="7a1ce-121">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="7a1ce-122">インストール可能な製品を更新してから、ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-122">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="7a1ce-123">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-123">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="7a1ce-124">openSUSE 用の .NET Core 3.1 パッケージ フィードには、**krb5** 依存関係の問題があります。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-124">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="7a1ce-125">次のコマンドを使用して適切な依存関係をインストールしてから、ASP.NET Core 3.1 ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-125">Use the following command to install the correct dependencies, then install the ASP.NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="7a1ce-126">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="7a1ce-126">Install the .NET Core runtime</span></span>

<span data-ttu-id="7a1ce-127">インストール可能な製品を更新してから、.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-127">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="7a1ce-128">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-128">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="7a1ce-129">openSUSE 用の .NET Core 3.1 パッケージ フィードには、**krb5** 依存関係の問題があります。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-129">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="7a1ce-130">次のコマンドを使用して適切な依存関係をインストールしてから、.NET Core 3.1 ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7a1ce-130">Use the following command to install the correct dependencies, then install the .NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="7a1ce-131">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="7a1ce-131">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
