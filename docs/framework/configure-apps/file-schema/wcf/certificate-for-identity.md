---
title: <certificate> の <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 76bdcb40d5016d7fcbff6c0d9769819f710065fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205837"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="e4d0f-102">\<証明書 > の\<identity ></span><span class="sxs-lookup"><span data-stu-id="e4d0f-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="e4d0f-103">クライアントに対するサービスの検証に使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4d0f-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="e4d0f-104">要素の値を設定する方法についての詳細については、次を参照してください。[サービス Id と認証](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4d0f-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="e4d0f-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="e4d0f-105">\<identity></span></span>  
<span data-ttu-id="e4d0f-106">\<証明書></span><span class="sxs-lookup"><span data-stu-id="e4d0f-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d0f-107">構文</span><span class="sxs-lookup"><span data-stu-id="e4d0f-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4d0f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e4d0f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e4d0f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4d0f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4d0f-110">属性</span><span class="sxs-lookup"><span data-stu-id="e4d0f-110">Attributes</span></span>  
  
|<span data-ttu-id="e4d0f-111">属性</span><span class="sxs-lookup"><span data-stu-id="e4d0f-111">Attribute</span></span>|<span data-ttu-id="e4d0f-112">説明</span><span class="sxs-lookup"><span data-stu-id="e4d0f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4d0f-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="e4d0f-113">encodedValue</span></span>|<span data-ttu-id="e4d0f-114">証明書の Base64 エンコーディングです。</span><span class="sxs-lookup"><span data-stu-id="e4d0f-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4d0f-115">子要素</span><span class="sxs-lookup"><span data-stu-id="e4d0f-115">Child Elements</span></span>  
 <span data-ttu-id="e4d0f-116">なし。</span><span class="sxs-lookup"><span data-stu-id="e4d0f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4d0f-117">親要素</span><span class="sxs-lookup"><span data-stu-id="e4d0f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e4d0f-118">要素</span><span class="sxs-lookup"><span data-stu-id="e4d0f-118">Element</span></span>|<span data-ttu-id="e4d0f-119">説明</span><span class="sxs-lookup"><span data-stu-id="e4d0f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4d0f-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="e4d0f-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e4d0f-121">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4d0f-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e4d0f-122">例</span><span class="sxs-lookup"><span data-stu-id="e4d0f-122">Example</span></span>  
 <span data-ttu-id="e4d0f-123">次のコードは、クライアントに対するサーバーの検証に使用される証明書のエンコードされた表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4d0f-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="e4d0f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4d0f-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="e4d0f-125">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="e4d0f-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e4d0f-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="e4d0f-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
