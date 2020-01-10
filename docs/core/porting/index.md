---
title: .NET Framework から .NET Core への移植
description: 移植プロセスを理解し、.NET Framework プロジェクトを .NET Core に移植する際に役立つツールを確認します。
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: 3dbd4a1f608d71f28fa507da2e11fc41226664c7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714340"
---
# <a name="overview-of-the-porting-process-from-net-framework-to-net-core"></a><span data-ttu-id="a7709-103">.NET Framework から .NET Core への移植プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="a7709-103">Overview of the porting process from .NET Framework to .NET Core</span></span>

<span data-ttu-id="a7709-104">現在 .NET Framework で実行しているコードの .NET Core への移植を検討する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7709-104">You might have code that currently runs on the .NET Framework that you're interested in porting to .NET Core.</span></span> <span data-ttu-id="a7709-105">この記事では、次について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7709-105">This article provides:</span></span>

* <span data-ttu-id="a7709-106">移植プロセスの概要。</span><span class="sxs-lookup"><span data-stu-id="a7709-106">An overview of the porting process.</span></span>
* <span data-ttu-id="a7709-107">コードを .NET Core に移植するときに役立つツールの一覧。</span><span class="sxs-lookup"><span data-stu-id="a7709-107">A list of the tools you may find helpful when you're porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="a7709-108">移植プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="a7709-108">Overview of the porting process</span></span>

<span data-ttu-id="a7709-109">プロジェクトを .NET Core に移植する場合は、次の手順を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7709-109">We recommend you to use the following process when porting your project to .NET Core:</span></span>

1. <span data-ttu-id="a7709-110">移植するすべてのプロジェクトを、.NET Framework 4.7.2 以降をターゲットとするように再ターゲットします。</span><span class="sxs-lookup"><span data-stu-id="a7709-110">Retarget all projects you wish to port to target the .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="a7709-111">この手順により、.NET Core で特定の API がサポートされない場合に、.NET Framework 固有のターゲットに対して API の代替を確実に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7709-111">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

2. <span data-ttu-id="a7709-112">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) を使ってアセンブリを分析し、それらが .NET Core に移植可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7709-112">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and see if they're portable to .NET Core.</span></span>

   <span data-ttu-id="a7709-113">API Portability Analyzer ツールによって、コンパイル済みのアセンブリが分析され、レポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a7709-113">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report.</span></span> <span data-ttu-id="a7709-114">このレポートには、移植性に関する大まかな概要と、使用している API のうち NET Core では利用できないものそれぞれについての内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7709-114">This report shows a high-level portability summary and a breakdown of each API you're using that isn't available on NET Core.</span></span>

3. <span data-ttu-id="a7709-115">[.NET API アナライザー](../../standard/analyzers/api-analyzer.md)をプロジェクトにインストールして、一部のプラットフォームで <xref:System.PlatformNotSupportedException> をスローする API と、発生する可能性のあるその他の互換性の問題を識別します。</span><span class="sxs-lookup"><span data-stu-id="a7709-115">Install the [.NET API analyzer](../../standard/analyzers/api-analyzer.md) into your projects to identify APIs throwing <xref:System.PlatformNotSupportedException> on some platforms and some other potential compatibility issues.</span></span>

   <span data-ttu-id="a7709-116">このツールは移植性アナライザーに似ていますが、.NET Core 上にビルドできるかどうかが分析される代わりに、実行時に <xref:System.PlatformNotSupportedException> をスローするような方法で API を使っているかどうかが分析されます。</span><span class="sxs-lookup"><span data-stu-id="a7709-116">This tool is similar to the portability analyzer, but instead of analyzing if things can build on .NET Core, it will analyze if you're using an API in a way that will throw the <xref:System.PlatformNotSupportedException> at runtime.</span></span> <span data-ttu-id="a7709-117">.NET Framework 4.7.2 以上から移行する場合、これは一般的ではありませんが、確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7709-117">Although this isn't common if you're moving from .NET Framework 4.7.2 or higher, it's good to check.</span></span>

