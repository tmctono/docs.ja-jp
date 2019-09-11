---
title: F# をインストールする
description: お客様の環境に基づいて、F# をインストールする方法について説明します。
ms.date: 09/05/2019
ms.openlocfilehash: dffa30eac0bdb59c85a66dca6cafd62b25daa572
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855804"
---
# <a name="install-f"></a><span data-ttu-id="13b38-103">F のインストール\#</span><span class="sxs-lookup"><span data-stu-id="13b38-103">Install F\#</span></span>

<span data-ttu-id="13b38-104">複数の方法で F# をインストールと、環境に応じてことができます。</span><span class="sxs-lookup"><span data-stu-id="13b38-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="13b38-105">Visual Studio を使用した F# のインストールします。</span><span class="sxs-lookup"><span data-stu-id="13b38-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="13b38-106">[Visual studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)を初めてダウンロードする場合は、最初に visual studio インストーラーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="13b38-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="13b38-107">インストーラーから適切な SKU の Visual Studio をインストールします。</span><span class="sxs-lookup"><span data-stu-id="13b38-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="13b38-108">既にインストールされている場合は、 **[変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13b38-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="13b38-109">次に、ワークロードの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="13b38-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="13b38-110">選択**ASP.NET および web 開発**F# サポートおよび ASP.NET Core プロジェクトの .NET Core のサポートがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="13b38-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="13b38-111">次に、右下にある **[変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13b38-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="13b38-112">これにより、選択したすべてのものがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="13b38-112">This will install everything you have selected.</span></span> <span data-ttu-id="13b38-113">クリックして、F# 言語サポートと Visual Studio 2017 を開くことができますし、**起動**します。</span><span class="sxs-lookup"><span data-stu-id="13b38-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="13b38-114">Visual Studio for Mac F#と共にインストールする</span><span class="sxs-lookup"><span data-stu-id="13b38-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="13b38-115">既定で F# がインストールされている[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)、選択した構成に関係なく。</span><span class="sxs-lookup"><span data-stu-id="13b38-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="13b38-116">インストールが完了したら、[Visual Studio の起動] を選択します。</span><span class="sxs-lookup"><span data-stu-id="13b38-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="13b38-117">また、macOS で Finder を使用して起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="13b38-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="13b38-118">Visual Studio Code で F# のインストールします。</span><span class="sxs-lookup"><span data-stu-id="13b38-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="13b38-119">プロジェクトテンプレートを使用するには、 [git をインストール](https://git-scm.com/download)し、パスに使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13b38-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="13b38-120">コマンドプロンプトで「」 `git --version`と入力し、 **enter**キーを押すと、正しくインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="13b38-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="13b38-121">macOS</span><span class="sxs-lookup"><span data-stu-id="13b38-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="13b38-122">[Mono](https://www.mono-project.com)使用[F# Interactive](../tutorials/fsharp-interactive/index.md)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="13b38-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="13b38-123">MacOS に Mono をインストールする最も簡単な方法は、Homebrew を使用することです。</span><span class="sxs-lookup"><span data-stu-id="13b38-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="13b38-124">ターミナルに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="13b38-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="13b38-125">また、 [.NET Core SDK](https://dotnet.microsoft.com/download)もインストールします。</span><span class="sxs-lookup"><span data-stu-id="13b38-125">Also install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="13b38-126">Linux</span><span class="sxs-lookup"><span data-stu-id="13b38-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="13b38-127">[Mono](https://www.mono-project.com)使用[F# Interactive](../tutorials/fsharp-interactive/index.md)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="13b38-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="13b38-128">Debian または Ubuntu を使用している場合は、次のものを使用できます。</span><span class="sxs-lookup"><span data-stu-id="13b38-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="13b38-129">また、 [.NET Core SDK](https://dotnet.microsoft.com/download)もインストールします。</span><span class="sxs-lookup"><span data-stu-id="13b38-129">Also install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="13b38-130">Windows</span><span class="sxs-lookup"><span data-stu-id="13b38-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="13b38-131">インストール[F# のサポートを使用した Visual Studio](#install-f-with-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="13b38-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="13b38-132">これにより、書き込み、コンパイル、および F# コードの実行に必要なすべてのコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="13b38-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="13b38-133">また、 [.NET Core SDK](https://dotnet.microsoft.com/download)もインストールします。</span><span class="sxs-lookup"><span data-stu-id="13b38-133">Also install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

---

<span data-ttu-id="13b38-134">その後、 [Visual Studio Code](https://code.visualstudio.com)インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13b38-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="13b38-135">次に、[拡張機能] アイコンをクリックし、"Ionide" を検索します。</span><span class="sxs-lookup"><span data-stu-id="13b38-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="13b38-136">Visual Studio Code での F# サポートが必要な唯一のプラグイン[ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)します。</span><span class="sxs-lookup"><span data-stu-id="13b38-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="13b38-137">ただし、Ionide をインストールして、[偽](https://fsharp.github.io/FAKE/)[の](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)サポートと[Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)を取得し、[パケット](https://fsprojects.github.io/Paket/)のサポートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="13b38-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="13b38-138">偽の追加 F# コミュニティのツールをプロジェクトのビルドとの依存関係をそれぞれ管理は、パケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="13b38-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="13b38-139">ビルドF#サーバーへのインストール</span><span class="sxs-lookup"><span data-stu-id="13b38-139">Install F# on a Build Server</span></span>

<span data-ttu-id="13b38-140">.Net Core または .net SDK を使用して .NET Framework を使用している場合は、単に .NET SDK をビルドサーバーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13b38-140">If you are using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="13b38-141">必要なものがすべて揃っています。</span><span class="sxs-lookup"><span data-stu-id="13b38-141">It has everything you need.</span></span>

<span data-ttu-id="13b38-142">.NET Framework を使用していて、.NET SDK を使用して**いない**場合は、 [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)を Windows Server にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13b38-142">If you are using .NET Framework and you are **not** using the .NET SDK, then you will need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="13b38-143">インストーラーで、 **[.net デスクトップビルドツール]** を選択し、インストーラーメニューの右側にある **F#コンパイラ**コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="13b38-143">In the installer, select **.NET desktop build tools** and then select the **F# compiler** component on the right side of the installer menu.</span></span>
