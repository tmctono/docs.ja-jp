---
title: <certificate> の <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850021"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="0330f-102">\<id > の\<証明書の ></span><span class="sxs-lookup"><span data-stu-id="0330f-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="0330f-103">クライアントに対するサービスの検証に使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="0330f-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="0330f-104">要素の値の設定の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0330f-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="0330f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0330f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0330f-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0330f-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0330f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="0330f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="0330f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<エンドポイント >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="0330f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="0330f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<id >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="0330f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="0330f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<証明書の >**</span><span class="sxs-lookup"><span data-stu-id="0330f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0330f-111">構文</span><span class="sxs-lookup"><span data-stu-id="0330f-111">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0330f-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0330f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0330f-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0330f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0330f-114">属性</span><span class="sxs-lookup"><span data-stu-id="0330f-114">Attributes</span></span>  
  
|<span data-ttu-id="0330f-115">属性</span><span class="sxs-lookup"><span data-stu-id="0330f-115">Attribute</span></span>|<span data-ttu-id="0330f-116">説明</span><span class="sxs-lookup"><span data-stu-id="0330f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0330f-117">encodedValue</span><span class="sxs-lookup"><span data-stu-id="0330f-117">encodedValue</span></span>|<span data-ttu-id="0330f-118">証明書の Base64 エンコーディングです。</span><span class="sxs-lookup"><span data-stu-id="0330f-118">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0330f-119">子要素</span><span class="sxs-lookup"><span data-stu-id="0330f-119">Child Elements</span></span>  
 <span data-ttu-id="0330f-120">なし。</span><span class="sxs-lookup"><span data-stu-id="0330f-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0330f-121">親要素</span><span class="sxs-lookup"><span data-stu-id="0330f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0330f-122">要素</span><span class="sxs-lookup"><span data-stu-id="0330f-122">Element</span></span>|<span data-ttu-id="0330f-123">説明</span><span class="sxs-lookup"><span data-stu-id="0330f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0330f-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="0330f-124">\<identity></span></span>](identity.md)|<span data-ttu-id="0330f-125">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="0330f-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0330f-126">例</span><span class="sxs-lookup"><span data-stu-id="0330f-126">Example</span></span>  
 <span data-ttu-id="0330f-127">次のコードは、クライアントに対するサーバーの検証に使用される証明書のエンコードされた表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="0330f-127">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="0330f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="0330f-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="0330f-129">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="0330f-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0330f-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="0330f-130">\<identity></span></span>](identity.md)
