---
title: Visual Studio を使用して .NET Standard クラス ライブラリを作成する
description: Visual Studio を使用して .NET Standard クラス ライブラリを作成する方法について説明します。
ms.date: 08/07/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet,contperfq1
ms.openlocfilehash: 45a44dcd73e1abcc8dfd75cd54da5a2310f027c4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118261"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio"></a><span data-ttu-id="16a60-103">チュートリアル: Visual Studio を使用して .NET Standard ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="16a60-103">Tutorial: Create a .NET Standard library using Visual Studio</span></span>

<span data-ttu-id="16a60-104">このチュートリアルでは、1 つの文字列処理メソッドを含むシンプルなクラス ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="16a60-104">In this tutorial, you create a simple class library that contains a single string-handling method.</span></span>

<span data-ttu-id="16a60-105">"*クラス ライブラリ*" は、アプリケーションから呼び出される型とメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="16a60-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="16a60-106">.NET Standard 2.0 をターゲットとするクラス ライブラリでは、お使いのライブラリを、そのバージョンの .NET Standard をサポートする任意の .NET 実装によって呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="16a60-106">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span>

<span data-ttu-id="16a60-107">自分のクラス ライブラリが完成したら、NuGet パッケージとして配布するか、それを使用するアプリケーションにコンポーネントとしてバンドルして配布することができます。</span><span class="sxs-lookup"><span data-stu-id="16a60-107">When you finish your class library, you can distribute it as a NuGet package or as a component bundled with the application that uses it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="16a60-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="16a60-108">Prerequisites</span></span>

