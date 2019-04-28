---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e307069bd3a98153cc66147ba7bcf511cf13a8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670659"
---
# <a name="rsa"></a><span data-ttu-id="07e19-101">\<rsa></span><span class="sxs-lookup"><span data-stu-id="07e19-101">\<rsa></span></span>
<span data-ttu-id="07e19-102">この ID のエンドポイントに接続するセキュリティで保護された WCF クライアントは、サーバーから提示されたクレームに、この ID を構築するために使用された RSA 公開キーを含むクレームが含まれていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="07e19-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="07e19-103">\<identity></span><span class="sxs-lookup"><span data-stu-id="07e19-103">\<identity></span></span>  
<span data-ttu-id="07e19-104">\<rsa></span><span class="sxs-lookup"><span data-stu-id="07e19-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07e19-105">構文</span><span class="sxs-lookup"><span data-stu-id="07e19-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07e19-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="07e19-106">Attributes and Elements</span></span>  
 <span data-ttu-id="07e19-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e19-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07e19-108">属性</span><span class="sxs-lookup"><span data-stu-id="07e19-108">Attributes</span></span>  
  
|<span data-ttu-id="07e19-109">属性</span><span class="sxs-lookup"><span data-stu-id="07e19-109">Attribute</span></span>|<span data-ttu-id="07e19-110">説明</span><span class="sxs-lookup"><span data-stu-id="07e19-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07e19-111">value</span><span class="sxs-lookup"><span data-stu-id="07e19-111">value</span></span>|<span data-ttu-id="07e19-112">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="07e19-112">Optional String.</span></span> <span data-ttu-id="07e19-113">クライアントで比較される RSA 公開キー値。</span><span class="sxs-lookup"><span data-stu-id="07e19-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07e19-114">子要素</span><span class="sxs-lookup"><span data-stu-id="07e19-114">Child Elements</span></span>  
 <span data-ttu-id="07e19-115">なし</span><span class="sxs-lookup"><span data-stu-id="07e19-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07e19-116">親要素</span><span class="sxs-lookup"><span data-stu-id="07e19-116">Parent Elements</span></span>  
  
|<span data-ttu-id="07e19-117">要素</span><span class="sxs-lookup"><span data-stu-id="07e19-117">Element</span></span>|<span data-ttu-id="07e19-118">説明</span><span class="sxs-lookup"><span data-stu-id="07e19-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07e19-119">\<identity></span><span class="sxs-lookup"><span data-stu-id="07e19-119">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="07e19-120">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="07e19-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07e19-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="07e19-121">Remarks</span></span>  
 <span data-ttu-id="07e19-122">RSA チェックを行うと、その RSA キーまたは生成された独自の RSA キー値に基づいて、単一の証明書の認証を明確に制限できます。</span><span class="sxs-lookup"><span data-stu-id="07e19-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="07e19-123">これにより、RSA キーが変更された場合に既存のクライアントで使用できなくなるサービスを犠牲にして、特定の RSA キーをより厳しく認証できます。</span><span class="sxs-lookup"><span data-stu-id="07e19-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="07e19-124">Identity を使用して、クライアントにサービスを検証する方法の詳細については、次を参照してください。[サービス Id と認証](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="07e19-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="07e19-125">例</span><span class="sxs-lookup"><span data-stu-id="07e19-125">Example</span></span>  
 <span data-ttu-id="07e19-126">次の構成コードは、サーバーの認証に使用される X.509 証明書の公開キー値を指定します。</span><span class="sxs-lookup"><span data-stu-id="07e19-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="07e19-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="07e19-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="07e19-128">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="07e19-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="07e19-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="07e19-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
