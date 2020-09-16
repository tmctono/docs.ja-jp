---
title: MEF (Managed Extensibility Framework)
description: アプリケーション開発者が .NET 4 以降で拡張機能を検出し、構成なしで使用できるようにする Managed Extensibility Framework (MEF) について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Managed Extensibility Framework, overview
- MEF, overview
ms.assetid: 6c61b4ec-c6df-4651-80f1-4854f8b14dde
ms.openlocfilehash: b743a26dd401e7015c588be2a197551aa891a687
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555576"
---
# <a name="managed-extensibility-framework-mef"></a><span data-ttu-id="c27c8-103">MEF (Managed Extensibility Framework)</span><span class="sxs-lookup"><span data-stu-id="c27c8-103">Managed Extensibility Framework (MEF)</span></span>

<span data-ttu-id="c27c8-104">ここでは、.NET Framework 4 で導入された Managed Extensibility Framework の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-104">This topic provides an overview of the Managed Extensibility Framework that was introduced in the .NET Framework 4.</span></span>

## <a name="what-is-mef"></a><span data-ttu-id="c27c8-105">MEF とは</span><span class="sxs-lookup"><span data-stu-id="c27c8-105">What is MEF?</span></span>

<span data-ttu-id="c27c8-106">Managed Extensibility Framework (MEF) は、軽量で拡張可能なアプリケーションを作成するためのライブラリです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-106">The Managed Extensibility Framework or MEF is a library for creating lightweight, and extensible applications.</span></span> <span data-ttu-id="c27c8-107">これにより、アプリケーション開発者は、拡張機能を見つけたら、それをそのまま使用できます。構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-107">It allows application developers to discover and use extensions with no configuration required.</span></span> <span data-ttu-id="c27c8-108">拡張機能の開発者は、コードを簡単にカプセル化できるため、ハードコーディングによる脆弱な依存関係を回避できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-108">It also lets extension developers easily encapsulate code and avoid fragile hard dependencies.</span></span> <span data-ttu-id="c27c8-109">MEF により、アプリケーション内だけでなく、アプリケーション間でも拡張機能を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-109">MEF not only allows extensions to be reused within applications, but across applications as well.</span></span>

## <a name="the-problem-of-extensibility"></a><span data-ttu-id="c27c8-110">機能拡張の問題</span><span class="sxs-lookup"><span data-stu-id="c27c8-110">The problem of extensibility</span></span>

<span data-ttu-id="c27c8-111">機能拡張のサポートを提供する必要のある大規模アプリケーションの設計担当者である場合を想像してください。</span><span class="sxs-lookup"><span data-stu-id="c27c8-111">Imagine that you are the architect of a large application that must provide support for extensibility.</span></span> <span data-ttu-id="c27c8-112">アプリケーションには数多くの小規模コンポーネントを含める必要がある可能性があり、アプリケーションはこれらを作成して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-112">Your application has to include a potentially large number of smaller components, and is responsible for creating and running them.</span></span>

<span data-ttu-id="c27c8-113">このような問題を解決する最も簡単な方法は、アプリケーションにコンポーネントをソース コードとして組み込み、これらのコードをコードから直接呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-113">The simplest approach to the problem is to include the components as source code in your application, and call them directly from your code.</span></span> <span data-ttu-id="c27c8-114">この方法には、数多くの明らかな欠点があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-114">This has a number of obvious drawbacks.</span></span> <span data-ttu-id="c27c8-115">最も重要な点は、ソース コードを変更することなく新しいコンポーネントを追加できないという点です。これは、Web アプリケーションなどでは許容されますが、クライアント アプリケーションでは許容されません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-115">Most importantly, you cannot add new components without modifying the source code, a restriction that might be acceptable in, for example, a Web application, but is unworkable in a client application.</span></span> <span data-ttu-id="c27c8-116">同様に重要な問題点として、開発元がサードパーティであるためにコンポーネントのソース コードにアクセスできないことがあります。また、同じ理由から、サードパーティ側からの (自分が開発したコンポーネントのソース コードへの) アクセスを許可することもできません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-116">Equally problematic, you may not have access to the source code for the components, because they might be developed by third parties, and for the same reason you cannot allow them to access yours.</span></span>

<span data-ttu-id="c27c8-117">より高度な方法として、拡張ポイントまたはインターフェイスを提供して、アプリケーションとそのコンポーネントを切り離すことを許可する方法があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-117">A slightly more sophisticated approach would be to provide an extension point or interface, to permit decoupling between the application and its components.</span></span> <span data-ttu-id="c27c8-118">このモデルでは、必要に応じて、コンポーネントによって実装可能なインターフェイスと、そのインターフェイスがアプリケーションと対話するための API を提供できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-118">Under this model, you might provide an interface that a component can implement, and an API to enable it to interact with your application.</span></span> <span data-ttu-id="c27c8-119">これにより、ソース コードへのアクセスが必要になるという問題は解決されますが、この方法そのものにまだ問題があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-119">This solves the problem of requiring source code access, but it still has its own difficulties.</span></span>

<span data-ttu-id="c27c8-120">アプリケーションには独自にコンポーネントを検出する機能がないため、アプリケーションに対して使用可能なコンポーネントと読み込む必要のあるコンポーネントを明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-120">Because the application lacks any capacity for discovering components on its own, it must still be explicitly told which components are available and should be loaded.</span></span> <span data-ttu-id="c27c8-121">これは、通常、構成ファイルに使用可能なコンポーネントを明示的に登録することで指定します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-121">This is typically accomplished by explicitly registering the available components in a configuration file.</span></span> <span data-ttu-id="c27c8-122">これは、登録されたコンポーネントが正しいことが想定されることにより、特に開発者ではなくエンド ユーザーが更新を行う場合は、保守の問題が生じることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-122">This means that assuring that the components are correct becomes a maintenance issue, particularly if it is the end user and not the developer who is expected to do the updating.</span></span>

<span data-ttu-id="c27c8-123">さらに、アプリケーション自体の厳密に定義されたチャネルを介する場合を除き、コンポーネントは相互に通信することができません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-123">In addition, components are incapable of communicating with one another, except through the rigidly defined channels of the application itself.</span></span> <span data-ttu-id="c27c8-124">アプリケーションの設計担当者が特定の通信の必要性が生じる状況を想定しなかった場合、通常、通信は不可能です。</span><span class="sxs-lookup"><span data-stu-id="c27c8-124">If the application architect has not anticipated the need for a particular communication, it is usually impossible.</span></span>

