---
title: Visual Studio for Mac を使用した完全な .NET Core ソリューションの構築
description: この記事では、再利用可能なライブラリと単体テストを含む .NET Core ソリューションの構築方法を示します。
ms.date: 12/19/2019
ms.openlocfilehash: dea23da33912de849f0dcbe1e2f6fa3edb3a5e24
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215199"
---
# <a name="build-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="1919a-103">Visual Studio for Mac を使用した macOS での完全な .NET Core ソリューションの構築</span><span class="sxs-lookup"><span data-stu-id="1919a-103">Build a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="1919a-104">Visual Studio for Mac では、.NET Core アプリケーション開発用の機能をすべて備えた統合開発環境 (IDE) が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="1919a-105">この記事では、再利用可能なライブラリと単体テストを含む .NET Core ソリューションの構築方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1919a-105">This article walks you through building a .NET Core solution that includes a reusable library and unit testing.</span></span>

<span data-ttu-id="1919a-106">このチュートリアルでは、ユーザーが入力した検索語とテキスト文字列を受け入れ、クラス ライブラリでメソッドを使用した場合に文字列に検索語が表示される回数をカウントし、ユーザーに結果を返すアプリケーションの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1919a-106">This tutorial shows you how to create an application that accepts a search word and a string of text from the user, counts the number of times the search word appears in the string using a method in a class library, and returns the result to the user.</span></span> <span data-ttu-id="1919a-107">ソリューションには、単体テストの概念を紹介するため、クラス ライブラリの単体テストも含まれています。</span><span class="sxs-lookup"><span data-stu-id="1919a-107">The solution also includes unit testing for the class library as an introduction to unit testing concepts.</span></span> <span data-ttu-id="1919a-108">完全なサンプルでチュートリアルを続行する場合は、[サンプル ソリューション](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="1919a-108">If you prefer to proceed through the tutorial with a complete sample, download the [sample solution](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter).</span></span> <span data-ttu-id="1919a-109">ダウンロード方法については、「[サンプルおよびチュートリアル](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1919a-109">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

