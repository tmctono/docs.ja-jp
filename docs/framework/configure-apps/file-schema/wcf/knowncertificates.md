---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 4c1dc15621138aa692f0a30d285f729c2bd670d3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274119"
---
# <a name="knowncertificates"></a><span data-ttu-id="da6f8-101">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="da6f8-101">\<knownCertificates></span></span>
<span data-ttu-id="da6f8-102">セキュリティ トークン サービス (STS) から発行されるセキュリティ資格情報を認証するために提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="da6f8-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="da6f8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="da6f8-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="da6f8-104">\<behaviors></span></span>  
<span data-ttu-id="da6f8-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="da6f8-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="da6f8-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="da6f8-106">\<behavior></span></span>  
<span data-ttu-id="da6f8-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="da6f8-107">\<serviceCredentials></span></span>  
<span data-ttu-id="da6f8-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="da6f8-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="da6f8-109">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="da6f8-109">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da6f8-110">構文</span><span class="sxs-lookup"><span data-stu-id="da6f8-110">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da6f8-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="da6f8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="da6f8-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da6f8-113">属性</span><span class="sxs-lookup"><span data-stu-id="da6f8-113">Attributes</span></span>  
 <span data-ttu-id="da6f8-114">なし。</span><span class="sxs-lookup"><span data-stu-id="da6f8-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da6f8-115">子要素</span><span class="sxs-lookup"><span data-stu-id="da6f8-115">Child Elements</span></span>  
  
|<span data-ttu-id="da6f8-116">要素</span><span class="sxs-lookup"><span data-stu-id="da6f8-116">Element</span></span>|<span data-ttu-id="da6f8-117">説明</span><span class="sxs-lookup"><span data-stu-id="da6f8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da6f8-118">\<add></span><span class="sxs-lookup"><span data-stu-id="da6f8-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="da6f8-119">コレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-119">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da6f8-120">親要素</span><span class="sxs-lookup"><span data-stu-id="da6f8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="da6f8-121">要素</span><span class="sxs-lookup"><span data-stu-id="da6f8-121">Element</span></span>|<span data-ttu-id="da6f8-122">説明</span><span class="sxs-lookup"><span data-stu-id="da6f8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da6f8-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="da6f8-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="da6f8-124">サービス資格情報として発行されるトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da6f8-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="da6f8-125">Remarks</span></span>  
 <span data-ttu-id="da6f8-126">発行されるトークンのシナリオには、3 つの段階があります。</span><span class="sxs-lookup"><span data-stu-id="da6f8-126">The issued token scenario has three stages.</span></span> <span data-ttu-id="da6f8-127">最初の段階でのサービスにアクセスしようとしています。 クライアントが参照される、*セキュア トークン サービス*します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-127">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="da6f8-128">次に、セキュリティ トークン サービスがクライアントを認証し、その後、クライアントにトークン (通常は、SAML (Security Assertions Markup Language) トークン) を発行します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-128">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="da6f8-129">最後に、クライアントがトークンを持ってサービスに戻ります。</span><span class="sxs-lookup"><span data-stu-id="da6f8-129">The client then returns to the service with the token.</span></span> <span data-ttu-id="da6f8-130">サービスはトークンを調べ、トークンを認証することでクライアントの認証を可能にするデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-130">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="da6f8-131">トークンを認証するには、セキュリティ トークン サービスで使用される証明書がサービスによって認識されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="da6f8-131">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="da6f8-132">[ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)要素はこのようなセキュリティ トークン サービス証明書のリポジトリです。</span><span class="sxs-lookup"><span data-stu-id="da6f8-132">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="da6f8-133">証明書を追加するには、使用、 [ \<knownCertificates > 要素](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-133">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="da6f8-134">挿入、 [\<追加 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)各証明書、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="da6f8-134">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="da6f8-135">既定では、証明書はセキュリティ トークン サービスから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da6f8-135">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="da6f8-136">このような "既知" の証明書により、正当なクライアントのみがサービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="da6f8-136">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="da6f8-137">この構成要素の使い方の詳細についてと、フェデレーション サービスで認証するクライアントに必要な条件を確認するを参照してください。[方法。フェデレーション サービスで資格情報を構成](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-137">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="da6f8-138">フェデレーション シナリオの詳細については、[フェデレーションと発行されたトークン](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da6f8-138">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="da6f8-139">構成のコレクションを設定する方法を示しますたとえば、[\<追加 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da6f8-139">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da6f8-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="da6f8-140">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="da6f8-141">\<add></span><span class="sxs-lookup"><span data-stu-id="da6f8-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="da6f8-142">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="da6f8-142">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="da6f8-143">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="da6f8-143">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="da6f8-144">方法: フェデレーション サービスで資格情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="da6f8-144">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="da6f8-145">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="da6f8-145">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="da6f8-146">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="da6f8-146">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="da6f8-147">\<add></span><span class="sxs-lookup"><span data-stu-id="da6f8-147">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)
- [<span data-ttu-id="da6f8-148">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="da6f8-148">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