<span data-ttu-id="c27c8-125">最後に、コンポーネントの開発者は、どのアセンブリが実装するインターフェイスを含んでいるかに対するハードコーディングによる依存関係を許容する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-125">Finally, the component developers must accept a hard dependency on what assembly contains the interface they implement.</span></span> <span data-ttu-id="c27c8-126">これにより、1 つのコンポーネントを複数のアプリケーションで使用することが困難となり、コンポーネントのテスト フレームワークを作成するときに問題が生じる可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-126">This makes it difficult for a component to be used in more than one application, and can also create problems when you create a test framework for components.</span></span>

## <a name="what-mef-provides"></a><span data-ttu-id="c27c8-127">MEF が提供する機能</span><span class="sxs-lookup"><span data-stu-id="c27c8-127">What MEF provides</span></span>

<span data-ttu-id="c27c8-128">使用可能なコンポーネントを明示的に登録する代わりに、MEF では、そのようなコンポーネントを "*合成*" によって暗黙的に検出できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-128">Instead of this explicit registration of available components, MEF provides a way to discover them implicitly, via *composition*.</span></span> <span data-ttu-id="c27c8-129">MEF コンポーネント ("*パート*") は、その依存関係 ("*インポート*") とそれが使用可能にする機能 ("*エクスポート*) の両方を宣言的に指定します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-129">A MEF component, called a *part*, declaratively specifies both its dependencies (known as *imports*) and what capabilities (known as *exports*) it makes available.</span></span> <span data-ttu-id="c27c8-130">パートが作成されると、MEF 合成エンジンは、他のパートから使用可能なパートでそのインポートを満たします。</span><span class="sxs-lookup"><span data-stu-id="c27c8-130">When a part is created, the MEF composition engine satisfies its imports with what is available from other parts.</span></span>

<span data-ttu-id="c27c8-131">この方法により、前のセクションで説明した問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-131">This approach solves the problems discussed in the previous section.</span></span> <span data-ttu-id="c27c8-132">MEF パートは、その機能を宣言的に指定するため、実行時に検出できます。これは、アプリケーションがハードコーディングされた参照または脆弱な構成ファイルを使用せずにパートを使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-132">Because MEF parts declaratively specify their capabilities, they are discoverable at runtime, which means an application can make use of parts without either hard-coded references or fragile configuration files.</span></span> <span data-ttu-id="c27c8-133">MEF を使用すると、アプリケーションは、メタデータを使用してパートを検出し、検証することができます。これらのパートをインスタンス化したり、そのアセンブリを読み込んだりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-133">MEF allows applications to discover and examine parts by their metadata, without instantiating them or even loading their assemblies.</span></span> <span data-ttu-id="c27c8-134">結果として、拡張機能がいつどのように読み込まれる必要があるかを慎重に指定する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-134">As a result, there is no need to carefully specify when and how extensions should be loaded.</span></span>

<span data-ttu-id="c27c8-135">パートは、それが提供するエクスポートに加えて、他のパートで満たされるインポートを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-135">In addition to its provided exports, a part can specify its imports, which will be filled by other parts.</span></span> <span data-ttu-id="c27c8-136">これにより、パート間の通信が可能になるだけでなく、簡単になり、コードのファクタリングが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-136">This makes communication among parts not only possible, but easy, and allows for good factoring of code.</span></span> <span data-ttu-id="c27c8-137">たとえば、多くのコンポーネントに共通のサービスを個々のパートにファクタリングして、簡単に変更したり置換したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-137">For example, services common to many components can be factored into a separate part and easily modified or replaced.</span></span>

<span data-ttu-id="c27c8-138">MEF モデルでは、特定のアプリケーション アセンブリでハードコーディングによる依存関係を指定する必要がないため、アプリケーション間で拡張機能を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-138">Because the MEF model requires no hard dependency on a particular application assembly, it allows extensions to be reused from application to application.</span></span> <span data-ttu-id="c27c8-139">これによってテスト ハーネスの開発も容易になり、アプリケーションに依存せずに拡張コンポーネントをテストできます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-139">This also makes it easy to develop a test harness, independent of the application, to test extension components.</span></span>

<span data-ttu-id="c27c8-140">MEF を使用して記述された拡張アプリケーションは、拡張コンポーネントで満たすことのできるインポートを宣言できます。また、拡張機能に対してアプリケーション サービスを公開するためにエクスポートを宣言できる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-140">An extensible application written by using MEF declares an import that can be filled by extension components, and may also declare exports in order to expose application services to extensions.</span></span> <span data-ttu-id="c27c8-141">各拡張コンポーネントは、エクスポートを宣言するだけではなく、インポートを宣言することもあります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-141">Each extension component declares an export, and may also declare imports.</span></span> <span data-ttu-id="c27c8-142">こうすると、拡張コンポーネント自体が自動的に拡張可能になります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-142">In this way, extension components themselves are automatically extensible.</span></span>

## <a name="where-mef-is-available"></a><span data-ttu-id="c27c8-143">MEF を使用できる場所</span><span class="sxs-lookup"><span data-stu-id="c27c8-143">Where MEF is available</span></span>

<span data-ttu-id="c27c8-144">MEF は、.NET Framework 4 の不可欠な構成要素であり、.NET Framework が使用されている環境であればどのような環境でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-144">MEF is an integral part of the .NET Framework 4, and is available wherever the .NET Framework is used.</span></span> <span data-ttu-id="c27c8-145">MEF は、Windows フォームや WPF などのテクノロジを使用するクライアント アプリケーション、または ASP.NET を使用するサーバー アプリケーションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-145">You can use MEF in your client applications, whether they use Windows Forms, WPF, or any other technology, or in server applications that use ASP.NET.</span></span>

## <a name="mef-and-maf"></a><span data-ttu-id="c27c8-146">MEF と MAF</span><span class="sxs-lookup"><span data-stu-id="c27c8-146">MEF and MAF</span></span>

<span data-ttu-id="c27c8-147">アプリケーションが拡張機能を特定および管理できるように設計された MAF (Managed Add-in Framework) は、以前のバージョンの .NET Framework で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c27c8-147">Previous versions of the .NET Framework introduced the Managed Add-in Framework (MAF), designed to allow applications to isolate and manage extensions.</span></span> <span data-ttu-id="c27c8-148">MAF では MEF と比較してやや高度なレベルに重点が置かれており、MEF では発見可能性、拡張性、および移植性に重点が置かれているのに対し、MAF では拡張機能の特定とアセンブリの読み込みおよびアンロードに重点が置かれています。</span><span class="sxs-lookup"><span data-stu-id="c27c8-148">The focus of MAF is slightly higher-level than MEF, concentrating on extension isolation and assembly loading and unloading, while MEF's focus is on discoverability, extensibility, and portability.</span></span> <span data-ttu-id="c27c8-149">この 2 つのフレームワークは円滑に相互運用でき、1 つのアプリケーションで両方を活用することができます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-149">The two frameworks interoperate smoothly, and a single application can take advantage of both.</span></span>

