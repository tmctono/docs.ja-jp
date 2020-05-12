---
title: .NET Core SDK とランタイムの依存関係 - .NET Core
description: Windows、Linux、および macOS に .NET Core SDK とランタイムをインストールするためのオペレーティング システムと CPU アーキテクチャの前提条件について説明します。
author: leecow
ms.author: leecow
ms.date: 04/30/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 280aa1431686ff99257580bb024a84b1e57f85c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895488"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="84dac-103">.NET Core の依存関係と要件</span><span class="sxs-lookup"><span data-stu-id="84dac-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="84dac-104">この記事では、.NET Core でサポートされているオペレーティング システムと CPU アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="84dac-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="84dac-105">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="84dac-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="84dac-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="84dac-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="84dac-107">.NET Core 3.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="84dac-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="84dac-108">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84dac-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="84dac-109">OS</span><span class="sxs-lookup"><span data-stu-id="84dac-109">OS</span></span>                            | <span data-ttu-id="84dac-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="84dac-110">Version</span></span>                        | <span data-ttu-id="84dac-111">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="84dac-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="84dac-112">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="84dac-112">Windows Client</span></span>                | <span data-ttu-id="84dac-113">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="84dac-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="84dac-114">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-114">x64, x86</span></span>        |
| <span data-ttu-id="84dac-115">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="84dac-115">Windows 10 Client</span></span>             | <span data-ttu-id="84dac-116">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="84dac-116">Version 1607+</span></span>                  | <span data-ttu-id="84dac-117">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-117">x64, x86</span></span>        |
| <span data-ttu-id="84dac-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="84dac-118">Windows Server</span></span>                | <span data-ttu-id="84dac-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="84dac-119">2012 R2+</span></span>                       | <span data-ttu-id="84dac-120">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-120">x64, x86</span></span>        |
| <span data-ttu-id="84dac-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="84dac-121">Nano Server</span></span>                   | <span data-ttu-id="84dac-122">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="84dac-122">Version 1803+</span></span>                  | <span data-ttu-id="84dac-123">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="84dac-123">x64, ARM32</span></span>      |

