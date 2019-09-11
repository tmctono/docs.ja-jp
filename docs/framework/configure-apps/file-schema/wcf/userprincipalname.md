---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854829"
---
# <a name="userprincipalname"></a><span data-ttu-id="4ecd5-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="4ecd5-101">\<userPrincipalName></span></span>
<span data-ttu-id="4ecd5-102">クライアントで認証するサービスのユーザー プリンシパル名 (UPN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="4ecd5-103">UPN の設定の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="4ecd5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4ecd5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4ecd5-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4ecd5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4ecd5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="4ecd5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="4ecd5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<エンドポイント >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="4ecd5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="4ecd5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<id >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="4ecd5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="4ecd5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userPrincipalName >**</span><span class="sxs-lookup"><span data-stu-id="4ecd5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ecd5-110">構文</span><span class="sxs-lookup"><span data-stu-id="4ecd5-110">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ecd5-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4ecd5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4ecd5-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ecd5-113">属性</span><span class="sxs-lookup"><span data-stu-id="4ecd5-113">Attributes</span></span>  
  
|<span data-ttu-id="4ecd5-114">属性</span><span class="sxs-lookup"><span data-stu-id="4ecd5-114">Attribute</span></span>|<span data-ttu-id="4ecd5-115">説明</span><span class="sxs-lookup"><span data-stu-id="4ecd5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ecd5-116">value</span><span class="sxs-lookup"><span data-stu-id="4ecd5-116">value</span></span>|<span data-ttu-id="4ecd5-117">ユーザー アカウント名 (ユーザー ログイン名と呼ばれることもある) と、ユーザー アカウントの検索範囲のドメインを識別するドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-117">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="4ecd5-118">これは、Windows ドメインにログオンするための標準的使用方法です。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-118">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="4ecd5-119">形式はsomeone@example.com 、(電子メールアドレスの場合) です。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-119">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ecd5-120">子要素</span><span class="sxs-lookup"><span data-stu-id="4ecd5-120">Child Elements</span></span>  
 <span data-ttu-id="4ecd5-121">なし。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ecd5-122">親要素</span><span class="sxs-lookup"><span data-stu-id="4ecd5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4ecd5-123">要素</span><span class="sxs-lookup"><span data-stu-id="4ecd5-123">Element</span></span>|<span data-ttu-id="4ecd5-124">説明</span><span class="sxs-lookup"><span data-stu-id="4ecd5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ecd5-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="4ecd5-125">\<identity></span></span>](identity.md)|<span data-ttu-id="4ecd5-126">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ecd5-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ecd5-127">Remarks</span></span>  
 <span data-ttu-id="4ecd5-128">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントで SSPI 認証を実行するときに UPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ecd5-129">例</span><span class="sxs-lookup"><span data-stu-id="4ecd5-129">Example</span></span>  
 <span data-ttu-id="4ecd5-130">次の構成コードは、クライアントで認証するサービスの UPN を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ecd5-130">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="4ecd5-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ecd5-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="4ecd5-132">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="4ecd5-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4ecd5-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="4ecd5-133">\<identity></span></span>](identity.md)
