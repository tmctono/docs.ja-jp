---
title: openSUSE に .NET Core をインストールする - .NET Core
description: openSUSE に .NET Core SDK と .NET Core ランタイムをインストールするさまざまな方法を示します。
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: ccdb23ca1838d2c15c9a95b45c8505efe7a6df0e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539231"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="b61d0-103">openSUSE に .NET Core SDK または .NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="b61d0-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="b61d0-104">.NET Core は openSUSE でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b61d0-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="b61d0-105">この記事では、openSUSE に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b61d0-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="b61d0-106">サポートされているディストリビューション</span><span class="sxs-lookup"><span data-stu-id="b61d0-106">Supported distributions</span></span>

<span data-ttu-id="b61d0-107">次の表は、openSUSE 15 で現在サポートされている .NET Core リリースの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b61d0-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="b61d0-108">これらのバージョンは、[.NET Core のバージョンがサポート終了になる](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)か、openSUSE のバージョンがサポート終了になるまでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b61d0-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="b61d0-109">✔️ は、openSUSE または .NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b61d0-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="b61d0-110">❌ は、openSUSE または .NET Core のバージョンがその openSUSE のリリースではサポートされていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b61d0-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="b61d0-111">openSUSE のバージョンと .NET Core のバージョンの両方に ✔️ が付いている場合、その OS と .NET の組み合わせはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b61d0-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="b61d0-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="b61d0-112">openSUSE</span></span>                   | <span data-ttu-id="b61d0-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b61d0-113">.NET Core 2.1</span></span> | <span data-ttu-id="b61d0-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b61d0-114">.NET Core 3.1</span></span> | <span data-ttu-id="b61d0-115">.NET 5 Preview (手動インストールのみ)</span><span class="sxs-lookup"><span data-stu-id="b61d0-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="b61d0-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="b61d0-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="b61d0-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="b61d0-117">✔️ 2.1</span></span>        | <span data-ttu-id="b61d0-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="b61d0-118">✔️ 3.1</span></span>        | <span data-ttu-id="b61d0-119">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="b61d0-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="b61d0-120">次のバージョンの .NET Core は、サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="b61d0-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="b61d0-121">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="b61d0-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="b61d0-122">3.0</span><span class="sxs-lookup"><span data-stu-id="b61d0-122">3.0</span></span>
- <span data-ttu-id="b61d0-123">2.2</span><span class="sxs-lookup"><span data-stu-id="b61d0-123">2.2</span></span>
- <span data-ttu-id="b61d0-124">2.0</span><span class="sxs-lookup"><span data-stu-id="b61d0-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b61d0-125">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="b61d0-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="b61d0-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="b61d0-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b61d0-127">パッケージ マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b61d0-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="b61d0-128">このセクションでは、パッケージ マネージャーを使用して .NET Core をインストールするときに発生する可能性のある一般的なエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b61d0-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="b61d0-129">パッケージが見つからない</span><span class="sxs-lookup"><span data-stu-id="b61d0-129">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="b61d0-130">フェッチできない</span><span class="sxs-lookup"><span data-stu-id="b61d0-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="b61d0-131">Snap</span><span class="sxs-lookup"><span data-stu-id="b61d0-131">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="b61d0-132">依存関係</span><span class="sxs-lookup"><span data-stu-id="b61d0-132">Dependencies</span></span>

<span data-ttu-id="b61d0-133">パッケージ マネージャーを使用してインストールする場合、次のライブラリが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b61d0-133">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="b61d0-134">ただし、手動で .NET Core をインストールする場合、または自己完結型アプリを公開する場合は、次のライブラリがインストールされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b61d0-134">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="b61d0-135">krb5</span><span class="sxs-lookup"><span data-stu-id="b61d0-135">krb5</span></span>
- <span data-ttu-id="b61d0-136">libicu</span><span class="sxs-lookup"><span data-stu-id="b61d0-136">libicu</span></span>
- <span data-ttu-id="b61d0-137">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="b61d0-137">libopenssl1_0_0</span></span>

<span data-ttu-id="b61d0-138">ターゲット ランタイム環境の OpenSSL バージョンが 1.1 以降である場合は、**compat-openssl10** をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b61d0-138">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="b61d0-139">依存関係の詳細については、「[Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」(自己完結型 Linux アプリケーション) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b61d0-139">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="b61d0-140">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="b61d0-140">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="b61d0-141">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="b61d0-141">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="b61d0-142">最新バージョンの *libgdiplus* をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="b61d0-142">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="b61d0-143">詳細については、「<https://www.mono-project.com/download/stable/>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b61d0-143">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="b61d0-144">スクリプトでのインストール</span><span class="sxs-lookup"><span data-stu-id="b61d0-144">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="b61d0-145">手動インストール</span><span class="sxs-lookup"><span data-stu-id="b61d0-145">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="b61d0-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="b61d0-146">Next steps</span></span>

- [<span data-ttu-id="b61d0-147">チュートリアル: Visual Studio Code を使用して .NET Core SDK でコンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="b61d0-147">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
