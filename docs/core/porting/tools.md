---
title: .NET Core に移植するためのツール
description: .NET Core への移植に使用できるいくつかのツールに関する詳細情報
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 3b71c31b4f26b278b2bd1088adc8e9f64d28ab7b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215194"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="ba037-103">.NET Core への移植で役立つツール</span><span class="sxs-lookup"><span data-stu-id="ba037-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="ba037-104">この記事に一覧表示されているツールは、移植するときに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="ba037-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="ba037-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - .NET Framework と .NET Core の間で、コードを</span><span class="sxs-lookup"><span data-stu-id="ba037-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="ba037-106">[コマンド ライン ツール](https://github.com/Microsoft/dotnet-apiport/releases)として</span><span class="sxs-lookup"><span data-stu-id="ba037-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="ba037-107">[Visual Studio 拡張機能](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)として、どの程度移植できるかを示すレポートを生成できるツールチェーン。</span><span class="sxs-lookup"><span data-stu-id="ba037-107">As a [Visual Studio extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span></span>
- <span data-ttu-id="ba037-108">[.NET API アナライザー](../../standard/analyzers/api-analyzer.md): さまざまなプラットフォームでの C# API の互換性リスクの可能性と、非推奨の API の呼び出しを検出する Roslyn アナライザー。</span><span class="sxs-lookup"><span data-stu-id="ba037-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>

<span data-ttu-id="ba037-109">さらに、[CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) ツールを使って、小規模なソリューションや個々のプロジェクトを .NET Core プロジェクトのファイル形式に移植してみることが可能です。</span><span class="sxs-lookup"><span data-stu-id="ba037-109">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING] 
> <span data-ttu-id="ba037-110">CsprojToVs2017 はサードパーティ製のツールです。</span><span class="sxs-lookup"><span data-stu-id="ba037-110">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="ba037-111">すべてのプロジェクトに対してこれが動作する保証はありません。また、依存している動作に微妙な変更が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ba037-111">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="ba037-112">CsprojToVs2017 は、自動化できる基本的なことを自動化するための "_開始点_" として使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba037-112">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="ba037-113">これは、プロジェクトのファイル形式の移行に対する保証されたソリューションではありません。</span><span class="sxs-lookup"><span data-stu-id="ba037-113">It is not a guaranteed solution to migrating project file formats.</span></span>
