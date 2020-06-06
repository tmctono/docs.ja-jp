---
title: <serviceCertificate><clientCredentials>要素の
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399681"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="e649f-102">\<serviceCertificate>\<clientCredentials>要素の</span><span class="sxs-lookup"><span data-stu-id="e649f-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="e649f-103">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="e649f-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="e649f-104">構文</span><span class="sxs-lookup"><span data-stu-id="e649f-104">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e649f-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e649f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e649f-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e649f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e649f-107">属性</span><span class="sxs-lookup"><span data-stu-id="e649f-107">Attributes</span></span>  
 <span data-ttu-id="e649f-108">なし。</span><span class="sxs-lookup"><span data-stu-id="e649f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e649f-109">子要素</span><span class="sxs-lookup"><span data-stu-id="e649f-109">Child Elements</span></span>  
  
|<span data-ttu-id="e649f-110">要素</span><span class="sxs-lookup"><span data-stu-id="e649f-110">Element</span></span>|<span data-ttu-id="e649f-111">説明</span><span class="sxs-lookup"><span data-stu-id="e649f-111">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|<span data-ttu-id="e649f-112">ネゴシエーション プロトコル経由でサービスまたは STS が証明書を提供しないときに使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="e649f-112">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="e649f-113">認証用の (範囲指定された) 特定のサービスにより提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e649f-113">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="e649f-114">このコレクションは一般に、フェデレーション シナリオでセキュリティ トークン サービスのサービス証明書を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e649f-114">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="e649f-115">クライアントで使用されるサービス証明書の認証動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="e649f-115">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e649f-116">親要素</span><span class="sxs-lookup"><span data-stu-id="e649f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e649f-117">要素</span><span class="sxs-lookup"><span data-stu-id="e649f-117">Element</span></span>|<span data-ttu-id="e649f-118">説明</span><span class="sxs-lookup"><span data-stu-id="e649f-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="e649f-119">サービスに対するクライアント自身の認証のためにクライアントによって使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e649f-119">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e649f-120">解説</span><span class="sxs-lookup"><span data-stu-id="e649f-120">Remarks</span></span>  
 <span data-ttu-id="e649f-121">この構成要素は、SSL 認証を使用してサービスから提示された証明書を検証するためにクライアントが使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e649f-121">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="e649f-122">また、このクラスには、メッセージ セキュリティを使用してサービスへのメッセージを暗号化するためにクライアントで明示的に構成される、サービスの証明書も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e649f-122">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="e649f-123">要素の属性 `serviceCertificate` は、の属性と同じです [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) 。</span><span class="sxs-lookup"><span data-stu-id="e649f-123">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e649f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e649f-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="e649f-125">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="e649f-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e649f-126">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e649f-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="e649f-127">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="e649f-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e649f-128">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e649f-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
