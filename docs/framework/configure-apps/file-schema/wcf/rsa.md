---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e1651f563bdb2b2b24eacacf7bfe387e33a82c7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855047"
---
# <a name="rsa"></a><span data-ttu-id="4ca59-101">\<rsa ></span><span class="sxs-lookup"><span data-stu-id="4ca59-101">\<rsa></span></span>
<span data-ttu-id="4ca59-102">この ID のエンドポイントに接続するセキュリティで保護された WCF クライアントは、サーバーから提示されたクレームに、この ID を構築するために使用された RSA 公開キーを含むクレームが含まれていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="4ca59-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
<span data-ttu-id="4ca59-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4ca59-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4ca59-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4ca59-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4ca59-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="4ca59-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="4ca59-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<エンドポイント >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="4ca59-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="4ca59-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<id >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="4ca59-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="4ca59-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<rsa >**</span><span class="sxs-lookup"><span data-stu-id="4ca59-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca59-109">構文</span><span class="sxs-lookup"><span data-stu-id="4ca59-109">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ca59-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4ca59-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4ca59-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ca59-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ca59-112">属性</span><span class="sxs-lookup"><span data-stu-id="4ca59-112">Attributes</span></span>  
  
|<span data-ttu-id="4ca59-113">属性</span><span class="sxs-lookup"><span data-stu-id="4ca59-113">Attribute</span></span>|<span data-ttu-id="4ca59-114">説明</span><span class="sxs-lookup"><span data-stu-id="4ca59-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ca59-115">value</span><span class="sxs-lookup"><span data-stu-id="4ca59-115">value</span></span>|<span data-ttu-id="4ca59-116">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="4ca59-116">Optional String.</span></span> <span data-ttu-id="4ca59-117">クライアントで比較される RSA 公開キー値。</span><span class="sxs-lookup"><span data-stu-id="4ca59-117">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ca59-118">子要素</span><span class="sxs-lookup"><span data-stu-id="4ca59-118">Child Elements</span></span>  
 <span data-ttu-id="4ca59-119">なし</span><span class="sxs-lookup"><span data-stu-id="4ca59-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ca59-120">親要素</span><span class="sxs-lookup"><span data-stu-id="4ca59-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4ca59-121">要素</span><span class="sxs-lookup"><span data-stu-id="4ca59-121">Element</span></span>|<span data-ttu-id="4ca59-122">説明</span><span class="sxs-lookup"><span data-stu-id="4ca59-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ca59-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="4ca59-123">\<identity></span></span>](identity.md)|<span data-ttu-id="4ca59-124">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ca59-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ca59-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ca59-125">Remarks</span></span>  
 <span data-ttu-id="4ca59-126">RSA チェックを行うと、その RSA キーまたは生成された独自の RSA キー値に基づいて、単一の証明書の認証を明確に制限できます。</span><span class="sxs-lookup"><span data-stu-id="4ca59-126">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="4ca59-127">これにより、RSA キーが変更された場合に既存のクライアントで使用できなくなるサービスを犠牲にして、特定の RSA キーをより厳しく認証できます。</span><span class="sxs-lookup"><span data-stu-id="4ca59-127">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="4ca59-128">Id を使用してクライアントに対するサービスを検証する方法の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ca59-128">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ca59-129">例</span><span class="sxs-lookup"><span data-stu-id="4ca59-129">Example</span></span>  
 <span data-ttu-id="4ca59-130">次の構成コードは、サーバーの認証に使用される X.509 証明書の公開キー値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ca59-130">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="4ca59-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ca59-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="4ca59-132">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="4ca59-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4ca59-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="4ca59-133">\<identity></span></span>](identity.md)
