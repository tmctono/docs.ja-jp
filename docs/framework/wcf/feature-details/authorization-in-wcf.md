---
title: WCF での承認
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 0097adc3d9677d9ce5595a3ac632b51d94d53f6f
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964684"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="48497-102">WCF での承認</span><span class="sxs-lookup"><span data-stu-id="48497-102">Authorization in WCF</span></span>
<span data-ttu-id="48497-103">承認は、サービスやファイルなどのリソースへのアクセスと権限を制御するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="48497-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="48497-104">このセクションのトピックでは、さまざまな方法で Windows Communication Foundation (WCF) でこの基本的なタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48497-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48497-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="48497-105">In This Section</span></span>  
 [<span data-ttu-id="48497-106">アクセス制御機構</span><span class="sxs-lookup"><span data-stu-id="48497-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="48497-107">WCF の承認メカニズムの概要と、推奨される使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48497-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="48497-108">方法: PrincipalPermissionAttribute クラスでアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="48497-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="48497-109"><xref:System.Security.Permissions.PrincipalPermissionAttribute> を使用してサービスへのアクセスを制限するプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="48497-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="48497-110">方法 : ASP.NET のロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="48497-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="48497-111">サービスの構成に従って、ASP.NET のロールプロバイダー機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="48497-111">Walks through the configuration of a service to enable it to use the role provider feature of ASP.NET.</span></span>  
  
 [<span data-ttu-id="48497-112">方法 : ASP.NET の承認マネージャー ロール プロバイダーとサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="48497-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="48497-113">ASP.NET は、承認マネージャーを使用して、Web サイトの承認を管理できます。</span><span class="sxs-lookup"><span data-stu-id="48497-113">ASP.NET can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="48497-114">WCF では、クライアントの承認に ASP.NET/Authorization Manager の組み合わせを利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="48497-114">WCF can similarly leverage the ASP.NET/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="48497-115">ID モデルを使用したクレームと承認の管理</span><span class="sxs-lookup"><span data-stu-id="48497-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="48497-116">ID モデル インフラストラクチャをクレーム ベースの承認に使用する際の基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="48497-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="48497-117">委任と偽装</span><span class="sxs-lookup"><span data-stu-id="48497-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="48497-118">委任と偽装の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="48497-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="48497-119">参照先</span><span class="sxs-lookup"><span data-stu-id="48497-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="48497-120">関連セクション</span><span class="sxs-lookup"><span data-stu-id="48497-120">Related Sections</span></span>  
 [<span data-ttu-id="48497-121">認証</span><span class="sxs-lookup"><span data-stu-id="48497-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="48497-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="48497-122">See also</span></span>

- [<span data-ttu-id="48497-123">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="48497-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="48497-124">[Windows Server App Fabric のセキュリティモデル](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="48497-124">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
