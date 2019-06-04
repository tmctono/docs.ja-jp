---
title: 共通言語ランタイムの ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 441cae712e7338b36e8983f41341b1721770a0bb
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489702"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="7a422-102">共通言語ランタイムの ETW イベント</span><span class="sxs-lookup"><span data-stu-id="7a422-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="7a422-103">共通言語ランタイム (CLR) は、さまざまなデバッグとプロファイリング イベントを通じて、有用な Windows イベント トレーシング (ETW) の診断情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7a422-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="7a422-104">CLR ETW イベントは、Windows ETW トレース システムを利用して、共通言語ランタイムによって提供される既存のプロファイリングとデバッグのサポートを拡張します。</span><span class="sxs-lookup"><span data-stu-id="7a422-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="7a422-105">ETW の詳細については、MSDN で「[Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142)」 (ETW によるデバッグとパフォーマンス チューニングの向上) の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a422-105">More information about ETW is available in the article [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) on MSDN.</span></span> <span data-ttu-id="7a422-106">Xperf に関する情報は、NTDebugging のブログ エントリ「[Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144)」にあります。</span><span class="sxs-lookup"><span data-stu-id="7a422-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="7a422-107">.NET Framework 4 またはそれ以降が、イベントのトピックで説明されているすべてのイベントに対して必要です。</span><span class="sxs-lookup"><span data-stu-id="7a422-107">The .NET Framework 4 or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="7a422-108">Windows Vista オペレーティング システムは、サポートされる最小のクライアントで、Windows Server 2008 は、サポートされる最小のサーバーです。</span><span class="sxs-lookup"><span data-stu-id="7a422-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a422-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7a422-109">In This Section</span></span>  
 [<span data-ttu-id="7a422-110">.NET Framework のログ記録の制御</span><span class="sxs-lookup"><span data-stu-id="7a422-110">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 <span data-ttu-id="7a422-111">ETW イベントをキャプチャおよび表示するためのツールとコマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a422-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="7a422-112">CLR ETW プロバイダー</span><span class="sxs-lookup"><span data-stu-id="7a422-112">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 <span data-ttu-id="7a422-113">ランタイム プロバイダーとランダウン プロバイダーの情報、およびこれらを使用して ETW データを収集する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="7a422-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="7a422-114">CLR ETW キーワードおよびレベル</span><span class="sxs-lookup"><span data-stu-id="7a422-114">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="7a422-115">イベントをカテゴリ別にフィルタ処理できるランタイム プロバイダーとランダウン プロバイダーのキーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a422-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="7a422-116">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="7a422-116">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)  
 <span data-ttu-id="7a422-117">CLR ETW イベント、キーワード、レベル、およびイベント データに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7a422-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a422-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a422-118">See also</span></span>

- [<span data-ttu-id="7a422-119">.NET Framework の ETW イベント</span><span class="sxs-lookup"><span data-stu-id="7a422-119">ETW Events in the .NET Framework</span></span>](../../../docs/framework/performance/etw-events.md)
