---
title: Linux における .NET Core の前提条件
description: Linux マシンで .NET Core アプリケーションを開発、展開、および実行するために必要なサポートされている Linux のバージョンと .NET Core の依存関係。
author: leecow
ms.author: leecow
ms.date: 09/25/2019
ms.openlocfilehash: 4c5d79459c9d69111ca6452d9305f0deb37212b8
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591697"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="49619-103">Linux における .NET Core の前提条件</span><span class="sxs-lookup"><span data-stu-id="49619-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="49619-104">この記事では、Linux で .NET Core アプリケーションを開発するために必要な依存関係を示します。</span><span class="sxs-lookup"><span data-stu-id="49619-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="49619-105">後述のサポートされている Linux ディストリビューション/バージョンと依存関係は、Linux で .NET Core アプリを開発する次の 2 つの方法に適用されます。</span><span class="sxs-lookup"><span data-stu-id="49619-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="49619-106">好みのエディターでのコマンドライン</span><span class="sxs-lookup"><span data-stu-id="49619-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="49619-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="49619-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="49619-108">.NET Core SDK パッケージは、運用サーバー/環境には必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49619-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="49619-109">運用環境に展開されるアプリに必要なものは、.NET Core ランタイム パッケージだけです。</span><span class="sxs-lookup"><span data-stu-id="49619-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="49619-110">.NET Core ランタイムは自己完結型の展開の一部としてアプリと供に展開されますが、フレームワークに依存して展開されるアプリでは個別に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49619-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="49619-111">フレームワークに依存する展開と自己完結型の展開について詳しくは、「[.NET Core アプリケーションの展開](./deploying/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49619-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="49619-112">具体的なガイドラインについては、「[Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」(自己完結型 Linux アプリケーション) もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49619-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="49619-113">サポートされている Linux バージョン</span><span class="sxs-lookup"><span data-stu-id="49619-113">Supported Linux versions</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="49619-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49619-114">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="49619-115">.NET Core 3.0 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="49619-115">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="49619-116">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="49619-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="49619-117">ダウンロード リンクと詳細については、[.NET Core 3.0 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.0) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49619-117">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="49619-118">.NET Core 3.0 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="49619-118">.NET Core 3.0 is supported on the following Linux distributions/versions):</span></span>

> [!NOTE]
> <span data-ttu-id="49619-119">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="49619-119">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="49619-120">OS</span><span class="sxs-lookup"><span data-stu-id="49619-120">OS</span></span>                             | <span data-ttu-id="49619-121">Version</span><span class="sxs-lookup"><span data-stu-id="49619-121">Version</span></span>               | <span data-ttu-id="49619-122">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="49619-122">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="49619-123">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="49619-123">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="49619-124">6+、7</span><span class="sxs-lookup"><span data-stu-id="49619-124">6+, 7</span></span>                 | <span data-ttu-id="49619-125">X64</span><span class="sxs-lookup"><span data-stu-id="49619-125">x64</span></span> |
| <span data-ttu-id="49619-126">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="49619-126">Oracle Linux</span></span>                   | <span data-ttu-id="49619-127">7</span><span class="sxs-lookup"><span data-stu-id="49619-127">7</span></span>                     | <span data-ttu-id="49619-128">X64</span><span class="sxs-lookup"><span data-stu-id="49619-128">x64</span></span> |
| <span data-ttu-id="49619-129">CentOS</span><span class="sxs-lookup"><span data-stu-id="49619-129">CentOS</span></span>                         | <span data-ttu-id="49619-130">7</span><span class="sxs-lookup"><span data-stu-id="49619-130">7</span></span>                     | <span data-ttu-id="49619-131">X64</span><span class="sxs-lookup"><span data-stu-id="49619-131">x64</span></span> |
| <span data-ttu-id="49619-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="49619-132">Fedora</span></span>                         | <span data-ttu-id="49619-133">29+</span><span class="sxs-lookup"><span data-stu-id="49619-133">29+</span></span>                   | <span data-ttu-id="49619-134">X64</span><span class="sxs-lookup"><span data-stu-id="49619-134">x64</span></span> |
| <span data-ttu-id="49619-135">Debian</span><span class="sxs-lookup"><span data-stu-id="49619-135">Debian</span></span>                         | <span data-ttu-id="49619-136">9+</span><span class="sxs-lookup"><span data-stu-id="49619-136">9+</span></span>                    | <span data-ttu-id="49619-137">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="49619-137">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="49619-138">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="49619-138">Ubuntu</span></span>                         | <span data-ttu-id="49619-139">16.04+</span><span class="sxs-lookup"><span data-stu-id="49619-139">16.04+</span></span>                | <span data-ttu-id="49619-140">x64、ARM32、ARM64</span><span class="sxs-lookup"><span data-stu-id="49619-140">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="49619-141">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="49619-141">Linux Mint</span></span>                     | <span data-ttu-id="49619-142">18+</span><span class="sxs-lookup"><span data-stu-id="49619-142">18+</span></span>                   | <span data-ttu-id="49619-143">X64</span><span class="sxs-lookup"><span data-stu-id="49619-143">x64</span></span> |
| <span data-ttu-id="49619-144">openSUSE</span><span class="sxs-lookup"><span data-stu-id="49619-144">openSUSE</span></span>                       | <span data-ttu-id="49619-145">15+</span><span class="sxs-lookup"><span data-stu-id="49619-145">15+</span></span>                   | <span data-ttu-id="49619-146">X64</span><span class="sxs-lookup"><span data-stu-id="49619-146">x64</span></span> |
| <span data-ttu-id="49619-147">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="49619-147">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="49619-148">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="49619-148">12 SP2+</span></span>               | <span data-ttu-id="49619-149">X64</span><span class="sxs-lookup"><span data-stu-id="49619-149">x64</span></span> |
| <span data-ttu-id="49619-150">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="49619-150">Alpine Linux</span></span>                   | <span data-ttu-id="49619-151">3.8+</span><span class="sxs-lookup"><span data-stu-id="49619-151">3.8+</span></span>                  | <span data-ttu-id="49619-152">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="49619-152">x64, ARM64</span></span> |

<span data-ttu-id="49619-153">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 3.0 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49619-153">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="49619-154">ARM64 で .NET Core 3.0 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」 (Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49619-154">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="49619-155">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="49619-155">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="49619-156">.NET Core 2.2 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="49619-156">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="49619-157">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="49619-157">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="49619-158">ダウンロード リンクと詳細については、[.NET Core 2.2 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.2) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49619-158">For download links and more information, see [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2).</span></span>

<span data-ttu-id="49619-159">.NET Core 2.2 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="49619-159">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="49619-160">`+` 記号は、最小バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="49619-160">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="49619-161">OS</span><span class="sxs-lookup"><span data-stu-id="49619-161">OS</span></span>                             |  <span data-ttu-id="49619-162">Version</span><span class="sxs-lookup"><span data-stu-id="49619-162">Version</span></span>                |  <span data-ttu-id="49619-163">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="49619-163">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="49619-164">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="49619-164">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="49619-165">6、7</span><span class="sxs-lookup"><span data-stu-id="49619-165">6, 7</span></span>                   | <span data-ttu-id="49619-166">X64</span><span class="sxs-lookup"><span data-stu-id="49619-166">x64</span></span> |
| <span data-ttu-id="49619-167">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="49619-167">Oracle Linux</span></span>                   |  <span data-ttu-id="49619-168">7</span><span class="sxs-lookup"><span data-stu-id="49619-168">7</span></span>                      | <span data-ttu-id="49619-169">X64</span><span class="sxs-lookup"><span data-stu-id="49619-169">x64</span></span> |
| <span data-ttu-id="49619-170">CentOS</span><span class="sxs-lookup"><span data-stu-id="49619-170">CentOS</span></span>                         |  <span data-ttu-id="49619-171">7</span><span class="sxs-lookup"><span data-stu-id="49619-171">7</span></span>                      | <span data-ttu-id="49619-172">X64</span><span class="sxs-lookup"><span data-stu-id="49619-172">x64</span></span> |
| <span data-ttu-id="49619-173">Fedora</span><span class="sxs-lookup"><span data-stu-id="49619-173">Fedora</span></span>                         |  <span data-ttu-id="49619-174">29、30</span><span class="sxs-lookup"><span data-stu-id="49619-174">29, 30</span></span>                 | <span data-ttu-id="49619-175">X64</span><span class="sxs-lookup"><span data-stu-id="49619-175">x64</span></span> |
| <span data-ttu-id="49619-176">Debian</span><span class="sxs-lookup"><span data-stu-id="49619-176">Debian</span></span>                         |  <span data-ttu-id="49619-177">9</span><span class="sxs-lookup"><span data-stu-id="49619-177">9</span></span>                      | <span data-ttu-id="49619-178">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="49619-178">x64, ARM32</span></span> |
| <span data-ttu-id="49619-179">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="49619-179">Ubuntu</span></span>                         |  <span data-ttu-id="49619-180">16.04、18.04、18.10</span><span class="sxs-lookup"><span data-stu-id="49619-180">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="49619-181">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="49619-181">x64, ARM32</span></span> |
| <span data-ttu-id="49619-182">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="49619-182">Linux Mint</span></span>                     |  <span data-ttu-id="49619-183">17、18</span><span class="sxs-lookup"><span data-stu-id="49619-183">17, 18</span></span>                 | <span data-ttu-id="49619-184">X64</span><span class="sxs-lookup"><span data-stu-id="49619-184">x64</span></span> |
| <span data-ttu-id="49619-185">openSUSE</span><span class="sxs-lookup"><span data-stu-id="49619-185">openSUSE</span></span>                       |  <span data-ttu-id="49619-186">15+</span><span class="sxs-lookup"><span data-stu-id="49619-186">15+</span></span>                    | <span data-ttu-id="49619-187">X64</span><span class="sxs-lookup"><span data-stu-id="49619-187">x64</span></span> |
| <span data-ttu-id="49619-188">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="49619-188">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="49619-189">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="49619-189">12 SP2+</span></span>                | <span data-ttu-id="49619-190">X64</span><span class="sxs-lookup"><span data-stu-id="49619-190">x64</span></span> |
| <span data-ttu-id="49619-191">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="49619-191">Alpine Linux</span></span>                   |  <span data-ttu-id="49619-192">3.7+</span><span class="sxs-lookup"><span data-stu-id="49619-192">3.7+</span></span>                   | <span data-ttu-id="49619-193">X64</span><span class="sxs-lookup"><span data-stu-id="49619-193">x64</span></span> |

<span data-ttu-id="49619-194">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 2.2 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49619-194">See [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="49619-195">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="49619-195">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="49619-196">.NET Core 2.1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="49619-196">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="49619-197">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="49619-197">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="49619-198">ダウンロード リンクと詳細については、[.NET Core 2.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.1) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49619-198">For download links and more information, see [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="49619-199">.NET Core 2.1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="49619-199">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

| <span data-ttu-id="49619-200">OS</span><span class="sxs-lookup"><span data-stu-id="49619-200">OS</span></span>                             |  <span data-ttu-id="49619-201">Version</span><span class="sxs-lookup"><span data-stu-id="49619-201">Version</span></span>                |  <span data-ttu-id="49619-202">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="49619-202">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="49619-203">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="49619-203">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="49619-204">6、7、8</span><span class="sxs-lookup"><span data-stu-id="49619-204">6, 7, 8</span></span>                | <span data-ttu-id="49619-205">X64</span><span class="sxs-lookup"><span data-stu-id="49619-205">x64</span></span> |
| <span data-ttu-id="49619-206">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="49619-206">Oracle Linux</span></span>                   |  <span data-ttu-id="49619-207">7</span><span class="sxs-lookup"><span data-stu-id="49619-207">7</span></span>                      | <span data-ttu-id="49619-208">X64</span><span class="sxs-lookup"><span data-stu-id="49619-208">x64</span></span> |
| <span data-ttu-id="49619-209">CentOS</span><span class="sxs-lookup"><span data-stu-id="49619-209">CentOS</span></span>                         |  <span data-ttu-id="49619-210">7</span><span class="sxs-lookup"><span data-stu-id="49619-210">7</span></span>                      | <span data-ttu-id="49619-211">X64</span><span class="sxs-lookup"><span data-stu-id="49619-211">x64</span></span> |
| <span data-ttu-id="49619-212">Fedora</span><span class="sxs-lookup"><span data-stu-id="49619-212">Fedora</span></span>                         |  <span data-ttu-id="49619-213">29、30</span><span class="sxs-lookup"><span data-stu-id="49619-213">29, 30</span></span>                 | <span data-ttu-id="49619-214">X64</span><span class="sxs-lookup"><span data-stu-id="49619-214">x64</span></span> |
| <span data-ttu-id="49619-215">Debian</span><span class="sxs-lookup"><span data-stu-id="49619-215">Debian</span></span>                         |  <span data-ttu-id="49619-216">9</span><span class="sxs-lookup"><span data-stu-id="49619-216">9</span></span>                      | <span data-ttu-id="49619-217">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="49619-217">x64, ARM32</span></span> |
| <span data-ttu-id="49619-218">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="49619-218">Ubuntu</span></span>                         |  <span data-ttu-id="49619-219">16.04、18.04、19.04</span><span class="sxs-lookup"><span data-stu-id="49619-219">16.04, 18.04, 19.04</span></span>    | <span data-ttu-id="49619-220">x64、ARM32</span><span class="sxs-lookup"><span data-stu-id="49619-220">x64, ARM32</span></span> |
| <span data-ttu-id="49619-221">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="49619-221">Linux Mint</span></span>                     |  <span data-ttu-id="49619-222">17、18</span><span class="sxs-lookup"><span data-stu-id="49619-222">17, 18</span></span>                 | <span data-ttu-id="49619-223">X64</span><span class="sxs-lookup"><span data-stu-id="49619-223">x64</span></span> |
| <span data-ttu-id="49619-224">openSUSE</span><span class="sxs-lookup"><span data-stu-id="49619-224">openSUSE</span></span>                       |  <span data-ttu-id="49619-225">42.3+</span><span class="sxs-lookup"><span data-stu-id="49619-225">42.3+</span></span>                  | <span data-ttu-id="49619-226">X64</span><span class="sxs-lookup"><span data-stu-id="49619-226">x64</span></span> |
| <span data-ttu-id="49619-227">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="49619-227">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="49619-228">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="49619-228">12 SP2+</span></span>                | <span data-ttu-id="49619-229">X64</span><span class="sxs-lookup"><span data-stu-id="49619-229">x64</span></span> |
| <span data-ttu-id="49619-230">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="49619-230">Alpine Linux</span></span>                   |  <span data-ttu-id="49619-231">3.7+</span><span class="sxs-lookup"><span data-stu-id="49619-231">3.7+</span></span>                   | <span data-ttu-id="49619-232">X64</span><span class="sxs-lookup"><span data-stu-id="49619-232">x64</span></span> |

<span data-ttu-id="49619-233">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 2.1 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49619-233">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="49619-234">Linux ディストリビューションの依存関係</span><span class="sxs-lookup"><span data-stu-id="49619-234">Linux distribution dependencies</span></span>

<span data-ttu-id="49619-235">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="49619-235">The following are intended to be examples.</span></span> <span data-ttu-id="49619-236">選択した Linux ディストリビューションで、バージョンと名前が多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="49619-236">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="49619-237">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="49619-237">Ubuntu</span></span>

<span data-ttu-id="49619-238">Ubuntu ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="49619-238">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="49619-239">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="49619-239">liblttng-ust0</span></span>
* <span data-ttu-id="49619-240">libcurl3 (14.x および 16.x 用)</span><span class="sxs-lookup"><span data-stu-id="49619-240">libcurl3 (for 14.x and 16.x)</span></span>
* <span data-ttu-id="49619-241">libcurl4 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="49619-241">libcurl4 (for 18.x)</span></span>
* <span data-ttu-id="49619-242">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="49619-242">libssl1.0.0</span></span>
* <span data-ttu-id="49619-243">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="49619-243">libkrb5-3</span></span>
* <span data-ttu-id="49619-244">zlib1g</span><span class="sxs-lookup"><span data-stu-id="49619-244">zlib1g</span></span>
* <span data-ttu-id="49619-245">libicu52 (14.x 用)</span><span class="sxs-lookup"><span data-stu-id="49619-245">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="49619-246">libicu55 (16.x 用)</span><span class="sxs-lookup"><span data-stu-id="49619-246">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="49619-247">libicu57 (17.x 用)</span><span class="sxs-lookup"><span data-stu-id="49619-247">libicu57 (for 17.x)</span></span>
* <span data-ttu-id="49619-248">libicu60 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="49619-248">libicu60 (for 18.x)</span></span>

<span data-ttu-id="49619-249">.NET Core 2.1 より前のバージョンには、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="49619-249">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="49619-250">libunwind8</span><span class="sxs-lookup"><span data-stu-id="49619-250">libunwind8</span></span>
* <span data-ttu-id="49619-251">libuuid1</span><span class="sxs-lookup"><span data-stu-id="49619-251">libuuid1</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="49619-252">CentOS と Fedora</span><span class="sxs-lookup"><span data-stu-id="49619-252">CentOS and Fedora</span></span>

<span data-ttu-id="49619-253">CentOS ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="49619-253">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="49619-254">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="49619-254">lttng-ust</span></span>
* <span data-ttu-id="49619-255">libcurl</span><span class="sxs-lookup"><span data-stu-id="49619-255">libcurl</span></span>
* <span data-ttu-id="49619-256">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="49619-256">openssl-libs</span></span>
* <span data-ttu-id="49619-257">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="49619-257">krb5-libs</span></span>
* <span data-ttu-id="49619-258">libicu</span><span class="sxs-lookup"><span data-stu-id="49619-258">libicu</span></span>
* <span data-ttu-id="49619-259">zlib</span><span class="sxs-lookup"><span data-stu-id="49619-259">zlib</span></span>

<span data-ttu-id="49619-260">Fedora ユーザー:ご使用の openssl のバージョンが 1.1 以降の場合は、compat-openssl10 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49619-260">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="49619-261">.NET Core 2.1 より前のバージョンには、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="49619-261">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="49619-262">libunwind</span><span class="sxs-lookup"><span data-stu-id="49619-262">libunwind</span></span>
* <span data-ttu-id="49619-263">libuuid</span><span class="sxs-lookup"><span data-stu-id="49619-263">libuuid</span></span>

<span data-ttu-id="49619-264">依存関係の詳細については、「[Self-contained Linux applications (自己完結型 Linux アプリケーション)](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49619-264">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="49619-265">ネイティブ インストーラーを使用した .NET Core の依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="49619-265">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="49619-266">.NET Core ネイティブ インストーラーは、サポートされている Linux ディストリビューション/バージョンに利用できます。</span><span class="sxs-lookup"><span data-stu-id="49619-266">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="49619-267">このネイティブ インストーラーは、サーバーへの admin (sudo) アクセスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="49619-267">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="49619-268">ネイティブ インストーラーを使用することの利点は、.NET Core ネイティブの依存関係がすべてインストールされることです。</span><span class="sxs-lookup"><span data-stu-id="49619-268">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="49619-269">また、ネイティブ インストーラーでは、.NET Core SDK もシステム全体にインストールします。</span><span class="sxs-lookup"><span data-stu-id="49619-269">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="49619-270">Linux では、2 つのインストーラー パッケージから選択できます。</span><span class="sxs-lookup"><span data-stu-id="49619-270">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="49619-271">フィードベースのパッケージ マネージャー (Ubuntu では apt-get、CentOS/RHEL では yum など) を使用する</span><span class="sxs-lookup"><span data-stu-id="49619-271">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="49619-272">パッケージ自体 (DEB または RPM) を使用する</span><span class="sxs-lookup"><span data-stu-id="49619-272">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="49619-273">.NET Core インストーラー スクリプトを使用したスクリプトのインストール</span><span class="sxs-lookup"><span data-stu-id="49619-273">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="49619-274">[dotnet-install スクリプト](./tools/dotnet-install-script.md)は、CLI ツールチェーンと共有ランタイムの非管理者インストールを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="49619-274">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="49619-275">このスクリプトは <https://dot.net/v1/dotnet-install.sh> からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="49619-275">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="49619-276">スクリプトは、既定で最新の "LTS" のバージョン (現在は .NET Core 1.1) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="49619-276">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="49619-277">NET Core 2.1 をインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="49619-277">To install .NET Core 2.1, run the script with the following switch:</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="49619-278">インストーラーの bash スクリプトは、自動化シナリオと管理者以外のインストールで使用されます。</span><span class="sxs-lookup"><span data-stu-id="49619-278">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="49619-279">このスクリプトは、PowerShell のスイッチも読み取るので、Linux/OS X システムのスクリプトで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="49619-279">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="49619-280">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="49619-280">Troubleshoot</span></span>

<span data-ttu-id="49619-281">サポートされている Linux ディストリビューション/バージョンへの .NET Core のインストールに問題がある場合は、インストールしているディストリビューション/バージョンに関する以下のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49619-281">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

* [<span data-ttu-id="49619-282">.NET Core 3.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="49619-282">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [<span data-ttu-id="49619-283">.NET Core 2.2 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="49619-283">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [<span data-ttu-id="49619-284">.NET Core 2.1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="49619-284">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [<span data-ttu-id="49619-285">.NET Core 1.1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="49619-285">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [<span data-ttu-id="49619-286">.NET Core 1.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="49619-286">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
