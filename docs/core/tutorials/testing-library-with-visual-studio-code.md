---
title: Visual Studio Code での .NET Core を使用した .NET Standard クラス ライブラリのテスト
description: .NET Core クラス ライブラリ用の単体テスト プロジェクトを作成します。 .NET Core クラス ライブラリが単体テストで正しく動作することを確認します。
ms.date: 05/29/2020
ms.openlocfilehash: be227453bd441028cc6ce348c00fad944140238f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292163"
---
# <a name="tutorial-test-a-net-standard-library-with-net-core-in-visual-studio-code"></a><span data-ttu-id="f55a1-104">チュートリアル: Visual Studio Code での .NET Core を使用した .NET Standard ライブラリのテスト</span><span class="sxs-lookup"><span data-stu-id="f55a1-104">Tutorial: Test a .NET Standard library with .NET Core in Visual Studio Code</span></span>

<span data-ttu-id="f55a1-105">このチュートリアルでは、テスト プロジェクトをソリューションに追加して、単体テストを自動化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f55a1-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f55a1-106">Prerequisites</span></span>

- <span data-ttu-id="f55a1-107">このチュートリアルでは、「[Visual Studio Code での .NET Standard ライブラリの作成](library-with-visual-studio-code.md)」で作成したソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="f55a1-108">単体テスト プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="f55a1-108">Create a unit test project</span></span>

