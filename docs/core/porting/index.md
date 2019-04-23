---
title: .NET Framework から .NET Core にコードを移植する
description: 移植プロセスを理解し、.NET Framework プロジェクトを .NET Core に移植する際に役立つツールを確認します。
author: cartermp
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 870320c8467237e87a2675ec5cfb57647026d8ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663233"
---
# <a name="port-your-code-from-net-framework-to-net-core"></a><span data-ttu-id="1d499-103">.NET Framework から .NET Core にコードを移植する</span><span class="sxs-lookup"><span data-stu-id="1d499-103">Port your code from .NET Framework to .NET Core</span></span>

<span data-ttu-id="1d499-104">.NET Framework 上で実行されるコードがある場合は、.NET Core 上でコードを実行することにも関心があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="1d499-104">If you've got code that runs on the .NET Framework, you may be interested in running your code on .NET Core, too.</span></span> <span data-ttu-id="1d499-105">ここでは、移植プロセスの概要と、コードを .NET Core に移植するときに役立つツールの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1d499-105">Here's an overview of the porting process and a list of the tools you may find helpful when porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="1d499-106">移植プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="1d499-106">Overview of the porting process</span></span>

<span data-ttu-id="1d499-107">プロジェクトを .NET Core に移植する場合、次のプロセスを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d499-107">This is the process we recommend you take when porting your project to .NET Core.</span></span> <span data-ttu-id="1d499-108">プロセスの各手順については、他の記事で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="1d499-108">Each step of the process is covered in more detail in further articles.</span></span>

1. <span data-ttu-id="1d499-109">サードパーティの依存関係を識別し、理解します。</span><span class="sxs-lookup"><span data-stu-id="1d499-109">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="1d499-110">この手順では、サードパーティの依存関係がどのようなものか、それらにどのように依存しているか、それらが .NET Core でも実行されるかどうかを確認する方法、および実行されない場合に従う手順について理解します。</span><span class="sxs-lookup"><span data-stu-id="1d499-110">This step involves understanding what your third-party dependencies are, how you depend on them, how to check if they also run on .NET Core, and steps you can take if they don't.</span></span> <span data-ttu-id="1d499-111">またここでは、.NET Core で使われる [PackageReference](/nuget/consume-packages/package-references-in-project-files) 形式に依存関係を移行する方法についても説明しています。</span><span class="sxs-lookup"><span data-stu-id="1d499-111">It also covers how you can migrate your dependencies over to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format that is used in .NET Core.</span></span>

2. <span data-ttu-id="1d499-112">移植するすべてのプロジェクトを、.NET Framework 4.7.2 以降をターゲットとするように再ターゲットします。</span><span class="sxs-lookup"><span data-stu-id="1d499-112">Retarget all projects you wish to port to target the .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="1d499-113">この手順により、.NET Core で特定の API がサポートされない場合に、.NET Framework 固有のターゲットに対して API の代替を確実に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d499-113">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

3. <span data-ttu-id="1d499-114">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md)使用して、アセンブリを分析し、その結果に基づいて移植を行う計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="1d499-114">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="1d499-115">API Portability Analyzer ツールは、コンパイル済みアセンブリを分析し、レポートを生成します。これには、移植性に関する大まかな概要と、使用中の API のうちで .NET Core では利用できないものそれぞれについての内訳が記載されています。</span><span class="sxs-lookup"><span data-stu-id="1d499-115">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report that shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span> <span data-ttu-id="1d499-116">このレポートをコードベースの分析と共に使用して、コードを移植する方法の計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="1d499-116">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>

4. <span data-ttu-id="1d499-117">テスト コードを移植します。</span><span class="sxs-lookup"><span data-stu-id="1d499-117">Port your tests code.</span></span>

   <span data-ttu-id="1d499-118">.NET Core への移植はコードベースにとって大きな変更となるため、コードの移植時にテストを実行できるように、テストを移植することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d499-118">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to get your tests ported, so that you can run tests as you port your code over.</span></span> <span data-ttu-id="1d499-119">MSTest、xUnit、NUnit はすべて .NET Core をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1d499-119">MSTest, xUnit, and NUnit all support .NET Core.</span></span>

5. <span data-ttu-id="1d499-120">移植の計画を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d499-120">Execute your plan for porting!</span></span>

<span data-ttu-id="1d499-121">移植プロセス中に使うと役立つツールを、次の一覧に示します。</span><span class="sxs-lookup"><span data-stu-id="1d499-121">The following list shows tools you might find helpful to use during the porting process:</span></span>

* <span data-ttu-id="1d499-122">.NET Portability Analyzer - [コマンドライン ツール](https://github.com/Microsoft/dotnet-apiport/releases)または [Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)。アセンブリごとの問題の内訳を含む、.NET Framework と .NET Core の間のコードの移植性に関するレポートを生成できるツール チェーンです。</span><span class="sxs-lookup"><span data-stu-id="1d499-122">.NET Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span> <span data-ttu-id="1d499-123">詳細については、[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d499-123">For more information, see [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md).</span></span>
* <span data-ttu-id="1d499-124">.NET API アナライザー - さまざまなプラットフォームでの C# API の互換性リスクの可能性と、非推奨の API の呼び出しを検出する Roslyn アナライザーです。</span><span class="sxs-lookup"><span data-stu-id="1d499-124">.NET API analyzer - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span> <span data-ttu-id="1d499-125">詳細については、「[.NET API アナライザー](../../standard/analyzers/api-analyzer.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d499-125">For more information, see [.NET API analyzer](../../standard/analyzers/api-analyzer.md).</span></span>
* <span data-ttu-id="1d499-126">Reverse Package Search - 型を検索し、その型を含むパッケージを検索するための[便利な Web サービス](https://packagesearch.azurewebsites.net)。</span><span class="sxs-lookup"><span data-stu-id="1d499-126">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

<span data-ttu-id="1d499-127">さらに、[CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) ツールを使って、小規模なソリューションや個々のプロジェクトを .NET Core プロジェクトのファイル形式に移植してみることが可能です。</span><span class="sxs-lookup"><span data-stu-id="1d499-127">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING] 
> <span data-ttu-id="1d499-128">CsprojToVs2017 はサードパーティ製のツールです。</span><span class="sxs-lookup"><span data-stu-id="1d499-128">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="1d499-129">すべてのプロジェクトに対してこれが動作する保証はありません。また、依存している動作に微妙な変更が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d499-129">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="1d499-130">CsprojToVs2017 は、自動化できる基本的なことを自動化するための "_開始点_" として使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d499-130">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="1d499-131">これは、プロジェクトのファイル形式の移行に対する保証されたソリューションではありません。</span><span class="sxs-lookup"><span data-stu-id="1d499-131">It is not a guaranteed solution to migrating project file formats.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="1d499-132">次へ</span><span class="sxs-lookup"><span data-stu-id="1d499-132">Next</span></span>](net-framework-tech-unavailable.md)
