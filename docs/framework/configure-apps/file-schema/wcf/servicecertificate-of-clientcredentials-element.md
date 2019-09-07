---
title: <serviceCertificate> <clientCredentials>要素
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399681"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="7d4f3-102">\<clientCredentials > 要素\<の serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="7d4f3-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="7d4f3-103">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
<span data-ttu-id="7d4f3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d4f3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d4f3-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7d4f3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7d4f3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d4f3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7d4f3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d4f3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="7d4f3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d4f3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="7d4f3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="7d4f3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="7d4f3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate >**</span><span class="sxs-lookup"><span data-stu-id="7d4f3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d4f3-111">構文</span><span class="sxs-lookup"><span data-stu-id="7d4f3-111">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d4f3-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7d4f3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7d4f3-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d4f3-114">属性</span><span class="sxs-lookup"><span data-stu-id="7d4f3-114">Attributes</span></span>  
 <span data-ttu-id="7d4f3-115">なし。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d4f3-116">子要素</span><span class="sxs-lookup"><span data-stu-id="7d4f3-116">Child Elements</span></span>  
  
|<span data-ttu-id="7d4f3-117">要素</span><span class="sxs-lookup"><span data-stu-id="7d4f3-117">Element</span></span>|<span data-ttu-id="7d4f3-118">説明</span><span class="sxs-lookup"><span data-stu-id="7d4f3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d4f3-119">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="7d4f3-119">\<defaultCertificate></span></span>](defaultcertificate-element.md)|<span data-ttu-id="7d4f3-120">ネゴシエーション プロトコル経由でサービスまたは STS が証明書を提供しないときに使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-120">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="7d4f3-121">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="7d4f3-121">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="7d4f3-122">認証用の (範囲指定された) 特定のサービスにより提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-122">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="7d4f3-123">このコレクションは一般に、フェデレーション シナリオでセキュリティ トークン サービスのサービス証明書を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-123">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="7d4f3-124">\<authentication></span><span class="sxs-lookup"><span data-stu-id="7d4f3-124">\<authentication></span></span>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="7d4f3-125">クライアントで使用されるサービス証明書の認証動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-125">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d4f3-126">親要素</span><span class="sxs-lookup"><span data-stu-id="7d4f3-126">Parent Elements</span></span>  
  
|<span data-ttu-id="7d4f3-127">要素</span><span class="sxs-lookup"><span data-stu-id="7d4f3-127">Element</span></span>|<span data-ttu-id="7d4f3-128">説明</span><span class="sxs-lookup"><span data-stu-id="7d4f3-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d4f3-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7d4f3-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="7d4f3-130">サービスに対するクライアント自身の認証のためにクライアントによって使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-130">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d4f3-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d4f3-131">Remarks</span></span>  
 <span data-ttu-id="7d4f3-132">この構成要素は、SSL 認証を使用してサービスから提示された証明書を検証するためにクライアントが使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-132">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="7d4f3-133">また、このクラスには、メッセージ セキュリティを使用してサービスへのメッセージを暗号化するためにクライアントで明示的に構成される、サービスの証明書も含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-133">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="7d4f3-134">`serviceCertificate`要素の属性は、 [ \<clientCertificate >](clientcertificate-of-clientcredentials-element.md)の属性と同じです。</span><span class="sxs-lookup"><span data-stu-id="7d4f3-134">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d4f3-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d4f3-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="7d4f3-136">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="7d4f3-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7d4f3-137">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="7d4f3-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7d4f3-138">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="7d4f3-138">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7d4f3-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="7d4f3-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
