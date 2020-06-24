---
title: Visual Studio Code を使用して .NET Core で .NET Standard クラス ライブラリをテストする
description: .NET Core クラス ライブラリ用の単体テスト プロジェクトを作成します。 .NET Core クラス ライブラリが単体テストで正しく動作することを確認します。
ms.date: 06/08/2020
ms.openlocfilehash: a61fd952eea2dec0d5a9f351d3f3d01c738e8fad
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701034"
---
# <a name="tutorial-test-a-net-standard-class-library-with-net-core-using-visual-studio-code"></a><span data-ttu-id="4f314-104">チュートリアル: Visual Studio Code を使用して .NET Core で .NET Standard クラス ライブラリをテストする</span><span class="sxs-lookup"><span data-stu-id="4f314-104">Tutorial: Test a .NET Standard class library with .NET Core using Visual Studio Code</span></span>

<span data-ttu-id="4f314-105">このチュートリアルでは、テスト プロジェクトをソリューションに追加して、単体テストを自動化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f314-105">This tutorial shows how to automate unit testing by adding a test project to a solution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4f314-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4f314-106">Prerequisites</span></span>

- <span data-ttu-id="4f314-107">このチュートリアルでは、「[Visual Studio Code での .NET Standard ライブラリの作成](library-with-visual-studio-code.md)」で作成したソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f314-107">This tutorial works with the solution that you create in [Create a .NET Standard library in Visual Studio Code](library-with-visual-studio-code.md).</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="4f314-108">単体テスト プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="4f314-108">Create a unit test project</span></span>

<span data-ttu-id="4f314-109">単体テストでは、開発および公開時に自動化されたソフトウェア テストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4f314-109">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="4f314-110">このチュートリアルで使用するテスト フレームワークは MSTest です。</span><span class="sxs-lookup"><span data-stu-id="4f314-110">The testing framework that you use in this tutorial is MSTest.</span></span> <span data-ttu-id="4f314-111">[MSTest](https://github.com/Microsoft/testfx-docs) は、選択できる 3 つのテスト フレームワークのうちの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="4f314-111">[MSTest](https://github.com/Microsoft/testfx-docs) is one of three test frameworks you can choose from.</span></span> <span data-ttu-id="4f314-112">これ以外は、[xUnit](https://xunit.net/) と [nUnit](https://nunit.org/) です。</span><span class="sxs-lookup"><span data-stu-id="4f314-112">The others are [xUnit](https://xunit.net/) and [nUnit](https://nunit.org/).</span></span>

1. <span data-ttu-id="4f314-113">Visual Studio Code を開始します。</span><span class="sxs-lookup"><span data-stu-id="4f314-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="4f314-114">「[Visual Studio で .NET Standard ライブラリを構築する](library-with-visual-studio.md)」で作成した `ClassLibraryProjects` ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f314-114">Open the `ClassLibraryProjects` solution you created in [Create a .NET Standard library in Visual Studio](library-with-visual-studio.md).</span></span>

