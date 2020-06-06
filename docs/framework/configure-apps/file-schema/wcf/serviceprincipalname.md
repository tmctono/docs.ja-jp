---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854992"
---
# \<servicePrincipalName>
<span data-ttu-id="de43f-101">サービスの ID をサービス プリンシパル名 (SPN) により指定します。</span><span class="sxs-lookup"><span data-stu-id="de43f-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="de43f-102">SPN の設定の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de43f-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="de43f-103">構文</span><span class="sxs-lookup"><span data-stu-id="de43f-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de43f-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="de43f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="de43f-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="de43f-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de43f-106">属性</span><span class="sxs-lookup"><span data-stu-id="de43f-106">Attributes</span></span>  
  
|<span data-ttu-id="de43f-107">属性</span><span class="sxs-lookup"><span data-stu-id="de43f-107">Attribute</span></span>|<span data-ttu-id="de43f-108">説明</span><span class="sxs-lookup"><span data-stu-id="de43f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de43f-109">value</span><span class="sxs-lookup"><span data-stu-id="de43f-109">value</span></span>|<span data-ttu-id="de43f-110">クライアントがサービスのインスタンスを一意に識別するための名前。</span><span class="sxs-lookup"><span data-stu-id="de43f-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="de43f-111">フォレストの複数のコンピューターに 1 つのサービスの複数のインスタンスをインストールする場合、各インスタンスには独自の SPN が必要です。</span><span class="sxs-lookup"><span data-stu-id="de43f-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="de43f-112">クライアントが認証に使用できる複数の名前がある場合は、指定したサービス インスタンスに複数の SPN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="de43f-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de43f-113">子要素</span><span class="sxs-lookup"><span data-stu-id="de43f-113">Child Elements</span></span>  
 <span data-ttu-id="de43f-114">なし。</span><span class="sxs-lookup"><span data-stu-id="de43f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de43f-115">親要素</span><span class="sxs-lookup"><span data-stu-id="de43f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="de43f-116">要素</span><span class="sxs-lookup"><span data-stu-id="de43f-116">Element</span></span>|<span data-ttu-id="de43f-117">Description</span><span class="sxs-lookup"><span data-stu-id="de43f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="de43f-118">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="de43f-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de43f-119">解説</span><span class="sxs-lookup"><span data-stu-id="de43f-119">Remarks</span></span>  
 <span data-ttu-id="de43f-120">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントで SSPI 認証を実行するときに SPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="de43f-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de43f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="de43f-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="de43f-122">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="de43f-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
