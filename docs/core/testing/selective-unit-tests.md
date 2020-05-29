---
title: 選択的単体テストの実行
description: .NET Core において dotnet test コマンドでフィルター式を使用して、選択的単体テストを実行する方法。
author: smadala
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: 6a6bbb0687742d1e3288d64fb88f6825dc678e28
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702981"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="b4045-103">選択的単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="b4045-103">Run selective unit tests</span></span>

<span data-ttu-id="b4045-104">.NET Core で [`dotnet test`](../tools/dotnet-test.md) コマンドを使用することで、フィルター式を使用して、選択的テストを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b4045-104">With the [`dotnet test`](../tools/dotnet-test.md) command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="b4045-105">この記事では、実行するテストをフィルター処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b4045-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="b4045-106">次の例では、`dotnet test` を使用します。</span><span class="sxs-lookup"><span data-stu-id="b4045-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="b4045-107">`vstest.console.exe` を使用している場合は、`--filter` を `--testcasefilter:` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="b4045-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="b4045-108">文字のエスケープ</span><span class="sxs-lookup"><span data-stu-id="b4045-108">Character escaping</span></span>

<span data-ttu-id="b4045-109">`*nix` で感嘆符 `!` を含むフィルターを使用するときは、`!` が予約されているため、エスケープが必要になります。</span><span class="sxs-lookup"><span data-stu-id="b4045-109">Using filters that include exclamation mark `!` on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="b4045-110">たとえば、次のように名前空間に IntegrationTests が含まれている場合、このフィルターではすべてのテストがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="b4045-110">For example, this filter skips all tests if the namespace contains IntegrationTests:</span></span>

```dotnetcli
dotnet test --filter FullyQualifiedName\!~IntegrationTests
```

> [!IMPORTANT]
> <span data-ttu-id="b4045-111">感嘆符の前に円記号を付けると (`\!`)、それがエスケープされた文字であることを示します。</span><span class="sxs-lookup"><span data-stu-id="b4045-111">The backslash precedes the exclamation mark to indicate it is an escaped character `\!`.</span></span>

<span data-ttu-id="b4045-112">ジェネリック型パラメーターで `FullyQualifiedName` 値にコンマを含める場合は、`%2C` を指定してコンマをエスケープします。</span><span class="sxs-lookup"><span data-stu-id="b4045-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="b4045-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b4045-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

:::zone pivot="mstest"

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestMethod, Priority(1), TestCategory("CategoryA")]
        public void TestMethod1()
        {
        }

        [TestMethod, Priority(2)]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="b4045-114">正規表現</span><span class="sxs-lookup"><span data-stu-id="b4045-114">Expression</span></span> | <span data-ttu-id="b4045-115">結果</span><span class="sxs-lookup"><span data-stu-id="b4045-115">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="b4045-116"><xref:System.Reflection.Module.FullyQualifiedName> に `Method` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-116">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="b4045-117">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4045-117">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="b4045-118">名前に `TestMethod1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-118">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="b4045-119">クラス `MSTestNamespace.UnitTest1` 内にあるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-119">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="b4045-120">**注:** `ClassName` 値には名前空間があるため、`ClassName=UnitTest1` は機能しません。</span><span class="sxs-lookup"><span data-stu-id="b4045-120">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="b4045-121">`MSTestNamespace.UnitTest1.TestMethod1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-121">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="b4045-122">`[TestCategory("CategoryA")]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-122">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="b4045-123">`[Priority(2)]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-123">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="b4045-124">条件演算子 `|` と `&` の使用例:</span><span class="sxs-lookup"><span data-stu-id="b4045-124">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="b4045-125"><xref:System.Reflection.Module.FullyQualifiedName> に `UnitTest1` が含まれるか、**または**、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> が `"CategoryA"` であるテストを実行するには。</span><span class="sxs-lookup"><span data-stu-id="b4045-125">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> is `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="b4045-126"><xref:System.Reflection.Module.FullyQualifiedName> に `UnitTest1` が含まれ、**かつ**、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> が `"CategoryA"` であるテストを実行するには。</span><span class="sxs-lookup"><span data-stu-id="b4045-126">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="b4045-127"><xref:System.Reflection.Module.FullyQualifiedName> に `UnitTest1` が含まれ、**かつ**、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> が `"CategoryA"` であるか、**または**、<xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> の優先順位が `1` であるテストを実行するには。</span><span class="sxs-lookup"><span data-stu-id="b4045-127">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"` **or** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> with a priority of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="xunit"

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Fact, Trait("Priority", "1"), Trait("Category", "CategoryA")]
        public void Test1()
        {
        }

        [Fact, Trait("Priority", "2")]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="b4045-128">正規表現</span><span class="sxs-lookup"><span data-stu-id="b4045-128">Expression</span></span> | <span data-ttu-id="b4045-129">結果</span><span class="sxs-lookup"><span data-stu-id="b4045-129">Result</span></span> |