1. <span data-ttu-id="4f314-115">「StringLibraryTest」という名前の単体テスト プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f314-115">Create a unit test project named "StringLibraryTest".</span></span>

   ```dotnetcli
   dotnet new mstest -o StringLibraryTest
   ```

   <span data-ttu-id="4f314-116">プロジェクト テンプレートでは、次のコードを使用して UnitTest1.cs ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f314-116">The project template creates a UnitTest1.cs file with the following code:</span></span>

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

   <span data-ttu-id="4f314-117">単体テストのテンプレートで作成されたソース コードにより、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="4f314-117">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="4f314-118">単体テストで使用される型が含まれた <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> 名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="4f314-118">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>
   - <span data-ttu-id="4f314-119"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 属性が `UnitTest1` クラスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f314-119">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span>
   - <span data-ttu-id="4f314-120"><xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性を適用して `TestMethod1` を定義します。</span><span class="sxs-lookup"><span data-stu-id="4f314-120">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1`.</span></span>

   <span data-ttu-id="4f314-121">[[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute)でタグ付けされたテスト クラスの [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) でタグ付けされた各テスト メソッドが、単体テスト実行時に自動実行されます。</span><span class="sxs-lookup"><span data-stu-id="4f314-121">Each method tagged with [[TestMethod]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) in a test class tagged with [[TestClass]](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) is executed automatically when the unit test is run.</span></span>

1. <span data-ttu-id="4f314-122">次のように、テスト プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4f314-122">Add the test project to the solution.</span></span>

   ```dotnetcli
   dotnet sln add StringLibraryTest/StringLibraryTest.csproj
   ```

## <a name="add-a-project-reference"></a><span data-ttu-id="4f314-123">プロジェクト参照を追加する</span><span class="sxs-lookup"><span data-stu-id="4f314-123">Add a project reference</span></span>

<span data-ttu-id="4f314-124">テスト プロジェクトが `StringLibrary` クラスと連動するように、`StringLibraryTest` プロジェクトに `StringLibrary` プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="4f314-124">For the test project to work with the `StringLibrary` class, add a reference in the `StringLibraryTest` project to the `StringLibrary` project.</span></span>

1. <span data-ttu-id="4f314-125">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4f314-125">Run the following command:</span></span>

   ```dotnetcli
   dotnet add StringLibraryTest/StringLibraryTest.csproj reference StringLibrary/StringLibrary.csproj
   ```

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="4f314-126">単体テスト メソッドの追加と実行</span><span class="sxs-lookup"><span data-stu-id="4f314-126">Add and run unit test methods</span></span>

<span data-ttu-id="4f314-127">Visual Studio で単体テストを実行すると、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> 属性でマークされたクラス内で、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> 属性でマークされた各メソッドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4f314-127">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a class that is marked with the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute.</span></span> <span data-ttu-id="4f314-128">テスト メソッドは、最初の失敗が検出されたとき、またはそのメソッドに含まれているすべてのテストが成功したときに終了します。</span><span class="sxs-lookup"><span data-stu-id="4f314-128">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="4f314-129">一般的なテストでは、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> クラスのメンバーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4f314-129">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="4f314-130">多くのアサート メソッドは最低 2 つのパラメーターを含んでいます。1 つは予期されるテスト結果、もう 1 つは実際のテスト結果です。</span><span class="sxs-lookup"><span data-stu-id="4f314-130">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="4f314-131">次の表に、`Assert` クラスの頻繁に呼び出されるメソッドをいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="4f314-131">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="4f314-132">Assert メソッド</span><span class="sxs-lookup"><span data-stu-id="4f314-132">Assert methods</span></span>     | <span data-ttu-id="4f314-133">関数</span><span class="sxs-lookup"><span data-stu-id="4f314-133">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="4f314-134">2 つの値または 2 つのオブジェクトが等しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f314-134">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="4f314-135">値またはオブジェクトが等しくない場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4f314-135">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="4f314-136">2 つのオブジェクト変数が同じオブジェクトを参照していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f314-136">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="4f314-137">変数が別々のオブジェクトを参照している場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4f314-137">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="4f314-138">条件が `false` であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f314-138">Verifies that a condition is `false`.</span></span> <span data-ttu-id="4f314-139">条件が `true` の場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4f314-139">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="4f314-140">オブジェクトが `null` でないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f314-140">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="4f314-141">オブジェクトが `null` である場合、アサートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4f314-141">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="4f314-142">また、テスト メソッドで <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> メソッドを使用して、スローすることが期待される例外の種類を示すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4f314-142">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="4f314-143">指定した例外がスローされない場合、テストは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4f314-143">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="4f314-144">`StringLibrary.StartsWithUpper` メソッドのテストでは、大文字で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="4f314-144">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="4f314-145">これらの場合ではメソッドが `true` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4f314-145">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4f314-146">同様に、大文字以外で始まる文字列を多く用意します。</span><span class="sxs-lookup"><span data-stu-id="4f314-146">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="4f314-147">これらの場合ではメソッドが `false` を返すと予測されるので、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4f314-147">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="4f314-148">ライブラリ メソッドでは文字列を処理するため、[空の文字列 (`String.Empty`)](xref:System.String.Empty) および `null` 文字列を正常に処理することも確認します。</span><span class="sxs-lookup"><span data-stu-id="4f314-148">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty) and a and a `null` string.</span></span> <span data-ttu-id="4f314-149">空の文字列は、文字を含まない、<xref:System.String.Length> が 0 の文字列です。</span><span class="sxs-lookup"><span data-stu-id="4f314-149">An empty string is one that has no characters and whose <xref:System.String.Length> is 0.</span></span> <span data-ttu-id="4f314-150">`null` 文字列は、初期化されていない文字列です。</span><span class="sxs-lookup"><span data-stu-id="4f314-150">A `null` string is one that hasn't been initialized.</span></span> <span data-ttu-id="4f314-151">しかし、`StartsWithUpper` を静的メソッドとして直接呼び出して、単一の <xref:System.String> 引数を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4f314-151">You can call `StartsWithUpper` directly as a static method and pass a single <xref:System.String> argument.</span></span> <span data-ttu-id="4f314-152">または、`null` に割り当てられた `string` 変数の拡張メソッドとして `StartsWithUpper` を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4f314-152">Or you can call `StartsWithUpper` as an extension method on a `string` variable assigned to `null`.</span></span>

<span data-ttu-id="4f314-153">メソッドを 3 つ定義します。これらのメソッドでは、文字列配列の各要素に対して <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4f314-153">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method for each element in a string array.</span></span> <span data-ttu-id="4f314-154">メソッドのオーバーロードを呼び出します。これにより、テストが失敗した場合に表示されるエラー メッセージを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4f314-154">You'll call a method overload that lets you specify an error message to be displayed in case of test failure.</span></span> <span data-ttu-id="4f314-155">このメッセージによって、エラーの原因となった文字列が識別されます。</span><span class="sxs-lookup"><span data-stu-id="4f314-155">The message identifies the string that caused the failure.</span></span>

<span data-ttu-id="4f314-156">テスト メソッドを作成するには</span><span class="sxs-lookup"><span data-stu-id="4f314-156">To create the test methods:</span></span>

1. <span data-ttu-id="4f314-157">*StringLibraryTest/UnitTest1.cs* を開き、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4f314-157">Open *StringLibraryTest/UnitTest1.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibraryTest/UnitTest1.cs":::

   <span data-ttu-id="4f314-158">`TestStartsWithUpper` メソッドの大文字のテストには、ギリシャ語の大文字のアルファ (U+0391) とキリル文字の大文字 EM (U+041C) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f314-158">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="4f314-159">`TestDoesNotStartWithUpper` メソッドの小文字のテストには、ギリシャ語の小文字のアルファ (U+03B1) とキリル文字の小文字 Ghe (U+0433) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f314-159">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="4f314-160">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="4f314-160">Save your changes.</span></span>

1. <span data-ttu-id="4f314-161">テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="4f314-161">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="4f314-162">次のターミナル出力は、すべてのテストが成功したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="4f314-162">The terminal output shows that all tests passed.</span></span>

   ```
   Starting test execution, please wait...

   A total of 1 test files matched the specified pattern.

   Test Run Successful.
   Total tests: 3
        Passed: 3
   Total time: 5.1116 Seconds
   ```

## <a name="handle-test-failures"></a><span data-ttu-id="4f314-163">テストの失敗の処理</span><span class="sxs-lookup"><span data-stu-id="4f314-163">Handle test failures</span></span>

<span data-ttu-id="4f314-164">テスト駆動開発 (TDD) を行っている場合、最初にテストを作成すると、1 回目のテスト実行は失敗します。</span><span class="sxs-lookup"><span data-stu-id="4f314-164">If you're doing test-driven development (TDD), you write tests first and they fail the first time you run them.</span></span> <span data-ttu-id="4f314-165">その後、テストを成功させるコードをアプリに追加します。</span><span class="sxs-lookup"><span data-stu-id="4f314-165">Then you add code to the app that makes the test succeed.</span></span> <span data-ttu-id="4f314-166">このチュートリアルでは、検証するアプリ コードを記述した後にテストを作成したため、テストが失敗することはありませんでした。</span><span class="sxs-lookup"><span data-stu-id="4f314-166">For this tutorial, you created the test after writing the app code that it validates, so you haven't seen the test fail.</span></span> <span data-ttu-id="4f314-167">テストの失敗が予想されるときにテストが失敗することを検証するには、テスト入力に無効な値を追加します。</span><span class="sxs-lookup"><span data-stu-id="4f314-167">To validate that a test fails when you expect it to fail, add an invalid value to the test input.</span></span>

1. <span data-ttu-id="4f314-168">`TestDoesNotStartWithUpper` メソッドの `words` 配列を変更し、文字列 "Error" を含めます。</span><span class="sxs-lookup"><span data-stu-id="4f314-168">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. <span data-ttu-id="4f314-169">テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="4f314-169">Run the tests:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj
   ```

   <span data-ttu-id="4f314-170">ターミナルの出力では、1 つのテストが失敗したことが示され、失敗したテストに関するエラー メッセージが表示されます。"Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="4f314-170">The terminal output shows that one test fails, and it provides an error message for the failed test: "Assert.IsFalse failed.</span></span> <span data-ttu-id="4f314-171">Expected for 'Error': false; actual:True" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f314-171">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="4f314-172">エラーのため、配列内の "Error" の後ろの文字列はテストされませんでした。</span><span class="sxs-lookup"><span data-stu-id="4f314-172">Because of the failure, no strings in the array after "Error" were tested.</span></span>

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

