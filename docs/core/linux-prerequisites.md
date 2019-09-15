---
title: Linux における .NET Core の前提条件
description: Linux マシンで .NET Core アプリケーションを開発、展開、および実行するために必要なサポートされている Linux のバージョンと .NET Core の依存関係。
author: thraka
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: 5fcf931572f3c7e9b9857d2e91e9d620c7aad0bd
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969864"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="2dd55-103">Linux における .NET Core の前提条件</span><span class="sxs-lookup"><span data-stu-id="2dd55-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="2dd55-104">この記事では、Linux で .NET Core アプリケーションを開発するために必要な依存関係を示します。</span><span class="sxs-lookup"><span data-stu-id="2dd55-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="2dd55-105">後述のサポートされている Linux ディストリビューション/バージョンと依存関係は、Linux で .NET Core アプリを開発する次の 2 つの方法に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2dd55-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="2dd55-106">好みのエディターでのコマンドライン</span><span class="sxs-lookup"><span data-stu-id="2dd55-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="2dd55-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2dd55-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="2dd55-108">.NET Core SDK パッケージは、運用サーバー/環境には必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2dd55-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="2dd55-109">運用環境に展開されるアプリに必要なものは、.NET Core ランタイム パッケージだけです。</span><span class="sxs-lookup"><span data-stu-id="2dd55-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="2dd55-110">.NET Core ランタイムは自己完結型の展開の一部としてアプリと供に展開されますが、フレームワークに依存して展開されるアプリでは個別に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dd55-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="2dd55-111">フレームワークに依存する展開と自己完結型の展開について詳しくは、「[.NET Core アプリケーションの展開](./deploying/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="2dd55-112">具体的なガイドラインについては、「[Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」(自己完結型 Linux アプリケーション) もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="2dd55-113">サポートされている Linux バージョン</span><span class="sxs-lookup"><span data-stu-id="2dd55-113">Supported Linux versions</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="2dd55-114">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="2dd55-114">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="2dd55-115">.NET Core 2.x は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="2dd55-115">.NET Core 2.x treats Linux as a single operating system.</span></span> <span data-ttu-id="2dd55-116">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="2dd55-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="2dd55-117">ダウンロード リンクと詳細については、[.NET Core 2.2 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.2)または [.NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1) のダウンロードのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-117">For download links and more information, see [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="2dd55-118">.NET Core 2.x は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2dd55-118">.NET Core 2.x is supported on the following Linux distributions/versions:</span></span>

* <span data-ttu-id="2dd55-119">Red Hat Enterprise Linux 7、6 - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-119">Red Hat Enterprise Linux 7, 6 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="2dd55-120">CentOS 7 - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-120">CentOS 7  - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="2dd55-121">Oracle Linux 7 - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-121">Oracle Linux 7 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="2dd55-122">Fedora 28、27 - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-122">Fedora 28, 27 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="2dd55-123">Debian 9 (64 ビット、`arm32`), 8.7 以降のバージョン - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-123">Debian 9 (64-bit, `arm32`), 8.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="2dd55-124">Ubuntu 18.04 (64 ビット、`arm32`)、16.04、14.04 - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-124">Ubuntu 18.04 (64-bit, `arm32`), 16.04, 14.04 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="2dd55-125">Linux Mint 18、17 - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-125">Linux Mint 18, 17 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="2dd55-126">openSUSE 42.3 以降のバージョン - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-126">openSUSE 42.3 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="2dd55-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 以降 - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 or later - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="2dd55-128">Alpine Linux 3.7 以降のバージョン - 64 ビット (`x86_64` または `amd64`)</span><span class="sxs-lookup"><span data-stu-id="2dd55-128">Alpine Linux 3.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>

<span data-ttu-id="2dd55-129">.NET Core 2.1 と .NET Core 2.2 がサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 2.1 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)と [.NET Core 2.2 がサポートされている OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-129">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2dd55-130">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2dd55-130">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="2dd55-131">ダウンロード リンクと詳細については、[.NET Core 1.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/1.1)または [.NET Core 1.0](https://dotnet.microsoft.com/download/dotnet-core/1.0) のダウンロードのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-131">For download links and more information, see [.NET Core 1.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/1.0).</span></span>

<span data-ttu-id="2dd55-132">.NET Core 1.x は、次の Linux 64 ビット (`x86_64` または `amd64`) ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2dd55-132">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="2dd55-133">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="2dd55-133">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="2dd55-134">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="2dd55-134">CentOS 7</span></span>
* <span data-ttu-id="2dd55-135">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="2dd55-135">Oracle Linux 7</span></span>
* <span data-ttu-id="2dd55-136">Fedora 28 (.NET Core 1.1)、27</span><span class="sxs-lookup"><span data-stu-id="2dd55-136">Fedora 28 (.NET Core 1.1), 27</span></span>
* <span data-ttu-id="2dd55-137">Debian 8.2 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="2dd55-137">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="2dd55-138">Ubuntu 18.04 (.NET Core 1.1)、16.04、14.04</span><span class="sxs-lookup"><span data-stu-id="2dd55-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span></span>
* <span data-ttu-id="2dd55-139">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="2dd55-139">Linux Mint 17</span></span>
* <span data-ttu-id="2dd55-140">openSUSE 42.3 以降のバージョン (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="2dd55-140">openSUSE 42.3 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="2dd55-141">.NET Core 1.x がサポートされているオペレーティング システム (サポートされている OS バージョン以外) の完全なリスト、およびライフサイクル ポリシーのリンクについては、「[.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)」 (.NET Core 1.x がサポートされる OS のバージョン) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-141">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-30-preview-1tabnetcore30"></a>[<span data-ttu-id="2dd55-142">.NET Core 3.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="2dd55-142">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="2dd55-143">.NET Core 3.0 Preview 1 は、1 つのオペレーティング システムとして Linux を扱います。</span><span class="sxs-lookup"><span data-stu-id="2dd55-143">.NET Core 3.0 Preview 1 treats Linux as a single operating system.</span></span> <span data-ttu-id="2dd55-144">サポートされている Linux ディストリビューション用に、1 つの Linux ビルド (チップ アーキテクチャあたり) があります。</span><span class="sxs-lookup"><span data-stu-id="2dd55-144">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="2dd55-145">ダウンロード リンクと詳細については、[.NET Core 3.0 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.0) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-145">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="2dd55-146">.NET Core 3.0 Preview 1 は、次の Linux ディストリビューション/バージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2dd55-146">.NET Core 3.0 Preview 1 is supported on the following Linux distributions/versions.</span></span> 

<span data-ttu-id="2dd55-147">OS</span><span class="sxs-lookup"><span data-stu-id="2dd55-147">OS</span></span>                            | <span data-ttu-id="2dd55-148">Version</span><span class="sxs-lookup"><span data-stu-id="2dd55-148">Version</span></span>               | <span data-ttu-id="2dd55-149">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="2dd55-149">Architectures</span></span>  
------------------------------|-----------------------|----------------
<span data-ttu-id="2dd55-150">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="2dd55-150">Red Hat Enterprise Linux</span></span>      | <span data-ttu-id="2dd55-151">6</span><span class="sxs-lookup"><span data-stu-id="2dd55-151">6</span></span>                     | <span data-ttu-id="2dd55-152">X64</span><span class="sxs-lookup"><span data-stu-id="2dd55-152">x64</span></span>
<span data-ttu-id="2dd55-153">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="2dd55-153">Red Hat Enterprise Linux</span></span><br><span data-ttu-id="2dd55-154">CentOS</span><span class="sxs-lookup"><span data-stu-id="2dd55-154">CentOS</span></span><br><span data-ttu-id="2dd55-155">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="2dd55-155">Oracle Linux</span></span>  | <span data-ttu-id="2dd55-156">7</span><span class="sxs-lookup"><span data-stu-id="2dd55-156">7</span></span>                     | <span data-ttu-id="2dd55-157">X64</span><span class="sxs-lookup"><span data-stu-id="2dd55-157">x64</span></span>
<span data-ttu-id="2dd55-158">Fedora</span><span class="sxs-lookup"><span data-stu-id="2dd55-158">Fedora</span></span>                        | <span data-ttu-id="2dd55-159">28</span><span class="sxs-lookup"><span data-stu-id="2dd55-159">28</span></span>                    | <span data-ttu-id="2dd55-160">X64</span><span class="sxs-lookup"><span data-stu-id="2dd55-160">x64</span></span>
<span data-ttu-id="2dd55-161">Debian</span><span class="sxs-lookup"><span data-stu-id="2dd55-161">Debian</span></span>                        | <span data-ttu-id="2dd55-162">9</span><span class="sxs-lookup"><span data-stu-id="2dd55-162">9</span></span>                     | <span data-ttu-id="2dd55-163">x64、ARM32\*、ARM64\*</span><span class="sxs-lookup"><span data-stu-id="2dd55-163">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="2dd55-164">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2dd55-164">Ubuntu</span></span>                        | <span data-ttu-id="2dd55-165">16.04+、18.04+</span><span class="sxs-lookup"><span data-stu-id="2dd55-165">16.04+, 18.04+</span></span>        | <span data-ttu-id="2dd55-166">x64、ARM32\*、ARM64\*</span><span class="sxs-lookup"><span data-stu-id="2dd55-166">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="2dd55-167">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="2dd55-167">Linux Mint</span></span>                    | <span data-ttu-id="2dd55-168">18</span><span class="sxs-lookup"><span data-stu-id="2dd55-168">18</span></span>                    | <span data-ttu-id="2dd55-169">X64</span><span class="sxs-lookup"><span data-stu-id="2dd55-169">x64</span></span>
<span data-ttu-id="2dd55-170">openSUSE</span><span class="sxs-lookup"><span data-stu-id="2dd55-170">openSUSE</span></span>                      | <span data-ttu-id="2dd55-171">42.3+</span><span class="sxs-lookup"><span data-stu-id="2dd55-171">42.3+</span></span>                 | <span data-ttu-id="2dd55-172">X64</span><span class="sxs-lookup"><span data-stu-id="2dd55-172">x64</span></span>
<span data-ttu-id="2dd55-173">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="2dd55-173">SUSE Enterprise Linux (SLES)</span></span>  | <span data-ttu-id="2dd55-174">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="2dd55-174">12 SP2+</span></span>               | <span data-ttu-id="2dd55-175">X64</span><span class="sxs-lookup"><span data-stu-id="2dd55-175">x64</span></span>
<span data-ttu-id="2dd55-176">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="2dd55-176">Alpine Linux</span></span>                  | <span data-ttu-id="2dd55-177">3.8+</span><span class="sxs-lookup"><span data-stu-id="2dd55-177">3.8+</span></span>                  | <span data-ttu-id="2dd55-178">x64、ARM64</span><span class="sxs-lookup"><span data-stu-id="2dd55-178">x64, ARM64</span></span>

<span data-ttu-id="2dd55-179">\* ARM32 および ARM64 は、Debian 9 以降および Ubuntu 16.04 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2dd55-179">\* ARM32 and ARM64 support starts with Debian 9 and Ubuntu 16.04.</span></span> <span data-ttu-id="2dd55-180">これらのディストリビューションのこれより古いバージョンでは、ARM チップはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2dd55-180">Earlier versions of those distros are not supported on ARM chips.</span></span>

<span data-ttu-id="2dd55-181">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 3.0 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-181">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="2dd55-182">ARM64 で .NET Core 3.0 をインストールする方法の詳細については、「[Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)」 (Linux ARM64 での .NET Core 3.0 のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-182">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="2dd55-183">Linux ディストリビューションの依存関係</span><span class="sxs-lookup"><span data-stu-id="2dd55-183">Linux distribution dependencies</span></span>

<span data-ttu-id="2dd55-184">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2dd55-184">The following are intended to be examples.</span></span> <span data-ttu-id="2dd55-185">選択した Linux ディストリビューションで、バージョンと名前が多少異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2dd55-185">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="2dd55-186">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2dd55-186">Ubuntu</span></span>

<span data-ttu-id="2dd55-187">Ubuntu ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dd55-187">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="2dd55-188">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="2dd55-188">liblttng-ust0</span></span>
* <span data-ttu-id="2dd55-189">libcurl3 (14.x および 16.x 用)</span><span class="sxs-lookup"><span data-stu-id="2dd55-189">libcurl3 (for 14.x and 16.x)</span></span>
* <span data-ttu-id="2dd55-190">libcurl4 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="2dd55-190">libcurl4 (for 18.x)</span></span>
* <span data-ttu-id="2dd55-191">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="2dd55-191">libssl1.0.0</span></span>
* <span data-ttu-id="2dd55-192">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="2dd55-192">libkrb5-3</span></span>
* <span data-ttu-id="2dd55-193">zlib1g</span><span class="sxs-lookup"><span data-stu-id="2dd55-193">zlib1g</span></span>
* <span data-ttu-id="2dd55-194">libicu52 (14.x 用)</span><span class="sxs-lookup"><span data-stu-id="2dd55-194">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="2dd55-195">libicu55 (16.x 用)</span><span class="sxs-lookup"><span data-stu-id="2dd55-195">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="2dd55-196">libicu57 (17.x 用)</span><span class="sxs-lookup"><span data-stu-id="2dd55-196">libicu57 (for 17.x)</span></span>
* <span data-ttu-id="2dd55-197">libicu60 (18.x 用)</span><span class="sxs-lookup"><span data-stu-id="2dd55-197">libicu60 (for 18.x)</span></span>

<span data-ttu-id="2dd55-198">.NET Core 2.1 より前のバージョンには、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="2dd55-198">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="2dd55-199">libunwind8</span><span class="sxs-lookup"><span data-stu-id="2dd55-199">libunwind8</span></span>
* <span data-ttu-id="2dd55-200">libuuid1</span><span class="sxs-lookup"><span data-stu-id="2dd55-200">libuuid1</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="2dd55-201">CentOS と Fedora</span><span class="sxs-lookup"><span data-stu-id="2dd55-201">CentOS and Fedora</span></span>

<span data-ttu-id="2dd55-202">CentOS ディストリビューションには、次のライブラリがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dd55-202">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="2dd55-203">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="2dd55-203">lttng-ust</span></span>
* <span data-ttu-id="2dd55-204">libcurl</span><span class="sxs-lookup"><span data-stu-id="2dd55-204">libcurl</span></span>
* <span data-ttu-id="2dd55-205">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="2dd55-205">openssl-libs</span></span>
* <span data-ttu-id="2dd55-206">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="2dd55-206">krb5-libs</span></span>
* <span data-ttu-id="2dd55-207">libicu</span><span class="sxs-lookup"><span data-stu-id="2dd55-207">libicu</span></span>
* <span data-ttu-id="2dd55-208">zlib</span><span class="sxs-lookup"><span data-stu-id="2dd55-208">zlib</span></span>

<span data-ttu-id="2dd55-209">Fedora ユーザー:ご使用の openssl のバージョンが 1.1 以降の場合は、compat-openssl10 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dd55-209">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="2dd55-210">.NET Core 2.1 より前のバージョンには、次の依存関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="2dd55-210">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="2dd55-211">libunwind</span><span class="sxs-lookup"><span data-stu-id="2dd55-211">libunwind</span></span>
* <span data-ttu-id="2dd55-212">libuuid</span><span class="sxs-lookup"><span data-stu-id="2dd55-212">libuuid</span></span>

<span data-ttu-id="2dd55-213">依存関係の詳細については、「[Self-contained Linux applications (自己完結型 Linux アプリケーション)](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-213">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="2dd55-214">ネイティブ インストーラーを使用した .NET Core の依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="2dd55-214">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="2dd55-215">.NET Core ネイティブ インストーラーは、サポートされている Linux ディストリビューション/バージョンに利用できます。</span><span class="sxs-lookup"><span data-stu-id="2dd55-215">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="2dd55-216">このネイティブ インストーラーは、サーバーへの admin (sudo) アクセスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="2dd55-216">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="2dd55-217">ネイティブ インストーラーを使用することの利点は、.NET Core ネイティブの依存関係がすべてインストールされることです。</span><span class="sxs-lookup"><span data-stu-id="2dd55-217">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="2dd55-218">また、ネイティブ インストーラーでは、.NET Core SDK もシステム全体にインストールします。</span><span class="sxs-lookup"><span data-stu-id="2dd55-218">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="2dd55-219">Linux では、2 つのインストーラー パッケージから選択できます。</span><span class="sxs-lookup"><span data-stu-id="2dd55-219">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="2dd55-220">フィードベースのパッケージ マネージャー (Ubuntu では apt-get、CentOS/RHEL では yum など) を使用する</span><span class="sxs-lookup"><span data-stu-id="2dd55-220">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="2dd55-221">パッケージ自体 (DEB または RPM) を使用する</span><span class="sxs-lookup"><span data-stu-id="2dd55-221">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="2dd55-222">.NET Core インストーラー スクリプトを使用したスクリプトのインストール</span><span class="sxs-lookup"><span data-stu-id="2dd55-222">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="2dd55-223">[dotnet-install スクリプト](./tools/dotnet-install-script.md)は、CLI ツールチェーンと共有ランタイムの非管理者インストールを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2dd55-223">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="2dd55-224">このスクリプトは <https://dot.net/v1/dotnet-install.sh> からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2dd55-224">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="2dd55-225">スクリプトは、既定で最新の "LTS" のバージョン (現在は .NET Core 1.1) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2dd55-225">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="2dd55-226">NET Core 2.1 をインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="2dd55-226">To install .NET Core 2.1, run the script with the following switch:</span></span>

```console
./dotnet-install.sh -c Current
```

<span data-ttu-id="2dd55-227">インストーラーの bash スクリプトは、自動化シナリオと管理者以外のインストールで使用されます。</span><span class="sxs-lookup"><span data-stu-id="2dd55-227">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="2dd55-228">このスクリプトは、PowerShell のスイッチも読み取るので、Linux/OS X システムのスクリプトで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="2dd55-228">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="2dd55-229">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2dd55-229">Troubleshoot</span></span>

<span data-ttu-id="2dd55-230">サポートされている Linux ディストリビューション/バージョンへの .NET Core のインストールに問題がある場合は、インストールしているディストリビューション/バージョンに関する以下のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2dd55-230">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

* [<span data-ttu-id="2dd55-231">.NET Core 3.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="2dd55-231">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [<span data-ttu-id="2dd55-232">.NET Core 2.2 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="2dd55-232">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [<span data-ttu-id="2dd55-233">.NET Core 2.1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="2dd55-233">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [<span data-ttu-id="2dd55-234">.NET Core 1.1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="2dd55-234">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [<span data-ttu-id="2dd55-235">.NET Core 1.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="2dd55-235">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
