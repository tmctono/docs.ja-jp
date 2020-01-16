---
title: .NET Framework から .NET Core への移植
description: 移植プロセスを理解し、.NET Framework プロジェクトを .NET Core に移植する際に役立つツールを確認します。
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: e483bb6e48dad6c3bf71bfa81e704a137fc02094
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937313"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a><span data-ttu-id="0794a-103">.NET Framework から .NET Core への移植の概要</span><span class="sxs-lookup"><span data-stu-id="0794a-103">Overview of porting from .NET Framework to .NET Core</span></span>

<span data-ttu-id="0794a-104">現在 .NET Framework で実行しているコードの .NET Core への移植を検討する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0794a-104">You might have code that currently runs on the .NET Framework that you're interested in porting to .NET Core.</span></span> <span data-ttu-id="0794a-105">この記事では、次について説明します。</span><span class="sxs-lookup"><span data-stu-id="0794a-105">This article provides:</span></span>

* <span data-ttu-id="0794a-106">移植プロセスの概要。</span><span class="sxs-lookup"><span data-stu-id="0794a-106">An overview of the porting process.</span></span>
* <span data-ttu-id="0794a-107">コードを .NET Core に移植するときに役立つ場合があるツールの一覧。</span><span class="sxs-lookup"><span data-stu-id="0794a-107">A list of tools that you may find helpful when you're porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="0794a-108">移植プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="0794a-108">Overview of the porting process</span></span>

<span data-ttu-id="0794a-109">プロジェクトを .NET Core に移植する場合は、次の手順を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0794a-109">We recommend you use the following process when porting your project to .NET Core:</span></span>

1. <span data-ttu-id="0794a-110">移植するすべてのプロジェクトを、.NET Framework 4.7.2 以降をターゲットとするように再ターゲットします。</span><span class="sxs-lookup"><span data-stu-id="0794a-110">Retarget all projects you wish to port to target .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="0794a-111">この手順により、.NET Core で特定の API がサポートされない場合に、.NET Framework 固有のターゲットに対して API の代替を確実に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0794a-111">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

2. <span data-ttu-id="0794a-112">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) を使ってアセンブリを分析し、それらが .NET Core に移植可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0794a-112">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and see if they're portable to .NET Core.</span></span>

   <span data-ttu-id="0794a-113">API Portability Analyzer ツールによって、コンパイル済みのアセンブリが分析され、レポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0794a-113">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report.</span></span> <span data-ttu-id="0794a-114">このレポートには、移植性に関する大まかな概要と、使用している API のうち NET Core では利用できないものそれぞれについての内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0794a-114">This report shows a high-level portability summary and a breakdown of each API you're using that isn't available on NET Core.</span></span>

