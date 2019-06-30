---
title: Visual Studio 2017 での .NET Core を使用した .NET Standard クラス ライブラリのテスト
description: .NET Core クラス ライブラリ用の単体テスト プロジェクトを作成します。 .NET Core クラス ライブラリが単体テストで正しく動作することを確認します。
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 32593465c1a161aa1293b7b233539fa930c7e1d8
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402209"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="ad8ae-104">Visual Studio 2017 での .NET Core を使用した .NET Standard ライブラリのテスト</span><span class="sxs-lookup"><span data-stu-id="ad8ae-104">Test a .NET Standard library with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="ad8ae-105">「[Visual Studio 2017 の C# と .NET Core を使用して .NET Standard クラス ライブラリを構築する](library-with-visual-studio.md)」または「[Visual Studio 2017 で Visual Basic と .NET Core SDK を使用してクラス ライブラリを構築する](vb-library-with-visual-studio.md)」では、<xref:System.String> クラスに拡張メソッドを追加する簡単なクラス ライブラリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-105">In [Build a .NET Standard library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md) or [Build a .NET Standard library with Visual Basic and .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="ad8ae-106">ここでは、それが期待どおり動作するかを確認する単体テストを作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-106">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="ad8ae-107">この単体テスト プロジェクトは、前の記事で作成したソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-107">You'll add your unit test project to the solution you created in the previous article.</span></span>

## <a name="creating-a-unit-test-project"></a><span data-ttu-id="ad8ae-108">単体テスト プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="ad8ae-108">Creating a unit test project</span></span>

<span data-ttu-id="ad8ae-109">単体テスト プロジェクトを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-109">To create the unit test project, do the following:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="ad8ae-110">C#</span><span class="sxs-lookup"><span data-stu-id="ad8ae-110">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="ad8ae-111">**ソリューション エクスプローラー**で **[ClassLibraryProjects]** ソリューション ノードのコンテキスト メニューを開き、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-111">In **Solution Explorer**, open the context menu for the **ClassLibraryProjects** solution node and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="ad8ae-112">**[新しいプロジェクトの追加]** ダイアログで、 **[Visual C#]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-112">In the **Add New Project** dialog, select the **Visual C#** node.</span></span> <span data-ttu-id="ad8ae-113">次に、 **[.NET Core]** ノードを選び、 **[MSTest テスト プロジェクト (.NET Core)]** プロジェクト テンプレートを選びます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-113">Then select the **.NET Core** node followed by the **MSTest Test Project (.NET Core)** project template.</span></span> <span data-ttu-id="ad8ae-114">**[名前]** テキスト ボックスに、プロジェクト名として "StringLibraryTest" と入力します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-114">In the **Name** text box, enter "StringLibraryTest" as the name of the project.</span></span> <span data-ttu-id="ad8ae-115">**[OK]** を選択し、単体テスト プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-115">Select **OK** to create the unit test project.</span></span>

   ![単体テスト プロジェクトが表示された [新しいプロジェクトの追加] ダイアログ - C#](./media/testing-library-with-visual-studio/create-new-test-project.png)

   > [!NOTE]  
   > <span data-ttu-id="ad8ae-117">MSTest テスト プロジェクトに加え、Visual Studio を使用して .NET Core 用の xUnit テスト プロジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-117">In addition to an MSTest Test project, you can also use Visual Studio to create an xUnit test project for .NET Core.</span></span>

1. <span data-ttu-id="ad8ae-118">Visual Studio でプロジェクトが作成され、コード ウィンドウ内に *UnitTest1.cs* ファイルが開かれます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-118">Visual Studio creates the project and opens the *UnitTest1.cs* file in the code window.</span></span>

   ![単体テスト プロジェクト クラスとメソッドの Visual Studio コード ウィンドウ - C#](./media/testing-library-with-visual-studio/unit-test-editor-window.png)

   <span data-ttu-id="ad8ae-120">単体テストのテンプレートで作成されたソース コードにより、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-120">The source code created by the unit test template does the following:</span></span>

   * <span data-ttu-id="ad8ae-121">単体テストで使用される型が含まれた <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-121">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   * <span data-ttu-id="ad8ae-122"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 属性が `UnitTest1` クラスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-122">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="ad8ae-123">\[TestMethod\] 属性でタグ付けされたテスト クラス内の各テスト メソッドは、単体テスト実行時に自動実行されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-123">Each test method in a test class tagged with the \[TestMethod\] attribute is executed automatically when the unit test is run.</span></span>

   * <span data-ttu-id="ad8ae-124"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性が適用され、単体テスト実行時に自動実行されるテスト メソッドとして `TestMethod1` が定義されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="ad8ae-125">**ソリューション エクスプローラー**で **[StringLibraryTest]** プロジェクトの **[依存関係]** ノードを右クリックし、コンテキスト メニューの **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-125">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   ![StringLibraryTest の依存関係のコンテキスト メニュー - C#](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="ad8ae-127">**[参照マネージャー]** ダイアログで、 **[プロジェクト]** ノードを展開し、 **[StringLibrary]** の横のボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-127">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="ad8ae-128">`StringLibrary` アセンブリへの参照を追加すると、コンパイラで **StringLibrary** メソッドを見つけることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="ad8ae-129">**[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-129">Select the **OK** button.</span></span> <span data-ttu-id="ad8ae-130">これによってクラス ライブラリ プロジェクト `StringLibrary` への参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-130">This adds a reference to your class library project, `StringLibrary`.</span></span>

   ![Visual Studio のプロジェクト参照の追加ダイアログ](./media/testing-library-with-visual-studio/project-reference-manager.png)
# <a name="visual-basictabvb"></a>[<span data-ttu-id="ad8ae-132">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad8ae-132">Visual Basic</span></span>](#tab/vb) 
1. <span data-ttu-id="ad8ae-133">**ソリューション エクスプローラー**で **[ClassLibraryProjects]** ソリューション ノードのコンテキスト メニューを開き、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-133">In **Solution Explorer**, open the context menu for the **ClassLibraryProjects** solution node and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="ad8ae-134">**[新しいプロジェクトの追加]** ダイアログで、 **[Visual Basic]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-134">In the **Add New Project** dialog, select the **Visual Basic** node.</span></span> <span data-ttu-id="ad8ae-135">次に、 **[.NET Core]** ノードを選び、 **[MSTest テスト プロジェクト (.NET Core)]** プロジェクト テンプレートを選びます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-135">Then select the **.NET Core** node followed by the **MSTest Test Project (.NET Core)** project template.</span></span> <span data-ttu-id="ad8ae-136">**[名前]** テキスト ボックスに、プロジェクト名として "StringLibraryTest" と入力します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-136">In the **Name** text box, enter "StringLibraryTest" as the name of the project.</span></span> <span data-ttu-id="ad8ae-137">**[OK]** を選択し、単体テスト プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-137">Select **OK** to create the unit test project.</span></span>

   ![単体テスト プロジェクトが表示された [新しいプロジェクトの追加] ダイアログ - Visual Basic](./media/testing-library-with-visual-studio/vb-create-new-test-project.png)

   > [!NOTE]  
   > <span data-ttu-id="ad8ae-139">MSTest テスト プロジェクトに加え、Visual Studio を使用して .NET Core 用の xUnit テスト プロジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-139">In addition to an MSTest Test project, you can also use Visual Studio to create an xUnit test project for .NET Core.</span></span>

1. <span data-ttu-id="ad8ae-140">Visual Studio でプロジェクトが作成され、コード ウィンドウ内に *UnitTest1.vb* ファイルが開かれます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-140">Visual Studio creates the project and opens the *UnitTest1.vb* file in the code window.</span></span>

   ![単体テストプロジェクト クラスとメソッドの Visual Studio コード ウィンドウ - Visual Basic](./media/testing-library-with-visual-studio/vb-unit-test-editor-window.png)

   <span data-ttu-id="ad8ae-142">単体テストのテンプレートで作成されたソース コードにより、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-142">The source code created by the unit test template does the following:</span></span>

   * <span data-ttu-id="ad8ae-143">単体テストで使用される型が含まれた <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-143">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   * <span data-ttu-id="ad8ae-144"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>) 属性が `UnitTest1` クラスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-144">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="ad8ae-145"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性でタグ付けされたテスト クラス内の各テスト メソッドは、単体テスト実行時に自動実行されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-145">Each test method in a test class tagged with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute is executed automatically when the unit test is run.</span></span>

   * <span data-ttu-id="ad8ae-146"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性が適用され、単体テスト実行時に自動実行されるテスト メソッドとして `TestMethod1` が定義されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-146">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="ad8ae-147">**ソリューション エクスプローラー**で **[StringLibraryTest]** プロジェクトの **[依存関係]** ノードを右クリックし、コンテキスト メニューの **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-147">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   ![StringLibraryTest の依存関係のコンテキスト メニュー](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="ad8ae-149">**[参照マネージャー]** ダイアログで、 **[プロジェクト]** ノードを展開し、 **[StringLibrary]** の横のボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-149">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="ad8ae-150">`StringLibrary` アセンブリへの参照を追加すると、コンパイラで **StringLibrary** メソッドを見つけることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-150">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="ad8ae-151">**[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-151">Select the **OK** button.</span></span> <span data-ttu-id="ad8ae-152">これによってクラス ライブラリ プロジェクト `StringLibrary` への参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-152">This adds a reference to your class library project, `StringLibrary`.</span></span>

   ![Visual Studio のプロジェクト参照の追加ダイアログ - Visual Basic](./media/testing-library-with-visual-studio/project-reference-manager.png)
---

## <a name="adding-and-running-unit-test-methods"></a><span data-ttu-id="ad8ae-154">単体テスト メソッドの追加と実行</span><span class="sxs-lookup"><span data-stu-id="ad8ae-154">Adding and running unit test methods</span></span>

<span data-ttu-id="ad8ae-155">Visual Studio で単体テストを実行すると、単体テスト クラス (<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性が適用されているクラス) 内の <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 属性でマークされた各メソッドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-155">When Visual Studio runs a unit test, it executes each method marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a unit test class, the class to which the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute is applied.</span></span> <span data-ttu-id="ad8ae-156">1 つのテスト メソッドは、最初のエラーが発生したとき、またはそのメソッドに含まれているすべてのテストが成功したときに終了します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-156">A test method ends when the first failure is encountered or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="ad8ae-157">一般的なテストでは、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> クラスのメンバーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-157">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="ad8ae-158">多くのアサート メソッドは最低 2 つのパラメーターを含んでいます。1 つは予期されるテスト結果、もう 1 つは実際のテスト結果です。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-158">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="ad8ae-159">頻繁に呼び出されるメソッドには、次の表のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-159">Some of its most frequently called methods are shown in the table below.</span></span>

<span data-ttu-id="ad8ae-160">Assert メソッド</span><span class="sxs-lookup"><span data-stu-id="ad8ae-160">Assert methods</span></span> | <span data-ttu-id="ad8ae-161">関数</span><span class="sxs-lookup"><span data-stu-id="ad8ae-161">Function</span></span>
--- | ---
`Assert.AreEqual` | <span data-ttu-id="ad8ae-162">2 つの値または 2 つのオブジェクトが等しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-162">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="ad8ae-163">値またはオブジェクトが等しくない場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-163">The assert fails if the values or objects are not equal.</span></span>
`Assert.AreSame` | <span data-ttu-id="ad8ae-164">2 つのオブジェクト変数が同じオブジェクトを参照していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-164">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="ad8ae-165">変数が別々のオブジェクトを参照している場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-165">The assert fails if the variables refer to different objects.</span></span>
`Assert.IsFalse` | <span data-ttu-id="ad8ae-166">条件が `false` であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-166">Verifies that a condition is `false`.</span></span> <span data-ttu-id="ad8ae-167">条件が `true` の場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-167">The assert fails if the condition is `true`.</span></span>
`Assert.IsNotNull` | <span data-ttu-id="ad8ae-168">オブジェクトが `null` でないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-168">Verifies that an object is not `null`.</span></span> <span data-ttu-id="ad8ae-169">オブジェクトが `null` である場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-169">The assert fails if the object is `null`.</span></span>

<span data-ttu-id="ad8ae-170">テスト メソッドに <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> 属性を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-170">You can also apply the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> attribute to a test method.</span></span> <span data-ttu-id="ad8ae-171">テスト メソッドがスローすることを期待されている例外の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-171">It indicates the type of exception a test method is expected to throw.</span></span> <span data-ttu-id="ad8ae-172">指定した例外がスローされない場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-172">The test fails if the specified exception is not thrown.</span></span>

<span data-ttu-id="ad8ae-173">`StringLibrary.StartsWithUpper` メソッドのテストでは、大文字で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-173">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="ad8ae-174">これらの場合ではメソッドが `true` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-174">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> method.</span></span> <span data-ttu-id="ad8ae-175">同様に、大文字以外で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-175">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="ad8ae-176">これらの場合ではメソッドが `false` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-176">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> method.</span></span>

<span data-ttu-id="ad8ae-177">ライブラリ メソッドは文字列を処理するので、[空の文字列 (`String.Empty`) ](xref:System.String.Empty) (文字がなく <xref:System.String.Length> が 0 である、有効な文字列)、および `null` 文字列 (初期化されていない文字列) を正しく処理するか確認します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-177">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that has not been initialized.</span></span> <span data-ttu-id="ad8ae-178"><xref:System.String> インスタンスで `StartsWithUpper` が例外メソッドとして呼び出される場合、それに `null` 文字列を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-178">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it cannot be passed a `null` string.</span></span> <span data-ttu-id="ad8ae-179">しかし、それを静的メソッドとして直接呼び出して、単一の <xref:System.String> 引数を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-179">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="ad8ae-180">メソッドを 3 つ定義します。これらのメソッドでは、文字列配列の各要素について <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> メソッドが繰り返し呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-180">You'll define three methods, each of which calls its <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="ad8ae-181">テスト メソッドは最初のエラーが発生するとすぐに失敗するので、メソッドのオーバー ロードを呼び出して、メソッドの呼び出しで使用される文字列値を示す文字列を渡すようにします。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-181">Because the test method fails as soon as it encounters the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="ad8ae-182">テスト メソッドを作成するには</span><span class="sxs-lookup"><span data-stu-id="ad8ae-182">To create the test methods:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="ad8ae-183">C#</span><span class="sxs-lookup"><span data-stu-id="ad8ae-183">C#</span></span>](#tab/csharp) 
1. <span data-ttu-id="ad8ae-184">*UnitTest1.cs* コード ウィンドウで、コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-184">In the *UnitTest1.cs* code window, replace the code with the following code:</span></span>

   [!CODE-csharp[Test#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]

   <span data-ttu-id="ad8ae-185">`TestStartsWithUpper` メソッドでの大文字のテストには、ギリシャ語の大文字のアルファ (U+0391) とキリル文字の大文字 EM (U+041C) が含まれており、`TestDoesNotStartWithUpper` メソッドでの小文字のテストにはギリシャ語の小文字のアルファ (U+03B1) とキリル文字の小文字 Ghe (U+0433) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-185">Note that your test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C), and the test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="ad8ae-186">メニュー バーで、 **[ファイル]**  >  **[名前を付けて UnitTest1.cs を保存]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-186">On the menu bar, select **File** > **Save UnitTest1.cs As**.</span></span> <span data-ttu-id="ad8ae-187">**[名前を付けてファイルを保存]** ダイアログで、 **[保存]** ボタンの横にある矢印を選択して、 **[エンコード付きで保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-187">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   ![Visual Studio の [名前を付けてファイルを保存] ダイアログ - C#](./media/testing-library-with-visual-studio/save-file-as-dialog.png)
# <a name="visual-basictabvb"></a>[<span data-ttu-id="ad8ae-189">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad8ae-189">Visual Basic</span></span>](#tab/vb) 
1. <span data-ttu-id="ad8ae-190">*UnitTest1.vb* コード ウィンドウで、コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-190">In the *UnitTest1.vb* code window, replace the code with the following code:</span></span>

    [!CODE-vb[Test#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="ad8ae-191">`TestStartsWithUpper` メソッドでの大文字のテストには、ギリシャ語の大文字のアルファ (U+0391) とキリル文字の大文字 EM (U+041C) が含まれており、`TestDoesNotStartWithUpper` メソッドでの小文字のテストにはギリシャ語の小文字のアルファ (U+03B1) とキリル文字の小文字 Ghe (U+0433) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-191">Note that your test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C), and the test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="ad8ae-192">メニュー バーで、 **[ファイル]**  >  **[名前を付けて UnitTest1.vb を保存]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-192">On the menu bar, select **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="ad8ae-193">**[名前を付けてファイルを保存]** ダイアログで、 **[保存]** ボタンの横にある矢印を選択して、 **[エンコード付きで保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-193">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   ![Visual Studio の [名前を付けてファイルを保存] ダイアログ - Visual Basic](./media/testing-library-with-visual-studio/save-file-as-dialog.png)
---

1. <span data-ttu-id="ad8ae-195">**[保存の確認]** ダイアログで **[はい]** ボタンを選択してファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-195">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="ad8ae-196">**[保存オプションの詳細設定]** ダイアログの **[エンコード]** ドロップダウン リストから **[Unicode (UTF-8 シグネチャ付き) - コードページ 65001]** を選択し、 **[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-196">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   ![Visual Studio の [保存オプションの詳細設定] ダイアログ](./media/testing-library-with-visual-studio/advanced-save-options.png)

   <span data-ttu-id="ad8ae-198">UTF8 でエンコードされたファイルにソース コードを保存できなかった場合、ASCII ファイルとして保存される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-198">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="ad8ae-199">その場合は、ランタイムで ASCII 範囲外の UTF8 文字が正確にデコードされず、テスト結果が正確でなくなります。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-199">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be accurate.</span></span>

1. <span data-ttu-id="ad8ae-200">メニュー バーで **[テスト]**  >  **[実行]**  >  **[すべてのテスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-200">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="ad8ae-201">**[テスト エクスプローラー]** ウィンドウが開き、テストが正常に実行されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-201">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="ad8ae-202">3 つのテストが **[成功したテスト]** セクションに表示され、 **[概要]** セクションにはテストの実行結果が表示されています。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-202">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   ![[テスト エクスプローラー] ウィンドウと成功したテスト](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handling-test-failures"></a><span data-ttu-id="ad8ae-204">テスト エラーの処理</span><span class="sxs-lookup"><span data-stu-id="ad8ae-204">Handling test failures</span></span>

<span data-ttu-id="ad8ae-205">テスト実行にはエラーがなかったので、少し変更を加えてテスト メソッドが 1 つ失敗するようにしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-205">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="ad8ae-206">`TestDoesNotStartWithUpper` メソッドの `words` 配列を変更し、文字列 "Error" を含めます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-206">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="ad8ae-207">ソリューションをビルドし、テストを実行するときに、Visual Studio では、自動的に開いているファイルが保存されるため、ファイルは保存する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-207">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="ad8ae-208">**[テスト]**  >  **[実行]**  >  **[すべてのテスト]** をメニュー バーから選択してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-208">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="ad8ae-209">**[テスト エクスプローラー]** ウィンドウに、テストが 2 つ成功し、1 つ失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-209">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   ![[テスト エクスプローラー] ウィンドウと失敗したテスト](./media/testing-library-with-visual-studio/failed-test-window.png)

1. <span data-ttu-id="ad8ae-211">**[失敗したテスト]** セクションで、失敗したテスト `TestDoesNotStartWith` を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-211">In the **Failed Tests** section, select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="ad8ae-212">**[テスト エクスプローラー]** ウィンドウに、アサートによって生成されたメッセージ"Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="ad8ae-212">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="ad8ae-213">Expected for 'Error': false; actual:True" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-213">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="ad8ae-214">エラーのため、配列内の "Error" の後ろのすべての文字列はテストされませんでした。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-214">Because of the failure, all strings in the array after "Error" were not tested.</span></span>

   ![Is False アサーションの失敗を示す [テスト エクスプローラー] ウィンドウ](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. <span data-ttu-id="ad8ae-216">手順 1 で行った変更を元に戻し、文字列 "Error" を削除します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-216">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="ad8ae-217">テストを再実行すると、テストは成功します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-217">Rerun the test and the tests will pass.</span></span>

## <a name="testing-the-release-version-of-the-library"></a><span data-ttu-id="ad8ae-218">ライブラリのリリース バージョンのテスト</span><span class="sxs-lookup"><span data-stu-id="ad8ae-218">Testing the Release version of the library</span></span>

<span data-ttu-id="ad8ae-219">ここまで、ライブラリのデバッグ バージョンをテストしてきました。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-219">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="ad8ae-220">すべてのテストが成功し、ライブラリを十分にテストしたので、さらにライブラリのリリース ビルドに対してテストを行います。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-220">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="ad8ae-221">コンパイラの最適化などのさまざまな要因により、デバッグ ビルドとリリース ビルドとでは動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-221">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="ad8ae-222">リリース ビルドをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-222">To test the Release build:</span></span>

1. <span data-ttu-id="ad8ae-223">Visual Studio のツールバーで、ビルド構成を **[デバッグ]** から **[リリース]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-223">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   ![リリース ビルドが強調表示された Visual Studio のツールバー](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="ad8ae-225">**ソリューション エクスプローラー**で **[StringLibrary]** プロジェクトを右クリックし、コンテキスト メニューの **[ビルド]** を選択し、ライブラリを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-225">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   ![StringLibrary のコンテキスト メニューとビルド コマンド](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. <span data-ttu-id="ad8ae-227">**[テスト]**  >  **[実行]**  >  **[すべてのテスト]** をメニュー バーから選択して単体テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-227">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="ad8ae-228">テストが成功します。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-228">The tests pass.</span></span>

<span data-ttu-id="ad8ae-229">これでライブラリのテストが完了したので、次の手順では呼び出し元が使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-229">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="ad8ae-230">1 つまたは複数のアプリケーションとバンドルするか、NuGet パッケージとして配布することができます。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-230">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="ad8ae-231">詳細については、「[Consuming a .NET Standard Class Library ](./consuming-library-with-visual-studio.md)」 (.NET Standard クラス ライブラリを使用する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad8ae-231">For more information, see [Consuming a .NET Standard Class Library](./consuming-library-with-visual-studio.md).</span></span>
