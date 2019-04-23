---
title: セキュリティ ネゴシエーションとタイムアウト
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: a02c9d7b42eadf9a5ce9af8022fe292d6c23249c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180649"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="96061-102">セキュリティ ネゴシエーションとタイムアウト</span><span class="sxs-lookup"><span data-stu-id="96061-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="96061-103">クライアントとサービスの認証と Windows Communication Foundation (WCF) には、認証の一部としてサービス資格情報をネゴシエートする場所のモードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="96061-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="96061-104">このようなシナリオでは、サービス資格情報をクライアントに反映させるために、クライアントとサービスの間でマルチレッグ交換が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96061-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="96061-105"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> プロパティは、マルチレッグ交換の完了に要する時間を制御します。</span><span class="sxs-lookup"><span data-stu-id="96061-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="96061-106">ただし、このタイムアウトは、実際に、単一の要求 - 応答よりも長い時間が交換にかかる場合のみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="96061-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="96061-107">単一のラウンド トリップでネゴシエーションが完了する場合、このタイムアウトは適用されません。</span><span class="sxs-lookup"><span data-stu-id="96061-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96061-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="96061-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="96061-109">方法: 最大クロックのずれを設定</span><span class="sxs-lookup"><span data-stu-id="96061-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