3. <span data-ttu-id="0794a-115">[.NET API アナライザー](../../standard/analyzers/api-analyzer.md)をプロジェクトにインストールして、一部のプラットフォームで <xref:System.PlatformNotSupportedException> をスローする API と、発生する可能性のあるその他の互換性の問題を識別します。</span><span class="sxs-lookup"><span data-stu-id="0794a-115">Install the [.NET API analyzer](../../standard/analyzers/api-analyzer.md) into your projects to identify APIs that throw <xref:System.PlatformNotSupportedException> on some platforms and some other potential compatibility issues.</span></span>

   <span data-ttu-id="0794a-116">このツールは移植性アナライザーに似ていますが、.NET Core 上にコードをビルドできるかどうかが分析されるのではなく、実行時に <xref:System.PlatformNotSupportedException> をスローするような方法で API を使っているかどうかが分析されます。</span><span class="sxs-lookup"><span data-stu-id="0794a-116">This tool is similar to the portability analyzer, but instead of analyzing if code can build on .NET Core, it analyzes whether you're using an API in a way that will throw a <xref:System.PlatformNotSupportedException> at run time.</span></span> <span data-ttu-id="0794a-117">.NET Framework 4.7.2 以上から移行する場合、これは一般的ではありませんが、確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0794a-117">Although this isn't common if you're moving from .NET Framework 4.7.2 or higher, it's good to check.</span></span> <span data-ttu-id="0794a-118">.NET Core で例外をスローする API の詳細については、「[.NET Core で常に例外をスローする API](../compatibility/unsupported-apis.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0794a-118">For more information about APIs that throw exceptions on .NET Core, see [APIs that always throw exceptions on .NET Core](../compatibility/unsupported-apis.md).</span></span>

4. <span data-ttu-id="0794a-119">[Visual Studio の変換ツール](/nuget/consume-packages/migrate-packages-config-to-package-reference)を使用して、すべての `packages.config` の依存関係を [PackageReference](/nuget/consume-packages/package-references-in-project-files) 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="0794a-119">Convert all of your `packages.config` dependencies to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format with the [conversion tool in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span></span>

   <span data-ttu-id="0794a-120">この手順では、依存関係を従来の `packages.config` 形式から変換します。</span><span class="sxs-lookup"><span data-stu-id="0794a-120">This step involves converting your dependencies from the legacy `packages.config` format.</span></span> <span data-ttu-id="0794a-121">`packages.config` は .NET Core では機能しないため、パッケージの依存関係がある場合は、この変換が必須です。</span><span class="sxs-lookup"><span data-stu-id="0794a-121">`packages.config` doesn't work on .NET Core, so this conversion is required if you have package dependencies.</span></span>

5. <span data-ttu-id="0794a-122">.NET Core 用の新しいプロジェクトを作成してソース ファイルをコピーするか、ツールを使って既存のプロジェクト ファイルの変換を試みます。</span><span class="sxs-lookup"><span data-stu-id="0794a-122">Create new projects for .NET Core and copy over source files, or attempt to convert your existing project file with a tool.</span></span>

   <span data-ttu-id="0794a-123">.NET Core では、.NET Framework よりも簡素化された (異なる) [プロジェクト ファイル形式](../tools/csproj.md)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0794a-123">.NET Core uses a simplified (and different) [project file format](../tools/csproj.md) than .NET Framework.</span></span> <span data-ttu-id="0794a-124">続行するには、プロジェクト ファイルをこの形式に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0794a-124">You'll need to convert your project files into this format to continue.</span></span>

6. <span data-ttu-id="0794a-125">テスト コードを移植します。</span><span class="sxs-lookup"><span data-stu-id="0794a-125">Port your test code.</span></span>

   <span data-ttu-id="0794a-126">.NET Core への移植はコードベースにとって大きな変更となるため、テスト プロジェクトを移植して、ご自分のコードの移植時にテストを実行できるようにすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0794a-126">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to port your test projects so that you can run tests as you port your code over.</span></span> <span data-ttu-id="0794a-127">MSTest、xUnit、NUnit はすべて .NET Core で動作します。</span><span class="sxs-lookup"><span data-stu-id="0794a-127">MSTest, xUnit, and NUnit all work on .NET Core.</span></span>

<span data-ttu-id="0794a-128">さらに、[dotnet try-convert](https://github.com/dotnet/try-convert) ツールを使って、より小規模なソリューションや個人のプロジェクトを、1 つの操作で .NET Core プロジェクトのファイル形式に移植してみることが可能です。</span><span class="sxs-lookup"><span data-stu-id="0794a-128">Additionally, you can attempt to port smaller solutions or individual projects in one operation to the .NET Core project file format with the [dotnet try-convert](https://github.com/dotnet/try-convert) tool.</span></span> <span data-ttu-id="0794a-129">`dotnet try-convert` がすべてのプロジェクトに対して動作する保証はありません。また、これが原因となって、依存していた動作に微妙な変更が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0794a-129">`dotnet try-convert` is not guaranteed to work for all your projects, and it may cause subtle changes in behavior that you depended on.</span></span> <span data-ttu-id="0794a-130">これは、自動化できる基本的なことを自動化するための "_開始点_" としてお使いください。</span><span class="sxs-lookup"><span data-stu-id="0794a-130">Use it as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="0794a-131">これは、プロジェクトの移行に対する保証されたソリューションではありません。</span><span class="sxs-lookup"><span data-stu-id="0794a-131">It isn't a guaranteed solution to migrating a project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0794a-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="0794a-132">Next steps</span></span>

>[!div class="nextstepaction"]
>[<span data-ttu-id="0794a-133">依存関係の分析</span><span class="sxs-lookup"><span data-stu-id="0794a-133">Analyze dependencies</span></span>](third-party-deps.md)
