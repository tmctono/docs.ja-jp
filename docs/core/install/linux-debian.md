---
title: Debian に .NET Core をインストールする - .NET Core
description: Debian に .NET Core SDK と .NET Core ランタイムをインストールするさまざまな方法を示します。
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: ded9d2be72e8ec476d5ace752e44d92eb0ee1028
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324927"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a><span data-ttu-id="34b46-103">Debian に .NET Core SDK または .NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="34b46-103">Install .NET Core SDK or .NET Core Runtime on Debian</span></span>

<span data-ttu-id="34b46-104">この記事では、Debian に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="34b46-104">This article describes how to install .NET Core on Debian.</span></span> <span data-ttu-id="34b46-105">Debian のバージョンがサポート対象外である場合、.NET Core もそのバージョンでサポート対象外となります。</span><span class="sxs-lookup"><span data-stu-id="34b46-105">When a Debian version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="34b46-106">ただし、サポートされていない場合でも、以下の手順はそれらのバージョンで実行される .NET Core の取得に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="34b46-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="34b46-107">サポートされているディストリビューション</span><span class="sxs-lookup"><span data-stu-id="34b46-107">Supported distributions</span></span>

<span data-ttu-id="34b46-108">次の表は、現在サポートされている .NET Core リリースと、それらがサポートされている Debian のバージョンの一覧です。</span><span class="sxs-lookup"><span data-stu-id="34b46-108">The following table is a list of currently supported .NET Core releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="34b46-109">これらのバージョンは、[.NET Core のバージョンがサポート終了になる](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)か、[Debian のバージョンがサポート終了になる](https://wiki.debian.org/DebianReleases)までサポートされます。</span><span class="sxs-lookup"><span data-stu-id="34b46-109">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="34b46-110">✔️ は、Debian または .NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="34b46-110">A ✔️ indicates that the version of Debian or .NET Core is still supported.</span></span>
- <span data-ttu-id="34b46-111">❌ は、Debian または .NET Core のバージョンがその Debian のリリースではサポートされていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="34b46-111">A ❌ indicates that the version of Debian or .NET Core isn't supported on that Debian release.</span></span>
- <span data-ttu-id="34b46-112">Debian のバージョンと .NET Core のバージョンの両方に ✔️ が付いている場合、その OS と .NET の組み合わせはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="34b46-112">When both a version of Debian and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="34b46-113">Debian</span><span class="sxs-lookup"><span data-stu-id="34b46-113">Debian</span></span>                   | <span data-ttu-id="34b46-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="34b46-114">.NET Core 2.1</span></span> | <span data-ttu-id="34b46-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="34b46-115">.NET Core 3.1</span></span> | <span data-ttu-id="34b46-116">.NET 5 Preview (手動インストールのみ)</span><span class="sxs-lookup"><span data-stu-id="34b46-116">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="34b46-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="34b46-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="34b46-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="34b46-118">✔️ 2.1</span></span>        | <span data-ttu-id="34b46-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="34b46-119">✔️ 3.1</span></span>        | <span data-ttu-id="34b46-120">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="34b46-120">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="34b46-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="34b46-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="34b46-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="34b46-122">✔️ 2.1</span></span>        | <span data-ttu-id="34b46-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="34b46-123">✔️ 3.1</span></span>        | <span data-ttu-id="34b46-124">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="34b46-124">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="34b46-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="34b46-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="34b46-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="34b46-126">✔️ 2.1</span></span>        | <span data-ttu-id="34b46-127">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="34b46-127">❌ 3.1</span></span>        | <span data-ttu-id="34b46-128">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="34b46-128">❌ 5.0 Preview</span></span> |

<span data-ttu-id="34b46-129">次のバージョンの .NET Core は、サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="34b46-129">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="34b46-130">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="34b46-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="34b46-131">3.0</span><span class="sxs-lookup"><span data-stu-id="34b46-131">3.0</span></span>
- <span data-ttu-id="34b46-132">2.2</span><span class="sxs-lookup"><span data-stu-id="34b46-132">2.2</span></span>
- <span data-ttu-id="34b46-133">2.0</span><span class="sxs-lookup"><span data-stu-id="34b46-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="34b46-134">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="34b46-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="34b46-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="34b46-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="34b46-136">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="34b46-136">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="34b46-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="34b46-137">Debian 8 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="34b46-138">APT での SDK またはランタイムの更新</span><span class="sxs-lookup"><span data-stu-id="34b46-138">APT update SDK or runtime</span></span>

<span data-ttu-id="34b46-139">.NET Core で新しい修正プログラムのリリースを利用できる場合は、次のコマンドを使用して、APT で簡単にアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="34b46-139">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="34b46-140">APT のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="34b46-140">APT troubleshooting</span></span>

<span data-ttu-id="34b46-141">このセクションでは、APT を使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="34b46-141">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="34b46-142">見つからない</span><span class="sxs-lookup"><span data-stu-id="34b46-142">Unable to locate</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="34b46-143">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="34b46-143">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="34b46-144">Snap</span><span class="sxs-lookup"><span data-stu-id="34b46-144">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="34b46-145">依存関係</span><span class="sxs-lookup"><span data-stu-id="34b46-145">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="34b46-146">スクリプトでのインストール</span><span class="sxs-lookup"><span data-stu-id="34b46-146">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="34b46-147">手動インストール</span><span class="sxs-lookup"><span data-stu-id="34b46-147">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="34b46-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="34b46-148">Next steps</span></span>

- [<span data-ttu-id="34b46-149">チュートリアル: Visual Studio Code を使用して .NET Core SDK でコンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="34b46-149">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
