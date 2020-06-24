---
title: .NET Core SDK とランタイムの依存関係 - .NET Core
description: Windows、Linux、および macOS に .NET Core SDK とランタイムをインストールするためのオペレーティング システムと CPU アーキテクチャの前提条件について説明します。
author: leecow
ms.author: leecow
ms.date: 06/01/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 81f6ab436428d71f71d9fd0f560bd2b0512a519b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590761"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="82bc9-103">.NET Core の依存関係と要件</span><span class="sxs-lookup"><span data-stu-id="82bc9-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="82bc9-104">この記事では、.NET Core でサポートされているオペレーティング システムと CPU アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="82bc9-105">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="82bc9-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="82bc9-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="82bc9-107">.NET Core 3.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="82bc9-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="82bc9-108">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="82bc9-109">OS</span><span class="sxs-lookup"><span data-stu-id="82bc9-109">OS</span></span>                            | <span data-ttu-id="82bc9-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="82bc9-110">Version</span></span>                        | <span data-ttu-id="82bc9-111">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82bc9-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="82bc9-112">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="82bc9-112">Windows Client</span></span>                | <span data-ttu-id="82bc9-113">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="82bc9-114">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-114">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-115">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="82bc9-115">Windows 10 Client</span></span>             | <span data-ttu-id="82bc9-116">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="82bc9-116">Version 1607+</span></span>                  | <span data-ttu-id="82bc9-117">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-117">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="82bc9-118">Windows Server</span></span>                | <span data-ttu-id="82bc9-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="82bc9-119">2012 R2+</span></span>                       | <span data-ttu-id="82bc9-120">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-120">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="82bc9-121">Nano Server</span></span>                   | <span data-ttu-id="82bc9-122">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="82bc9-122">Version 1803+</span></span>                  | <span data-ttu-id="82bc9-123">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="82bc9-123">x64, ARM32</span></span>      |

