---
title: Visual Studio for Mac を使用した macOS での .NET Core の概要
description: このトピックでは、Visual Studio for Mac と .NET Core を使用して、単純なコンソール アプリケーションをビルドする手順を示します。
author: mairaw
ms.date: 06/12/2017
ms.custom: seodec18
ms.openlocfilehash: 4467842c0b65ea536cc26601981d9fcc2bc68f2d
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300048"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="7cc52-103">Visual Studio for Mac を使用した macOS での .NET Core の概要</span><span class="sxs-lookup"><span data-stu-id="7cc52-103">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="7cc52-104">Visual Studio for Mac では、.NET Core アプリケーション開発用の機能をすべて備えた統合開発環境 (IDE) が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7cc52-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="7cc52-105">このトピックでは、Visual Studio for Mac と .NET Core を使用して、単純なコンソール アプリケーションをビルドする手順を示します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="7cc52-106">お客様のフィードバックは非常に貴重です。</span><span class="sxs-lookup"><span data-stu-id="7cc52-106">Your feedback is highly valued.</span></span> <span data-ttu-id="7cc52-107">次の 2 つの方法で Visual Studio for Mac の開発チームにフィードバックを送信できます。</span><span class="sxs-lookup"><span data-stu-id="7cc52-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="7cc52-108">Visual Studio for Mac で、メニューから **[ヘルプ]**  >  **[問題の報告]** の順に選択するか、ようこそ画面から **[問題の報告]** を選択して、バグ報告を提出するためのウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cc52-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="7cc52-109">お客様のフィードバックは、[開発者コミュニティ](https://developercommunity.visualstudio.com/spaces/8/index.html) ポータルで追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="7cc52-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="7cc52-110">提案するには、メニューから **[ヘルプ]**  >  **[提案の送信]** の順に選択するか、ようこそ画面から **[提案の送信]** を選択し、[Visual Studio for Mac の開発者コミュニティの Web ページ](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)に移動します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7cc52-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7cc52-111">Prerequisites</span></span>

<span data-ttu-id="7cc52-112">「[Mac における .NET Core の前提条件](../../core/macos-prerequisites.md)」のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7cc52-112">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="get-started"></a><span data-ttu-id="7cc52-113">作業開始</span><span class="sxs-lookup"><span data-stu-id="7cc52-113">Get started</span></span>

<span data-ttu-id="7cc52-114">必須コンポーネントと Visual Studio for Mac を既にインストールしている場合は、このセクションをスキップして、「[プロジェクトの作成](#creating-a-project)」に進みます。</span><span class="sxs-lookup"><span data-stu-id="7cc52-114">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="7cc52-115">以下の手順に従って、必須コンポーネントと Visual Studio for Mac をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7cc52-115">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="7cc52-116">[Visual Studio for Mac インストーラー](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7cc52-116">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="7cc52-117">インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-117">Run the installer.</span></span> <span data-ttu-id="7cc52-118">使用許諾契約書を読み、同意します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-118">Read and accept the license agreement.</span></span> <span data-ttu-id="7cc52-119">インストール中に、Xamarin (クロスプラットフォーム モバイル アプリ開発テクノロジ) をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="7cc52-119">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="7cc52-120">.NET Core の開発の場合、Xamarin とその関連コンポーネントのインストールは省略できます。</span><span class="sxs-lookup"><span data-stu-id="7cc52-120">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="7cc52-121">Visual Studio for Mac のインストール プロセスのチュートリアルについては、[Visual Studio for Mac のドキュメント](/visualstudio/mac/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7cc52-121">For a walk-through of the Visual Studio for Mac install process, see [Visual Studio for Mac documentation](/visualstudio/mac/).</span></span> <span data-ttu-id="7cc52-122">インストールが完了したら、Visual Studio for Mac IDE を起動します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-122">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="7cc52-123">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="7cc52-123">Creating a project</span></span>

1. <span data-ttu-id="7cc52-124">ようこそ画面で **[新しいプロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-124">Select **New Project** on the Welcome screen.</span></span>

   ![Visual Studio for Mac のようこそ画面の [新しいプロジェクト] ボタン](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. <span data-ttu-id="7cc52-126">**[新しいプロジェクト]** ダイアログで、 **[.NET Core]** ノードの下にある **[アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-126">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="7cc52-127">**[コンソール アプリケーション]** テンプレートを選択してから **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-127">Select the **Console Application** template followed by **Next**.</span></span>

   ![新しいプロジェクト テンプレートのリスト](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. <span data-ttu-id="7cc52-129">**[プロジェクト名]** には「HelloWorld」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-129">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="7cc52-130">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-130">Select **Create**.</span></span>

   ![[Configure your new Console Application (新しいコンソール アプリケーションの構成)] ダイアログ](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. <span data-ttu-id="7cc52-132">プロジェクトの依存関係が復元されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="7cc52-132">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="7cc52-133">プロジェクトには、`Main` メソッドを持つ `Program` クラスを含む *Program.cs* という C# ファイルが 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="7cc52-133">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="7cc52-134">`Console.WriteLine` ステートメントは、アプリの実行時に</span><span class="sxs-lookup"><span data-stu-id="7cc52-134">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="7cc52-135">コンソールに "Hello World!" と出力します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-135">to the console when the app is run.</span></span>

   ![Program.cs ファイルが開かれた状態のメイン ウィンドウ](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a><span data-ttu-id="7cc52-137">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="7cc52-137">Run the application</span></span>

<span data-ttu-id="7cc52-138">アプリは、<kbd>F5</kbd> キーを使用する場合はデバッグ モードで、<kbd>Ctrl</kbd> + <kbd>F5</kbd> キーを使用する場合はリリース モードで実行します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-138">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![[アプリケーション出力] ウィンドウに Hello World! が表示された状態](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a><span data-ttu-id="7cc52-140">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7cc52-140">Next step</span></span>

<span data-ttu-id="7cc52-141">「[Visual Studio for Mac を使用した macOS での完全な .NET Core ソリューションの構築](using-on-mac-vs-full-solution.md)」トピックでは、再利用可能なライブラリと単体テストを含む完全な .NET Core ソリューションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7cc52-141">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
