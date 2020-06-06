---
title: <scopedCertificates> 要素
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 3c06159709df0afe2a475de1e186b0114af32bc2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399952"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="0d649-102">\<scopedCertificates> 要素</span><span class="sxs-lookup"><span data-stu-id="0d649-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="0d649-103">認証用の (範囲指定された) 特定のサービスにより提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="0d649-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="0d649-104">このコレクションは一般に、フェデレーション シナリオでセキュリティ トークン サービスのサービス証明書を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d649-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopedCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="0d649-105">構文</span><span class="sxs-lookup"><span data-stu-id="0d649-105">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d649-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0d649-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0d649-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d649-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d649-108">属性</span><span class="sxs-lookup"><span data-stu-id="0d649-108">Attributes</span></span>  
 <span data-ttu-id="0d649-109">なし。</span><span class="sxs-lookup"><span data-stu-id="0d649-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0d649-110">子要素</span><span class="sxs-lookup"><span data-stu-id="0d649-110">Child Elements</span></span>  
  
|<span data-ttu-id="0d649-111">要素</span><span class="sxs-lookup"><span data-stu-id="0d649-111">Element</span></span>|<span data-ttu-id="0d649-112">説明</span><span class="sxs-lookup"><span data-stu-id="0d649-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-scopedcertificates-element.md)|<span data-ttu-id="0d649-113">範囲指定された証明書のコレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="0d649-113">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d649-114">親要素</span><span class="sxs-lookup"><span data-stu-id="0d649-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0d649-115">要素</span><span class="sxs-lookup"><span data-stu-id="0d649-115">Element</span></span>|<span data-ttu-id="0d649-116">説明</span><span class="sxs-lookup"><span data-stu-id="0d649-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="0d649-117">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d649-117">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d649-118">解説</span><span class="sxs-lookup"><span data-stu-id="0d649-118">Remarks</span></span>  
 <span data-ttu-id="0d649-119">このコレクションを使用すると、クライアントは、通信するサービスの URL に基づいて、使用するサービス証明書を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0d649-119">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="0d649-120">これは、クライアントが複数のサービス (エンド サービスと中間セキュリティ トークン サービス) と通信している可能性がある発行済みトークンのシナリオで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="0d649-120">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="0d649-121">証明書に基づくメッセージ セキュリティを使用したバインドにおいて、この証明書を使用してサービスへのメッセージを暗号化します。サービスがクライアントへの応答に署名する際には、この証明書を使用することが要求されます。</span><span class="sxs-lookup"><span data-stu-id="0d649-121">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="0d649-122">バインディングにサービスの証明書が必要で、サービスの URL に対する特定の証明書が ScopedCertificates 内に存在しない場合は、既定の証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d649-122">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="0d649-123">詳細については、「[方法: フェデレーションクライアントを作成](../../../wcf/feature-details/how-to-create-a-federated-client.md)する」の「スコープ付き証明書」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d649-123">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d649-124">例</span><span class="sxs-lookup"><span data-stu-id="0d649-124">Example</span></span>  
 <span data-ttu-id="0d649-125">次の例では、HTTP プロトコル経由でドメイン名を持つエンドポイントと通信するときにクライアントが使用するサービス証明書を指定し `http://www.contoso.com` ます。</span><span class="sxs-lookup"><span data-stu-id="0d649-125">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="0d649-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d649-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="0d649-127">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="0d649-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0d649-128">方法: フェデレーション クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="0d649-128">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [\<add>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="0d649-129">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0d649-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0d649-130">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0d649-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
