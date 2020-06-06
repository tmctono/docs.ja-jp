---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854829"
---
# \<userPrincipalName>
<span data-ttu-id="7fabf-101">クライアントで認証するサービスのユーザー プリンシパル名 (UPN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="7fabf-101">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="7fabf-102">UPN の設定の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fabf-102">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="7fabf-103">構文</span><span class="sxs-lookup"><span data-stu-id="7fabf-103">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fabf-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7fabf-104">Attributes and Elements</span></span>  
 <span data-ttu-id="7fabf-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7fabf-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fabf-106">属性</span><span class="sxs-lookup"><span data-stu-id="7fabf-106">Attributes</span></span>  
  
|<span data-ttu-id="7fabf-107">属性</span><span class="sxs-lookup"><span data-stu-id="7fabf-107">Attribute</span></span>|<span data-ttu-id="7fabf-108">説明</span><span class="sxs-lookup"><span data-stu-id="7fabf-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fabf-109">value</span><span class="sxs-lookup"><span data-stu-id="7fabf-109">value</span></span>|<span data-ttu-id="7fabf-110">ユーザー アカウント名 (ユーザー ログイン名と呼ばれることもある) と、ユーザー アカウントの検索範囲のドメインを識別するドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="7fabf-110">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="7fabf-111">これは、Windows ドメインにログオンするための標準的使用方法です。</span><span class="sxs-lookup"><span data-stu-id="7fabf-111">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="7fabf-112">形式は、 someone@example.com (電子メールアドレスの場合) です。</span><span class="sxs-lookup"><span data-stu-id="7fabf-112">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7fabf-113">子要素</span><span class="sxs-lookup"><span data-stu-id="7fabf-113">Child Elements</span></span>  
 <span data-ttu-id="7fabf-114">なし。</span><span class="sxs-lookup"><span data-stu-id="7fabf-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7fabf-115">親要素</span><span class="sxs-lookup"><span data-stu-id="7fabf-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7fabf-116">要素</span><span class="sxs-lookup"><span data-stu-id="7fabf-116">Element</span></span>|<span data-ttu-id="7fabf-117">Description</span><span class="sxs-lookup"><span data-stu-id="7fabf-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="7fabf-118">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="7fabf-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fabf-119">解説</span><span class="sxs-lookup"><span data-stu-id="7fabf-119">Remarks</span></span>  
 <span data-ttu-id="7fabf-120">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントで SSPI 認証を実行するときに UPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="7fabf-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fabf-121">例</span><span class="sxs-lookup"><span data-stu-id="7fabf-121">Example</span></span>  
 <span data-ttu-id="7fabf-122">次の構成コードは、クライアントで認証するサービスの UPN を指定します。</span><span class="sxs-lookup"><span data-stu-id="7fabf-122">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="7fabf-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fabf-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="7fabf-124">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="7fabf-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
