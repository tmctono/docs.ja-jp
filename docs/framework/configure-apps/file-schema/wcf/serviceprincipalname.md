---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 28ae27481ea9cb86c31b5be1f12b5491f8ca143e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936153"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="61d04-101">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="61d04-101">\<servicePrincipalName></span></span>
<span data-ttu-id="61d04-102">サービスの ID をサービス プリンシパル名 (SPN) により指定します。</span><span class="sxs-lookup"><span data-stu-id="61d04-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="61d04-103">SPN の設定の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d04-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="61d04-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="61d04-104">\<identity></span></span>  
<span data-ttu-id="61d04-105">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="61d04-105">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61d04-106">構文</span><span class="sxs-lookup"><span data-stu-id="61d04-106">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61d04-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="61d04-107">Attributes and Elements</span></span>  
 <span data-ttu-id="61d04-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="61d04-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61d04-109">属性</span><span class="sxs-lookup"><span data-stu-id="61d04-109">Attributes</span></span>  
  
|<span data-ttu-id="61d04-110">属性</span><span class="sxs-lookup"><span data-stu-id="61d04-110">Attribute</span></span>|<span data-ttu-id="61d04-111">説明</span><span class="sxs-lookup"><span data-stu-id="61d04-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61d04-112">value</span><span class="sxs-lookup"><span data-stu-id="61d04-112">value</span></span>|<span data-ttu-id="61d04-113">クライアントがサービスのインスタンスを一意に識別する名前です。</span><span class="sxs-lookup"><span data-stu-id="61d04-113">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="61d04-114">フォレストの複数のコンピューターに 1 つのサービスの複数のインスタンスをインストールする場合、各インスタンスには独自の SPN が必要です。</span><span class="sxs-lookup"><span data-stu-id="61d04-114">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="61d04-115">クライアントが認証に使用できる複数の名前がある場合は、指定したサービス インスタンスに複数の SPN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="61d04-115">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61d04-116">子要素</span><span class="sxs-lookup"><span data-stu-id="61d04-116">Child Elements</span></span>  
 <span data-ttu-id="61d04-117">なし。</span><span class="sxs-lookup"><span data-stu-id="61d04-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61d04-118">親要素</span><span class="sxs-lookup"><span data-stu-id="61d04-118">Parent Elements</span></span>  
  
|<span data-ttu-id="61d04-119">要素</span><span class="sxs-lookup"><span data-stu-id="61d04-119">Element</span></span>|<span data-ttu-id="61d04-120">説明</span><span class="sxs-lookup"><span data-stu-id="61d04-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61d04-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="61d04-121">\<identity></span></span>](identity.md)|<span data-ttu-id="61d04-122">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="61d04-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61d04-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="61d04-123">Remarks</span></span>  
 <span data-ttu-id="61d04-124">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントで SSPI 認証を実行するときに SPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="61d04-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d04-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="61d04-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="61d04-126">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="61d04-126">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="61d04-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="61d04-127">\<identity></span></span>](identity.md)
