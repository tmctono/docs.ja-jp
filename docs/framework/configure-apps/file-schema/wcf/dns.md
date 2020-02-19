---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: e49a564c9793b371425b2b787586bb9d3cbed58b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452228"
---
# <a name="dns"></a><span data-ttu-id="95cea-101">dns > の \<</span><span class="sxs-lookup"><span data-stu-id="95cea-101">\<dns></span></span>
<span data-ttu-id="95cea-102">予想されるサーバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="95cea-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="95cea-103">この ID は、同じ値を持つ DNS がサーバーの証明書に含まれていれば、X509 証明書の認証モードで有効です。</span><span class="sxs-lookup"><span data-stu-id="95cea-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="95cea-104">さらに、SPN に同じ値があれば、Windows 認証モードでも有効です。</span><span class="sxs-lookup"><span data-stu-id="95cea-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="95cea-105">要素の値の設定の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95cea-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="95cea-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="95cea-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="95cea-107">&nbsp;&nbsp;[ **\<system.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="95cea-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="95cea-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント**](client.md)></span><span class="sxs-lookup"><span data-stu-id="95cea-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="95cea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**エンドポイント >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="95cea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="95cea-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**id >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="95cea-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="95cea-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**dns\<**</span><span class="sxs-lookup"><span data-stu-id="95cea-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95cea-112">構文</span><span class="sxs-lookup"><span data-stu-id="95cea-112">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95cea-113">属性と要素</span><span class="sxs-lookup"><span data-stu-id="95cea-113">Attributes and Elements</span></span>  
 <span data-ttu-id="95cea-114">次のセクションでは、属性、子要素、親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="95cea-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95cea-115">属性</span><span class="sxs-lookup"><span data-stu-id="95cea-115">Attributes</span></span>  
  
|<span data-ttu-id="95cea-116">属性</span><span class="sxs-lookup"><span data-stu-id="95cea-116">Attribute</span></span>|<span data-ttu-id="95cea-117">説明</span><span class="sxs-lookup"><span data-stu-id="95cea-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95cea-118">value</span><span class="sxs-lookup"><span data-stu-id="95cea-118">value</span></span>|<span data-ttu-id="95cea-119">証明書の DNS です。</span><span class="sxs-lookup"><span data-stu-id="95cea-119">The DNS of the certificate.</span></span> <span data-ttu-id="95cea-120">DNS は、IP ベースのネットワーク上でコンピューターを特定するために使用される業界標準のプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="95cea-120">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="95cea-121">ユーザーは `https://go.microsoft.com/fwlink/?prd=10929` や `https://go.microsoft.com/fwlink/?LinkID=96165`などの表示名を、207.46.131.137 などの数字ベースのアドレスよりも覚えやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="95cea-121">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95cea-122">子要素</span><span class="sxs-lookup"><span data-stu-id="95cea-122">Child Elements</span></span>  
 <span data-ttu-id="95cea-123">[なし]。</span><span class="sxs-lookup"><span data-stu-id="95cea-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95cea-124">親要素</span><span class="sxs-lookup"><span data-stu-id="95cea-124">Parent Elements</span></span>  
  
|<span data-ttu-id="95cea-125">要素</span><span class="sxs-lookup"><span data-stu-id="95cea-125">Element</span></span>|<span data-ttu-id="95cea-126">説明</span><span class="sxs-lookup"><span data-stu-id="95cea-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95cea-127">\<id ></span><span class="sxs-lookup"><span data-stu-id="95cea-127">\<identity></span></span>](identity.md)|<span data-ttu-id="95cea-128">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="95cea-128">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95cea-129">例</span><span class="sxs-lookup"><span data-stu-id="95cea-129">Example</span></span>  
 <span data-ttu-id="95cea-130">次の構成コードは、サーバーの認証に使用される X.509 証明書の DNS を指定します。</span><span class="sxs-lookup"><span data-stu-id="95cea-130">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="95cea-131">参照</span><span class="sxs-lookup"><span data-stu-id="95cea-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="95cea-132">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="95cea-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="95cea-133">\<id ></span><span class="sxs-lookup"><span data-stu-id="95cea-133">\<identity></span></span>](identity.md)