## <a name="simplecalculator-an-example-application"></a><span data-ttu-id="c27c8-150">SimpleCalculator:アプリケーションの例</span><span class="sxs-lookup"><span data-stu-id="c27c8-150">SimpleCalculator: An example application</span></span>

<span data-ttu-id="c27c8-151">MEF が実行できる処理を理解する最も簡単な方法は、単純な MEF アプリケーションを作成することです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-151">The simplest way to see what MEF can do is to build a simple MEF application.</span></span> <span data-ttu-id="c27c8-152">この例では、SimpleCalculator という名前の単純な電卓を作成します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-152">In this example, you build a very simple calculator named SimpleCalculator.</span></span> <span data-ttu-id="c27c8-153">SimpleCalculator の目的は、"5+3" や "6-2" などの形式で基本的な算術命令を受け取り、正しい答えを返すコンソール アプリケーションを作成することです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-153">The goal of SimpleCalculator is to create a console application that accepts basic arithmetic commands, in the form "5+3" or "6-2", and returns the correct answers.</span></span> <span data-ttu-id="c27c8-154">MEF を使用すると、アプリケーション コードを変更せずに、新しい演算子を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-154">Using MEF, you'll be able to add new operators without changing the application code.</span></span>

<span data-ttu-id="c27c8-155">この例の完成したコードをダウンロードするには、[SimpleCalculator のサンプル (Visual Basic)](/samples/dotnet/samples/simple-calculator-vb/) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c27c8-155">To download the complete code for this example, see the [SimpleCalculator sample (Visual Basic)](/samples/dotnet/samples/simple-calculator-vb/).</span></span>

> [!NOTE]
> <span data-ttu-id="c27c8-156">SimpleCalculator を作成する目的は、これを使用する実際のシナリオを必ずしも提供することではなく、MEF の概念と構文を示すことにあります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-156">The purpose of SimpleCalculator is to demonstrate the concepts and syntax of MEF, rather than to necessarily provide a realistic scenario for its use.</span></span> <span data-ttu-id="c27c8-157">MEF の機能を最大限に活用できるアプリケーションの多くは、SimpleCalculator よりも複雑です。</span><span class="sxs-lookup"><span data-stu-id="c27c8-157">Many of the applications that would benefit most from the power of MEF are more complex than SimpleCalculator.</span></span> <span data-ttu-id="c27c8-158">その他のサンプルについては、GitHub の「[Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c27c8-158">For more extensive examples, see the [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) on GitHub.</span></span>

- <span data-ttu-id="c27c8-159">開始するには、Visual Studio で新しいコンソール アプリケーション プロジェクトを作成し、`SimpleCalculator` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-159">To start, in Visual Studio, create a new Console Application project and name it `SimpleCalculator`.</span></span>

- <span data-ttu-id="c27c8-160">MEF がある `System.ComponentModel.Composition` アセンブリに参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-160">Add a reference to the `System.ComponentModel.Composition` assembly, where MEF resides.</span></span>

- <span data-ttu-id="c27c8-161">*Module1.vb* または *Program.cs* を開き、`System.ComponentModel.Composition` および `System.ComponentModel.Composition.Hosting` に `Imports` または `using` のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-161">Open *Module1.vb* or *Program.cs* and add `Imports` or `using` statements for `System.ComponentModel.Composition` and `System.ComponentModel.Composition.Hosting`.</span></span> <span data-ttu-id="c27c8-162">これらの 2 つの名前空間には、拡張可能なアプリケーションの開発に必要な MEF 型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c27c8-162">These two namespaces contain MEF types you will need to develop an extensible application.</span></span>

- <span data-ttu-id="c27c8-163">Visual Basic を使用している場合は、`Public` モジュールを宣言する行に `Module1` キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-163">If you're using Visual Basic, add the `Public` keyword to the line that declares the `Module1` module.</span></span>

## <a name="composition-container-and-catalogs"></a><span data-ttu-id="c27c8-164">合成コンテナーとカタログ</span><span class="sxs-lookup"><span data-stu-id="c27c8-164">Composition container and catalogs</span></span>

<span data-ttu-id="c27c8-165">MEF 合成モデルのコアは、すべての使用可能なパートが含まれ、合成を実行する "*合成コンテナー*" です</span><span class="sxs-lookup"><span data-stu-id="c27c8-165">The core of the MEF composition model is the *composition container*, which contains all the parts available and performs composition.</span></span> <span data-ttu-id="c27c8-166">合成はインポートとエクスポートの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-166">Composition is the matching up of imports to exports.</span></span> <span data-ttu-id="c27c8-167">最も一般的な種類の合成コンテナーは <xref:System.ComponentModel.Composition.Hosting.CompositionContainer> であり、これは SimpleCalculator で使用します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-167">The most common type of composition container is <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, and you'll use this for SimpleCalculator.</span></span>

<span data-ttu-id="c27c8-168">Visual Basic を使用している場合は、*Module1.vb* に `Program` という名前のパブリック クラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-168">If you're using Visual Basic, add a public class named `Program` in *Module1.vb*.</span></span>

<span data-ttu-id="c27c8-169">*Module1.vb* または *Program.cs* の `Program` クラスに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-169">Add the following line to the `Program` class in *Module1.vb* or *Program.cs*:</span></span>

```vb
Dim _container As CompositionContainer
```

```csharp
private CompositionContainer _container;
```

<span data-ttu-id="c27c8-170">合成コンテナーは、*カタログ*を使用して使用可能なパートを検出します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-170">In order to discover the parts available to it, the composition containers makes use of a *catalog*.</span></span> <span data-ttu-id="c27c8-171">カタログは、いくつかのソースから使用できるパートを検出するためのオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-171">A catalog is an object that makes available parts discovered from some source.</span></span> <span data-ttu-id="c27c8-172">MEF では、指定された型、アセンブリ、またはディレクトリからパートを検出するカタログを提供します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-172">MEF provides catalogs to discover parts from a provided type, an assembly, or a directory.</span></span> <span data-ttu-id="c27c8-173">アプリケーション開発者は、Web サービスなどの他のソースからパートを検出する新しいカタログを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-173">Application developers can easily create new catalogs to discover parts from other sources, such as a Web service.</span></span>

