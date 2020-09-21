---
title: .NET Core の紹介と概要
description: .NET Core は、Windows、Linux、macOS アプリを作成するための .NET のモジュール型の高性能な実装です。 ここでは、.NET Core の概要について説明します。
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 350fd50bee3403a05d1c19c9a692535613b17498
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538277"
---
# <a name="introduction-to-net-core"></a><span data-ttu-id="6c65e-104">.NET Core の概要</span><span class="sxs-lookup"><span data-stu-id="6c65e-104">Introduction to .NET Core</span></span>

<span data-ttu-id="6c65e-105">[.NET Core](about.md) は、[オープンソース](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)の汎用開発プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="6c65e-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform.</span></span> <span data-ttu-id="6c65e-106">複数のプログラミング言語を使用して、x64、x86、ARM32、および ARM64 の各プロセッサ用に Windows、macOS、および Linux 用 .NET Core アプリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6c65e-106">You can create .NET Core apps for Windows, macOS, and Linux for x64, x86, ARM32, and ARM64 processors using multiple programming languages.</span></span> <span data-ttu-id="6c65e-107">フレームワークと API は、[クラウド](/aspnet/core/)、[IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0)、[クライアント UI](../desktop-wpf/overview/index.md)、[機械学習](../machine-learning/index.yml)用に提供されています。</span><span class="sxs-lookup"><span data-stu-id="6c65e-107">Frameworks and APIs are provided for [cloud](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [client UI](../desktop-wpf/overview/index.md), and [machine learning](../machine-learning/index.yml).</span></span>

<span data-ttu-id="6c65e-108">[.NET Core SDK をダウンロード](https://dotnet.microsoft.com/download)して、お使いのマシンで .NET Core を試してください。</span><span class="sxs-lookup"><span data-stu-id="6c65e-108">[Download the .NET Core SDK](https://dotnet.microsoft.com/download) to try .NET Core on your machine.</span></span> <span data-ttu-id="6c65e-109">最新バージョンは [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/) です。</span><span class="sxs-lookup"><span data-stu-id="6c65e-109">The latest version is [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

## <a name="download-net-core"></a><span data-ttu-id="6c65e-110">.NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="6c65e-110">Download .NET Core</span></span>

<span data-ttu-id="6c65e-111">.NET Core は、次の方法で入手できます。</span><span class="sxs-lookup"><span data-stu-id="6c65e-111">You can get .NET Core in the following ways:</span></span>

* [<span data-ttu-id="6c65e-112">Windows および macOS 用のインストーラー</span><span class="sxs-lookup"><span data-stu-id="6c65e-112">Installers for Windows and macOS</span></span>](https://dotnet.microsoft.com/download)
* [<span data-ttu-id="6c65e-113">Linux パッケージ</span><span class="sxs-lookup"><span data-stu-id="6c65e-113">Linux packages</span></span>](./install/linux.md)
* [<span data-ttu-id="6c65e-114">Docker コンテナー</span><span class="sxs-lookup"><span data-stu-id="6c65e-114">Docker containers</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
* [<span data-ttu-id="6c65e-115">zip と tar ボール</span><span class="sxs-lookup"><span data-stu-id="6c65e-115">Zips and tarballs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [<span data-ttu-id="6c65e-116">スクリプトのインストール</span><span class="sxs-lookup"><span data-stu-id="6c65e-116">Install scripts</span></span>](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [<span data-ttu-id="6c65e-117">リリース ノート</span><span class="sxs-lookup"><span data-stu-id="6c65e-117">Release notes</span></span>](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a><span data-ttu-id="6c65e-118">最初のアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="6c65e-118">Create your first application</span></span>

<span data-ttu-id="6c65e-119">.NET Core SDK をインストールしたらコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="6c65e-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="6c65e-120">次のコマンドを使用し、アプリケーションを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="6c65e-120">Use the following commands to create and run an application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="6c65e-121">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c65e-121">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="contribute"></a><span data-ttu-id="6c65e-122">投稿</span><span class="sxs-lookup"><span data-stu-id="6c65e-122">Contribute</span></span>

<span data-ttu-id="6c65e-123">.NET Core はオープン プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="6c65e-123">.NET Core is an open platform.</span></span> <span data-ttu-id="6c65e-124">どなたでも参加できます。</span><span class="sxs-lookup"><span data-stu-id="6c65e-124">Everyone is welcome to participate.</span></span>

* <span data-ttu-id="6c65e-125">[開発者コミュニティ](https://developercommunity.visualstudio.com/spaces/61/index.html)で製品に関する問題と質問をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6c65e-125">File product issues and questions at [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).</span></span>
* <span data-ttu-id="6c65e-126">製品の投稿は、[dotnet/runtime](https://github.com/dotnet/runtime)、[dotnet/sdk](https://github.com/dotnet/sdk)、[dotnet/rosyln](https://github.com/dotnet/roslyn)、[aspnetcore](https://github.com/dotnet/aspnetcore) などのプロジェクト リポジトリのいずれかで行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c65e-126">Product contributions should be made on one of the project repositories, such as [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn), or [aspnetcore](https://github.com/dotnet/aspnetcore).</span></span> <span data-ttu-id="6c65e-127">詳細については、[.NET Core リポジトリ](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c65e-127">For more information, see [.NET Core repos](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span></span>

## <a name="support"></a><span data-ttu-id="6c65e-128">サポート</span><span class="sxs-lookup"><span data-stu-id="6c65e-128">Support</span></span>

<span data-ttu-id="6c65e-129">.NET Core は、Windows、macOS、および Linux 上の Microsoft と、Red Hat Enterprise Linux 上の Red Hat でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6c65e-129">.NET Core is supported by Microsoft on Windows, macOS, and Linux and by Red Hat on Red Hat Enterprise Linux.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c65e-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="6c65e-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6c65e-131">.NET Core チュートリアル</span><span class="sxs-lookup"><span data-stu-id="6c65e-131">.NET Core tutorials</span></span>](tutorials/index.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="6c65e-132">ブラウザーで .NET Core を試す</span><span class="sxs-lookup"><span data-stu-id="6c65e-132">Try .NET Core in your browser</span></span>](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
