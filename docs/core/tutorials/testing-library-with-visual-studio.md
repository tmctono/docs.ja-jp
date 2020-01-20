---
title: Visual Studio での .NET Core を使用した .NET Standard クラス ライブラリのテスト
description: .NET Core クラス ライブラリ用の単体テスト プロジェクトを作成します。 .NET Core クラス ライブラリが単体テストで正しく動作することを確認します。
ms.date: 12/24/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 3a4f25b0d250469102fdac6ee960e42b2d969aed
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559579"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="c1c44-104">Visual Studio での .NET Core を使用した .NET Standard ライブラリのテスト</span><span class="sxs-lookup"><span data-stu-id="c1c44-104">Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="c1c44-105">「[Visual Studio での .NET Standard ライブラリの構築](library-with-visual-studio.md)」では、<xref:System.String> クラスに拡張メソッドを追加する簡単なクラス ライブラリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="c1c44-105">In [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="c1c44-106">ここでは、それが期待どおり動作するかを確認する単体テストを作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="c1c44-106">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="c1c44-107">この単体テスト プロジェクトは、前の記事で作成したソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-107">You'll add your unit test project to the solution you created in the previous article.</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="c1c44-108">単体テスト プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c1c44-108">Create a unit test project</span></span>

<span data-ttu-id="c1c44-109">単体テスト プロジェクトを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c1c44-109">To create the unit test project, do the following:</span></span>

