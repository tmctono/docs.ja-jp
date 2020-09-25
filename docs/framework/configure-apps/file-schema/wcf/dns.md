---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: adfd94365ceb0ddc3164a6baef838c16027b4bc3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190139"
---
# \<dns>

<span data-ttu-id="37fca-101">予想されるサーバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="37fca-101">Specifies the expected identity of the server.</span></span> <span data-ttu-id="37fca-102">この ID は、同じ値を持つ DNS がサーバーの証明書に含まれていれば、X509 証明書の認証モードで有効です。</span><span class="sxs-lookup"><span data-stu-id="37fca-102">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="37fca-103">さらに、SPN に同じ値があれば、Windows 認証モードでも有効です。</span><span class="sxs-lookup"><span data-stu-id="37fca-103">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="37fca-104">要素の値の設定の詳細については、「 [サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37fca-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**  
  
## <a name="syntax"></a><span data-ttu-id="37fca-105">構文</span><span class="sxs-lookup"><span data-stu-id="37fca-105">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37fca-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="37fca-106">Attributes and Elements</span></span>  

 <span data-ttu-id="37fca-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="37fca-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37fca-108">属性</span><span class="sxs-lookup"><span data-stu-id="37fca-108">Attributes</span></span>  
  
|<span data-ttu-id="37fca-109">属性</span><span class="sxs-lookup"><span data-stu-id="37fca-109">Attribute</span></span>|<span data-ttu-id="37fca-110">説明</span><span class="sxs-lookup"><span data-stu-id="37fca-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37fca-111">value</span><span class="sxs-lookup"><span data-stu-id="37fca-111">value</span></span>|<span data-ttu-id="37fca-112">証明書の DNS です。</span><span class="sxs-lookup"><span data-stu-id="37fca-112">The DNS of the certificate.</span></span> <span data-ttu-id="37fca-113">DNS は、IP ベースのネットワーク上でコンピューターを特定するために使用される業界標準のプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="37fca-113">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="37fca-114">ユーザーは、やなどの表示名を覚えておくことができます。たとえば、207.46.131.137 のように、 `https://go.microsoft.com/fwlink/?prd=10929` `https://go.microsoft.com/fwlink/?LinkID=96165` 数字ベースのアドレスよりも簡単です。</span><span class="sxs-lookup"><span data-stu-id="37fca-114">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37fca-115">子要素</span><span class="sxs-lookup"><span data-stu-id="37fca-115">Child Elements</span></span>  

 <span data-ttu-id="37fca-116">なし。</span><span class="sxs-lookup"><span data-stu-id="37fca-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37fca-117">親要素</span><span class="sxs-lookup"><span data-stu-id="37fca-117">Parent Elements</span></span>  
  
|<span data-ttu-id="37fca-118">要素</span><span class="sxs-lookup"><span data-stu-id="37fca-118">Element</span></span>|<span data-ttu-id="37fca-119">説明</span><span class="sxs-lookup"><span data-stu-id="37fca-119">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="37fca-120">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="37fca-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="37fca-121">例</span><span class="sxs-lookup"><span data-stu-id="37fca-121">Example</span></span>  

 <span data-ttu-id="37fca-122">次の構成コードは、サーバーの認証に使用される X.509 証明書の DNS を指定します。</span><span class="sxs-lookup"><span data-stu-id="37fca-122">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="37fca-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="37fca-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="37fca-124">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="37fca-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