1. <span data-ttu-id="4f314-173">手順 1 で追加した文字列 "Error" を削除します。</span><span class="sxs-lookup"><span data-stu-id="4f314-173">Remove the string "Error" that you added in step 1.</span></span> <span data-ttu-id="4f314-174">テストを再実行すると、テストは成功します。</span><span class="sxs-lookup"><span data-stu-id="4f314-174">Rerun the test and the tests pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="4f314-175">ライブラリのリリース バージョンのテスト</span><span class="sxs-lookup"><span data-stu-id="4f314-175">Test the Release version of the library</span></span>

<span data-ttu-id="4f314-176">これで、ライブラリのデバッグ ビルドを実行したときにすべてのテストが成功したので、さらにライブラリのリリース ビルドに対してテストを行います。</span><span class="sxs-lookup"><span data-stu-id="4f314-176">Now that the tests have all passed when running the Debug build of the library, run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="4f314-177">コンパイラの最適化などのさまざまな要因により、デバッグ ビルドとリリース ビルドとでは動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f314-177">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

1. <span data-ttu-id="4f314-178">リリース ビルド構成を使用してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="4f314-178">Run the tests with the Release build configuration:</span></span>

   ```dotnetcli
   dotnet test StringLibraryTest/StringLibraryTest.csproj --configuration Release
   ```

   <span data-ttu-id="4f314-179">テストが成功します。</span><span class="sxs-lookup"><span data-stu-id="4f314-179">The tests pass.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4f314-180">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="4f314-180">Additional resources</span></span>

