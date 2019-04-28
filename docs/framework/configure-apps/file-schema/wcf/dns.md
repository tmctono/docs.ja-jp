---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 26b45b17ecd7bbd3fffb5d03553834ec22eedc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700931"
---
# <a name="dns"></a><span data-ttu-id="41fac-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="41fac-101">\<dns></span></span>
<span data-ttu-id="41fac-102">予想されるサーバーの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="41fac-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="41fac-103">この ID は、同じ値を持つ DNS がサーバーの証明書に含まれていれば、X509 証明書の認証モードで有効です。</span><span class="sxs-lookup"><span data-stu-id="41fac-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="41fac-104">さらに、SPN に同じ値があれば、Windows 認証モードでも有効です。</span><span class="sxs-lookup"><span data-stu-id="41fac-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="41fac-105">要素の値を設定する方法についての詳細については、次を参照してください。[サービス Id と認証](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="41fac-105">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="41fac-106">\<identity></span><span class="sxs-lookup"><span data-stu-id="41fac-106">\<identity></span></span>  
<span data-ttu-id="41fac-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="41fac-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41fac-108">構文</span><span class="sxs-lookup"><span data-stu-id="41fac-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41fac-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="41fac-109">Attributes and Elements</span></span>  
 <span data-ttu-id="41fac-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="41fac-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41fac-111">属性</span><span class="sxs-lookup"><span data-stu-id="41fac-111">Attributes</span></span>  
  
|<span data-ttu-id="41fac-112">属性</span><span class="sxs-lookup"><span data-stu-id="41fac-112">Attribute</span></span>|<span data-ttu-id="41fac-113">説明</span><span class="sxs-lookup"><span data-stu-id="41fac-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41fac-114">value</span><span class="sxs-lookup"><span data-stu-id="41fac-114">value</span></span>|<span data-ttu-id="41fac-115">証明書の DNS です。</span><span class="sxs-lookup"><span data-stu-id="41fac-115">The DNS of the certificate.</span></span> <span data-ttu-id="41fac-116">DNS は、IP ベースのネットワーク上でコンピューターを特定するために使用される業界標準のプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="41fac-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="41fac-117">ユーザーなど、表示名が覚え<https://go.microsoft.com/fwlink/?prd=10929>または[ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165)、207.46.131.137 など、数値ベースのアドレスよりも簡単です。</span><span class="sxs-lookup"><span data-stu-id="41fac-117">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41fac-118">子要素</span><span class="sxs-lookup"><span data-stu-id="41fac-118">Child Elements</span></span>  
 <span data-ttu-id="41fac-119">なし。</span><span class="sxs-lookup"><span data-stu-id="41fac-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41fac-120">親要素</span><span class="sxs-lookup"><span data-stu-id="41fac-120">Parent Elements</span></span>  
  
|<span data-ttu-id="41fac-121">要素</span><span class="sxs-lookup"><span data-stu-id="41fac-121">Element</span></span>|<span data-ttu-id="41fac-122">説明</span><span class="sxs-lookup"><span data-stu-id="41fac-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41fac-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="41fac-123">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="41fac-124">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="41fac-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="41fac-125">例</span><span class="sxs-lookup"><span data-stu-id="41fac-125">Example</span></span>  
 <span data-ttu-id="41fac-126">次の構成コードは、サーバーの認証に使用される X.509 証明書の DNS を指定します。</span><span class="sxs-lookup"><span data-stu-id="41fac-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="41fac-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="41fac-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="41fac-128">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="41fac-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="41fac-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="41fac-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
