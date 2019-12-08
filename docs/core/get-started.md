---
title: .NET Core の概要
description: Windows、Linux、macOS で .NET Core アプリケーションをビルドする方法を学習するためのリソースを示します。
author: thraka
ms.author: adegeo
ms.date: 09/19/2019
ms.openlocfilehash: 89db6d79336c01315983133d9041904d88cba301
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884255"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="406a3-103">.NET Core の概要</span><span class="sxs-lookup"><span data-stu-id="406a3-103">Get started with .NET Core</span></span>

<span data-ttu-id="406a3-104">この記事では、.NET Core の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="406a3-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="406a3-105">.NET Core は、Windows、Linux、および macOS にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="406a3-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="406a3-106">任意のテキスト エディターでコーディングし、クロスプラットフォーム ライブラリとアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="406a3-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span> 

<span data-ttu-id="406a3-107">.NET Core が何であるかや、他の .NET テクノロジとどのように関連しているのかがわからない場合は、まず、[.NET の概要](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="406a3-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="406a3-108">簡単に言うと、.NET Core は .NET のオープンソースのクロスプラットフォーム実装です。</span><span class="sxs-lookup"><span data-stu-id="406a3-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="406a3-109">アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="406a3-109">Create an application</span></span>

<span data-ttu-id="406a3-110">まず、ご利用のコンピューターで [NET Core SDK](https://dotnet.microsoft.com/download) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="406a3-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="406a3-111">次に、**PowerShell**、**コマンド プロンプト**、**bash** などのターミナルを開きます。</span><span class="sxs-lookup"><span data-stu-id="406a3-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="406a3-112">次の `dotnet` コマンドを入力し、C# アプリケーションを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="406a3-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="406a3-113">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="406a3-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="406a3-114">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="406a3-114">Congratulations!</span></span> <span data-ttu-id="406a3-115">シンプルな .NET Core アプリケーションが作成されました。</span><span class="sxs-lookup"><span data-stu-id="406a3-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="406a3-116">[Visual Studio Code](tutorials/with-visual-studio-code.md)、[Visual Studio](tutorials/with-visual-studio.md) (Windows のみ)、または [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS のみ) を使用して、.NET Core アプリケーションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="406a3-116">You can also use [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="406a3-117">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="406a3-117">Tutorials</span></span>

<span data-ttu-id="406a3-118">次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始できます。</span><span class="sxs-lookup"><span data-stu-id="406a3-118">You can get started developing .NET Core applications by following these step-by-step tutorials.</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="406a3-119">Windows</span><span class="sxs-lookup"><span data-stu-id="406a3-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="406a3-120">Visual Studio 2017 での .NET Core を使用した C# Hello World アプリケーションの構築。</span><span class="sxs-lookup"><span data-stu-id="406a3-120">Build a C# "Hello World" Application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="406a3-121">Visual Studio 2017 の C# および .NET Core を使用したクラス ライブラリの構築。</span><span class="sxs-lookup"><span data-stu-id="406a3-121">Build a C# class library with .NET Core in Visual Studio 2017.</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="406a3-122">Visual Studio 2017 での .NET Core を使用した Visual Basic Hello World アプリケーションの構築。</span><span class="sxs-lookup"><span data-stu-id="406a3-122">Build a Visual Basic "Hello World" application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-with-visual-studio.md)
- [<span data-ttu-id="406a3-123">Visual Studio 2017 で Visual Basic と .NET Core を使用したクラス ライブラリの構築。</span><span class="sxs-lookup"><span data-stu-id="406a3-123">Build a class library with Visual Basic and .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-library-with-visual-studio.md)  
- <span data-ttu-id="406a3-124">[Visual Studio Code と .NET Core をインストールして使用する方法](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/)に関するビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="406a3-124">Watch a video on [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span></span>
- <span data-ttu-id="406a3-125">[Visual Studio 2017 と .NET Core をインストールして使用する方法](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/)に関するビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="406a3-125">Watch a video on [how to install and use Visual Studio 2017 and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span></span>
- [<span data-ttu-id="406a3-126">.NET Core でのコマンド ラインの使用に関する概要。</span><span class="sxs-lookup"><span data-stu-id="406a3-126">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)

<span data-ttu-id="406a3-127">サポートされている Windows バージョンの一覧については、[.NET Core の依存関係と要件](install/dependencies.md?tabs=netcore30&pivots=os-windows)に関する記事を参加してください。</span><span class="sxs-lookup"><span data-stu-id="406a3-127">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="406a3-128">Linux</span><span class="sxs-lookup"><span data-stu-id="406a3-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="406a3-129">次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始できます。</span><span class="sxs-lookup"><span data-stu-id="406a3-129">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="406a3-130">.NET Core でのコマンド ラインの使用に関する概要。</span><span class="sxs-lookup"><span data-stu-id="406a3-130">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)
- <span data-ttu-id="406a3-131">[Ubuntu 上の Visual Studio Code での C# と .NET Core の使用に関する概要](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)のビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="406a3-131">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

<span data-ttu-id="406a3-132">サポートされている Linux のディストリビューションとバージョンの一覧については、[.NET Core の依存関係と要件](install/dependencies.md?tabs=netcore30&pivots=os-linux)に関する記事を参加してください。</span><span class="sxs-lookup"><span data-stu-id="406a3-132">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="406a3-133">macOS</span><span class="sxs-lookup"><span data-stu-id="406a3-133">macOS</span></span>](#tab/macos)

<span data-ttu-id="406a3-134">次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始できます。</span><span class="sxs-lookup"><span data-stu-id="406a3-134">You can get started developing .NET Core application by following these step-by-step tutorials:</span></span>

- <span data-ttu-id="406a3-135">[macOS 上の Visual Studio Code での C# と .NET Core の使用に関する概要](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac)のビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="406a3-135">Watch a video on [Getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span>
- [<span data-ttu-id="406a3-136">macOS 上の .NET Core での Visual Studio Code の使用に関する概要。</span><span class="sxs-lookup"><span data-stu-id="406a3-136">Getting started with .NET Core on macOS, using Visual Studio Code.</span></span>](tutorials/using-on-macos.md)
- [<span data-ttu-id="406a3-137">.NET Core でのコマンド ラインの使用に関する概要。</span><span class="sxs-lookup"><span data-stu-id="406a3-137">Getting started with .NET Core using the command-line.</span></span>](tutorials/cli-create-console-app.md)
- [<span data-ttu-id="406a3-138">Visual Studio for Mac を使用した macOS での .NET Core の概要。</span><span class="sxs-lookup"><span data-stu-id="406a3-138">Getting started with .NET Core on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="406a3-139">Visual Studio for Mac を使用した macOS での完全な .NET Core ソリューションの構築。</span><span class="sxs-lookup"><span data-stu-id="406a3-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs-full-solution.md)

<span data-ttu-id="406a3-140">サポートされている OS X / macOS バージョンの一覧については、[.NET Core の依存関係と要件](install/dependencies.md?tabs=netcore30&pivots=os-macos)に関する記事を参加してください。</span><span class="sxs-lookup"><span data-stu-id="406a3-140">See the [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
