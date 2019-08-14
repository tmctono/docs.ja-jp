---
title: 診断ツールの概要 - .NET Core
description: .NET Core アプリケーションの診断に使用できるツールと手法の概要。
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974150"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="bac60-103">.NET Core で使用できる診断ツール</span><span class="sxs-lookup"><span data-stu-id="bac60-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="bac60-104">ソフトウェアは期待どおりに動作するとは限りませんが、.NET Core には、そのような問題を迅速かつ効果的に診断するために役立つツールと API が用意されています。</span><span class="sxs-lookup"><span data-stu-id="bac60-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="bac60-105">この記事は、必要な各種ツールを見つけるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bac60-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggersmanaged-debuggersmd"></a>[<span data-ttu-id="bac60-106">マネージド デバッガー</span><span class="sxs-lookup"><span data-stu-id="bac60-106">Managed debuggers</span></span>](managed-debuggers.md)
<span data-ttu-id="bac60-107">マネージド デバッガーを使用すると、プログラムと対話することができます。</span><span class="sxs-lookup"><span data-stu-id="bac60-107">Managed debuggers allow you to interact with your program.</span></span> <span data-ttu-id="bac60-108">一時停止、段階的な実行、調査、および再開によって、コードの動作を分析できます。</span><span class="sxs-lookup"><span data-stu-id="bac60-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="bac60-109">デバッガーは、簡単に再現できる機能の問題を診断するための最初の選択肢です。</span><span class="sxs-lookup"><span data-stu-id="bac60-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracinglogging-tracingmd"></a>[<span data-ttu-id="bac60-110">ログとトレース</span><span class="sxs-lookup"><span data-stu-id="bac60-110">Logging and tracing</span></span>](logging-tracing.md)
<span data-ttu-id="bac60-111">ログとトレースは、関連する手法です。</span><span class="sxs-lookup"><span data-stu-id="bac60-111">Logging and tracing are related techniques.</span></span> <span data-ttu-id="bac60-112">ログ ファイルを作成するためのコードのインストルメント化を指します。</span><span class="sxs-lookup"><span data-stu-id="bac60-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="bac60-113">ファイルには、プログラムの機能の詳細が記録されます。</span><span class="sxs-lookup"><span data-stu-id="bac60-113">The files record the details of what a program does.</span></span> <span data-ttu-id="bac60-114">これらの詳細は、複雑度の高い問題を診断するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="bac60-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="bac60-115">タイム スタンプと組み合わせると、これらの手法はパフォーマンスの調査にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bac60-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testingtestingindexmd"></a>[<span data-ttu-id="bac60-116">単体テスト</span><span class="sxs-lookup"><span data-stu-id="bac60-116">Unit testing</span></span>](../testing/index.md)
<span data-ttu-id="bac60-117">単体テストは、高品質のソフトウェアを継続的に統合して展開するための重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="bac60-117">Unit testing is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="bac60-118">単体テストは、何かを中断するときに早期警告を提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bac60-118">Unit tests are designed to give you an early warning when you break something.</span></span>
