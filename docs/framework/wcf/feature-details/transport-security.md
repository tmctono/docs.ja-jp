---
title: トランスポート セキュリティ
ms.date: 03/30/2017
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
ms.openlocfilehash: 036c3db96a14b6e2be299380f495f54436b5c87d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218967"
---
# <a name="transport-security"></a><span data-ttu-id="c7bd3-102">トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c7bd3-102">Transport Security</span></span>
<span data-ttu-id="c7bd3-103">Windows Communication Foundation (WCF) でのトランスポート セキュリティは、選択したバインドに依存します。</span><span class="sxs-lookup"><span data-stu-id="c7bd3-103">Transport security in Windows Communication Foundation (WCF) depends on the binding selected.</span></span> <span data-ttu-id="c7bd3-104">バインディングが実装するトランスポートによって実際のセキュリティ機構が決まります。</span><span class="sxs-lookup"><span data-stu-id="c7bd3-104">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="c7bd3-105">このセクションの各トピックでは、実装される機構とそのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c7bd3-105">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7bd3-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c7bd3-106">In This Section</span></span>  
 [<span data-ttu-id="c7bd3-107">トランスポート セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="c7bd3-107">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="c7bd3-108">WCF でのトランスポート セキュリティの基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7bd3-108">Explains the basics of transport security in WCF.</span></span>  
  
 [<span data-ttu-id="c7bd3-109">HTTP トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c7bd3-109">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)  
 <span data-ttu-id="c7bd3-110">WCF が (、SSL または HTTPS) の Secure Sockets Layer を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7bd3-110">Explains how WCF implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="c7bd3-111">HTTP 認証の理解</span><span class="sxs-lookup"><span data-stu-id="c7bd3-111">Understanding HTTP Authentication</span></span>](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)  
 <span data-ttu-id="c7bd3-112">HTTP 認証方式 (基本、ダイジェスト、NTLM (NT LAN Manager) など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7bd3-112">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="c7bd3-113">トランスポート セキュリティでの偽装の使用</span><span class="sxs-lookup"><span data-stu-id="c7bd3-113">Using Impersonation with Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)  
 <span data-ttu-id="c7bd3-114">トランスポート セキュリティ モードで使用できる 5 つの偽装レベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c7bd3-114">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="c7bd3-115">方法: SSL 証明書でポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c7bd3-115">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="c7bd3-116">SSL (トランスポート) セキュリティを実現するために、X.509 証明書を使用してコンピューターのポートを構成する際の基本事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7bd3-116">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c7bd3-117">参照</span><span class="sxs-lookup"><span data-stu-id="c7bd3-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="c7bd3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7bd3-118">Related Sections</span></span>  
 [<span data-ttu-id="c7bd3-119">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="c7bd3-119">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7bd3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7bd3-120">See also</span></span>

- [<span data-ttu-id="c7bd3-121">WCF セキュリティのプログラミング</span><span class="sxs-lookup"><span data-stu-id="c7bd3-121">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
