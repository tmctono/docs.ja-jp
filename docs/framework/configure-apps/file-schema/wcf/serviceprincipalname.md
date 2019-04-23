---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 75e95bcbaee229f19bdfdd119b548ed612f4ddaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204407"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="8323d-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="8323d-101">\<servicePrincipalName></span></span>
<span data-ttu-id="8323d-102">サービスの ID をサービス プリンシパル名 (SPN) により指定します。</span><span class="sxs-lookup"><span data-stu-id="8323d-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="8323d-103">SPN を設定する方法についての詳細については、次を参照してください。[サービス Id と認証](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="8323d-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="8323d-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="8323d-104">\<identity></span></span>  
<span data-ttu-id="8323d-105">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="8323d-105">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8323d-106">構文</span><span class="sxs-lookup"><span data-stu-id="8323d-106">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8323d-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8323d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8323d-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8323d-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8323d-109">属性</span><span class="sxs-lookup"><span data-stu-id="8323d-109">Attributes</span></span>  
  
|<span data-ttu-id="8323d-110">属性</span><span class="sxs-lookup"><span data-stu-id="8323d-110">Attribute</span></span>|<span data-ttu-id="8323d-111">説明</span><span class="sxs-lookup"><span data-stu-id="8323d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8323d-112">value</span><span class="sxs-lookup"><span data-stu-id="8323d-112">value</span></span>|<span data-ttu-id="8323d-113">クライアントがサービスのインスタンスを一意に識別する名前です。</span><span class="sxs-lookup"><span data-stu-id="8323d-113">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="8323d-114">フォレストの複数のコンピューターに 1 つのサービスの複数のインスタンスをインストールする場合、各インスタンスには独自の SPN が必要です。</span><span class="sxs-lookup"><span data-stu-id="8323d-114">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="8323d-115">クライアントが認証に使用できる複数の名前がある場合は、指定したサービス インスタンスに複数の SPN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8323d-115">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8323d-116">子要素</span><span class="sxs-lookup"><span data-stu-id="8323d-116">Child Elements</span></span>  
 <span data-ttu-id="8323d-117">なし。</span><span class="sxs-lookup"><span data-stu-id="8323d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8323d-118">親要素</span><span class="sxs-lookup"><span data-stu-id="8323d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8323d-119">要素</span><span class="sxs-lookup"><span data-stu-id="8323d-119">Element</span></span>|<span data-ttu-id="8323d-120">説明</span><span class="sxs-lookup"><span data-stu-id="8323d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8323d-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="8323d-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8323d-122">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="8323d-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8323d-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="8323d-123">Remarks</span></span>  
 <span data-ttu-id="8323d-124">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントの SSPI 認証を実行するときに SPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="8323d-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8323d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8323d-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="8323d-126">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="8323d-126">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8323d-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="8323d-127">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
