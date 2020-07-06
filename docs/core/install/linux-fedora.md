---
title: Fedora に .NET Core をインストールする - .NET Core
description: Fedora に .NET Core SDK と .NET Core ランタイムをインストールするさまざまな方法を示します。
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: c90c08eefa074fa139642a268f879af79d7280da
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619482"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-fedora"></a><span data-ttu-id="b3489-103">Fedora に .NET Core SDK または .NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="b3489-103">Install .NET Core SDK or .NET Core Runtime on Fedora</span></span>

<span data-ttu-id="b3489-104">.NET Core は Fedora でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3489-104">.NET Core is supported on Fedora.</span></span> <span data-ttu-id="b3489-105">この記事では、Fedora に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3489-105">This article describes how to install .NET Core on Fedora.</span></span> <span data-ttu-id="b3489-106">Fedora のバージョンがサポート対象外である場合、.NET Core もそのバージョンでサポート対象外となります。</span><span class="sxs-lookup"><span data-stu-id="b3489-106">When a Fedora version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="b3489-107">ただし、サポートされていない場合でも、以下の手順はそれらのバージョンで実行される .NET Core の取得に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3489-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="b3489-108">サポートされているディストリビューション</span><span class="sxs-lookup"><span data-stu-id="b3489-108">Supported distributions</span></span>

<span data-ttu-id="b3489-109">次の表は、現在サポートされている .NET Core リリースと、それらがサポートされている Fedora のバージョンの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b3489-109">The following table is a list of currently supported .NET Core releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="b3489-110">これらのバージョンは、[.NET Core のバージョンがサポート終了になる](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)か、[Fedora のバージョンがサポート終了になる](https://fedoraproject.org/wiki/End_of_life)までサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b3489-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="b3489-111">✔️ は、Fedora または .NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b3489-111">A ✔️ indicates that the version of Fedora or .NET Core is still supported.</span></span>
- <span data-ttu-id="b3489-112">❌ は、Fedora または .NET Core のバージョンがその Fedora のリリースではサポートされていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b3489-112">A ❌ indicates that the version of Fedora or .NET Core isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="b3489-113">Fedora のバージョンと .NET Core のバージョンの両方に ✔️ が付いている場合、その OS と .NET の組み合わせはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3489-113">When both a version of Fedora and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="b3489-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="b3489-114">Fedora</span></span>                   | <span data-ttu-id="b3489-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b3489-115">.NET Core 2.1</span></span> | <span data-ttu-id="b3489-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b3489-116">.NET Core 3.1</span></span> | <span data-ttu-id="b3489-117">.NET 5 Preview (手動インストールのみ)</span><span class="sxs-lookup"><span data-stu-id="b3489-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="b3489-118">✔️ [32](linux-fedora.md#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="b3489-118">✔️ [32](linux-fedora.md#fedora-32-)</span></span> | <span data-ttu-id="b3489-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b3489-119">✔️ 2.1</span></span>        | <span data-ttu-id="b3489-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b3489-120">✔️ 3.1</span></span>        | <span data-ttu-id="b3489-121">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="b3489-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b3489-122">✔️ [31](linux-fedora.md#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="b3489-122">✔️ [31](linux-fedora.md#fedora-31-)</span></span> | <span data-ttu-id="b3489-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b3489-123">✔️ 2.1</span></span>        | <span data-ttu-id="b3489-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b3489-124">✔️ 3.1</span></span>        | <span data-ttu-id="b3489-125">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="b3489-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="b3489-126">❌ [30](linux-fedora.md#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="b3489-126">❌ [30](linux-fedora.md#fedora-30-)</span></span> | <span data-ttu-id="b3489-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b3489-127">✔️ 2.1</span></span>        | <span data-ttu-id="b3489-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b3489-128">✔️ 3.1</span></span>        | <span data-ttu-id="b3489-129">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="b3489-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="b3489-130">❌ [29](linux-fedora.md#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="b3489-130">❌ [29](linux-fedora.md#fedora-29-)</span></span> | <span data-ttu-id="b3489-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b3489-131">✔️ 2.1</span></span>        | <span data-ttu-id="b3489-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b3489-132">✔️ 3.1</span></span>        | <span data-ttu-id="b3489-133">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="b3489-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="b3489-134">❌ [28](linux-fedora.md#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="b3489-134">❌ [28](linux-fedora.md#fedora-28-)</span></span> | <span data-ttu-id="b3489-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b3489-135">✔️ 2.1</span></span>        | <span data-ttu-id="b3489-136">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="b3489-136">❌ 3.1</span></span>        | <span data-ttu-id="b3489-137">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="b3489-137">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="b3489-138">❌ [27](linux-fedora.md#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="b3489-138">❌ [27](linux-fedora.md#fedora-27-)</span></span> | <span data-ttu-id="b3489-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b3489-139">✔️ 2.1</span></span>        | <span data-ttu-id="b3489-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="b3489-140">❌ 3.1</span></span>        | <span data-ttu-id="b3489-141">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="b3489-141">❌ 5.0 Preview</span></span> |

<span data-ttu-id="b3489-142">次のバージョンの .NET Core は、サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="b3489-142">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="b3489-143">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="b3489-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="b3489-144">3.0</span><span class="sxs-lookup"><span data-stu-id="b3489-144">3.0</span></span>
- <span data-ttu-id="b3489-145">2.2</span><span class="sxs-lookup"><span data-stu-id="b3489-145">2.2</span></span>
- <span data-ttu-id="b3489-146">2.0</span><span class="sxs-lookup"><span data-stu-id="b3489-146">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b3489-147">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="b3489-147">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-32-"></a><span data-ttu-id="b3489-148">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="b3489-148">Fedora 32 ✔️</span></span>

<span data-ttu-id="b3489-149">.NET Core 3.1 は Fedora 32 の既定のパッケージ リポジトリで利用できます。</span><span class="sxs-lookup"><span data-stu-id="b3489-149">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="b3489-150">Fedora 31 ✔️</span><span class="sxs-lookup"><span data-stu-id="b3489-150">Fedora 31 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="b3489-151">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="b3489-151">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="b3489-152">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="b3489-152">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="b3489-153">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="b3489-153">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="b3489-154">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="b3489-154">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b3489-155">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b3489-155">Troubleshoot the package manager</span></span>

<span data-ttu-id="b3489-156">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3489-156">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="b3489-157">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="b3489-157">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="b3489-158">Snap</span><span class="sxs-lookup"><span data-stu-id="b3489-158">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="b3489-159">依存関係</span><span class="sxs-lookup"><span data-stu-id="b3489-159">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="b3489-160">スクリプトでのインストール</span><span class="sxs-lookup"><span data-stu-id="b3489-160">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="b3489-161">手動インストール</span><span class="sxs-lookup"><span data-stu-id="b3489-161">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="b3489-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="b3489-162">Next steps</span></span>

- [<span data-ttu-id="b3489-163">チュートリアル: Visual Studio Code を使用して .NET Core SDK でコンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="b3489-163">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
