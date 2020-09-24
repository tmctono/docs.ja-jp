---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 0d03844a58de5b4af93f276de75c88af6efed3f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153795"
---
# \<servicePrincipalName>

<span data-ttu-id="dcb2a-101">サービスの ID をサービス プリンシパル名 (SPN) により指定します。</span><span class="sxs-lookup"><span data-stu-id="dcb2a-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="dcb2a-102">SPN の設定の詳細については、「 [サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcb2a-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="dcb2a-103">構文</span><span class="sxs-lookup"><span data-stu-id="dcb2a-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcb2a-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dcb2a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="dcb2a-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dcb2a-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcb2a-106">属性</span><span class="sxs-lookup"><span data-stu-id="dcb2a-106">Attributes</span></span>  
  
|<span data-ttu-id="dcb2a-107">属性</span><span class="sxs-lookup"><span data-stu-id="dcb2a-107">Attribute</span></span>|<span data-ttu-id="dcb2a-108">説明</span><span class="sxs-lookup"><span data-stu-id="dcb2a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dcb2a-109">value</span><span class="sxs-lookup"><span data-stu-id="dcb2a-109">value</span></span>|<span data-ttu-id="dcb2a-110">クライアントがサービスのインスタンスを一意に識別するための名前。</span><span class="sxs-lookup"><span data-stu-id="dcb2a-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="dcb2a-111">フォレストの複数のコンピューターに 1 つのサービスの複数のインスタンスをインストールする場合、各インスタンスには独自の SPN が必要です。</span><span class="sxs-lookup"><span data-stu-id="dcb2a-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="dcb2a-112">クライアントが認証に使用できる複数の名前がある場合は、指定したサービス インスタンスに複数の SPN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="dcb2a-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dcb2a-113">子要素</span><span class="sxs-lookup"><span data-stu-id="dcb2a-113">Child Elements</span></span>  

 <span data-ttu-id="dcb2a-114">なし。</span><span class="sxs-lookup"><span data-stu-id="dcb2a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dcb2a-115">親要素</span><span class="sxs-lookup"><span data-stu-id="dcb2a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="dcb2a-116">要素</span><span class="sxs-lookup"><span data-stu-id="dcb2a-116">Element</span></span>|<span data-ttu-id="dcb2a-117">説明</span><span class="sxs-lookup"><span data-stu-id="dcb2a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="dcb2a-118">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcb2a-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcb2a-119">解説</span><span class="sxs-lookup"><span data-stu-id="dcb2a-119">Remarks</span></span>  

 <span data-ttu-id="dcb2a-120">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントで SSPI 認証を実行するときに SPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="dcb2a-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb2a-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcb2a-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="dcb2a-122">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="dcb2a-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
