---
title: dotnet テストと xUnit を使用した .NET Core での単体テスト Visual Basic
description: dotnet テストおよび xUnit を使用した Visual Basic ソリューションのサンプルを段階的に構築していく対話型エクスペリエンスを通じて、.NET Core の単体テストの概念について説明します。
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.custom: seodec18
ms.openlocfilehash: 63898f23f7c70a96409c6de9029fb0c067223016
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373880"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a><span data-ttu-id="76320-103">dotnet テストと xUnit を使用した Visual Basic .NET Core ライブラリでの単体テスト</span><span class="sxs-lookup"><span data-stu-id="76320-103">Unit testing Visual Basic .NET Core libraries using dotnet test and xUnit</span></span>

<span data-ttu-id="76320-104">このチュートリアルでは、単体テストの概念について学習するためにサンプル ソリューションを段階的に構築する対話型のエクスペリエンスを示します。</span><span class="sxs-lookup"><span data-stu-id="76320-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="76320-105">構築済みのソリューションを使用してチュートリアルに従う場合は、開始する前に[サンプル コードを参照またはダウンロード](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-dotnet-test)してください。</span><span class="sxs-lookup"><span data-stu-id="76320-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-dotnet-test) before you begin.</span></span> <span data-ttu-id="76320-106">ダウンロード方法については、「[サンプルおよびチュートリアル](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76320-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="76320-107">ソース プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="76320-107">Creating the source project</span></span>

<span data-ttu-id="76320-108">シェル ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="76320-108">Open a shell window.</span></span> <span data-ttu-id="76320-109">ソリューションを保存するための *unit-testing-vb-using-dotnet-test* というディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="76320-109">Create a directory called *unit-testing-vb-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="76320-110">この新しいディレクトリ内で [`dotnet new sln`](../tools/dotnet-new.md) を実行して、ソリューションを新たに作成します。</span><span class="sxs-lookup"><span data-stu-id="76320-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="76320-111">こうすることで、クラス ライブラリと単体テスト プロジェクトの両方を管理しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="76320-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="76320-112">ソリューションのディレクトリ内で、*PrimeService* ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="76320-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="76320-113">現時点のディレクトリとファイルの構造は次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="76320-113">You have the following directory and file structure thus far:</span></span>

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="76320-114">*PrimeService* を現在のディレクトリにし、[`dotnet new classlib -lang VB`](../tools/dotnet-new.md) を実行してソース プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="76320-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="76320-115">*Class1.VB* の名前を *PrimeService.VB* に変更します。</span><span class="sxs-lookup"><span data-stu-id="76320-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="76320-116">`PrimeService` クラスのエラーが発生する実装を作成します。</span><span class="sxs-lookup"><span data-stu-id="76320-116">You create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="76320-117">*unit-testing-vb-using-dotnet-test* ディレクトリに戻ります。</span><span class="sxs-lookup"><span data-stu-id="76320-117">Change the directory back to the *unit-testing-vb-using-dotnet-test* directory.</span></span> <span data-ttu-id="76320-118">[`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) を実行して、クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="76320-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="76320-119">テスト プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="76320-119">Creating the test project</span></span>

<span data-ttu-id="76320-120">次に、*PrimeService.Tests* ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="76320-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="76320-121">次の一覧はディレクトリ構造を示したものです。</span><span class="sxs-lookup"><span data-stu-id="76320-121">The following outline shows the directory structure:</span></span>

```console
/unit-testing-vb-using-dotnet-test
    unit-testing-vb-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="76320-122">*PrimeService.Tests* ディレクトリを現在のディレクトリにし、[`dotnet new xunit -lang VB`](../tools/dotnet-new.md) を使用して新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="76320-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="76320-123">このコマンドによって、テスト ライブラリとして xUnit を使用するテスト プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="76320-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="76320-124">生成されたテンプレートで、*PrimeServiceTests.vbproj* のテスト ランナーが構成されます。</span><span class="sxs-lookup"><span data-stu-id="76320-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="76320-125">テスト プロジェクトには、単体テストを作成して実行するための、他のパッケージが必要です。</span><span class="sxs-lookup"><span data-stu-id="76320-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="76320-126">前の手順の `dotnet new` によって、xUnit と xUnit ランナーが追加されています。</span><span class="sxs-lookup"><span data-stu-id="76320-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="76320-127">ここで、プロジェクトに別の依存関係として `PrimeService` クラス ライブラリを追加します。</span><span class="sxs-lookup"><span data-stu-id="76320-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="76320-128">次の [`dotnet add reference`](../tools/dotnet-add-reference.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="76320-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="76320-129">全体のファイルは GitHub の[サンプル リポジトリ](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="76320-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="76320-130">フォルダーの最終的なレイアウトは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="76320-130">You have the following final folder layout:</span></span>

```console
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="76320-131">*unit-testing-vb-using-dotnet-test* ディレクトリで [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) を実行します。</span><span class="sxs-lookup"><span data-stu-id="76320-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="76320-132">最初のテストの作成</span><span class="sxs-lookup"><span data-stu-id="76320-132">Creating the first test</span></span>

<span data-ttu-id="76320-133">失敗するテストを 1 つ作成してそれを合格させる、というプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="76320-133">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="76320-134">*PrimeService.Tests* ディレクトリから *UnitTest1.vb* を削除し、*PrimeService_IsPrimeShould.VB* という名前の新しい Visual Basic ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="76320-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="76320-135">次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="76320-135">Add the following code:</span></span>

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Fact>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="76320-136">`<Fact>` 属性は、テスト ランナーによって実行されるテスト メソッドを表します。</span><span class="sxs-lookup"><span data-stu-id="76320-136">The `<Fact>` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="76320-137">*unit-testing-using-dotnet-test* で [`dotnet test`](../tools/dotnet-test.md) を実行してテストとクラス ライブラリをビルドし、それからテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="76320-137">From the *unit-testing-using-dotnet-test*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="76320-138">xUnit テスト ランナーには、テストを実行するためのプログラムのエントリ ポイントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="76320-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="76320-139">`dotnet test` を実行すると、作成した単体テスト プロジェクトを使用してテスト ランナーが開始されます。</span><span class="sxs-lookup"><span data-stu-id="76320-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="76320-140">テストが失敗します。</span><span class="sxs-lookup"><span data-stu-id="76320-140">Your test fails.</span></span> <span data-ttu-id="76320-141">実装はまだ作成していません。</span><span class="sxs-lookup"><span data-stu-id="76320-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="76320-142">最も単純な動作のコードを `PrimeService` クラスに記述して、このテストが成功するようにします。</span><span class="sxs-lookup"><span data-stu-id="76320-142">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

<span data-ttu-id="76320-143">*unit-testing-vb-using-dotnet-test* ディレクトリで、もう一度 `dotnet test` を実行します。</span><span class="sxs-lookup"><span data-stu-id="76320-143">In the *unit-testing-vb-using-dotnet-test* directory, run `dotnet test` again.</span></span> <span data-ttu-id="76320-144">`dotnet test` コマンドは `PrimeService` プロジェクトのビルドを実行してから、`PrimeService.Tests` プロジェクトのビルドを実行します。</span><span class="sxs-lookup"><span data-stu-id="76320-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="76320-145">両方のプロジェクトをビルドすると、この単一テストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="76320-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="76320-146">成功します。</span><span class="sxs-lookup"><span data-stu-id="76320-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="76320-147">他の機能の追加</span><span class="sxs-lookup"><span data-stu-id="76320-147">Adding more features</span></span>

<span data-ttu-id="76320-148">テストが成功したので、他のテストも記述してみましょう。</span><span class="sxs-lookup"><span data-stu-id="76320-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="76320-149">素数に関する、いくつかの単純なケースが他にもあります(0、-1)。</span><span class="sxs-lookup"><span data-stu-id="76320-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="76320-150">`<Fact>` 属性を使用すると、これらの例を新しいテストとして追加できますが、すぐに煩雑になります。</span><span class="sxs-lookup"><span data-stu-id="76320-150">You could add those cases as new tests with the `<Fact>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="76320-151">一連の類似のテストを記述できるようになる、他の xUnit 属性があります。</span><span class="sxs-lookup"><span data-stu-id="76320-151">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="76320-152">`<Theory>` 属性は同じコードを実行するものの、異なる入力引数が含まれる一連のテストを表します。</span><span class="sxs-lookup"><span data-stu-id="76320-152">A `<Theory>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="76320-153">`<InlineData>` 属性を使用して、そのような入力の値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="76320-153">You can use the `<InlineData>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="76320-154">新しいテストを作成するのではなく、この 2 つの属性を適用することで 1 つの理論を作成できます。</span><span class="sxs-lookup"><span data-stu-id="76320-154">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="76320-155">その理論とは、複数の 2 未満の値を調べて、もっとも小さい素数を特定するという手法です。</span><span class="sxs-lookup"><span data-stu-id="76320-155">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="76320-156">`dotnet test` を実行して、これらの 2 つのテストが失敗したとします。</span><span class="sxs-lookup"><span data-stu-id="76320-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="76320-157">すべてのテストを成功させるために、メソッドの先頭にある `if` 句を変更します。</span><span class="sxs-lookup"><span data-stu-id="76320-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="76320-158">他のテスト、理論、コードをメイン ライブラリに追加して、反復を続けます。</span><span class="sxs-lookup"><span data-stu-id="76320-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="76320-159">[テストの最終版](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb)ができ、[ライブラリの完全な実装](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb)が完了しました。</span><span class="sxs-lookup"><span data-stu-id="76320-159">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-dotnet-test/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="76320-160">これで、小さなライブラリとそのライブラリの単体テストのセットが構築されました。</span><span class="sxs-lookup"><span data-stu-id="76320-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="76320-161">ソリューションを構築したことで、新しいパッケージとテストの追加が通常のワークフローに組み込まれました。</span><span class="sxs-lookup"><span data-stu-id="76320-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="76320-162">アプリケーションの目標を達成することに時間と労力の多くを割き、集中して取り組みました。</span><span class="sxs-lookup"><span data-stu-id="76320-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
