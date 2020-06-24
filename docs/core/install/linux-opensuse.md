---
title: openSUSE に .NET Core をインストールする - .NET Core
description: openSUSE に .NET Core SDK と .NET Core ランタイムをインストールするさまざまな方法を示します。
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: a642cee9ae78f81cd671d8745d5ce241be6a3b69
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602802"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="efbd2-103">openSUSE に .NET Core SDK または .NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="efbd2-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="efbd2-104">.NET Core は openSUSE でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="efbd2-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="efbd2-105">この記事では、openSUSE に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="efbd2-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="efbd2-106">サポートされているディストリビューション</span><span class="sxs-lookup"><span data-stu-id="efbd2-106">Supported distributions</span></span>

<span data-ttu-id="efbd2-107">次の表は、openSUSE 15 で現在サポートされている .NET Core リリースの一覧です。</span><span class="sxs-lookup"><span data-stu-id="efbd2-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="efbd2-108">これらのバージョンは、[.NET Core のバージョンがサポート終了になる](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)か、openSUSE のバージョンがサポート終了になるまでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="efbd2-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="efbd2-109">✔️ は、openSUSE または .NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="efbd2-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="efbd2-110">❌ は、openSUSE または .NET Core のバージョンがその openSUSE のリリースではサポートされていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="efbd2-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="efbd2-111">openSUSE のバージョンと .NET Core のバージョンの両方に ✔️ が付いている場合、その OS と .NET の組み合わせはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="efbd2-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="efbd2-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="efbd2-112">openSUSE</span></span>                   | <span data-ttu-id="efbd2-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="efbd2-113">.NET Core 2.1</span></span> | <span data-ttu-id="efbd2-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="efbd2-114">.NET Core 3.1</span></span> | <span data-ttu-id="efbd2-115">.NET 5 Preview (手動インストールのみ)</span><span class="sxs-lookup"><span data-stu-id="efbd2-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="efbd2-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="efbd2-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="efbd2-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="efbd2-117">✔️ 2.1</span></span>        | <span data-ttu-id="efbd2-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="efbd2-118">✔️ 3.1</span></span>        | <span data-ttu-id="efbd2-119">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="efbd2-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="efbd2-120">次のバージョンの .NET Core は、サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="efbd2-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="efbd2-121">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="efbd2-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="efbd2-122">3.0</span><span class="sxs-lookup"><span data-stu-id="efbd2-122">3.0</span></span>
- <span data-ttu-id="efbd2-123">2.2</span><span class="sxs-lookup"><span data-stu-id="efbd2-123">2.2</span></span>
- <span data-ttu-id="efbd2-124">2.0</span><span class="sxs-lookup"><span data-stu-id="efbd2-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="efbd2-125">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="efbd2-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="efbd2-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="efbd2-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="efbd2-127">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="efbd2-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="efbd2-128">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="efbd2-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="efbd2-129">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="efbd2-129">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="efbd2-130">Snap</span><span class="sxs-lookup"><span data-stu-id="efbd2-130">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="efbd2-131">依存関係</span><span class="sxs-lookup"><span data-stu-id="efbd2-131">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="efbd2-132">スクリプトでのインストール</span><span class="sxs-lookup"><span data-stu-id="efbd2-132">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="efbd2-133">手動インストール</span><span class="sxs-lookup"><span data-stu-id="efbd2-133">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="efbd2-134">次の手順</span><span class="sxs-lookup"><span data-stu-id="efbd2-134">Next steps</span></span>

- [<span data-ttu-id="efbd2-135">チュートリアル: Visual Studio Code を使用して .NET Core SDK でコンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="efbd2-135">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