- <span data-ttu-id="16a60-109">**.NET Core クロスプラットフォーム開発**ワークロードがインストールされている [Visual Studio 2019 バージョン 16.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="16a60-109">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="16a60-110">このワークロードを選択すると、.NET Core 3.1 SDK が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="16a60-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="16a60-111">ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="16a60-111">Create a solution</span></span>

<span data-ttu-id="16a60-112">まず、クラス ライブラリ プロジェクトを配置する空のソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="16a60-112">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="16a60-113">1 つの Visual Studio のソリューションは、1 つまたは複数のプロジェクトのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="16a60-113">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="16a60-114">さらに関連するプロジェクトを同じソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="16a60-114">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="16a60-115">空のソリューションを作成するには:</span><span class="sxs-lookup"><span data-stu-id="16a60-115">To create the blank solution:</span></span>

1. <span data-ttu-id="16a60-116">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="16a60-116">Start Visual Studio.</span></span>

2. <span data-ttu-id="16a60-117">スタート ウィンドウで、 **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-117">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="16a60-118">**[新しいプロジェクトの作成]** ページで、検索ボックスに「**ソリューション**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="16a60-118">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="16a60-119">**[空のソリューション]** テンプレートを選択して、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-119">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Visual Studio での空のソリューション テンプレート](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="16a60-121">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**ClassLibraryProjects**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="16a60-121">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="16a60-122">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-122">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="16a60-123">クラス ライブラリ プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="16a60-123">Create a class library project</span></span>

1. <span data-ttu-id="16a60-124">"StringLibrary" という名前の新しい .NET Standard クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="16a60-124">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="16a60-125">**ソリューション エクスプローラー**でソリューションを右クリックし、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-125">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="16a60-126">**[新しいプロジェクトの追加]** ページで、検索ボックスに「**ライブラリ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="16a60-126">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="16a60-127">言語の一覧から **[C#]** または **[Visual Basic]** を選択し、次に、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-127">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="16a60-128">**[クラス ライブラリ (.NET Standard)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-128">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="16a60-129">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**StringLibrary**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="16a60-129">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="16a60-130">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-130">Then, choose **Create**.</span></span>

1. <span data-ttu-id="16a60-131">ライブラリが正しいバージョンの .NET Standard をターゲットにしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16a60-131">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="16a60-132">**ソリューション エクスプローラー** でライブラリ プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-132">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="16a60-133">**[ターゲット フレームワーク]** テキスト ボックスに、.NET Standard 2.0 がプロジェクトのターゲットになっていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="16a60-133">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![クラス ライブラリのプロジェクト プロパティ](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="16a60-135">Visual Basic を使用している場合は、 **[ルート名前空間]** テキスト ボックス内のテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="16a60-135">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![クラス ライブラリのプロジェクト プロパティ](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="16a60-137">プロジェクトごとに、そのプロジェクト名に対応する名前空間が Visual Basic によって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="16a60-137">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="16a60-138">このチュートリアルでは、コード ファイルで [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) キーワードを使用して、最上位の名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="16a60-138">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="16a60-139">*Class1.cs* または *Class1.vb* のコード ウィンドウ内のコードを次のコードに置き換えて、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="16a60-139">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="16a60-140">使用する言語が表示されていない場合は、ページの上部にある言語セレクターを変更します。</span><span class="sxs-lookup"><span data-stu-id="16a60-140">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="16a60-141">クラス ライブラリ `UtilityLibraries.StringLibrary` には、`StartsWithUpper` という名前のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="16a60-141">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="16a60-142">このメソッドによって、現在の文字列のインスタンスが大文字で始まるかどうかを示す <xref:System.Boolean> 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="16a60-142">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="16a60-143">Unicode 規格では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="16a60-143">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="16a60-144"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> メソッドは文字が大文字の場合に `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="16a60-144">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

   <span data-ttu-id="16a60-145">`StartsWithUpper` は、<xref:System.String> クラスのメンバーであるかのように呼び出すことができる[拡張メソッド](../../csharp/programming-guide/classes-and-structs/extension-methods.md)として実装されます。</span><span class="sxs-lookup"><span data-stu-id="16a60-145">`StartsWithUpper` is implemented as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

1. <span data-ttu-id="16a60-146">メニュー バーで、 **[ビルド]**  >  **[ソリューションのビルド]** を選択するか、<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>B</kbd> キーを押して、プロジェクトがエラーなくコンパイルされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16a60-146">On the menu bar, select **Build** > **Build Solution** or press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd> to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="16a60-147">ソリューションにコンソール アプリを追加する</span><span class="sxs-lookup"><span data-stu-id="16a60-147">Add a console app to the solution</span></span>

<span data-ttu-id="16a60-148">このクラス ライブラリを使用するコンソール アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="16a60-148">Add a console application that uses the class library.</span></span> <span data-ttu-id="16a60-149">アプリによって、ユーザーに文字列の入力が求められ、文字列が大文字で始まるかどうかが報告されます。</span><span class="sxs-lookup"><span data-stu-id="16a60-149">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="16a60-150">"ShowCase" という名前の新しい .NET Core コンソール アプリケーションをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="16a60-150">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="16a60-151">**ソリューション エクスプローラー**で、ソリューションを右クリックし、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-151">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="16a60-152">**[新しいプロジェクトの追加]** ページで、検索ボックスに「**コンソール**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="16a60-152">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="16a60-153">言語の一覧から **[C#]** または **[Visual Basic]** を選択し、次に、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-153">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="16a60-154">**[コンソール アプリ (.NET Core)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-154">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="16a60-155">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**ShowCase**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="16a60-155">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="16a60-156">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16a60-156">Then choose **Create**.</span></span>

1. <span data-ttu-id="16a60-157">*Program.cs* または *Program.vb* ファイルのコード ウィンドウで、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="16a60-157">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="16a60-158">このコードでは、`row` 変数を使って、コンソール ウィンドウに書き込まれるデータの行数のカウントを維持します。</span><span class="sxs-lookup"><span data-stu-id="16a60-158">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="16a60-159">これが 25 以上になると、コードによってコンソール ウィンドウがクリアされ、ユーザーにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="16a60-159">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="16a60-160">プログラムは、ユーザーに文字列の入力を要求し、</span><span class="sxs-lookup"><span data-stu-id="16a60-160">The program prompts the user to enter a string.</span></span> <span data-ttu-id="16a60-161">文字列が大文字で始まるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="16a60-161">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="16a60-162">ユーザーが文字列を入力せずに <kbd>Enter</kbd> キーを押すと、アプリケーションが終了し、コンソール ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="16a60-162">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="16a60-163">プロジェクト参照を追加する</span><span class="sxs-lookup"><span data-stu-id="16a60-163">Add a project reference</span></span>

<span data-ttu-id="16a60-164">最初は、新しいコンソール アプリ プロジェクトにクラス ライブラリへのアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="16a60-164">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="16a60-165">クラス ライブラリでメソッドを呼び出せるようにするには、クラス ライブラリ プロジェクトへのプロジェクト参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="16a60-165">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="16a60-166">**ソリューション エクスプローラー**で、`ShowCase` プロジェクトの **[依存関係]** ノードを右クリックして、 **[プロジェクト参照の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="16a60-166">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Visual Studio の [参照の追加] コンテキスト メニュー](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="16a60-168">**[参照マネージャー]** ダイアログ ボックスで、 **[StringLibrary]** プロジェクトを選び、 **[OK]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="16a60-168">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![StringLibrary が選択された [参照マネージャー] ダイアログ](media/library-with-visual-studio/manage-project-references.png)

## <a name="run-the-app"></a><span data-ttu-id="16a60-170">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="16a60-170">Run the app</span></span>

1. <span data-ttu-id="16a60-171">**ソリューション エクスプローラー**で、**ShowCase** プロジェクトを右クリックして、コンテキスト メニューで **[スタートアップ プロジェクトに設定]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="16a60-171">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![スタートアップ プロジェクトを設定する Visual Studio プロジェクトのコンテキスト メニュー](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="16a60-173"><kbd>Ctrl</kbd>+<kbd>F5</kbd> キーを押して、デバッグなしでプログラムをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="16a60-173">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to compile and run the program without debugging.</span></span>

   ![[デバッグ] ボタンを示している Visual Studio プロジェクトのツールバー](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="16a60-175">文字列を入力して <kbd>Enter</kbd> キーを押してプログラムを実行し、<kbd>Enter</kbd> キーを押して終了します。</span><span class="sxs-lookup"><span data-stu-id="16a60-175">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="ShowCase が実行されているコンソール ウィンドウ":::

## <a name="additional-resources"></a><span data-ttu-id="16a60-177">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="16a60-177">Additional resources</span></span>

* [<span data-ttu-id="16a60-178">.NET Core CLI を使用したライブラリの開発</span><span class="sxs-lookup"><span data-stu-id="16a60-178">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="16a60-179">[.NET Standard のバージョンとそれらでサポートされているプラットフォーム](../../standard/net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="16a60-179">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="16a60-180">次の手順</span><span class="sxs-lookup"><span data-stu-id="16a60-180">Next steps</span></span>

<span data-ttu-id="16a60-181">このチュートリアルでは、クラス ライブラリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="16a60-181">In this tutorial, you created a class library.</span></span> <span data-ttu-id="16a60-182">次のチュートリアルでは、そのクラス ライブラリを単体テストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16a60-182">In the next tutorial, you learn how to unit test the class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="16a60-183">Visual Studio を使用して .NET Standard ライブラリを単体テストする</span><span class="sxs-lookup"><span data-stu-id="16a60-183">Unit test a .NET Standard library using Visual Studio</span></span>](testing-library-with-visual-studio.md)

<span data-ttu-id="16a60-184">または、自動化された単体テストをスキップし、NuGet パッケージを作成してそのライブラリを共有する方法を学習することもできます。</span><span class="sxs-lookup"><span data-stu-id="16a60-184">Or you can skip automated unit testing and learn how to share the library by creating a NuGet package:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="16a60-185">Visual Studio を使用した、パッケージの作成と公開</span><span class="sxs-lookup"><span data-stu-id="16a60-185">Create and publish a package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio)

<span data-ttu-id="16a60-186">または、コンソール アプリを公開する方法を学習することもできます。</span><span class="sxs-lookup"><span data-stu-id="16a60-186">Or learn how to publish a console app.</span></span> <span data-ttu-id="16a60-187">このチュートリアルで作成したソリューションからそのコンソール アプリを発行すると、それに付属するクラス ライブラリは *.dll* ファイルとなります。</span><span class="sxs-lookup"><span data-stu-id="16a60-187">If you publish the console app from the solution you created in this tutorial, the class library goes with it as a *.dll* file.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="16a60-188">Visual Studio を使用して .NET Core コンソール アプリケーションを発行する</span><span class="sxs-lookup"><span data-stu-id="16a60-188">Publish a .NET Core console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