> [!NOTE]
> <span data-ttu-id="1919a-110">お客様のフィードバックは非常に貴重です。</span><span class="sxs-lookup"><span data-stu-id="1919a-110">Your feedback is highly valued.</span></span> <span data-ttu-id="1919a-111">次の 2 つの方法で Visual Studio for Mac の開発チームにフィードバックを送信できます。</span><span class="sxs-lookup"><span data-stu-id="1919a-111">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> - <span data-ttu-id="1919a-112">Visual Studio for Mac で、メニューから **[ヘルプ]**  >  **[問題の報告]** の順に選択するか、ようこそ画面から **[問題の報告]** を選択して、バグ報告を提出するためのウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="1919a-112">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="1919a-113">お客様のフィードバックは、[開発者コミュニティ](https://developercommunity.visualstudio.com/spaces/41/index.html) ポータルで追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="1919a-113">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html) portal.</span></span>
> - <span data-ttu-id="1919a-114">提案するには、メニューから **[ヘルプ]**  >  **[提案の送信]** の順に選択するか、ようこそ画面から **[提案の送信]** を選択し、[Visual Studio for Mac の開発者コミュニティの Web ページ](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)に移動します。</span><span class="sxs-lookup"><span data-stu-id="1919a-114">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1919a-115">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1919a-115">Prerequisites</span></span>

- [<span data-ttu-id="1919a-116">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="1919a-116">.NET Core SDK 3.1 or later</span></span>](https://dotnet.microsoft.com/download)
- [<span data-ttu-id="1919a-117">Visual Studio 2019 for Mac</span><span class="sxs-lookup"><span data-stu-id="1919a-117">Visual Studio 2019 for Mac</span></span>](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

<span data-ttu-id="1919a-118">前提条件の詳細については、[.NET Core の依存関係と要件](../install/dependencies.md?pivots=os-macos)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1919a-118">For more information on prerequisites, see the [.NET Core dependencies and requirements](../install/dependencies.md?pivots=os-macos).</span></span> <span data-ttu-id="1919a-119">Visual Studio 2019 for Mac の完全なシステム要件については、「[Visual Studio 2019 for Mac 製品ファミリのシステム要件](/visualstudio/productinfo/vs2019-system-requirements-mac)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1919a-119">For the full system requirements of Visual Studio 2019 for Mac, see [Visual Studio 2019 for Mac Product Family System Requirements](/visualstudio/productinfo/vs2019-system-requirements-mac).</span></span>

## <a name="building-a-library"></a><span data-ttu-id="1919a-120">ライブラリのビルド</span><span class="sxs-lookup"><span data-stu-id="1919a-120">Building a library</span></span>

1. <span data-ttu-id="1919a-121">スタート ウィンドウで、 **[新しいプロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-121">On the start window, select **New Project**.</span></span> <span data-ttu-id="1919a-122">**[新しいプロジェクト]** ダイアログで、 **[.NET Core]** ノードの下にある **[.NET Standard ライブラリ]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-122">In the **New Project** dialog under the **.NET Core** node, select the **.NET Standard Library** template.</span></span> <span data-ttu-id="1919a-123">このコマンドより、.NET Core を対象とする .NET Standard ライブラリと、[.NET Standard](../../standard/net-standard.md) のバージョン 2.1 をサポートするその他の .NET 実装が作成されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-123">This command creates a .NET Standard library that targets .NET Core as well as any other .NET implementation that supports version 2.1 of the [.NET Standard](../../standard/net-standard.md).</span></span> <span data-ttu-id="1919a-124">複数のバージョンの .NET Core SDK がインストールされている場合は、お使いのライブラリに異なるバージョンの .NET Standard を選択できます。</span><span class="sxs-lookup"><span data-stu-id="1919a-124">If you have multiple versions of the .NET Core SDK installed, you can choose different versions of .NET Standard for your library.</span></span> <span data-ttu-id="1919a-125">[.NET Standard 2.1] を選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-125">Choose ".NET Standard 2.1" and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-126">![Visual Studio for Mac の [新しいプロジェクト] ダイアログ](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-126">![Visual Studio for Mac New project dialog](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)</span></span>

1. <span data-ttu-id="1919a-127">プロジェクトには "TextUtils" ("Text Utilities" の短い名前)、ソリューションには "WordCounter" という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1919a-127">Name the project "TextUtils" (a short name for "Text Utilities") and the solution "WordCounter".</span></span> <span data-ttu-id="1919a-128">**[ソリューション ディレクトリ内にプロジェクト ディレクトリを作成します]** チェック ボックスはそのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="1919a-128">Leave **Create a project directory within the solution directory** checked.</span></span> <span data-ttu-id="1919a-129">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-129">Select **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-130">![Visual Studio for Mac の [新しいプロジェクト] ダイアログのオプション](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-130">![Visual Studio for Mac New project dialog options](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)</span></span>

1. <span data-ttu-id="1919a-131">**[ソリューション]** パッドで、`TextUtils` ノードを展開し、テンプレートで提供される *Class1.cs* というクラス ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="1919a-131">In the **Solution** pad, expand the `TextUtils` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="1919a-132">Ctrl キーを押しながらそのファイルをクリックし、コンテキスト メニューから **[名前の変更]** を選択して、ファイル名を *WordCount.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="1919a-132">Ctrl-click the file, select **Rename** from the context menu, and rename the file to *WordCount.cs*.</span></span> <span data-ttu-id="1919a-133">ファイルを開き、内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1919a-133">Open the file and replace the contents with the following code:</span></span>

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]

1. <span data-ttu-id="1919a-134">ファイルを保存します。その場合、3 つの異なる方法 (キーボード ショートカット <kbd>&#8984;</kbd>+<kbd>s</kbd> を使用する、メニューから **[ファイル]**  >  **[保存]** の順に選択する、Ctrl キーを押しながらファイルのタブをクリックしてコンテキスト メニューから **[保存]** を選択する) のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="1919a-134">Save the file by using any of three different methods: use the keyboard shortcut <kbd>&#8984;</kbd>+<kbd>s</kbd>, select **File** > **Save** from the menu, or ctrl-click on the file's tab and select **Save** from the contextual menu.</span></span> <span data-ttu-id="1919a-135">次のイメージは IDE ウィンドウを示しています。</span><span class="sxs-lookup"><span data-stu-id="1919a-135">The following image shows the IDE window:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-136">![クラス ライブラリ ファイルとメソッドが示された Visual Studio for Mac IDE ウィンドウ](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-136">![Visual Studio for Mac IDE window with class library file and method](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)</span></span>

1. <span data-ttu-id="1919a-137">IDE ウィンドウの下部の余白にある **[エラー]** を選択して、 **[エラー]** パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1919a-137">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="1919a-138">**[ビルド出力]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-138">Select the **Build Output** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-139">![[エラー] ボタンが示された Visual Studio Mac IDE の下部余白](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-139">![Bottom margin of the Visual Studio Mac IDE showing the Errors button](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)</span></span>

1. <span data-ttu-id="1919a-140">メニューから **[ビルド]**  >  **[すべてビルド]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-140">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="1919a-141">ソリューションがビルドされます。</span><span class="sxs-lookup"><span data-stu-id="1919a-141">The solution builds.</span></span> <span data-ttu-id="1919a-142">ビルド出力パネルに、ビルドが成功したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-142">The build output panel shows that the build is successful.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-143">![ビルドの成功メッセージが表示された、[エラー] パネルの Visual Studio Mac のビルド出力ウィンドウ](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-143">![Visual Studio Mac Build output pane of the Errors panel with Build successful message](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)</span></span>

## <a name="creating-a-test-project"></a><span data-ttu-id="1919a-144">テスト プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="1919a-144">Creating a test project</span></span>

<span data-ttu-id="1919a-145">単体テストでは、開発および公開時に自動化されたソフトウェア テストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-145">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="1919a-146">このチュートリアルで使用するテスト フレームワークは [xUnit (バージョン 2.4.0 以降)](https://xunit.github.io/) です。これは、以下の手順で xUnit テスト プロジェクトをソリューションに追加したときに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1919a-146">The testing framework that you use in this tutorial is [xUnit (version 2.4.0 or later)](https://xunit.github.io/), which is installed automatically when the xUnit test project is added to the solution in the following steps:</span></span>

1. <span data-ttu-id="1919a-147">**[ソリューション]** サイドバーで、Ctrl キーを押しながら `WordCounter` ソリューションをクリックし、 **[追加]**  >  **[新しいプロジェクトの追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-147">In the **Solution** sidebar, ctrl-click the `WordCounter` solution and select **Add** > **Add New Project**.</span></span>

1. <span data-ttu-id="1919a-148">**[新しいプロジェクト]** ダイアログで、 **[.NET Core]** ノードから **[テスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-148">In the **New Project** dialog, select **Tests** from the **.NET Core** node.</span></span> <span data-ttu-id="1919a-149">**[xUnit Test Project (xUnit テスト プロジェクト)]** を選択してから **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-149">Select the **xUnit Test Project** followed by **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-150">![xUnit テスト プロジェクトを作成する Visual Studio Mac の [新しいプロジェクト] ダイアログ](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-150">![Visual Studio Mac New Project dialog creating xUnit test project](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)</span></span>

1. <span data-ttu-id="1919a-151">複数のバージョンの .NET Core SDK がある場合は、このプロジェクトのバージョンを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1919a-151">If you have multiple versions of the .NET Core SDK, you'll need to select the version for this project.</span></span> <span data-ttu-id="1919a-152">**.NET Core 3.1** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-152">Select **.NET Core 3.1**.</span></span> <span data-ttu-id="1919a-153">新しいプロジェクトに "TestLibrary" という名前を付けて、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-153">Name the new project "TestLibrary" and select **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-154">![プロジェクト名を指定する Visual Studio Mac の [新しいプロジェクト] ダイアログ](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-154">![Visual Studio Mac New Project dialog providing project name](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)</span></span>

1. <span data-ttu-id="1919a-155">テスト ライブラリを `WordCount` クラスで使用するには、`TextUtils` プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="1919a-155">In order for the test library to work with the `WordCount` class, add a reference to the `TextUtils` project.</span></span> <span data-ttu-id="1919a-156">**[ソリューション]** サイドバーで、**TestLibrary** の下にある **[依存関係]** を Ctrl キーを押しながらクリックします。</span><span class="sxs-lookup"><span data-stu-id="1919a-156">In the **Solution** sidebar, ctrl-click **Dependencies** under **TestLibrary**.</span></span> <span data-ttu-id="1919a-157">コンテキスト メニューから **[参照の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-157">Select **Edit References** from the context menu.</span></span>

1. <span data-ttu-id="1919a-158">**[参照の編集]** ダイアログで、 **[プロジェクト]** タブの **[TextUtils]** プロジェクトを選択します。 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-158">In the **Edit References** dialog, select the **TextUtils** project on the **Projects** tab. Select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-159">![Visual Studio Mac の [参照の編集] ダイアログ](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-159">![Visual Studio Mac Edit References dialog](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)</span></span>

1. <span data-ttu-id="1919a-160">**[TestLibrary]** プロジェクトで、*UnitTest1.cs* ファイルの名前を *TextUtilsTests.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="1919a-160">In the **TestLibrary** project, rename the *UnitTest1.cs* file to *TextUtilsTests.cs*.</span></span>

1. <span data-ttu-id="1919a-161">そのファイルを開き、コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1919a-161">Open the file and replace the code with the following code:</span></span>

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");

               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   <span data-ttu-id="1919a-162">次のイメージは、単体テスト コードが配置済みの IDE を示しています。</span><span class="sxs-lookup"><span data-stu-id="1919a-162">The following image shows the IDE with the unit test code in place.</span></span> <span data-ttu-id="1919a-163">`Assert.NotEqual` ステートメントに注目してください。</span><span class="sxs-lookup"><span data-stu-id="1919a-163">Pay attention to the `Assert.NotEqual` statement.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-164">![IDE のメイン ウィンドウでの Visual Studio for Mac の最初の単体テスト](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-164">![Visual Studio for Mac Initial unit test in the IDE main window](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)</span></span>

   <span data-ttu-id="1919a-165">新しいテストを一度失敗させてテスト ロジックが正しいことを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1919a-165">It's important to make a new test fail once to confirm its testing logic is correct.</span></span> <span data-ttu-id="1919a-166">メソッドは "Jack" (先頭が大文字) という名前と、"Jack" および "jack" (先頭が大文字のものと小文字のもの) を含む文字列を渡します。</span><span class="sxs-lookup"><span data-stu-id="1919a-166">The method passes in the name "Jack" (uppercase) and a string with "Jack" and "jack" (uppercase and lowercase).</span></span> <span data-ttu-id="1919a-167">`GetWordCount` メソッドが正しく機能している場合は、検索語の 2 つのインスタンスのカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-167">If the `GetWordCount` method is working properly, it returns a count of two instances of the search word.</span></span> <span data-ttu-id="1919a-168">このテストを意図的に失敗させるには、まず、検索語 "Jack" の 2 つのインスタンスが `GetWordCount` メソッドで返されないことをアサートするテストを実装します。</span><span class="sxs-lookup"><span data-stu-id="1919a-168">In order to fail this test on purpose, you first implement the test asserting that two instances of the search word "Jack" aren't returned by the `GetWordCount` method.</span></span> <span data-ttu-id="1919a-169">次の手順に進んで意図的にテストを失敗させます。</span><span class="sxs-lookup"><span data-stu-id="1919a-169">Continue to the next step to fail the test on purpose.</span></span>

1. <span data-ttu-id="1919a-170">画面の右側の **[単体テスト]** パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1919a-170">Open the **Unit Tests** panel on the right side of the screen.</span></span> <span data-ttu-id="1919a-171">メニューから **[表示]**  >  **[テスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-171">Select **View** > **Tests** from the menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-172">![Visual Studio for Mac の [単体テスト] パネル](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-172">![Visual Studio for Mac Unit Tests panel](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)</span></span>

1. <span data-ttu-id="1919a-173">**[ドッキング]** アイコンをクリックして、パネルを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="1919a-173">Click the **Dock** icon to keep the panel open.</span></span> <span data-ttu-id="1919a-174">(次の画像で強調表示されています。)</span><span class="sxs-lookup"><span data-stu-id="1919a-174">(Highlighted in the following image.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-175">![Visual Studio for Mac の [単体テスト] パネルの [ドッキング] アイコン](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-175">![Visual Studio for Mac Unit Tests panel dock icon](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)</span></span>

1. <span data-ttu-id="1919a-176">**[すべて実行]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1919a-176">Click the **Run All** button.</span></span>

   <span data-ttu-id="1919a-177">テストは失敗します。これが正しい結果です。</span><span class="sxs-lookup"><span data-stu-id="1919a-177">The test fails, which is the correct result.</span></span> <span data-ttu-id="1919a-178">テスト メソッドは、`GetWordCount` メソッドに指定された文字列 "Jack jack" から `inputString` "Jack" の 2 つのインスタンスが返されないことをアサートします。</span><span class="sxs-lookup"><span data-stu-id="1919a-178">The test method asserts that two instances of the `inputString`, "Jack," aren't returned from the string "Jack jack" provided to the `GetWordCount` method.</span></span> <span data-ttu-id="1919a-179">単語の大文字と小文字は `GetWordCount` メソッドでは考慮されないため、2 つのインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-179">Since word casing was factored out in the `GetWordCount` method, two instances are returned.</span></span> <span data-ttu-id="1919a-180">2 *is not equal to* 2 というアサーションは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1919a-180">The assertion that 2 *is not equal to* 2 fails.</span></span> <span data-ttu-id="1919a-181">これは正しい結果であり、テストのロジックは適切です。</span><span class="sxs-lookup"><span data-stu-id="1919a-181">This result is the correct outcome, and the logic of our test is good.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-182">![Visual Studio for Mac のテスト失敗の表示](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-182">![Visual Studio for Mac test failure display](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)</span></span>

1. <span data-ttu-id="1919a-183">`Assert.NotEqual` から `Assert.Equal` に変更して `IgnoreCasing` テスト メソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="1919a-183">Modify the `IgnoreCasing` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="1919a-184">ファイルを保存します。その場合、キーボード ショートカット <kbd>Ctrl</kbd>+<kbd>s</kbd> を使用するか、メニューから **[ファイル]**  >  **[保存]** の順に選択するか、Ctrl キーを押しながらファイルのタブをクリックしてコンテキスト メニューから **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-184">Save the file by using the keyboard shortcut <kbd>Ctrl</kbd>+<kbd>s</kbd>, **File** > **Save** from the menu, or ctrl-clicking on the file's tab and selecting **Save** from the context menu.</span></span>

   <span data-ttu-id="1919a-185">`searchWord` "Jack" は `GetWordCount` に渡された `inputString` "Jack jack" を含む 2 つのインスタンスを返すことが予想されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-185">You expect that the `searchWord` "Jack" returns two instances with `inputString` "Jack jack" passed into `GetWordCount`.</span></span> <span data-ttu-id="1919a-186">**[単体テスト]** パネルの **[テストの実行]** ボタン、または画面下部の **[テスト結果]** パネルの **[テストの再実行]** ボタンをクリックして、テストを再実行します。</span><span class="sxs-lookup"><span data-stu-id="1919a-186">Run the test again by clicking the **Run Tests** button in the **Unit Tests** panel or the **Rerun Tests** button in the **Test Results** panel at the bottom of the screen.</span></span> <span data-ttu-id="1919a-187">テストに合格します。</span><span class="sxs-lookup"><span data-stu-id="1919a-187">The test passes.</span></span> <span data-ttu-id="1919a-188">文字列 "Jack jack" (大文字と小文字の区別は無視) に "Jack" のインスタンスが 2 つあり、テスト アサーションは `true` です。</span><span class="sxs-lookup"><span data-stu-id="1919a-188">There are two instances of "Jack" in the string "Jack jack" (ignoring casing), and the test assertion is `true`.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-189">![Visual Studio for Mac のテスト成功の表示](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-189">![Visual Studio for Mac tests pass display](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span></span>

1. <span data-ttu-id="1919a-190">`Fact` での個々の戻り値のテストは、単体テストで実行できることのほんの一部に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="1919a-190">Testing individual return values with a `Fact` is only the beginning of what you can do with unit testing.</span></span> <span data-ttu-id="1919a-191">別の強力な手法では、`Theory` を使用して一度に複数の値をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="1919a-191">Another powerful technique allows you to test several values at once using a `Theory`.</span></span> <span data-ttu-id="1919a-192">次のメソッドを `TextUtils_GetWordCountShould` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="1919a-192">Add the following method to your `TextUtils_GetWordCountShould` class.</span></span> <span data-ttu-id="1919a-193">このメソッドを追加すると、クラスのメソッドは 2 つになります。</span><span class="sxs-lookup"><span data-stu-id="1919a-193">You have two methods in the class after you add this method:</span></span>

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count,
                                       string searchWord,
                                       string inputString)
   {
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   <span data-ttu-id="1919a-194">`CountInstancesCorrectly` は、`GetWordCount` メソッドが正しくカウントすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1919a-194">The `CountInstancesCorrectly` checks that the `GetWordCount` method counts correctly.</span></span> <span data-ttu-id="1919a-195">`InlineData` は確認するカウント、検索語、および入力文字列を示します。</span><span class="sxs-lookup"><span data-stu-id="1919a-195">The `InlineData` provides a count, a search word, and an input string to check.</span></span> <span data-ttu-id="1919a-196">テスト メソッドはデータの行ごとに一度実行されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-196">The test method runs once for each line of data.</span></span> <span data-ttu-id="1919a-197">繰り返しますが、データのカウントが正しく、値が `GetWordCount` メソッドで返されるカウントと一致することがわかっている場合でも、まず、`Assert.NotEqual` を使用して失敗をアサートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1919a-197">Note once again that you're asserting a failure first by using `Assert.NotEqual`, even when you know that the counts in the data are correct and that the values match the counts returned by the `GetWordCount` method.</span></span> <span data-ttu-id="1919a-198">意図的にテストを失敗させる手順を実行するのは、最初は時間の無駄と思えるかもしれませんが、まず、テストを失敗させてロジックを確認することはテストのロジックを確認するうえで重要なことです。</span><span class="sxs-lookup"><span data-stu-id="1919a-198">Performing the step of failing the test on purpose might seem like a waste of time at first, but checking the logic of the test by failing it first is an important check on the logic of your tests.</span></span> <span data-ttu-id="1919a-199">失敗させようとしたのに成功するテスト メソッドがある場合、そのテストのロジックにバグがあります。</span><span class="sxs-lookup"><span data-stu-id="1919a-199">When you come across a test method that passes when you expect it to fail, you've found a bug in the logic of the test.</span></span> <span data-ttu-id="1919a-200">テスト メソッドを作成するたびに、この手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1919a-200">It's worth the effort to take this step every time you create a test method.</span></span>

1. <span data-ttu-id="1919a-201">ファイルを保存し、もう一度テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="1919a-201">Save the file and run the tests again.</span></span> <span data-ttu-id="1919a-202">大文字と小文字のテストは成功しますが、3 つのカウント テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1919a-202">The casing test passes but the three count tests fail.</span></span> <span data-ttu-id="1919a-203">これは予想したとおりの結果です。</span><span class="sxs-lookup"><span data-stu-id="1919a-203">This outcome is exactly what you expect to happen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-204">![Visual Studio for Mac の予測されるテスト失敗](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-204">![Visual Studio for Mac expected test failure](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)</span></span>

1. <span data-ttu-id="1919a-205">`Assert.NotEqual` から `Assert.Equal` に変更して `CountInstancesCorrectly` テスト メソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="1919a-205">Modify the `CountInstancesCorrectly` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="1919a-206">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="1919a-206">Save the file.</span></span> <span data-ttu-id="1919a-207">テストをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="1919a-207">Run the tests again.</span></span> <span data-ttu-id="1919a-208">すべてのテストに成功します。</span><span class="sxs-lookup"><span data-stu-id="1919a-208">All tests pass.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-209">![Visual Studio for Mac の予測されるテスト成功](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-209">![Visual Studio for Mac expected test passes](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)</span></span>

## <a name="adding-a-console-app"></a><span data-ttu-id="1919a-210">コンソール アプリの追加</span><span class="sxs-lookup"><span data-stu-id="1919a-210">Adding a console app</span></span>

1. <span data-ttu-id="1919a-211">**[ソリューション]** サイドバーで、Ctrl キーを押しながら `WordCounter` ソリューションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1919a-211">In the **Solution** sidebar, ctrl-click the `WordCounter` solution.</span></span> <span data-ttu-id="1919a-212">**[.NET Core]**  >  **[アプリ]** テンプレートの順に移動してテンプレートを選択し、新しい**コンソール アプリケーション**プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="1919a-212">Add a new **Console Application** project by selecting the template from the **.NET Core** > **App** templates.</span></span> <span data-ttu-id="1919a-213">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-213">Select **Next**.</span></span> <span data-ttu-id="1919a-214">プロジェクトに **WordCounterApp** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1919a-214">Name the project **WordCounterApp**.</span></span> <span data-ttu-id="1919a-215">**[作成]** を選択し、ソリューションでプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1919a-215">Select **Create** to create the project in the solution.</span></span>

1. <span data-ttu-id="1919a-216">**[ソリューション]** サイドバーで、新しい **WordCounterApp** プロジェクトの **[依存関係]** ノードを Ctrl キーを押しながらクリックします。</span><span class="sxs-lookup"><span data-stu-id="1919a-216">In the **Solutions** sidebar, ctrl-click the **Dependencies** node of the new **WordCounterApp** project.</span></span> <span data-ttu-id="1919a-217">**[参照の編集]** ダイアログで、**TextUtils** にチェック マークを付けて **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-217">In the **Edit References** dialog, check **TextUtils** and select **OK**.</span></span>

1. <span data-ttu-id="1919a-218">*Program.cs* ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1919a-218">Open the *Program.cs* file.</span></span> <span data-ttu-id="1919a-219">このコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1919a-219">Replace the code with the following code:</span></span>

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]

1. <span data-ttu-id="1919a-220">Ctrl キーを押しながら `WordCounterApp` プロジェクトをクリックし、コンテキスト メニューから **[プロジェクトの実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-220">Ctrl-click on the `WordCounterApp` project and select **Run project** from the context menu.</span></span> <span data-ttu-id="1919a-221">アプリを実行する際に、コンソール ウィンドウで入力を求めるメッセージが表示されたら、検索語と入力文字列の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="1919a-221">When you run the app, provide values for the search word and input string at the prompts in the console window.</span></span> <span data-ttu-id="1919a-222">アプリには、文字列での検索語の表示回数が示されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-222">The app indicates the number of times the search word appears in the string.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-223">![アプリが実行中であることを示す Visual Studio for Mac のコンソール ウィンドウ](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-223">![Visual Studio for Mac console window showing your app running](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)</span></span>

1. <span data-ttu-id="1919a-224">確認する最後の機能は、Visual Studio for Mac でのデバッグです。</span><span class="sxs-lookup"><span data-stu-id="1919a-224">The last feature to explore is debugging with Visual Studio for Mac.</span></span> <span data-ttu-id="1919a-225">`Console.WriteLine` ステートメントにブレークポイントを設定します。23 行目の左余白を選択すると、コード行の横に赤い丸が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-225">Set a breakpoint on the `Console.WriteLine` statement: Select in the left margin of line 23, and you see a red circle appear next to the line of code.</span></span> <span data-ttu-id="1919a-226">コード行の任意の場所を選択し、メニューから **[実行]**  >  **[ブレークポイントの設定/解除]** の順に選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="1919a-226">Alternatively, select anywhere on the line of code and select **Run** > **Toggle Breakpoint** from the menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-227">![Visual Studio for Mac のブレークポイントの設定](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-227">![Visual Studio for Mac breakpoint set](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)</span></span>

1. <span data-ttu-id="1919a-228">Ctrl キーを押しながら `WordCounterApp` プロジェクトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1919a-228">ctrl-click the `WordCounterApp` project.</span></span> <span data-ttu-id="1919a-229">コンテキスト メニューから **[プロジェクトのデバッグを開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-229">Select **Start Debugging Project** from the context menu.</span></span> <span data-ttu-id="1919a-230">アプリが実行されたら、検索語 "cat" と検索文字列 "The dog chased the cat, but the cat escaped"</span><span class="sxs-lookup"><span data-stu-id="1919a-230">When the app runs, enter the search word "cat" and "The dog chased the cat, but the cat escaped."</span></span> <span data-ttu-id="1919a-231">を入力します。</span><span class="sxs-lookup"><span data-stu-id="1919a-231">for the string to search.</span></span> <span data-ttu-id="1919a-232">`Console.WriteLine` ステートメントに達した時点でプログラムの実行が停止します。その後、ステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-232">When the `Console.WriteLine` statement is reached, program execution halts before the statement is executed.</span></span> <span data-ttu-id="1919a-233">**[ローカル]** タブで、`searchWord`、`inputString`、`wordCount`、および `pluralChar` の各値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1919a-233">In the **Locals** tab, you can see the `searchWord`, `inputString`, `wordCount`, and `pluralChar` values.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-234">![Visual Studio for Mac の停止されたデバッガー プログラムの実行](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-234">![Visual Studio for Mac debugger program execution stopped](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)</span></span>

1. <span data-ttu-id="1919a-235">**[イミディエイト]** ウィンドウで、「wordCount = 999;」と入力してから Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1919a-235">In the **Immediate** pane, type "wordCount = 999;" and press Enter.</span></span> <span data-ttu-id="1919a-236">このコマンドで、`wordCount` 変数に 999 という意味のない値が割り当てられます。これは、デバッグ中に変数値の置き換えが可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="1919a-236">This command assigns a nonsense value of 999 to the `wordCount` variable showing that you can replace variable values while debugging.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-237">![Visual Studio for Mac の [イミディエイト] ウィンドウで値を変更する](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-237">![Visual Studio for Mac changing values in the immediate window](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)</span></span>

1. <span data-ttu-id="1919a-238">ツールバーで、*続行*矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1919a-238">In the toolbar, click the *continue* arrow.</span></span> <span data-ttu-id="1919a-239">コンソール ウィンドウの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="1919a-239">Look at the output in the console window.</span></span> <span data-ttu-id="1919a-240">アプリのデバッグ時に設定した 999 という不適切な値が報告されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-240">It reports the incorrect value of 999 that you set when you were debugging the app.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-241">![Visual Studio for Mac ツールバーの続行ボタン](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-241">![Visual Studio for Mac continue button in the toolbar](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1919a-242">![Visual Studio for Mac のコンソール ウィンドウの出力](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)</span><span class="sxs-lookup"><span data-stu-id="1919a-242">![Visual Studio for Mac console window output](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)</span></span>

<span data-ttu-id="1919a-243">同じプロセスを使用して、単体テスト プロジェクトを使用してコードをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="1919a-243">You can use the same process to debug code using your unit test project.</span></span> <span data-ttu-id="1919a-244">WordCount アプリ プロジェクトを開始する代わりに、Ctrl キーを押しながら **[テスト ライブラリ]** プロジェクトをクリックし、コンテキスト メニューから **[プロジェクトのデバッグを開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1919a-244">Instead of starting the WordCount app project, ctrl-click the **Test Library** project, and select **Start Debugging Project** from the context menu.</span></span> <span data-ttu-id="1919a-245">デバッガーがアタッチされた状態で Visual Studio for Mac でテスト プロジェクトが開始されます。</span><span class="sxs-lookup"><span data-stu-id="1919a-245">Visual Studio for Mac starts your test project with the debugger attached.</span></span> <span data-ttu-id="1919a-246">実行は、テスト プロジェクトに追加したブレークポイント、または基になるライブラリ コードで停止します。</span><span class="sxs-lookup"><span data-stu-id="1919a-246">Execution will stop at any breakpoint you've added to the test project, or the underlying library code.</span></span>

## <a name="see-also"></a><span data-ttu-id="1919a-247">関連項目</span><span class="sxs-lookup"><span data-stu-id="1919a-247">See also</span></span>

- [<span data-ttu-id="1919a-248">Visual Studio 2019 for Mac リリース ノート</span><span class="sxs-lookup"><span data-stu-id="1919a-248">Visual Studio 2019 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2019-mac-relnotes)
