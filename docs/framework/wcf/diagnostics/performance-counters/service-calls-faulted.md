---
title: 'サービス : 失敗した呼び出し'
ms.date: 03/30/2017
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
ms.openlocfilehash: d02139bcd6540fb973e0f1040c8877c04addc2f4
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321428"
---
# <a name="service-calls-faulted"></a><span data-ttu-id="3c9e3-102">サービス : 失敗した呼び出し</span><span class="sxs-lookup"><span data-stu-id="3c9e3-102">Service: Calls Faulted</span></span>
<span data-ttu-id="3c9e3-103">カウンター名 : 失敗した呼び出し。</span><span class="sxs-lookup"><span data-stu-id="3c9e3-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3c9e3-104">説明</span><span class="sxs-lookup"><span data-stu-id="3c9e3-104">Description</span></span>  
 <span data-ttu-id="3c9e3-105">このサービスの呼び出しのうち、エラーとなったものの回数です。</span><span class="sxs-lookup"><span data-stu-id="3c9e3-105">Number of calls to this service that have returned faults.</span></span> <span data-ttu-id="3c9e3-106">Windows Communication Foundation (WCF) アプリケーションでは、サービスメソッドは SOAP エラーメッセージを使用して処理エラー情報を通信します。</span><span class="sxs-lookup"><span data-stu-id="3c9e3-106">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="3c9e3-107">SOAP エラーは、サービス操作のメタデータに含まれるメッセージ型であり、堅牢かつインタラクティブに実行できるようにクライアントが使用するエラー コントラクトを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c9e3-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="3c9e3-108">SOAP エラーは XML 形式でクライアントに渡されるので、相互運用性の面でも優れています。</span><span class="sxs-lookup"><span data-stu-id="3c9e3-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9e3-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c9e3-109">See also</span></span>

- [<span data-ttu-id="3c9e3-110">コントラクトおよびサービスのエラーの指定と処理</span><span class="sxs-lookup"><span data-stu-id="3c9e3-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
