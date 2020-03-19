---
title: F# をインストールする
description: さまざまな方法で F# をインストールする方法について説明します。
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401095"
---
# <a name="install-f"></a><span data-ttu-id="20161-103">F をインストールする\#</span><span class="sxs-lookup"><span data-stu-id="20161-103">Install F\#</span></span>

<span data-ttu-id="20161-104">F# は、環境に応じて複数の方法でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="20161-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="20161-105">F# をインストールする</span><span class="sxs-lookup"><span data-stu-id="20161-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="20161-106">初めて[Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)をダウンロードする場合は、最初に Visual Studio インストーラーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="20161-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="20161-107">インストーラーから適切なエディションの Visual Studio をインストールします。</span><span class="sxs-lookup"><span data-stu-id="20161-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="20161-108">Visual Studio が既にインストールされている場合は、F# を追加するエディションの横にある **[変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20161-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="20161-109">[ワークロード] ページで、ASP.NET コア プロジェクトの F# および .NET Core サポートを含む **、ASP.NETと Web 開発**ワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="20161-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="20161-110">右下隅にある [**変更]** を選択して、選択したすべてのものをインストールします。</span><span class="sxs-lookup"><span data-stu-id="20161-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="20161-111">その後、Visual Studio インストーラーで**起動**を選択して、F# で Visual Studio を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="20161-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="20161-112">F# をインストールする</span><span class="sxs-lookup"><span data-stu-id="20161-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="20161-113">パスに[git](https://git-scm.com/download)がインストールされ、使用可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20161-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="20161-114">コマンド プロンプトで入力し`git --version`**、Enter**キーを押すと、正しくインストールされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="20161-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="20161-115">[.NET コア SDK](https://dotnet.microsoft.com/download)と[Visual Studio コード](https://code.visualstudio.com)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="20161-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="20161-116">拡張機能アイコンを選択し、「Ionide」を検索します。</span><span class="sxs-lookup"><span data-stu-id="20161-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="20161-117">Visual Studio コードで F# のサポートに必要なプラグインは[、Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)だけです。</span><span class="sxs-lookup"><span data-stu-id="20161-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="20161-118">しかし, また、[フェイ](https://fake.build/)クサポートを取得するために[Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)をインストールし[、Paket](https://fsprojects.github.io/Paket/)のサポートを得るために[Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)を取得することができます.</span><span class="sxs-lookup"><span data-stu-id="20161-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="20161-119">FAKE と Paket は、プロジェクトをビルドし、依存関係を管理するための追加の F# コミュニティ ツールです。</span><span class="sxs-lookup"><span data-stu-id="20161-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="20161-120">Mac 用の Visual Studio で F# をインストールする</span><span class="sxs-lookup"><span data-stu-id="20161-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="20161-121">F# は、選択した構成に関係なく、[既定では、Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="20161-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="20161-122">インストールが完了したら **、[Visual Studio の起動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20161-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="20161-123">macOS のファインダーを使用して Visual Studio を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="20161-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="20161-124">ビルド サーバーに F# をインストールする</span><span class="sxs-lookup"><span data-stu-id="20161-124">Install F# on a build server</span></span>

<span data-ttu-id="20161-125">NET SDK を使用して .NET Core または .NET Framework を使用している場合は、ビルド サーバーに .NET SDK をインストールするだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="20161-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="20161-126">それはあなたが必要とするすべてを持っています。</span><span class="sxs-lookup"><span data-stu-id="20161-126">It has everything you need.</span></span>

<span data-ttu-id="20161-127">NET Framework を使用していて、.NET SDK を使用**していない**場合は、Windows サーバーに Visual [Studio ビルド ツール SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20161-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="20161-128">インストーラーで **、.NET デスクトップ ビルド ツール**を選択し、インストーラー メニューの右側にある**F# コンパイラ**コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="20161-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
