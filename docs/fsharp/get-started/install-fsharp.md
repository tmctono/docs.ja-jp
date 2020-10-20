---
title: F# をインストールする
description: 'さまざまな方法で F # をインストールする方法について説明します。'
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224282"
---
# <a name="install-f"></a><span data-ttu-id="2c21c-103">F のインストール\#</span><span class="sxs-lookup"><span data-stu-id="2c21c-103">Install F\#</span></span>

<span data-ttu-id="2c21c-104">F # は、環境に応じて複数の方法でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2c21c-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="2c21c-105">Visual Studio を使用して F # をインストールする</span><span class="sxs-lookup"><span data-stu-id="2c21c-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="2c21c-106">[Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)を初めてダウンロードする場合は、最初に Visual Studio インストーラーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2c21c-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="2c21c-107">インストーラーから適切なエディションの Visual Studio をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2c21c-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="2c21c-108">Visual Studio が既にインストールされている場合は、F # を追加するエディションの横にある [ **変更** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c21c-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="2c21c-109">[ワークロード] ページで、 **ASP.NET および web 開発** ワークロードを選択します。これには ASP.NET Core プロジェクトの F # と .net Core のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2c21c-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="2c21c-110">右下隅にある [ **変更** ] を選択して、選択したすべてのものをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2c21c-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="2c21c-111">その後、[Visual Studio インストーラーで **起動** ] を選択すると、F # を使用して Visual Studio を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2c21c-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="2c21c-112">Visual Studio Code を使用して F # をインストールする</span><span class="sxs-lookup"><span data-stu-id="2c21c-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="2c21c-113">[Git](https://git-scm.com/download)がインストールされ、パスに使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c21c-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="2c21c-114">`git --version`コマンドプロンプトで「 **」** と入力し、enter キーを押すと、正しくインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2c21c-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="2c21c-115">[.NET Core SDK](https://dotnet.microsoft.com/download)と[Visual Studio Code](https://code.visualstudio.com)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2c21c-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="2c21c-116">拡張機能のアイコンを選択し、"Ionide" を検索します。</span><span class="sxs-lookup"><span data-stu-id="2c21c-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="2c21c-117">Visual Studio Code で F # をサポートするために必要なプラグインは、 [Ionide fsharp.core](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)だけです。</span><span class="sxs-lookup"><span data-stu-id="2c21c-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="2c21c-118">ただし、Ionide をインストールして、[偽](https://fake.build/)[の](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)サポートと[Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)を取得し、[パケット](https://fsprojects.github.io/Paket/)のサポートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="2c21c-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="2c21c-119">フェイクとパケットは、プロジェクトをビルドし、依存関係を管理するための追加の F # コミュニティツールです。</span><span class="sxs-lookup"><span data-stu-id="2c21c-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="2c21c-120">Visual Studio for Mac を使用して F # をインストールする</span><span class="sxs-lookup"><span data-stu-id="2c21c-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="2c21c-121">F # は、選択した構成に関係なく、既定で [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2c21c-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="2c21c-122">インストールが完了したら、[ **Visual Studio の開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c21c-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="2c21c-123">MacOS で Finder を使用して Visual Studio を開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="2c21c-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="2c21c-124">ビルドサーバーに F # をインストールする</span><span class="sxs-lookup"><span data-stu-id="2c21c-124">Install F# on a build server</span></span>

<span data-ttu-id="2c21c-125">.Net Core または .net SDK を使用して .NET Framework を使用している場合は、単に .NET SDK をビルドサーバーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c21c-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="2c21c-126">必要なものがすべて揃っています。</span><span class="sxs-lookup"><span data-stu-id="2c21c-126">It has everything you need.</span></span>

<span data-ttu-id="2c21c-127">.NET Framework を使用していて、.NET SDK を使用して **いない** 場合は、 [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) を Windows Server にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c21c-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="2c21c-128">インストーラーで、[ **.net デスクトップビルドツール**] を選択し、インストーラーメニューの右側にある **F # コンパイラ** コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="2c21c-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
