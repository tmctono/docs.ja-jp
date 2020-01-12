---
title: Linux RHEL 8.1 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを RHEL 8.1 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8781d6bd14daf975fcc602fd2924a333750d4256
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714375"
---
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="0cf7a-103">RHEL 8.1 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="0cf7a-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="0cf7a-104">この記事では、パッケージ マネージャーを使用して RHEL 8.1 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="0cf7a-105">.NET Core 3.1 は、RHEL 8.1 ではまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="0cf7a-106">RHEL 8.0 に .NET Core 3.0 は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="0cf7a-107">コマンド `yum upgrade` を使用することで、RHEL 8.1 に更新できます。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="0cf7a-108">ご利用の Red Hat サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="0cf7a-108">Register your Red Hat subscription</span></span>

<span data-ttu-id="0cf7a-109">Red Hat から RHEL に .NET Core をインストールするには、まず、Red Hat Subscription Manager を使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-109">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="0cf7a-110">ご利用のシステム上でこれがまだ行われていない場合、または不明な場合は、[.NET Core 向け Red Hat 製品ドキュメント](https://access.redhat.com/documentation/net_core/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-110">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="0cf7a-111">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="0cf7a-111">Install the .NET Core SDK</span></span>

<span data-ttu-id="0cf7a-112">Subscription Manager に登録すると、.NET Core SDK をインストールして有効にする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-112">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="0cf7a-113">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-113">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="0cf7a-114">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="0cf7a-114">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="0cf7a-115">Subscription Manager に登録すると、ASP.NET Core ランタイムをインストールして有効にする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-115">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="0cf7a-116">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-116">In your terminal, run the following commands.</span></span>

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="0cf7a-117">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="0cf7a-117">Install the .NET Core Runtime</span></span>

<span data-ttu-id="0cf7a-118">Subscription Manager に登録すると、.NET Core ランタイムをインストールして有効にする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-118">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="0cf7a-119">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0cf7a-119">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="0cf7a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cf7a-120">See also</span></span>

- [<span data-ttu-id="0cf7a-121">Red Hat Enterprise Linux 8 での .NET Core 3.0 の使用</span><span class="sxs-lookup"><span data-stu-id="0cf7a-121">Using .NET Core 3.0 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)
