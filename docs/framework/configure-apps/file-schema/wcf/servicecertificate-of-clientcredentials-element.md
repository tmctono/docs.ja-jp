---
title: <serviceCertificate> <clientCredentials>要素
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4fe196ef8737c7abde939e36c2bb7afd5a0d86b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670301"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="7ab4d-102">\<serviceCertificate > の\<clientCredentials > 要素</span><span class="sxs-lookup"><span data-stu-id="7ab4d-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="7ab4d-103">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
 <span data-ttu-id="7ab4d-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7ab4d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7ab4d-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="7ab4d-105">\<behaviors></span></span>  
<span data-ttu-id="7ab4d-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="7ab4d-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="7ab4d-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7ab4d-107">\<behavior></span></span>  
<span data-ttu-id="7ab4d-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7ab4d-108">\<clientCredentials></span></span>  
<span data-ttu-id="7ab4d-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="7ab4d-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab4d-110">構文</span><span class="sxs-lookup"><span data-stu-id="7ab4d-110">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ab4d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7ab4d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7ab4d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ab4d-113">属性</span><span class="sxs-lookup"><span data-stu-id="7ab4d-113">Attributes</span></span>  
 <span data-ttu-id="7ab4d-114">なし。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ab4d-115">子要素</span><span class="sxs-lookup"><span data-stu-id="7ab4d-115">Child Elements</span></span>  
  
|<span data-ttu-id="7ab4d-116">要素</span><span class="sxs-lookup"><span data-stu-id="7ab4d-116">Element</span></span>|<span data-ttu-id="7ab4d-117">説明</span><span class="sxs-lookup"><span data-stu-id="7ab4d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ab4d-118">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="7ab4d-118">\<defaultCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|<span data-ttu-id="7ab4d-119">ネゴシエーション プロトコル経由でサービスまたは STS が証明書を提供しないときに使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-119">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="7ab4d-120">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="7ab4d-120">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="7ab4d-121">認証用の (範囲指定された) 特定のサービスにより提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-121">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="7ab4d-122">このコレクションは一般に、フェデレーション シナリオでセキュリティ トークン サービスのサービス証明書を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-122">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="7ab4d-123">\<authentication></span><span class="sxs-lookup"><span data-stu-id="7ab4d-123">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|<span data-ttu-id="7ab4d-124">クライアントで使用されるサービス証明書の認証動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-124">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ab4d-125">親要素</span><span class="sxs-lookup"><span data-stu-id="7ab4d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7ab4d-126">要素</span><span class="sxs-lookup"><span data-stu-id="7ab4d-126">Element</span></span>|<span data-ttu-id="7ab4d-127">説明</span><span class="sxs-lookup"><span data-stu-id="7ab4d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ab4d-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7ab4d-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="7ab4d-129">サービスに対するクライアント自身の認証のためにクライアントによって使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-129">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ab4d-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="7ab4d-130">Remarks</span></span>  
 <span data-ttu-id="7ab4d-131">この構成要素は、SSL 認証を使用してサービスから提示された証明書を検証するためにクライアントが使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-131">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="7ab4d-132">また、このクラスには、メッセージ セキュリティを使用してサービスへのメッセージを暗号化するためにクライアントで明示的に構成される、サービスの証明書も含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-132">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="7ab4d-133">属性、`serviceCertificate`要素は同一の属性には、 [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="7ab4d-133">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab4d-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ab4d-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="7ab4d-135">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="7ab4d-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7ab4d-136">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="7ab4d-136">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="7ab4d-137">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="7ab4d-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7ab4d-138">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="7ab4d-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
