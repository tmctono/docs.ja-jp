---
title: .NET Core の概要
description: Windows、Linux、macOS で .NET Core アプリケーションをビルドする方法を学習するためのリソースを示します。
author: thraka
ms.author: adegeo
ms.date: 06/27/2018
ms.openlocfilehash: 2ec7f57250db8779552305b2ee69cbcf1db55d0c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977170"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="e5fa7-103">.NET Core の概要</span><span class="sxs-lookup"><span data-stu-id="e5fa7-103">Get started with .NET Core</span></span>

<span data-ttu-id="e5fa7-104">この記事では、.NET Core の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="e5fa7-105">.NET Core は、Windows、Linux、および macOS にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="e5fa7-106">任意のテキスト エディターでコーディングし、クロスプラットフォーム ライブラリとアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span> 

<span data-ttu-id="e5fa7-107">.NET Core が何であるかや、他の .NET テクノロジとどのように関連しているのかがわからない場合は、まず、[.NET の概要](https://www.microsoft.com/net/learn/dotnet/what-is-dotnet)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://www.microsoft.com/net/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="e5fa7-108">簡単に言うと、.NET Core は .NET のオープンソースのクロスプラットフォーム実装です。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-108">Put simply, .NET Core is an open-source, cross-platform, implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="e5fa7-109">アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="e5fa7-109">Create an application</span></span>

<span data-ttu-id="e5fa7-110">まず、ご利用のコンピューターで [NET Core SDK](https://www.microsoft.com/net/download/) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-110">First, download and install the [.NET Core SDK](https://www.microsoft.com/net/download/) on your computer.</span></span>

<span data-ttu-id="e5fa7-111">次に、**PowerShell**、**コマンド プロンプト**、**bash** などのターミナルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="e5fa7-112">次の `dotnet` コマンドを入力し、C# アプリケーションを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-112">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="e5fa7-113">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="e5fa7-114">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="e5fa7-114">Congratulations!</span></span> <span data-ttu-id="e5fa7-115">シンプルな .NET Core アプリケーションが作成されました。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="e5fa7-116">[Visual Studio Code](tutorials/with-visual-studio-code.md)、[Visual Studio 2017](tutorials/with-visual-studio.md) (Windows のみ)、または [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS のみ) を使用して、.NET Core アプリケーションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-116">You can also use [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio 2017](tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="e5fa7-117">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="e5fa7-117">Tutorials</span></span>

<span data-ttu-id="e5fa7-118">次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始できます。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-118">You can get started developing .NET Core applications by following these step-by-step tutorials.</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="e5fa7-119">Windows</span><span class="sxs-lookup"><span data-stu-id="e5fa7-119">Windows</span></span>](#tab/windows)

* [<span data-ttu-id="e5fa7-120">Visual Studio 2017 での .NET Core を使用した C# Hello World アプリケーションの構築。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-120">Build a C# "Hello World" Application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/with-visual-studio.md)

* [<span data-ttu-id="e5fa7-121">Visual Studio 2017 の C# および .NET Core を使用したクラス ライブラリの構築。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-121">Build a C# class library with .NET Core in Visual Studio 2017.</span></span>](./tutorials/library-with-visual-studio.md)

* [<span data-ttu-id="e5fa7-122">Visual Studio 2017 での .NET Core を使用した Visual Basic Hello World アプリケーションの構築。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-122">Build a Visual Basic "Hello World" application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-with-visual-studio.md)

* [<span data-ttu-id="e5fa7-123">Visual Studio 2017 で Visual Basic と .NET Core を使用したクラス ライブラリの構築。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-123">Build a class library with Visual Basic and .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-library-with-visual-studio.md)  

* <span data-ttu-id="e5fa7-124">[Visual Studio Code と .NET Core をインストールして使用する方法](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/)に関するビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-124">Watch a video on [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span></span>

* <span data-ttu-id="e5fa7-125">[Visual Studio 2017 と .NET Core をインストールして使用する方法](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/)に関するビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-125">Watch a video on [how to install and use Visual Studio 2017 and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span></span>

* [<span data-ttu-id="e5fa7-126">.NET Core でのコマンド ラインの使用に関する概要。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-126">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

<span data-ttu-id="e5fa7-127">サポートされている Windows のバージョンの一覧については、[Windows 開発の前提条件](windows-prerequisites.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-127">See the [Prerequisites for Windows development](windows-prerequisites.md) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="e5fa7-128">Linux</span><span class="sxs-lookup"><span data-stu-id="e5fa7-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="e5fa7-129">次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始できます。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-129">You can get started developing .NET Core application by following these step-by-step tutorials.</span></span>

* [<span data-ttu-id="e5fa7-130">.NET Core でのコマンド ラインの使用に関する概要。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-130">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

* <span data-ttu-id="e5fa7-131">[Ubuntu 上の Visual Studio Code での C# と .NET Core の使用に関する概要](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)のビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-131">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

<span data-ttu-id="e5fa7-132">サポートされている Linux ディストリビューションおよびバージョンの一覧については、[Linux 開発における前提条件](linux-prerequisites.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-132">See the [Prerequisites for Linux development](linux-prerequisites.md) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="e5fa7-133">macOS</span><span class="sxs-lookup"><span data-stu-id="e5fa7-133">macOS</span></span>](#tab/macos)

<span data-ttu-id="e5fa7-134">次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始できます。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-134">You can get started developing .NET Core application by following these step-by-step tutorials.</span></span>

* <span data-ttu-id="e5fa7-135">[macOS 上の Visual Studio Code での C# と .NET Core の使用に関する概要](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac)のビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-135">Watch a video on [Getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span>

* [<span data-ttu-id="e5fa7-136">macOS 上の .NET Core での Visual Studio Code の使用に関する概要。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-136">Getting started with .NET Core on macOS, using Visual Studio Code.</span></span>](tutorials/using-on-macos.md)

* [<span data-ttu-id="e5fa7-137">.NET Core でのコマンド ラインの使用に関する概要。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-137">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

* [<span data-ttu-id="e5fa7-138">Visual Studio for Mac を使用した macOS での .NET Core の概要。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-138">Getting started with .NET Core on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs.md)

* [<span data-ttu-id="e5fa7-139">Visual Studio for Mac を使用した macOS での完全な .NET Core ソリューションの構築。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs-full-solution.md)

<span data-ttu-id="e5fa7-140">サポートされている OS X または macOS のバージョンの一覧については、「[macOS における .NET Core の前提条件](macos-prerequisites.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5fa7-140">See the [Prerequisites for macOS development](macos-prerequisites.md) article for a list of the supported OS X / macOS versions.</span></span>

---
