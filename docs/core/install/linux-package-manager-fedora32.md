---
title: Fedora 32 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを Fedora 32 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624952"
---
# <a name="fedora-32-package-manager---install-net-core"></a><span data-ttu-id="5e3e1-103">Fedora 32 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="5e3e1-103">Fedora 32 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="5e3e1-104">この記事では、パッケージ マネージャーを使用して Fedora 32 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e3e1-104">This article describes how to use a package manager to install .NET Core on Fedora 32.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

<span data-ttu-id="5e3e1-105">Fedora 32 以降、.NET Core 3.1 は Fedora の既定のパッケージ リポジトリで利用できます。</span><span class="sxs-lookup"><span data-stu-id="5e3e1-105">Starting with Fedora 32, .NET Core 3.1 is available in the default package repositories in Fedora.</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="5e3e1-106">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="5e3e1-106">Install the .NET Core SDK</span></span>

<span data-ttu-id="5e3e1-107">.NET Core SDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e3e1-107">Install the .NET Core SDK.</span></span> <span data-ttu-id="5e3e1-108">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e3e1-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="5e3e1-109">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="5e3e1-109">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="5e3e1-110">ASP.NET ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e3e1-110">Install the ASP.NET runtime.</span></span> <span data-ttu-id="5e3e1-111">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e3e1-111">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="5e3e1-112">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="5e3e1-112">Install the .NET Core runtime</span></span>

<span data-ttu-id="5e3e1-113">.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e3e1-113">Install the .NET Core runtime.</span></span> <span data-ttu-id="5e3e1-114">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e3e1-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5e3e1-115">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="5e3e1-115">How to install other versions</span></span>

<span data-ttu-id="5e3e1-116">.NET Core のその他のバージョンをインストールするには、[.NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) または [.NET Core Runtime](runtime.md?pivots=os-linux#download-and-manually-install) を手動でインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e3e1-116">To install other versions of .NET Core, manually install [the .NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) or [the .NET Core Runtime](runtime.md?pivots=os-linux#download-and-manually-install).</span></span>