4. <span data-ttu-id="a7709-118">[Visual Studio の変換ツール](/nuget/consume-packages/migrate-packages-config-to-package-reference)を使用して、すべての `packages.config` の依存関係を [PackageReference](/nuget/consume-packages/package-references-in-project-files) 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="a7709-118">Convert all of your `packages.config` dependencies to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format with the [conversion tool in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span></span>

   <span data-ttu-id="a7709-119">この手順では、依存関係を従来の `packages.config` 形式から変換します。</span><span class="sxs-lookup"><span data-stu-id="a7709-119">This step involves converting your dependencies from the legacy `packages.config` format.</span></span> <span data-ttu-id="a7709-120">`packages.config` は .NET Core では機能しないため、パッケージの依存関係がある場合は、この変換が必須です。</span><span class="sxs-lookup"><span data-stu-id="a7709-120">`packages.config` doesn't work on .NET Core, so this conversion is required if you have package dependencies.</span></span>

5. <span data-ttu-id="a7709-121">.NET Core 用の新しいプロジェクトを作成してソース ファイルをコピーするか、ツールを使って既存のプロジェクト ファイルの変換を試みます。</span><span class="sxs-lookup"><span data-stu-id="a7709-121">Create new projects for .NET Core and copy over source files, or attempt to convert your existing project file with a tool.</span></span>

   <span data-ttu-id="a7709-122">.NET Core では、.NET Framework よりも簡素化された (異なる) [プロジェクト ファイル形式](../tools/csproj.md)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7709-122">.NET Core uses a simplified (and different) [project file format](../tools/csproj.md) than .NET Framework.</span></span> <span data-ttu-id="a7709-123">続行するには、プロジェクト ファイルをこの形式に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7709-123">You'll need to convert your project files into this format to continue.</span></span>

6. <span data-ttu-id="a7709-124">テスト コードを移植します。</span><span class="sxs-lookup"><span data-stu-id="a7709-124">Port your test code.</span></span>

   <span data-ttu-id="a7709-125">.NET Core への移植はコードベースにとって大きな変更となるため、コードの移植時にテストを実行できるように、テストを移植することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7709-125">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to get your tests ported, so that you can run tests as you port your code over.</span></span> <span data-ttu-id="a7709-126">MSTest、xUnit、NUnit はすべて .NET Core で動作します。</span><span class="sxs-lookup"><span data-stu-id="a7709-126">MSTest, xUnit, and NUnit all work on .NET Core.</span></span>

<span data-ttu-id="a7709-127">さらに、[dotnet try-convert](https://github.com/dotnet/try-convert) ツールを使って、より小規模なソリューションや個人のプロジェクトを、1 つの操作で .NET Core プロジェクトのファイル形式に移植してみることが可能です。</span><span class="sxs-lookup"><span data-stu-id="a7709-127">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [dotnet try-convert](https://github.com/dotnet/try-convert) tool in one operation.</span></span> <span data-ttu-id="a7709-128">`dotnet try-convert` がすべてのプロジェクトに対して動作する保証はありません。また、依存していた動作に微妙な変更が生じる原因となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7709-128">`dotnet try-convert` is not guaranteed to work for all your projects, and it may cause subtle changes in behavior that you may find that you depended on.</span></span> <span data-ttu-id="a7709-129">これは、自動化できる基本的なことを自動化するための "_開始点_" として使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7709-129">It should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="a7709-130">これは、プロジェクトの移行に対する保証されたソリューションではありません。</span><span class="sxs-lookup"><span data-stu-id="a7709-130">It isn't a guaranteed solution to migrating a project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="a7709-131">次へ</span><span class="sxs-lookup"><span data-stu-id="a7709-131">Next</span></span>](net-framework-tech-unavailable.md)
