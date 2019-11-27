---
title: F# をインストールする
description: 環境に基づいてF#をインストールする方法について説明します。
ms.date: 09/05/2019
ms.openlocfilehash: 592a4c7763266cee68809fca84f9604d7e96b8f1
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204874"
---
# <a name="install-f"></a><span data-ttu-id="2ea26-103">F\# のインストール</span><span class="sxs-lookup"><span data-stu-id="2ea26-103">Install F\#</span></span>

<span data-ttu-id="2ea26-104">環境に応じて、複数の方法で F# をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2ea26-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="2ea26-105">Visual Studio で F# をインストールする</span><span class="sxs-lookup"><span data-stu-id="2ea26-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="2ea26-106">[Visual studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)を初めてダウンロードする場合は、最初に visual studio インストーラーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2ea26-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="2ea26-107">インストーラーから適切な SKU の Visual Studio をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2ea26-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="2ea26-108">既にインストールされている場合は、 **[変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ea26-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="2ea26-109">次に、ワークロードの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ea26-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="2ea26-110">ASP.NET Core プロジェクトのサポートと .NET Core サポートF#をインストールする**ASP.NET と web 開発**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ea26-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="2ea26-111">次に、右下にある **[変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ea26-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="2ea26-112">これにより、選択したすべてのものがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2ea26-112">This will install everything you have selected.</span></span> <span data-ttu-id="2ea26-113">その後、 **[起動]** をクリックF#して、Visual Studio 2017 を言語サポートで開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2ea26-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="2ea26-114">Visual Studio Code F#と共にインストールする</span><span class="sxs-lookup"><span data-stu-id="2ea26-114">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="2ea26-115">最初に、git が[インストールされ](https://git-scm.com/download)、パスに使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ea26-115">First, ensure you have [git installed](https://git-scm.com/download) and available on your PATH.</span></span> <span data-ttu-id="2ea26-116">コマンドプロンプトで「`git --version`」と入力し、 **enter**キーを押すと、正しくインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2ea26-116">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

<span data-ttu-id="2ea26-117">次に、 [.NET Core SDK](https://dotnet.microsoft.com/download)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2ea26-117">Next, install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="2ea26-118">その後、 [Visual Studio Code](https://code.visualstudio.com)インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ea26-118">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="2ea26-119">次に、[拡張機能] アイコンをクリックし、"Ionide" を検索します。</span><span class="sxs-lookup"><span data-stu-id="2ea26-119">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="2ea26-120">Visual Studio Code でのサポートにF#必要なプラグインは、 [Ionide fsharp.core](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)だけです。</span><span class="sxs-lookup"><span data-stu-id="2ea26-120">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="2ea26-121">ただし、Ionide をインストールして、[偽](https://fake.build/)[の](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)サポートと[Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)を取得し、[パケット](https://fsprojects.github.io/Paket/)のサポートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ea26-121">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="2ea26-122">フェイクとパケットは、 F#プロジェクトをビルドし、依存関係を管理するための追加のコミュニティツールです。</span><span class="sxs-lookup"><span data-stu-id="2ea26-122">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="2ea26-123">Visual Studio for Macで F# をインストールする</span><span class="sxs-lookup"><span data-stu-id="2ea26-123">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="2ea26-124">F#は、選択した構成に関係なく[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)に既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2ea26-124">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="2ea26-125">インストールが完了したら、[Visual Studio の起動] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ea26-125">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="2ea26-126">また、macOS で Finder を使用して起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ea26-126">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="2ea26-127">ビルドサーバーに F＃ をインストールする</span><span class="sxs-lookup"><span data-stu-id="2ea26-127">Install F# on a Build Server</span></span>

<span data-ttu-id="2ea26-128">.Net Core または .net SDK を .NET Framework を経由で使用している場合は、.NET SDK をビルドサーバーにインストールするだけです。</span><span class="sxs-lookup"><span data-stu-id="2ea26-128">If you are using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="2ea26-129">必要なものはすべて揃っています。</span><span class="sxs-lookup"><span data-stu-id="2ea26-129">It has everything you need.</span></span>

<span data-ttu-id="2ea26-130">.NET Framework を使用していて、.NET SDK を使用して**いない**場合は、 [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)を Windows Server にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ea26-130">If you are using .NET Framework and you are **not** using the .NET SDK, then you will need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="2ea26-131">インストーラーで、 **[.net デスクトップビルドツール]** を選択し、インストーラーメニューの右側にある **F#コンパイラ**コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ea26-131">In the installer, select **.NET desktop build tools** and then select the **F# compiler** component on the right side of the installer menu.</span></span>
