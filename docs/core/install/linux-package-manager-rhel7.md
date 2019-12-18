---
title: Linux RHEL 7 に .NET Core をインストールする - パッケージ マネージャー - .NET Core
description: パッケージ マネージャーを使用して、.NET Core SDK とランタイムを RHEL 7 にインストールします。
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: f17a410ccea1ef4dec32de1d80ef6aac889aa6f3
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998907"
---
# <a name="rhel-7-package-manager---install-net-core"></a><span data-ttu-id="5466b-103">RHEL 7 パッケージ マネージャー - .NET Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="5466b-103">RHEL 7 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="5466b-104">この記事では、パッケージ マネージャーを使用して RHEL 7 に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5466b-104">This article describes how to use a package manager to install .NET Core on RHEL 7.</span></span> <span data-ttu-id="5466b-105">.NET Core 3.1 は、RHEL 7 ではまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="5466b-105">.NET Core 3.1 is not yet available for RHEL 7.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="5466b-106">ご利用の Red Hat サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="5466b-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="5466b-107">Red Hat から RHEL に .NET Core をインストールするには、まず、Red Hat Subscription Manager を使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5466b-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="5466b-108">ご利用のシステム上でこれがまだ行われていない場合、または不明な場合は、[.NET Core 向け Red Hat 製品ドキュメント](https://access.redhat.com/documentation/net_core/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5466b-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="5466b-109">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="5466b-109">Install the .NET Core SDK</span></span>

<span data-ttu-id="5466b-110">Subscription Manager に登録すると、.NET Core SDK をインストールして有効にする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="5466b-110">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="5466b-111">ご利用のターミナルで、次のコマンドを実行することで、RHEL 7 dotnet チャネルを有効にしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="5466b-111">In your terminal, run the following commands to enable the RHEL 7 dotnet channel and install.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="5466b-112">ASP.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="5466b-112">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="5466b-113">Subscription Manager に登録すると、ASP.NET Core ランタイムをインストールして有効にする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="5466b-113">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="5466b-114">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5466b-114">In your terminal, run the following commands.</span></span>

<!-- TODO: is this the correct value? Taken from the webpage but it doesn't have aspnet in the name -->
```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-aspnetcore-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="5466b-115">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="5466b-115">Install the .NET Core Runtime</span></span>

<span data-ttu-id="5466b-116">Subscription Manager に登録すると、.NET Core ランタイムをインストールして有効にする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="5466b-116">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="5466b-117">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5466b-117">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet30-dotnet-runtime-3.0 -y
scl enable rh-dotnet30 bash
```

## <a name="see-also"></a><span data-ttu-id="5466b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5466b-118">See also</span></span>

- [<span data-ttu-id="5466b-119">Red Hat Enterprise Linux 7 での .NET Core 3.0 の使用</span><span class="sxs-lookup"><span data-stu-id="5466b-119">Using .NET Core 3.0 on Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide/gs_install_dotnet)
