---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 423a3249a9298675517f0cff08566c3735fa35f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940509"
---
# <a name="userprincipalname"></a><span data-ttu-id="e625a-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="e625a-101">\<userPrincipalName></span></span>
<span data-ttu-id="e625a-102">クライアントで認証するサービスのユーザー プリンシパル名 (UPN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e625a-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="e625a-103">UPN の設定の詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e625a-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="e625a-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="e625a-104">\<identity></span></span>  
<span data-ttu-id="e625a-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="e625a-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e625a-106">構文</span><span class="sxs-lookup"><span data-stu-id="e625a-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e625a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e625a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e625a-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e625a-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e625a-109">属性</span><span class="sxs-lookup"><span data-stu-id="e625a-109">Attributes</span></span>  
  
|<span data-ttu-id="e625a-110">属性</span><span class="sxs-lookup"><span data-stu-id="e625a-110">Attribute</span></span>|<span data-ttu-id="e625a-111">説明</span><span class="sxs-lookup"><span data-stu-id="e625a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e625a-112">value</span><span class="sxs-lookup"><span data-stu-id="e625a-112">value</span></span>|<span data-ttu-id="e625a-113">ユーザー アカウント名 (ユーザー ログイン名と呼ばれることもある) と、ユーザー アカウントの検索範囲のドメインを識別するドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="e625a-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="e625a-114">これは、Windows ドメインにログオンするための標準的使用方法です。</span><span class="sxs-lookup"><span data-stu-id="e625a-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="e625a-115">形式はsomeone@example.com 、(電子メールアドレスの場合) です。</span><span class="sxs-lookup"><span data-stu-id="e625a-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e625a-116">子要素</span><span class="sxs-lookup"><span data-stu-id="e625a-116">Child Elements</span></span>  
 <span data-ttu-id="e625a-117">なし。</span><span class="sxs-lookup"><span data-stu-id="e625a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e625a-118">親要素</span><span class="sxs-lookup"><span data-stu-id="e625a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e625a-119">要素</span><span class="sxs-lookup"><span data-stu-id="e625a-119">Element</span></span>|<span data-ttu-id="e625a-120">説明</span><span class="sxs-lookup"><span data-stu-id="e625a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e625a-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="e625a-121">\<identity></span></span>](identity.md)|<span data-ttu-id="e625a-122">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="e625a-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e625a-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="e625a-123">Remarks</span></span>  
 <span data-ttu-id="e625a-124">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントで SSPI 認証を実行するときに UPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="e625a-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e625a-125">例</span><span class="sxs-lookup"><span data-stu-id="e625a-125">Example</span></span>  
 <span data-ttu-id="e625a-126">次の構成コードは、クライアントで認証するサービスの UPN を指定します。</span><span class="sxs-lookup"><span data-stu-id="e625a-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="e625a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="e625a-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="e625a-128">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="e625a-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e625a-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="e625a-129">\<identity></span></span>](identity.md)
