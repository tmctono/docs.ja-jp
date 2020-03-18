---
title: 選択的単体テストの実行
description: .NET Core において dotnet test コマンドでフィルター式を使用して、選択的単体テストを実行する方法。
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: b9156300587215e68c01c609e298dbc1a2c53d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543509"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="e6db6-103">選択的単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="e6db6-103">Running selective unit tests</span></span>

<span data-ttu-id="e6db6-104">.NET Core で `dotnet test` コマンドを使用することで、フィルター式を使用して、選択的テストを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e6db6-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="e6db6-105">この記事では、実行するテストをフィルター処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="e6db6-106">次の例では、`dotnet test` を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="e6db6-107">`vstest.console.exe` を使用している場合は、`--filter` を `--testcasefilter:` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e6db6-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

> [!NOTE]
> <span data-ttu-id="e6db6-108">`*nix` に感嘆符 (!) を含むフィルターを使用すると、`!` が予約されているために、エスケープが必要になります。</span><span class="sxs-lookup"><span data-stu-id="e6db6-108">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="e6db6-109">たとえば、名前空間に IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests` が含まれている場合、このフィルターではすべてのテストがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="e6db6-109">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
> <span data-ttu-id="e6db6-110">感嘆符の前にある円記号に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e6db6-110">Note the backslash that precedes the exclamation mark.</span></span>

## <a name="mstest"></a><span data-ttu-id="e6db6-111">MSTest</span><span class="sxs-lookup"><span data-stu-id="e6db6-111">MSTest</span></span>

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

| <span data-ttu-id="e6db6-112">正規表現</span><span class="sxs-lookup"><span data-stu-id="e6db6-112">Expression</span></span> | <span data-ttu-id="e6db6-113">結果</span><span class="sxs-lookup"><span data-stu-id="e6db6-113">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="e6db6-114">`FullyQualifiedName` に `Method` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-114">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="e6db6-115">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6db6-115">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="e6db6-116">名前に `TestMethod1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-116">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="e6db6-117">クラス `MSTestNamespace.UnitTest1` 内にあるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-117">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="e6db6-118">**注:** `ClassName` 値には名前空間があるため、`ClassName=UnitTest1` は機能しません。</span><span class="sxs-lookup"><span data-stu-id="e6db6-118">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="e6db6-119">`MSTestNamespace.UnitTest1.TestMethod1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-119">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="e6db6-120">`[TestCategory("CategoryA")]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-120">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="e6db6-121">`[Priority(2)]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-121">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="e6db6-122">**条件演算子| と &amp; の使用**</span><span class="sxs-lookup"><span data-stu-id="e6db6-122">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="e6db6-123">正規表現</span><span class="sxs-lookup"><span data-stu-id="e6db6-123">Expression</span></span> | <span data-ttu-id="e6db6-124">結果</span><span class="sxs-lookup"><span data-stu-id="e6db6-124">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="e6db6-125">`UnitTest1` に `FullyQualifiedName` がある、**または** `TestCategory` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-125">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="e6db6-126">`UnitTest1` に `FullyQualifiedName` がある、**および** `TestCategory` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-126">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="e6db6-127">`FullyQualifiedName` を含む `UnitTest1` **および** `TestCategory` が `CategoryA`、**または** `Priority` が 1 かのいずれかのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-127">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="e6db6-128">xUnit</span><span class="sxs-lookup"><span data-stu-id="e6db6-128">xUnit</span></span>

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

| <span data-ttu-id="e6db6-129">正規表現</span><span class="sxs-lookup"><span data-stu-id="e6db6-129">Expression</span></span> | <span data-ttu-id="e6db6-130">結果</span><span class="sxs-lookup"><span data-stu-id="e6db6-130">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="e6db6-131">`XUnitNamespace.TestClass1.Test1` という 1 つのテストのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-131">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="e6db6-132">`XUnitNamespace.TestClass1.Test1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-132">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="e6db6-133">表示名に `TestClass1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-133">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="e6db6-134">コード例では、特性をキー `Category` や `Priority` で定義すると、フィルター処理に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6db6-134">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="e6db6-135">正規表現</span><span class="sxs-lookup"><span data-stu-id="e6db6-135">Expression</span></span> | <span data-ttu-id="e6db6-136">結果</span><span class="sxs-lookup"><span data-stu-id="e6db6-136">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="e6db6-137">`FullyQualifiedName` に `XUnit` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-137">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="e6db6-138">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6db6-138">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="e6db6-139">`[Trait("Category", "CategoryA")]` があるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-139">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="e6db6-140">**条件演算子| と &amp; の使用**</span><span class="sxs-lookup"><span data-stu-id="e6db6-140">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="e6db6-141">正規表現</span><span class="sxs-lookup"><span data-stu-id="e6db6-141">Expression</span></span> | <span data-ttu-id="e6db6-142">結果</span><span class="sxs-lookup"><span data-stu-id="e6db6-142">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="e6db6-143">`TestClass1` に `FullyQualifiedName` がある、**または** `Category` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-143">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="e6db6-144">`TestClass1` に `FullyQualifiedName` がある、**および** `Category` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-144">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="e6db6-145">`FullyQualifiedName` を含む `TestClass1` **および** `Category` が `CategoryA`、**または** `Priority` が 1 かのいずれかのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-145">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="e6db6-146">NUnit</span><span class="sxs-lookup"><span data-stu-id="e6db6-146">NUnit</span></span>

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

| <span data-ttu-id="e6db6-147">正規表現</span><span class="sxs-lookup"><span data-stu-id="e6db6-147">Expression</span></span> | <span data-ttu-id="e6db6-148">結果</span><span class="sxs-lookup"><span data-stu-id="e6db6-148">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="e6db6-149">`FullyQualifiedName` に `Method` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-149">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="e6db6-150">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6db6-150">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="e6db6-151">名前に `TestMethod1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-151">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="e6db6-152">クラス `NUnitNamespace.UnitTest1` 内にあるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-152">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="e6db6-153">`NUnitNamespace.UnitTest1.TestMethod1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-153">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="e6db6-154">`[Category("CategoryA")]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-154">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="e6db6-155">`[Priority(2)]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-155">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="e6db6-156">**条件演算子| と &amp; の使用**</span><span class="sxs-lookup"><span data-stu-id="e6db6-156">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="e6db6-157">正規表現</span><span class="sxs-lookup"><span data-stu-id="e6db6-157">Expression</span></span> | <span data-ttu-id="e6db6-158">結果</span><span class="sxs-lookup"><span data-stu-id="e6db6-158">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="e6db6-159">`UnitTest1` に `FullyQualifiedName` がある、**または** `TestCategory` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-159">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="e6db6-160">`UnitTest1` に `FullyQualifiedName` がある、**および** `TestCategory` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-160">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="e6db6-161">`FullyQualifiedName` を含む `UnitTest1` **および** `TestCategory` が `CategoryA`、**または** `Priority` が 1 かのいずれかのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6db6-161">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
