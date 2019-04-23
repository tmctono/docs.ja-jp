---
title: Visual Studio for Mac を使用した macOS での完全な .NET Core ソリューションの構築
description: このトピックでは、再利用可能なライブラリと単体テストを含む .NET Core ソリューションの構築方法を示します。
author: guardrex
ms.date: 06/12/2017
ms.custom: seodec18
ms.openlocfilehash: be0aebb1ac700de07a52c4c50383f45d1191b7f6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327751"
---
# <a name="building-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="c1a54-103">Visual Studio for Mac を使用した macOS での完全な .NET Core ソリューションの構築</span><span class="sxs-lookup"><span data-stu-id="c1a54-103">Building a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="c1a54-104">Visual Studio for Mac では、.NET Core アプリケーション開発用の機能をすべて備えた統合開発環境 (IDE) が提供されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="c1a54-105">このトピックでは、再利用可能なライブラリと単体テストを含む .NET Core ソリューションの構築方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-105">This topic walks you through building a .NET Core solution that includes a reusable library and unit testing.</span></span>

<span data-ttu-id="c1a54-106">このチュートリアルでは、ユーザーが入力した検索語とテキスト文字列を受け入れ、クラス ライブラリでメソッドを使用した場合に文字列に検索語が表示される回数をカウントし、ユーザーに結果を返すアプリケーションの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-106">This tutorial shows you how to create an application that accepts a search word and a string of text from the user, counts the number of times the search word appears in the string using a method in a class library, and returns the result to the user.</span></span> <span data-ttu-id="c1a54-107">ソリューションには、単体テストの概念を紹介するため、クラス ライブラリの単体テストも含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1a54-107">The solution also includes unit testing for the class library as an introduction to unit testing concepts.</span></span> <span data-ttu-id="c1a54-108">完全なサンプルでチュートリアルを続行する場合は、[サンプル ソリューション](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="c1a54-108">If you prefer to proceed through the tutorial with a complete sample, download the [sample solution](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter).</span></span> <span data-ttu-id="c1a54-109">ダウンロード方法については、「[サンプルおよびチュートリアル](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a54-109">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

> [!NOTE]
> <span data-ttu-id="c1a54-110">お客様のフィードバックは非常に貴重です。</span><span class="sxs-lookup"><span data-stu-id="c1a54-110">Your feedback is highly valued.</span></span> <span data-ttu-id="c1a54-111">次の 2 つの方法で Visual Studio for Mac の開発チームにフィードバックを送信できます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-111">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="c1a54-112">Visual Studio for Mac で、メニューから **[ヘルプ]** > **[問題の報告]** の順に選択するか、ようこそ画面から **[問題の報告]** を選択して、バグ報告を提出するためのウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-112">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="c1a54-113">お客様のフィードバックは、[開発者コミュニティ](https://developercommunity.visualstudio.com/spaces/41/index.html) ポータルで追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-113">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html) portal.</span></span>
> * <span data-ttu-id="c1a54-114">提案するには、メニューから **[ヘルプ]** > **[提案の送信]** の順に選択するか、ようこそ画面から **[提案の送信]** を選択し、[Visual Studio for Mac の開発者コミュニティの Web ページ](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)に移動します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-114">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c1a54-115">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c1a54-115">Prerequisites</span></span>

- <span data-ttu-id="c1a54-116">OpenSSL (.NET Core 1.1 が実行されている場合):「[Mac における .NET Core の前提条件](../macos-prerequisites.md)」のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c1a54-116">OpenSSL (if running .NET Core 1.1): See the [Prerequisites for .NET Core on Mac](../macos-prerequisites.md) topic.</span></span>
- [<span data-ttu-id="c1a54-117">.NET Core SDK 1.1 以降</span><span class="sxs-lookup"><span data-stu-id="c1a54-117">.NET Core SDK 1.1 or later</span></span>](https://www.microsoft.com/net/core#macos)
- [<span data-ttu-id="c1a54-118">Visual Studio 2017 for Mac</span><span class="sxs-lookup"><span data-stu-id="c1a54-118">Visual Studio 2017 for Mac</span></span>](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

<span data-ttu-id="c1a54-119">必須コンポーネントの詳細については、「[Mac における .NET Core の前提条件](../../core/macos-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a54-119">For more information on prerequisites, see the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md).</span></span> <span data-ttu-id="c1a54-120">Visual Studio 2017 for Mac の完全なシステム要件については、「[Visual Studio 2017 for Mac 製品ファミリのシステム要件](/visualstudio/productinfo/vs2017-system-requirements-mac)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c1a54-120">For the full system requirements of Visual Studio 2017 for Mac, see [Visual Studio 2017 for Mac Product Family System Requirements](/visualstudio/productinfo/vs2017-system-requirements-mac).</span></span>

## <a name="building-a-library"></a><span data-ttu-id="c1a54-121">ライブラリのビルド</span><span class="sxs-lookup"><span data-stu-id="c1a54-121">Building a library</span></span>

1. <span data-ttu-id="c1a54-122">ようこそ画面で、**[新しいプロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-122">On the Welcome screen, select **New Project**.</span></span> <span data-ttu-id="c1a54-123">**[新しいプロジェクト]** ダイアログで、**[.NET Core]** ノードの下にある **[.NET Standard ライブラリ]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-123">In the **New Project** dialog under the **.NET Core** node, select the **.NET Standard Library** template.</span></span> <span data-ttu-id="c1a54-124">これにより、.NET Core を対象とする .NET Standard ライブラリと、[.NET Standard](../../standard/net-standard.md) のバージョン 2.0 をサポートするその他の .NET 実装が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-124">This creates a .NET Standard library that targets .NET Core as well as any other .NET implementation that supports version 2.0 of the [.NET Standard](../../standard/net-standard.md).</span></span> <span data-ttu-id="c1a54-125">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-125">Select **Next**.</span></span>

   ![Visual Studio for Mac の [新しいプロジェクト] ダイアログ](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)

1. <span data-ttu-id="c1a54-127">プロジェクトには "TextUtils" ("Text Utilities" の短い名前)、ソリューションには "WordCounter" という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-127">Name the project "TextUtils" (a short name for "Text Utilities") and the solution "WordCounter".</span></span> <span data-ttu-id="c1a54-128">**[ソリューション ディレクトリ内にプロジェクト ディレクトリを作成します]** チェック ボックスはそのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-128">Leave **Create a project directory within the solution directory** checked.</span></span> <span data-ttu-id="c1a54-129">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-129">Select **Create**.</span></span>

   ![Visual Studio for Mac の [新しいプロジェクト] ダイアログのオプション](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)

1. <span data-ttu-id="c1a54-131">**[ソリューション]** サイドバーで、`TextUtils` ノードを展開し、テンプレートで提供される *Class1.cs* というクラス ファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-131">In the **Solution** sidebar, expand the `TextUtils` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="c1a54-132">ファイルを右クリックし、コンテキスト メニューから **[名前の変更]** を選択して、ファイル名を *WordCount.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-132">Right-click the file, select **Rename** from the context menu, and rename the file to *WordCount.cs*.</span></span> <span data-ttu-id="c1a54-133">ファイルを開き、内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-133">Open the file and replace the contents with the following code:</span></span>

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]

1. <span data-ttu-id="c1a54-134">ファイルを保存します。その場合、3 つの異なる方法 (キーボード ショートカット <kbd>&#8984;</kbd>+<kbd>s</kbd> キーを使用する、メニューから **[ファイル]** > **[保存]** の順に選択する、ファイルのタブを右クリックしてコンテキスト メニューから **[保存]** を選択する) のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-134">Save the file by using any of three different methods: use the keyboard shortcut <kbd>&#8984;</kbd>+<kbd>s</kbd>, select **File** > **Save** from the menu, or right-click on the file's tab and select **Save** from the contextual menu.</span></span> <span data-ttu-id="c1a54-135">次のイメージは IDE ウィンドウを示しています。</span><span class="sxs-lookup"><span data-stu-id="c1a54-135">The following image shows the IDE window:</span></span>

   ![クラス ライブラリ ファイルとメソッドが示された Visual Studio for Mac IDE ウィンドウ](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)

1. <span data-ttu-id="c1a54-137">IDE ウィンドウの下部の余白にある **[エラー]** を選択して、**[エラー]** パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-137">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="c1a54-138">**[ビルド出力]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-138">Select the **Build Output** button.</span></span>

   ![[エラー] ボタンが示された Visual Studio Mac IDE の下余白](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)

1. <span data-ttu-id="c1a54-140">メニューから **[ビルド]** > **[すべてビルド]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-140">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="c1a54-141">ソリューションがビルドされます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-141">The solution builds.</span></span> <span data-ttu-id="c1a54-142">ビルド出力パネルに、ビルドが成功したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-142">The build output panel shows that the build is successful.</span></span>

   ![ビルドの成功メッセージが表示された、[エラー] パネルの Visual Studio Mac のビルド出力ウィンドウ](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)

## <a name="creating-a-test-project"></a><span data-ttu-id="c1a54-144">テスト プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="c1a54-144">Creating a test project</span></span>

<span data-ttu-id="c1a54-145">単体テストでは、開発および公開時に自動化されたソフトウェア テストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-145">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="c1a54-146">このチュートリアルで使用するテスト フレームワークは [xUnit (バージョン 2.2.0 以降)](https://xunit.github.io/) です。これは、以下の手順で xUnit テスト プロジェクトをソリューションに追加したときに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-146">The testing framework that you use in this tutorial is [xUnit (version 2.2.0 or later)](https://xunit.github.io/), which is installed automatically when the xUnit test project is added to the solution in the following steps:</span></span>

1. <span data-ttu-id="c1a54-147">**[ソリューション]** サイドバーで、`WordCounter` ソリューション名を右クリックし、**[追加]** > **[新しいプロジェクトの追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-147">In the **Solution** sidebar, right-click the `WordCounter` solution and select **Add** > **Add New Project**.</span></span>

1. <span data-ttu-id="c1a54-148">**[新しいプロジェクト]** ダイアログで、**[.NET Core]** ノードから **[テスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-148">In the **New Project** dialog, select **Tests** from the **.NET Core** node.</span></span> <span data-ttu-id="c1a54-149">**[xUnit Test Project (xUnit テスト プロジェクト)]** を選択してから **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-149">Select the **xUnit Test Project** followed by **Next**.</span></span>

   ![xUnit テスト プロジェクトを作成する Visual Studio Mac の [新しいプロジェクト] ダイアログ](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)

1. <span data-ttu-id="c1a54-151">新しいプロジェクトに "TestLibrary" という名前を付けて、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-151">Name the new project "TestLibrary" and select **Create**.</span></span>

   ![プロジェクト名を指定する Visual Studio Mac の [新しいプロジェクト] ダイアログ](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)

1. <span data-ttu-id="c1a54-153">テスト ライブラリを `WordCount` クラスで使用するには、`TextUtils` プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-153">In order for the test library to work with the `WordCount` class, add a reference to the `TextUtils` project.</span></span> <span data-ttu-id="c1a54-154">**[ソリューション]** サイドバーで、**TestLibrary** の下にある **[依存関係]** を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-154">In the **Solution** sidebar, right-click **Dependencies** under **TestLibrary**.</span></span> <span data-ttu-id="c1a54-155">コンテキスト メニューから **[参照の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-155">Select **Edit References** from the context menu.</span></span>

1. <span data-ttu-id="c1a54-156">**[参照の編集]** ダイアログで、**[プロジェクト]** タブの **[TextUtils]** プロジェクトを選択します。**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-156">In the **Edit References** dialog, select the **TextUtils** project on the **Projects** tab. Select **OK**.</span></span>

   ![Visual Studio Mac の [参照の編集] ダイアログ](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)

1. <span data-ttu-id="c1a54-158">**[TestLibrary]** プロジェクトで、*UnitTest1.cs* ファイルの名前を *TextUtilsTests.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-158">In the **TestLibrary** project, rename the *UnitTest1.cs* file to *TextUtilsTests.cs*.</span></span>

1. <span data-ttu-id="c1a54-159">ファイルを開き、コードを次のものと置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-159">Open the file and replace the code with the following:</span></span>

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

   <span data-ttu-id="c1a54-160">次のイメージは、単体テスト コードが配置済みの IDE を示しています。</span><span class="sxs-lookup"><span data-stu-id="c1a54-160">The following image shows the IDE with the unit test code in place.</span></span> <span data-ttu-id="c1a54-161">`Assert.NotEqual` ステートメントに注目してください。</span><span class="sxs-lookup"><span data-stu-id="c1a54-161">Pay attention to the `Assert.NotEqual` statement.</span></span>

   ![IDE のメイン ウィンドウでの Visual Studio for Mac の最初の単体テスト](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)

   <span data-ttu-id="c1a54-163">新しいテストを一度失敗させてテスト ロジックが正しいことを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c1a54-163">It's important to make a new test fail once to confirm its testing logic is correct.</span></span> <span data-ttu-id="c1a54-164">メソッドは "Jack" (先頭が大文字) という名前と、"Jack" および "jack" (先頭が大文字のものと小文字のもの) を含む文字列を渡します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-164">The method passes in the name "Jack" (uppercase) and a string with "Jack" and "jack" (uppercase and lowercase).</span></span> <span data-ttu-id="c1a54-165">`GetWordCount` メソッドが正しく機能している場合は、検索語の 2 つのインスタンスのカウントが返されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-165">If the `GetWordCount` method is working properly, it returns a count of two instances of the search word.</span></span> <span data-ttu-id="c1a54-166">このテストを意図的に失敗させるには、まず、検索語 "Jack" の 2 つのインスタンスが `GetWordCount` メソッドで返されないことをアサートするテストを実装します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-166">In order to fail this test on purpose, you first implement the test asserting that two instances of the search word "Jack" aren't returned by the `GetWordCount` method.</span></span> <span data-ttu-id="c1a54-167">次の手順に進んで意図的にテストを失敗させます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-167">Continue to the next step to fail the test on purpose.</span></span>

1. <span data-ttu-id="c1a54-168">画面の右側の **[単体テスト]** パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-168">Open the **Unit Tests** panel on the right side of the screen.</span></span>

   ![Visual Studio for Mac の [単体テスト] パネル](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)

1. <span data-ttu-id="c1a54-170">**[ドッキング]** アイコンをクリックして、パネルを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-170">Click the **Dock** icon to keep the panel open.</span></span>

   ![Visual Studio for Mac の [単体テスト] パネルの [ドッキング] アイコン](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)

1. <span data-ttu-id="c1a54-172">**[すべて実行]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-172">Click the **Run All** button.</span></span>

   <span data-ttu-id="c1a54-173">テストは失敗します。これが正しい結果です。</span><span class="sxs-lookup"><span data-stu-id="c1a54-173">The test fails, which is the correct result.</span></span> <span data-ttu-id="c1a54-174">テスト メソッドは、`GetWordCount` メソッドに指定された文字列 "Jack jack" から `inputString` "Jack" の 2 つのインスタンスが返されないことをアサートします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-174">The test method asserts that two instances of the `inputString`, "Jack," aren't returned from the string "Jack jack" provided to the `GetWordCount` method.</span></span> <span data-ttu-id="c1a54-175">単語の大文字と小文字は `GetWordCount` メソッドでは考慮されないため、2 つのインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-175">Since word casing was factored out in the `GetWordCount` method, two instances are returned.</span></span> <span data-ttu-id="c1a54-176">2 *is not equal to* 2 というアサーションは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-176">The assertion that 2 *is not equal to* 2 fails.</span></span> <span data-ttu-id="c1a54-177">これは正しい結果であり、テストのロジックは適切です。</span><span class="sxs-lookup"><span data-stu-id="c1a54-177">This is the correct outcome, and the logic of our test is good.</span></span>

   ![Visual Studio for Mac のテスト エラーの表示](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)

1. <span data-ttu-id="c1a54-179">`Assert.NotEqual` から `Assert.Equal` に変更して `IgnoreCasing` テスト メソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-179">Modify the `IgnoreCasing` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="c1a54-180">ファイルを保存します。その場合、キーボード ショートカット <kbd>&#8984;</kbd>+<kbd>s</kbd> を使用するか、メニューの **[ファイル]** > **[保存]** の順に選択するか、ファイルのタブを右クリックしてコンテキスト メニューから **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-180">Save the file by using the keyboard shortcut <kbd>&#8984;</kbd>+<kbd>s</kbd>, **File** > **Save** from the menu, or right-clicking on the file's tab and selecting **Save** from the context menu.</span></span>

   <span data-ttu-id="c1a54-181">`searchWord` "Jack" は `GetWordCount` に渡された `inputString` "Jack jack" を含む 2 つのインスタンスを返すことが予想されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-181">You expect that the `searchWord` "Jack" returns two instances with `inputString` "Jack jack" passed into `GetWordCount`.</span></span> <span data-ttu-id="c1a54-182">**[単体テスト]** パネルの **[テストの実行]** ボタン、または画面下部の **[テスト結果]** パネルの **[テストの再実行]** ボタンをクリックして、テストを再実行します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-182">Run the test again by clicking the **Run Tests** button in the **Unit Tests** panel or the **Rerun Tests** button in the **Test Results** panel at the bottom of the screen.</span></span> <span data-ttu-id="c1a54-183">テストに合格します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-183">The test passes.</span></span> <span data-ttu-id="c1a54-184">文字列 "Jack jack" (大文字と小文字の区別は無視) に "Jack" のインスタンスが 2 つあり、テスト アサーションは `true` です。</span><span class="sxs-lookup"><span data-stu-id="c1a54-184">There are two instances of "Jack" in the string "Jack jack" (ignoring casing), and the test assertion is `true`.</span></span>

   ![Visual Studio for Mac のテスト成功の表示](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)

1. <span data-ttu-id="c1a54-186">`Fact` での個々の戻り値のテストは、単体テストで実行できることのほんの一部に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="c1a54-186">Testing individual return values with a `Fact` is only the beginning of what you can do with unit testing.</span></span> <span data-ttu-id="c1a54-187">別の強力な手法では、`Theory` を使用して一度に複数の値をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-187">Another powerful technique allows you to test several values at once using a `Theory`.</span></span> <span data-ttu-id="c1a54-188">次のメソッドを `TextUtils_GetWordCountShould` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-188">Add the following method to your `TextUtils_GetWordCountShould` class.</span></span> <span data-ttu-id="c1a54-189">このメソッドを追加すると、クラスのメソッドは 2 つになります。</span><span class="sxs-lookup"><span data-stu-id="c1a54-189">You have two methods in the class after you add this method:</span></span>

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

   <span data-ttu-id="c1a54-190">`CountInstancesCorrectly` は、`GetWordCount` メソッドが正しくカウントすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-190">The `CountInstancesCorrectly` checks that the `GetWordCount` method counts correctly.</span></span> <span data-ttu-id="c1a54-191">`InlineData` は確認するカウント、検索語、および入力文字列を示します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-191">The `InlineData` provides a count, a search word, and an input string to check.</span></span> <span data-ttu-id="c1a54-192">テスト メソッドはデータの行ごとに一度実行されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-192">The test method runs once for each line of data.</span></span> <span data-ttu-id="c1a54-193">繰り返しますが、データのカウントが正しく、値が `GetWordCount` メソッドで返されるカウントと一致することがわかっている場合でも、まず、`Assert.NotEqual` を使用して失敗をアサートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1a54-193">Note once again that you're asserting a failure first by using `Assert.NotEqual`, even when you know that the counts in the data are correct and that the values match the counts returned by the `GetWordCount` method.</span></span> <span data-ttu-id="c1a54-194">意図的にテストを失敗させる手順を実行するのは、最初は時間の無駄と思えるかもしれませんが、まず、テストを失敗させてロジックを確認することはテストのロジックを確認するうえで重要なことです。</span><span class="sxs-lookup"><span data-stu-id="c1a54-194">Performing the step of failing the test on purpose might seem like a waste of time at first, but checking the logic of the test by failing it first is an important check on the logic of your tests.</span></span> <span data-ttu-id="c1a54-195">失敗させようとしたのに成功するテスト メソッドがある場合、そのテストのロジックにバグがあります。</span><span class="sxs-lookup"><span data-stu-id="c1a54-195">When you come across a test method that passes when you expect it to fail, you've found a bug in the logic of the test.</span></span> <span data-ttu-id="c1a54-196">テスト メソッドを作成するたびに、この手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-196">It's worth the effort to take this step every time you create a test method.</span></span>

1. <span data-ttu-id="c1a54-197">ファイルを保存し、もう一度テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-197">Save the file and run the tests again.</span></span> <span data-ttu-id="c1a54-198">大文字と小文字のテストは成功しますが、3 つのカウント テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-198">The casing test passes but the three count tests fail.</span></span> <span data-ttu-id="c1a54-199">これは予想したとおりの結果です。</span><span class="sxs-lookup"><span data-stu-id="c1a54-199">This is exactly what you expect to happen.</span></span>

   ![Visual Studio for Mac の予測されるテスト エラー](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)

1. <span data-ttu-id="c1a54-201">`Assert.NotEqual` から `Assert.Equal` に変更して `CountInstancesCorrectly` テスト メソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-201">Modify the `CountInstancesCorrectly` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="c1a54-202">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-202">Save the file.</span></span> <span data-ttu-id="c1a54-203">テストをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-203">Run the tests again.</span></span> <span data-ttu-id="c1a54-204">すべてのテストに成功します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-204">All tests pass.</span></span>

   ![Visual Studio for Mac の予測されるテスト成功](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)

## <a name="adding-a-console-app"></a><span data-ttu-id="c1a54-206">コンソール アプリの追加</span><span class="sxs-lookup"><span data-stu-id="c1a54-206">Adding a console app</span></span>

1. <span data-ttu-id="c1a54-207">**[ソリューション]** サイドバーで、`WordCounter` ソリューションを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-207">In the **Solution** sidebar, right-click the `WordCounter` solution.</span></span> <span data-ttu-id="c1a54-208">**[.NET Core]** > **[アプリ]** テンプレートの順に移動してテンプレートを選択し、新しい**コンソール アプリケーション**プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-208">Add a new **Console Application** project by selecting the template from the **.NET Core** > **App** templates.</span></span> <span data-ttu-id="c1a54-209">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-209">Select **Next**.</span></span> <span data-ttu-id="c1a54-210">プロジェクトに **WordCounterApp** という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-210">Name the project **WordCounterApp**.</span></span> <span data-ttu-id="c1a54-211">**[作成]** を選択し、ソリューションでプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-211">Select **Create** to create the project in the solution.</span></span>

1. <span data-ttu-id="c1a54-212">**[ソリューション]** サイドバーで、新しい **WordCounterApp** プロジェクトの **[依存関係]** ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-212">In the **Solutions** sidebar, right-click the **Dependencies** node of the new **WordCounterApp** project.</span></span> <span data-ttu-id="c1a54-213">**[参照の編集]** ダイアログで、**TextUtils** にチェック マークを付けて **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-213">In the **Edit References** dialog, check **TextUtils** and select **OK**.</span></span>

1. <span data-ttu-id="c1a54-214">*Program.cs* ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-214">Open the *Program.cs* file.</span></span> <span data-ttu-id="c1a54-215">このコードを次のコードを使って置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-215">Replace the code with the following:</span></span>

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]

1. <span data-ttu-id="c1a54-216">IDE ではなく、コンソール ウィンドウでアプリを実行するには、`WordCounterApp` プロジェクトを右クリックして **[オプション]** を選択し、**[構成]** の下の **[既定]** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-216">To run the app in a console window instead of the IDE, right-click the `WordCounterApp` project, select **Options**, and open the **Default** node under **Configurations**.</span></span> <span data-ttu-id="c1a54-217">**[外部コンソールで実行]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-217">Check the box for **Run on external console**.</span></span> <span data-ttu-id="c1a54-218">**[コンソール出力を一時停止する]** オプションはオンのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-218">Leave the **Pause console output** option checked.</span></span> <span data-ttu-id="c1a54-219">この設定により、コンソール ウィンドウでアプリが起動し、`Console.ReadLine` ステートメントに入力できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c1a54-219">This setting causes the app to spawn in a console window so that you can type input for the `Console.ReadLine` statements.</span></span> <span data-ttu-id="c1a54-220">IDE でそのままアプリを実行すると、`Console.WriteLine` ステートメントの出力が表示されるだけです。</span><span class="sxs-lookup"><span data-stu-id="c1a54-220">If you leave the app to run in the IDE, you can only see the output of `Console.WriteLine` statements.</span></span> `Console.ReadLine` <span data-ttu-id="c1a54-221">ステートメントは、IDE の **[アプリケーション出力]** パネルでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="c1a54-221">statements do not work in the IDE's **Application Output** panel.</span></span>

   ![Visual Studio for Mac の [プロジェクト オプション] ウィンドウ](./media/using-on-mac-vs-full-solution/visual-studio-mac-project-options.png)

1. <span data-ttu-id="c1a54-223">Visual Studio for Mac の現在のバージョンでは、ソリューションの実行時にテストを実行できないため、コンソール アプリを直接実行します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-223">Because the current version of Visual Studio for Mac cannot run the tests when the solution is run, you run the console app directly.</span></span> <span data-ttu-id="c1a54-224">`WordCounterApp` プロジェクトを右クリックし、コンテキスト メニューから **[Run item (項目の実行)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-224">Right-click on the `WordCounterApp` project and select **Run item** from the context menu.</span></span> <span data-ttu-id="c1a54-225">[再生] ボタンでアプリを実行しようとすると、テスト ランナーとアプリの実行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-225">If you attempt to run the app with the Play button, the test runner and app fail to run.</span></span> <span data-ttu-id="c1a54-226">この問題への取り組みの状態について詳しくは、[xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a54-226">For more information on the status of the work on this issue, see [xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60).</span></span> <span data-ttu-id="c1a54-227">アプリを実行する際に、コンソール ウィンドウで入力を求めるメッセージが表示されたら、検索語と入力文字列の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-227">When you run the app, provide values for the search word and input string at the prompts in the console window.</span></span> <span data-ttu-id="c1a54-228">アプリには、文字列での検索語の表示回数が示されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-228">The app indicates the number of times the search word appears in the string.</span></span>

   ![アプリが実行中であることを示す Visual Studio for Mac のコンソール ウィンドウ](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)

1. <span data-ttu-id="c1a54-230">確認する最後の機能は、Visual Studio for Mac でのデバッグです。</span><span class="sxs-lookup"><span data-stu-id="c1a54-230">The last feature to explore is debugging with Visual Studio for Mac.</span></span> <span data-ttu-id="c1a54-231">`Console.WriteLine` ステートメントにブレークポイントを設定します。23 行目の左余白を選択すると、コード行の横に赤い丸が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-231">Set a breakpoint on the `Console.WriteLine` statement: Select in the left margin of line 23, and you see a red circle appear next to the line of code.</span></span> <span data-ttu-id="c1a54-232">コード行の任意の場所を選択し、メニューから **[実行]** > **[ブレークポイントの設定/解除]** の順に選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-232">Alternatively, select anywhere on the line of code and select **Run** > **Toggle Breakpoint** from the menu.</span></span>

   ![Visual Studio for Mac のブレークポイントの設定](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)

1. <span data-ttu-id="c1a54-234">`WordCounterApp` プロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-234">Right-click the `WordCounterApp` project.</span></span> <span data-ttu-id="c1a54-235">コンテキスト メニューから **[Start Debugging item (項目のデバッグの開始)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-235">Select **Start Debugging item** from the context menu.</span></span> <span data-ttu-id="c1a54-236">アプリが実行されたら、検索語 "cat" と検索文字列 "The dog chased the cat, but the cat escaped" </span><span class="sxs-lookup"><span data-stu-id="c1a54-236">When the app runs, enter the search word "cat" and "The dog chased the cat, but the cat escaped."</span></span> <span data-ttu-id="c1a54-237">を入力します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-237">for the string to search.</span></span> <span data-ttu-id="c1a54-238">`Console.WriteLine` ステートメントに達した時点でプログラムの実行が停止します。その後、ステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-238">When the `Console.WriteLine` statement is reached, program execution halts before the statement is executed.</span></span> <span data-ttu-id="c1a54-239">**[ローカル]** タブで、`searchWord`、`inputString`、`wordCount`、および `pluralChar` の各値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-239">In the **Locals** tab, you can see the `searchWord`, `inputString`, `wordCount`, and `pluralChar` values.</span></span>

   ![Visual Studio for Mac の停止されたデバッガー プログラムの実行](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)

1. <span data-ttu-id="c1a54-241">**[イミディエイト]** ウィンドウで、「wordCount = 999;」と入力してから Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-241">In the **Immediate** pane, type "wordCount = 999;" and press Enter.</span></span> <span data-ttu-id="c1a54-242">これで、`wordCount` 変数に 999 という意味のない値が割り当てられます。これは、デバッグ中に変数値の置き換えが可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-242">This assigns a nonsense value of 999 to the `wordCount` variable showing that you can replace variable values while debugging.</span></span>

   ![Visual Studio for Mac の [イミディエイト] ウィンドウで値を変更する](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)

1. <span data-ttu-id="c1a54-244">ツールバーで、*続行*矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1a54-244">In the toolbar, click the *continue* arrow.</span></span> <span data-ttu-id="c1a54-245">コンソール ウィンドウの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="c1a54-245">Look at the output in the console window.</span></span> <span data-ttu-id="c1a54-246">アプリのデバッグ時に設定した 999 という不適切な値が報告されます。</span><span class="sxs-lookup"><span data-stu-id="c1a54-246">It reports the incorrect value of 999 that you set when you were debugging the app.</span></span>

   ![Visual Studio for Mac ツールバーの続行ボタン](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)

   ![Visual Studio for Mac のコンソール ウィンドウの出力](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)

## <a name="see-also"></a><span data-ttu-id="c1a54-249">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1a54-249">See also</span></span>

- [<span data-ttu-id="c1a54-250">Visual Studio 2017 for Mac リリース ノート</span><span class="sxs-lookup"><span data-stu-id="c1a54-250">Visual Studio 2017 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2017-mac-relnotes)
