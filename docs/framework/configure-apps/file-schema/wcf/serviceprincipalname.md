---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854992"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="e9b8d-101">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="e9b8d-101">\<servicePrincipalName></span></span>
<span data-ttu-id="e9b8d-102">サービスの ID をサービス プリンシパル名 (SPN) により指定します。</span><span class="sxs-lookup"><span data-stu-id="e9b8d-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="e9b8d-103">SPN の設定の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9b8d-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="e9b8d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9b8d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9b8d-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e9b8d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e9b8d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="e9b8d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="e9b8d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<エンドポイント >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="e9b8d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="e9b8d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<id >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="e9b8d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="e9b8d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicePrincipalName >**</span><span class="sxs-lookup"><span data-stu-id="e9b8d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b8d-110">構文</span><span class="sxs-lookup"><span data-stu-id="e9b8d-110">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9b8d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e9b8d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e9b8d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9b8d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9b8d-113">属性</span><span class="sxs-lookup"><span data-stu-id="e9b8d-113">Attributes</span></span>  
  
|<span data-ttu-id="e9b8d-114">属性</span><span class="sxs-lookup"><span data-stu-id="e9b8d-114">Attribute</span></span>|<span data-ttu-id="e9b8d-115">説明</span><span class="sxs-lookup"><span data-stu-id="e9b8d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9b8d-116">value</span><span class="sxs-lookup"><span data-stu-id="e9b8d-116">value</span></span>|<span data-ttu-id="e9b8d-117">クライアントがサービスのインスタンスを一意に識別する名前です。</span><span class="sxs-lookup"><span data-stu-id="e9b8d-117">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="e9b8d-118">フォレストの複数のコンピューターに 1 つのサービスの複数のインスタンスをインストールする場合、各インスタンスには独自の SPN が必要です。</span><span class="sxs-lookup"><span data-stu-id="e9b8d-118">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="e9b8d-119">クライアントが認証に使用できる複数の名前がある場合は、指定したサービス インスタンスに複数の SPN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="e9b8d-119">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9b8d-120">子要素</span><span class="sxs-lookup"><span data-stu-id="e9b8d-120">Child Elements</span></span>  
 <span data-ttu-id="e9b8d-121">なし。</span><span class="sxs-lookup"><span data-stu-id="e9b8d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9b8d-122">親要素</span><span class="sxs-lookup"><span data-stu-id="e9b8d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e9b8d-123">要素</span><span class="sxs-lookup"><span data-stu-id="e9b8d-123">Element</span></span>|<span data-ttu-id="e9b8d-124">説明</span><span class="sxs-lookup"><span data-stu-id="e9b8d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9b8d-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="e9b8d-125">\<identity></span></span>](identity.md)|<span data-ttu-id="e9b8d-126">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9b8d-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9b8d-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="e9b8d-127">Remarks</span></span>  
 <span data-ttu-id="e9b8d-128">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントで SSPI 認証を実行するときに SPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9b8d-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b8d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9b8d-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="e9b8d-130">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="e9b8d-130">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e9b8d-131">\<identity></span><span class="sxs-lookup"><span data-stu-id="e9b8d-131">\<identity></span></span>](identity.md)
