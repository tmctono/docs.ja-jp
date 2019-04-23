---
title: Roslyn ベースのアナライザー - .NET
description: 問題を検出し、各問題について修正を提案する Roslyn ベースのアナライザーについて説明します。
author: billwagner
ms.author: wiwagn
ms.date: 01/24/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 436cfb3904f0891f8c18bb5890563a13d65e2d1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003055"
---
# <a name="the-roslyn-based-analyzers"></a><span data-ttu-id="cb948-103">Roslyn ベースのアナライザー</span><span class="sxs-lookup"><span data-stu-id="cb948-103">The Roslyn based Analyzers</span></span>

<span data-ttu-id="cb948-104">Roslyn ベースのアナライザーでは、.NET Compiler SDK (Roslyn の API) を使用して、プロジェクトのソース コードを分析し、問題の検出と修正の提案を行います。</span><span class="sxs-lookup"><span data-stu-id="cb948-104">Roslyn-based analyzers use the .NET Compiler SDK (Roslyn APIs) to analyze your project's source code to find issues and suggest corrections.</span></span> <span data-ttu-id="cb948-105">検出する問題のクラスは、バグを起こしやすい慣習から API の互換性に関するセキュリティの問題まで、アナライザーによってさまざまです。</span><span class="sxs-lookup"><span data-stu-id="cb948-105">Different analyzers look for different classes of issues, ranging from practices that are likely to cause bugs to security concerns to API compatibility.</span></span>

<span data-ttu-id="cb948-106">Roslyn ベースのアナライザーは対話型であり、ビルド中にも動作します。</span><span class="sxs-lookup"><span data-stu-id="cb948-106">Roslyn-based analyzers work both interactively and during builds.</span></span> <span data-ttu-id="cb948-107">Visual Studio またはコマンド ラインからビルドする際に、アナライザーはさまざまなガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cb948-107">The analyzer provides different guidance when in Visual Studio or in command-line builds.</span></span>

<span data-ttu-id="cb948-108">Visual Studio でコードを編集する場合、コードを変更するとアナライザーが実行され、問題を含むコードの作成後すぐに考えられる問題がキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="cb948-108">While you edit code in Visual Studio, the analyzers run as you make changes, catching possible issues as soon as you create code that trigger concerns.</span></span> <span data-ttu-id="cb948-109">すべての問題は波線で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb948-109">Any issues are highlighted with squiggles under any issue.</span></span> <span data-ttu-id="cb948-110">Visual Studio に表示される電球をクリックすると、その問題に対して考えられる修正方法がアナライザーによって提案されます。</span><span class="sxs-lookup"><span data-stu-id="cb948-110">Visual Studio displays a light bulb, and when you click on it the analyzer will suggest possible fixes for that issue.</span></span> <span data-ttu-id="cb948-111">Visual Studio またはコマンド ラインでプロジェクトをビルドすると、すべてのソース コードが分析され、潜在的な問題の全リストがアナライザーによって示されます。</span><span class="sxs-lookup"><span data-stu-id="cb948-111">When you build the project, either in Visual Studio or from the command line, all the source code is analyzed and the analyzer provides a full list of potential issues.</span></span> <span data-ttu-id="cb948-112">次の図に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cb948-112">The following figure shows one example.</span></span>

![フレームワーク アナライザーによって報告される問題](./media/framework-analyzers-2.png)

<span data-ttu-id="cb948-114">Roslyn ベースのアナライザーでは、エラー、警告、または問題の重大度に基づく情報として、潜在的な問題が報告されます。</span><span class="sxs-lookup"><span data-stu-id="cb948-114">Roslyn-based analyzers report potential issues as errors, warnings, or information based on the severity of the issue.</span></span>

<span data-ttu-id="cb948-115">Roslyn ベースのアナライザーは、プロジェクト内に NuGet パッケージとしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb948-115">You install Roslyn-based analyzers as NuGet packages in your project.</span></span> <span data-ttu-id="cb948-116">構成されたアナライザーと各アナライザーに対するすべての設定は復元され、そのプロジェクト用の任意の開発者のマシンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="cb948-116">The configured analyzers and any settings for each analyzer are restored and run on any developer's machine for that project.</span></span>

> [!NOTE]
> <span data-ttu-id="cb948-117">Roslyn ベースのアナライザーのユーザー エクスペリエンスは、FxCop の旧バージョンのようなコード分析ライブラリや、セキュリティ分析ツールとは異なるものです。</span><span class="sxs-lookup"><span data-stu-id="cb948-117">The user experience for Roslyn-based analyzers is different than that of the Code Analysis libraries like the older versions of FxCop and the security analysis tools.</span></span>  <span data-ttu-id="cb948-118">明示的に Roslyn ベースのアナライザーを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cb948-118">You don't need to explicitly run the Roslyn-based analyzers.</span></span> <span data-ttu-id="cb948-119">Visual Studio の [分析] メニューで [コード分析の実行] メニュー項目を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cb948-119">There's no need to use the "Run Code Analysis" menu items on the "Analyze" menu in Visual Studio.</span></span> <span data-ttu-id="cb948-120">Roslyn ベースのアナライザーは、ユーザーの作業と同期して実行されます。</span><span class="sxs-lookup"><span data-stu-id="cb948-120">Roslyn-based analyzers run asynchronously as you work.</span></span>

## <a name="more-information-on-specific-analyzers"></a><span data-ttu-id="cb948-121">特定のアナライザーについての詳細</span><span class="sxs-lookup"><span data-stu-id="cb948-121">More information on specific analyzers</span></span>

<span data-ttu-id="cb948-122">このセクションでは、次のアナライザーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cb948-122">The following analyzers are covered in this section:</span></span>

* <span data-ttu-id="cb948-123">[API アナライザー](api-analyzer.md): このアナライザーでは、コードの互換性の潜在的リスクや、非推奨の API の使用が調べられます。</span><span class="sxs-lookup"><span data-stu-id="cb948-123">[API Analyzer](api-analyzer.md): This analyzer examines your code for potential compatibility risks or uses of deprecated APIs.</span></span>
* <span data-ttu-id="cb948-124">[フレームワーク アナライザー](framework-analyzer.md): このアナライザーでは、コードが .NET Framework アプリケーションのガイドラインに従っているかどうかが調べられます。</span><span class="sxs-lookup"><span data-stu-id="cb948-124">[Framework Analyzer](framework-analyzer.md): This analyzer examines your code to ensure it follows the guidelines for .NET Framework applications.</span></span> <span data-ttu-id="cb948-125">これらの規則には、セキュリティに基づく推奨事項がいくつか含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb948-125">These rules include several security-based recommendations.</span></span>
* <span data-ttu-id="cb948-126">[.NET Portability Analyzer](portability-analyzer.md): このアナライザーでは、コードを調べて、アプリケーションと他の .NET の実装やプロファイル (.NET Core、.NET Standard、UWP、Xamarin for iOS、Android、Mac など) との互換性を確保するために必要な作業量を確認します。</span><span class="sxs-lookup"><span data-stu-id="cb948-126">[.NET Portability Analyzer](portability-analyzer.md): This analyzer examines your code to see how much work is required to make your application compatible with other .NET implementations and profiles, including .NET Core, .NET Standard, UWP, and Xamarin for iOS, Android, and Mac.</span></span>
