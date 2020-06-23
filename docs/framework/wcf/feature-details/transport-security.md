---
title: トランスポート セキュリティ
description: これらの参照を使用して、WFC のトランスポートセキュリティメカニズム、実装方法、およびそれらのオプションについて理解します。
ms.date: 03/30/2017
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
ms.openlocfilehash: d39aa49906b79b9e12eecf04629080863719f986
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244752"
---
# <a name="transport-security"></a><span data-ttu-id="8cd4f-103">トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8cd4f-103">Transport Security</span></span>
<span data-ttu-id="8cd4f-104">Windows Communication Foundation (WCF) のトランスポートセキュリティは、選択したバインディングによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8cd4f-104">Transport security in Windows Communication Foundation (WCF) depends on the binding selected.</span></span> <span data-ttu-id="8cd4f-105">バインディングが実装するトランスポートによって実際のセキュリティ機構が決まります。</span><span class="sxs-lookup"><span data-stu-id="8cd4f-105">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="8cd4f-106">このセクションの各トピックでは、実装される機構とそのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8cd4f-106">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8cd4f-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8cd4f-107">In This Section</span></span>  
 [<span data-ttu-id="8cd4f-108">トランスポート セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="8cd4f-108">Transport Security Overview</span></span>](transport-security-overview.md)  
 <span data-ttu-id="8cd4f-109">WCF でのトランスポートセキュリティの基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cd4f-109">Explains the basics of transport security in WCF.</span></span>  
  
 [<span data-ttu-id="8cd4f-110">HTTP トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8cd4f-110">HTTP Transport Security</span></span>](http-transport-security.md)  
 <span data-ttu-id="8cd4f-111">WCF が Secure Sockets Layer (SSL または HTTPS) を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cd4f-111">Explains how WCF implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="8cd4f-112">HTTP 認証の理解</span><span class="sxs-lookup"><span data-stu-id="8cd4f-112">Understanding HTTP Authentication</span></span>](understanding-http-authentication.md)  
 <span data-ttu-id="8cd4f-113">HTTP 認証方式 (基本、ダイジェスト、NTLM (NT LAN Manager) など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cd4f-113">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="8cd4f-114">トランスポート セキュリティでの偽装の使用</span><span class="sxs-lookup"><span data-stu-id="8cd4f-114">Using Impersonation with Transport Security</span></span>](using-impersonation-with-transport-security.md)  
 <span data-ttu-id="8cd4f-115">トランスポート セキュリティ モードで使用できる 5 つの偽装レベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8cd4f-115">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="8cd4f-116">方法: SSL 証明書を使用してポートを構成する</span><span class="sxs-lookup"><span data-stu-id="8cd4f-116">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="8cd4f-117">SSL (トランスポート) セキュリティを実現するために、X.509 証明書を使用してコンピューターのポートを構成する際の基本事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cd4f-117">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8cd4f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cd4f-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="8cd4f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cd4f-119">Related Sections</span></span>  
 [<span data-ttu-id="8cd4f-120">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="8cd4f-120">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="8cd4f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cd4f-121">See also</span></span>

- [<span data-ttu-id="8cd4f-122">WCF セキュリティのプログラミング</span><span class="sxs-lookup"><span data-stu-id="8cd4f-122">Programming WCF Security</span></span>](programming-wcf-security.md)