|--|--|
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="b4045-130">`XUnitNamespace.TestClass1.Test1` という 1 つのテストのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-130">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="b4045-131">`XUnitNamespace.TestClass1.Test1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-131">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="b4045-132">表示名に `TestClass1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-132">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="b4045-133">コード例では、特性をキー `"Category"` や `"Priority"` で定義すると、フィルター処理に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4045-133">In the code example, the defined traits with keys `"Category"` and `"Priority"` can be used for filtering.</span></span>

| <span data-ttu-id="b4045-134">正規表現</span><span class="sxs-lookup"><span data-stu-id="b4045-134">Expression</span></span> | <span data-ttu-id="b4045-135">結果</span><span class="sxs-lookup"><span data-stu-id="b4045-135">Result</span></span> |
|--|--|
| `dotnet test --filter XUnit` | <span data-ttu-id="b4045-136"><xref:System.Reflection.Module.FullyQualifiedName> に `XUnit` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-136">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `XUnit`.</span></span>  <span data-ttu-id="b4045-137">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4045-137">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="b4045-138">`[Trait("Category", "CategoryA")]` があるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-138">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="b4045-139">条件演算子 `|` と `&` の使用例:</span><span class="sxs-lookup"><span data-stu-id="b4045-139">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="b4045-140"><xref:System.Reflection.Module.FullyQualifiedName> に `TestClass1` が含まれるか、**または**、`Trait` のキーが `"Category"` で値が `"CategoryA"` であるテストを実行するには。</span><span class="sxs-lookup"><span data-stu-id="b4045-140">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1|Category=CategoryA"
```

<span data-ttu-id="b4045-141"><xref:System.Reflection.Module.FullyQualifiedName> に `TestClass1` が含まれ、**かつ**、`Trait` のキーが `"Category"` で値が `"CategoryA"` であるテストを実行するには。</span><span class="sxs-lookup"><span data-stu-id="b4045-141">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"
```

<span data-ttu-id="b4045-142"><xref:System.Reflection.Module.FullyQualifiedName> に `TestClass1` が含まれ、**かつ**、`Trait` のキーが `"Category"` で値が `"CategoryA"` であるか、**または**、`Trait` のキーが `"Priority"` で値が `1` であるテストを実行するには。</span><span class="sxs-lookup"><span data-stu-id="b4045-142">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `TestClass1` **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"` **or** have a `Trait` with a key of `"Priority"` and value of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="nunit"

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Test, Property("Priority", 1), Category("CategoryA")]
        public void TestMethod1()
        {
        }

        [Test, Property("Priority", 2)]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="b4045-143">正規表現</span><span class="sxs-lookup"><span data-stu-id="b4045-143">Expression</span></span> | <span data-ttu-id="b4045-144">結果</span><span class="sxs-lookup"><span data-stu-id="b4045-144">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="b4045-145"><xref:System.Reflection.Module.FullyQualifiedName> に `Method` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-145">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="b4045-146">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4045-146">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="b4045-147">名前に `TestMethod1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-147">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="b4045-148">クラス `NUnitNamespace.UnitTest1` 内にあるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-148">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="b4045-149">`NUnitNamespace.UnitTest1.TestMethod1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-149">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="b4045-150">`[Category("CategoryA")]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-150">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="b4045-151">`[Priority(2)]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4045-151">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="b4045-152">条件演算子 `|` と `&` の使用例:</span><span class="sxs-lookup"><span data-stu-id="b4045-152">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="b4045-153"><xref:System.Reflection.Module.FullyQualifiedName> に `UnitTest1` が含まれるか、**または**、`Category` が `"CategoryA"` であるテストを実行するには。</span><span class="sxs-lookup"><span data-stu-id="b4045-153">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="b4045-154"><xref:System.Reflection.Module.FullyQualifiedName> に `UnitTest1` が含まれ、**かつ**、`Category` が `"CategoryA"` であるテストを実行するには。</span><span class="sxs-lookup"><span data-stu-id="b4045-154">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="b4045-155"><xref:System.Reflection.Module.FullyQualifiedName> に `UnitTest1` が含まれ、**かつ**、`Category` が `"CategoryA"` であるか、**または**、`Property` の `"Priority"` が `1` であるテストを実行するには。</span><span class="sxs-lookup"><span data-stu-id="b4045-155">To run tests that have either a <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a `Category` of `"CategoryA"` **or** have a `Property` with a `"Priority"` of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

<span data-ttu-id="b4045-156">詳細については、[TestCase フィルター](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4045-156">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

:::zone-end

## <a name="see-also"></a><span data-ttu-id="b4045-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4045-157">See also</span></span>

- [<span data-ttu-id="b4045-158">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b4045-158">dotnet test</span></span>](../tools/dotnet-test.md)
- [<span data-ttu-id="b4045-159">dotnet test --filter</span><span class="sxs-lookup"><span data-stu-id="b4045-159">dotnet test --filter</span></span>](../tools/dotnet-test.md#filter-option-details)

## <a name="next-steps"></a><span data-ttu-id="b4045-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="b4045-160">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b4045-161">単体テストの順序を設定する</span><span class="sxs-lookup"><span data-stu-id="b4045-161">Order unit tests</span></span>](order-unit-tests.md)