<span data-ttu-id="82bc9-124">.NET Core 3.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)」(.NET Core 3.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="82bc9-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="82bc9-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="82bc9-126">" *.NET Core 3.0 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="82bc9-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="82bc9-127">.NET Core 3.0 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="82bc9-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="82bc9-128">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="82bc9-129">OS</span><span class="sxs-lookup"><span data-stu-id="82bc9-129">OS</span></span>                            | <span data-ttu-id="82bc9-130">バージョン</span><span class="sxs-lookup"><span data-stu-id="82bc9-130">Version</span></span>                        | <span data-ttu-id="82bc9-131">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82bc9-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="82bc9-132">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="82bc9-132">Windows Client</span></span>                | <span data-ttu-id="82bc9-133">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="82bc9-134">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-134">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-135">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="82bc9-135">Windows 10 Client</span></span>             | <span data-ttu-id="82bc9-136">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="82bc9-136">Version 1607+</span></span>                  | <span data-ttu-id="82bc9-137">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-137">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="82bc9-138">Windows Server</span></span>                | <span data-ttu-id="82bc9-139">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="82bc9-139">2012 R2+</span></span>                       | <span data-ttu-id="82bc9-140">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-140">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="82bc9-141">Nano Server</span></span>                   | <span data-ttu-id="82bc9-142">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="82bc9-142">Version 1803+</span></span>                  | <span data-ttu-id="82bc9-143">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="82bc9-143">x64, ARM32</span></span>      |

<span data-ttu-id="82bc9-144">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)」(.NET Core 3.0 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="82bc9-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="82bc9-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="82bc9-146">" *.NET Core 2.2 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="82bc9-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="82bc9-147">.NET Core 2.2 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="82bc9-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="82bc9-148">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="82bc9-149">OS</span><span class="sxs-lookup"><span data-stu-id="82bc9-149">OS</span></span>                            | <span data-ttu-id="82bc9-150">バージョン</span><span class="sxs-lookup"><span data-stu-id="82bc9-150">Version</span></span>                        | <span data-ttu-id="82bc9-151">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82bc9-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="82bc9-152">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="82bc9-152">Windows Client</span></span>                | <span data-ttu-id="82bc9-153">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="82bc9-154">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-154">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-155">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="82bc9-155">Windows 10 Client</span></span>             | <span data-ttu-id="82bc9-156">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="82bc9-156">Version 1607+</span></span>                  | <span data-ttu-id="82bc9-157">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-157">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="82bc9-158">Windows Server</span></span>                | <span data-ttu-id="82bc9-159">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="82bc9-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="82bc9-160">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-160">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="82bc9-161">Nano Server</span></span>                   | <span data-ttu-id="82bc9-162">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="82bc9-162">Version 1803+</span></span>                   | <span data-ttu-id="82bc9-163">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="82bc9-163">x64, ARM32</span></span>      |

<span data-ttu-id="82bc9-164">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)」(.NET Core 2.2 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="82bc9-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="82bc9-166">.NET Core 2.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="82bc9-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="82bc9-167">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="82bc9-168">OS</span><span class="sxs-lookup"><span data-stu-id="82bc9-168">OS</span></span>                            | <span data-ttu-id="82bc9-169">バージョン</span><span class="sxs-lookup"><span data-stu-id="82bc9-169">Version</span></span>                        | <span data-ttu-id="82bc9-170">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82bc9-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="82bc9-171">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="82bc9-171">Windows Client</span></span>                | <span data-ttu-id="82bc9-172">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="82bc9-173">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-173">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-174">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="82bc9-174">Windows 10 Client</span></span>             | <span data-ttu-id="82bc9-175">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="82bc9-175">Version 1607+</span></span>                  | <span data-ttu-id="82bc9-176">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-176">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="82bc9-177">Windows Server</span></span>                | <span data-ttu-id="82bc9-178">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="82bc9-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="82bc9-179">x64、x86</span><span class="sxs-lookup"><span data-stu-id="82bc9-179">x64, x86</span></span>        |
| <span data-ttu-id="82bc9-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="82bc9-180">Nano Server</span></span>                   | <span data-ttu-id="82bc9-181">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="82bc9-181">Version 1803+</span></span>                  | <span data-ttu-id="82bc9-182">x64、</span><span class="sxs-lookup"><span data-stu-id="82bc9-182">x64,</span></span>            |

<span data-ttu-id="82bc9-183">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」(.NET Core 2.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="82bc9-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="82bc9-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="82bc9-185">次の Windows のバージョンに .NET SDK またはランタイムをインストールする場合は、追加の依存関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="82bc9-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="82bc9-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="82bc9-186">Windows 7 SP1</span></span>
- <span data-ttu-id="82bc9-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="82bc9-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="82bc9-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-188">Windows 8.1</span></span>
- <span data-ttu-id="82bc9-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="82bc9-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="82bc9-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="82bc9-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="82bc9-191">以下をインストールします。</span><span class="sxs-lookup"><span data-stu-id="82bc9-191">Install the following:</span></span>

- <span data-ttu-id="82bc9-192">[Microsoft Visual C++ 2015 再頒布可能パッケージ Update 3](https://www.microsoft.com/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="82bc9-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="82bc9-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="82bc9-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="82bc9-194">上記の要件は、次のいずれかのエラーが発生した場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="82bc9-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="82bc9-195">お使いのコンピューターに *api-ms-win-crt-runtime-l1-1-0.dll* が見つからず、プログラムを開始できない。</span><span class="sxs-lookup"><span data-stu-id="82bc9-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="82bc9-196">この問題を解決するには、プログラムを再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="82bc9-197">\- または</span><span class="sxs-lookup"><span data-stu-id="82bc9-197">\- or -</span></span>
>
> <span data-ttu-id="82bc9-198">お使いのコンピューターに *api-ms-win-cor-timezone-l1-1-0.dll* が見つからず、プログラムを開始できない。</span><span class="sxs-lookup"><span data-stu-id="82bc9-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="82bc9-199">この問題を解決するには、プログラムを再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="82bc9-200">\- または</span><span class="sxs-lookup"><span data-stu-id="82bc9-200">\- or -</span></span>
>
> <span data-ttu-id="82bc9-201">ライブラリ *hostfxr.dll* は見つかったが、その *C:\\\<path_to_app>\\hostfxr.dll* からの読み込みに失敗した。</span><span class="sxs-lookup"><span data-stu-id="82bc9-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="82bc9-202">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="82bc9-203">.NET Core 3.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="82bc9-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="82bc9-204">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="82bc9-205">.NET Core 3.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="82bc9-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="82bc9-206">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="82bc9-207">OS</span><span class="sxs-lookup"><span data-stu-id="82bc9-207">OS</span></span>                             | <span data-ttu-id="82bc9-208">バージョン</span><span class="sxs-lookup"><span data-stu-id="82bc9-208">Version</span></span>               | <span data-ttu-id="82bc9-209">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82bc9-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="82bc9-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="82bc9-211">6、7、8</span><span class="sxs-lookup"><span data-stu-id="82bc9-211">6, 7, 8</span></span>               | <span data-ttu-id="82bc9-212">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-212">x64</span></span> |
| <span data-ttu-id="82bc9-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="82bc9-213">CentOS</span></span>                         | <span data-ttu-id="82bc9-214">7+</span><span class="sxs-lookup"><span data-stu-id="82bc9-214">7+</span></span>                    | <span data-ttu-id="82bc9-215">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-215">x64</span></span> |
| <span data-ttu-id="82bc9-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-216">Oracle Linux</span></span>                   | <span data-ttu-id="82bc9-217">7+</span><span class="sxs-lookup"><span data-stu-id="82bc9-217">7+</span></span>                    | <span data-ttu-id="82bc9-218">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-218">x64</span></span> |
| <span data-ttu-id="82bc9-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="82bc9-219">Fedora</span></span>                         | <span data-ttu-id="82bc9-220">30+</span><span class="sxs-lookup"><span data-stu-id="82bc9-220">30+</span></span>                   | <span data-ttu-id="82bc9-221">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-221">x64</span></span> |
| <span data-ttu-id="82bc9-222">Debian</span><span class="sxs-lookup"><span data-stu-id="82bc9-222">Debian</span></span>                         | <span data-ttu-id="82bc9-223">9+</span><span class="sxs-lookup"><span data-stu-id="82bc9-223">9+</span></span>                    | <span data-ttu-id="82bc9-224">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="82bc9-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="82bc9-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="82bc9-225">Ubuntu</span></span>                         | <span data-ttu-id="82bc9-226">16.04+</span><span class="sxs-lookup"><span data-stu-id="82bc9-226">16.04+</span></span>                | <span data-ttu-id="82bc9-227">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="82bc9-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="82bc9-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="82bc9-228">Linux Mint</span></span>                     | <span data-ttu-id="82bc9-229">18+</span><span class="sxs-lookup"><span data-stu-id="82bc9-229">18+</span></span>                   | <span data-ttu-id="82bc9-230">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-230">x64</span></span> |
| <span data-ttu-id="82bc9-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="82bc9-231">openSUSE</span></span>                       | <span data-ttu-id="82bc9-232">15+</span><span class="sxs-lookup"><span data-stu-id="82bc9-232">15+</span></span>                   | <span data-ttu-id="82bc9-233">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-233">x64</span></span> |
| <span data-ttu-id="82bc9-234">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="82bc9-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="82bc9-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="82bc9-235">12 SP2+</span></span>               | <span data-ttu-id="82bc9-236">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-236">x64</span></span> |
| <span data-ttu-id="82bc9-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-237">Alpine Linux</span></span>                   | <span data-ttu-id="82bc9-238">3.10+</span><span class="sxs-lookup"><span data-stu-id="82bc9-238">3.10+</span></span>                 | <span data-ttu-id="82bc9-239">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="82bc9-239">x64, ARM64</span></span> |

<span data-ttu-id="82bc9-240">.NET Core 3.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)」(.NET Core 3.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="82bc9-241">ARM64 (カーネル 4.14+) 上に .NET Core 3.1 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」(Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82bc9-242">ARM64 のサポートには、Linux カーネル 4.14 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="82bc9-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="82bc9-243">一部の linux ディストリビューションは、この要件を満たしていますが、そうでないものもあります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="82bc9-244">たとえば、Ubuntu 18.04 ではサポートされていますが、Ubuntu 16.04 ではされていません。</span><span class="sxs-lookup"><span data-stu-id="82bc9-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="82bc9-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="82bc9-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="82bc9-246">" *.NET Core 3.0 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="82bc9-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="82bc9-247">.NET Core 3.0 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="82bc9-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="82bc9-248">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="82bc9-249">.NET Core 3.0 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="82bc9-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="82bc9-250">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="82bc9-251">OS</span><span class="sxs-lookup"><span data-stu-id="82bc9-251">OS</span></span>                             | <span data-ttu-id="82bc9-252">バージョン</span><span class="sxs-lookup"><span data-stu-id="82bc9-252">Version</span></span>               | <span data-ttu-id="82bc9-253">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82bc9-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="82bc9-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="82bc9-255">6、7、8</span><span class="sxs-lookup"><span data-stu-id="82bc9-255">6, 7, 8</span></span>               | <span data-ttu-id="82bc9-256">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-256">x64</span></span> |
| <span data-ttu-id="82bc9-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="82bc9-257">CentOS</span></span>                         | <span data-ttu-id="82bc9-258">7+</span><span class="sxs-lookup"><span data-stu-id="82bc9-258">7+</span></span>                    | <span data-ttu-id="82bc9-259">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-259">x64</span></span> |
| <span data-ttu-id="82bc9-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-260">Oracle Linux</span></span>                   | <span data-ttu-id="82bc9-261">7+</span><span class="sxs-lookup"><span data-stu-id="82bc9-261">7+</span></span>                    | <span data-ttu-id="82bc9-262">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-262">x64</span></span> |
| <span data-ttu-id="82bc9-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="82bc9-263">Fedora</span></span>                         | <span data-ttu-id="82bc9-264">29+</span><span class="sxs-lookup"><span data-stu-id="82bc9-264">29+</span></span>                   | <span data-ttu-id="82bc9-265">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-265">x64</span></span> |
| <span data-ttu-id="82bc9-266">Debian</span><span class="sxs-lookup"><span data-stu-id="82bc9-266">Debian</span></span>                         | <span data-ttu-id="82bc9-267">9+</span><span class="sxs-lookup"><span data-stu-id="82bc9-267">9+</span></span>                    | <span data-ttu-id="82bc9-268">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="82bc9-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="82bc9-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="82bc9-269">Ubuntu</span></span>                         | <span data-ttu-id="82bc9-270">16.04+</span><span class="sxs-lookup"><span data-stu-id="82bc9-270">16.04+</span></span>                | <span data-ttu-id="82bc9-271">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="82bc9-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="82bc9-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="82bc9-272">Linux Mint</span></span>                     | <span data-ttu-id="82bc9-273">18+</span><span class="sxs-lookup"><span data-stu-id="82bc9-273">18+</span></span>                   | <span data-ttu-id="82bc9-274">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-274">x64</span></span> |
| <span data-ttu-id="82bc9-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="82bc9-275">openSUSE</span></span>                       | <span data-ttu-id="82bc9-276">15+</span><span class="sxs-lookup"><span data-stu-id="82bc9-276">15+</span></span>                   | <span data-ttu-id="82bc9-277">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-277">x64</span></span> |
| <span data-ttu-id="82bc9-278">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="82bc9-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="82bc9-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="82bc9-279">12 SP2+</span></span>               | <span data-ttu-id="82bc9-280">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-280">x64</span></span> |
| <span data-ttu-id="82bc9-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-281">Alpine Linux</span></span>                   | <span data-ttu-id="82bc9-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="82bc9-282">3.8+</span></span>                  | <span data-ttu-id="82bc9-283">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="82bc9-283">x64, ARM64</span></span> |

<span data-ttu-id="82bc9-284">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)」(.NET Core 3.0 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="82bc9-285">ARM64 で .NET Core 3.0 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」 (Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="82bc9-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="82bc9-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="82bc9-287">" *.NET Core 2.2 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="82bc9-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="82bc9-288">.NET Core 2.2 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="82bc9-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="82bc9-289">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="82bc9-290">.NET Core 2.2 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="82bc9-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="82bc9-291">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="82bc9-292">OS</span><span class="sxs-lookup"><span data-stu-id="82bc9-292">OS</span></span>                             |  <span data-ttu-id="82bc9-293">バージョン</span><span class="sxs-lookup"><span data-stu-id="82bc9-293">Version</span></span>                |  <span data-ttu-id="82bc9-294">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82bc9-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="82bc9-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="82bc9-296">6、7</span><span class="sxs-lookup"><span data-stu-id="82bc9-296">6, 7</span></span>                   | <span data-ttu-id="82bc9-297">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-297">x64</span></span> |
| <span data-ttu-id="82bc9-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="82bc9-298">CentOS</span></span>                         |  <span data-ttu-id="82bc9-299">7</span><span class="sxs-lookup"><span data-stu-id="82bc9-299">7</span></span>                      | <span data-ttu-id="82bc9-300">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-300">x64</span></span> |
| <span data-ttu-id="82bc9-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-301">Oracle Linux</span></span>                   |  <span data-ttu-id="82bc9-302">7</span><span class="sxs-lookup"><span data-stu-id="82bc9-302">7</span></span>                      | <span data-ttu-id="82bc9-303">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-303">x64</span></span> |
| <span data-ttu-id="82bc9-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="82bc9-304">Fedora</span></span>                         |  <span data-ttu-id="82bc9-305">29、30</span><span class="sxs-lookup"><span data-stu-id="82bc9-305">29, 30</span></span>                 | <span data-ttu-id="82bc9-306">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-306">x64</span></span> |
| <span data-ttu-id="82bc9-307">Debian</span><span class="sxs-lookup"><span data-stu-id="82bc9-307">Debian</span></span>                         |  <span data-ttu-id="82bc9-308">9</span><span class="sxs-lookup"><span data-stu-id="82bc9-308">9</span></span>                      | <span data-ttu-id="82bc9-309">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="82bc9-309">x64, ARM32</span></span> |
| <span data-ttu-id="82bc9-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="82bc9-310">Ubuntu</span></span>                         |  <span data-ttu-id="82bc9-311">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="82bc9-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="82bc9-312">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="82bc9-312">x64, ARM32</span></span> |
| <span data-ttu-id="82bc9-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="82bc9-313">Linux Mint</span></span>                     |  <span data-ttu-id="82bc9-314">17、18</span><span class="sxs-lookup"><span data-stu-id="82bc9-314">17, 18</span></span>                 | <span data-ttu-id="82bc9-315">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-315">x64</span></span> |
| <span data-ttu-id="82bc9-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="82bc9-316">openSUSE</span></span>                       |  <span data-ttu-id="82bc9-317">15+</span><span class="sxs-lookup"><span data-stu-id="82bc9-317">15+</span></span>                    | <span data-ttu-id="82bc9-318">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-318">x64</span></span> |
| <span data-ttu-id="82bc9-319">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="82bc9-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="82bc9-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="82bc9-320">12 SP2+</span></span>                | <span data-ttu-id="82bc9-321">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-321">x64</span></span> |
| <span data-ttu-id="82bc9-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-322">Alpine Linux</span></span>                   |  <span data-ttu-id="82bc9-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="82bc9-323">3.8+</span></span>                   | <span data-ttu-id="82bc9-324">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-324">x64</span></span> |

<span data-ttu-id="82bc9-325">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)」(.NET Core 2.2 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="82bc9-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="82bc9-327">.NET Core 2.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="82bc9-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="82bc9-328">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="82bc9-329">.NET Core 2.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="82bc9-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="82bc9-330">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="82bc9-331">OS</span><span class="sxs-lookup"><span data-stu-id="82bc9-331">OS</span></span>                             |  <span data-ttu-id="82bc9-332">バージョン</span><span class="sxs-lookup"><span data-stu-id="82bc9-332">Version</span></span>                |  <span data-ttu-id="82bc9-333">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82bc9-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="82bc9-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="82bc9-335">6、7、8</span><span class="sxs-lookup"><span data-stu-id="82bc9-335">6, 7, 8</span></span>                | <span data-ttu-id="82bc9-336">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-336">x64</span></span> |
| <span data-ttu-id="82bc9-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="82bc9-337">CentOS</span></span>                         |  <span data-ttu-id="82bc9-338">7+</span><span class="sxs-lookup"><span data-stu-id="82bc9-338">7+</span></span>                     | <span data-ttu-id="82bc9-339">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-339">x64</span></span> |
| <span data-ttu-id="82bc9-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-340">Oracle Linux</span></span>                   |  <span data-ttu-id="82bc9-341">7+</span><span class="sxs-lookup"><span data-stu-id="82bc9-341">7+</span></span>                     | <span data-ttu-id="82bc9-342">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-342">x64</span></span> |
| <span data-ttu-id="82bc9-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="82bc9-343">Fedora</span></span>                         |  <span data-ttu-id="82bc9-344">30+</span><span class="sxs-lookup"><span data-stu-id="82bc9-344">30+</span></span>                    | <span data-ttu-id="82bc9-345">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-345">x64</span></span> |
| <span data-ttu-id="82bc9-346">Debian</span><span class="sxs-lookup"><span data-stu-id="82bc9-346">Debian</span></span>                         |  <span data-ttu-id="82bc9-347">9</span><span class="sxs-lookup"><span data-stu-id="82bc9-347">9</span></span>                      | <span data-ttu-id="82bc9-348">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="82bc9-348">x64, ARM32</span></span> |
| <span data-ttu-id="82bc9-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="82bc9-349">Ubuntu</span></span>                         |  <span data-ttu-id="82bc9-350">16.04、18.04、19.04、19.10</span><span class="sxs-lookup"><span data-stu-id="82bc9-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="82bc9-351">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="82bc9-351">x64, ARM32</span></span> |
| <span data-ttu-id="82bc9-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="82bc9-352">Linux Mint</span></span>                     |  <span data-ttu-id="82bc9-353">17+</span><span class="sxs-lookup"><span data-stu-id="82bc9-353">17+</span></span>                    | <span data-ttu-id="82bc9-354">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-354">x64</span></span> |
| <span data-ttu-id="82bc9-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="82bc9-355">openSUSE</span></span>                       |  <span data-ttu-id="82bc9-356">15+</span><span class="sxs-lookup"><span data-stu-id="82bc9-356">15+</span></span>                    | <span data-ttu-id="82bc9-357">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-357">x64</span></span> |
| <span data-ttu-id="82bc9-358">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="82bc9-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="82bc9-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="82bc9-359">12 SP2+</span></span>                | <span data-ttu-id="82bc9-360">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-360">x64</span></span> |
| <span data-ttu-id="82bc9-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="82bc9-361">Alpine Linux</span></span>                   |  <span data-ttu-id="82bc9-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="82bc9-362">3.8+</span></span>                   | <span data-ttu-id="82bc9-363">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-363">x64</span></span> |

<span data-ttu-id="82bc9-364">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」(.NET Core 2.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="82bc9-365">Linux ディストリビューションの依存関係</span><span class="sxs-lookup"><span data-stu-id="82bc9-365">Linux distribution dependencies</span></span>

<span data-ttu-id="82bc9-366">Linux ディストリビューションによっては、追加の依存関係のインストールが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82bc9-367">選択した Linux ディストリビューションで、バージョンと名前が多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="82bc9-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="82bc9-368">Ubuntu</span></span>

<span data-ttu-id="82bc9-369">Ubuntu ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="82bc9-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="82bc9-370">liblttng-ust0</span></span>
- <span data-ttu-id="82bc9-371">libcurl3 (14.x および 16.x 用)</span><span class="sxs-lookup"><span data-stu-id="82bc9-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="82bc9-372">libcurl4 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="82bc9-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="82bc9-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="82bc9-373">libssl1.0.0</span></span>
- <span data-ttu-id="82bc9-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="82bc9-374">libkrb5-3</span></span>
- <span data-ttu-id="82bc9-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="82bc9-375">zlib1g</span></span>
- <span data-ttu-id="82bc9-376">libicu52 (14.x 用)</span><span class="sxs-lookup"><span data-stu-id="82bc9-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="82bc9-377">libicu55 (16.x 用)</span><span class="sxs-lookup"><span data-stu-id="82bc9-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="82bc9-378">libicu57 (17.x 用)</span><span class="sxs-lookup"><span data-stu-id="82bc9-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="82bc9-379">libicu60 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="82bc9-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="82bc9-380">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="82bc9-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="82bc9-381">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="82bc9-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="82bc9-382">Ubuntu のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82bc9-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="82bc9-383">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="82bc9-384">詳細については、「<https://www.mono-project.com/download/stable/>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="82bc9-385">CentOS と Fedora</span><span class="sxs-lookup"><span data-stu-id="82bc9-385">CentOS and Fedora</span></span>

<span data-ttu-id="82bc9-386">CentOS ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="82bc9-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="82bc9-387">lttng-ust</span></span>
- <span data-ttu-id="82bc9-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="82bc9-388">libcurl</span></span>
- <span data-ttu-id="82bc9-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="82bc9-389">openssl-libs</span></span>
- <span data-ttu-id="82bc9-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="82bc9-390">krb5-libs</span></span>
- <span data-ttu-id="82bc9-391">libicu</span><span class="sxs-lookup"><span data-stu-id="82bc9-391">libicu</span></span>
- <span data-ttu-id="82bc9-392">zlib</span><span class="sxs-lookup"><span data-stu-id="82bc9-392">zlib</span></span>

<span data-ttu-id="82bc9-393">Fedora ユーザー:ご使用の OpenSSL のバージョンが 1.1 以降の場合は、**compat-openssl10** をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="82bc9-394">.NET Core 2.0 では、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="82bc9-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="82bc9-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="82bc9-395">libunwind</span></span>
- <span data-ttu-id="82bc9-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="82bc9-396">libuuid</span></span>

<span data-ttu-id="82bc9-397">依存関係の詳細については、「[Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」(自己完結型 Linux アプリケーション) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="82bc9-398">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="82bc9-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="82bc9-399">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="82bc9-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="82bc9-400">CentOS と Fedora のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="82bc9-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="82bc9-401">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="82bc9-402">詳細については、「<https://www.mono-project.com/download/stable/>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="alpine"></a><span data-ttu-id="82bc9-403">Alpine</span><span class="sxs-lookup"><span data-stu-id="82bc9-403">Alpine</span></span>

<span data-ttu-id="82bc9-404">Alpine ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-404">Alpine distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="82bc9-405">icu-libs (グローバリゼーションが無効になっている場合、これは不要です)</span><span class="sxs-lookup"><span data-stu-id="82bc9-405">icu-libs (this is not needed if globalization is disabled)</span></span>
- <span data-ttu-id="82bc9-406">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="82bc9-406">krb5-libs</span></span>
- <span data-ttu-id="82bc9-407">libcurl</span><span class="sxs-lookup"><span data-stu-id="82bc9-407">libcurl</span></span>
- <span data-ttu-id="82bc9-408">libintl</span><span class="sxs-lookup"><span data-stu-id="82bc9-408">libintl</span></span>
- <span data-ttu-id="82bc9-409">libssl1.1 (Alpine 3.9 以降の場合) または libssl1.0 (それより以前のもの)</span><span class="sxs-lookup"><span data-stu-id="82bc9-409">libssl1.1 (for Alpine 3.9 or later) or libssl1.0 (for older ones)</span></span>
- <span data-ttu-id="82bc9-410">libstdc++</span><span class="sxs-lookup"><span data-stu-id="82bc9-410">libstdc++</span></span>
- <span data-ttu-id="82bc9-411">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="82bc9-411">lttng-ust</span></span>
- <span data-ttu-id="82bc9-412">numactl (省略可能、NUMA が有効になっているデバイスでのみ便利)</span><span class="sxs-lookup"><span data-stu-id="82bc9-412">numactl (optional, useful only for devices with NUMA enabled)</span></span>
- <span data-ttu-id="82bc9-413">zlib</span><span class="sxs-lookup"><span data-stu-id="82bc9-413">zlib</span></span>

<span data-ttu-id="82bc9-414">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="82bc9-414">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="82bc9-415">libgdiplus (edge/testing リポジトリでのみ利用可能)</span><span class="sxs-lookup"><span data-stu-id="82bc9-415">libgdiplus (it is available only in the edge/testing repository)</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="82bc9-416">.NET Core は、次の macOS のリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="82bc9-416">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="82bc9-417">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="82bc9-417">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="82bc9-418">.NET Core のバージョン</span><span class="sxs-lookup"><span data-stu-id="82bc9-418">.NET Core Version</span></span> | <span data-ttu-id="82bc9-419">macOS</span><span class="sxs-lookup"><span data-stu-id="82bc9-419">macOS</span></span>                 | <span data-ttu-id="82bc9-420">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="82bc9-420">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="82bc9-421">3.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-421">3.1</span></span>               | <span data-ttu-id="82bc9-422">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="82bc9-422">High Sierra (10.13+)</span></span>  | <span data-ttu-id="82bc9-423">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-423">x64</span></span> | [<span data-ttu-id="82bc9-424">詳細情報</span><span class="sxs-lookup"><span data-stu-id="82bc9-424">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="82bc9-425">3.0</span><span class="sxs-lookup"><span data-stu-id="82bc9-425">3.0</span></span>               | <span data-ttu-id="82bc9-426">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="82bc9-426">High Sierra (10.13+)</span></span>  | <span data-ttu-id="82bc9-427">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-427">x64</span></span> | [<span data-ttu-id="82bc9-428">詳細情報</span><span class="sxs-lookup"><span data-stu-id="82bc9-428">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="82bc9-429">2.2</span><span class="sxs-lookup"><span data-stu-id="82bc9-429">2.2</span></span>               | <span data-ttu-id="82bc9-430">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="82bc9-430">Sierra (10.12+)</span></span>       | <span data-ttu-id="82bc9-431">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-431">x64</span></span> | [<span data-ttu-id="82bc9-432">詳細情報</span><span class="sxs-lookup"><span data-stu-id="82bc9-432">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="82bc9-433">2.1</span><span class="sxs-lookup"><span data-stu-id="82bc9-433">2.1</span></span>               | <span data-ttu-id="82bc9-434">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="82bc9-434">Sierra (10.12+)</span></span>       | <span data-ttu-id="82bc9-435">X64</span><span class="sxs-lookup"><span data-stu-id="82bc9-435">x64</span></span> | [<span data-ttu-id="82bc9-436">詳細情報</span><span class="sxs-lookup"><span data-stu-id="82bc9-436">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="82bc9-437">macOS Catalina (バージョン 10.15) 以降では、2019 年 6 月 1 日より後に作成され、Developer ID と共に配布されたすべてのソフトウェアは公証される必要があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-437">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="82bc9-438">この要件は、.NET Core ランタイム、.NET Core SDK、および .NET Core を使用して作成されたソフトウェアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="82bc9-438">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="82bc9-439">.NET Core (ランタイムと SDK の両方) バージョン 3.1、3.0、2.1 のインストーラーは、2020 年 2 月 18 日から公証されています。</span><span class="sxs-lookup"><span data-stu-id="82bc9-439">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="82bc9-440">それより前にリリースされたバージョンは、公証されていません。</span><span class="sxs-lookup"><span data-stu-id="82bc9-440">Prior released versions aren't notarized.</span></span> <span data-ttu-id="82bc9-441">公証されていないアプリを実行すると、次のイメージのようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82bc9-441">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina の公証に関するアラート](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="82bc9-443">公証の強制が .NET Core (および .NET Core アプリ) に与える影響の詳細については、[macOS Catalina の公証への対応](macos-notarization-issues.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82bc9-443">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="82bc9-444">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="82bc9-444">libgdiplus</span></span>

<span data-ttu-id="82bc9-445">*System.Drawing.Common* アセンブリを使用する .NET Core アプリケーションでは、libgdiplus をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82bc9-445">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="82bc9-446">libgdiplus を取得する簡単な方法は、macOS の [Homebrew ("brew")](https://brew.sh/) パッケージ マネージャーを使用することです。</span><span class="sxs-lookup"><span data-stu-id="82bc9-446">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="82bc9-447">*brew* をインストールしたら、端末 (コマンド) プロンプトで次のコマンドを実行して libgdiplus をインストールします。</span><span class="sxs-lookup"><span data-stu-id="82bc9-447">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="82bc9-448">次の手順</span><span class="sxs-lookup"><span data-stu-id="82bc9-448">Next steps</span></span>

- <span data-ttu-id="82bc9-449">アプリを開発して実行するには、[.NET Core SDK](sdk.md) (ランタイムを含む) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="82bc9-449">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="82bc9-450">他のユーザーが作成したアプリを実行するには、[.NET Core ランタイム](runtime.md)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="82bc9-450">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
