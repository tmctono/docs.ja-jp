---
title: .NET Core に移植するためのツール
description: .NET Core への移植に使用できるいくつかのツールに関する詳細情報
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: d0cf0abf206950beb34556ca3ba7243d8cad241e
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795587"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="882a2-103">.NET Core への移植で役立つツール</span><span class="sxs-lookup"><span data-stu-id="882a2-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="882a2-104">この記事に一覧表示されているツールは、移植するときに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="882a2-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="882a2-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - .NET Framework と .NET Core の間で、コードを</span><span class="sxs-lookup"><span data-stu-id="882a2-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="882a2-106">[コマンド ライン ツール](https://github.com/Microsoft/dotnet-apiport/releases)として</span><span class="sxs-lookup"><span data-stu-id="882a2-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="882a2-107">[Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)として、どの程度移植できるかを示すレポートを生成できるツールチェーン。</span><span class="sxs-lookup"><span data-stu-id="882a2-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="882a2-108">[.NET API アナライザー](../../standard/analyzers/api-analyzer.md): さまざまなプラットフォームでの C# API の互換性リスクの可能性と、非推奨の API の呼び出しを検出する Roslyn アナライザー。</span><span class="sxs-lookup"><span data-stu-id="882a2-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>
- <span data-ttu-id="882a2-109">[try-convert](https://www.nuget.org/packages/try-convert/) - デスクトップ アプリを .NET Core に移動するなど、プロジェクトかソリューション全体を .NET SDK に変換できる .NET Core グローバル ツール。</span><span class="sxs-lookup"><span data-stu-id="882a2-109">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="882a2-110">もっと複雑なビルドを確立し (カスタムのタスク、ターゲット、インポートなど)、.NET Core との間で互換性がない多くのプロジェクト タイプが拒否される場合は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="882a2-110">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
