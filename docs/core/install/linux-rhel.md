---
title: RHEL に .NET Core をインストールする - .NET Core
description: RHEL に .NET Core SDK と .NET Core ランタイムをインストールするさまざまな方法を示します。
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 7ae55f881cd0c877cf1db24be7a4ee23320e21a8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602796"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-rhel"></a><span data-ttu-id="88829-103">RHEL に .NET Core SDK または .NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="88829-103">Install .NET Core SDK or .NET Core Runtime on RHEL</span></span>

<span data-ttu-id="88829-104">.NET Core は RHEL でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="88829-104">.NET Core is supported on RHEL.</span></span> <span data-ttu-id="88829-105">この記事では、RHEL に .NET Core をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88829-105">This article describes how to install .NET Core on RHEL.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="88829-106">ご利用の Red Hat サブスクリプションを登録する</span><span class="sxs-lookup"><span data-stu-id="88829-106">Register your Red Hat subscription</span></span>

<span data-ttu-id="88829-107">Red Hat から RHEL に .NET Core をインストールするには、まず、Red Hat Subscription Manager を使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88829-107">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="88829-108">ご利用のシステム上でこれがまだ行われていない場合、または不明な場合は、[.NET Core 向け Red Hat 製品ドキュメント](https://access.redhat.com/documentation/net_core/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88829-108">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="88829-109">サポートされているディストリビューション</span><span class="sxs-lookup"><span data-stu-id="88829-109">Supported distributions</span></span>

<span data-ttu-id="88829-110">次の表は、RHEL 7 と RHEL 8 の両方で現在サポートされている .NET Core リリースの一覧です。</span><span class="sxs-lookup"><span data-stu-id="88829-110">The following table is a list of currently supported .NET Core releases on both RHEL 7 and RHEL 8.</span></span> <span data-ttu-id="88829-111">これらのバージョンは、[.NET Core のバージョンがサポート終了になる](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)か、RHEL のバージョンがサポート終了になるまでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="88829-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of RHEL is no longer supported.</span></span>