<span data-ttu-id="84dac-124">.NET Core 3.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)」(.NET Core 3.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="84dac-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84dac-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="84dac-126">" *.NET Core 3.0 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="84dac-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="84dac-127">.NET Core 3.0 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="84dac-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="84dac-128">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84dac-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="84dac-129">OS</span><span class="sxs-lookup"><span data-stu-id="84dac-129">OS</span></span>                            | <span data-ttu-id="84dac-130">バージョン</span><span class="sxs-lookup"><span data-stu-id="84dac-130">Version</span></span>                        | <span data-ttu-id="84dac-131">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="84dac-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="84dac-132">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="84dac-132">Windows Client</span></span>                | <span data-ttu-id="84dac-133">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="84dac-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="84dac-134">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-134">x64, x86</span></span>        |
| <span data-ttu-id="84dac-135">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="84dac-135">Windows 10 Client</span></span>             | <span data-ttu-id="84dac-136">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="84dac-136">Version 1607+</span></span>                  | <span data-ttu-id="84dac-137">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-137">x64, x86</span></span>        |
| <span data-ttu-id="84dac-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="84dac-138">Windows Server</span></span>                | <span data-ttu-id="84dac-139">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="84dac-139">2012 R2+</span></span>                       | <span data-ttu-id="84dac-140">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-140">x64, x86</span></span>        |
| <span data-ttu-id="84dac-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="84dac-141">Nano Server</span></span>                   | <span data-ttu-id="84dac-142">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="84dac-142">Version 1803+</span></span>                  | <span data-ttu-id="84dac-143">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="84dac-143">x64, ARM32</span></span>      |

<span data-ttu-id="84dac-144">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)」(.NET Core 3.0 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="84dac-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="84dac-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="84dac-146">" *.NET Core 2.2 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="84dac-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="84dac-147">.NET Core 2.2 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="84dac-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="84dac-148">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84dac-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="84dac-149">OS</span><span class="sxs-lookup"><span data-stu-id="84dac-149">OS</span></span>                            | <span data-ttu-id="84dac-150">バージョン</span><span class="sxs-lookup"><span data-stu-id="84dac-150">Version</span></span>                        | <span data-ttu-id="84dac-151">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="84dac-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="84dac-152">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="84dac-152">Windows Client</span></span>                | <span data-ttu-id="84dac-153">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="84dac-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="84dac-154">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-154">x64, x86</span></span>        |
| <span data-ttu-id="84dac-155">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="84dac-155">Windows 10 Client</span></span>             | <span data-ttu-id="84dac-156">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="84dac-156">Version 1607+</span></span>                  | <span data-ttu-id="84dac-157">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-157">x64, x86</span></span>        |
| <span data-ttu-id="84dac-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="84dac-158">Windows Server</span></span>                | <span data-ttu-id="84dac-159">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="84dac-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="84dac-160">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-160">x64, x86</span></span>        |
| <span data-ttu-id="84dac-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="84dac-161">Nano Server</span></span>                   | <span data-ttu-id="84dac-162">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="84dac-162">Version 1803+</span></span>                   | <span data-ttu-id="84dac-163">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="84dac-163">x64, ARM32</span></span>      |

<span data-ttu-id="84dac-164">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)」(.NET Core 2.2 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="84dac-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="84dac-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="84dac-166">.NET Core 2.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="84dac-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="84dac-167">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84dac-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="84dac-168">OS</span><span class="sxs-lookup"><span data-stu-id="84dac-168">OS</span></span>                            | <span data-ttu-id="84dac-169">バージョン</span><span class="sxs-lookup"><span data-stu-id="84dac-169">Version</span></span>                        | <span data-ttu-id="84dac-170">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="84dac-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="84dac-171">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="84dac-171">Windows Client</span></span>                | <span data-ttu-id="84dac-172">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="84dac-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="84dac-173">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-173">x64, x86</span></span>        |
| <span data-ttu-id="84dac-174">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="84dac-174">Windows 10 Client</span></span>             | <span data-ttu-id="84dac-175">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="84dac-175">Version 1607+</span></span>                  | <span data-ttu-id="84dac-176">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-176">x64, x86</span></span>        |
| <span data-ttu-id="84dac-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="84dac-177">Windows Server</span></span>                | <span data-ttu-id="84dac-178">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="84dac-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="84dac-179">x64、x86</span><span class="sxs-lookup"><span data-stu-id="84dac-179">x64, x86</span></span>        |
| <span data-ttu-id="84dac-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="84dac-180">Nano Server</span></span>                   | <span data-ttu-id="84dac-181">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="84dac-181">Version 1803+</span></span>                  | <span data-ttu-id="84dac-182">x64、</span><span class="sxs-lookup"><span data-stu-id="84dac-182">x64,</span></span>            |

<span data-ttu-id="84dac-183">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」(.NET Core 2.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="84dac-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="84dac-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="84dac-185">次の Windows のバージョンに .NET SDK またはランタイムをインストールする場合は、追加の依存関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="84dac-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="84dac-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="84dac-186">Windows 7 SP1</span></span>
- <span data-ttu-id="84dac-187">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="84dac-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="84dac-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="84dac-188">Windows 8.1</span></span>
- <span data-ttu-id="84dac-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="84dac-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="84dac-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="84dac-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="84dac-191">以下をインストールします。</span><span class="sxs-lookup"><span data-stu-id="84dac-191">Install the following:</span></span>

- <span data-ttu-id="84dac-192">[Microsoft Visual C++ 2015 再頒布可能パッケージ Update 3](https://www.microsoft.com/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="84dac-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="84dac-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="84dac-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="84dac-194">上記の要件は、次のいずれかのエラーが発生した場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="84dac-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="84dac-195">お使いのコンピューターに *api-ms-win-crt-runtime-l1-1-0.dll* が見つからず、プログラムを開始できない。</span><span class="sxs-lookup"><span data-stu-id="84dac-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="84dac-196">この問題を解決するには、プログラムを再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="84dac-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="84dac-197">\- または</span><span class="sxs-lookup"><span data-stu-id="84dac-197">\- or -</span></span>
>
> <span data-ttu-id="84dac-198">お使いのコンピューターに *api-ms-win-cor-timezone-l1-1-0.dll* が見つからず、プログラムを開始できない。</span><span class="sxs-lookup"><span data-stu-id="84dac-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="84dac-199">この問題を解決するには、プログラムを再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="84dac-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="84dac-200">\- または</span><span class="sxs-lookup"><span data-stu-id="84dac-200">\- or -</span></span>
>
> <span data-ttu-id="84dac-201">ライブラリ *hostfxr.dll* はあるが、それを *C:\\\<path_to_app>\\hostfxr.dll* から読み込むと失敗する。</span><span class="sxs-lookup"><span data-stu-id="84dac-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="84dac-202">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="84dac-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="84dac-203">.NET Core 3.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="84dac-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="84dac-204">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="84dac-205">.NET Core 3.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="84dac-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="84dac-206">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84dac-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="84dac-207">OS</span><span class="sxs-lookup"><span data-stu-id="84dac-207">OS</span></span>                             | <span data-ttu-id="84dac-208">バージョン</span><span class="sxs-lookup"><span data-stu-id="84dac-208">Version</span></span>               | <span data-ttu-id="84dac-209">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="84dac-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="84dac-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="84dac-211">6、7、8</span><span class="sxs-lookup"><span data-stu-id="84dac-211">6, 7, 8</span></span>               | <span data-ttu-id="84dac-212">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-212">x64</span></span> |
| <span data-ttu-id="84dac-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="84dac-213">CentOS</span></span>                         | <span data-ttu-id="84dac-214">7+</span><span class="sxs-lookup"><span data-stu-id="84dac-214">7+</span></span>                    | <span data-ttu-id="84dac-215">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-215">x64</span></span> |
| <span data-ttu-id="84dac-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-216">Oracle Linux</span></span>                   | <span data-ttu-id="84dac-217">7+</span><span class="sxs-lookup"><span data-stu-id="84dac-217">7+</span></span>                    | <span data-ttu-id="84dac-218">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-218">x64</span></span> |
| <span data-ttu-id="84dac-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="84dac-219">Fedora</span></span>                         | <span data-ttu-id="84dac-220">30+</span><span class="sxs-lookup"><span data-stu-id="84dac-220">30+</span></span>                   | <span data-ttu-id="84dac-221">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-221">x64</span></span> |
| <span data-ttu-id="84dac-222">Debian</span><span class="sxs-lookup"><span data-stu-id="84dac-222">Debian</span></span>                         | <span data-ttu-id="84dac-223">9+</span><span class="sxs-lookup"><span data-stu-id="84dac-223">9+</span></span>                    | <span data-ttu-id="84dac-224">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="84dac-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="84dac-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="84dac-225">Ubuntu</span></span>                         | <span data-ttu-id="84dac-226">16.04+</span><span class="sxs-lookup"><span data-stu-id="84dac-226">16.04+</span></span>                | <span data-ttu-id="84dac-227">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="84dac-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="84dac-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="84dac-228">Linux Mint</span></span>                     | <span data-ttu-id="84dac-229">18+</span><span class="sxs-lookup"><span data-stu-id="84dac-229">18+</span></span>                   | <span data-ttu-id="84dac-230">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-230">x64</span></span> |
| <span data-ttu-id="84dac-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="84dac-231">openSUSE</span></span>                       | <span data-ttu-id="84dac-232">15+</span><span class="sxs-lookup"><span data-stu-id="84dac-232">15+</span></span>                   | <span data-ttu-id="84dac-233">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-233">x64</span></span> |
| <span data-ttu-id="84dac-234">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="84dac-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="84dac-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="84dac-235">12 SP2+</span></span>               | <span data-ttu-id="84dac-236">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-236">x64</span></span> |
| <span data-ttu-id="84dac-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-237">Alpine Linux</span></span>                   | <span data-ttu-id="84dac-238">3.10+</span><span class="sxs-lookup"><span data-stu-id="84dac-238">3.10+</span></span>                 | <span data-ttu-id="84dac-239">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="84dac-239">x64, ARM64</span></span> |

<span data-ttu-id="84dac-240">.NET Core 3.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)」(.NET Core 3.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="84dac-241">ARM64 (カーネル 4.14+) 上に .NET Core 3.1 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」(Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84dac-242">ARM64 のサポートには、Linux カーネル 4.14 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="84dac-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="84dac-243">一部の linux ディストリビューションは、この要件を満たしていますが、そうでないものもあります。</span><span class="sxs-lookup"><span data-stu-id="84dac-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="84dac-244">たとえば、Ubuntu 18.04 ではサポートされていますが、Ubuntu 16.04 ではされていません。</span><span class="sxs-lookup"><span data-stu-id="84dac-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="84dac-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84dac-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="84dac-246">" *.NET Core 3.0 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="84dac-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="84dac-247">.NET Core 3.0 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="84dac-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="84dac-248">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="84dac-249">.NET Core 3.0 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="84dac-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="84dac-250">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84dac-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="84dac-251">OS</span><span class="sxs-lookup"><span data-stu-id="84dac-251">OS</span></span>                             | <span data-ttu-id="84dac-252">バージョン</span><span class="sxs-lookup"><span data-stu-id="84dac-252">Version</span></span>               | <span data-ttu-id="84dac-253">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="84dac-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="84dac-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="84dac-255">6、7、8</span><span class="sxs-lookup"><span data-stu-id="84dac-255">6, 7, 8</span></span>               | <span data-ttu-id="84dac-256">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-256">x64</span></span> |
| <span data-ttu-id="84dac-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="84dac-257">CentOS</span></span>                         | <span data-ttu-id="84dac-258">7+</span><span class="sxs-lookup"><span data-stu-id="84dac-258">7+</span></span>                    | <span data-ttu-id="84dac-259">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-259">x64</span></span> |
| <span data-ttu-id="84dac-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-260">Oracle Linux</span></span>                   | <span data-ttu-id="84dac-261">7+</span><span class="sxs-lookup"><span data-stu-id="84dac-261">7+</span></span>                    | <span data-ttu-id="84dac-262">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-262">x64</span></span> |
| <span data-ttu-id="84dac-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="84dac-263">Fedora</span></span>                         | <span data-ttu-id="84dac-264">29+</span><span class="sxs-lookup"><span data-stu-id="84dac-264">29+</span></span>                   | <span data-ttu-id="84dac-265">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-265">x64</span></span> |
| <span data-ttu-id="84dac-266">Debian</span><span class="sxs-lookup"><span data-stu-id="84dac-266">Debian</span></span>                         | <span data-ttu-id="84dac-267">9+</span><span class="sxs-lookup"><span data-stu-id="84dac-267">9+</span></span>                    | <span data-ttu-id="84dac-268">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="84dac-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="84dac-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="84dac-269">Ubuntu</span></span>                         | <span data-ttu-id="84dac-270">16.04+</span><span class="sxs-lookup"><span data-stu-id="84dac-270">16.04+</span></span>                | <span data-ttu-id="84dac-271">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="84dac-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="84dac-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="84dac-272">Linux Mint</span></span>                     | <span data-ttu-id="84dac-273">18+</span><span class="sxs-lookup"><span data-stu-id="84dac-273">18+</span></span>                   | <span data-ttu-id="84dac-274">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-274">x64</span></span> |
| <span data-ttu-id="84dac-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="84dac-275">openSUSE</span></span>                       | <span data-ttu-id="84dac-276">15+</span><span class="sxs-lookup"><span data-stu-id="84dac-276">15+</span></span>                   | <span data-ttu-id="84dac-277">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-277">x64</span></span> |
| <span data-ttu-id="84dac-278">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="84dac-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="84dac-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="84dac-279">12 SP2+</span></span>               | <span data-ttu-id="84dac-280">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-280">x64</span></span> |
| <span data-ttu-id="84dac-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-281">Alpine Linux</span></span>                   | <span data-ttu-id="84dac-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="84dac-282">3.8+</span></span>                  | <span data-ttu-id="84dac-283">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="84dac-283">x64, ARM64</span></span> |

<span data-ttu-id="84dac-284">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)」(.NET Core 3.0 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="84dac-285">ARM64 で .NET Core 3.0 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」 (Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="84dac-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="84dac-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="84dac-287">" *.NET Core 2.2 は現在サポートされていません。詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。* "</span><span class="sxs-lookup"><span data-stu-id="84dac-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="84dac-288">.NET Core 2.2 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="84dac-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="84dac-289">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="84dac-290">.NET Core 2.2 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="84dac-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="84dac-291">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84dac-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="84dac-292">OS</span><span class="sxs-lookup"><span data-stu-id="84dac-292">OS</span></span>                             |  <span data-ttu-id="84dac-293">バージョン</span><span class="sxs-lookup"><span data-stu-id="84dac-293">Version</span></span>                |  <span data-ttu-id="84dac-294">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="84dac-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="84dac-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="84dac-296">6、7</span><span class="sxs-lookup"><span data-stu-id="84dac-296">6, 7</span></span>                   | <span data-ttu-id="84dac-297">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-297">x64</span></span> |
| <span data-ttu-id="84dac-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="84dac-298">CentOS</span></span>                         |  <span data-ttu-id="84dac-299">7</span><span class="sxs-lookup"><span data-stu-id="84dac-299">7</span></span>                      | <span data-ttu-id="84dac-300">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-300">x64</span></span> |
| <span data-ttu-id="84dac-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-301">Oracle Linux</span></span>                   |  <span data-ttu-id="84dac-302">7</span><span class="sxs-lookup"><span data-stu-id="84dac-302">7</span></span>                      | <span data-ttu-id="84dac-303">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-303">x64</span></span> |
| <span data-ttu-id="84dac-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="84dac-304">Fedora</span></span>                         |  <span data-ttu-id="84dac-305">29、30</span><span class="sxs-lookup"><span data-stu-id="84dac-305">29, 30</span></span>                 | <span data-ttu-id="84dac-306">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-306">x64</span></span> |
| <span data-ttu-id="84dac-307">Debian</span><span class="sxs-lookup"><span data-stu-id="84dac-307">Debian</span></span>                         |  <span data-ttu-id="84dac-308">9</span><span class="sxs-lookup"><span data-stu-id="84dac-308">9</span></span>                      | <span data-ttu-id="84dac-309">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="84dac-309">x64, ARM32</span></span> |
| <span data-ttu-id="84dac-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="84dac-310">Ubuntu</span></span>                         |  <span data-ttu-id="84dac-311">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="84dac-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="84dac-312">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="84dac-312">x64, ARM32</span></span> |
| <span data-ttu-id="84dac-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="84dac-313">Linux Mint</span></span>                     |  <span data-ttu-id="84dac-314">17、18</span><span class="sxs-lookup"><span data-stu-id="84dac-314">17, 18</span></span>                 | <span data-ttu-id="84dac-315">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-315">x64</span></span> |
| <span data-ttu-id="84dac-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="84dac-316">openSUSE</span></span>                       |  <span data-ttu-id="84dac-317">15+</span><span class="sxs-lookup"><span data-stu-id="84dac-317">15+</span></span>                    | <span data-ttu-id="84dac-318">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-318">x64</span></span> |
| <span data-ttu-id="84dac-319">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="84dac-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="84dac-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="84dac-320">12 SP2+</span></span>                | <span data-ttu-id="84dac-321">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-321">x64</span></span> |
| <span data-ttu-id="84dac-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-322">Alpine Linux</span></span>                   |  <span data-ttu-id="84dac-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="84dac-323">3.8+</span></span>                   | <span data-ttu-id="84dac-324">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-324">x64</span></span> |

<span data-ttu-id="84dac-325">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)」(.NET Core 2.2 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="84dac-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="84dac-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="84dac-327">.NET Core 2.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="84dac-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="84dac-328">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="84dac-329">.NET Core 2.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="84dac-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="84dac-330">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84dac-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="84dac-331">OS</span><span class="sxs-lookup"><span data-stu-id="84dac-331">OS</span></span>                             |  <span data-ttu-id="84dac-332">バージョン</span><span class="sxs-lookup"><span data-stu-id="84dac-332">Version</span></span>                |  <span data-ttu-id="84dac-333">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="84dac-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="84dac-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="84dac-335">6、7、8</span><span class="sxs-lookup"><span data-stu-id="84dac-335">6, 7, 8</span></span>                | <span data-ttu-id="84dac-336">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-336">x64</span></span> |
| <span data-ttu-id="84dac-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="84dac-337">CentOS</span></span>                         |  <span data-ttu-id="84dac-338">7+</span><span class="sxs-lookup"><span data-stu-id="84dac-338">7+</span></span>                     | <span data-ttu-id="84dac-339">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-339">x64</span></span> |
| <span data-ttu-id="84dac-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-340">Oracle Linux</span></span>                   |  <span data-ttu-id="84dac-341">7+</span><span class="sxs-lookup"><span data-stu-id="84dac-341">7+</span></span>                     | <span data-ttu-id="84dac-342">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-342">x64</span></span> |
| <span data-ttu-id="84dac-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="84dac-343">Fedora</span></span>                         |  <span data-ttu-id="84dac-344">30+</span><span class="sxs-lookup"><span data-stu-id="84dac-344">30+</span></span>                    | <span data-ttu-id="84dac-345">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-345">x64</span></span> |
| <span data-ttu-id="84dac-346">Debian</span><span class="sxs-lookup"><span data-stu-id="84dac-346">Debian</span></span>                         |  <span data-ttu-id="84dac-347">9</span><span class="sxs-lookup"><span data-stu-id="84dac-347">9</span></span>                      | <span data-ttu-id="84dac-348">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="84dac-348">x64, ARM32</span></span> |
| <span data-ttu-id="84dac-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="84dac-349">Ubuntu</span></span>                         |  <span data-ttu-id="84dac-350">16.04、18.04、19.04、19.10</span><span class="sxs-lookup"><span data-stu-id="84dac-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="84dac-351">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="84dac-351">x64, ARM32</span></span> |
| <span data-ttu-id="84dac-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="84dac-352">Linux Mint</span></span>                     |  <span data-ttu-id="84dac-353">17+</span><span class="sxs-lookup"><span data-stu-id="84dac-353">17+</span></span>                    | <span data-ttu-id="84dac-354">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-354">x64</span></span> |
| <span data-ttu-id="84dac-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="84dac-355">openSUSE</span></span>                       |  <span data-ttu-id="84dac-356">15+</span><span class="sxs-lookup"><span data-stu-id="84dac-356">15+</span></span>                    | <span data-ttu-id="84dac-357">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-357">x64</span></span> |
| <span data-ttu-id="84dac-358">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="84dac-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="84dac-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="84dac-359">12 SP2+</span></span>                | <span data-ttu-id="84dac-360">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-360">x64</span></span> |
| <span data-ttu-id="84dac-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="84dac-361">Alpine Linux</span></span>                   |  <span data-ttu-id="84dac-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="84dac-362">3.8+</span></span>                   | <span data-ttu-id="84dac-363">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-363">x64</span></span> |

<span data-ttu-id="84dac-364">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」(.NET Core 2.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="84dac-365">Linux ディストリビューションの依存関係</span><span class="sxs-lookup"><span data-stu-id="84dac-365">Linux distribution dependencies</span></span>

<span data-ttu-id="84dac-366">Linux ディストリビューションによっては、追加の依存関係のインストールが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84dac-367">選択した Linux ディストリビューションで、バージョンと名前が多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="84dac-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="84dac-368">Ubuntu</span></span>

<span data-ttu-id="84dac-369">Ubuntu ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="84dac-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="84dac-370">liblttng-ust0</span></span>
- <span data-ttu-id="84dac-371">libcurl3 (14.x および 16.x 用)</span><span class="sxs-lookup"><span data-stu-id="84dac-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="84dac-372">libcurl4 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="84dac-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="84dac-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="84dac-373">libssl1.0.0</span></span>
- <span data-ttu-id="84dac-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="84dac-374">libkrb5-3</span></span>
- <span data-ttu-id="84dac-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="84dac-375">zlib1g</span></span>
- <span data-ttu-id="84dac-376">libicu52 (14.x 用)</span><span class="sxs-lookup"><span data-stu-id="84dac-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="84dac-377">libicu55 (16.x 用)</span><span class="sxs-lookup"><span data-stu-id="84dac-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="84dac-378">libicu57 (17.x 用)</span><span class="sxs-lookup"><span data-stu-id="84dac-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="84dac-379">libicu60 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="84dac-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="84dac-380">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="84dac-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="84dac-381">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="84dac-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="84dac-382">Ubuntu のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="84dac-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="84dac-383">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="84dac-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="84dac-384">詳細については、「<https://www.mono-project.com/download/stable/>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="84dac-385">CentOS と Fedora</span><span class="sxs-lookup"><span data-stu-id="84dac-385">CentOS and Fedora</span></span>

<span data-ttu-id="84dac-386">CentOS ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="84dac-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="84dac-387">lttng-ust</span></span>
- <span data-ttu-id="84dac-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="84dac-388">libcurl</span></span>
- <span data-ttu-id="84dac-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="84dac-389">openssl-libs</span></span>
- <span data-ttu-id="84dac-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="84dac-390">krb5-libs</span></span>
- <span data-ttu-id="84dac-391">libicu</span><span class="sxs-lookup"><span data-stu-id="84dac-391">libicu</span></span>
- <span data-ttu-id="84dac-392">zlib</span><span class="sxs-lookup"><span data-stu-id="84dac-392">zlib</span></span>

<span data-ttu-id="84dac-393">Fedora ユーザー:ご使用の OpenSSL のバージョンが 1.1 以降の場合は、**compat-openssl10** をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="84dac-394">.NET Core 2.0 では、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="84dac-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="84dac-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="84dac-395">libunwind</span></span>
- <span data-ttu-id="84dac-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="84dac-396">libuuid</span></span>

<span data-ttu-id="84dac-397">依存関係の詳細については、「[Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」(自己完結型 Linux アプリケーション) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="84dac-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="84dac-398">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="84dac-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="84dac-399">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="84dac-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="84dac-400">CentOS と Fedora のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="84dac-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="84dac-401">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="84dac-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="84dac-402">詳細については、「<https://www.mono-project.com/download/stable/>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="alpine"></a><span data-ttu-id="84dac-403">Alpine</span><span class="sxs-lookup"><span data-stu-id="84dac-403">Alpine</span></span>

<span data-ttu-id="84dac-404">Alpine ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-404">Alpine distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="84dac-405">icu-libs (グローバリゼーションが無効になっている場合、これは不要です)</span><span class="sxs-lookup"><span data-stu-id="84dac-405">icu-libs (this is not needed if globalization is disabled)</span></span>
- <span data-ttu-id="84dac-406">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="84dac-406">krb5-libs</span></span>
- <span data-ttu-id="84dac-407">libcurl</span><span class="sxs-lookup"><span data-stu-id="84dac-407">libcurl</span></span>
- <span data-ttu-id="84dac-408">libintl</span><span class="sxs-lookup"><span data-stu-id="84dac-408">libintl</span></span>
- <span data-ttu-id="84dac-409">libssl1.1 (Alpine 3.9 以降の場合) または libssl1.0 (それより以前のもの)</span><span class="sxs-lookup"><span data-stu-id="84dac-409">libssl1.1 (for Alpine 3.9 or later) or libssl1.0 (for older ones)</span></span>
- <span data-ttu-id="84dac-410">libstdc++</span><span class="sxs-lookup"><span data-stu-id="84dac-410">libstdc++</span></span>
- <span data-ttu-id="84dac-411">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="84dac-411">lttng-ust</span></span>
- <span data-ttu-id="84dac-412">numactl (省略可能、NUMA が有効になっているデバイスでのみ便利)</span><span class="sxs-lookup"><span data-stu-id="84dac-412">numactl (optional, useful only for devices with NUMA enabled)</span></span>
- <span data-ttu-id="84dac-413">zlib</span><span class="sxs-lookup"><span data-stu-id="84dac-413">zlib</span></span>

<span data-ttu-id="84dac-414">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="84dac-414">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="84dac-415">libgdiplus (edge/testing リポジトリでのみ利用可能)</span><span class="sxs-lookup"><span data-stu-id="84dac-415">libgdiplus (it is available only in the edge/testing repository)</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="84dac-416">.NET Core は、次の macOS のリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="84dac-416">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="84dac-417">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84dac-417">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="84dac-418">.NET Core のバージョン</span><span class="sxs-lookup"><span data-stu-id="84dac-418">.NET Core Version</span></span> | <span data-ttu-id="84dac-419">macOS</span><span class="sxs-lookup"><span data-stu-id="84dac-419">macOS</span></span>                 | <span data-ttu-id="84dac-420">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="84dac-420">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="84dac-421">3.1</span><span class="sxs-lookup"><span data-stu-id="84dac-421">3.1</span></span>               | <span data-ttu-id="84dac-422">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="84dac-422">High Sierra (10.13+)</span></span>  | <span data-ttu-id="84dac-423">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-423">x64</span></span> | [<span data-ttu-id="84dac-424">詳細情報</span><span class="sxs-lookup"><span data-stu-id="84dac-424">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="84dac-425">3.0</span><span class="sxs-lookup"><span data-stu-id="84dac-425">3.0</span></span>               | <span data-ttu-id="84dac-426">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="84dac-426">High Sierra (10.13+)</span></span>  | <span data-ttu-id="84dac-427">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-427">x64</span></span> | [<span data-ttu-id="84dac-428">詳細情報</span><span class="sxs-lookup"><span data-stu-id="84dac-428">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="84dac-429">2.2</span><span class="sxs-lookup"><span data-stu-id="84dac-429">2.2</span></span>               | <span data-ttu-id="84dac-430">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="84dac-430">Sierra (10.12+)</span></span>       | <span data-ttu-id="84dac-431">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-431">x64</span></span> | [<span data-ttu-id="84dac-432">詳細情報</span><span class="sxs-lookup"><span data-stu-id="84dac-432">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="84dac-433">2.1</span><span class="sxs-lookup"><span data-stu-id="84dac-433">2.1</span></span>               | <span data-ttu-id="84dac-434">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="84dac-434">Sierra (10.12+)</span></span>       | <span data-ttu-id="84dac-435">X64</span><span class="sxs-lookup"><span data-stu-id="84dac-435">x64</span></span> | [<span data-ttu-id="84dac-436">詳細情報</span><span class="sxs-lookup"><span data-stu-id="84dac-436">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="84dac-437">macOS Catalina (バージョン 10.15) 以降では、2019 年 6 月 1 日より後に作成され、Developer ID と共に配布されたすべてのソフトウェアは公証される必要があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-437">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="84dac-438">この要件は、.NET Core ランタイム、.NET Core SDK、および .NET Core を使用して作成されたソフトウェアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="84dac-438">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="84dac-439">.NET Core (ランタイムと SDK の両方) バージョン 3.1、3.0、2.1 のインストーラーは、2020 年 2 月 18 日から公証されています。</span><span class="sxs-lookup"><span data-stu-id="84dac-439">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="84dac-440">それより前にリリースされたバージョンは、公証されていません。</span><span class="sxs-lookup"><span data-stu-id="84dac-440">Prior released versions aren't notarized.</span></span> <span data-ttu-id="84dac-441">公証されていないアプリを実行すると、次のイメージのようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84dac-441">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina の公証に関するアラート](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="84dac-443">公証の強制が .NET Core (および .NET Core アプリ) に与える影響の詳細については、[macOS Catalina の公証への対応](macos-notarization-issues.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84dac-443">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="84dac-444">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="84dac-444">libgdiplus</span></span>

<span data-ttu-id="84dac-445">*System.Drawing.Common* アセンブリを使用する .NET Core アプリケーションでは、libgdiplus をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84dac-445">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="84dac-446">libgdiplus を取得する簡単な方法は、macOS の [Homebrew ("brew")](https://brew.sh/) パッケージ マネージャーを使用することです。</span><span class="sxs-lookup"><span data-stu-id="84dac-446">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="84dac-447">*brew* をインストールしたら、端末 (コマンド) プロンプトで次のコマンドを実行して libgdiplus をインストールします。</span><span class="sxs-lookup"><span data-stu-id="84dac-447">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="84dac-448">次の手順</span><span class="sxs-lookup"><span data-stu-id="84dac-448">Next steps</span></span>

- <span data-ttu-id="84dac-449">アプリを開発して実行するには、[.NET Core SDK](sdk.md) (ランタイムを含む) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="84dac-449">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="84dac-450">他のユーザーが作成したアプリを実行するには、[.NET Core ランタイム](runtime.md)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="84dac-450">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