* [<span data-ttu-id="4f314-181">.NET Core と .NET Standard の単体テスト</span><span class="sxs-lookup"><span data-stu-id="4f314-181">Unit testing in .NET Core and .NET Standard</span></span>](../testing/index.md)

## <a name="next-steps"></a><span data-ttu-id="4f314-182">次の手順</span><span class="sxs-lookup"><span data-stu-id="4f314-182">Next steps</span></span>

<span data-ttu-id="4f314-183">このチュートリアルでは、クラス ライブラリの単体テストを行いました。</span><span class="sxs-lookup"><span data-stu-id="4f314-183">In this tutorial, you unit tested a class library.</span></span> <span data-ttu-id="4f314-184">ライブラリをパッケージとして [NuGet](https://nuget.org) に発行した場合、他のユーザーもそれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f314-184">You can make the library available to others by publishing it to [NuGet](https://nuget.org) as a package.</span></span> <span data-ttu-id="4f314-185">方法については、次の NuGet のチュートリアルに従ってください。</span><span class="sxs-lookup"><span data-stu-id="4f314-185">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f314-186">dotnet CLI を使用したパッケージの作成と公開</span><span class="sxs-lookup"><span data-stu-id="4f314-186">Create and publish a package using the dotnet CLI</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)

<span data-ttu-id="4f314-187">ライブラリを NuGet パッケージとして発行した場合、他のユーザーもそれをインストールして使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f314-187">If you publish a library as a NuGet package, others can install and use it.</span></span> <span data-ttu-id="4f314-188">方法については、次の NuGet のチュートリアルに従ってください。</span><span class="sxs-lookup"><span data-stu-id="4f314-188">To learn how, follow a NuGet tutorial:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f314-189">dotnet CLI を使用してパッケージをインストールし使用する</span><span class="sxs-lookup"><span data-stu-id="4f314-189">Install and use a package using the dotnet CLI</span></span>](/nuget/quickstart/install-and-use-a-package-using-the-dotnet-cli)

<span data-ttu-id="4f314-190">ライブラリはパッケージとして配布する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f314-190">A library doesn't have to be distributed as a package.</span></span> <span data-ttu-id="4f314-191">それが使用されるコンソール アプリにバンドルすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f314-191">It can be bundled with a console app that uses it.</span></span> <span data-ttu-id="4f314-192">コンソール アプリを発行する方法については、このシリーズの前のチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f314-192">To learn how to publish a console app, see the earlier tutorial in this series:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4f314-193">Visual Studio Code を使用して .NET Core コンソール アプリケーションを発行する</span><span class="sxs-lookup"><span data-stu-id="4f314-193">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
