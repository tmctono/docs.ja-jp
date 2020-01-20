---
title: .NET Core の概要
description: Windows、Linux、macOS で .NET Core アプリケーションをビルドする方法を学習するためのリソースを示します。
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 0968d9db1dbfbdc8c586328ee8e02315f17950b9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714391"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="284f2-103">.NET Core の概要</span><span class="sxs-lookup"><span data-stu-id="284f2-103">Get started with .NET Core</span></span>

<span data-ttu-id="284f2-104">この記事では、.NET Core の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="284f2-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="284f2-105">.NET Core は、Windows、Linux、および macOS にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="284f2-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="284f2-106">任意のテキスト エディターでコーディングし、クロスプラットフォーム ライブラリとアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="284f2-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span>

<span data-ttu-id="284f2-107">.NET Core が何であるかや、他の .NET テクノロジとどのように関連しているのかがわからない場合は、まず、[.NET の概要](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="284f2-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="284f2-108">簡単に言うと、.NET Core は .NET のオープンソースのクロスプラットフォーム実装です。</span><span class="sxs-lookup"><span data-stu-id="284f2-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="284f2-109">アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="284f2-109">Create an application</span></span>

<span data-ttu-id="284f2-110">まず、ご利用のコンピューターで [NET Core SDK](https://dotnet.microsoft.com/download) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="284f2-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="284f2-111">次に、**PowerShell**、**コマンド プロンプト**、**bash** などのターミナルを開きます。</span><span class="sxs-lookup"><span data-stu-id="284f2-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="284f2-112">次の `dotnet` コマンドを入力し、C# アプリケーションを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="284f2-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="284f2-113">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="284f2-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="284f2-114">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="284f2-114">Congratulations!</span></span> <span data-ttu-id="284f2-115">シンプルな .NET Core アプリケーションが作成されました。</span><span class="sxs-lookup"><span data-stu-id="284f2-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="284f2-116">[Visual Studio Code](./tutorials/with-visual-studio-code.md)、[Visual Studio](./tutorials/with-visual-studio.md) (Windows のみ)、または [Visual Studio for Mac](./tutorials/using-on-mac-vs.md) (macOS のみ) を使用して、.NET Core アプリケーションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="284f2-116">You can also use [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](./tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="284f2-117">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="284f2-117">Tutorials</span></span>

<span data-ttu-id="284f2-118">次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始します。</span><span class="sxs-lookup"><span data-stu-id="284f2-118">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="284f2-119">Windows</span><span class="sxs-lookup"><span data-stu-id="284f2-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="284f2-120">Visual Studio 2019 で最初の .NET Core コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="284f2-120">Create your first .NET Core console application in Visual Studio 2019</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="284f2-121">Visual Studio で .NET Standard を使用してクラス ライブラリを構築する</span><span class="sxs-lookup"><span data-stu-id="284f2-121">Build a class library with .NET Standard in Visual Studio</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="284f2-122">.NET Core での .NET Core CLI の使用に関する概要</span><span class="sxs-lookup"><span data-stu-id="284f2-122">Get started with .NET Core using the .NET Core CLI</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="284f2-123">![ビデオのムービー カメラ アイコン](./media/video-icon.png "ビデオを見る")</span><span class="sxs-lookup"><span data-stu-id="284f2-123">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="284f2-124">Channel 9 で [Visual Studio Code と .NET Core をインストールして使用する方法](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/)についてのビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="284f2-124">Watch the [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) video on Channel 9.</span></span> |
| <span data-ttu-id="284f2-125">![ビデオのムービー カメラ アイコン](./media/video-icon.png "ビデオを見る")</span><span class="sxs-lookup"><span data-stu-id="284f2-125">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="284f2-126">YouTube で [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) に関するビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="284f2-126">Watch the [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) videos on YouTube.</span></span> |

<span data-ttu-id="284f2-127">サポートされている Windows バージョンの一覧については、[.NET Core の依存関係と要件](install/dependencies.md?pivots=os-windows)に関する記事を参加してください。</span><span class="sxs-lookup"><span data-stu-id="284f2-127">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="284f2-128">Linux</span><span class="sxs-lookup"><span data-stu-id="284f2-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="284f2-129">次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始します。</span><span class="sxs-lookup"><span data-stu-id="284f2-129">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="284f2-130">.NET Core でのコマンド ラインの使用に関する概要</span><span class="sxs-lookup"><span data-stu-id="284f2-130">Get started with .NET Core using the command line</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="284f2-131">![ビデオのムービー カメラ アイコン](./media/video-icon.png "ビデオを見る")</span><span class="sxs-lookup"><span data-stu-id="284f2-131">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="284f2-132">[Ubuntu 上の Visual Studio Code での C# と .NET Core の使用に関する概要](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)のビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="284f2-132">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span> |

<span data-ttu-id="284f2-133">サポートされている Linux のディストリビューションとバージョンの一覧については、[.NET Core の依存関係と要件](install/dependencies.md?pivots=os-linux)に関する記事を参加してください。</span><span class="sxs-lookup"><span data-stu-id="284f2-133">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="284f2-134">macOS</span><span class="sxs-lookup"><span data-stu-id="284f2-134">macOS</span></span>](#tab/macos)

<span data-ttu-id="284f2-135">次のステップ バイ ステップのチュートリアルに従って、.NET Core アプリケーションの開発を開始します。</span><span class="sxs-lookup"><span data-stu-id="284f2-135">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="284f2-136">macOS 上の .NET Core での Visual Studio Code の使用に関する概要</span><span class="sxs-lookup"><span data-stu-id="284f2-136">Get started with .NET Core on macOS using Visual Studio Code</span></span>](./tutorials/using-on-macos.md)
- [<span data-ttu-id="284f2-137">.NET Core でのコマンド ラインの使用に関する概要</span><span class="sxs-lookup"><span data-stu-id="284f2-137">Get started with .NET Core using the command-line</span></span>](./tutorials/cli-create-console-app.md)
- [<span data-ttu-id="284f2-138">Visual Studio for Mac を使用した macOS での .NET Core の概要</span><span class="sxs-lookup"><span data-stu-id="284f2-138">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="284f2-139">Visual Studio for Mac を使用した macOS での完全な .NET Core ソリューションの構築</span><span class="sxs-lookup"><span data-stu-id="284f2-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs-full-solution.md)

|   |   |
|---|---|
| <span data-ttu-id="284f2-140">![ビデオのムービー カメラ アイコン](media/video-icon.png "ビデオを見る")</span><span class="sxs-lookup"><span data-stu-id="284f2-140">![movie camera icon for video](media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="284f2-141">[macOS 上の Visual Studio Code での C# と .NET Core の使用に関する概要](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac)のビデオを見る。</span><span class="sxs-lookup"><span data-stu-id="284f2-141">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span> |

<span data-ttu-id="284f2-142">サポートされている OS X / macOS バージョンの一覧については、[.NET Core の依存関係と要件](install/dependencies.md?pivots=os-macos)に関する記事を参加してください。</span><span class="sxs-lookup"><span data-stu-id="284f2-142">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