- <span data-ttu-id="88829-112">✔️ は、RHEL または .NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="88829-112">A ✔️ indicates that the version of RHEL or .NET Core is still supported.</span></span>
- <span data-ttu-id="88829-113">❌ は、RHEL または .NET Core のバージョンがその RHEL のリリースではサポートされていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="88829-113">A ❌ indicates that the version of RHEL or .NET Core isn't supported on that RHEL release.</span></span>
- <span data-ttu-id="88829-114">RHEL のバージョンと .NET Core のバージョンの両方に ✔️ が付いている場合、その OS と .NET の組み合わせはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="88829-114">When both a version of RHEL and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="88829-115">RHEL</span><span class="sxs-lookup"><span data-stu-id="88829-115">RHEL</span></span>                   | <span data-ttu-id="88829-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="88829-116">.NET Core 2.1</span></span> | <span data-ttu-id="88829-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="88829-117">.NET Core 3.1</span></span> | <span data-ttu-id="88829-118">.NET 5 Preview (手動インストールのみ)</span><span class="sxs-lookup"><span data-stu-id="88829-118">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="88829-119">✔️ [8](#rhel-8-)</span><span class="sxs-lookup"><span data-stu-id="88829-119">✔️ [8](#rhel-8-)</span></span> | <span data-ttu-id="88829-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="88829-120">✔️ 2.1</span></span>        | <span data-ttu-id="88829-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="88829-121">✔️ 3.1</span></span>        | <span data-ttu-id="88829-122">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="88829-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="88829-123">✔️ [7](#rhel-7-)</span><span class="sxs-lookup"><span data-stu-id="88829-123">✔️ [7](#rhel-7-)</span></span> | <span data-ttu-id="88829-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="88829-124">✔️ 2.1</span></span>        | <span data-ttu-id="88829-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="88829-125">✔️ 3.1</span></span>        | <span data-ttu-id="88829-126">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="88829-126">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="88829-127">次のバージョンの .NET Core は、サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="88829-127">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="88829-128">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="88829-128">The downloads for these still remain published:</span></span>

- <span data-ttu-id="88829-129">3.0</span><span class="sxs-lookup"><span data-stu-id="88829-129">3.0</span></span>
- <span data-ttu-id="88829-130">2.2</span><span class="sxs-lookup"><span data-stu-id="88829-130">2.2</span></span>
- <span data-ttu-id="88829-131">2.0</span><span class="sxs-lookup"><span data-stu-id="88829-131">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="88829-132">その他のバージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="88829-132">How to install other versions</span></span>

<span data-ttu-id="88829-133">.NET Core の他のリリースをインストールするために必要な手順については、[.NET Core に関する Red Hat のドキュメント](https://access.redhat.com/documentation/net_core/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88829-133">Consult the [Red Hat documentation for .NET Core](https://access.redhat.com/documentation/net_core/) on the steps required to install other releases of .NET Core.</span></span>

## <a name="rhel-8-"></a><span data-ttu-id="88829-134">RHEL 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="88829-134">RHEL 8 ✔️</span></span>

<span data-ttu-id="88829-135">.NET Core は、RHEL 8 用の AppStream リポジトリに含まれています。</span><span class="sxs-lookup"><span data-stu-id="88829-135">.NET Core is included in the AppStream repositories for RHEL 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="rhel-7-"></a><span data-ttu-id="88829-136">RHEL 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="88829-136">RHEL 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="88829-137">次のコマンドでは、`scl-utils` パッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="88829-137">The following command installs the `scl-utils` package:</span></span>

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a><span data-ttu-id="88829-138">SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="88829-138">Install the SDK</span></span>

<span data-ttu-id="88829-139">.NET Core SDK を使用すると、.NET Core を使用してアプリを開発できます。</span><span class="sxs-lookup"><span data-stu-id="88829-139">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="88829-140">.NET Core SDK をインストールする場合、対応するランタイムをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="88829-140">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="88829-141">.NET Core SDK をインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="88829-141">To install .NET Core SDK, run the following commands:</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

<span data-ttu-id="88829-142">Red Hat では、`rh-dotnet31` を永続的に有効にすることは推奨されません。他のプログラムに影響を与える可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="88829-142">Red Hat does not recommend permanently enabling `rh-dotnet31` because it may affect other programs.</span></span> <span data-ttu-id="88829-143">たとえば、`rh-dotnet31` には、ベースとなる RHEL のバージョンとは異なるバージョンの `libcurl` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88829-143">For example, `rh-dotnet31` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="88829-144">これにより、異なるバージョンの `libcurl` を想定していないプログラムで問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88829-144">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="88829-145">`rh-dotnet` を永続的に有効にする場合は、 _~/.bashrc_ ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="88829-145">If you want to enable `rh-dotnet` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a><span data-ttu-id="88829-146">ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="88829-146">Install the runtime</span></span>

<span data-ttu-id="88829-147">.NET Core ランタイムを使用すると、ランタイムを含まない .NET Core を使用して作成されたアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="88829-147">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="88829-148">次のコマンドを実行すると、.NET Core の最も互換性の高いランタイムである ASP.NET Core ランタイムがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="88829-148">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="88829-149">ご利用のターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="88829-149">In your terminal, run the following commands.</span></span>

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

<span data-ttu-id="88829-150">Red Hat では、`rh-dotnet31-aspnetcore-runtime-3.1` を永続的に有効にすることは推奨されません。他のプログラムに影響を与える可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="88829-150">Red Hat does not recommend permanently enabling `rh-dotnet31-aspnetcore-runtime-3.1` because it may affect other programs.</span></span> <span data-ttu-id="88829-151">たとえば、`rh-dotnet31-aspnetcore-runtime-3.1` には、ベースとなる RHEL のバージョンとは異なるバージョンの `libcurl` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88829-151">For example, `rh-dotnet31-aspnetcore-runtime-3.1` includes a version of `libcurl` that differs from the base RHEL version.</span></span> <span data-ttu-id="88829-152">これにより、異なるバージョンの `libcurl` を想定していないプログラムで問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88829-152">This may lead to issues in programs that do not expect a different version of `libcurl`.</span></span> <span data-ttu-id="88829-153">`rh-dotnet31-aspnetcore-runtime-3.1` を永続的に有効にする場合は、 _~/.bashrc_ ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="88829-153">If you want to enable `rh-dotnet31-aspnetcore-runtime-3.1` permanently, add the following line to your _~/.bashrc_ file.</span></span>

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

<span data-ttu-id="88829-154">ASP.NET Core ランタイムの代替手段として、ASP.NET Core サポートを含まない .NET Core ランタイムをインストールできます。それには、前述のコマンドの `rh-dotnet31-aspnetcore-runtime-3.1` を `rh-dotnet31-dotnet-runtime-3.1` で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="88829-154">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `rh-dotnet31-aspnetcore-runtime-3.1` in the commands above with `rh-dotnet31-dotnet-runtime-3.1`.</span></span>

## <a name="snap"></a><span data-ttu-id="88829-155">Snap</span><span class="sxs-lookup"><span data-stu-id="88829-155">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="88829-156">依存関係</span><span class="sxs-lookup"><span data-stu-id="88829-156">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="88829-157">スクリプトでのインストール</span><span class="sxs-lookup"><span data-stu-id="88829-157">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="88829-158">手動インストール</span><span class="sxs-lookup"><span data-stu-id="88829-158">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="88829-159">次の手順</span><span class="sxs-lookup"><span data-stu-id="88829-159">Next steps</span></span>

- [<span data-ttu-id="88829-160">チュートリアル: Visual Studio Code を使用して .NET Core SDK でコンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="88829-160">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
