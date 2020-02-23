---
title: .NET Core SDK とランタイムの依存関係 - .NET Core
description: Windows、Linux、および macOS に .NET Core SDK とランタイムをインストールするためのオペレーティング システムと CPU アーキテクチャの前提条件について説明します。
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4164ea5a04d80ab20109168a225b793b02ee616a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448894"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="1d041-103">.NET Core の依存関係と要件</span><span class="sxs-lookup"><span data-stu-id="1d041-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="1d041-104">この記事では、.NET Core でサポートされているオペレーティング システムと CPU アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1d041-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="1d041-105">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="1d041-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="1d041-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1d041-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="1d041-107">.NET Core 3.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1d041-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="1d041-108">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d041-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1d041-109">OS</span><span class="sxs-lookup"><span data-stu-id="1d041-109">OS</span></span>                            | <span data-ttu-id="1d041-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="1d041-110">Version</span></span>                        | <span data-ttu-id="1d041-111">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d041-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1d041-112">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="1d041-112">Windows Client</span></span>                | <span data-ttu-id="1d041-113">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="1d041-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1d041-114">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-114">x64, x86</span></span>        |
| <span data-ttu-id="1d041-115">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="1d041-115">Windows 10 Client</span></span>             | <span data-ttu-id="1d041-116">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="1d041-116">Version 1607+</span></span>                  | <span data-ttu-id="1d041-117">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-117">x64, x86</span></span>        |
| <span data-ttu-id="1d041-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1d041-118">Windows Server</span></span>                | <span data-ttu-id="1d041-119">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="1d041-119">2012 R2+</span></span>                       | <span data-ttu-id="1d041-120">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-120">x64, x86</span></span>        |
| <span data-ttu-id="1d041-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1d041-121">Nano Server</span></span>                   | <span data-ttu-id="1d041-122">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="1d041-122">Version 1803+</span></span>                  | <span data-ttu-id="1d041-123">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1d041-123">x64, ARM32</span></span>      |

