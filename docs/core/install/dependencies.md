---
title: .NET Core SDK とランタイムの依存関係 - .NET Core
description: Windows、Linux、および macOS に .NET Core SDK とランタイムをインストールするためのオペレーティング システムと CPU アーキテクチャの前提条件について説明します。
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 023b8fdf029dd6b17fe2186296d87dd7507c60b5
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546563"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="849eb-103">.NET Core の依存関係と要件</span><span class="sxs-lookup"><span data-stu-id="849eb-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="849eb-104">この記事では、.NET Core でサポートされているオペレーティング システムと CPU アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="849eb-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="849eb-105">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="849eb-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="849eb-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="849eb-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="849eb-107">.NET Core 3.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="849eb-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="849eb-108">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="849eb-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="849eb-109">OS</span><span class="sxs-lookup"><span data-stu-id="849eb-109">OS</span></span>                            | <span data-ttu-id="849eb-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="849eb-110">Version</span></span>                        | <span data-ttu-id="849eb-111">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="849eb-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="849eb-112">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="849eb-112">Windows Client</span></span>                | <span data-ttu-id="849eb-113">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="849eb-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="849eb-114">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-114">x64, x86</span></span>        |
| <span data-ttu-id="849eb-115">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="849eb-115">Windows 10 Client</span></span>             | <span data-ttu-id="849eb-116">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="849eb-116">Version 1607+</span></span>                  | <span data-ttu-id="849eb-117">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-117">x64, x86</span></span>        |
| <span data-ttu-id="849eb-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="849eb-118">Windows Server</span></span>                | <span data-ttu-id="849eb-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="849eb-119">2012 R2+</span></span>                       | <span data-ttu-id="849eb-120">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-120">x64, x86</span></span>        |
| <span data-ttu-id="849eb-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="849eb-121">Nano Server</span></span>                   | <span data-ttu-id="849eb-122">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="849eb-122">Version 1803+</span></span>                  | <span data-ttu-id="849eb-123">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="849eb-123">x64, ARM32</span></span>      |

