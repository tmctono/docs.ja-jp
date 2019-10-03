---
title: Mac における .NET Core の前提条件
description: macOS コンピューターで .NET Core アプリケーションを開発、展開、および実行するために必要なサポート対象 macOS のバージョンと .NET Core の依存関係。
author: thraka
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 09/27/2019
ms.openlocfilehash: 13eea0043be9cf5d5574d6b38f144853c22e8d07
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591683"
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="20cd7-103">macOS における .NET Core の前提条件</span><span class="sxs-lookup"><span data-stu-id="20cd7-103">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="20cd7-104">この記事では、macOS コンピューターで .NET Core アプリケーションを開発、展開、および実行するために必要なサポート対象 macOS のバージョンと .NET Core の依存関係を示します。</span><span class="sxs-lookup"><span data-stu-id="20cd7-104">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="20cd7-105">後述のサポート対象 OS のバージョンと依存関係は、Mac で .NET Core アプリを開発する 3 つの方法 ([好きなエディターでコマンド ラインを使用](tutorials/using-with-xplat-cli.md)、[Visual Studio Code を使用](https://code.visualstudio.com/)、および [Visual Studio for Mac を使用](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="20cd7-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>

## <a name="downloads-and-dependencies"></a><span data-ttu-id="20cd7-106">ダウンロードと依存関係</span><span class="sxs-lookup"><span data-stu-id="20cd7-106">Downloads and dependencies</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="20cd7-107">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="20cd7-107">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="20cd7-108">.NET Core 3.0 は、**macOS High Sierra (バージョン 10.13)** 以降のバージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="20cd7-108">.NET Core 3.0 is supported on **macOS High Sierra (version 10.13)** and later versions.</span></span> <span data-ttu-id="20cd7-109">**x64** CPU アーキテクチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="20cd7-109">A **x64** CPU architecture is required.</span></span>

<span data-ttu-id="20cd7-110">[.NET Core 3.0 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.0) ページから .NET Core SDK をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="20cd7-110">Download and install the .NET Core SDK from the [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0) page.</span></span> <span data-ttu-id="20cd7-111">.NET Core 3.0 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 3.0 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20cd7-111">[.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="20cd7-112">既知の問題の一覧については、「[.NET Core の既知の問題](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-known-issues.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20cd7-112">For a list of known issues, see [.NET Core known issues](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-known-issues.md).</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="20cd7-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="20cd7-113">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="20cd7-114">.NET Core 2.2 は、**macOS Sierra (バージョン 10.12)** 以降のバージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="20cd7-114">.NET Core 2.2 is supported on **macOS Sierra (version 10.12)** and later versions.</span></span> <span data-ttu-id="20cd7-115">**x64** CPU アーキテクチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="20cd7-115">A **x64** CPU architecture is required.</span></span>

<span data-ttu-id="20cd7-116">[.NET Core 2.2 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.2) ページから .NET Core SDK をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="20cd7-116">Download and install the .NET Core SDK from the [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2) page.</span></span> <span data-ttu-id="20cd7-117">.NET Core 2.2 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 2.2 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20cd7-117">[.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="20cd7-118">既知の問題の一覧については、「[.NET Core の既知の問題](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-known-issues.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20cd7-118">For a list of known issues, see [.NET Core known issues](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-known-issues.md).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="20cd7-119">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="20cd7-119">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="20cd7-120">.NET Core 2.1 は、**macOS Sierra (バージョン 10.12)** 以降のバージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="20cd7-120">.NET Core 2.1 is supported on **macOS Sierra (version 10.12)** and later versions.</span></span> <span data-ttu-id="20cd7-121">**x64** CPU アーキテクチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="20cd7-121">A **x64** CPU architecture is required.</span></span>

<span data-ttu-id="20cd7-122">[.NET Core 2.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.1) ページから .NET Core SDK をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="20cd7-122">Download and install the .NET Core SDK from the [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1) page.</span></span> <span data-ttu-id="20cd7-123">.NET Core 2.1 でサポートされているオペレーティング システム、ディストリビューション、バージョン、サポートされていない OS バージョン、ライフサイクル ポリシー リンクの完全なリストについては、[.NET Core 2.1 がサポートされる OS バージョン](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20cd7-123">[.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="20cd7-124">既知の問題の一覧については、「[.NET Core の既知の問題](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-known-issues.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20cd7-124">For a list of known issues, see [.NET Core known issues](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-known-issues.md).</span></span>

---

## <a name="visual-studio-for-mac"></a><span data-ttu-id="20cd7-125">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="20cd7-125">Visual Studio for Mac</span></span>

<span data-ttu-id="20cd7-126">.NET Core SDK を使用して .NET Core アプリケーションを開発する場合は、好きなエディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="20cd7-126">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="20cd7-127">ただし、Mac 上の統合開発環境で .NET Core アプリケーションを開発する場合には、[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="20cd7-127">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span>
