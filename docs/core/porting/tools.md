---
title: .NET Core に移植するためのツール
description: .NET Core への移植に使用できるいくつかのツールに関する詳細情報
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: b8678ec72fe5d910d5f8cff4768106e7496f9276
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406129"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="30ed4-103">.NET Core への移植で役立つツール</span><span class="sxs-lookup"><span data-stu-id="30ed4-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="30ed4-104">この記事に一覧表示されているツールは、移植するときに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="30ed4-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="30ed4-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - .NET Framework と .NET Core の間で、コードを</span><span class="sxs-lookup"><span data-stu-id="30ed4-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="30ed4-106">[コマンド ライン ツール](https://github.com/Microsoft/dotnet-apiport/releases)として</span><span class="sxs-lookup"><span data-stu-id="30ed4-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="30ed4-107">[Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)として、どの程度移植できるかを示すレポートを生成できるツールチェーン。</span><span class="sxs-lookup"><span data-stu-id="30ed4-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="30ed4-108">[プラットフォーム互換性アナライザー](../../standard/analyzers/platform-compat-analyzer.md) - API を使用できない可能性のある呼び出しサイトからプラットフォーム固有の API を使用するときに開発者に通知する Roslyn アナライザーです。</span><span class="sxs-lookup"><span data-stu-id="30ed4-108">[Platform compatibility analyzer](../../standard/analyzers/platform-compat-analyzer.md) - A Roslyn analyzer that informs developers when they use platform-specific APIs from call sites where the API might not be available.</span></span>
- <span data-ttu-id="30ed4-109">[.NET API アナライザー](../../standard/analyzers/api-analyzer.md) - クロスプラットフォームのアプリとライブラリにおいてプラットフォームの互換性に関する問題を検出するのに役立つ Roslyn アナライザー。</span><span class="sxs-lookup"><span data-stu-id="30ed4-109">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that can help detect platform compatibility issues in cross-platform apps and libraries.</span></span>
- <span data-ttu-id="30ed4-110">[try-convert](https://www.nuget.org/packages/try-convert/) - デスクトップ アプリを .NET Core に移動するなど、プロジェクトかソリューション全体を .NET SDK に変換できる .NET Core グローバル ツール。</span><span class="sxs-lookup"><span data-stu-id="30ed4-110">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="30ed4-111">もっと複雑なビルドを確立し (カスタムのタスク、ターゲット、インポートなど)、.NET Core との間で互換性がない多くのプロジェクト タイプが拒否される場合は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="30ed4-111">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
