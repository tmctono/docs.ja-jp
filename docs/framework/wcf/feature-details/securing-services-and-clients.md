---
title: サービスおよびクライアントのセキュリティ保護
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: e455c7a48e1484d5acdcc5f6cdc9098997a3ba83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120732"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="5a9e7-102">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="5a9e7-102">Securing Services and Clients</span></span>
<span data-ttu-id="5a9e7-103">このセクションの情報は、Windows Communication Foundation (WCF) のセキュリティのプログラミングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5a9e7-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="5a9e7-104">一般に、これには、システムが提供する適切なバインディングを選択すること、セキュリティ要素のプロパティを適切に設定すること、サービス側/クライアント側で使う資格情報の検索方法にまつわる、サービスの動作に関するプロパティを適切に設定することなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a9e7-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="5a9e7-105">ように、これらの手法はほとんどのシナリオでは、ほとんどのユーザーのセキュリティ要件をカバー[一般的なセキュリティ シナリオ](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)します。</span><span class="sxs-lookup"><span data-stu-id="5a9e7-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="5a9e7-106">実際のシナリオでは、多くの機能が必要とする場合が初めて表示[カスタム バインドを使用したセキュリティ機能](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); ソリューションは、明らかなかどうかは、次を参照してください。[拡張セキュリティ](../../../../docs/framework/wcf/extending/extending-security.md)。</span><span class="sxs-lookup"><span data-stu-id="5a9e7-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="5a9e7-107">作成 (またはとの相互運用) に多様なクレームを使用するシステムでは、トピックを参照して[承認](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)します。</span><span class="sxs-lookup"><span data-stu-id="5a9e7-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a9e7-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5a9e7-108">In This Section</span></span>  
 [<span data-ttu-id="5a9e7-109">WCF セキュリティのプログラミング</span><span class="sxs-lookup"><span data-stu-id="5a9e7-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="5a9e7-110">メッセージを保護するために使うプログラミング モデルの概要</span><span class="sxs-lookup"><span data-stu-id="5a9e7-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="5a9e7-111">トランスポート セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="5a9e7-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="5a9e7-112">トランスポート層を介してやり取りするメッセージを保護する方法の概要</span><span class="sxs-lookup"><span data-stu-id="5a9e7-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="5a9e7-113">メッセージのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="5a9e7-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="5a9e7-114">Windows Communication Foundation (WCF) メッセージ レベルのセキュリティを使用する理由をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="5a9e7-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="5a9e7-115">セキュリティで保護されたセッション</span><span class="sxs-lookup"><span data-stu-id="5a9e7-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="5a9e7-116">WCF のセッションをセキュリティで保護するときに必要な考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a9e7-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="5a9e7-117">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="5a9e7-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="5a9e7-118">X.509 証明書を使用する際に必要となる主なタスクの解説</span><span class="sxs-lookup"><span data-stu-id="5a9e7-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5a9e7-119">参照</span><span class="sxs-lookup"><span data-stu-id="5a9e7-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="5a9e7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a9e7-120">Related Sections</span></span>  
 [<span data-ttu-id="5a9e7-121">セキュリティの概念</span><span class="sxs-lookup"><span data-stu-id="5a9e7-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="5a9e7-122">セキュリティの拡張</span><span class="sxs-lookup"><span data-stu-id="5a9e7-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="5a9e7-123">一般的なセキュリティ シナリオ</span><span class="sxs-lookup"><span data-stu-id="5a9e7-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="5a9e7-124">バインディングとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="5a9e7-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="5a9e7-125">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="5a9e7-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="5a9e7-126">セキュリティの拡張</span><span class="sxs-lookup"><span data-stu-id="5a9e7-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="5a9e7-127">承認</span><span class="sxs-lookup"><span data-stu-id="5a9e7-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="5a9e7-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a9e7-128">See also</span></span>

- [<span data-ttu-id="5a9e7-129">基本的な WCF プログラミング</span><span class="sxs-lookup"><span data-stu-id="5a9e7-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="5a9e7-130">Windows Server AppFabric のセキュリティ モデル</span><span class="sxs-lookup"><span data-stu-id="5a9e7-130">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
