---
title: Visual Studio を使用して .NET Standard クラス ライブラリを作成する
description: Visual Studio を使用して .NET Standard クラス ライブラリを作成する方法について説明します。
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: ef9c62b0378e1064d8cfd90a8c59aed74ea312b2
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701566"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio"></a><span data-ttu-id="ae235-103">チュートリアル: Visual Studio を使用して .NET Standard ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="ae235-103">Tutorial: Create a .NET Standard library using Visual Studio</span></span>

<span data-ttu-id="ae235-104">このチュートリアルでは、1 つの文字列処理メソッドを含む簡単なユーティリティ ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae235-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="ae235-105">それを[拡張メソッド](../../csharp/programming-guide/classes-and-structs/extension-methods.md)として実装し、<xref:System.String> クラスのメンバーと同じように呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="ae235-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="ae235-106">"*クラス ライブラリ*" は、アプリケーションから呼び出される型とメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="ae235-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="ae235-107">.NET Standard 2.0 をターゲットとするクラス ライブラリでは、お使いのライブラリを、そのバージョンの .NET Standard をサポートする任意の .NET 実装によって呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ae235-107">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="ae235-108">クラス ライブラリが完成したら、サードパーティ製のコンポーネントとして配布するか、1 つ以上のアプリケーションを含むバンドルされたコンポーネントとして配布することができます。</span><span class="sxs-lookup"><span data-stu-id="ae235-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae235-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ae235-109">Prerequisites</span></span>

