---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 9e7b845d39495dba1d1a19af95faf308b8b8c0fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769812"
---
# <a name="userprincipalname"></a><span data-ttu-id="4330d-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="4330d-101">\<userPrincipalName></span></span>
<span data-ttu-id="4330d-102">クライアントで認証するサービスのユーザー プリンシパル名 (UPN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4330d-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="4330d-103">UPN を設定する方法についての詳細については、次を参照してください。[サービス Id と認証](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="4330d-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="4330d-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="4330d-104">\<identity></span></span>  
<span data-ttu-id="4330d-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="4330d-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4330d-106">構文</span><span class="sxs-lookup"><span data-stu-id="4330d-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4330d-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4330d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4330d-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4330d-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4330d-109">属性</span><span class="sxs-lookup"><span data-stu-id="4330d-109">Attributes</span></span>  
  
|<span data-ttu-id="4330d-110">属性</span><span class="sxs-lookup"><span data-stu-id="4330d-110">Attribute</span></span>|<span data-ttu-id="4330d-111">説明</span><span class="sxs-lookup"><span data-stu-id="4330d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4330d-112">value</span><span class="sxs-lookup"><span data-stu-id="4330d-112">value</span></span>|<span data-ttu-id="4330d-113">ユーザー アカウント名 (ユーザー ログイン名と呼ばれることもある) と、ユーザー アカウントの検索範囲のドメインを識別するドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="4330d-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="4330d-114">これは、Windows ドメインにログオンするための標準的使用方法です。</span><span class="sxs-lookup"><span data-stu-id="4330d-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="4330d-115">形式: someone@example.com (電子メール アドレス) です。</span><span class="sxs-lookup"><span data-stu-id="4330d-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4330d-116">子要素</span><span class="sxs-lookup"><span data-stu-id="4330d-116">Child Elements</span></span>  
 <span data-ttu-id="4330d-117">なし。</span><span class="sxs-lookup"><span data-stu-id="4330d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4330d-118">親要素</span><span class="sxs-lookup"><span data-stu-id="4330d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4330d-119">要素</span><span class="sxs-lookup"><span data-stu-id="4330d-119">Element</span></span>|<span data-ttu-id="4330d-120">説明</span><span class="sxs-lookup"><span data-stu-id="4330d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4330d-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="4330d-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="4330d-122">クライアントで認証するサービスの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="4330d-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4330d-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="4330d-123">Remarks</span></span>  
 <span data-ttu-id="4330d-124">この id を持つエンドポイントに接続するセキュリティで保護された Windows Communication Foundation (WCF) クライアントは、エンドポイントの SSPI 認証を実行するときに、UPN を使用します。</span><span class="sxs-lookup"><span data-stu-id="4330d-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4330d-125">例</span><span class="sxs-lookup"><span data-stu-id="4330d-125">Example</span></span>  
 <span data-ttu-id="4330d-126">次の構成コードは、クライアントで認証するサービスの UPN を指定します。</span><span class="sxs-lookup"><span data-stu-id="4330d-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="4330d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="4330d-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="4330d-128">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="4330d-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4330d-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="4330d-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
