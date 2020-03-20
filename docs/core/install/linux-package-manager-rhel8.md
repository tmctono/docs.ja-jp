---
title: Linux RHEL 8 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを RHEL 8 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 054494a9b77e1c7803e42c947e067d3eb290f73c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78849796"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="6c46c-103">RHEL 8 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="6c46c-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="6c46c-104">この記事では、パッケージ マネージャーを使用して RHEL 8 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c46c-104">This article describes how to use a package manager to install .NET Core on RHEL 8.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="6c46c-105">ご利用の Red Hat サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="6c46c-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="6c46c-106">Red Hat から RHEL に .NET Core をインストールするには、まず、Red Hat Subscription Manager を使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c46c-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="6c46c-107">ご利用のシステム上でこれがまだ行われていない場合、または不明な場合は、[.NET Core 向け Red Hat 製品ドキュメント](https://access.redhat.com/documentation/net_core/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c46c-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="6c46c-108">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="6c46c-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="6c46c-109">Subscription Manager に登録すると、.NET Core SDK をインストールして有効にする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="6c46c-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="6c46c-110">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c46c-110">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="6c46c-111">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="6c46c-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="6c46c-112">Subscription Manager に登録すると、ASP.NET Core ランタイムをインストールして有効にする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="6c46c-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="6c46c-113">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c46c-113">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="6c46c-114">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="6c46c-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="6c46c-115">Subscription Manager に登録すると、.NET Core ランタイムをインストールして有効にする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="6c46c-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="6c46c-116">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c46c-116">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a><span data-ttu-id="6c46c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c46c-117">See also</span></span>

- [<span data-ttu-id="6c46c-118">Red Hat Enterprise Linux 8 での .NET Core 3.1 の使用</span><span class="sxs-lookup"><span data-stu-id="6c46c-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)
