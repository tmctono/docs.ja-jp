---
title: SLES に .NET Core をインストールする - .NET Core
description: SLES に .NET Core SDK と .NET Core ランタイムをインストールするさまざまな方法を示します。
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: b2eab6a0305d492e37e1b33d02be43ca41d42b6f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602790"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a><span data-ttu-id="c4ba5-103">SLES に .NET Core SDK または .NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="c4ba5-103">Install .NET Core SDK or .NET Core Runtime on SLES</span></span>

<span data-ttu-id="c4ba5-104">.NET Core は SLES でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-104">.NET Core is supported on SLES.</span></span> <span data-ttu-id="c4ba5-105">この記事では、SLES に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-105">This article describes how to install .NET Core on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="c4ba5-106">サポートされているディストリビューション</span><span class="sxs-lookup"><span data-stu-id="c4ba5-106">Supported distributions</span></span>

<span data-ttu-id="c4ba5-107">次の表は、SLES 12 SP2 と SLES 15 の両方で現在サポートされている .NET Core リリースの一覧です。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-107">The following table is a list of currently supported .NET Core releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="c4ba5-108">これらのバージョンは、[.NET Core のバージョンがサポート終了になる](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)か、SLES のバージョンがサポート終了になるまでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="c4ba5-109">✔️ は、SLES または .NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-109">A ✔️ indicates that the version of SLES or .NET Core is still supported.</span></span>
- <span data-ttu-id="c4ba5-110">❌ は、SLES または .NET Core のバージョンがその SLES のリリースではサポートされていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-110">A ❌ indicates that the version of SLES or .NET Core isn't supported on that SLES release.</span></span>
- <span data-ttu-id="c4ba5-111">SLES のバージョンと .NET Core のバージョンの両方に ✔️ が付いている場合、その OS と .NET の組み合わせはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-111">When both a version of SLES and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="c4ba5-112">SLES</span><span class="sxs-lookup"><span data-stu-id="c4ba5-112">SLES</span></span>                   | <span data-ttu-id="c4ba5-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c4ba5-113">.NET Core 2.1</span></span> | <span data-ttu-id="c4ba5-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c4ba5-114">.NET Core 3.1</span></span> | <span data-ttu-id="c4ba5-115">.NET 5 Preview (手動インストールのみ)</span><span class="sxs-lookup"><span data-stu-id="c4ba5-115">.NET 5 Preview (manual install only)</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="c4ba5-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="c4ba5-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="c4ba5-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="c4ba5-117">✔️ 2.1</span></span>        | <span data-ttu-id="c4ba5-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="c4ba5-118">✔️ 3.1</span></span>        | <span data-ttu-id="c4ba5-119">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="c4ba5-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="c4ba5-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="c4ba5-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="c4ba5-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="c4ba5-121">✔️ 2.1</span></span>        | <span data-ttu-id="c4ba5-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="c4ba5-122">✔️ 3.1</span></span>        | <span data-ttu-id="c4ba5-123">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="c4ba5-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="c4ba5-124">次のバージョンの .NET Core は、サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="c4ba5-125">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="c4ba5-126">3.0</span><span class="sxs-lookup"><span data-stu-id="c4ba5-126">3.0</span></span>
- <span data-ttu-id="c4ba5-127">2.2</span><span class="sxs-lookup"><span data-stu-id="c4ba5-127">2.2</span></span>
- <span data-ttu-id="c4ba5-128">2.0</span><span class="sxs-lookup"><span data-stu-id="c4ba5-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="c4ba5-129">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="c4ba5-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="c4ba5-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="c4ba5-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="c4ba5-131">現時点では、SLES 15 Microsoft リポジトリ セットアップ パッケージによって "*microsoft-prod.repo*" ファイルが間違ったディレクトリにインストールされるため、zypper が .NET Core パッケージを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="c4ba5-132">この問題を解決するには、正しいディレクトリにシンボリックリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="c4ba5-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="c4ba5-133">SLES 12 ✔️</span></span>

<span data-ttu-id="c4ba5-134">.NET Core では、SLES 12 ファミリの最小要件として SP2 が必要です。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-134">.NET Core requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="c4ba5-135">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c4ba5-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="c4ba5-136">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4ba5-136">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="c4ba5-137">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="c4ba5-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="c4ba5-138">Snap</span><span class="sxs-lookup"><span data-stu-id="c4ba5-138">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="c4ba5-139">依存関係</span><span class="sxs-lookup"><span data-stu-id="c4ba5-139">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="c4ba5-140">スクリプトでのインストール</span><span class="sxs-lookup"><span data-stu-id="c4ba5-140">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="c4ba5-141">手動インストール</span><span class="sxs-lookup"><span data-stu-id="c4ba5-141">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="c4ba5-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="c4ba5-142">Next steps</span></span>

- [<span data-ttu-id="c4ba5-143">チュートリアル: Visual Studio Code を使用して .NET Core SDK でコンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="c4ba5-143">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
