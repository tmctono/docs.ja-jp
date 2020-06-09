---
title: Visual Studio での .NET Core を使用した .NET Standard クラス ライブラリのテスト
description: .NET Core クラス ライブラリ用の単体テスト プロジェクトを作成します。 .NET Core クラス ライブラリが単体テストで正しく動作することを確認します。
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 48ada77b8422030fd93aa29df1df50a3ae5104fe
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283508"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="bfa43-104">チュートリアル: Visual Studio での .NET Core を使用した .NET Standard ライブラリのテスト</span><span class="sxs-lookup"><span data-stu-id="bfa43-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="bfa43-105">このチュートリアルでは、テスト プロジェクトをソリューションに追加して、単体テストを自動化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfa43-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bfa43-106">Prerequisites</span></span>

- <span data-ttu-id="bfa43-107">このチュートリアルでは、「[Visual Studio で .NET Standard ライブラリを構築する](library-with-visual-studio.md)」で作成したソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="bfa43-108">単体テスト プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="bfa43-108">Create a unit test project</span></span>

1. <span data-ttu-id="bfa43-109">「[Visual Studio で .NET Standard ライブラリを構築する](library-with-visual-studio.md)」で作成した `ClassLibraryProjects` ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-109">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="bfa43-110">「StringLibraryTest」 という名前の新しい単体テスト プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-110">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="bfa43-111">**ソリューション エクスプローラー**で、ソリューションを右クリックし、 **[追加]**  >  **[新しいプロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-111">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="bfa43-112">**[新しいプロジェクトの追加]** ページで、検索ボックスに「**mstest**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-112">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="bfa43-113">言語の一覧から **[C#]** または **[Visual Basic]** を選択し、次に、プラットフォームの一覧から **[すべてのプラットフォーム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-113">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="bfa43-114">**[MsTest テスト プロジェクト (.NET Core)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-114">Choose the **MSTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="bfa43-115">**[新しいプロジェクトの構成]** ページで、 **[プロジェクト名]** ボックスに「**StringLibraryTest**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-115">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="bfa43-116">次に、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-116">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bfa43-117">MSTest は、選択できる 3 つのテストフレームワークのうちの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="bfa43-117">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="bfa43-118">これ以外は、xUnit と nUnit です。</span><span class="sxs-lookup"><span data-stu-id="bfa43-118">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="bfa43-119">Visual Studio によってプロジェクトが作成され、クラス ファイルが次のコードでコード ウィンドウに開かれます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-119">Visual Studio creates the project and opens the class file in the code window with the following code.</span></span> <span data-ttu-id="bfa43-120">使用する言語で表示されていない場合は、ページの上部にある言語セレクターを変更します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-120">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   <span data-ttu-id="bfa43-121">単体テストのテンプレートで作成されたソース コードにより、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-121">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="bfa43-122">単体テストで使用される型が含まれた <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-122">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="bfa43-123"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 属性が `UnitTest1` クラスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-123">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="bfa43-124"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性を適用して、C# では `TestMethod1` を、また Visual Basic では `TestSub` が定義されます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic.</span></span>

   <span data-ttu-id="bfa43-125">[[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)でタグ付けされたテスト クラスの [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) でタグ付けされた各テスト メソッドが、単体テスト実行時に自動実行されます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-125">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="bfa43-126">**ソリューション エクスプローラー**で **[StringLibraryTest]** プロジェクトの **[依存関係]** ノードを右クリックし、コンテキスト メニューの **[プロジェクト参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-126">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Project Reference** from the context menu.</span></span>

1. <span data-ttu-id="bfa43-127">**[参照マネージャー]** ダイアログで、 **[プロジェクト]** ノードを展開し、 **[StringLibrary]** の横のボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bfa43-127">In the **Reference Manager** dialog, expand the **Projects** node, and select the box next to **StringLibrary**.</span></span> <span data-ttu-id="bfa43-128">`StringLibrary` アセンブリに参照を追加すると、コンパイラが **StringLibraryTest** プロジェクトをコンパイル中に、**StringLibrary** メソッドを見つけることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfa43-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods while compiling the **StringLibraryTest** project.</span></span>

1. <span data-ttu-id="bfa43-129">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-129">Select **OK**.</span></span>

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="bfa43-130">単体テスト メソッドの追加と実行</span><span class="sxs-lookup"><span data-stu-id="bfa43-130">Add and run unit test methods</span></span>

<span data-ttu-id="bfa43-131">Visual Studio で単体テストを実行すると、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 属性でマークされたクラス内で、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性でマークされた各メソッドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-131">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="bfa43-132">テスト メソッドは、最初の失敗が検出されたとき、またはそのメソッドに含まれているすべてのテストが成功したときに終了します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-132">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="bfa43-133">一般的なテストでは、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> クラスのメンバーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-133">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="bfa43-134">多くのアサート メソッドは最低 2 つのパラメーターを含んでいます。1 つは予期されるテスト結果、もう 1 つは実際のテスト結果です。</span><span class="sxs-lookup"><span data-stu-id="bfa43-134">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="bfa43-135">次の表に、`Assert` クラスの頻繁に呼び出されるメソッドをいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-135">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="bfa43-136">Assert メソッド</span><span class="sxs-lookup"><span data-stu-id="bfa43-136">Assert methods</span></span>     | <span data-ttu-id="bfa43-137">関数</span><span class="sxs-lookup"><span data-stu-id="bfa43-137">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="bfa43-138">2 つの値または 2 つのオブジェクトが等しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-138">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="bfa43-139">値またはオブジェクトが等しくない場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-139">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="bfa43-140">2 つのオブジェクト変数が同じオブジェクトを参照していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-140">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="bfa43-141">変数が別々のオブジェクトを参照している場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-141">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="bfa43-142">条件が `false` であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-142">Verifies that a condition is `false`.</span></span> <span data-ttu-id="bfa43-143">条件が `true` の場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-143">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="bfa43-144">オブジェクトが `null` でないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-144">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="bfa43-145">オブジェクトが `null` である場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-145">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="bfa43-146">また、テスト メソッドで <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> メソッドを使用して、スローすることが期待される例外の種類を示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-146">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="bfa43-147">指定した例外がスローされない場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-147">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="bfa43-148">`StringLibrary.StartsWithUpper` メソッドのテストでは、大文字で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-148">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="bfa43-149">これらの場合ではメソッドが `true` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-149">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bfa43-150">同様に、大文字以外で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-150">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="bfa43-151">これらの場合ではメソッドが `false` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-151">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="bfa43-152">ライブラリ メソッドは文字列を処理するため、[空の文字列 (`String.Empty`) ](xref:System.String.Empty) (文字がなく <xref:System.String.Length> が 0 である有効な文字列)、および初期化されていない `null` 文字列を正しく処理することも確認します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-152">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="bfa43-153"><xref:System.String> インスタンスで `StartsWithUpper` が拡張メソッドとして呼び出される場合、それに `null` 文字列を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="bfa43-153">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="bfa43-154">しかし、それを静的メソッドとして直接呼び出して、単一の <xref:System.String> 引数を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-154">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="bfa43-155">メソッドを 3 つ定義します。これらのメソッドでは、文字列配列の各要素について <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> メソッドが繰り返し呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-155">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="bfa43-156">テスト メソッドは最初の失敗を検出するとすぐに失敗するので、メソッドのオーバー ロードを呼び出して、メソッドの呼び出しで使用される文字列値を示す文字列を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-156">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="bfa43-157">テスト メソッドを作成するには</span><span class="sxs-lookup"><span data-stu-id="bfa43-157">To create the test methods:</span></span>

1. <span data-ttu-id="bfa43-158">*UnitTest1.cs* または *UnitTest1.vb* コード ウィンドウで、コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-158">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibraryTest/UnitTest1.vb":::

   <span data-ttu-id="bfa43-159">`TestStartsWithUpper` メソッドの大文字のテストには、ギリシャ語の大文字のアルファ (U+0391) とキリル文字の大文字 EM (U+041C) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfa43-159">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="bfa43-160">`TestDoesNotStartWithUpper` メソッドの小文字のテストには、ギリシャ語の小文字のアルファ (U+03B1) とキリル文字の小文字 Ghe (U+0433) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfa43-160">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="bfa43-161">メニュー バーで、 **[ファイル]**  >  **[名前を付けて UnitTest1.cs を保存]** または **[ファイル]**  >  **[名前を付けて UnitTest1.vb を保存]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-161">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="bfa43-162">**[名前を付けてファイルを保存]** ダイアログで、 **[保存]** ボタンの横にある矢印を選択して、 **[エンコード付きで保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-162">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfa43-163">![Visual Studio の [名前を付けてファイルを保存] ダイアログ](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="bfa43-163">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="bfa43-164">**[保存の確認]** ダイアログで **[はい]** ボタンを選択してファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-164">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="bfa43-165">**[保存オプションの詳細設定]** ダイアログの **[エンコード]** ドロップダウン リストから **[Unicode (UTF-8 シグネチャ付き) - コードページ 65001]** を選択し、 **[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-165">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfa43-166">![Visual Studio の [保存オプションの詳細設定] ダイアログ](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="bfa43-166">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="bfa43-167">UTF8 でエンコードされたファイルにソース コードを保存できなかった場合、ASCII ファイルとして保存される場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfa43-167">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="bfa43-168">その場合は、ランタイムで ASCII 範囲外の UTF8 文字が正確にデコードされず、テスト結果が正確でなくなります。</span><span class="sxs-lookup"><span data-stu-id="bfa43-168">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="bfa43-169">メニュー バーで **[テスト]**  >  **[すべてのテストを実行する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-169">On the menu bar, select **Test** > **Run All Tests**.</span></span> <span data-ttu-id="bfa43-170">**テスト エクスプローラー** ウィンドウが開かない場合は、 **[テスト]**  >  **[テスト エクスプローラー]** を選択して開きます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-170">If the **Test Explorer** window doesn't open, open it by choosing **Test** > **Test Explorer**.</span></span> <span data-ttu-id="bfa43-171">3 つのテストが **[成功したテスト]** セクションに表示され、 **[概要]** セクションにはテストの実行結果が表示されています。</span><span class="sxs-lookup"><span data-stu-id="bfa43-171">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfa43-172">![[テスト エクスプローラー] ウィンドウと成功したテスト](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="bfa43-172">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="bfa43-173">テストの失敗の処理</span><span class="sxs-lookup"><span data-stu-id="bfa43-173">Handle test failures</span></span>

<span data-ttu-id="bfa43-174">テスト駆動開発 (TDD) を行っている場合、最初にテストを作成すると、1 回目のテスト実行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-174">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="bfa43-175">その後、テストを成功させるコードをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-175">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="bfa43-176">この場合は、検証するアプリ コードを記述した後にテストを作成しているので、テストの失敗が確認されることはありません。</span><span class="sxs-lookup"><span data-stu-id="bfa43-176">In this case, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="bfa43-177">テストの失敗が予想されるときにテストが失敗することを検証するには、テスト入力に無効な値を追加します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-177">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="bfa43-178">`TestDoesNotStartWithUpper` メソッドの `words` 配列を変更し、文字列 "Error" を含めます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-178">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="bfa43-179">ソリューションをビルドし、テストを実行するときに、Visual Studio では、自動的に開いているファイルが保存されるため、ファイルは保存する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bfa43-179">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="bfa43-180">メニュー バーから **[テスト]**  >  **[すべてのテストを実行]** を選択してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-180">Run the test by selecting **Test** > **Run All Tests** from the menu bar.</span></span> <span data-ttu-id="bfa43-181">**[テスト エクスプローラー]** ウィンドウに、テストが 2 つ成功し、1 つ失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-181">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfa43-182">![[テスト エクスプローラー] ウィンドウと失敗したテスト](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="bfa43-182">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="bfa43-183">失敗したテスト `TestDoesNotStartWith` を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-183">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="bfa43-184">**[テスト エクスプローラー]** ウィンドウに、アサートによって生成されたメッセージ"Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="bfa43-184">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="bfa43-185">Expected for 'Error': false; actual:True" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-185">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="bfa43-186">失敗のため、配列内の "Error" の後ろのすべての文字列はテストされませんでした。</span><span class="sxs-lookup"><span data-stu-id="bfa43-186">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfa43-187">![IsFalse アサーションの失敗を示す [テスト エクスプローラー] ウィンドウ](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="bfa43-187">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="bfa43-188">手順 1 で行った変更を元に戻し、文字列 "Error" を削除します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-188">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="bfa43-189">テストを再実行すると、テストは成功します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-189">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="bfa43-190">ライブラリのリリース バージョンのテスト</span><span class="sxs-lookup"><span data-stu-id="bfa43-190">Test the Release version of the library</span></span>

<span data-ttu-id="bfa43-191">ライブラリのデバッグ バージョンを実行すると、すべてのテストが成功するようになったので、さらにライブラリのリリース ビルドに対してテストを行います。</span><span class="sxs-lookup"><span data-stu-id="bfa43-191">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="bfa43-192">コンパイラの最適化などのさまざまな要因により、デバッグ ビルドとリリース ビルドとでは動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfa43-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="bfa43-193">リリース ビルドをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bfa43-193">To test the Release build:</span></span>

1. <span data-ttu-id="bfa43-194">Visual Studio のツールバーで、ビルド構成を **[デバッグ]** から **[リリース]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfa43-195">![リリース ビルドが強調表示された Visual Studio のツールバー](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="bfa43-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="bfa43-196">**ソリューション エクスプローラー**で **[StringLibrary]** プロジェクトを右クリックし、コンテキスト メニューの **[ビルド]** を選択し、ライブラリを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="bfa43-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfa43-197">![StringLibrary のコンテキスト メニューとビルド コマンド](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="bfa43-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="bfa43-198">**[テストの実行]**  >  **[すべてのテスト]** をメニュー バーから選択して単体テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-198">Run the unit tests by choosing **Test Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="bfa43-199">テストが成功します。</span><span class="sxs-lookup"><span data-stu-id="bfa43-199">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bfa43-200">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="bfa43-200">Additional resources</span></span>

- [<span data-ttu-id="bfa43-201">Visual Studio - 単体テストの基本</span><span class="sxs-lookup"><span data-stu-id="bfa43-201">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)

## <a name="next-steps"></a><span data-ttu-id="bfa43-202">次の手順</span><span class="sxs-lookup"><span data-stu-id="bfa43-202">Next steps</span></span>

<span data-ttu-id="bfa43-203">このチュートリアルでは、クラス ライブラリの単体テストを行いました。</span><span class="sxs-lookup"><span data-stu-id="bfa43-203">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="bfa43-204">ライブラリをパッケージとして [NuGet](https://nuget.org) に発行した場合、他のユーザーもそれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-204">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="bfa43-205">方法については、次の NuGet のチュートリアルに従ってください。</span><span class="sxs-lookup"><span data-stu-id="bfa43-205">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bfa43-206">Visual Studio を使用した NuGet パッケージの作成と公開</span><span class="sxs-lookup"><span data-stu-id="bfa43-206">Create and publish a NuGet package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli)

<span data-ttu-id="bfa43-207">ライブラリを NuGet パッケージとして発行した場合、他のユーザーもそれをインストールして使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-207">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="bfa43-208">方法については、次の NuGet のチュートリアルに従ってください。</span><span class="sxs-lookup"><span data-stu-id="bfa43-208">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bfa43-209">Visual Studio でパッケージをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="bfa43-209">Install and use a package in Visual Studio</span></span>](/nuget/quickstart/install-and-use-a-package-in-visual-studio)

<span data-ttu-id="bfa43-210">ライブラリはパッケージとして配布する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bfa43-210">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="bfa43-211">それが使用されるコンソール アプリにバンドルすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfa43-211">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="bfa43-212">コンソール アプリを発行する方法については、このシリーズの前のチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfa43-212">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bfa43-213">Visual Studio での .NET Core コンソール アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="bfa43-213">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