<span data-ttu-id="c27c8-174">`Program` クラスに次のコンストラクターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-174">Add the following constructor to the `Program` class:</span></span>

```vb
Public Sub New()
    ' An aggregate catalog that combines multiple catalogs.
     Dim catalog = New AggregateCatalog()

    ' Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(New AssemblyCatalog(GetType(Program).Assembly))

    ' Create the CompositionContainer with the parts in the catalog.
    _container = New CompositionContainer(catalog)

    ' Fill the imports of this object.
    Try
        _container.ComposeParts(Me)
    Catch ex As CompositionException
        Console.WriteLine(ex.ToString)
    End Try
End Sub
```

```csharp
private Program()
{
    // An aggregate catalog that combines multiple catalogs.
    var catalog = new AggregateCatalog();
    // Adds all the parts found in the same assembly as the Program class.
    catalog.Catalogs.Add(new AssemblyCatalog(typeof(Program).Assembly));

    // Create the CompositionContainer with the parts in the catalog.
    _container = new CompositionContainer(catalog);

    // Fill the imports of this object.
    try
    {
        this._container.ComposeParts(this);
    }
    catch (CompositionException compositionException)
    {
        Console.WriteLine(compositionException.ToString());
   }
}
```

<span data-ttu-id="c27c8-175"><xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> を呼び出すことで、合成コンテナーに対して特定のパート セット (この例では `Program` の現在のインスタンス) を合成するように指示します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-175">The call to <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> tells the composition container to compose a specific set of parts, in this case the current instance of `Program`.</span></span> <span data-ttu-id="c27c8-176">ただし、この時点では、`Program` に満たす必要のあるインポートがないため、何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-176">At this point, however, nothing will happen, since `Program` has no imports to fill.</span></span>

## <a name="imports-and-exports-with-attributes"></a><span data-ttu-id="c27c8-177">属性を使用したインポートとエクスポート</span><span class="sxs-lookup"><span data-stu-id="c27c8-177">Imports and Exports with attributes</span></span>

<span data-ttu-id="c27c8-178">まず、`Program` で電卓をインポートします。</span><span class="sxs-lookup"><span data-stu-id="c27c8-178">First, you have `Program` import a calculator.</span></span> <span data-ttu-id="c27c8-179">これにより、`Program` に渡されるコンソール入力やコンソール出力などのユーザー インターフェイスに関連する要素が電卓のロジックから切り離されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-179">This allows the separation of user interface concerns, such as the console input and output that will go into `Program`, from the logic of the calculator.</span></span>

<span data-ttu-id="c27c8-180">`Program` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-180">Add the following code to the `Program` class:</span></span>

```vb
<Import(GetType(ICalculator))>
Public Property calculator As ICalculator
```

```csharp
[Import(typeof(ICalculator))]
public ICalculator calculator;
```

<span data-ttu-id="c27c8-181">`calculator` オブジェクトの宣言に特に変わった点はありませんが、<xref:System.ComponentModel.Composition.ImportAttribute> 属性で装飾されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c27c8-181">Notice that the declaration of the `calculator` object is not unusual, but that it is decorated with the <xref:System.ComponentModel.Composition.ImportAttribute> attribute.</span></span> <span data-ttu-id="c27c8-182">この属性は、インポートとなるもの、つまり、オブジェクトが合成されると合成エンジンによって満たされるものを宣言します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-182">This attribute declares something to be an import; that is, it will be filled by the composition engine when the object is composed.</span></span>

