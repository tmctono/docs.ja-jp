---
title: <scopedCertificates> 要素
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 73e78a6ca27ed45e1eadc7121987b75f79bc6aa5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670639"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="262f6-102">\<scopedCertificates > 要素</span><span class="sxs-lookup"><span data-stu-id="262f6-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="262f6-103">認証用の (範囲指定された) 特定のサービスにより提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="262f6-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="262f6-104">このコレクションは一般に、フェデレーション シナリオでセキュリティ トークン サービスのサービス証明書を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="262f6-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="262f6-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="262f6-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="262f6-106">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="262f6-106">\<behaviors></span></span>  
<span data-ttu-id="262f6-107">endpointBehaviors セクション</span><span class="sxs-lookup"><span data-stu-id="262f6-107">endpointBehaviors section</span></span>  
<span data-ttu-id="262f6-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="262f6-108">\<behavior></span></span>  
<span data-ttu-id="262f6-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="262f6-109">\<clientCredentials></span></span>  
<span data-ttu-id="262f6-110">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="262f6-110">\<serviceCertificate></span></span>  
<span data-ttu-id="262f6-111">\<scopedCertificates > 要素</span><span class="sxs-lookup"><span data-stu-id="262f6-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="262f6-112">\<追加 > 要素の\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="262f6-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="262f6-113">構文</span><span class="sxs-lookup"><span data-stu-id="262f6-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="262f6-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="262f6-114">Attributes and Elements</span></span>  
 <span data-ttu-id="262f6-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="262f6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="262f6-116">属性</span><span class="sxs-lookup"><span data-stu-id="262f6-116">Attributes</span></span>  
 <span data-ttu-id="262f6-117">なし。</span><span class="sxs-lookup"><span data-stu-id="262f6-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="262f6-118">子要素</span><span class="sxs-lookup"><span data-stu-id="262f6-118">Child Elements</span></span>  
  
|<span data-ttu-id="262f6-119">要素</span><span class="sxs-lookup"><span data-stu-id="262f6-119">Element</span></span>|<span data-ttu-id="262f6-120">説明</span><span class="sxs-lookup"><span data-stu-id="262f6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="262f6-121">\<add></span><span class="sxs-lookup"><span data-stu-id="262f6-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|<span data-ttu-id="262f6-122">範囲指定された証明書のコレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="262f6-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="262f6-123">親要素</span><span class="sxs-lookup"><span data-stu-id="262f6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="262f6-124">要素</span><span class="sxs-lookup"><span data-stu-id="262f6-124">Element</span></span>|<span data-ttu-id="262f6-125">説明</span><span class="sxs-lookup"><span data-stu-id="262f6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="262f6-126">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="262f6-126">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="262f6-127">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="262f6-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="262f6-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="262f6-128">Remarks</span></span>  
 <span data-ttu-id="262f6-129">このコレクションを使用すると、クライアントは、通信するサービスの URL に基づいて、使用するサービス証明書を構成できます。</span><span class="sxs-lookup"><span data-stu-id="262f6-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="262f6-130">これは、クライアントが複数のサービス (エンド サービスと中間セキュリティ トークン サービス) と通信している可能性がある発行済みトークンのシナリオで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="262f6-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="262f6-131">証明書に基づくメッセージ セキュリティを使用したバインドにおいて、この証明書を使用してサービスへのメッセージを暗号化します。サービスがクライアントへの応答に署名する際には、この証明書を使用することが要求されます。</span><span class="sxs-lookup"><span data-stu-id="262f6-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="262f6-132">バインディングにサービスの証明書が必要で、サービスの URL に対する特定の証明書が ScopedCertificates 内に存在しない場合は、既定の証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="262f6-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="262f6-133">詳細については、の スコープの証明書"セクションを参照してください。[方法。フェデレーション クライアントを作成](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)です。</span><span class="sxs-lookup"><span data-stu-id="262f6-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="262f6-134">例</span><span class="sxs-lookup"><span data-stu-id="262f6-134">Example</span></span>  
 <span data-ttu-id="262f6-135">次の例は、ドメインの名前のエンドポイントと通信するときに使用するクライアントのサービス証明書を指定する `http://www.contoso.com` HTTP プロトコル経由します。</span><span class="sxs-lookup"><span data-stu-id="262f6-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="262f6-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="262f6-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="262f6-137">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="262f6-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="262f6-138">方法: フェデレーション クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="262f6-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="262f6-139">\<add></span><span class="sxs-lookup"><span data-stu-id="262f6-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)
- [<span data-ttu-id="262f6-140">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="262f6-140">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="262f6-141">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="262f6-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
