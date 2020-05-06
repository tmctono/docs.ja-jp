---
title: 選択的単体テストの実行
description: .NET Core において dotnet test コマンドでフィルター式を使用して、選択的単体テストを実行する方法。
author: smadala
ms.date: 04/29/2020
ms.openlocfilehash: 50642126f3b470180ddd303ed4a2d2d90bfa5b8f
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728180"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="f248d-103">選択的単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="f248d-103">Run selective unit tests</span></span>

<span data-ttu-id="f248d-104">.NET Core で `dotnet test` コマンドを使用することで、フィルター式を使用して、選択的テストを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f248d-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="f248d-105">この記事では、実行するテストをフィルター処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f248d-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="f248d-106">次の例では、`dotnet test` を使用します。</span><span class="sxs-lookup"><span data-stu-id="f248d-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="f248d-107">`vstest.console.exe` を使用している場合は、`--filter` を `--testcasefilter:` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f248d-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="f248d-108">文字のエスケープ</span><span class="sxs-lookup"><span data-stu-id="f248d-108">Character escaping</span></span>

<span data-ttu-id="f248d-109">`*nix` に感嘆符 (!) を含むフィルターを使用すると、`!` が予約されているために、エスケープが必要になります。</span><span class="sxs-lookup"><span data-stu-id="f248d-109">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="f248d-110">たとえば、名前空間に IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests` が含まれている場合、このフィルターではすべてのテストがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="f248d-110">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
<span data-ttu-id="f248d-111">感嘆符の前にある円記号に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f248d-111">Note the backslash that precedes the exclamation mark.</span></span>

<span data-ttu-id="f248d-112">ジェネリック型パラメーターで `FullyQualifiedName` 値にコンマを含める場合は、`%2C` を指定してコンマをエスケープします。</span><span class="sxs-lookup"><span data-stu-id="f248d-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="f248d-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f248d-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

## <a name="mstest"></a><span data-ttu-id="f248d-114">MSTest</span><span class="sxs-lookup"><span data-stu-id="f248d-114">MSTest</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="f248d-115">正規表現</span><span class="sxs-lookup"><span data-stu-id="f248d-115">Expression</span></span> | <span data-ttu-id="f248d-116">結果</span><span class="sxs-lookup"><span data-stu-id="f248d-116">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="f248d-117">`FullyQualifiedName` に `Method` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-117">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="f248d-118">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f248d-118">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="f248d-119">名前に `TestMethod1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-119">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="f248d-120">クラス `MSTestNamespace.UnitTest1` 内にあるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-120">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="f248d-121">**注:** `ClassName` 値には名前空間があるため、`ClassName=UnitTest1` は機能しません。</span><span class="sxs-lookup"><span data-stu-id="f248d-121">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="f248d-122">`MSTestNamespace.UnitTest1.TestMethod1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-122">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="f248d-123">`[TestCategory("CategoryA")]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-123">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="f248d-124">`[Priority(2)]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-124">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="f248d-125">**条件演算子| と &amp; の使用**</span><span class="sxs-lookup"><span data-stu-id="f248d-125">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f248d-126">正規表現</span><span class="sxs-lookup"><span data-stu-id="f248d-126">Expression</span></span> | <span data-ttu-id="f248d-127">結果</span><span class="sxs-lookup"><span data-stu-id="f248d-127">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="f248d-128">`FullyQualifiedName` に `UnitTest1` が含まれる、**または** `TestCategory` が `CategoryA` であるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-128">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="f248d-129">`FullyQualifiedName` に `UnitTest1` が含まれ、**かつ** `TestCategory` が `CategoryA` であるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-129">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="f248d-130">`FullyQualifiedName` に `UnitTest1` が含まれ、**かつ** `TestCategory` が `CategoryA` であるか、**または**、`Priority` が 1 であるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-130">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="f248d-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="f248d-131">xUnit</span></span>

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="f248d-132">正規表現</span><span class="sxs-lookup"><span data-stu-id="f248d-132">Expression</span></span> | <span data-ttu-id="f248d-133">結果</span><span class="sxs-lookup"><span data-stu-id="f248d-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f248d-134">`XUnitNamespace.TestClass1.Test1` という 1 つのテストのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-134">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f248d-135">`XUnitNamespace.TestClass1.Test1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-135">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="f248d-136">表示名に `TestClass1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-136">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="f248d-137">コード例では、特性をキー `Category` や `Priority` で定義すると、フィルター処理に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f248d-137">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="f248d-138">正規表現</span><span class="sxs-lookup"><span data-stu-id="f248d-138">Expression</span></span> | <span data-ttu-id="f248d-139">結果</span><span class="sxs-lookup"><span data-stu-id="f248d-139">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="f248d-140">`FullyQualifiedName` に `XUnit` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-140">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="f248d-141">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f248d-141">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="f248d-142">`[Trait("Category", "CategoryA")]` があるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-142">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="f248d-143">**条件演算子| と &amp; の使用**</span><span class="sxs-lookup"><span data-stu-id="f248d-143">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f248d-144">正規表現</span><span class="sxs-lookup"><span data-stu-id="f248d-144">Expression</span></span> | <span data-ttu-id="f248d-145">結果</span><span class="sxs-lookup"><span data-stu-id="f248d-145">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="f248d-146">`FullyQualifiedName` に `TestClass1` が含まれる、**または** `Category` が `CategoryA` であるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-146">Runs tests that have `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="f248d-147">`FullyQualifiedName` に `TestClass1` が含まれ、**かつ** `Category` が `CategoryA` であるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-147">Runs tests that have `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="f248d-148">`FullyQualifiedName` に `TestClass1` が含まれ、**かつ** `Category` が `CategoryA` であるか、**または**、`Priority` が 1 であるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-148">Runs tests that have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="f248d-149">NUnit</span><span class="sxs-lookup"><span data-stu-id="f248d-149">NUnit</span></span>

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="f248d-150">正規表現</span><span class="sxs-lookup"><span data-stu-id="f248d-150">Expression</span></span> | <span data-ttu-id="f248d-151">結果</span><span class="sxs-lookup"><span data-stu-id="f248d-151">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="f248d-152">`FullyQualifiedName` に `Method` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-152">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="f248d-153">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f248d-153">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="f248d-154">名前に `TestMethod1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-154">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="f248d-155">クラス `NUnitNamespace.UnitTest1` 内にあるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-155">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="f248d-156">`NUnitNamespace.UnitTest1.TestMethod1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-156">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="f248d-157">`[Category("CategoryA")]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-157">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="f248d-158">`[Priority(2)]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-158">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="f248d-159">**条件演算子| と &amp; の使用**</span><span class="sxs-lookup"><span data-stu-id="f248d-159">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f248d-160">正規表現</span><span class="sxs-lookup"><span data-stu-id="f248d-160">Expression</span></span> | <span data-ttu-id="f248d-161">結果</span><span class="sxs-lookup"><span data-stu-id="f248d-161">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="f248d-162">`FullyQualifiedName` に `UnitTest1` が含まれる、**または** `TestCategory` が `CategoryA` であるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-162">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="f248d-163">`FullyQualifiedName` に `UnitTest1` が含まれ、**かつ** `TestCategory` が `CategoryA` であるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-163">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="f248d-164">`FullyQualifiedName` に `UnitTest1` が含まれ、**かつ** `TestCategory` が `CategoryA` であるか、**または**、`Priority` が 1 であるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="f248d-164">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

<span data-ttu-id="f248d-165">詳細については、[TestCase フィルター](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f248d-165">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>