- <span data-ttu-id="ae235-110">**.NET Core クロスプラットフォーム開発**ワークロードがインストールされている [Visual Studio 2019 バージョン 16.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="ae235-110">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="ae235-111">このワークロードを選択すると、.NET Core 3.1 SDK が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ae235-111">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="ae235-112">詳細については、記事「[.NET Core SDK をインストールする](../install/sdk.md?pivots=os-windows)」の「[Visual Studio を使用してインストールする](../install/sdk.md?pivots=os-windows#install-with-visual-studio)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae235-112">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="ae235-113">ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="ae235-113">Create a solution</span></span>

<span data-ttu-id="ae235-114">まず、クラス ライブラリ プロジェクトを配置する空のソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae235-114">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="ae235-115">1 つの Visual Studio のソリューションは、1 つまたは複数のプロジェクトのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="ae235-115">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="ae235-116">さらに関連するプロジェクトを同じソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ae235-116">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="ae235-117">空のソリューションを作成するには:</span><span class="sxs-lookup"><span data-stu-id="ae235-117">To create the blank solution:</span></span>

1. <span data-ttu-id="ae235-118">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="ae235-118">Start Visual Studio.</span></span>

2. <span data-ttu-id="ae235-119">スタート ウィンドウで、 **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-119">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="ae235-120">**[新しいプロジェクトの作成]** ページで、検索ボックスに「**ソリューション**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ae235-120">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="ae235-121">**[空のソリューション]** テンプレートを選択して、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-121">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Visual Studio での空のソリューション テンプレート](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="ae235-123">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**ClassLibraryProjects**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ae235-123">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="ae235-124">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-124">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="ae235-125">クラス ライブラリ プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="ae235-125">Create a class library project</span></span>

1. <span data-ttu-id="ae235-126">"StringLibrary" という名前の新しい .NET Standard クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ae235-126">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="ae235-127">**ソリューション エクスプローラー**でソリューションを右クリックし、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="ae235-128">**[新しいプロジェクトの追加]** ページで、検索ボックスに「**ライブラリ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ae235-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="ae235-129">言語の一覧から **[C#]** または **[Visual Basic]** を選択し、次に、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-129">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="ae235-130">**[クラス ライブラリ (.NET Standard)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="ae235-131">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**StringLibrary**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ae235-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="ae235-132">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="ae235-133">ライブラリが正しいバージョンの .NET Standard をターゲットにしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae235-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="ae235-134">**ソリューション エクスプローラー** でライブラリ プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="ae235-135">**[ターゲット フレームワーク]** テキスト ボックスに、.NET Standard 2.0 がプロジェクトのターゲットになっていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="ae235-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![クラス ライブラリのプロジェクト プロパティ](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="ae235-137">Visual Basic を使用している場合は、 **[ルート名前空間]** テキスト ボックス内のテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="ae235-137">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![クラス ライブラリのプロジェクト プロパティ](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="ae235-139">プロジェクトごとに、そのプロジェクト名に対応する名前空間が Visual Basic によって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ae235-139">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="ae235-140">このチュートリアルでは、コード ファイルで [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) キーワードを使用して、最上位の名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="ae235-140">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="ae235-141">*Class1.cs* または *Class1.vb* のコード ウィンドウ内のコードを次のコードに置き換えて、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ae235-141">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="ae235-142">使用する言語が表示されていない場合は、ページの上部にある言語セレクターを変更します。</span><span class="sxs-lookup"><span data-stu-id="ae235-142">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="ae235-143">クラス ライブラリ `UtilityLibraries.StringLibrary` には、`StartsWithUpper` という名前のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae235-143">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="ae235-144">このメソッドによって、現在の文字列のインスタンスが大文字で始まるかどうかを示す <xref:System.Boolean> 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="ae235-144">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="ae235-145">Unicode 規格では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="ae235-145">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="ae235-146"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> メソッドは文字が大文字の場合に `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="ae235-146">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="ae235-147">メニュー バーで、 **[ビルド]**  >  **[ソリューションのビルド]** を選択し、プロジェクトがエラーなくコンパイルされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae235-147">On the menu bar, select **Build** > **Build Solution** to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="ae235-148">ソリューションにコンソール アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="ae235-148">Add a console app to the solution</span></span>

<span data-ttu-id="ae235-149">このクラス ライブラリを使用するコンソール アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae235-149">Add a console application that uses the class library.</span></span> <span data-ttu-id="ae235-150">アプリによって、ユーザーに文字列の入力が求められ、文字列が大文字で始まるかどうかが報告されます。</span><span class="sxs-lookup"><span data-stu-id="ae235-150">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="ae235-151">"ShowCase" という名前の新しい .NET Core コンソール アプリケーションをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ae235-151">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="ae235-152">**ソリューション エクスプローラー**で、ソリューションを右クリックし、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-152">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="ae235-153">**[新しいプロジェクトの追加]** ページで、検索ボックスに「**コンソール**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ae235-153">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="ae235-154">言語の一覧から **[C#]** または **[Visual Basic]** を選択し、次に、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-154">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="ae235-155">**[コンソール アプリ (.NET Core)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-155">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="ae235-156">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**ShowCase**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ae235-156">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="ae235-157">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae235-157">Then choose **Create**.</span></span>

1. <span data-ttu-id="ae235-158">*Program.cs* または *Program.vb* ファイルのコード ウィンドウで、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ae235-158">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="ae235-159">このコードでは、`row` 変数を使って、コンソール ウィンドウに書き込まれるデータの行数のカウントを維持します。</span><span class="sxs-lookup"><span data-stu-id="ae235-159">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="ae235-160">これが 25 以上になると、コードによってコンソール ウィンドウがクリアされ、ユーザーにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae235-160">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="ae235-161">プログラムは、ユーザーに文字列の入力を要求し、</span><span class="sxs-lookup"><span data-stu-id="ae235-161">The program prompts the user to enter a string.</span></span> <span data-ttu-id="ae235-162">文字列が大文字で始まるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ae235-162">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="ae235-163">ユーザーが文字列を入力せずに <kbd>Enter</kbd> キーを押すと、アプリケーションが終了し、コンソール ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="ae235-163">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="ae235-164">プロジェクト参照を追加する</span><span class="sxs-lookup"><span data-stu-id="ae235-164">Add a project reference</span></span>

<span data-ttu-id="ae235-165">最初は、新しいコンソール アプリ プロジェクトにクラス ライブラリへのアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="ae235-165">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="ae235-166">クラス ライブラリでメソッドを呼び出せるようにするには、クラス ライブラリ プロジェクトへのプロジェクト参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="ae235-166">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="ae235-167">**ソリューション エクスプローラー**で、`ShowCase` プロジェクトの **[依存関係]** ノードを右クリックして、 **[プロジェクト参照の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae235-167">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Visual Studio の [参照の追加] コンテキスト メニュー](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="ae235-169">**[参照マネージャー]** ダイアログ ボックスで、 **[StringLibrary]** プロジェクトを選び、 **[OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae235-169">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![StringLibrary が選択された [参照マネージャー] ダイアログ](media/library-with-visual-studio/manage-project-references.png)

## <a name="run-the-app"></a><span data-ttu-id="ae235-171">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="ae235-171">Run the app</span></span>

1. <span data-ttu-id="ae235-172">**ソリューション エクスプローラー**で、**ShowCase** プロジェクトを右クリックして、コンテキスト メニューで **[スタートアップ プロジェクトに設定]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ae235-172">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![スタートアップ プロジェクトを設定する Visual Studio プロジェクトのコンテキスト メニュー](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="ae235-174"><kbd>Shift</kbd> + <kbd>F5</kbd> キーを押して、デバッグなしでプログラムをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="ae235-174">Press <kbd>Shift</kbd>+<kbd>F5</kbd> to compile and run the program without debugging.</span></span>

   ![[デバッグ] ボタンを示している Visual Studio プロジェクトのツールバー](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="ae235-176">文字列を入力して <kbd>Enter</kbd> キーを押してプログラムを実行し、<kbd>Enter</kbd> キーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="ae235-176">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="ShowCase が実行されているコンソール ウィンドウ":::

## <a name="additional-resources"></a><span data-ttu-id="ae235-178">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="ae235-178">Additional resources</span></span>

* [<span data-ttu-id="ae235-179">.NET Core CLI を使用したライブラリの開発</span><span class="sxs-lookup"><span data-stu-id="ae235-179">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="ae235-180">[.NET Standard のバージョンとそれらでサポートされているプラットフォーム](../../standard/net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="ae235-180">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae235-181">次の手順</span><span class="sxs-lookup"><span data-stu-id="ae235-181">Next steps</span></span>

<span data-ttu-id="ae235-182">このチュートリアルでは、ソリューションを作成し、ライブラリ プロジェクトを追加し、ライブラリを使用するコンソール アプリ プロジェクトを追加しました。</span><span class="sxs-lookup"><span data-stu-id="ae235-182">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="ae235-183">次のチュートリアルでは、ソリューションに単体テスト プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae235-183">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ae235-184">Visual Studio を使用して .NET Core で .NET Standard ライブラリをテストする</span><span class="sxs-lookup"><span data-stu-id="ae235-184">Test a .NET Standard library with .NET Core using Visual Studio</span></span>](testing-library-with-visual-studio.md)