1. <span data-ttu-id="f55a1-109">Visual Studio Code を開きます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-109">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="f55a1-110">「[Visual Studio で .NET Standard ライブラリを構築する](library-with-visual-studio.md)」で作成した `ClassLibraryProjects` ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-110">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="f55a1-111">「StringLibraryTest」という名前の単体テスト プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-111">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="f55a1-112">プロジェクト テンプレートでは、次のコードを使用して UnitTest1.cs ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-112">The project template creates a UnitTest1.cs file with the following code:</span></span>

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

   <span data-ttu-id="f55a1-113">単体テストのテンプレートで作成されたソース コードにより、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-113">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="f55a1-114">単体テストで使用される型が含まれた <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-114">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="f55a1-115"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 属性が `UnitTest1` クラスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-115">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="f55a1-116"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性を適用して `TestMethod1` を定義します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-116">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="f55a1-117">[[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)でタグ付けされたテスト クラスの [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) でタグ付けされた各テスト メソッドが、単体テスト実行時に自動実行されます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-117">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f55a1-118">MSTest は、選択できる 3 つのテストフレームワークのうちの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="f55a1-118">MSTest is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="f55a1-119">これ以外は、xUnit と nUnit です。</span><span class="sxs-lookup"><span data-stu-id="f55a1-119">The others are xUnit and nUnit.</span></span>

1. <span data-ttu-id="f55a1-120">次のように、テスト プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-120">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

1. <span data-ttu-id="f55a1-121">次のコマンドを実行して、クラス ライブラリ プロジェクトへのプロジェクト参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-121">Create a project reference to the class library project by running the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="f55a1-122">単体テスト メソッドの追加と実行</span><span class="sxs-lookup"><span data-stu-id="f55a1-122">Add and run unit test methods</span></span>

<span data-ttu-id="f55a1-123">Visual Studio で単体テストを実行すると、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 属性でマークされたクラス内で、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性でマークされた各メソッドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-123">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="f55a1-124">テスト メソッドは、最初の失敗が検出されたとき、またはそのメソッドに含まれているすべてのテストが成功したときに終了します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-124">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="f55a1-125">一般的なテストでは、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> クラスのメンバーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-125">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="f55a1-126">多くのアサート メソッドは最低 2 つのパラメーターを含んでいます。1 つは予期されるテスト結果、もう 1 つは実際のテスト結果です。</span><span class="sxs-lookup"><span data-stu-id="f55a1-126">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="f55a1-127">次の表に、`Assert` クラスの頻繁に呼び出されるメソッドをいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-127">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="f55a1-128">Assert メソッド</span><span class="sxs-lookup"><span data-stu-id="f55a1-128">Assert methods</span></span>     | <span data-ttu-id="f55a1-129">関数</span><span class="sxs-lookup"><span data-stu-id="f55a1-129">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="f55a1-130">2 つの値または 2 つのオブジェクトが等しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-130">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="f55a1-131">値またはオブジェクトが等しくない場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-131">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="f55a1-132">2 つのオブジェクト変数が同じオブジェクトを参照していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-132">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="f55a1-133">変数が別々のオブジェクトを参照している場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-133">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="f55a1-134">条件が `false` であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-134">Verifies that a condition is `false`.</span></span> <span data-ttu-id="f55a1-135">条件が `true` の場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-135">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="f55a1-136">オブジェクトが `null` でないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-136">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="f55a1-137">オブジェクトが `null` である場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-137">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="f55a1-138">また、テスト メソッドで <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> メソッドを使用して、スローすることが期待される例外の種類を示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-138">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="f55a1-139">指定した例外がスローされない場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-139">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="f55a1-140">`StringLibrary.StartsWithUpper` メソッドのテストでは、大文字で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-140">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="f55a1-141">これらの場合ではメソッドが `true` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-141">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f55a1-142">同様に、大文字以外で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-142">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="f55a1-143">これらの場合ではメソッドが `false` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-143">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f55a1-144">ライブラリ メソッドでは文字列を処理するため、[空の文字列 (`String.Empty`)](xref:System.String.Empty) および `null` 文字列を正常に処理することも確認します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-144">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="f55a1-145">空の文字列は、文字を含まない、<xref:System.String.Length> が 0 の文字列です。</span><span class="sxs-lookup"><span data-stu-id="f55a1-145">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="f55a1-146">`null` 文字列は、初期化されていない文字列です。</span><span class="sxs-lookup"><span data-stu-id="f55a1-146">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="f55a1-147">しかし、`StartsWithUpper` を静的メソッドとして直接呼び出して、単一の <xref:System.String> 引数を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-147">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="f55a1-148">または、`null` に割り当てられた `string` 変数の拡張メソッドとして `StartsWithUpper` を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-148">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="f55a1-149">メソッドを 3 つ定義します。これらのメソッドでは、文字列配列の各要素について <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> メソッドが繰り返し呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-149">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="f55a1-150">テスト メソッドは最初の失敗を検出するとすぐに失敗するので、メソッドのオーバー ロードを呼び出して、メソッドの呼び出しで使用される文字列値を示す文字列を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-150">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="f55a1-151">テスト メソッドを作成するには</span><span class="sxs-lookup"><span data-stu-id="f55a1-151">To create the test methods:</span></span>

1. <span data-ttu-id="f55a1-152">*StringLibraryTest/UnitTest1.cs* を開き、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-152">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="f55a1-153">`TestStartsWithUpper` メソッドの大文字のテストには、ギリシャ語の大文字のアルファ (U+0391) とキリル文字の大文字 EM (U+041C) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f55a1-153">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="f55a1-154">`TestDoesNotStartWithUpper` メソッドの小文字のテストには、ギリシャ語の小文字のアルファ (U+03B1) とキリル文字の小文字 Ghe (U+0433) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f55a1-154">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="f55a1-155">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-155">Save your changes.</span></span>

1. <span data-ttu-id="f55a1-156">テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-156">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="f55a1-157">次のターミナル出力は、すべてのテストが成功したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="f55a1-157">The terminal output shows that all tests passed.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="f55a1-158">テストの失敗の処理</span><span class="sxs-lookup"><span data-stu-id="f55a1-158">Handle test failures</span></span>

<span data-ttu-id="f55a1-159">テスト駆動開発 (TDD) を行っている場合、最初にテストを作成すると、1 回目のテスト実行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-159">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="f55a1-160">その後、テストを成功させるコードをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-160">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="f55a1-161">この場合は、検証するアプリ コードを記述した後にテストを作成しているので、テストの失敗が確認されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f55a1-161">In this case, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="f55a1-162">テストの失敗が予想されるときにテストが失敗することを検証するには、テスト入力に無効な値を追加します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-162">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="f55a1-163">`TestDoesNotStartWithUpper` メソッドの `words` 配列を変更し、文字列 "Error" を含めます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-163">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="f55a1-164">テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-164">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="f55a1-165">次のターミナル出力は、1 つのテストが失敗したことを示しており、失敗したテストに関するエラー メッセージが表示されています。</span><span class="sxs-lookup"><span data-stu-id="f55a1-165">The terminal output shows that one test fails, and it provides an error message for the failed test.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.
     X TestDoesNotStartWithUpper [283ms]
     Error Message:
      Assert.IsFalse failed. Expected for 'Error': false; Actual: True
     Stack Trace:
     at StringLibraryTest.UnitTest1.TestDoesNotStartWithUpper()
       in C:\Projects\ClassLibraryProjects\StringLibraryTest\UnitTest1.cs:line 33

   Test Run Failed.
   Total tests: 3
        Passed: 2
        Failed: 1
   Total time: 1.7825 Seconds
   ```

1. <span data-ttu-id="f55a1-166">手順 1 で行った変更を元に戻し、文字列 "Error" を削除します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-166">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="f55a1-167">テストを再実行すると、テストは成功します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-167">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="f55a1-168">ライブラリのリリース バージョンのテスト</span><span class="sxs-lookup"><span data-stu-id="f55a1-168">Test the Release version of the library</span></span>

<span data-ttu-id="f55a1-169">ライブラリのデバッグ バージョンを実行すると、すべてのテストが成功するようになったので、さらにライブラリのリリース ビルドに対してテストを行います。</span><span class="sxs-lookup"><span data-stu-id="f55a1-169">Now that the tests have all passed when running the Debug version of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="f55a1-170">コンパイラの最適化などのさまざまな要因により、デバッグ ビルドとリリース ビルドとでは動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f55a1-170">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="f55a1-171">リリース ビルド構成を使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-171">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="f55a1-172">テストが成功します。</span><span class="sxs-lookup"><span data-stu-id="f55a1-172">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f55a1-173">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="f55a1-173">Additional resources</span></span>

- [<span data-ttu-id="f55a1-174">.NET Core と .NET Standard の単体テスト</span><span class="sxs-lookup"><span data-stu-id="f55a1-174">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="f55a1-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="f55a1-175">Next steps</span></span>

<span data-ttu-id="f55a1-176">このチュートリアルでは、クラス ライブラリの単体テストを行いました。</span><span class="sxs-lookup"><span data-stu-id="f55a1-176">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="f55a1-177">ライブラリをパッケージとして [NuGet](https://nuget.org) に発行した場合、他のユーザーもそれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-177">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="f55a1-178">方法については、次の NuGet のチュートリアルに従ってください。</span><span class="sxs-lookup"><span data-stu-id="f55a1-178">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f55a1-179">dotnet CLI を使用したパッケージの作成と公開</span><span class="sxs-lookup"><span data-stu-id="f55a1-179">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="f55a1-180">ライブラリを NuGet パッケージとして発行した場合、他のユーザーもそれをインストールして使用できます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-180">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="f55a1-181">方法については、次の NuGet のチュートリアルに従ってください。</span><span class="sxs-lookup"><span data-stu-id="f55a1-181">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f55a1-182">dotnet CLI を使用してパッケージをインストールし使用する</span><span class="sxs-lookup"><span data-stu-id="f55a1-182">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="f55a1-183">ライブラリはパッケージとして配布する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f55a1-183">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="f55a1-184">それが使用されるコンソール アプリにバンドルすることができます。</span><span class="sxs-lookup"><span data-stu-id="f55a1-184">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="f55a1-185">コンソール アプリを発行する方法については、このシリーズの前のチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f55a1-185">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f55a1-186">Visual Studio Code を使用して .NET Core コンソール アプリケーションを発行する</span><span class="sxs-lookup"><span data-stu-id="f55a1-186">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
