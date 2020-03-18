---
title: Visual Studio で .NET Standard クラス ライブラリを構築する
description: Visual Studio を使用して C# または Visual Basic で記述された .NET Standard クラス ライブラリを構築する方法について説明します
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714017"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="df83f-103">Visual Studio で .NET Standard ライブラリを構築する</span><span class="sxs-lookup"><span data-stu-id="df83f-103">Build a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="df83f-104">"*クラス ライブラリ*" は、アプリケーションから呼び出される型とメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="df83f-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="df83f-105">.NET Standard 2.0 をターゲットとするクラス ライブラリでは、お使いのライブラリを、そのバージョンの .NET Standard をサポートする任意の .NET 実装によって呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="df83f-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="df83f-106">クラス ライブラリを完了させたら、サードパーティ製のコンポーネントとして配布するかどうか、あるいは 1 つまたは複数のアプリケーションにバンドルされたコンポーネントとして含めるかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="df83f-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="df83f-107">.NET Standard のバージョンとそれらがサポートするプラットフォームの一覧は、「[.NET Standard](../../standard/net-standard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df83f-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="df83f-108">このトピックでは、1 つの文字列処理メソッドを含む簡単なユーティリティ ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="df83f-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="df83f-109">それを[拡張メソッド](../../csharp/programming-guide/classes-and-structs/extension-methods.md)として実装し、<xref:System.String> クラスのメンバーと同じように呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="df83f-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="create-a-visual-studio-solution"></a><span data-ttu-id="df83f-110">Visual Studio ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="df83f-110">Create a Visual Studio solution</span></span>

<span data-ttu-id="df83f-111">まず、クラス ライブラリ プロジェクトを配置する空のソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="df83f-111">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="df83f-112">1 つの Visual Studio のソリューションは、1 つまたは複数のプロジェクトのコンテナーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="df83f-112">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="df83f-113">このチュートリアル シリーズを続行する場合は、関連するプロジェクトを同じソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="df83f-113">You'll add additional, related projects to the same solution if you continue on with the tutorial series.</span></span>

<span data-ttu-id="df83f-114">空のソリューションを作成するには:</span><span class="sxs-lookup"><span data-stu-id="df83f-114">To create the blank solution:</span></span>

1. <span data-ttu-id="df83f-115">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="df83f-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="df83f-116">スタート ウィンドウで、 **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-116">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="df83f-117">**[新しいプロジェクトの作成]** ページで、検索ボックスに「**ソリューション**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="df83f-117">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="df83f-118">**[空のソリューション]** テンプレートを選択して、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-118">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Visual Studio での空のソリューション テンプレート](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="df83f-120">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**ClassLibraryProjects**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="df83f-120">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="df83f-121">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-121">Then, choose **Create**.</span></span>

> [!TIP]
> <span data-ttu-id="df83f-122">この手順をスキップして、次の手順でプロジェクトを作成するときに Visual Studio によってソリューションが自動的に作成されるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="df83f-122">You can also skip this step and let Visual Studio create the solution for you when you create the project in the next step.</span></span> <span data-ttu-id="df83f-123">**[新しいプロジェクトの構成]** ページでソリューション オプションを探します。</span><span class="sxs-lookup"><span data-stu-id="df83f-123">Look for the solution options on the **Configure your new project** page.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="df83f-124">クラス ライブラリ プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="df83f-124">Create a class library project</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="df83f-125">C#</span><span class="sxs-lookup"><span data-stu-id="df83f-125">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="df83f-126">"StringLibrary" という名前の新しい C# .NET Standard クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="df83f-126">Add a new C# .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="df83f-127">**ソリューション エクスプローラー**で、ソリューションを右クリックし、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="df83f-128">**[新しいプロジェクトの追加]** ページで、検索ボックスに「**ライブラリ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="df83f-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="df83f-129">言語の一覧から **[C#]** を選択し、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-129">Choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="df83f-130">**[クラス ライブラリ (.NET Standard)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="df83f-131">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**StringLibrary**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="df83f-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="df83f-132">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="df83f-133">ライブラリが正しいバージョンの .NET Standard をターゲットにしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="df83f-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="df83f-134">**ソリューション エクスプローラー** でライブラリ プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="df83f-135">**[ターゲット フレームワーク]** テキスト ボックスに、.NET Standard 2.0 がプロジェクトのターゲットになっていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="df83f-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![クラス ライブラリのプロジェクト プロパティ](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="df83f-137">コード ウィンドウ内のコードを次のコードに置き換えて、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="df83f-137">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="df83f-138">クラス ライブラリ `UtilityLibraries.StringLibrary` には、`StartsWithUpper` という名前のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df83f-138">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="df83f-139">このメソッドによって、現在の文字列のインスタンスが大文字で始まるかどうかを示す <xref:System.Boolean> 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="df83f-139">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="df83f-140">Unicode 規格では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="df83f-140">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="df83f-141"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> メソッドは文字が大文字の場合に `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="df83f-141">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="df83f-142">メニュー バーで **[ビルド]**  >  **[ソリューションのビルド]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-142">On the menu bar, select **Build** > **Build Solution**.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="df83f-143">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df83f-143">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="df83f-144">"StringLibrary" という名前の新しい Visual Basic .NET Standard クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="df83f-144">Add a new Visual Basic .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="df83f-145">**ソリューション エクスプローラー**で、ソリューションを右クリックし、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-145">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="df83f-146">**[新しいプロジェクトの追加]** ページで、検索ボックスに「**ライブラリ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="df83f-146">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="df83f-147">言語の一覧から **[Visual Basic]** を選択し、次に、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-147">Choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="df83f-148">**[クラス ライブラリ (.NET Standard)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-148">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="df83f-149">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**StringLibrary**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="df83f-149">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="df83f-150">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-150">Then, choose **Create**.</span></span>

1. <span data-ttu-id="df83f-151">ライブラリが正しいバージョンの .NET Standard をターゲットにしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="df83f-151">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="df83f-152">**ソリューション エクスプローラー** でライブラリ プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-152">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="df83f-153">**[ターゲット フレームワーク]** テキスト ボックスに、.NET Standard 2.0 がプロジェクトのターゲットになっていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="df83f-153">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![クラス ライブラリのプロジェクト プロパティ](./media/library-with-visual-studio/vb/library-project-properties.png)

1. <span data-ttu-id="df83f-155">**[プロパティ]** ダイアログで、 **[ルート名前空間]** テキスト ボックス内のテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="df83f-155">In the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="df83f-156">プロジェクトごとに、そのプロジェクト名に対応する名前空間が Visual Basic によって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="df83f-156">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="df83f-157">このチュートリアルでは、コード ファイルで [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) キーワードを使用して、最上位の名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="df83f-157">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="df83f-158">コード ウィンドウ内のコードを次のコードに置き換えて、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="df83f-158">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="df83f-159">クラス ライブラリ `UtilityLibraries.StringLibrary` には、`StartsWithUpper` という名前のメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df83f-159">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="df83f-160">このメソッドによって、現在の文字列のインスタンスが大文字で始まるかどうかを示す <xref:System.Boolean> 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="df83f-160">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="df83f-161">Unicode 規格では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="df83f-161">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="df83f-162"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> メソッドは文字が大文字の場合に `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="df83f-162">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="df83f-163">メニュー バーで **[ビルド]**  >  **[ソリューションのビルド]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="df83f-163">On the menu bar, select **Build** > **Build Solution**.</span></span>

---

   <span data-ttu-id="df83f-164">プロジェクトはエラーなしでコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="df83f-164">The project should compile without error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="df83f-165">次のステップ</span><span class="sxs-lookup"><span data-stu-id="df83f-165">Next steps</span></span>

<span data-ttu-id="df83f-166">ライブラリを正常に作成できました。</span><span class="sxs-lookup"><span data-stu-id="df83f-166">You've successfully built the library.</span></span> <span data-ttu-id="df83f-167">そのメソッドの呼び出しをまだ行っていないので、期待どおりに動作するかわかりません。</span><span class="sxs-lookup"><span data-stu-id="df83f-167">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="df83f-168">ライブラリの開発における次のステップでは、それをテストします。</span><span class="sxs-lookup"><span data-stu-id="df83f-168">The next step in developing your library is to test it.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="df83f-169">単体テスト プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="df83f-169">Create a unit test project</span></span>](testing-library-with-visual-studio.md)
