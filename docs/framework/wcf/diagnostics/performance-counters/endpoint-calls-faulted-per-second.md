---
title: 'エンドポイント : 1 秒あたりの失敗した呼び出し'
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: ead4b074748307f30d16557c3359f730880595da
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163541"
---
# <a name="endpoint-calls-faulted-per-second"></a><span data-ttu-id="c102a-102">エンドポイント : 1 秒あたりの失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="c102a-102">Endpoint: Calls Faulted Per Second</span></span>
<span data-ttu-id="c102a-103">カウンター名 : 1 秒あたりの失敗した呼び出し。</span><span class="sxs-lookup"><span data-stu-id="c102a-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c102a-104">説明</span><span class="sxs-lookup"><span data-stu-id="c102a-104">Description</span></span>  
 <span data-ttu-id="c102a-105">このエンドポイントの呼び出しのうち、エラーを返したものの 1 秒あたりの回数です。</span><span class="sxs-lookup"><span data-stu-id="c102a-105">Number of calls that have returned faults to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="c102a-106">このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="c102a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c102a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="c102a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="c102a-108">Windows Communication Foundation (WCF) アプリケーションでは、サービスメソッドは SOAP エラーメッセージを使用して処理エラー情報を通信します。</span><span class="sxs-lookup"><span data-stu-id="c102a-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="c102a-109">SOAP エラーは、サービス操作のメタデータに含まれるメッセージ型であり、堅牢かつインタラクティブに実行できるようにクライアントが使用するエラー コントラクトを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c102a-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="c102a-110">SOAP エラーは XML 形式でクライアントに渡されるので、相互運用性の面でも優れています。</span><span class="sxs-lookup"><span data-stu-id="c102a-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c102a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c102a-111">See also</span></span>

- [<span data-ttu-id="c102a-112">コントラクトおよびサービスのエラーの指定と処理</span><span class="sxs-lookup"><span data-stu-id="c102a-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
