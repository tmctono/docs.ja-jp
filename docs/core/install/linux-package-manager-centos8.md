---
title: Linux CentOS 8 パッケージ マネージャーに .NET Core をインストールする - .NET Core
description: パッケージ マネージャーを使用して、CentOS 8 に .NET Core SDK とランタイムをインストールします。
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: b4cf5975e18aa8dfa8649c0d038caf38d648ad86
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728505"
---
# <a name="centos-8-package-manager---install-net-core"></a><span data-ttu-id="e4783-103">CentOS 8 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="e4783-103">CentOS 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="e4783-104">この記事では、パッケージ マネージャーを使用して CentOS 8 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4783-104">This article describes how to use a package manager to install .NET Core on CentOS 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="e4783-105">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="e4783-105">Install the .NET Core SDK</span></span>

<span data-ttu-id="e4783-106">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4783-106">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="e4783-107">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="e4783-107">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="e4783-108">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4783-108">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="e4783-109">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="e4783-109">Install the .NET Core Runtime</span></span>

<span data-ttu-id="e4783-110">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4783-110">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="e4783-111">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="e4783-111">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