1. <span data-ttu-id="c1c44-110">[Visual Studio での .NET Standard ライブラリの構築](library-with-visual-studio.md)に関する記事で作成した `ClassLibraryProjects` ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-110">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="c1c44-111">「StringLibraryTest」 という名前の新しい単体テスト プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-111">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="c1c44-112">**ソリューション エクスプローラー**で、ソリューションを右クリックし、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-112">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="c1c44-113">**[新しいプロジェクトの追加]** ページで、検索ボックスに「**mstest**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-113">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="c1c44-114">言語のリストから **[C#]** または **[Visual Basic]** を選択し、次に、プラットフォームのリストから **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-114">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="c1c44-115">**[MsTest テスト プロジェクト (.NET Core)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-115">Choose the **MsTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="c1c44-116">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**StringLibraryTest**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-116">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="c1c44-117">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-117">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c1c44-118">MSTest に加え、Visual Studio で .NET Core 用の xUnit と nUnit テスト プロジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-118">In addition to an MSTest, you can also create xUnit and nUnit test projects for .NET Core in Visual Studio.</span></span>

1. <span data-ttu-id="c1c44-119">Visual Studio によってプロジェクトが作成され、次のコードでクラス ファイルがコード ウィンドウに開かれます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-119">Visual Studio creates the project and opens the class file in the code window with the following code:</span></span>

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

    namespace StringLibraryTest
    {
        [TestClass]
        public class UnitTest1
        {
            [TestMethod]
            public void TestMethod1()
            {
            }
        }
    }
    ```

    ```vb
    Imports Microsoft.VisualStudio.TestTools.UnitTesting
    
    Namespace StringLibraryTest
        <TestClass>
        Public Class UnitTest1
            <TestMethod>
            Sub TestSub()
    
            End Sub
        End Class
    End Namespace
    ```

   <span data-ttu-id="c1c44-120">単体テストのテンプレートで作成されたソース コードにより、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-120">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="c1c44-121">単体テストで使用される型が含まれた <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-121">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   - <span data-ttu-id="c1c44-122">[TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) 属性が `UnitTest1` クラスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-122">It applies the [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="c1c44-123">[TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) 属性でタグ付けされたテスト クラス内の各テスト メソッドは、単体テスト実行時に自動実行されます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-123">Each test method in a test class tagged with the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute is executed automatically when the unit test is run.</span></span>

   - <span data-ttu-id="c1c44-124">[TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) 属性が適用され、単体テスト実行時に自動実行されるテスト メソッドとして、C# では `TestMethod1`、Visual Basic では `TestSub` が定義されます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-124">It applies the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="c1c44-125">**ソリューション エクスプローラー**で **[StringLibraryTest]** プロジェクトの **[依存関係]** ノードを右クリックし、コンテキスト メニューの **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-125">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1c44-126">![StringLibraryTest の依存関係のコンテキスト メニュー](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="c1c44-126">![Context menu of StringLibraryTest dependencies](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span></span>

1. <span data-ttu-id="c1c44-127">**[参照マネージャー]** ダイアログで、 **[プロジェクト]** ノードを展開し、 **[StringLibrary]** の横のボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c1c44-127">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="c1c44-128">`StringLibrary` アセンブリへの参照を追加すると、コンパイラで **StringLibrary** メソッドを見つけることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="c1c44-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="c1c44-129">**[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-129">Select the **OK** button.</span></span> <span data-ttu-id="c1c44-130">クラス ライブラリ プロジェクト `StringLibrary` への参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-130">A reference is added to your class library project, `StringLibrary`.</span></span>

   ![Visual Studio の [参照マネージャー] ダイアログ](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="c1c44-132">単体テスト メソッドの追加と実行</span><span class="sxs-lookup"><span data-stu-id="c1c44-132">Add and run unit test methods</span></span>

<span data-ttu-id="c1c44-133">Visual Studio で単体テストを実行すると、単体テスト クラス (<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 属性が適用されているクラス) 内の <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性でマークされた各メソッドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-133">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a unit test class, the class to which the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute is applied.</span></span> <span data-ttu-id="c1c44-134">テスト メソッドは、最初の失敗が検出されたとき、またはそのメソッドに含まれているすべてのテストが成功したときに終了します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-134">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="c1c44-135">一般的なテストでは、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> クラスのメンバーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-135">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="c1c44-136">多くのアサート メソッドは最低 2 つのパラメーターを含んでいます。1 つは予期されるテスト結果、もう 1 つは実際のテスト結果です。</span><span class="sxs-lookup"><span data-stu-id="c1c44-136">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="c1c44-137">次の表に、`Assert` クラスの頻繁に呼び出されるメソッドをいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-137">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="c1c44-138">Assert メソッド</span><span class="sxs-lookup"><span data-stu-id="c1c44-138">Assert methods</span></span>     | <span data-ttu-id="c1c44-139">関数</span><span class="sxs-lookup"><span data-stu-id="c1c44-139">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="c1c44-140">2 つの値または 2 つのオブジェクトが等しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-140">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="c1c44-141">値またはオブジェクトが等しくない場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-141">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="c1c44-142">2 つのオブジェクト変数が同じオブジェクトを参照していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-142">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="c1c44-143">変数が別々のオブジェクトを参照している場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-143">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="c1c44-144">条件が `false` であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-144">Verifies that a condition is `false`.</span></span> <span data-ttu-id="c1c44-145">条件が `true` の場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-145">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="c1c44-146">オブジェクトが `null` でないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-146">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="c1c44-147">オブジェクトが `null` である場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-147">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="c1c44-148">また、テスト メソッドで <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> メソッドを使用して、スローすることが期待される例外の種類を示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-148">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="c1c44-149">指定した例外がスローされない場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-149">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="c1c44-150">`StringLibrary.StartsWithUpper` メソッドのテストでは、大文字で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-150">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="c1c44-151">これらの場合ではメソッドが `true` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-151">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> method.</span></span> <span data-ttu-id="c1c44-152">同様に、大文字以外で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-152">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="c1c44-153">これらの場合ではメソッドが `false` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-153">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> method.</span></span>

<span data-ttu-id="c1c44-154">ライブラリ メソッドは文字列を処理するため、[空の文字列 (`String.Empty`) ](xref:System.String.Empty) (文字がなく <xref:System.String.Length> が 0 である有効な文字列)、および初期化されていない `null` 文字列を正しく処理することも確認します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-154">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="c1c44-155"><xref:System.String> インスタンスで `StartsWithUpper` が拡張メソッドとして呼び出される場合、それに `null` 文字列を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="c1c44-155">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="c1c44-156">しかし、それを静的メソッドとして直接呼び出して、単一の <xref:System.String> 引数を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-156">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="c1c44-157">メソッドを 3 つ定義します。これらのメソッドでは、文字列配列の各要素について <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> メソッドが繰り返し呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-157">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="c1c44-158">テスト メソッドは最初の失敗を検出するとすぐに失敗するので、メソッドのオーバー ロードを呼び出して、メソッドの呼び出しで使用される文字列値を示す文字列を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-158">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="c1c44-159">テスト メソッドを作成するには</span><span class="sxs-lookup"><span data-stu-id="c1c44-159">To create the test methods:</span></span>

1. <span data-ttu-id="c1c44-160">*UnitTest1.cs* または *UnitTest1.vb* コード ウィンドウで、コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-160">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="c1c44-161">`TestStartsWithUpper` メソッドの大文字のテストには、ギリシャ語の大文字のアルファ (U+0391) とキリル文字の大文字 EM (U+041C) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1c44-161">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="c1c44-162">`TestDoesNotStartWithUpper` メソッドの小文字のテストには、ギリシャ語の小文字のアルファ (U+03B1) とキリル文字の小文字 Ghe (U+0433) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1c44-162">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="c1c44-163">メニュー バーで、 **[ファイル]**  >  **[名前を付けて UnitTest1.cs を保存]** または **[ファイル]**  >  **[名前を付けて UnitTest1.vb を保存]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-163">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="c1c44-164">**[名前を付けてファイルを保存]** ダイアログで、 **[保存]** ボタンの横にある矢印を選択して、 **[エンコード付きで保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-164">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1c44-165">![Visual Studio の [名前を付けてファイルを保存] ダイアログ](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="c1c44-165">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="c1c44-166">**[保存の確認]** ダイアログで **[はい]** ボタンを選択してファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-166">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="c1c44-167">**[保存オプションの詳細設定]** ダイアログの **[エンコード]** ドロップダウン リストから **[Unicode (UTF-8 シグネチャ付き) - コードページ 65001]** を選択し、 **[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-167">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1c44-168">![Visual Studio の [保存オプションの詳細設定] ダイアログ](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="c1c44-168">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="c1c44-169">UTF8 でエンコードされたファイルにソース コードを保存できなかった場合、ASCII ファイルとして保存される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c1c44-169">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="c1c44-170">その場合は、ランタイムで ASCII 範囲外の UTF8 文字が正確にデコードされず、テスト結果が正確でなくなります。</span><span class="sxs-lookup"><span data-stu-id="c1c44-170">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="c1c44-171">メニュー バーで **[テスト]**  >  **[実行]**  >  **[すべてのテスト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-171">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="c1c44-172">**[テスト エクスプローラー]** ウィンドウが開き、テストが正常に実行されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-172">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="c1c44-173">3 つのテストが **[成功したテスト]** セクションに表示され、 **[概要]** セクションにはテストの実行結果が表示されています。</span><span class="sxs-lookup"><span data-stu-id="c1c44-173">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1c44-174">![[テスト エクスプローラー] ウィンドウと成功したテスト](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="c1c44-174">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="c1c44-175">テストの失敗の処理</span><span class="sxs-lookup"><span data-stu-id="c1c44-175">Handle test failures</span></span>

<span data-ttu-id="c1c44-176">テスト実行にはエラーがなかったので、少し変更を加えてテスト メソッドが 1 つ失敗するようにしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="c1c44-176">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="c1c44-177">`TestDoesNotStartWithUpper` メソッドの `words` 配列を変更し、文字列 "Error" を含めます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-177">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="c1c44-178">ソリューションをビルドし、テストを実行するときに、Visual Studio では、自動的に開いているファイルが保存されるため、ファイルは保存する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c1c44-178">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="c1c44-179">**[テスト]**  >  **[実行]**  >  **[すべてのテスト]** をメニュー バーから選択してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-179">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="c1c44-180">**[テスト エクスプローラー]** ウィンドウに、テストが 2 つ成功し、1 つ失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-180">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1c44-181">![[テスト エクスプローラー] ウィンドウと失敗したテスト](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="c1c44-181">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="c1c44-182">失敗したテスト `TestDoesNotStartWith` を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-182">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="c1c44-183">**[テスト エクスプローラー]** ウィンドウに、アサートによって生成されたメッセージ"Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="c1c44-183">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="c1c44-184">Expected for 'Error': false; actual:True" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-184">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="c1c44-185">失敗のため、配列内の "Error" の後ろのすべての文字列はテストされませんでした。</span><span class="sxs-lookup"><span data-stu-id="c1c44-185">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1c44-186">![IsFalse アサーションの失敗を示す [テスト エクスプローラー] ウィンドウ](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="c1c44-186">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="c1c44-187">手順 1 で行った変更を元に戻し、文字列 "Error" を削除します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-187">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="c1c44-188">テストを再実行すると、テストは成功します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-188">Rerun the test and the tests will pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="c1c44-189">ライブラリのリリース バージョンのテスト</span><span class="sxs-lookup"><span data-stu-id="c1c44-189">Test the Release version of the library</span></span>

<span data-ttu-id="c1c44-190">ここまで、ライブラリのデバッグ バージョンをテストしてきました。</span><span class="sxs-lookup"><span data-stu-id="c1c44-190">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="c1c44-191">すべてのテストが成功し、ライブラリを十分にテストしたので、さらにライブラリのリリース ビルドに対してテストを行います。</span><span class="sxs-lookup"><span data-stu-id="c1c44-191">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="c1c44-192">コンパイラの最適化などのさまざまな要因により、デバッグ ビルドとリリース ビルドとでは動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c1c44-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="c1c44-193">リリース ビルドをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c1c44-193">To test the Release build:</span></span>

1. <span data-ttu-id="c1c44-194">Visual Studio のツールバーで、ビルド構成を **[デバッグ]** から **[リリース]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1c44-195">![リリース ビルドが強調表示された Visual Studio のツールバー](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="c1c44-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="c1c44-196">**ソリューション エクスプローラー**で **[StringLibrary]** プロジェクトを右クリックし、コンテキスト メニューの **[ビルド]** を選択し、ライブラリを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="c1c44-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1c44-197">![StringLibrary のコンテキスト メニューとビルド コマンド](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="c1c44-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="c1c44-198">**[テスト]**  >  **[実行]**  >  **[すべてのテスト]** をメニュー バーから選択して単体テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-198">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="c1c44-199">テストが成功します。</span><span class="sxs-lookup"><span data-stu-id="c1c44-199">The tests pass.</span></span>

<span data-ttu-id="c1c44-200">これでライブラリのテストが完了したので、次の手順では呼び出し元が使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c1c44-200">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="c1c44-201">1 つまたは複数のアプリケーションとバンドルするか、NuGet パッケージとして配布することができます。</span><span class="sxs-lookup"><span data-stu-id="c1c44-201">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="c1c44-202">詳細については、　[.NET Standard クラス ライブラリの使用](consuming-library-with-visual-studio.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1c44-202">For more information, see [Consuming a .NET Standard Class Library](consuming-library-with-visual-studio.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c1c44-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1c44-203">See also</span></span>

- [<span data-ttu-id="c1c44-204">Visual Studio - 単体テストの基本</span><span class="sxs-lookup"><span data-stu-id="c1c44-204">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