<span data-ttu-id="c27c8-183">各インポートには "*コントラクト*" があり、これにより、対応するエクスポートが決定されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-183">Every import has a *contract*, which determines what exports it will be matched with.</span></span> <span data-ttu-id="c27c8-184">コントラクトは、明示的に指定された文字列であったり、指定された型に基づいて MEF によって自動的に生成されたりします (この例では、`ICalculator` というインターフェイス)。</span><span class="sxs-lookup"><span data-stu-id="c27c8-184">The contract can be an explicitly specified string, or it can be automatically generated by MEF from a given type, in this case the interface `ICalculator`.</span></span> <span data-ttu-id="c27c8-185">対応するコントラクトで宣言されたエクスポートが、このインポートを満たします。</span><span class="sxs-lookup"><span data-stu-id="c27c8-185">Any export declared with a matching contract will fulfill this import.</span></span> <span data-ttu-id="c27c8-186">`calculator` オブジェクトの型は実際には `ICalculator` ですが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-186">Note that while the type of the `calculator` object is in fact `ICalculator`, this is not required.</span></span> <span data-ttu-id="c27c8-187">コントラクトは、インポートするオブジェクトの型に依存しません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-187">The contract is independent from the type of the importing object.</span></span> <span data-ttu-id="c27c8-188">この例では、`typeof(ICalculator)` は省略できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-188">(In this case, you could leave out the `typeof(ICalculator)`.</span></span> <span data-ttu-id="c27c8-189">MEF では、明示的に指定しない限り、インポートの型に基づいて自動的にコントラクトが想定されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-189">MEF will automatically assume the contract to be based on the type of the import unless you specify it explicitly.)</span></span>

<span data-ttu-id="c27c8-190">次のように、この単純なインターフェイスをモジュールまたは `SimpleCalculator` 名前空間に追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-190">Add this very simple interface to the module or `SimpleCalculator` namespace:</span></span>

```vb
Public Interface ICalculator
    Function Calculate(input As String) As String
End Interface
```

```csharp
public interface ICalculator
{
    String Calculate(String input);
}
```

<span data-ttu-id="c27c8-191">`ICalculator` を定義したので、これを実装するクラスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c27c8-191">Now that you have defined `ICalculator`, you need a class that implements it.</span></span> <span data-ttu-id="c27c8-192">モジュールまたは `SimpleCalculator` 名前空間に次のクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-192">Add the following class to the module or `SimpleCalculator` namespace:</span></span>

```vb
<Export(GetType(ICalculator))>
Public Class MySimpleCalculator
   Implements ICalculator

End Class
```

```csharp
[Export(typeof(ICalculator))]
class MySimpleCalculator : ICalculator
{

}
```

<span data-ttu-id="c27c8-193">これが、`Program` でインポートに対応するエクスポートになります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-193">Here is the export that will match the import in `Program`.</span></span> <span data-ttu-id="c27c8-194">エクスポートがインポートと一致するには、エクスポートで同じコントラクトを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-194">In order for the export to match the import, the export must have the same contract.</span></span> <span data-ttu-id="c27c8-195">`typeof(MySimpleCalculator)` に基づいてコントラクトでエクスポートすると、不一致が発生し、インポートは満たされません。コントラクトは正確に対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-195">Exporting under a contract based on `typeof(MySimpleCalculator)` would produce a mismatch, and the import would not be filled; the contract needs to match exactly.</span></span>

<span data-ttu-id="c27c8-196">合成コンテナーはこのアセンブリで使用可能なすべてのパートを使用して設定されるため、`MySimpleCalculator` パートが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-196">Since the composition container will be populated with all the parts available in this assembly, the `MySimpleCalculator` part will be available.</span></span> <span data-ttu-id="c27c8-197">`Program` のコンストラクターが `Program` オブジェクトで合成を実行するとき、そのインポートは、それを満たすために作成される `MySimpleCalculator` オブジェクトで満たされます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-197">When the constructor for `Program` performs composition on the `Program` object, its import will be filled with a `MySimpleCalculator` object, which will be created for that purpose.</span></span>

<span data-ttu-id="c27c8-198">ユーザー インターフェイス レイヤー (`Program`) がそれ以外のことを認識する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-198">The user interface layer (`Program`) does not need to know anything else.</span></span> <span data-ttu-id="c27c8-199">したがって、`Main` メソッド内の残りのユーザー インターフェイス ロジックを記述できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-199">You can therefore fill in the rest of the user interface logic in the `Main` method.</span></span>

<span data-ttu-id="c27c8-200">`Main` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-200">Add the following code to the `Main` method:</span></span>

```vb
Sub Main()
    ' Composition is performed in the constructor.
    Dim p As New Program()
    Dim s As String
    Console.WriteLine("Enter Command:")
    While (True)
        s = Console.ReadLine()
        Console.WriteLine(p.calculator.Calculate(s))
    End While
End Sub
```

```csharp
static void Main(string[] args)
{
    // Composition is performed in the constructor.
    var p = new Program();
    string s;
    Console.WriteLine("Enter Command:");
    while (true)
    {
        s = Console.ReadLine();
        Console.WriteLine(p.calculator.Calculate(s));
    }
}
```

 <span data-ttu-id="c27c8-201">このコードは、単純に入力行を読み取り、結果に対して `Calculate` の `ICalculator` 関数を呼び出して、結果をコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-201">This code simply reads a line of input and calls the `Calculate` function of `ICalculator` on the result, which it writes back to the console.</span></span> <span data-ttu-id="c27c8-202">これが、`Program` で必要なすべてのコードです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-202">That is all the code you need in `Program`.</span></span> <span data-ttu-id="c27c8-203">その他の処理は、パート内で行われます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-203">All the rest of the work will happen in the parts.</span></span>

## <a name="further-imports-and-importmany"></a><span data-ttu-id="c27c8-204">その他のインポートと ImportMany</span><span class="sxs-lookup"><span data-stu-id="c27c8-204">Further Imports and ImportMany</span></span>

<span data-ttu-id="c27c8-205">SimpleCalculator に拡張性を持たせるためには、演算の一覧をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-205">In order for SimpleCalculator to be extensible, it needs to import a list of operations.</span></span> <span data-ttu-id="c27c8-206">通常の <xref:System.ComponentModel.Composition.ImportAttribute> 属性は、1 つの <xref:System.ComponentModel.Composition.ExportAttribute> だけで満たされます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-206">An ordinary <xref:System.ComponentModel.Composition.ImportAttribute> attribute is filled by one and only one <xref:System.ComponentModel.Composition.ExportAttribute>.</span></span> <span data-ttu-id="c27c8-207">使用可能なエクスポートが複数あれば、合成エンジンでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-207">If more than one is available, the composition engine produces an error.</span></span> <span data-ttu-id="c27c8-208">任意の数のエクスポートで満たすことのできるインポートを作成するには、<xref:System.ComponentModel.Composition.ImportManyAttribute> 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-208">To create an import that can be filled by any number of exports, you can use the <xref:System.ComponentModel.Composition.ImportManyAttribute> attribute.</span></span>

<span data-ttu-id="c27c8-209">`MySimpleCalculator` クラスに次の演算プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-209">Add the following operations property to the `MySimpleCalculator` class:</span></span>

```vb
<ImportMany()>
Public Property operations As IEnumerable(Of Lazy(Of IOperation, IOperationData))
```

```csharp
[ImportMany]
IEnumerable<Lazy<IOperation, IOperationData>> operations;
```

<span data-ttu-id="c27c8-210"><xref:System.Lazy%602> は、エクスポートの間接参照を格納するために MEF に用意されている型です。</span><span class="sxs-lookup"><span data-stu-id="c27c8-210"><xref:System.Lazy%602> is a type provided by MEF to hold indirect references to exports.</span></span> <span data-ttu-id="c27c8-211">これにより、エクスポートされるオブジェクト自体に加えて、"*エクスポート メタデータ*" (エクスポートされるオブジェクトについて説明する情報) も取得できます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-211">Here, in addition to the exported object itself, you also get *export metadata*, or information that describes the exported object.</span></span> <span data-ttu-id="c27c8-212">各 <xref:System.Lazy%602> には、実際の操作を表す `IOperation` オブジェクト、およびそのメタデータを表す `IOperationData` オブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-212">Each <xref:System.Lazy%602> contains an `IOperation` object, representing an actual operation, and an `IOperationData` object, representing its metadata.</span></span>

<span data-ttu-id="c27c8-213">次の単純なインターフェイスをモジュールまたは `SimpleCalculator` 名前空間に追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-213">Add the following simple interfaces to the module or `SimpleCalculator` namespace:</span></span>

```vb
Public Interface IOperation
    Function Operate(left As Integer, right As Integer) As Integer
End Interface

Public Interface IOperationData
    ReadOnly Property Symbol As Char
End Interface
```

```csharp
public interface IOperation
{
     int Operate(int left, int right);
}

public interface IOperationData
{
    Char Symbol { get; }
}
```

 <span data-ttu-id="c27c8-214">ここでは、各演算のメタデータは、演算を表す +、-、\* などの記号です。</span><span class="sxs-lookup"><span data-stu-id="c27c8-214">In this case, the metadata for each operation is the symbol that represents that operation, such as +, -, \*, and so on.</span></span> <span data-ttu-id="c27c8-215">加算の演算を使用可能にするには、次のクラスをモジュールまたは `SimpleCalculator` 名前空間に追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-215">To make the addition operation available, add the following class to the module or `SimpleCalculator` namespace:</span></span>

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "+"c)>
Public Class Add
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left + right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '+')]
class Add: IOperation
{
    public int Operate(int left, int right)
    {
        return left + right;
    }
}
```

<span data-ttu-id="c27c8-216"><xref:System.ComponentModel.Composition.ExportAttribute> 属性は、以前と同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-216">The <xref:System.ComponentModel.Composition.ExportAttribute> attribute functions as it did before.</span></span> <span data-ttu-id="c27c8-217"><xref:System.ComponentModel.Composition.ExportMetadataAttribute> 属性は、そのエクスポートに対し、名前と値のペアの形式でメタデータをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="c27c8-217">The <xref:System.ComponentModel.Composition.ExportMetadataAttribute> attribute attaches metadata, in the form of a name-value pair, to that export.</span></span> <span data-ttu-id="c27c8-218">`Add` クラスは `IOperation` を実装していますが、`IOperationData` を実装するクラスは明示的に定義されていません。</span><span class="sxs-lookup"><span data-stu-id="c27c8-218">While the `Add` class implements `IOperation`, a class that implements `IOperationData` is not explicitly defined.</span></span> <span data-ttu-id="c27c8-219">代わりに、提供されるメタデータの名前に基づくプロパティを使用して、MEF によってクラスが暗黙的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-219">Instead, a class is implicitly created by MEF with properties based on the names of the metadata provided.</span></span> <span data-ttu-id="c27c8-220">(MEF でメタデータにアクセスする方法にはいくつかありますが、これはその 1 つです)。</span><span class="sxs-lookup"><span data-stu-id="c27c8-220">(This is one of several ways to access metadata in MEF.)</span></span>

<span data-ttu-id="c27c8-221">MEF での合成は "*再帰的*" です。</span><span class="sxs-lookup"><span data-stu-id="c27c8-221">Composition in MEF is *recursive*.</span></span> <span data-ttu-id="c27c8-222">先ほど、`Program` オブジェクトを明示的に合成しました。これは `ICalculator` をインポートし、その型は `MySimpleCalculator` であることが判明しました。</span><span class="sxs-lookup"><span data-stu-id="c27c8-222">You explicitly composed the `Program` object, which imported an `ICalculator` that turned out to be of type `MySimpleCalculator`.</span></span> <span data-ttu-id="c27c8-223">この `MySimpleCalculator` は `IOperation` オブジェクトのコレクションをインポートし、このインポートは `MySimpleCalculator` が作成されるときに `Program` のインポートと同時に満たされます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-223">`MySimpleCalculator`, in turn, imports a collection of `IOperation` objects, and that import will be filled when `MySimpleCalculator` is created, at the same time as the imports of `Program`.</span></span> <span data-ttu-id="c27c8-224">`Add` クラスがさらに別のインポートを宣言している場合は、そのインポートも満たされる必要があり、宣言されているインポートごとにそれが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-224">If the `Add` class declared a further import, that too would have to be filled, and so on.</span></span> <span data-ttu-id="c27c8-225">満たされないインポートが残ると、合成エラーが発生します</span><span class="sxs-lookup"><span data-stu-id="c27c8-225">Any import left unfilled results in a composition error.</span></span> <span data-ttu-id="c27c8-226">(省略可能なインポートを宣言する、またはそれらに既定値を割り当てることはできます)。</span><span class="sxs-lookup"><span data-stu-id="c27c8-226">(It is possible, however, to declare imports to be optional or to assign them default values.)</span></span>

## <a name="calculator-logic"></a><span data-ttu-id="c27c8-227">電卓のロジック</span><span class="sxs-lookup"><span data-stu-id="c27c8-227">Calculator Logic</span></span>

<span data-ttu-id="c27c8-228">3 つのパートを作成したので、残っている作業は電卓ロジックを作成することです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-228">With these parts in place, all that remains is the calculator logic itself.</span></span> <span data-ttu-id="c27c8-229">`MySimpleCalculator` クラスに次のコードを追加して、`Calculate` メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-229">Add the following code in the `MySimpleCalculator` class to implement the `Calculate` method:</span></span>

```vb
Public Function Calculate(input As String) As String Implements ICalculator.Calculate
    Dim left, right As Integer
    Dim operation As Char
    ' Finds the operator.
    Dim fn = FindFirstNonDigit(input)
    If fn < 0 Then
        Return "Could not parse command."
    End If
    operation = input(fn)
    Try
        ' Separate out the operands.
        left = Integer.Parse(input.Substring(0, fn))
        right = Integer.Parse(input.Substring(fn + 1))
    Catch ex As Exception
        Return "Could not parse command."
    End Try
    For Each i As Lazy(Of IOperation, IOperationData) In operations
        If i.Metadata.symbol = operation Then
            Return i.Value.Operate(left, right).ToString()
        End If
    Next
    Return "Operation not found!"
