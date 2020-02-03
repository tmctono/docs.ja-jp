---
title: サービスおよびクライアントのセキュリティ保護
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: 719ab26198bd7b83310025e03e541fa11b109612
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746417"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="b9c4b-102">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="b9c4b-102">Securing Services and Clients</span></span>
<span data-ttu-id="b9c4b-103">このセクションの情報は、Windows Communication Foundation (WCF) でのセキュリティのプログラミングに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="b9c4b-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="b9c4b-104">一般に、これには、システムが提供する適切なバインディングを選択すること、セキュリティ要素のプロパティを適切に設定すること、サービス側/クライアント側で使う資格情報の検索方法にまつわる、サービスの動作に関するプロパティを適切に設定することなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9c4b-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="b9c4b-105">これらの手法は、[一般的なセキュリティシナリオ](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)に示すように、ほとんどのシナリオでほとんどのユーザーのセキュリティ要件に対応しています。</span><span class="sxs-lookup"><span data-stu-id="b9c4b-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="b9c4b-106">シナリオにより多くの機能が必要な場合は、まず「[カスタムバインドを使用したセキュリティ機能](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)」を参照してください。ソリューションが明らかでない場合は、「[セキュリティの拡張](../../../../docs/framework/wcf/extending/extending-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9c4b-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="b9c4b-107">豊富な信頼性情報を使用するシステムを作成 (または相互運用) する場合は、「[承認](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9c4b-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9c4b-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b9c4b-108">In This Section</span></span>  
 [<span data-ttu-id="b9c4b-109">WCF セキュリティのプログラミング</span><span class="sxs-lookup"><span data-stu-id="b9c4b-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="b9c4b-110">メッセージを保護するために使うプログラミング モデルの概要</span><span class="sxs-lookup"><span data-stu-id="b9c4b-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="b9c4b-111">トランスポート セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="b9c4b-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="b9c4b-112">トランスポート層を介してやり取りするメッセージを保護する方法の概要</span><span class="sxs-lookup"><span data-stu-id="b9c4b-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="b9c4b-113">メッセージのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="b9c4b-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="b9c4b-114">Windows Communication Foundation (WCF) でメッセージレベルのセキュリティを使用する理由の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b9c4b-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="b9c4b-115">セキュリティで保護されたセッション</span><span class="sxs-lookup"><span data-stu-id="b9c4b-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="b9c4b-116">WCF セッションをセキュリティで保護する場合に必要な考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9c4b-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="b9c4b-117">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="b9c4b-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="b9c4b-118">X.509 証明書を使用する際に必要となる主なタスクの解説</span><span class="sxs-lookup"><span data-stu-id="b9c4b-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b9c4b-119">リファレンス</span><span class="sxs-lookup"><span data-stu-id="b9c4b-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="b9c4b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9c4b-120">Related Sections</span></span>  
 [<span data-ttu-id="b9c4b-121">セキュリティの概念</span><span class="sxs-lookup"><span data-stu-id="b9c4b-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="b9c4b-122">セキュリティの拡張</span><span class="sxs-lookup"><span data-stu-id="b9c4b-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="b9c4b-123">一般的なセキュリティ シナリオ</span><span class="sxs-lookup"><span data-stu-id="b9c4b-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="b9c4b-124">バインディングとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="b9c4b-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="b9c4b-125">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="b9c4b-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="b9c4b-126">セキュリティの拡張</span><span class="sxs-lookup"><span data-stu-id="b9c4b-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="b9c4b-127">承認</span><span class="sxs-lookup"><span data-stu-id="b9c4b-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="b9c4b-128">参照</span><span class="sxs-lookup"><span data-stu-id="b9c4b-128">See also</span></span>

- [<span data-ttu-id="b9c4b-129">基本的な WCF プログラミング</span><span class="sxs-lookup"><span data-stu-id="b9c4b-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- <span data-ttu-id="b9c4b-130">[Windows Server App Fabric のセキュリティモデル](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b9c4b-130">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
