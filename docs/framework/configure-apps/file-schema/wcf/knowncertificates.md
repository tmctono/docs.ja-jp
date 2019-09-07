---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400332"
---
# <a name="knowncertificates"></a><span data-ttu-id="138c3-101">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="138c3-101">\<knownCertificates></span></span>
<span data-ttu-id="138c3-102">セキュリティ トークン サービス (STS) から発行されるセキュリティ資格情報を認証するために提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="138c3-102">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
<span data-ttu-id="138c3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="138c3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="138c3-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="138c3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="138c3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="138c3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="138c3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="138c3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="138c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="138c3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="138c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="138c3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="138c3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenAuthentication >** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="138c3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="138c3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<knownCertificates >**</span><span class="sxs-lookup"><span data-stu-id="138c3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="138c3-111">構文</span><span class="sxs-lookup"><span data-stu-id="138c3-111">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="138c3-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="138c3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="138c3-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="138c3-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="138c3-114">属性</span><span class="sxs-lookup"><span data-stu-id="138c3-114">Attributes</span></span>  
 <span data-ttu-id="138c3-115">なし。</span><span class="sxs-lookup"><span data-stu-id="138c3-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="138c3-116">子要素</span><span class="sxs-lookup"><span data-stu-id="138c3-116">Child Elements</span></span>  
  
|<span data-ttu-id="138c3-117">要素</span><span class="sxs-lookup"><span data-stu-id="138c3-117">Element</span></span>|<span data-ttu-id="138c3-118">説明</span><span class="sxs-lookup"><span data-stu-id="138c3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="138c3-119">\<add></span><span class="sxs-lookup"><span data-stu-id="138c3-119">\<add></span></span>](add-of-knowncertificates.md)|<span data-ttu-id="138c3-120">コレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="138c3-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="138c3-121">親要素</span><span class="sxs-lookup"><span data-stu-id="138c3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="138c3-122">要素</span><span class="sxs-lookup"><span data-stu-id="138c3-122">Element</span></span>|<span data-ttu-id="138c3-123">説明</span><span class="sxs-lookup"><span data-stu-id="138c3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="138c3-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="138c3-124">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="138c3-125">サービス資格情報として発行されるトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="138c3-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="138c3-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="138c3-126">Remarks</span></span>  
 <span data-ttu-id="138c3-127">発行されるトークンのシナリオには、3 つの段階があります。</span><span class="sxs-lookup"><span data-stu-id="138c3-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="138c3-128">最初の段階では、サービスにアクセスしようとしているクライアントは、*セキュリティで保護されたトークンサービス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="138c3-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="138c3-129">次に、セキュリティ トークン サービスがクライアントを認証し、その後、クライアントにトークン (通常は、SAML (Security Assertions Markup Language) トークン) を発行します。</span><span class="sxs-lookup"><span data-stu-id="138c3-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="138c3-130">最後に、クライアントがトークンを持ってサービスに戻ります。</span><span class="sxs-lookup"><span data-stu-id="138c3-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="138c3-131">サービスはトークンを調べ、トークンを認証することでクライアントの認証を可能にするデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="138c3-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="138c3-132">トークンを認証するには、セキュリティ トークン サービスで使用される証明書がサービスによって認識されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="138c3-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="138c3-133">IssuedTokenAuthentication > 要素は、このようなセキュリティトークンサービス証明書のリポジトリです。 [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="138c3-133">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="138c3-134">証明書を追加するには、 [ \<knowncertificates > 要素](knowncertificates.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="138c3-134">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="138c3-135">次の例に示すように、各証明書の[ add>を挿入します。\<](add-of-knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="138c3-135">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="138c3-136">既定では、証明書はセキュリティ トークン サービスから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="138c3-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="138c3-137">このような "既知" の証明書により、正当なクライアントのみがサービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="138c3-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="138c3-138">フェデレーションサービスによってクライアントが認証されるために必要な条件を確認し、この構成要素の使用方法の詳細[については、「」を参照してください。フェデレーションサービス](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)で資格情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="138c3-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="138c3-139">フェデレーションシナリオの詳細については、「[フェデレーションと発行済みトークン](../../../wcf/feature-details/federation-and-issued-tokens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="138c3-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="138c3-140">構成のコレクションにデータを設定する方法を示す例については、「 [ \<> の追加](add-of-knowncertificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="138c3-140">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138c3-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="138c3-141">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="138c3-142">\<add></span><span class="sxs-lookup"><span data-stu-id="138c3-142">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="138c3-143">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="138c3-143">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="138c3-144">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="138c3-144">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="138c3-145">方法: フェデレーションサービスで資格情報を構成する</span><span class="sxs-lookup"><span data-stu-id="138c3-145">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="138c3-146">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="138c3-146">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="138c3-147">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="138c3-147">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="138c3-148">\<add></span><span class="sxs-lookup"><span data-stu-id="138c3-148">\<add></span></span>](add-of-knowncertificates.md)
- [<span data-ttu-id="138c3-149">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="138c3-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