End Function
```

```csharp
public String Calculate(string input)
{
    int left;
    int right;
    char operation;
    // Finds the operator.
    int fn = FindFirstNonDigit(input);
    if (fn < 0) return "Could not parse command.";

    try
    {
        // Separate out the operands.
        left = int.Parse(input.Substring(0, fn));
        right = int.Parse(input.Substring(fn + 1));
    }
    catch
    {
        return "Could not parse command.";
    }

    operation = input[fn];

    foreach (Lazy<IOperation, IOperationData> i in operations)
    {
        if (i.Metadata.Symbol.Equals(operation)) return i.Value.Operate(left, right).ToString();
    }
    return "Operation Not Found!";
}
```

<span data-ttu-id="c27c8-230">1 つ目のステップでは、入力文字列が解析され、左オペランド、右オペランド、および演算子文字が特定されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-230">The initial steps parse the input string into left and right operands and an operator character.</span></span> <span data-ttu-id="c27c8-231">`foreach` ループでは、`operations` コレクションのすべてのメンバーが検証されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-231">In the `foreach` loop, every member of the `operations` collection is examined.</span></span> <span data-ttu-id="c27c8-232">これらのオブジェクトの型は <xref:System.Lazy%602> です。またそのメタデータ値とエクスポートされるオブジェクトにはそれぞれ <xref:System.Lazy%602.Metadata%2A> プロパティと <xref:System.Lazy%601.Value%2A> プロパティでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-232">These objects are of type <xref:System.Lazy%602>, and their metadata values and exported object can be accessed with the <xref:System.Lazy%602.Metadata%2A> property and the <xref:System.Lazy%601.Value%2A> property respectively.</span></span> <span data-ttu-id="c27c8-233">この場合、`Symbol` オブジェクトの `IOperationData` プロパティが一致することが検出されると、電卓は `Operate` オブジェクトの `IOperation` メソッドを呼び出し、結果を返します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-233">In this case, if the `Symbol` property of the `IOperationData` object is discovered to be a match, the calculator calls the `Operate` method of the `IOperation` object and returns the result.</span></span>

<span data-ttu-id="c27c8-234">電卓を完成させるには、文字列内で最初に出現する数字以外の文字の位置を返すヘルパー メソッドも必要です。</span><span class="sxs-lookup"><span data-stu-id="c27c8-234">To complete the calculator, you also need a helper method that returns the position of the first non-digit character in a string.</span></span> <span data-ttu-id="c27c8-235">`MySimpleCalculator` クラスに次のヘルパー メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-235">Add the following helper method to the `MySimpleCalculator` class:</span></span>

```vb
Private Function FindFirstNonDigit(s As String) As Integer
    For i = 0 To s.Length - 1
        If Not Char.IsDigit(s(i)) Then Return i
    Next
    Return -1
