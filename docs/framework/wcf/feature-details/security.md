---
title: Windows Communication Foundation セキュリティ
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 58bec40f197dd1f2b104607a65c3ad456b95f69d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118197"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="49b8b-102">Windows Communication Foundation セキュリティ</span><span class="sxs-lookup"><span data-stu-id="49b8b-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="49b8b-103">このセクションのトピックでは、Windows Communication Foundation (WCF) のセキュリティ機能とそれらを使用してメッセージをセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="49b8b-104">Windows Server AppFabric およびセキュリティの詳細については、次を参照してください[Windows Server AppFabric のセキュリティ モデル。](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="49b8b-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49b8b-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="49b8b-105">In This Section</span></span>  
 [<span data-ttu-id="49b8b-106">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="49b8b-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="49b8b-107">WCF のセキュリティ機能をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="49b8b-108">セキュリティの概念</span><span class="sxs-lookup"><span data-stu-id="49b8b-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="49b8b-109">基本的な用語と WCF のセキュリティに使用される概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="49b8b-110">一般的なセキュリティ シナリオ</span><span class="sxs-lookup"><span data-stu-id="49b8b-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="49b8b-111">シナリオと WCF を構成することができますトポロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="49b8b-112">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="49b8b-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="49b8b-113">資格情報の設定など、セキュリティに影響する WCF の動作に関する概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="49b8b-114">バインディングとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="49b8b-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="49b8b-115">カスタム セキュリティ バインディングの作成方法を示すトピックなど、バインディングをセキュリティの観点から説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="49b8b-116">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="49b8b-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="49b8b-117">WCF セキュリティ機能を使用してメッセージをセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="49b8b-118">認証</span><span class="sxs-lookup"><span data-stu-id="49b8b-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="49b8b-119">一般的な認証タスクを示します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="49b8b-120">承認</span><span class="sxs-lookup"><span data-stu-id="49b8b-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="49b8b-121">セキュリティ実装を使用した一般的な承認シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="49b8b-122">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="49b8b-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="49b8b-123">フェデレーションの基本事項と、フェデレーション サーバーと通信するクライアントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="49b8b-124">部分信頼</span><span class="sxs-lookup"><span data-stu-id="49b8b-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="49b8b-125">部分的に信頼されたを実行している場合は、部分的に信頼のシナリオと WCF の制限事項を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="49b8b-126">監査</span><span class="sxs-lookup"><span data-stu-id="49b8b-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="49b8b-127">セキュリティ イベントを監査する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="49b8b-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="49b8b-128">セキュリティ ガイドラインとベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="49b8b-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="49b8b-129">セキュリティで保護された WCF アプリケーションの作成に関するガイドラインです。</span><span class="sxs-lookup"><span data-stu-id="49b8b-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="49b8b-130">参照</span><span class="sxs-lookup"><span data-stu-id="49b8b-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="49b8b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="49b8b-131">Related Sections</span></span>  
 [<span data-ttu-id="49b8b-132">WCF 機能の詳細</span><span class="sxs-lookup"><span data-stu-id="49b8b-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="49b8b-133">基本的な WCF プログラミング</span><span class="sxs-lookup"><span data-stu-id="49b8b-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="49b8b-134">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="49b8b-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="49b8b-135">概念</span><span class="sxs-lookup"><span data-stu-id="49b8b-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="49b8b-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="49b8b-136">See also</span></span>

- [<span data-ttu-id="49b8b-137">アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="49b8b-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
