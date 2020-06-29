---
title: Alpine に .NET Core をインストールする - .NET Core
description: Alpine に .NET Core SDK と .NET Core ランタイムをインストールするさまざまな方法を示します。
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 92753933cbcedae28867b66293d1044f700d7baa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324834"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a><span data-ttu-id="91bb2-103">Alpine に .NET Core SDK または .NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="91bb2-103">Install .NET Core SDK or .NET Core Runtime on Alpine</span></span>

<span data-ttu-id="91bb2-104">この記事では、Alpine に .NET Core をインストール方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91bb2-104">This article describes how to install .NET Core on Alpine.</span></span> <span data-ttu-id="91bb2-105">Alpine のバージョンがサポート対象外である場合、.NET Core もそのバージョンでサポート対象外となります。</span><span class="sxs-lookup"><span data-stu-id="91bb2-105">When a Alpine version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="91bb2-106">ただし、サポート対象外のバージョンで .NET Core を実行するのに、ここで説明する手順が役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="91bb2-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="91bb2-107">Alpine には、インストーラーはありません。</span><span class="sxs-lookup"><span data-stu-id="91bb2-107">There are no installers for Alpine.</span></span> <span data-ttu-id="91bb2-108">[インストール スクリプト](#scripted-install)を使用するか、[手動でのインストール](#manual-install)手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="91bb2-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="91bb2-109">サポートされているディストリビューション</span><span class="sxs-lookup"><span data-stu-id="91bb2-109">Supported distributions</span></span>

<span data-ttu-id="91bb2-110">次の表に、現在サポートされている .NET Core リリースと、それらがサポートされている Alpine のバージョンの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="91bb2-110">The following table is a list of currently supported .NET Core releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="91bb2-111">これらのバージョンは、[.NET Core のバージョンがサポート終了](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)するか、[Alpine のバージョンの有効期限が切れるまで](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases)サポートされます。</span><span class="sxs-lookup"><span data-stu-id="91bb2-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="91bb2-112">✔️ は、Alpine または .NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="91bb2-112">A ✔️ indicates that the version of Alpine or .NET Core is still supported.</span></span>
- <span data-ttu-id="91bb2-113">❌ は、Alpine または .NET Core のバージョンがその Alpine のリリースではサポートされないことを示します。</span><span class="sxs-lookup"><span data-stu-id="91bb2-113">A ❌ indicates that the version of Alpine or .NET Core isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="91bb2-114">Alpine のバージョンと .NET Core のバージョンの両方に ✔️ がある場合、その OS と .NET の組み合わせはサポートされます。</span><span class="sxs-lookup"><span data-stu-id="91bb2-114">When both a version of Alpine and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="91bb2-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="91bb2-115">Alpine</span></span>                   | <span data-ttu-id="91bb2-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-116">.NET Core 2.1</span></span> | <span data-ttu-id="91bb2-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-117">.NET Core 3.1</span></span> | <span data-ttu-id="91bb2-118">.NET 5 Preview</span><span class="sxs-lookup"><span data-stu-id="91bb2-118">.NET 5 Preview</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="91bb2-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="91bb2-119">✔️ 3.12</span></span>  | <span data-ttu-id="91bb2-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-120">✔️ 2.1</span></span>        | <span data-ttu-id="91bb2-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-121">✔️ 3.1</span></span>        | <span data-ttu-id="91bb2-122">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="91bb2-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="91bb2-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="91bb2-123">✔️ 3.11</span></span>  | <span data-ttu-id="91bb2-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-124">✔️ 2.1</span></span>        | <span data-ttu-id="91bb2-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-125">✔️ 3.1</span></span>        | <span data-ttu-id="91bb2-126">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="91bb2-126">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="91bb2-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="91bb2-127">✔️ 3.10</span></span>  | <span data-ttu-id="91bb2-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-128">✔️ 2.1</span></span>        | <span data-ttu-id="91bb2-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-129">✔️ 3.1</span></span>        | <span data-ttu-id="91bb2-130">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="91bb2-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="91bb2-131">✔️ 3.9</span><span class="sxs-lookup"><span data-stu-id="91bb2-131">✔️ 3.9</span></span>   | <span data-ttu-id="91bb2-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-132">✔️ 2.1</span></span>        | <span data-ttu-id="91bb2-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-133">✔️ 3.1</span></span>        | <span data-ttu-id="91bb2-134">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="91bb2-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="91bb2-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="91bb2-135">❌ 3.8</span></span>   | <span data-ttu-id="91bb2-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-136">✔️ 2.1</span></span>        | <span data-ttu-id="91bb2-137">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="91bb2-137">❌ 3.1</span></span>        | <span data-ttu-id="91bb2-138">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="91bb2-138">❌ 5.0 Preview</span></span> |

<span data-ttu-id="91bb2-139">次のバージョンの .NET Core は、サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="91bb2-139">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="91bb2-140">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="91bb2-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="91bb2-141">3.0</span><span class="sxs-lookup"><span data-stu-id="91bb2-141">3.0</span></span>
- <span data-ttu-id="91bb2-142">2.2</span><span class="sxs-lookup"><span data-stu-id="91bb2-142">2.2</span></span>
- <span data-ttu-id="91bb2-143">2.0</span><span class="sxs-lookup"><span data-stu-id="91bb2-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="91bb2-144">依存関係</span><span class="sxs-lookup"><span data-stu-id="91bb2-144">Dependencies</span></span>

<span data-ttu-id="91bb2-145">Alpine Linux 上の .NET Core には、次の依存関係がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="91bb2-145">.NET Core on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="91bb2-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="91bb2-146">icu-libs</span></span>
- <span data-ttu-id="91bb2-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="91bb2-147">krb5-libs</span></span>
- <span data-ttu-id="91bb2-148">libintl</span><span class="sxs-lookup"><span data-stu-id="91bb2-148">libintl</span></span>
- <span data-ttu-id="91bb2-149">libssl1.1 (Alpine v3.9 以上)</span><span class="sxs-lookup"><span data-stu-id="91bb2-149">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="91bb2-150">libssl1.0 (Alpine v3.8)</span><span class="sxs-lookup"><span data-stu-id="91bb2-150">libssl1.0 (Alpine v3.8)</span></span>
- <span data-ttu-id="91bb2-151">libstdc++</span><span class="sxs-lookup"><span data-stu-id="91bb2-151">libstdc++</span></span>
- <span data-ttu-id="91bb2-152">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="91bb2-152">lttng-ust</span></span>
- <span data-ttu-id="91bb2-153">numactl (省略可能)</span><span class="sxs-lookup"><span data-stu-id="91bb2-153">numactl (optional)</span></span>
- <span data-ttu-id="91bb2-154">zlib</span><span class="sxs-lookup"><span data-stu-id="91bb2-154">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="91bb2-155">スクリプトでのインストール</span><span class="sxs-lookup"><span data-stu-id="91bb2-155">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="91bb2-156">手動インストール</span><span class="sxs-lookup"><span data-stu-id="91bb2-156">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="91bb2-157">次の手順</span><span class="sxs-lookup"><span data-stu-id="91bb2-157">Next steps</span></span>

- [<span data-ttu-id="91bb2-158">チュートリアル: Visual Studio Code を使用して .NET Core SDK でコンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="91bb2-158">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
