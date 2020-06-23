---
title: Alpine に .NET Core をインストールする - .NET Core
description: Alpine に .NET Core SDK と .NET Core ランタイムをインストールするさまざまな方法を示します。
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: bbaf4ee9020dcd33c894b5376bf04ad65db8d378
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2020
ms.locfileid: "84771489"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a><span data-ttu-id="0584a-103">Alpine に .NET Core SDK または .NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="0584a-103">Install .NET Core SDK or .NET Core Runtime on Alpine</span></span>

<span data-ttu-id="0584a-104">この記事では、Alpine に .NET Core をインストール方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0584a-104">This article describes how to install .NET Core on Alpine.</span></span> <span data-ttu-id="0584a-105">Alpine のバージョンがサポート対象外である場合、.NET Core もそのバージョンでサポート対象外となります。</span><span class="sxs-lookup"><span data-stu-id="0584a-105">When a Alpine version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="0584a-106">ただし、サポート対象外のバージョンで .NET Core を実行するのに、ここで説明する手順が役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="0584a-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="0584a-107">Alpine には、インストーラーはありません。</span><span class="sxs-lookup"><span data-stu-id="0584a-107">There are no installers for Alpine.</span></span> <span data-ttu-id="0584a-108">[インストール スクリプト](#scripted-install)を使用するか、[手動でのインストール](#manual-install)手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0584a-108">You must either use the [install script](#scripted-install) or follow the [manual install](#manual-install) instructions.</span></span>

## <a name="supported-distributions"></a><span data-ttu-id="0584a-109">サポートされているディストリビューション</span><span class="sxs-lookup"><span data-stu-id="0584a-109">Supported distributions</span></span>

<span data-ttu-id="0584a-110">次の表に、現在サポートされている .NET Core リリースと、それらがサポートされている Alpine のバージョンの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0584a-110">The following table is a list of currently supported .NET Core releases and the versions of Alpine they're supported on.</span></span> <span data-ttu-id="0584a-111">これらのバージョンは、[.NET Core のバージョンがサポート終了](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)するか、[Alpine のバージョンの有効期限が切れるまで](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases)サポートされます。</span><span class="sxs-lookup"><span data-stu-id="0584a-111">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Alpine reaches end-of-life](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).</span></span>

- <span data-ttu-id="0584a-112">✔️ は、Alpine または .NET Core のバージョンがまだサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="0584a-112">A ✔️ indicates that the version of Alpine or .NET Core is still supported.</span></span>
- <span data-ttu-id="0584a-113">❌ は、Alpine または .NET Core のバージョンがその Alpine のリリースではサポートされないことを示します。</span><span class="sxs-lookup"><span data-stu-id="0584a-113">A ❌ indicates that the version of Alpine or .NET Core isn't supported on that Alpine release.</span></span>
- <span data-ttu-id="0584a-114">Alpine のバージョンと .NET Core のバージョンの両方に ✔️ がある場合、その OS と .NET の組み合わせはサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0584a-114">When both a version of Alpine and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="0584a-115">Alpine</span><span class="sxs-lookup"><span data-stu-id="0584a-115">Alpine</span></span>                   | <span data-ttu-id="0584a-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0584a-116">.NET Core 2.1</span></span> | <span data-ttu-id="0584a-117">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="0584a-117">.NET Core 3.1</span></span> | <span data-ttu-id="0584a-118">.NET 5 Preview</span><span class="sxs-lookup"><span data-stu-id="0584a-118">.NET 5 Preview</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="0584a-119">✔️ 3.12</span><span class="sxs-lookup"><span data-stu-id="0584a-119">✔️ 3.12</span></span>  | <span data-ttu-id="0584a-120">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="0584a-120">✔️ 2.1</span></span>        | <span data-ttu-id="0584a-121">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="0584a-121">✔️ 3.1</span></span>        | <span data-ttu-id="0584a-122">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="0584a-122">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="0584a-123">✔️ 3.11</span><span class="sxs-lookup"><span data-stu-id="0584a-123">✔️ 3.11</span></span>  | <span data-ttu-id="0584a-124">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="0584a-124">✔️ 2.1</span></span>        | <span data-ttu-id="0584a-125">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="0584a-125">✔️ 3.1</span></span>        | <span data-ttu-id="0584a-126">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="0584a-126">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="0584a-127">✔️ 3.10</span><span class="sxs-lookup"><span data-stu-id="0584a-127">✔️ 3.10</span></span>  | <span data-ttu-id="0584a-128">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="0584a-128">✔️ 2.1</span></span>        | <span data-ttu-id="0584a-129">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="0584a-129">✔️ 3.1</span></span>        | <span data-ttu-id="0584a-130">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="0584a-130">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="0584a-131">✔️ 3.9</span><span class="sxs-lookup"><span data-stu-id="0584a-131">✔️ 3.9</span></span>   | <span data-ttu-id="0584a-132">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="0584a-132">✔️ 2.1</span></span>        | <span data-ttu-id="0584a-133">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="0584a-133">✔️ 3.1</span></span>        | <span data-ttu-id="0584a-134">✔️ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="0584a-134">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="0584a-135">❌ 3.8</span><span class="sxs-lookup"><span data-stu-id="0584a-135">❌ 3.8</span></span>   | <span data-ttu-id="0584a-136">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="0584a-136">✔️ 2.1</span></span>        | <span data-ttu-id="0584a-137">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="0584a-137">❌ 3.1</span></span>        | <span data-ttu-id="0584a-138">❌ 5.0 Preview</span><span class="sxs-lookup"><span data-stu-id="0584a-138">❌ 5.0 Preview</span></span> |

<span data-ttu-id="0584a-139">次のバージョンの .NET Core は、サポート対象外となりました。</span><span class="sxs-lookup"><span data-stu-id="0584a-139">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="0584a-140">これらのダウンロードは、まだ公開されています。</span><span class="sxs-lookup"><span data-stu-id="0584a-140">The downloads for these still remain published:</span></span>

- <span data-ttu-id="0584a-141">3.0</span><span class="sxs-lookup"><span data-stu-id="0584a-141">3.0</span></span>
- <span data-ttu-id="0584a-142">2.2</span><span class="sxs-lookup"><span data-stu-id="0584a-142">2.2</span></span>
- <span data-ttu-id="0584a-143">2.0</span><span class="sxs-lookup"><span data-stu-id="0584a-143">2.0</span></span>

## <a name="dependencies"></a><span data-ttu-id="0584a-144">依存関係</span><span class="sxs-lookup"><span data-stu-id="0584a-144">Dependencies</span></span>

<span data-ttu-id="0584a-145">Alpine Linux 上の .NET Core には、次の依存関係がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0584a-145">.NET Core on Alpine Linux requires the following dependencies installed:</span></span>

- <span data-ttu-id="0584a-146">icu-libs</span><span class="sxs-lookup"><span data-stu-id="0584a-146">icu-libs</span></span>
- <span data-ttu-id="0584a-147">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="0584a-147">krb5-libs</span></span>
- <span data-ttu-id="0584a-148">libintl</span><span class="sxs-lookup"><span data-stu-id="0584a-148">libintl</span></span>
- <span data-ttu-id="0584a-149">libssl1.1 (Alpine v3.9 以上)</span><span class="sxs-lookup"><span data-stu-id="0584a-149">libssl1.1 (Alpine v3.9 or greater)</span></span>
- <span data-ttu-id="0584a-150">libssl1.0 (Alpine v3.8)</span><span class="sxs-lookup"><span data-stu-id="0584a-150">libssl1.0 (Alpine v3.8)</span></span>
- <span data-ttu-id="0584a-151">libstdc++</span><span class="sxs-lookup"><span data-stu-id="0584a-151">libstdc++</span></span>
- <span data-ttu-id="0584a-152">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="0584a-152">lttng-ust</span></span>
- <span data-ttu-id="0584a-153">numactl (省略可能)</span><span class="sxs-lookup"><span data-stu-id="0584a-153">numactl (optional)</span></span>
- <span data-ttu-id="0584a-154">zlib</span><span class="sxs-lookup"><span data-stu-id="0584a-154">zlib</span></span>

## <a name="scripted-install"></a><span data-ttu-id="0584a-155">スクリプトでのインストール</span><span class="sxs-lookup"><span data-stu-id="0584a-155">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="0584a-156">手動インストール</span><span class="sxs-lookup"><span data-stu-id="0584a-156">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="0584a-157">次の手順</span><span class="sxs-lookup"><span data-stu-id="0584a-157">Next steps</span></span>

- [<span data-ttu-id="0584a-158">チュートリアル: Visual Studio Code を使用して .NET Core SDK でコンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="0584a-158">Tutorial: Create a console application with .NET Core SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
