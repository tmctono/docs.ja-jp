---
title: 選択的単体テストの実行
description: .NET Core において dotnet test コマンドでフィルター式を使用して、選択的単体テストを実行する方法。
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: 57428dad2de6c2507ca2cdc42e3df9e83a1edd69
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715459"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="957cf-103">選択的単体テストの実行</span><span class="sxs-lookup"><span data-stu-id="957cf-103">Running selective unit tests</span></span>

<span data-ttu-id="957cf-104">.NET Core で `dotnet test` コマンドを使用することで、フィルター式を使用して、選択的テストを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="957cf-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="957cf-105">この記事では、実行するテストをフィルター処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="957cf-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="957cf-106">次の例では、`dotnet test` を使用します。</span><span class="sxs-lookup"><span data-stu-id="957cf-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="957cf-107">`vstest.console.exe` を使用している場合は、`--filter` を `--testcasefilter:` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="957cf-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="957cf-108">MSTest</span><span class="sxs-lookup"><span data-stu-id="957cf-108">MSTest</span></span>

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

| <span data-ttu-id="957cf-109">正規表現</span><span class="sxs-lookup"><span data-stu-id="957cf-109">Expression</span></span> | <span data-ttu-id="957cf-110">結果</span><span class="sxs-lookup"><span data-stu-id="957cf-110">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="957cf-111">`FullyQualifiedName` に `Method` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-111">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="957cf-112">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="957cf-112">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="957cf-113">名前に `TestMethod1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-113">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="957cf-114">クラス `MSTestNamespace.UnitTest1` 内にあるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-114">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="957cf-115">**注:** `ClassName` 値には名前空間があるため、`ClassName=UnitTest1` は機能しません。</span><span class="sxs-lookup"><span data-stu-id="957cf-115">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="957cf-116">`MSTestNamespace.UnitTest1.TestMethod1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-116">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="957cf-117">`[TestCategory("CategoryA")]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-117">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="957cf-118">`[Priority(2)]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-118">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="957cf-119">**条件演算子| と &amp; の使用**</span><span class="sxs-lookup"><span data-stu-id="957cf-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="957cf-120">正規表現</span><span class="sxs-lookup"><span data-stu-id="957cf-120">Expression</span></span> | <span data-ttu-id="957cf-121">結果</span><span class="sxs-lookup"><span data-stu-id="957cf-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="957cf-122">`FullyQualifiedName` に `UnitTest1` がある、**または** `TestCategory` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-122">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="957cf-123">`FullyQualifiedName` に `UnitTest1` がある、**および** `TestCategory` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-123">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="957cf-124">`UnitTest1` を含む `FullyQualifiedName` **および** `TestCategory` が `CategoryA`、**または** `Priority` が 1 かのいずれかのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-124">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="957cf-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="957cf-125">xUnit</span></span>

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

| <span data-ttu-id="957cf-126">正規表現</span><span class="sxs-lookup"><span data-stu-id="957cf-126">Expression</span></span> | <span data-ttu-id="957cf-127">結果</span><span class="sxs-lookup"><span data-stu-id="957cf-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="957cf-128">`XUnitNamespace.TestClass1.Test1` という 1 つのテストのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="957cf-129">`XUnitNamespace.TestClass1.Test1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="957cf-130">表示名に `TestClass1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="957cf-131">コード例では、特性をキー `Category` や `Priority` で定義すると、フィルター処理に使用できます。</span><span class="sxs-lookup"><span data-stu-id="957cf-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="957cf-132">正規表現</span><span class="sxs-lookup"><span data-stu-id="957cf-132">Expression</span></span> | <span data-ttu-id="957cf-133">結果</span><span class="sxs-lookup"><span data-stu-id="957cf-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="957cf-134">`FullyQualifiedName` に `XUnit` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="957cf-135">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="957cf-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="957cf-136">`[Trait("Category", "CategoryA")]` があるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-136">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="957cf-137">**条件演算子| と &amp; の使用**</span><span class="sxs-lookup"><span data-stu-id="957cf-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="957cf-138">正規表現</span><span class="sxs-lookup"><span data-stu-id="957cf-138">Expression</span></span> | <span data-ttu-id="957cf-139">結果</span><span class="sxs-lookup"><span data-stu-id="957cf-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="957cf-140">`FullyQualifiedName` に `TestClass1` がある、**または** `Category` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="957cf-141">`FullyQualifiedName` に `TestClass1` がある、**および** `Category` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="957cf-142">`TestClass1` を含む `FullyQualifiedName` **および** `Category` が `CategoryA`、**または** `Priority` が 1 かのいずれかのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="957cf-143">NUnit</span><span class="sxs-lookup"><span data-stu-id="957cf-143">NUnit</span></span>

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

| <span data-ttu-id="957cf-144">正規表現</span><span class="sxs-lookup"><span data-stu-id="957cf-144">Expression</span></span> | <span data-ttu-id="957cf-145">結果</span><span class="sxs-lookup"><span data-stu-id="957cf-145">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="957cf-146">`FullyQualifiedName` に `Method` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-146">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="957cf-147">`vstest 15.1+` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="957cf-147">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="957cf-148">名前に `TestMethod1` が含まれるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-148">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="957cf-149">クラス `NUnitNamespace.UnitTest1` 内にあるテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-149">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="957cf-150">`NUnitNamespace.UnitTest1.TestMethod1` 以外のテストをすべて実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-150">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="957cf-151">`[Category("CategoryA")]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-151">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="957cf-152">`[Priority(2)]` の注釈が付けられているテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-152">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="957cf-153">**条件演算子| と &amp; の使用**</span><span class="sxs-lookup"><span data-stu-id="957cf-153">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="957cf-154">正規表現</span><span class="sxs-lookup"><span data-stu-id="957cf-154">Expression</span></span> | <span data-ttu-id="957cf-155">結果</span><span class="sxs-lookup"><span data-stu-id="957cf-155">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="957cf-156">`FullyQualifiedName` に `UnitTest1` がある、**または** `TestCategory` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-156">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="957cf-157">`FullyQualifiedName` に `UnitTest1` がある、**および** `TestCategory` が `CategoryA` のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-157">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="957cf-158">`UnitTest1` を含む `FullyQualifiedName` **および** `TestCategory` が `CategoryA`、**または** `Priority` が 1 かのいずれかのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="957cf-158">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