<span data-ttu-id="849eb-124">.NET Core 3.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)」(.NET Core 3.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="849eb-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="849eb-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="849eb-126">" *.NET Core 3.0 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="849eb-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="849eb-127">.NET Core 3.0 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="849eb-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="849eb-128">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="849eb-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="849eb-129">OS</span><span class="sxs-lookup"><span data-stu-id="849eb-129">OS</span></span>                            | <span data-ttu-id="849eb-130">バージョン</span><span class="sxs-lookup"><span data-stu-id="849eb-130">Version</span></span>                        | <span data-ttu-id="849eb-131">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="849eb-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="849eb-132">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="849eb-132">Windows Client</span></span>                | <span data-ttu-id="849eb-133">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="849eb-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="849eb-134">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-134">x64, x86</span></span>        |
| <span data-ttu-id="849eb-135">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="849eb-135">Windows 10 Client</span></span>             | <span data-ttu-id="849eb-136">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="849eb-136">Version 1607+</span></span>                  | <span data-ttu-id="849eb-137">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-137">x64, x86</span></span>        |
| <span data-ttu-id="849eb-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="849eb-138">Windows Server</span></span>                | <span data-ttu-id="849eb-139">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="849eb-139">2012 R2+</span></span>                       | <span data-ttu-id="849eb-140">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-140">x64, x86</span></span>        |
| <span data-ttu-id="849eb-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="849eb-141">Nano Server</span></span>                   | <span data-ttu-id="849eb-142">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="849eb-142">Version 1803+</span></span>                  | <span data-ttu-id="849eb-143">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="849eb-143">x64, ARM32</span></span>      |

<span data-ttu-id="849eb-144">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)」(.NET Core 3.0 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="849eb-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="849eb-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="849eb-146">" *.NET Core 2.2 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="849eb-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="849eb-147">.NET Core 2.2 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="849eb-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="849eb-148">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="849eb-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="849eb-149">OS</span><span class="sxs-lookup"><span data-stu-id="849eb-149">OS</span></span>                            | <span data-ttu-id="849eb-150">バージョン</span><span class="sxs-lookup"><span data-stu-id="849eb-150">Version</span></span>                        | <span data-ttu-id="849eb-151">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="849eb-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="849eb-152">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="849eb-152">Windows Client</span></span>                | <span data-ttu-id="849eb-153">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="849eb-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="849eb-154">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-154">x64, x86</span></span>        |
| <span data-ttu-id="849eb-155">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="849eb-155">Windows 10 Client</span></span>             | <span data-ttu-id="849eb-156">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="849eb-156">Version 1607+</span></span>                  | <span data-ttu-id="849eb-157">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-157">x64, x86</span></span>        |
| <span data-ttu-id="849eb-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="849eb-158">Windows Server</span></span>                | <span data-ttu-id="849eb-159">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="849eb-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="849eb-160">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-160">x64, x86</span></span>        |
| <span data-ttu-id="849eb-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="849eb-161">Nano Server</span></span>                   | <span data-ttu-id="849eb-162">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="849eb-162">Version 1803+</span></span>                   | <span data-ttu-id="849eb-163">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="849eb-163">x64, ARM32</span></span>      |

<span data-ttu-id="849eb-164">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)」(.NET Core 2.2 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="849eb-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="849eb-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="849eb-166">.NET Core 2.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="849eb-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="849eb-167">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="849eb-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="849eb-168">OS</span><span class="sxs-lookup"><span data-stu-id="849eb-168">OS</span></span>                            | <span data-ttu-id="849eb-169">バージョン</span><span class="sxs-lookup"><span data-stu-id="849eb-169">Version</span></span>                        | <span data-ttu-id="849eb-170">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="849eb-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="849eb-171">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="849eb-171">Windows Client</span></span>                | <span data-ttu-id="849eb-172">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="849eb-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="849eb-173">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-173">x64, x86</span></span>        |
| <span data-ttu-id="849eb-174">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="849eb-174">Windows 10 Client</span></span>             | <span data-ttu-id="849eb-175">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="849eb-175">Version 1607+</span></span>                  | <span data-ttu-id="849eb-176">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-176">x64, x86</span></span>        |
| <span data-ttu-id="849eb-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="849eb-177">Windows Server</span></span>                | <span data-ttu-id="849eb-178">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="849eb-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="849eb-179">x64、x86</span><span class="sxs-lookup"><span data-stu-id="849eb-179">x64, x86</span></span>        |
| <span data-ttu-id="849eb-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="849eb-180">Nano Server</span></span>                   | <span data-ttu-id="849eb-181">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="849eb-181">Version 1803+</span></span>                  | <span data-ttu-id="849eb-182">x64、</span><span class="sxs-lookup"><span data-stu-id="849eb-182">x64,</span></span>            |

<span data-ttu-id="849eb-183">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」(.NET Core 2.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="849eb-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="849eb-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="849eb-185">次の Windows のバージョンに .NET SDK またはランタイムをインストールする場合は、追加の依存関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="849eb-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="849eb-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="849eb-186">Windows 7 SP1</span></span>
- <span data-ttu-id="849eb-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="849eb-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="849eb-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="849eb-188">Windows 8.1</span></span>
- <span data-ttu-id="849eb-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="849eb-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="849eb-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="849eb-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="849eb-191">以下をインストールします。</span><span class="sxs-lookup"><span data-stu-id="849eb-191">Install the following:</span></span>

- <span data-ttu-id="849eb-192">[Microsoft Visual C++ 2015 再頒布可能パッケージ Update 3](https://www.microsoft.com/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="849eb-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="849eb-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="849eb-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="849eb-194">上記の要件は、次のいずれかのエラーが発生した場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="849eb-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="849eb-195">お使いのコンピューターに *api-ms-win-crt-runtime-l1-1-0.dll* が見つからず、プログラムを開始できない。</span><span class="sxs-lookup"><span data-stu-id="849eb-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="849eb-196">この問題を解決するには、プログラムを再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="849eb-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="849eb-197">\- または</span><span class="sxs-lookup"><span data-stu-id="849eb-197">\- or -</span></span>
>
> <span data-ttu-id="849eb-198">ライブラリ *hostfxr.dll* はあるが、それを *C:\\\<path_to_app>\\hostfxr.dll* から読み込むと失敗する。</span><span class="sxs-lookup"><span data-stu-id="849eb-198">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="849eb-199">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="849eb-199">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="849eb-200">.NET Core 3.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="849eb-200">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="849eb-201">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-201">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="849eb-202">.NET Core 3.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="849eb-202">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="849eb-203">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="849eb-203">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="849eb-204">OS</span><span class="sxs-lookup"><span data-stu-id="849eb-204">OS</span></span>                             | <span data-ttu-id="849eb-205">バージョン</span><span class="sxs-lookup"><span data-stu-id="849eb-205">Version</span></span>               | <span data-ttu-id="849eb-206">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="849eb-206">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="849eb-207">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-207">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="849eb-208">6、7、8</span><span class="sxs-lookup"><span data-stu-id="849eb-208">6, 7, 8</span></span>               | <span data-ttu-id="849eb-209">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-209">x64</span></span> |
| <span data-ttu-id="849eb-210">CentOS</span><span class="sxs-lookup"><span data-stu-id="849eb-210">CentOS</span></span>                         | <span data-ttu-id="849eb-211">7+</span><span class="sxs-lookup"><span data-stu-id="849eb-211">7+</span></span>                    | <span data-ttu-id="849eb-212">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-212">x64</span></span> |
| <span data-ttu-id="849eb-213">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-213">Oracle Linux</span></span>                   | <span data-ttu-id="849eb-214">7+</span><span class="sxs-lookup"><span data-stu-id="849eb-214">7+</span></span>                    | <span data-ttu-id="849eb-215">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-215">x64</span></span> |
| <span data-ttu-id="849eb-216">Fedora</span><span class="sxs-lookup"><span data-stu-id="849eb-216">Fedora</span></span>                         | <span data-ttu-id="849eb-217">30+</span><span class="sxs-lookup"><span data-stu-id="849eb-217">30+</span></span>                   | <span data-ttu-id="849eb-218">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-218">x64</span></span> |
| <span data-ttu-id="849eb-219">Debian</span><span class="sxs-lookup"><span data-stu-id="849eb-219">Debian</span></span>                         | <span data-ttu-id="849eb-220">9+</span><span class="sxs-lookup"><span data-stu-id="849eb-220">9+</span></span>                    | <span data-ttu-id="849eb-221">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="849eb-221">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="849eb-222">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="849eb-222">Ubuntu</span></span>                         | <span data-ttu-id="849eb-223">16.04+</span><span class="sxs-lookup"><span data-stu-id="849eb-223">16.04+</span></span>                | <span data-ttu-id="849eb-224">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="849eb-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="849eb-225">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="849eb-225">Linux Mint</span></span>                     | <span data-ttu-id="849eb-226">18+</span><span class="sxs-lookup"><span data-stu-id="849eb-226">18+</span></span>                   | <span data-ttu-id="849eb-227">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-227">x64</span></span> |
| <span data-ttu-id="849eb-228">openSUSE</span><span class="sxs-lookup"><span data-stu-id="849eb-228">openSUSE</span></span>                       | <span data-ttu-id="849eb-229">15+</span><span class="sxs-lookup"><span data-stu-id="849eb-229">15+</span></span>                   | <span data-ttu-id="849eb-230">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-230">x64</span></span> |
| <span data-ttu-id="849eb-231">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="849eb-231">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="849eb-232">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="849eb-232">12 SP2+</span></span>               | <span data-ttu-id="849eb-233">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-233">x64</span></span> |
| <span data-ttu-id="849eb-234">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-234">Alpine Linux</span></span>                   | <span data-ttu-id="849eb-235">3.10+</span><span class="sxs-lookup"><span data-stu-id="849eb-235">3.10+</span></span>                 | <span data-ttu-id="849eb-236">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="849eb-236">x64, ARM64</span></span> |

<span data-ttu-id="849eb-237">.NET Core 3.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)」(.NET Core 3.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-237">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="849eb-238">ARM64 (カーネル 4.14+) 上に .NET Core 3.1 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」(Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-238">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="849eb-239">ARM64 のサポートには、Linux カーネル 4.14 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="849eb-239">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="849eb-240">一部の linux ディストリビューションは、この要件を満たしていますが、そうでないものもあります。</span><span class="sxs-lookup"><span data-stu-id="849eb-240">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="849eb-241">たとえば、Ubuntu 18.04 ではサポートされていますが、Ubuntu 16.04 ではされていません。</span><span class="sxs-lookup"><span data-stu-id="849eb-241">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="849eb-242">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="849eb-242">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="849eb-243">" *.NET Core 3.0 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="849eb-243">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="849eb-244">.NET Core 3.0 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="849eb-244">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="849eb-245">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-245">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="849eb-246">.NET Core 3.0 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="849eb-246">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="849eb-247">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="849eb-247">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="849eb-248">OS</span><span class="sxs-lookup"><span data-stu-id="849eb-248">OS</span></span>                             | <span data-ttu-id="849eb-249">バージョン</span><span class="sxs-lookup"><span data-stu-id="849eb-249">Version</span></span>               | <span data-ttu-id="849eb-250">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="849eb-250">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="849eb-251">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-251">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="849eb-252">6、7、8</span><span class="sxs-lookup"><span data-stu-id="849eb-252">6, 7, 8</span></span>               | <span data-ttu-id="849eb-253">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-253">x64</span></span> |
| <span data-ttu-id="849eb-254">CentOS</span><span class="sxs-lookup"><span data-stu-id="849eb-254">CentOS</span></span>                         | <span data-ttu-id="849eb-255">7+</span><span class="sxs-lookup"><span data-stu-id="849eb-255">7+</span></span>                    | <span data-ttu-id="849eb-256">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-256">x64</span></span> |
| <span data-ttu-id="849eb-257">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-257">Oracle Linux</span></span>                   | <span data-ttu-id="849eb-258">7+</span><span class="sxs-lookup"><span data-stu-id="849eb-258">7+</span></span>                    | <span data-ttu-id="849eb-259">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-259">x64</span></span> |
| <span data-ttu-id="849eb-260">Fedora</span><span class="sxs-lookup"><span data-stu-id="849eb-260">Fedora</span></span>                         | <span data-ttu-id="849eb-261">29+</span><span class="sxs-lookup"><span data-stu-id="849eb-261">29+</span></span>                   | <span data-ttu-id="849eb-262">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-262">x64</span></span> |
| <span data-ttu-id="849eb-263">Debian</span><span class="sxs-lookup"><span data-stu-id="849eb-263">Debian</span></span>                         | <span data-ttu-id="849eb-264">9+</span><span class="sxs-lookup"><span data-stu-id="849eb-264">9+</span></span>                    | <span data-ttu-id="849eb-265">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="849eb-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="849eb-266">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="849eb-266">Ubuntu</span></span>                         | <span data-ttu-id="849eb-267">16.04+</span><span class="sxs-lookup"><span data-stu-id="849eb-267">16.04+</span></span>                | <span data-ttu-id="849eb-268">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="849eb-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="849eb-269">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="849eb-269">Linux Mint</span></span>                     | <span data-ttu-id="849eb-270">18+</span><span class="sxs-lookup"><span data-stu-id="849eb-270">18+</span></span>                   | <span data-ttu-id="849eb-271">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-271">x64</span></span> |
| <span data-ttu-id="849eb-272">openSUSE</span><span class="sxs-lookup"><span data-stu-id="849eb-272">openSUSE</span></span>                       | <span data-ttu-id="849eb-273">15+</span><span class="sxs-lookup"><span data-stu-id="849eb-273">15+</span></span>                   | <span data-ttu-id="849eb-274">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-274">x64</span></span> |
| <span data-ttu-id="849eb-275">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="849eb-275">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="849eb-276">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="849eb-276">12 SP2+</span></span>               | <span data-ttu-id="849eb-277">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-277">x64</span></span> |
| <span data-ttu-id="849eb-278">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-278">Alpine Linux</span></span>                   | <span data-ttu-id="849eb-279">3.8+</span><span class="sxs-lookup"><span data-stu-id="849eb-279">3.8+</span></span>                  | <span data-ttu-id="849eb-280">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="849eb-280">x64, ARM64</span></span> |

<span data-ttu-id="849eb-281">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)」(.NET Core 3.0 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-281">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="849eb-282">ARM64 で .NET Core 3.0 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」 (Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-282">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="849eb-283">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="849eb-283">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="849eb-284">" *.NET Core 2.2 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="849eb-284">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="849eb-285">.NET Core 2.2 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="849eb-285">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="849eb-286">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-286">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="849eb-287">.NET Core 2.2 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="849eb-287">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="849eb-288">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="849eb-288">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="849eb-289">OS</span><span class="sxs-lookup"><span data-stu-id="849eb-289">OS</span></span>                             |  <span data-ttu-id="849eb-290">バージョン</span><span class="sxs-lookup"><span data-stu-id="849eb-290">Version</span></span>                |  <span data-ttu-id="849eb-291">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="849eb-291">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="849eb-292">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-292">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="849eb-293">6、7</span><span class="sxs-lookup"><span data-stu-id="849eb-293">6, 7</span></span>                   | <span data-ttu-id="849eb-294">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-294">x64</span></span> |
| <span data-ttu-id="849eb-295">CentOS</span><span class="sxs-lookup"><span data-stu-id="849eb-295">CentOS</span></span>                         |  <span data-ttu-id="849eb-296">7</span><span class="sxs-lookup"><span data-stu-id="849eb-296">7</span></span>                      | <span data-ttu-id="849eb-297">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-297">x64</span></span> |
| <span data-ttu-id="849eb-298">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-298">Oracle Linux</span></span>                   |  <span data-ttu-id="849eb-299">7</span><span class="sxs-lookup"><span data-stu-id="849eb-299">7</span></span>                      | <span data-ttu-id="849eb-300">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-300">x64</span></span> |
| <span data-ttu-id="849eb-301">Fedora</span><span class="sxs-lookup"><span data-stu-id="849eb-301">Fedora</span></span>                         |  <span data-ttu-id="849eb-302">29、30</span><span class="sxs-lookup"><span data-stu-id="849eb-302">29, 30</span></span>                 | <span data-ttu-id="849eb-303">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-303">x64</span></span> |
| <span data-ttu-id="849eb-304">Debian</span><span class="sxs-lookup"><span data-stu-id="849eb-304">Debian</span></span>                         |  <span data-ttu-id="849eb-305">9</span><span class="sxs-lookup"><span data-stu-id="849eb-305">9</span></span>                      | <span data-ttu-id="849eb-306">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="849eb-306">x64, ARM32</span></span> |
| <span data-ttu-id="849eb-307">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="849eb-307">Ubuntu</span></span>                         |  <span data-ttu-id="849eb-308">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="849eb-308">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="849eb-309">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="849eb-309">x64, ARM32</span></span> |
| <span data-ttu-id="849eb-310">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="849eb-310">Linux Mint</span></span>                     |  <span data-ttu-id="849eb-311">17、18</span><span class="sxs-lookup"><span data-stu-id="849eb-311">17, 18</span></span>                 | <span data-ttu-id="849eb-312">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-312">x64</span></span> |
| <span data-ttu-id="849eb-313">openSUSE</span><span class="sxs-lookup"><span data-stu-id="849eb-313">openSUSE</span></span>                       |  <span data-ttu-id="849eb-314">15+</span><span class="sxs-lookup"><span data-stu-id="849eb-314">15+</span></span>                    | <span data-ttu-id="849eb-315">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-315">x64</span></span> |
| <span data-ttu-id="849eb-316">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="849eb-316">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="849eb-317">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="849eb-317">12 SP2+</span></span>                | <span data-ttu-id="849eb-318">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-318">x64</span></span> |
| <span data-ttu-id="849eb-319">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-319">Alpine Linux</span></span>                   |  <span data-ttu-id="849eb-320">3.8+</span><span class="sxs-lookup"><span data-stu-id="849eb-320">3.8+</span></span>                   | <span data-ttu-id="849eb-321">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-321">x64</span></span> |

<span data-ttu-id="849eb-322">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)」(.NET Core 2.2 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-322">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="849eb-323">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="849eb-323">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="849eb-324">.NET Core 2.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="849eb-324">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="849eb-325">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-325">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="849eb-326">.NET Core 2.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="849eb-326">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="849eb-327">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="849eb-327">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="849eb-328">OS</span><span class="sxs-lookup"><span data-stu-id="849eb-328">OS</span></span>                             |  <span data-ttu-id="849eb-329">バージョン</span><span class="sxs-lookup"><span data-stu-id="849eb-329">Version</span></span>                |  <span data-ttu-id="849eb-330">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="849eb-330">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="849eb-331">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-331">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="849eb-332">6、7、8</span><span class="sxs-lookup"><span data-stu-id="849eb-332">6, 7, 8</span></span>                | <span data-ttu-id="849eb-333">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-333">x64</span></span> |
| <span data-ttu-id="849eb-334">CentOS</span><span class="sxs-lookup"><span data-stu-id="849eb-334">CentOS</span></span>                         |  <span data-ttu-id="849eb-335">7+</span><span class="sxs-lookup"><span data-stu-id="849eb-335">7+</span></span>                     | <span data-ttu-id="849eb-336">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-336">x64</span></span> |
| <span data-ttu-id="849eb-337">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-337">Oracle Linux</span></span>                   |  <span data-ttu-id="849eb-338">7+</span><span class="sxs-lookup"><span data-stu-id="849eb-338">7+</span></span>                     | <span data-ttu-id="849eb-339">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-339">x64</span></span> |
| <span data-ttu-id="849eb-340">Fedora</span><span class="sxs-lookup"><span data-stu-id="849eb-340">Fedora</span></span>                         |  <span data-ttu-id="849eb-341">30+</span><span class="sxs-lookup"><span data-stu-id="849eb-341">30+</span></span>                    | <span data-ttu-id="849eb-342">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-342">x64</span></span> |
| <span data-ttu-id="849eb-343">Debian</span><span class="sxs-lookup"><span data-stu-id="849eb-343">Debian</span></span>                         |  <span data-ttu-id="849eb-344">9</span><span class="sxs-lookup"><span data-stu-id="849eb-344">9</span></span>                      | <span data-ttu-id="849eb-345">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="849eb-345">x64, ARM32</span></span> |
| <span data-ttu-id="849eb-346">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="849eb-346">Ubuntu</span></span>                         |  <span data-ttu-id="849eb-347">16.04、18.04、19.04、19.10</span><span class="sxs-lookup"><span data-stu-id="849eb-347">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="849eb-348">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="849eb-348">x64, ARM32</span></span> |
| <span data-ttu-id="849eb-349">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="849eb-349">Linux Mint</span></span>                     |  <span data-ttu-id="849eb-350">17+</span><span class="sxs-lookup"><span data-stu-id="849eb-350">17+</span></span>                    | <span data-ttu-id="849eb-351">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-351">x64</span></span> |
| <span data-ttu-id="849eb-352">openSUSE</span><span class="sxs-lookup"><span data-stu-id="849eb-352">openSUSE</span></span>                       |  <span data-ttu-id="849eb-353">15+</span><span class="sxs-lookup"><span data-stu-id="849eb-353">15+</span></span>                    | <span data-ttu-id="849eb-354">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-354">x64</span></span> |
| <span data-ttu-id="849eb-355">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="849eb-355">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="849eb-356">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="849eb-356">12 SP2+</span></span>                | <span data-ttu-id="849eb-357">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-357">x64</span></span> |
| <span data-ttu-id="849eb-358">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="849eb-358">Alpine Linux</span></span>                   |  <span data-ttu-id="849eb-359">3.8+</span><span class="sxs-lookup"><span data-stu-id="849eb-359">3.8+</span></span>                   | <span data-ttu-id="849eb-360">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-360">x64</span></span> |

<span data-ttu-id="849eb-361">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」(.NET Core 2.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-361">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="849eb-362">Linux ディストリビューションの依存関係</span><span class="sxs-lookup"><span data-stu-id="849eb-362">Linux distribution dependencies</span></span>

<span data-ttu-id="849eb-363">Linux ディストリビューションによっては、追加の依存関係のインストールが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-363">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="849eb-364">選択した Linux ディストリビューションで、バージョンと名前が多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-364">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="849eb-365">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="849eb-365">Ubuntu</span></span>

<span data-ttu-id="849eb-366">Ubuntu ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-366">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="849eb-367">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="849eb-367">liblttng-ust0</span></span>
- <span data-ttu-id="849eb-368">libcurl3 (14.x および 16.x 用)</span><span class="sxs-lookup"><span data-stu-id="849eb-368">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="849eb-369">libcurl4 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="849eb-369">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="849eb-370">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="849eb-370">libssl1.0.0</span></span>
- <span data-ttu-id="849eb-371">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="849eb-371">libkrb5-3</span></span>
- <span data-ttu-id="849eb-372">zlib1g</span><span class="sxs-lookup"><span data-stu-id="849eb-372">zlib1g</span></span>
- <span data-ttu-id="849eb-373">libicu52 (14.x 用)</span><span class="sxs-lookup"><span data-stu-id="849eb-373">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="849eb-374">libicu55 (16.x 用)</span><span class="sxs-lookup"><span data-stu-id="849eb-374">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="849eb-375">libicu57 (17.x 用)</span><span class="sxs-lookup"><span data-stu-id="849eb-375">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="849eb-376">libicu60 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="849eb-376">libicu60 (for 18.x)</span></span>

<span data-ttu-id="849eb-377">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="849eb-377">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="849eb-378">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="849eb-378">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="849eb-379">Ubuntu のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="849eb-379">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="849eb-380">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="849eb-380">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="849eb-381">詳細については、「<https://www.mono-project.com/download/stable/>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-381">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="849eb-382">CentOS と Fedora</span><span class="sxs-lookup"><span data-stu-id="849eb-382">CentOS and Fedora</span></span>

<span data-ttu-id="849eb-383">CentOS ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-383">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="849eb-384">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="849eb-384">lttng-ust</span></span>
- <span data-ttu-id="849eb-385">libcurl</span><span class="sxs-lookup"><span data-stu-id="849eb-385">libcurl</span></span>
- <span data-ttu-id="849eb-386">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="849eb-386">openssl-libs</span></span>
- <span data-ttu-id="849eb-387">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="849eb-387">krb5-libs</span></span>
- <span data-ttu-id="849eb-388">libicu</span><span class="sxs-lookup"><span data-stu-id="849eb-388">libicu</span></span>
- <span data-ttu-id="849eb-389">zlib</span><span class="sxs-lookup"><span data-stu-id="849eb-389">zlib</span></span>

<span data-ttu-id="849eb-390">Fedora ユーザー:ご使用の OpenSSL のバージョンが 1.1 以降の場合は、**compat-openssl10** をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-390">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="849eb-391">.NET Core 2.0 では、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="849eb-391">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="849eb-392">libunwind</span><span class="sxs-lookup"><span data-stu-id="849eb-392">libunwind</span></span>
- <span data-ttu-id="849eb-393">libuuid</span><span class="sxs-lookup"><span data-stu-id="849eb-393">libuuid</span></span>

<span data-ttu-id="849eb-394">依存関係の詳細については、「[Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」(自己完結型 Linux アプリケーション) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="849eb-394">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="849eb-395">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="849eb-395">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="849eb-396">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="849eb-396">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="849eb-397">CentOS と Fedora のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="849eb-397">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="849eb-398">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="849eb-398">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="849eb-399">詳細については、「<https://www.mono-project.com/download/stable/>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-399">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="849eb-400">.NET Core は、次の macOS のリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="849eb-400">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="849eb-401">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="849eb-401">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="849eb-402">.NET Core のバージョン</span><span class="sxs-lookup"><span data-stu-id="849eb-402">.NET Core Version</span></span> | <span data-ttu-id="849eb-403">macOS</span><span class="sxs-lookup"><span data-stu-id="849eb-403">macOS</span></span>                 | <span data-ttu-id="849eb-404">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="849eb-404">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="849eb-405">3.1</span><span class="sxs-lookup"><span data-stu-id="849eb-405">3.1</span></span>               | <span data-ttu-id="849eb-406">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="849eb-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="849eb-407">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-407">x64</span></span> | [<span data-ttu-id="849eb-408">詳細情報</span><span class="sxs-lookup"><span data-stu-id="849eb-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="849eb-409">3.0</span><span class="sxs-lookup"><span data-stu-id="849eb-409">3.0</span></span>               | <span data-ttu-id="849eb-410">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="849eb-410">High Sierra (10.13+)</span></span>  | <span data-ttu-id="849eb-411">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-411">x64</span></span> | [<span data-ttu-id="849eb-412">詳細情報</span><span class="sxs-lookup"><span data-stu-id="849eb-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="849eb-413">2.2</span><span class="sxs-lookup"><span data-stu-id="849eb-413">2.2</span></span>               | <span data-ttu-id="849eb-414">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="849eb-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="849eb-415">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-415">x64</span></span> | [<span data-ttu-id="849eb-416">詳細情報</span><span class="sxs-lookup"><span data-stu-id="849eb-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="849eb-417">2.1</span><span class="sxs-lookup"><span data-stu-id="849eb-417">2.1</span></span>               | <span data-ttu-id="849eb-418">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="849eb-418">Sierra (10.12+)</span></span>       | <span data-ttu-id="849eb-419">X64</span><span class="sxs-lookup"><span data-stu-id="849eb-419">x64</span></span> | [<span data-ttu-id="849eb-420">詳細情報</span><span class="sxs-lookup"><span data-stu-id="849eb-420">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="849eb-421">macOS Catalina (バージョン 10.15) 以降では、2019 年 6 月 1 日より後に作成され、Developer ID と共に配布されたすべてのソフトウェアは公証される必要があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-421">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="849eb-422">この要件は、.NET Core ランタイム、.NET Core SDK、および .NET Core を使用して作成されたソフトウェアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="849eb-422">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="849eb-423">.NET Core (ランタイムと SDK の両方) バージョン 3.1、3.0、2.1 のインストーラーは、2020 年 2 月 18 日から公証されています。</span><span class="sxs-lookup"><span data-stu-id="849eb-423">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="849eb-424">それより前にリリースされたバージョンは、公証されていません。</span><span class="sxs-lookup"><span data-stu-id="849eb-424">Prior released versions aren't notarized.</span></span> <span data-ttu-id="849eb-425">公証されていないアプリを実行すると、次のイメージのようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="849eb-425">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina の公証に関するアラート](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="849eb-427">公証の強制が .NET Core (および .NET Core アプリ) に与える影響の詳細については、[macOS Catalina の公証への対応](macos-notarization-issues.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="849eb-427">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="849eb-428">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="849eb-428">libgdiplus</span></span>

<span data-ttu-id="849eb-429">*System.Drawing.Common* アセンブリを使用する .NET Core アプリケーションでは、libgdiplus をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="849eb-429">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="849eb-430">libgdiplus を取得する簡単な方法は、macOS の [Homebrew ("brew")](https://brew.sh/) パッケージ マネージャーを使用することです。</span><span class="sxs-lookup"><span data-stu-id="849eb-430">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="849eb-431">*brew* をインストールしたら、端末 (コマンド) プロンプトで次のコマンドを実行して libgdiplus をインストールします。</span><span class="sxs-lookup"><span data-stu-id="849eb-431">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="849eb-432">次の手順</span><span class="sxs-lookup"><span data-stu-id="849eb-432">Next steps</span></span>

- <span data-ttu-id="849eb-433">アプリを開発して実行するには、[.NET Core SDK](sdk.md) (ランタイムを含む) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="849eb-433">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="849eb-434">他のユーザーが作成したアプリを実行するには、[.NET Core ランタイム](runtime.md)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="849eb-434">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