<span data-ttu-id="1d041-124">.NET Core 3.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)」(.NET Core 3.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="1d041-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1d041-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="1d041-126">.NET Core 3.0 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1d041-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="1d041-127">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d041-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1d041-128">OS</span><span class="sxs-lookup"><span data-stu-id="1d041-128">OS</span></span>                            | <span data-ttu-id="1d041-129">バージョン</span><span class="sxs-lookup"><span data-stu-id="1d041-129">Version</span></span>                        | <span data-ttu-id="1d041-130">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d041-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1d041-131">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="1d041-131">Windows Client</span></span>                | <span data-ttu-id="1d041-132">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="1d041-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1d041-133">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-133">x64, x86</span></span>        |
| <span data-ttu-id="1d041-134">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="1d041-134">Windows 10 Client</span></span>             | <span data-ttu-id="1d041-135">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="1d041-135">Version 1607+</span></span>                  | <span data-ttu-id="1d041-136">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-136">x64, x86</span></span>        |
| <span data-ttu-id="1d041-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1d041-137">Windows Server</span></span>                | <span data-ttu-id="1d041-138">2012 R2+</span><span class="sxs-lookup"><span data-stu-id="1d041-138">2012 R2+</span></span>                       | <span data-ttu-id="1d041-139">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-139">x64, x86</span></span>        |
| <span data-ttu-id="1d041-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1d041-140">Nano Server</span></span>                   | <span data-ttu-id="1d041-141">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="1d041-141">Version 1803+</span></span>                  | <span data-ttu-id="1d041-142">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1d041-142">x64, ARM32</span></span>      |

<span data-ttu-id="1d041-143">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)」(.NET Core 3.0 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="1d041-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="1d041-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="1d041-145">.NET Core 2.2 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1d041-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="1d041-146">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d041-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1d041-147">OS</span><span class="sxs-lookup"><span data-stu-id="1d041-147">OS</span></span>                            | <span data-ttu-id="1d041-148">バージョン</span><span class="sxs-lookup"><span data-stu-id="1d041-148">Version</span></span>                        | <span data-ttu-id="1d041-149">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d041-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1d041-150">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="1d041-150">Windows Client</span></span>                | <span data-ttu-id="1d041-151">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="1d041-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1d041-152">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-152">x64, x86</span></span>        |
| <span data-ttu-id="1d041-153">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="1d041-153">Windows 10 Client</span></span>             | <span data-ttu-id="1d041-154">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="1d041-154">Version 1607+</span></span>                  | <span data-ttu-id="1d041-155">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-155">x64, x86</span></span>        |
| <span data-ttu-id="1d041-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1d041-156">Windows Server</span></span>                | <span data-ttu-id="1d041-157">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="1d041-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="1d041-158">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-158">x64, x86</span></span>        |
| <span data-ttu-id="1d041-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1d041-159">Nano Server</span></span>                   | <span data-ttu-id="1d041-160">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="1d041-160">Version 1803+</span></span>                   | <span data-ttu-id="1d041-161">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1d041-161">x64, ARM32</span></span>      |

<span data-ttu-id="1d041-162">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)」(.NET Core 2.2 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1d041-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1d041-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1d041-164">.NET Core 2.1 では以下の Windows のバージョンがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1d041-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="1d041-165">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d041-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1d041-166">OS</span><span class="sxs-lookup"><span data-stu-id="1d041-166">OS</span></span>                            | <span data-ttu-id="1d041-167">バージョン</span><span class="sxs-lookup"><span data-stu-id="1d041-167">Version</span></span>                        | <span data-ttu-id="1d041-168">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d041-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1d041-169">Windows クライアント</span><span class="sxs-lookup"><span data-stu-id="1d041-169">Windows Client</span></span>                | <span data-ttu-id="1d041-170">7 SP1+、8.1</span><span class="sxs-lookup"><span data-stu-id="1d041-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1d041-171">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-171">x64, x86</span></span>        |
| <span data-ttu-id="1d041-172">Windows 10 クライアント</span><span class="sxs-lookup"><span data-stu-id="1d041-172">Windows 10 Client</span></span>             | <span data-ttu-id="1d041-173">バージョン 1607+</span><span class="sxs-lookup"><span data-stu-id="1d041-173">Version 1607+</span></span>                  | <span data-ttu-id="1d041-174">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-174">x64, x86</span></span>        |
| <span data-ttu-id="1d041-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1d041-175">Windows Server</span></span>                | <span data-ttu-id="1d041-176">2008 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="1d041-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="1d041-177">x64、x86</span><span class="sxs-lookup"><span data-stu-id="1d041-177">x64, x86</span></span>        |
| <span data-ttu-id="1d041-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1d041-178">Nano Server</span></span>                   | <span data-ttu-id="1d041-179">バージョン 1803+</span><span class="sxs-lookup"><span data-stu-id="1d041-179">Version 1803+</span></span>                  | <span data-ttu-id="1d041-180">x64、</span><span class="sxs-lookup"><span data-stu-id="1d041-180">x64,</span></span>            |

<span data-ttu-id="1d041-181">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」(.NET Core 2.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="1d041-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1d041-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="1d041-183">次の Windows のバージョンに .NET SDK またはランタイムをインストールする場合は、追加の依存関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d041-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="1d041-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="1d041-184">Windows 7 SP1</span></span>
- <span data-ttu-id="1d041-185">Windows Vista SP 2</span><span class="sxs-lookup"><span data-stu-id="1d041-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="1d041-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1d041-186">Windows 8.1</span></span>
- <span data-ttu-id="1d041-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1d041-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="1d041-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1d041-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="1d041-189">以下をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d041-189">Install the following:</span></span>

- <span data-ttu-id="1d041-190">[Microsoft Visual C++ 2015 再頒布可能パッケージ Update 3](https://www.microsoft.com/download/details.aspx?id=52685)。</span><span class="sxs-lookup"><span data-stu-id="1d041-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="1d041-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="1d041-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="1d041-192">上記の要件は、次のいずれかのエラーが発生した場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="1d041-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="1d041-193">お使いのコンピューターに *api-ms-win-crt-runtime-l1-1-0.dll* が見つからず、プログラムを開始できない。</span><span class="sxs-lookup"><span data-stu-id="1d041-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="1d041-194">この問題を解決するには、プログラムを再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="1d041-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="1d041-195">\- または</span><span class="sxs-lookup"><span data-stu-id="1d041-195">\- or -</span></span>
>
> <span data-ttu-id="1d041-196">ライブラリ *hostfxr.dll* はあるが、それを *C:\\\<path_to_app>\\hostfxr.dll* から読み込むと失敗する。</span><span class="sxs-lookup"><span data-stu-id="1d041-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="1d041-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1d041-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="1d041-198">.NET Core 3.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="1d041-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="1d041-199">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1d041-200">.NET Core 3.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1d041-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1d041-201">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d041-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1d041-202">OS</span><span class="sxs-lookup"><span data-stu-id="1d041-202">OS</span></span>                             | <span data-ttu-id="1d041-203">バージョン</span><span class="sxs-lookup"><span data-stu-id="1d041-203">Version</span></span>               | <span data-ttu-id="1d041-204">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d041-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="1d041-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="1d041-206">6、7、8</span><span class="sxs-lookup"><span data-stu-id="1d041-206">6, 7, 8</span></span>               | <span data-ttu-id="1d041-207">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-207">x64</span></span> |
| <span data-ttu-id="1d041-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="1d041-208">CentOS</span></span>                         | <span data-ttu-id="1d041-209">7+</span><span class="sxs-lookup"><span data-stu-id="1d041-209">7+</span></span>                    | <span data-ttu-id="1d041-210">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-210">x64</span></span> |
| <span data-ttu-id="1d041-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-211">Oracle Linux</span></span>                   | <span data-ttu-id="1d041-212">7+</span><span class="sxs-lookup"><span data-stu-id="1d041-212">7+</span></span>                    | <span data-ttu-id="1d041-213">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-213">x64</span></span> |
| <span data-ttu-id="1d041-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="1d041-214">Fedora</span></span>                         | <span data-ttu-id="1d041-215">29+</span><span class="sxs-lookup"><span data-stu-id="1d041-215">29+</span></span>                   | <span data-ttu-id="1d041-216">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-216">x64</span></span> |
| <span data-ttu-id="1d041-217">Debian</span><span class="sxs-lookup"><span data-stu-id="1d041-217">Debian</span></span>                         | <span data-ttu-id="1d041-218">9+</span><span class="sxs-lookup"><span data-stu-id="1d041-218">9+</span></span>                    | <span data-ttu-id="1d041-219">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="1d041-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1d041-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1d041-220">Ubuntu</span></span>                         | <span data-ttu-id="1d041-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="1d041-221">16.04+</span></span>                | <span data-ttu-id="1d041-222">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="1d041-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1d041-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1d041-223">Linux Mint</span></span>                     | <span data-ttu-id="1d041-224">18+</span><span class="sxs-lookup"><span data-stu-id="1d041-224">18+</span></span>                   | <span data-ttu-id="1d041-225">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-225">x64</span></span> |
| <span data-ttu-id="1d041-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1d041-226">openSUSE</span></span>                       | <span data-ttu-id="1d041-227">15+</span><span class="sxs-lookup"><span data-stu-id="1d041-227">15+</span></span>                   | <span data-ttu-id="1d041-228">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-228">x64</span></span> |
| <span data-ttu-id="1d041-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1d041-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="1d041-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1d041-230">12 SP2+</span></span>               | <span data-ttu-id="1d041-231">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-231">x64</span></span> |
| <span data-ttu-id="1d041-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-232">Alpine Linux</span></span>                   | <span data-ttu-id="1d041-233">3.10+</span><span class="sxs-lookup"><span data-stu-id="1d041-233">3.10+</span></span>                 | <span data-ttu-id="1d041-234">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="1d041-234">x64, ARM64</span></span> |

<span data-ttu-id="1d041-235">.NET Core 3.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)」(.NET Core 3.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="1d041-236">ARM64 (カーネル 4.14+) 上に .NET Core 3.1 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」(Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d041-237">ARM64 のサポートには、Linux カーネル 4.14 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d041-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="1d041-238">一部の linux ディストリビューションは、この要件を満たしていますが、そうでないものもあります。</span><span class="sxs-lookup"><span data-stu-id="1d041-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="1d041-239">たとえば、Ubuntu 18.04 ではサポートされていますが、Ubuntu 16.04 ではされていません。</span><span class="sxs-lookup"><span data-stu-id="1d041-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="1d041-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1d041-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="1d041-241">.NET Core 3.0 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="1d041-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="1d041-242">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1d041-243">.NET Core 3.0 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1d041-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1d041-244">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d041-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1d041-245">OS</span><span class="sxs-lookup"><span data-stu-id="1d041-245">OS</span></span>                             | <span data-ttu-id="1d041-246">バージョン</span><span class="sxs-lookup"><span data-stu-id="1d041-246">Version</span></span>               | <span data-ttu-id="1d041-247">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d041-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="1d041-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="1d041-249">6、7、8</span><span class="sxs-lookup"><span data-stu-id="1d041-249">6, 7, 8</span></span>               | <span data-ttu-id="1d041-250">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-250">x64</span></span> |
| <span data-ttu-id="1d041-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="1d041-251">CentOS</span></span>                         | <span data-ttu-id="1d041-252">7+</span><span class="sxs-lookup"><span data-stu-id="1d041-252">7+</span></span>                    | <span data-ttu-id="1d041-253">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-253">x64</span></span> |
| <span data-ttu-id="1d041-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-254">Oracle Linux</span></span>                   | <span data-ttu-id="1d041-255">7+</span><span class="sxs-lookup"><span data-stu-id="1d041-255">7+</span></span>                    | <span data-ttu-id="1d041-256">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-256">x64</span></span> |
| <span data-ttu-id="1d041-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="1d041-257">Fedora</span></span>                         | <span data-ttu-id="1d041-258">29+</span><span class="sxs-lookup"><span data-stu-id="1d041-258">29+</span></span>                   | <span data-ttu-id="1d041-259">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-259">x64</span></span> |
| <span data-ttu-id="1d041-260">Debian</span><span class="sxs-lookup"><span data-stu-id="1d041-260">Debian</span></span>                         | <span data-ttu-id="1d041-261">9+</span><span class="sxs-lookup"><span data-stu-id="1d041-261">9+</span></span>                    | <span data-ttu-id="1d041-262">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="1d041-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1d041-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1d041-263">Ubuntu</span></span>                         | <span data-ttu-id="1d041-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="1d041-264">16.04+</span></span>                | <span data-ttu-id="1d041-265">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="1d041-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1d041-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1d041-266">Linux Mint</span></span>                     | <span data-ttu-id="1d041-267">18+</span><span class="sxs-lookup"><span data-stu-id="1d041-267">18+</span></span>                   | <span data-ttu-id="1d041-268">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-268">x64</span></span> |
| <span data-ttu-id="1d041-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1d041-269">openSUSE</span></span>                       | <span data-ttu-id="1d041-270">15+</span><span class="sxs-lookup"><span data-stu-id="1d041-270">15+</span></span>                   | <span data-ttu-id="1d041-271">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-271">x64</span></span> |
| <span data-ttu-id="1d041-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1d041-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="1d041-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1d041-273">12 SP2+</span></span>               | <span data-ttu-id="1d041-274">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-274">x64</span></span> |
| <span data-ttu-id="1d041-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-275">Alpine Linux</span></span>                   | <span data-ttu-id="1d041-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="1d041-276">3.8+</span></span>                  | <span data-ttu-id="1d041-277">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="1d041-277">x64, ARM64</span></span> |

<span data-ttu-id="1d041-278">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)」(.NET Core 3.0 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="1d041-279">ARM64 で .NET Core 3.0 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」 (Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="1d041-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="1d041-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="1d041-281">.NET Core 2.2 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="1d041-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="1d041-282">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1d041-283">.NET Core 2.2 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1d041-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1d041-284">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d041-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1d041-285">OS</span><span class="sxs-lookup"><span data-stu-id="1d041-285">OS</span></span>                             |  <span data-ttu-id="1d041-286">バージョン</span><span class="sxs-lookup"><span data-stu-id="1d041-286">Version</span></span>                |  <span data-ttu-id="1d041-287">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d041-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="1d041-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="1d041-289">6、7</span><span class="sxs-lookup"><span data-stu-id="1d041-289">6, 7</span></span>                   | <span data-ttu-id="1d041-290">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-290">x64</span></span> |
| <span data-ttu-id="1d041-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="1d041-291">CentOS</span></span>                         |  <span data-ttu-id="1d041-292">7</span><span class="sxs-lookup"><span data-stu-id="1d041-292">7</span></span>                      | <span data-ttu-id="1d041-293">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-293">x64</span></span> |
| <span data-ttu-id="1d041-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-294">Oracle Linux</span></span>                   |  <span data-ttu-id="1d041-295">7</span><span class="sxs-lookup"><span data-stu-id="1d041-295">7</span></span>                      | <span data-ttu-id="1d041-296">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-296">x64</span></span> |
| <span data-ttu-id="1d041-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="1d041-297">Fedora</span></span>                         |  <span data-ttu-id="1d041-298">29、30</span><span class="sxs-lookup"><span data-stu-id="1d041-298">29, 30</span></span>                 | <span data-ttu-id="1d041-299">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-299">x64</span></span> |
| <span data-ttu-id="1d041-300">Debian</span><span class="sxs-lookup"><span data-stu-id="1d041-300">Debian</span></span>                         |  <span data-ttu-id="1d041-301">9</span><span class="sxs-lookup"><span data-stu-id="1d041-301">9</span></span>                      | <span data-ttu-id="1d041-302">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1d041-302">x64, ARM32</span></span> |
| <span data-ttu-id="1d041-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1d041-303">Ubuntu</span></span>                         |  <span data-ttu-id="1d041-304">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="1d041-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="1d041-305">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1d041-305">x64, ARM32</span></span> |
| <span data-ttu-id="1d041-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1d041-306">Linux Mint</span></span>                     |  <span data-ttu-id="1d041-307">17、18</span><span class="sxs-lookup"><span data-stu-id="1d041-307">17, 18</span></span>                 | <span data-ttu-id="1d041-308">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-308">x64</span></span> |
| <span data-ttu-id="1d041-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1d041-309">openSUSE</span></span>                       |  <span data-ttu-id="1d041-310">15+</span><span class="sxs-lookup"><span data-stu-id="1d041-310">15+</span></span>                    | <span data-ttu-id="1d041-311">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-311">x64</span></span> |
| <span data-ttu-id="1d041-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1d041-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="1d041-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1d041-313">12 SP2+</span></span>                | <span data-ttu-id="1d041-314">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-314">x64</span></span> |
| <span data-ttu-id="1d041-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-315">Alpine Linux</span></span>                   |  <span data-ttu-id="1d041-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="1d041-316">3.8+</span></span>                   | <span data-ttu-id="1d041-317">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-317">x64</span></span> |

<span data-ttu-id="1d041-318">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)」(.NET Core 2.2 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1d041-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1d041-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1d041-320">.NET Core 2.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="1d041-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="1d041-321">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1d041-322">.NET Core 2.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1d041-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1d041-323">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d041-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1d041-324">OS</span><span class="sxs-lookup"><span data-stu-id="1d041-324">OS</span></span>                             |  <span data-ttu-id="1d041-325">バージョン</span><span class="sxs-lookup"><span data-stu-id="1d041-325">Version</span></span>                |  <span data-ttu-id="1d041-326">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d041-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="1d041-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="1d041-328">6、7、8</span><span class="sxs-lookup"><span data-stu-id="1d041-328">6, 7, 8</span></span>                | <span data-ttu-id="1d041-329">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-329">x64</span></span> |
| <span data-ttu-id="1d041-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="1d041-330">CentOS</span></span>                         |  <span data-ttu-id="1d041-331">7+</span><span class="sxs-lookup"><span data-stu-id="1d041-331">7+</span></span>                     | <span data-ttu-id="1d041-332">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-332">x64</span></span> |
| <span data-ttu-id="1d041-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-333">Oracle Linux</span></span>                   |  <span data-ttu-id="1d041-334">7+</span><span class="sxs-lookup"><span data-stu-id="1d041-334">7+</span></span>                     | <span data-ttu-id="1d041-335">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-335">x64</span></span> |
| <span data-ttu-id="1d041-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="1d041-336">Fedora</span></span>                         |  <span data-ttu-id="1d041-337">29+</span><span class="sxs-lookup"><span data-stu-id="1d041-337">29+</span></span>                    | <span data-ttu-id="1d041-338">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-338">x64</span></span> |
| <span data-ttu-id="1d041-339">Debian</span><span class="sxs-lookup"><span data-stu-id="1d041-339">Debian</span></span>                         |  <span data-ttu-id="1d041-340">9</span><span class="sxs-lookup"><span data-stu-id="1d041-340">9</span></span>                      | <span data-ttu-id="1d041-341">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1d041-341">x64, ARM32</span></span> |
| <span data-ttu-id="1d041-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1d041-342">Ubuntu</span></span>                         |  <span data-ttu-id="1d041-343">16.04、18.04、19.04、19.10</span><span class="sxs-lookup"><span data-stu-id="1d041-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="1d041-344">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="1d041-344">x64, ARM32</span></span> |
| <span data-ttu-id="1d041-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1d041-345">Linux Mint</span></span>                     |  <span data-ttu-id="1d041-346">17+</span><span class="sxs-lookup"><span data-stu-id="1d041-346">17+</span></span>                    | <span data-ttu-id="1d041-347">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-347">x64</span></span> |
| <span data-ttu-id="1d041-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1d041-348">openSUSE</span></span>                       |  <span data-ttu-id="1d041-349">15+</span><span class="sxs-lookup"><span data-stu-id="1d041-349">15+</span></span>                    | <span data-ttu-id="1d041-350">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-350">x64</span></span> |
| <span data-ttu-id="1d041-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1d041-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="1d041-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1d041-352">12 SP2+</span></span>                | <span data-ttu-id="1d041-353">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-353">x64</span></span> |
| <span data-ttu-id="1d041-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1d041-354">Alpine Linux</span></span>                   |  <span data-ttu-id="1d041-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="1d041-355">3.8+</span></span>                   | <span data-ttu-id="1d041-356">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-356">x64</span></span> |

<span data-ttu-id="1d041-357">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、ライフサイクル ポリシーの詳細については、「[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)」(.NET Core 2.1 でサポートされている OS バージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="1d041-358">Linux ディストリビューションの依存関係</span><span class="sxs-lookup"><span data-stu-id="1d041-358">Linux distribution dependencies</span></span>

<span data-ttu-id="1d041-359">Linux ディストリビューションによっては、追加の依存関係のインストールが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d041-360">選択した Linux ディストリビューションで、バージョンと名前が多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="1d041-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1d041-361">Ubuntu</span></span>

<span data-ttu-id="1d041-362">Ubuntu ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="1d041-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="1d041-363">liblttng-ust0</span></span>
- <span data-ttu-id="1d041-364">libcurl3 (14.x および 16.x 用)</span><span class="sxs-lookup"><span data-stu-id="1d041-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="1d041-365">libcurl4 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="1d041-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="1d041-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="1d041-366">libssl1.0.0</span></span>
- <span data-ttu-id="1d041-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="1d041-367">libkrb5-3</span></span>
- <span data-ttu-id="1d041-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="1d041-368">zlib1g</span></span>
- <span data-ttu-id="1d041-369">libicu52 (14.x 用)</span><span class="sxs-lookup"><span data-stu-id="1d041-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="1d041-370">libicu55 (16.x 用)</span><span class="sxs-lookup"><span data-stu-id="1d041-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="1d041-371">libicu57 (17.x 用)</span><span class="sxs-lookup"><span data-stu-id="1d041-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="1d041-372">libicu60 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="1d041-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="1d041-373">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="1d041-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="1d041-374">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="1d041-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="1d041-375">Ubuntu のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d041-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="1d041-376">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="1d041-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="1d041-377">詳細については、「<https://www.mono-project.com/download/stable/>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="1d041-378">CentOS と Fedora</span><span class="sxs-lookup"><span data-stu-id="1d041-378">CentOS and Fedora</span></span>

<span data-ttu-id="1d041-379">CentOS ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="1d041-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="1d041-380">lttng-ust</span></span>
- <span data-ttu-id="1d041-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="1d041-381">libcurl</span></span>
- <span data-ttu-id="1d041-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="1d041-382">openssl-libs</span></span>
- <span data-ttu-id="1d041-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="1d041-383">krb5-libs</span></span>
- <span data-ttu-id="1d041-384">libicu</span><span class="sxs-lookup"><span data-stu-id="1d041-384">libicu</span></span>
- <span data-ttu-id="1d041-385">zlib</span><span class="sxs-lookup"><span data-stu-id="1d041-385">zlib</span></span>

<span data-ttu-id="1d041-386">Fedora ユーザー:ご使用の OpenSSL のバージョンが 1.1 以降の場合は、**compat-openssl10** をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="1d041-387">.NET Core 2.0 では、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="1d041-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="1d041-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="1d041-388">libunwind</span></span>
- <span data-ttu-id="1d041-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="1d041-389">libuuid</span></span>

<span data-ttu-id="1d041-390">依存関係の詳細については、「[Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」(自己完結型 Linux アプリケーション) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d041-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="1d041-391">*System.Drawing.Common* アセンブリを使用する .NET Core アプリの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="1d041-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="1d041-392">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="1d041-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="1d041-393">CentOS と Fedora のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d041-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="1d041-394">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="1d041-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="1d041-395">詳細については、「<https://www.mono-project.com/download/stable/>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d041-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="1d041-396">.NET Core は、次の macOS のリリースでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1d041-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="1d041-397">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d041-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1d041-398">.NET Core のバージョン</span><span class="sxs-lookup"><span data-stu-id="1d041-398">.NET Core Version</span></span> | <span data-ttu-id="1d041-399">macOS</span><span class="sxs-lookup"><span data-stu-id="1d041-399">macOS</span></span>                 | <span data-ttu-id="1d041-400">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1d041-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="1d041-401">3.1</span><span class="sxs-lookup"><span data-stu-id="1d041-401">3.1</span></span>               | <span data-ttu-id="1d041-402">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="1d041-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="1d041-403">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-403">x64</span></span> | [<span data-ttu-id="1d041-404">詳細情報</span><span class="sxs-lookup"><span data-stu-id="1d041-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="1d041-405">3.0</span><span class="sxs-lookup"><span data-stu-id="1d041-405">3.0</span></span>               | <span data-ttu-id="1d041-406">High Sierra (10.13+)</span><span class="sxs-lookup"><span data-stu-id="1d041-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="1d041-407">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-407">x64</span></span> | [<span data-ttu-id="1d041-408">詳細情報</span><span class="sxs-lookup"><span data-stu-id="1d041-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="1d041-409">2.2</span><span class="sxs-lookup"><span data-stu-id="1d041-409">2.2</span></span>               | <span data-ttu-id="1d041-410">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="1d041-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="1d041-411">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-411">x64</span></span> | [<span data-ttu-id="1d041-412">詳細情報</span><span class="sxs-lookup"><span data-stu-id="1d041-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="1d041-413">2.1</span><span class="sxs-lookup"><span data-stu-id="1d041-413">2.1</span></span>               | <span data-ttu-id="1d041-414">Sierra (10.12+)</span><span class="sxs-lookup"><span data-stu-id="1d041-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="1d041-415">X64</span><span class="sxs-lookup"><span data-stu-id="1d041-415">x64</span></span> | [<span data-ttu-id="1d041-416">詳細情報</span><span class="sxs-lookup"><span data-stu-id="1d041-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a><span data-ttu-id="1d041-417">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="1d041-417">libgdiplus</span></span>

<span data-ttu-id="1d041-418">*System.Drawing.Common* アセンブリを使用する .NET Core アプリケーションでは、libgdiplus をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d041-418">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="1d041-419">libgdiplus を取得する簡単な方法は、macOS の [Homebrew ("brew")](https://brew.sh/) パッケージ マネージャーを使用することです。</span><span class="sxs-lookup"><span data-stu-id="1d041-419">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="1d041-420">*brew* をインストールしたら、端末 (コマンド) プロンプトで次のコマンドを実行して libgdiplus をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d041-420">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="1d041-421">次の手順</span><span class="sxs-lookup"><span data-stu-id="1d041-421">Next steps</span></span>

- <span data-ttu-id="1d041-422">アプリを開発して実行するには、[.NET Core SDK](sdk.md) (ランタイムを含む) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d041-422">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="1d041-423">他のユーザーが作成したアプリを実行するには、[.NET Core ランタイム](runtime.md)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d041-423">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
