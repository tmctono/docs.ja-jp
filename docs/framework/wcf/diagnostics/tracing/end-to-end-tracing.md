---
title: エンドツーエンドのトレース
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: fc8fc448bdcf94ab25349f6b34961a34e5ed2a5a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598581"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="a98fe-102">エンドツーエンドのトレース</span><span class="sxs-lookup"><span data-stu-id="a98fe-102">End-to-End Tracing</span></span>
<span data-ttu-id="a98fe-103">エンドツーエンド (e2e) のトレースにより、開発者は、Windows Communication Foundation (WCF) インフラストラクチャでコードの実行に従い、コードパスが失敗した原因を調査したり、容量計画とパフォーマンス分析の詳細なトレースを提供したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a98fe-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="a98fe-104">Windows Communication Foundation (WCF) には、エラーの原因を診断するのに役立つ3つの相関関係メカニズム (アクティビティ、転送、および伝達) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a98fe-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="a98fe-105">エンドツーエンドのトレースシナリオの一覧と、それぞれのアクティビティとトレースの設計については、「[エンドツーエンドのトレースのシナリオ](end-to-end-tracing-scenarios.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a98fe-105">See [End-To-End Tracing Scenarios](end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a98fe-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a98fe-106">In This Section</span></span>  
 <span data-ttu-id="a98fe-107">[アクティビティ](activity.md): WINDOWS COMMUNICATION FOUNDATION (WCF) トレースモデルのアクティビティトレースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a98fe-107">[Activity](activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="a98fe-108">[転送](transfer.md): WINDOWS COMMUNICATION FOUNDATION (WCF) トレースモデルでの転送について説明し、transfer を使用してエンドポイント内のアクティビティを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a98fe-108">[Transfer](transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="a98fe-109">[伝達](propagation.md): WINDOWS COMMUNICATION FOUNDATION (WCF) トレースモデルでのアクティビティの伝達、および伝達を使用したエンドポイント間でのアクティビティの関連付けについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a98fe-109">[Propagation](propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="a98fe-110">トレースの種類の概要</span><span class="sxs-lookup"><span data-stu-id="a98fe-110">Trace Type Summary</span></span>](trace-type-summary.md)  
  
 <span data-ttu-id="a98fe-111">すべてのアクティビティ トレースの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="a98fe-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a98fe-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a98fe-112">See also</span></span>

- [<span data-ttu-id="a98fe-113">トレースの構成</span><span class="sxs-lookup"><span data-stu-id="a98fe-113">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="a98fe-114">サービス トレース ビューアーを使用した相関トレースの表示とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a98fe-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="a98fe-115">エンドツーエンドのトレースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="a98fe-115">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="a98fe-116">サービス トレース ビューアー ツール (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="a98fe-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