End Function
```

```csharp
private int FindFirstNonDigit(string s)
{
    for (int i = 0; i < s.Length; i++)
    {
        if (!Char.IsDigit(s[i])) return i;
    }
    return -1;
}
```

<span data-ttu-id="c27c8-236">これで、プロジェクトをコンパイルして実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c27c8-236">You should now be able to compile and run the project.</span></span> <span data-ttu-id="c27c8-237">Visual Basic の場合、`Public` に `Module1` キーワードを追加していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c27c8-237">In Visual Basic, make sure that you added the `Public` keyword to `Module1`.</span></span> <span data-ttu-id="c27c8-238">コンソール ウィンドウで "5+3" などの加算演算を入力すると、電卓が結果を返します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-238">In the console window, type an addition operation, such as "5+3", and the calculator returns the results.</span></span> <span data-ttu-id="c27c8-239">それ以外の演算子を入力すると、"Operation Not Found!" という</span><span class="sxs-lookup"><span data-stu-id="c27c8-239">Any other operator results in the "Operation Not Found!"</span></span> <span data-ttu-id="c27c8-240">メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-240">message.</span></span>

## <a name="extending-simplecalculator-using-a-new-class"></a><span data-ttu-id="c27c8-241">新しいクラスを使用した SimpleCalculator の拡張</span><span class="sxs-lookup"><span data-stu-id="c27c8-241">Extending SimpleCalculator using a new class</span></span>

<span data-ttu-id="c27c8-242">これで、電卓が機能するようになりました。新しい演算の追加は簡単です。</span><span class="sxs-lookup"><span data-stu-id="c27c8-242">Now that the calculator works, adding a new operation is easy.</span></span> <span data-ttu-id="c27c8-243">モジュールまたは `SimpleCalculator` 名前空間に次のクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-243">Add the following class to the module or `SimpleCalculator` namespace:</span></span>

```vb
<Export(GetType(IOperation))>
<ExportMetadata("Symbol", "-"c)>
Public Class Subtract
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left - right
    End Function
End Class
```

```csharp
[Export(typeof(IOperation))]
[ExportMetadata("Symbol", '-')]
class Subtract : IOperation
{
    public int Operate(int left, int right)
    {
        return left - right;
    }
}
```

<span data-ttu-id="c27c8-244">プロジェクトをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-244">Compile and run the project.</span></span> <span data-ttu-id="c27c8-245">"5-3" などの減算演算を入力します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-245">Type a subtraction operation, such as "5-3".</span></span> <span data-ttu-id="c27c8-246">電卓は、加算だけでなく減算もサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="c27c8-246">The calculator now supports subtraction as well as addition.</span></span>

## <a name="extending-simplecalculator-using-a-new-assembly"></a><span data-ttu-id="c27c8-247">新しいアセンブリを使用した SimpleCalculator の拡張</span><span class="sxs-lookup"><span data-stu-id="c27c8-247">Extending SimpleCalculator using a new assembly</span></span>

<span data-ttu-id="c27c8-248">ソース コードにクラスを追加するのは簡単ですが、MEF には、アプリケーション独自のソースの外部でパートを検索する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="c27c8-248">Adding classes to the source code is simple enough, but MEF provides the ability to look outside an application’s own source for parts.</span></span> <span data-ttu-id="c27c8-249">この例を示すためには、<xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> を追加することで、独自のアセンブリだけではなくディレクトリでもパートを検索するように SimpleCalculator を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-249">To demonstrate this, you will need to modify SimpleCalculator to search a directory, as well as its own assembly, for parts, by adding a <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.</span></span>

<span data-ttu-id="c27c8-250">SimpleCalculator プロジェクトに `Extensions` という名前の新しいディレクトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-250">Add a new directory named `Extensions` to the SimpleCalculator project.</span></span> <span data-ttu-id="c27c8-251">これは、アプリケーション レベルではなく、プロジェクト レベルで追加してください。</span><span class="sxs-lookup"><span data-stu-id="c27c8-251">Make sure to add it at the project level, and not at the solution level.</span></span> <span data-ttu-id="c27c8-252">次に、`ExtendedOperations` という名前の新しいクラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-252">Then add a new Class Library project to the solution, named `ExtendedOperations`.</span></span> <span data-ttu-id="c27c8-253">新しいプロジェクトをコンパイルし、個別のアセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-253">The new project will compile into a separate assembly.</span></span>

<span data-ttu-id="c27c8-254">ExtendedOperations プロジェクトのプロジェクト プロパティ デザイナーを開き、 **[コンパイル]** タブまたは **[ビルド]** タブをクリックします。SimpleCalculator プロジェクト ディレクトリの Extensions ディレクトリ ( *..\SimpleCalculator\Extensions\\* ) を指すように、 **[ビルド出力パス]** または **[出力パス]** を変更します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-254">Open the Project Properties Designer for the ExtendedOperations project and click the **Compile** or **Build** tab. Change the **Build output path** or **Output path** to point to the Extensions directory in the SimpleCalculator project directory (*..\SimpleCalculator\Extensions\\*).</span></span>

 <span data-ttu-id="c27c8-255">*Module1.vb* または *Program.cs* で、`Program` コンストラクターに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-255">In *Module1.vb* or *Program.cs*, add the following line to the `Program` constructor:</span></span>

```vb
catalog.Catalogs.Add(New DirectoryCatalog("C:\SimpleCalculator\SimpleCalculator\Extensions"))
```

```csharp
catalog.Catalogs.Add(new DirectoryCatalog("C:\\SimpleCalculator\\SimpleCalculator\\Extensions"));
```

<span data-ttu-id="c27c8-256">例に示されているパスを、Extensions ディレクトリのパスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-256">Replace the example path with the path to your Extensions directory.</span></span> <span data-ttu-id="c27c8-257">(この絶対パスはデバッグにのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-257">(This absolute path is for debugging purposes only.</span></span> <span data-ttu-id="c27c8-258">運用アプリケーションでは、相対パスを使用します。)これで、<xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> により、Extensions ディレクトリ内のアセンブリで見つかったすべてのパーツが合成コンテナーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-258">In a production application, you would use a relative path.) The <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> will now add any parts found in any assemblies in the Extensions directory to the composition container.</span></span>

<span data-ttu-id="c27c8-259">ExtendedOperations プロジェクトで、SimpleCalculator と System.ComponentModel.Composition への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-259">In the ExtendedOperations project, add references to SimpleCalculator and System.ComponentModel.Composition.</span></span> <span data-ttu-id="c27c8-260">ExtendedOperations クラス ファイルで、System.ComponentModel.Composition の `Imports` ステートメントまたは `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-260">In the ExtendedOperations class file, add an `Imports` or a `using` statement for System.ComponentModel.Composition.</span></span> <span data-ttu-id="c27c8-261">Visual Basic では、SimpleCalculator の `Imports` ステートメントも追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-261">In Visual Basic, also add an `Imports` statement for SimpleCalculator.</span></span> <span data-ttu-id="c27c8-262">次に、ExtendedOperations クラス ファイルに次のクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-262">Then add the following class to the ExtendedOperations class file:</span></span>

