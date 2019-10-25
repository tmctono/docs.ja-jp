---
title: Linux における .NET Core の前提条件
description: Linux マシンで .NET Core アプリケーションを開発、展開、および実行するために必要なサポートされている Linux のバージョンと .NET Core の依存関係。
author: leecow
ms.author: leecow
ms.date: 10/11/2019
ms.openlocfilehash: 0e798e86fcf88a1b7a67f50c2301e10ad725fad8
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521491"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="a70bd-103">Linux における .NET Core の前提条件</span><span class="sxs-lookup"><span data-stu-id="a70bd-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="a70bd-104">この記事では、Linux で .NET Core アプリケーションを開発するために必要な依存関係を示します。</span><span class="sxs-lookup"><span data-stu-id="a70bd-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="a70bd-105">後述のサポートされている Linux ディストリビューション/バージョンと依存関係は、Linux で .NET Core アプリを開発する次の 2 つの方法に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a70bd-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

- [<span data-ttu-id="a70bd-106">好みのエディターでのコマンドライン</span><span class="sxs-lookup"><span data-stu-id="a70bd-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
- [<span data-ttu-id="a70bd-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a70bd-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="a70bd-108">.NET Core SDK パッケージは、運用サーバー/環境には必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a70bd-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="a70bd-109">運用環境に展開されるアプリに必要なものは、.NET Core ランタイム パッケージだけです。</span><span class="sxs-lookup"><span data-stu-id="a70bd-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="a70bd-110">.NET Core ランタイムは自己完結型の展開の一部としてアプリと供に展開されますが、フレームワークに依存して展開されるアプリでは個別に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a70bd-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="a70bd-111">フレームワークに依存する展開と自己完結型の展開について詳しくは、「[.NET Core アプリケーションの展開](./deploying/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="a70bd-112">具体的なガイドラインについては、「[Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」(自己完結型 Linux アプリケーション) もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="a70bd-113">サポートされている Linux バージョン</span><span class="sxs-lookup"><span data-stu-id="a70bd-113">Supported Linux versions</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="a70bd-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a70bd-114">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="a70bd-115">.NET Core 3.0 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="a70bd-115">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="a70bd-116">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="a70bd-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="a70bd-117">ダウンロード リンクと詳細については、[.NET Core 3.0 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.0) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-117">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="a70bd-118">.NET Core 3.0 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a70bd-118">.NET Core 3.0 is supported on the following Linux distributions/versions):</span></span>

> [!NOTE]
> <span data-ttu-id="a70bd-119">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="a70bd-119">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a70bd-120">OS</span><span class="sxs-lookup"><span data-stu-id="a70bd-120">OS</span></span>                             | <span data-ttu-id="a70bd-121">Version</span><span class="sxs-lookup"><span data-stu-id="a70bd-121">Version</span></span>               | <span data-ttu-id="a70bd-122">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="a70bd-122">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="a70bd-123">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a70bd-123">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="a70bd-124">6+、7</span><span class="sxs-lookup"><span data-stu-id="a70bd-124">6+, 7</span></span>                 | <span data-ttu-id="a70bd-125">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-125">x64</span></span> |
| <span data-ttu-id="a70bd-126">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a70bd-126">Oracle Linux</span></span>                   | <span data-ttu-id="a70bd-127">7</span><span class="sxs-lookup"><span data-stu-id="a70bd-127">7</span></span>                     | <span data-ttu-id="a70bd-128">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-128">x64</span></span> |
| <span data-ttu-id="a70bd-129">CentOS</span><span class="sxs-lookup"><span data-stu-id="a70bd-129">CentOS</span></span>                         | <span data-ttu-id="a70bd-130">7</span><span class="sxs-lookup"><span data-stu-id="a70bd-130">7</span></span>                     | <span data-ttu-id="a70bd-131">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-131">x64</span></span> |
| <span data-ttu-id="a70bd-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="a70bd-132">Fedora</span></span>                         | <span data-ttu-id="a70bd-133">29+</span><span class="sxs-lookup"><span data-stu-id="a70bd-133">29+</span></span>                   | <span data-ttu-id="a70bd-134">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-134">x64</span></span> |
| <span data-ttu-id="a70bd-135">Debian</span><span class="sxs-lookup"><span data-stu-id="a70bd-135">Debian</span></span>                         | <span data-ttu-id="a70bd-136">9+</span><span class="sxs-lookup"><span data-stu-id="a70bd-136">9+</span></span>                    | <span data-ttu-id="a70bd-137">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="a70bd-137">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a70bd-138">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a70bd-138">Ubuntu</span></span>                         | <span data-ttu-id="a70bd-139">16.04+</span><span class="sxs-lookup"><span data-stu-id="a70bd-139">16.04+</span></span>                | <span data-ttu-id="a70bd-140">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="a70bd-140">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a70bd-141">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a70bd-141">Linux Mint</span></span>                     | <span data-ttu-id="a70bd-142">18+</span><span class="sxs-lookup"><span data-stu-id="a70bd-142">18+</span></span>                   | <span data-ttu-id="a70bd-143">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-143">x64</span></span> |
| <span data-ttu-id="a70bd-144">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a70bd-144">openSUSE</span></span>                       | <span data-ttu-id="a70bd-145">15+</span><span class="sxs-lookup"><span data-stu-id="a70bd-145">15+</span></span>                   | <span data-ttu-id="a70bd-146">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-146">x64</span></span> |
| <span data-ttu-id="a70bd-147">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a70bd-147">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="a70bd-148">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a70bd-148">12 SP2+</span></span>               | <span data-ttu-id="a70bd-149">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-149">x64</span></span> |
| <span data-ttu-id="a70bd-150">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a70bd-150">Alpine Linux</span></span>                   | <span data-ttu-id="a70bd-151">3.8+</span><span class="sxs-lookup"><span data-stu-id="a70bd-151">3.8+</span></span>                  | <span data-ttu-id="a70bd-152">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="a70bd-152">x64, ARM64</span></span> |

<span data-ttu-id="a70bd-153">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 3.0 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-153">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="a70bd-154">ARM64 で .NET Core 3.0 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」 (Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-154">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="a70bd-155">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a70bd-155">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="a70bd-156">.NET Core 2.2 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="a70bd-156">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="a70bd-157">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="a70bd-157">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a70bd-158">ダウンロード リンクと詳細については、[.NET Core 2.2 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.2) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-158">For download links and more information, see [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2).</span></span>

<span data-ttu-id="a70bd-159">.NET Core 2.2 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a70bd-159">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="a70bd-160">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="a70bd-160">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a70bd-161">OS</span><span class="sxs-lookup"><span data-stu-id="a70bd-161">OS</span></span>                             |  <span data-ttu-id="a70bd-162">Version</span><span class="sxs-lookup"><span data-stu-id="a70bd-162">Version</span></span>                |  <span data-ttu-id="a70bd-163">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="a70bd-163">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="a70bd-164">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a70bd-164">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="a70bd-165">6、7</span><span class="sxs-lookup"><span data-stu-id="a70bd-165">6, 7</span></span>                   | <span data-ttu-id="a70bd-166">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-166">x64</span></span> |
| <span data-ttu-id="a70bd-167">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a70bd-167">Oracle Linux</span></span>                   |  <span data-ttu-id="a70bd-168">7</span><span class="sxs-lookup"><span data-stu-id="a70bd-168">7</span></span>                      | <span data-ttu-id="a70bd-169">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-169">x64</span></span> |
| <span data-ttu-id="a70bd-170">CentOS</span><span class="sxs-lookup"><span data-stu-id="a70bd-170">CentOS</span></span>                         |  <span data-ttu-id="a70bd-171">7</span><span class="sxs-lookup"><span data-stu-id="a70bd-171">7</span></span>                      | <span data-ttu-id="a70bd-172">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-172">x64</span></span> |
| <span data-ttu-id="a70bd-173">Fedora</span><span class="sxs-lookup"><span data-stu-id="a70bd-173">Fedora</span></span>                         |  <span data-ttu-id="a70bd-174">29、30</span><span class="sxs-lookup"><span data-stu-id="a70bd-174">29, 30</span></span>                 | <span data-ttu-id="a70bd-175">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-175">x64</span></span> |
| <span data-ttu-id="a70bd-176">Debian</span><span class="sxs-lookup"><span data-stu-id="a70bd-176">Debian</span></span>                         |  <span data-ttu-id="a70bd-177">9</span><span class="sxs-lookup"><span data-stu-id="a70bd-177">9</span></span>                      | <span data-ttu-id="a70bd-178">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a70bd-178">x64, ARM32</span></span> |
| <span data-ttu-id="a70bd-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a70bd-179">Ubuntu</span></span>                         |  <span data-ttu-id="a70bd-180">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="a70bd-180">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="a70bd-181">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a70bd-181">x64, ARM32</span></span> |
| <span data-ttu-id="a70bd-182">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a70bd-182">Linux Mint</span></span>                     |  <span data-ttu-id="a70bd-183">17、18</span><span class="sxs-lookup"><span data-stu-id="a70bd-183">17, 18</span></span>                 | <span data-ttu-id="a70bd-184">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-184">x64</span></span> |
| <span data-ttu-id="a70bd-185">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a70bd-185">openSUSE</span></span>                       |  <span data-ttu-id="a70bd-186">15+</span><span class="sxs-lookup"><span data-stu-id="a70bd-186">15+</span></span>                    | <span data-ttu-id="a70bd-187">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-187">x64</span></span> |
| <span data-ttu-id="a70bd-188">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a70bd-188">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="a70bd-189">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a70bd-189">12 SP2+</span></span>                | <span data-ttu-id="a70bd-190">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-190">x64</span></span> |
| <span data-ttu-id="a70bd-191">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a70bd-191">Alpine Linux</span></span>                   |  <span data-ttu-id="a70bd-192">3.7+</span><span class="sxs-lookup"><span data-stu-id="a70bd-192">3.7+</span></span>                   | <span data-ttu-id="a70bd-193">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-193">x64</span></span> |

<span data-ttu-id="a70bd-194">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 2.2 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-194">See [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a70bd-195">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a70bd-195">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="a70bd-196">.NET Core 2.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="a70bd-196">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="a70bd-197">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="a70bd-197">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a70bd-198">ダウンロード リンクと詳細については、[.NET Core 2.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.1) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-198">For download links and more information, see [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="a70bd-199">.NET Core 2.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a70bd-199">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

| <span data-ttu-id="a70bd-200">OS</span><span class="sxs-lookup"><span data-stu-id="a70bd-200">OS</span></span>                             |  <span data-ttu-id="a70bd-201">Version</span><span class="sxs-lookup"><span data-stu-id="a70bd-201">Version</span></span>                |  <span data-ttu-id="a70bd-202">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="a70bd-202">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="a70bd-203">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a70bd-203">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="a70bd-204">6、7、8</span><span class="sxs-lookup"><span data-stu-id="a70bd-204">6, 7, 8</span></span>                | <span data-ttu-id="a70bd-205">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-205">x64</span></span> |
| <span data-ttu-id="a70bd-206">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a70bd-206">Oracle Linux</span></span>                   |  <span data-ttu-id="a70bd-207">7</span><span class="sxs-lookup"><span data-stu-id="a70bd-207">7</span></span>                      | <span data-ttu-id="a70bd-208">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-208">x64</span></span> |
| <span data-ttu-id="a70bd-209">CentOS</span><span class="sxs-lookup"><span data-stu-id="a70bd-209">CentOS</span></span>                         |  <span data-ttu-id="a70bd-210">7</span><span class="sxs-lookup"><span data-stu-id="a70bd-210">7</span></span>                      | <span data-ttu-id="a70bd-211">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-211">x64</span></span> |
| <span data-ttu-id="a70bd-212">Fedora</span><span class="sxs-lookup"><span data-stu-id="a70bd-212">Fedora</span></span>                         |  <span data-ttu-id="a70bd-213">29、30</span><span class="sxs-lookup"><span data-stu-id="a70bd-213">29, 30</span></span>                 | <span data-ttu-id="a70bd-214">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-214">x64</span></span> |
| <span data-ttu-id="a70bd-215">Debian</span><span class="sxs-lookup"><span data-stu-id="a70bd-215">Debian</span></span>                         |  <span data-ttu-id="a70bd-216">9</span><span class="sxs-lookup"><span data-stu-id="a70bd-216">9</span></span>                      | <span data-ttu-id="a70bd-217">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a70bd-217">x64, ARM32</span></span> |
| <span data-ttu-id="a70bd-218">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a70bd-218">Ubuntu</span></span>                         |  <span data-ttu-id="a70bd-219">16.04、18.04、19.04</span><span class="sxs-lookup"><span data-stu-id="a70bd-219">16.04, 18.04, 19.04</span></span>    | <span data-ttu-id="a70bd-220">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="a70bd-220">x64, ARM32</span></span> |
| <span data-ttu-id="a70bd-221">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a70bd-221">Linux Mint</span></span>                     |  <span data-ttu-id="a70bd-222">17、18</span><span class="sxs-lookup"><span data-stu-id="a70bd-222">17, 18</span></span>                 | <span data-ttu-id="a70bd-223">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-223">x64</span></span> |
| <span data-ttu-id="a70bd-224">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a70bd-224">openSUSE</span></span>                       |  <span data-ttu-id="a70bd-225">42.3+</span><span class="sxs-lookup"><span data-stu-id="a70bd-225">42.3+</span></span>                  | <span data-ttu-id="a70bd-226">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-226">x64</span></span> |
| <span data-ttu-id="a70bd-227">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a70bd-227">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="a70bd-228">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a70bd-228">12 SP2+</span></span>                | <span data-ttu-id="a70bd-229">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-229">x64</span></span> |
| <span data-ttu-id="a70bd-230">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a70bd-230">Alpine Linux</span></span>                   |  <span data-ttu-id="a70bd-231">3.7+</span><span class="sxs-lookup"><span data-stu-id="a70bd-231">3.7+</span></span>                   | <span data-ttu-id="a70bd-232">X64</span><span class="sxs-lookup"><span data-stu-id="a70bd-232">x64</span></span> |

<span data-ttu-id="a70bd-233">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 2.1 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-233">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="a70bd-234">Linux ディストリビューションの依存関係</span><span class="sxs-lookup"><span data-stu-id="a70bd-234">Linux distribution dependencies</span></span>

<span data-ttu-id="a70bd-235">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a70bd-235">The following are intended to be examples.</span></span> <span data-ttu-id="a70bd-236">選択した Linux ディストリビューションで、バージョンと名前が多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a70bd-236">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="a70bd-237">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a70bd-237">Ubuntu</span></span>

<span data-ttu-id="a70bd-238">Ubuntu ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a70bd-238">Ubuntu distributions require the following libraries installed:</span></span>

- <span data-ttu-id="a70bd-239">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="a70bd-239">liblttng-ust0</span></span>
- <span data-ttu-id="a70bd-240">libcurl3 (14.x および 16.x 用)</span><span class="sxs-lookup"><span data-stu-id="a70bd-240">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="a70bd-241">libcurl4 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="a70bd-241">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="a70bd-242">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="a70bd-242">libssl1.0.0</span></span>
- <span data-ttu-id="a70bd-243">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="a70bd-243">libkrb5-3</span></span>
- <span data-ttu-id="a70bd-244">zlib1g</span><span class="sxs-lookup"><span data-stu-id="a70bd-244">zlib1g</span></span>
- <span data-ttu-id="a70bd-245">libicu52 (14.x 用)</span><span class="sxs-lookup"><span data-stu-id="a70bd-245">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="a70bd-246">libicu55 (16.x 用)</span><span class="sxs-lookup"><span data-stu-id="a70bd-246">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="a70bd-247">libicu57 (17.x 用)</span><span class="sxs-lookup"><span data-stu-id="a70bd-247">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="a70bd-248">libicu60 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="a70bd-248">libicu60 (for 18.x)</span></span>

<span data-ttu-id="a70bd-249">.NET Core 2.1 より前のバージョンには、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="a70bd-249">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

- <span data-ttu-id="a70bd-250">libunwind8</span><span class="sxs-lookup"><span data-stu-id="a70bd-250">libunwind8</span></span>
- <span data-ttu-id="a70bd-251">libuuid1</span><span class="sxs-lookup"><span data-stu-id="a70bd-251">libuuid1</span></span>

<span data-ttu-id="a70bd-252">*System.Drawing.Common* アセンブリを使用する .NET Core アプリケーションの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="a70bd-252">For .NET Core applications that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

* <span data-ttu-id="a70bd-253">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="a70bd-253">libgdiplus (version 6.0.1 or later)</span></span>

> [!NOTE]
> <span data-ttu-id="a70bd-254">Ubuntu のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a70bd-254">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="a70bd-255">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="a70bd-255">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="a70bd-256">詳細については、<https://www.mono-project.com/download/stable/> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-256">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="a70bd-257">CentOS と Fedora</span><span class="sxs-lookup"><span data-stu-id="a70bd-257">CentOS and Fedora</span></span>

<span data-ttu-id="a70bd-258">CentOS ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a70bd-258">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="a70bd-259">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="a70bd-259">lttng-ust</span></span>
- <span data-ttu-id="a70bd-260">libcurl</span><span class="sxs-lookup"><span data-stu-id="a70bd-260">libcurl</span></span>
- <span data-ttu-id="a70bd-261">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="a70bd-261">openssl-libs</span></span>
- <span data-ttu-id="a70bd-262">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="a70bd-262">krb5-libs</span></span>
- <span data-ttu-id="a70bd-263">libicu</span><span class="sxs-lookup"><span data-stu-id="a70bd-263">libicu</span></span>
- <span data-ttu-id="a70bd-264">zlib</span><span class="sxs-lookup"><span data-stu-id="a70bd-264">zlib</span></span>

<span data-ttu-id="a70bd-265">Fedora ユーザー:ご使用の openssl のバージョンが 1.1 以降の場合は、compat-openssl10 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a70bd-265">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="a70bd-266">.NET Core 2.1 より前のバージョンには、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="a70bd-266">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

- <span data-ttu-id="a70bd-267">libunwind</span><span class="sxs-lookup"><span data-stu-id="a70bd-267">libunwind</span></span>
- <span data-ttu-id="a70bd-268">libuuid</span><span class="sxs-lookup"><span data-stu-id="a70bd-268">libuuid</span></span>

<span data-ttu-id="a70bd-269">依存関係の詳細については、「[Self-contained Linux applications (自己完結型 Linux アプリケーション)](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-269">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="a70bd-270">*System.Drawing.Common* アセンブリを使用する .NET Core アプリケーションの場合は、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="a70bd-270">For .NET Core applications that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

* <span data-ttu-id="a70bd-271">libgdiplus (バージョン 6.0.1 以降)</span><span class="sxs-lookup"><span data-stu-id="a70bd-271">libgdiplus (version 6.0.1 or later)</span></span>

> [!NOTE]
> <span data-ttu-id="a70bd-272">CentOS と Fedora のほとんどのバージョンには、以前のバージョンの libgdiplus が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a70bd-272">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="a70bd-273">新しいバージョンの libgdiplus をインストールするには、システムに Mono リポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="a70bd-273">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="a70bd-274">詳細については、<https://www.mono-project.com/download/stable/> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-274">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="a70bd-275">ネイティブ インストーラーを使用した .NET Core の依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="a70bd-275">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="a70bd-276">.NET Core ネイティブ インストーラーは、サポートされている Linux ディストリビューション/バージョンに利用できます。</span><span class="sxs-lookup"><span data-stu-id="a70bd-276">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="a70bd-277">このネイティブ インストーラーは、サーバーへの admin (sudo) アクセスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="a70bd-277">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="a70bd-278">ネイティブ インストーラーを使用することの利点は、.NET Core ネイティブの依存関係がすべてインストールされることです。</span><span class="sxs-lookup"><span data-stu-id="a70bd-278">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="a70bd-279">また、ネイティブ インストーラーでは、.NET Core SDK もシステム全体にインストールします。</span><span class="sxs-lookup"><span data-stu-id="a70bd-279">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="a70bd-280">Linux では、2 つのインストーラー パッケージから選択できます。</span><span class="sxs-lookup"><span data-stu-id="a70bd-280">On Linux, there are two installer package choices:</span></span>

- <span data-ttu-id="a70bd-281">フィードベースのパッケージ マネージャー (Ubuntu では apt-get、CentOS/RHEL では yum など) を使用する</span><span class="sxs-lookup"><span data-stu-id="a70bd-281">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
- <span data-ttu-id="a70bd-282">パッケージ自体 (DEB または RPM) を使用する</span><span class="sxs-lookup"><span data-stu-id="a70bd-282">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="a70bd-283">.NET Core インストーラー スクリプトを使用したスクリプトのインストール</span><span class="sxs-lookup"><span data-stu-id="a70bd-283">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="a70bd-284">[dotnet-install スクリプト](./tools/dotnet-install-script.md)は、CLI ツールチェーンと共有ランタイムの非管理者インストールを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a70bd-284">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="a70bd-285">このスクリプトは <https://dot.net/v1/dotnet-install.sh> からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a70bd-285">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="a70bd-286">スクリプトは、既定で最新の "LTS" のバージョン (現在は .NET Core 1.1) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a70bd-286">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="a70bd-287">NET Core 2.1 をインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="a70bd-287">To install .NET Core 2.1, run the script with the following switch:</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="a70bd-288">インストーラーの bash スクリプトは、自動化シナリオと管理者以外のインストールで使用されます。</span><span class="sxs-lookup"><span data-stu-id="a70bd-288">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="a70bd-289">このスクリプトは、PowerShell のスイッチも読み取るので、Linux/OS X システムのスクリプトで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a70bd-289">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="a70bd-290">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a70bd-290">Troubleshoot</span></span>

<span data-ttu-id="a70bd-291">サポートされている Linux ディストリビューション/バージョンへの .NET Core のインストールに問題がある場合は、インストールしているディストリビューション/バージョンに関する以下のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a70bd-291">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

- [<span data-ttu-id="a70bd-292">.NET Core 3.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="a70bd-292">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
- [<span data-ttu-id="a70bd-293">.NET Core 2.2 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="a70bd-293">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
- [<span data-ttu-id="a70bd-294">.NET Core 2.1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="a70bd-294">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
- [<span data-ttu-id="a70bd-295">.NET Core 1.1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="a70bd-295">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
- [<span data-ttu-id="a70bd-296">.NET Core 1.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="a70bd-296">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
