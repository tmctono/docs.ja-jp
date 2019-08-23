---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 35d33fd4d174c8e4ccdaaf1ac33884663340e16a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919123"
---
# <a name="dns"></a><span data-ttu-id="c7160-101">\<dns ></span><span class="sxs-lookup"><span data-stu-id="c7160-101">\<dns></span></span>
<span data-ttu-id="c7160-102">予想されるサーバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7160-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="c7160-103">この ID は、同じ値を持つ DNS がサーバーの証明書に含まれていれば、X509 証明書の認証モードで有効です。</span><span class="sxs-lookup"><span data-stu-id="c7160-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="c7160-104">さらに、SPN に同じ値があれば、Windows 認証モードでも有効です。</span><span class="sxs-lookup"><span data-stu-id="c7160-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="c7160-105">要素の値の設定の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7160-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="c7160-106">\<identity></span><span class="sxs-lookup"><span data-stu-id="c7160-106">\<identity></span></span>  
<span data-ttu-id="c7160-107">\<dns ></span><span class="sxs-lookup"><span data-stu-id="c7160-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7160-108">構文</span><span class="sxs-lookup"><span data-stu-id="c7160-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7160-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c7160-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c7160-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7160-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7160-111">属性</span><span class="sxs-lookup"><span data-stu-id="c7160-111">Attributes</span></span>  
  
|<span data-ttu-id="c7160-112">属性</span><span class="sxs-lookup"><span data-stu-id="c7160-112">Attribute</span></span>|<span data-ttu-id="c7160-113">説明</span><span class="sxs-lookup"><span data-stu-id="c7160-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7160-114">value</span><span class="sxs-lookup"><span data-stu-id="c7160-114">value</span></span>|<span data-ttu-id="c7160-115">証明書の DNS です。</span><span class="sxs-lookup"><span data-stu-id="c7160-115">The DNS of the certificate.</span></span> <span data-ttu-id="c7160-116">DNS は、IP ベースのネットワーク上でコンピューターを特定するために使用される業界標準のプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="c7160-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="c7160-117">ユーザー <https://go.microsoft.com/fwlink/?prd=10929>は、や[https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165)などの表示名を覚えておくことができます。たとえば、207.46.131.137 のように、数字ベースのアドレスよりも簡単です。</span><span class="sxs-lookup"><span data-stu-id="c7160-117">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7160-118">子要素</span><span class="sxs-lookup"><span data-stu-id="c7160-118">Child Elements</span></span>  
 <span data-ttu-id="c7160-119">なし。</span><span class="sxs-lookup"><span data-stu-id="c7160-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7160-120">親要素</span><span class="sxs-lookup"><span data-stu-id="c7160-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c7160-121">要素</span><span class="sxs-lookup"><span data-stu-id="c7160-121">Element</span></span>|<span data-ttu-id="c7160-122">説明</span><span class="sxs-lookup"><span data-stu-id="c7160-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7160-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="c7160-123">\<identity></span></span>](identity.md)|<span data-ttu-id="c7160-124">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7160-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c7160-125">例</span><span class="sxs-lookup"><span data-stu-id="c7160-125">Example</span></span>  
 <span data-ttu-id="c7160-126">次の構成コードは、サーバーの認証に使用される X.509 証明書の DNS を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7160-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="c7160-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7160-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="c7160-128">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="c7160-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c7160-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="c7160-129">\<identity></span></span>](identity.md)
