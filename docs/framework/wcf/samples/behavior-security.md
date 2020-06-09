---
title: 動作のセキュリティ
ms.date: 03/30/2017
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
ms.openlocfilehash: 5d09fcc2068133b3bb302850a647a2539ab07ee3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575590"
---
# <a name="behavior-security"></a><span data-ttu-id="6e249-102">動作のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="6e249-102">Behavior Security</span></span>
<span data-ttu-id="6e249-103">このセクションには、サービスの動作に対するセキュリティの構成を示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e249-103">This section includes samples that demonstrate configuring security for service behaviors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e249-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6e249-104">In This Section</span></span>  
 [<span data-ttu-id="6e249-105">サービス監査動作</span><span class="sxs-lookup"><span data-stu-id="6e249-105">Service Auditing Behavior</span></span>](service-auditing-behavior.md)  
 <span data-ttu-id="6e249-106">このサンプルでは、<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> を使用して、サービス操作中にセキュリティ イベントの監査を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6e249-106">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span>  
  
 [<span data-ttu-id="6e249-107">メンバーシップとロール プロバイダー</span><span class="sxs-lookup"><span data-stu-id="6e249-107">Membership and Role Provider</span></span>](membership-and-role-provider.md)  
 <span data-ttu-id="6e249-108">このサンプルでは、サービスが ASP.NET のメンバーシップとロールプロバイダーを使用して、クライアントを認証および承認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6e249-108">This sample demonstrates how a service can use the ASP.NET membership and role providers to authenticate and authorize clients.</span></span>  
  
 [<span data-ttu-id="6e249-109">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="6e249-109">Authorizing Access to Service Operations</span></span>](authorizing-access-to-service-operations.md)  
 <span data-ttu-id="6e249-110">このサンプルでは、を使用して、 [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) サービス操作へのアクセスを承認するために属性を使用できるようにする方法を示し <xref:System.Security.Permissions.PrincipalPermissionAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="6e249-110">This sample demonstrates how to use the [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span>  
  
 [<span data-ttu-id="6e249-111">クライアントの偽装</span><span class="sxs-lookup"><span data-stu-id="6e249-111">Impersonating the Client</span></span>](impersonating-the-client.md)  
 <span data-ttu-id="6e249-112">サービスで呼び出し元のアプリケーションを偽装し、サービスが呼び出し元の代わりにシステム リソースにアクセスできるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6e249-112">This sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>