```vb
<Export(GetType(SimpleCalculator.IOperation))>
<ExportMetadata("Symbol", "%"c)>
Public Class Modulo
    Implements IOperation

    Public Function Operate(left As Integer, right As Integer) As Integer Implements IOperation.Operate
        Return left Mod right
    End Function
End Class
```

```csharp
[Export(typeof(SimpleCalculator.IOperation))]
[ExportMetadata("Symbol", '%')]
public class Mod : SimpleCalculator.IOperation
{
    public int Operate(int left, int right)
    {
        return left % right;
    }
}
```

<span data-ttu-id="c27c8-263">コントラクトを対応させるには、<xref:System.ComponentModel.Composition.ExportAttribute> 属性が <xref:System.ComponentModel.Composition.ImportAttribute> と同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27c8-263">Note that in order for the contract to match, the <xref:System.ComponentModel.Composition.ExportAttribute> attribute must have the same type as the <xref:System.ComponentModel.Composition.ImportAttribute>.</span></span>

<span data-ttu-id="c27c8-264">プロジェクトをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-264">Compile and run the project.</span></span> <span data-ttu-id="c27c8-265">新しい Mod (%) 演算子をテストします。</span><span class="sxs-lookup"><span data-stu-id="c27c8-265">Test the new Mod (%) operator.</span></span>

## <a name="conclusion"></a><span data-ttu-id="c27c8-266">まとめ</span><span class="sxs-lookup"><span data-stu-id="c27c8-266">Conclusion</span></span>

<span data-ttu-id="c27c8-267">ここでは、MEF の基本的な概念について説明しました。</span><span class="sxs-lookup"><span data-stu-id="c27c8-267">This topic covered the basic concepts of MEF.</span></span>

- <span data-ttu-id="c27c8-268">パート、カタログ、および合成コンテナー</span><span class="sxs-lookup"><span data-stu-id="c27c8-268">Parts, catalogs, and the composition container</span></span>

     <span data-ttu-id="c27c8-269">パートと合成コンテナーは、MEF アプリケーションの基本のビルド ブロックです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-269">Parts and the composition container are the basic building blocks of a MEF application.</span></span> <span data-ttu-id="c27c8-270">パートは、それ自体までの (自身を含む) 値をインポートまたはエクスポートするオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c27c8-270">A part is any object that imports or exports a value, up to and including itself.</span></span> <span data-ttu-id="c27c8-271">カタログは、特定のソースからのパートのコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-271">A catalog provides a collection of parts from a particular source.</span></span> <span data-ttu-id="c27c8-272">合成コンテナーは、カタログによって提供されるパートを使用して合成 (インポートのエクスポートへの結合) を実行します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-272">The composition container uses the parts provided by a catalog to perform composition, the binding of imports to exports.</span></span>

- <span data-ttu-id="c27c8-273">インポートとエクスポート</span><span class="sxs-lookup"><span data-stu-id="c27c8-273">Imports and exports</span></span>

     <span data-ttu-id="c27c8-274">インポートとエクスポートは、コンポーネントが通信を行う手段です。</span><span class="sxs-lookup"><span data-stu-id="c27c8-274">Imports and exports are the way by which components communicate.</span></span> <span data-ttu-id="c27c8-275">インポートを使用して、コンポーネントは特定の値またはオブジェクトが必要であることを指定します。エクスポートを使用して、コンポーネントは値が使用可能であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="c27c8-275">With an import, the component specifies a need for a particular value or object, and with an export it specifies the availability of a value.</span></span> <span data-ttu-id="c27c8-276">各インポートは、コントラクトを通じて、エクスポートの一覧と対応付けされます。</span><span class="sxs-lookup"><span data-stu-id="c27c8-276">Each import is matched with a list of exports by way of its contract.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c27c8-277">次の手順</span><span class="sxs-lookup"><span data-stu-id="c27c8-277">Next steps</span></span>

<span data-ttu-id="c27c8-278">この例の完成したコードをダウンロードするには、[SimpleCalculator のサンプル (Visual Basic)](/samples/dotnet/samples/simple-calculator-vb/) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c27c8-278">To download the complete code for this example, see the [SimpleCalculator sample (Visual Basic)](/samples/dotnet/samples/simple-calculator-vb/).</span></span>

 <span data-ttu-id="c27c8-279">詳しい情報とコード例については、「[Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c27c8-279">For more information and code examples, see [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef).</span></span> <span data-ttu-id="c27c8-280">MEF 型の一覧については、<xref:System.ComponentModel.Composition?displayProperty=nameWithType> 名前空間を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c27c8-280">For a list of the MEF types, see the <xref:System.ComponentModel.Composition?displayProperty=nameWithType> namespace.</span></span>
