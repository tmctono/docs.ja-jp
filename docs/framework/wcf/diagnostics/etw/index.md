---
title: ETW を使用した分析トレース
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: dd745730ca186b9489c547f790c546e95bf96372
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798091"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="c4b79-102">ETW を使用した分析トレース</span><span class="sxs-lookup"><span data-stu-id="c4b79-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="c4b79-103">Windows Communication Foundation (WCF) 分析トレースには、WCF サービスの実行中に診断情報をキャプチャする方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="c4b79-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="c4b79-104">Wcf 分析トレースイベントは、運用環境での WCF サービスのトラブルシューティングを可能にするために、WCF スタックの主要なポイントで生成されます。</span><span class="sxs-lookup"><span data-stu-id="c4b79-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="c4b79-105">Wcf サービスの分析トレースは、wcf サービスをホスト[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]する製品サーバーのパフォーマンスにほとんど影響を与えません。これらのイベントは、Windows イベントトレーシング (ETW) セッションに非常に効率的に出力されるためです。</span><span class="sxs-lookup"><span data-stu-id="c4b79-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4b79-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c4b79-106">In This Section</span></span>  
 [<span data-ttu-id="c4b79-107">分析トレースの概要</span><span class="sxs-lookup"><span data-stu-id="c4b79-107">Analytic Tracing Overview</span></span>](analytic-tracing-overview.md)  
 <span data-ttu-id="c4b79-108">での WCF 分析トレースの動作[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4b79-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="c4b79-109">分析トレースの動的な有効化</span><span class="sxs-lookup"><span data-stu-id="c4b79-109">Dynamically Enabling Analytic Tracing</span></span>](dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="c4b79-110">ETW を使用してトレースを動的に有効化または無効化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4b79-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="c4b79-111">メッセージ フローのトレースの構成</span><span class="sxs-lookup"><span data-stu-id="c4b79-111">Configuring Message Flow Tracing</span></span>](configuring-message-flow-tracing.md)  
 <span data-ttu-id="c4b79-112">メッセージ フローのトレースを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4b79-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="c4b79-113">分析トレース イベント リファレンス</span><span class="sxs-lookup"><span data-stu-id="c4b79-113">Analytic Trace Event Reference</span></span>](analytic-trace-event-reference.md)  
 <span data-ttu-id="c4b79-114">イベント ID とそれらのイベント レベル、イベント メッセージ、およびキーワードを表で示します。</span><span class="sxs-lookup"><span data-stu-id="c4b79-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b79-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4b79-115">See also</span></span>

- [<span data-ttu-id="c4b79-116">WCF サービスと Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="c4b79-116">WCF Services and Event Tracing for Windows</span></span>](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="c4b79-117">Windows のイベント トレースへの追跡イベント</span><span class="sxs-lookup"><span data-stu-id="c4b79-117">Tracking Events into Event Tracing in Windows</span></span>](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
