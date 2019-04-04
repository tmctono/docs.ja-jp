---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 19ea7e940fc7013fc526629a8aac4361ff3fb8bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275017"
---
# <a name="userprincipalname"></a><span data-ttu-id="b4d74-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="b4d74-101">\<userPrincipalName></span></span>
<span data-ttu-id="b4d74-102">クライアントで認証するサービスのユーザー プリンシパル名 (UPN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d74-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="b4d74-103">UPN を設定する方法についての詳細については、[サービス Id と認証](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d74-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="b4d74-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="b4d74-104">\<identity></span></span>  
<span data-ttu-id="b4d74-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="b4d74-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d74-106">構文</span><span class="sxs-lookup"><span data-stu-id="b4d74-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4d74-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b4d74-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b4d74-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4d74-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4d74-109">属性</span><span class="sxs-lookup"><span data-stu-id="b4d74-109">Attributes</span></span>  
  
|<span data-ttu-id="b4d74-110">属性</span><span class="sxs-lookup"><span data-stu-id="b4d74-110">Attribute</span></span>|<span data-ttu-id="b4d74-111">説明</span><span class="sxs-lookup"><span data-stu-id="b4d74-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4d74-112">value</span><span class="sxs-lookup"><span data-stu-id="b4d74-112">value</span></span>|<span data-ttu-id="b4d74-113">ユーザー アカウント名 (ユーザー ログイン名と呼ばれることもある) と、ユーザー アカウントの検索範囲のドメインを識別するドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="b4d74-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="b4d74-114">これは、Windows ドメインにログオンするための標準的使用方法です。</span><span class="sxs-lookup"><span data-stu-id="b4d74-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="b4d74-115">形式: someone@example.com (電子メール アドレス) です。</span><span class="sxs-lookup"><span data-stu-id="b4d74-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4d74-116">子要素</span><span class="sxs-lookup"><span data-stu-id="b4d74-116">Child Elements</span></span>  
 <span data-ttu-id="b4d74-117">なし。</span><span class="sxs-lookup"><span data-stu-id="b4d74-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4d74-118">親要素</span><span class="sxs-lookup"><span data-stu-id="b4d74-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b4d74-119">要素</span><span class="sxs-lookup"><span data-stu-id="b4d74-119">Element</span></span>|<span data-ttu-id="b4d74-120">説明</span><span class="sxs-lookup"><span data-stu-id="b4d74-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4d74-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="b4d74-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="b4d74-122">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d74-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4d74-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4d74-123">Remarks</span></span>  
 <span data-ttu-id="b4d74-124">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントの SSPI 認証を実行するときに、UPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="b4d74-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4d74-125">例</span><span class="sxs-lookup"><span data-stu-id="b4d74-125">Example</span></span>  
 <span data-ttu-id="b4d74-126">次の構成コードは、クライアントで認証するサービスの UPN を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d74-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="b4d74-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4d74-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="b4d74-128">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="b4d74-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b4d74-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="b4d74-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
