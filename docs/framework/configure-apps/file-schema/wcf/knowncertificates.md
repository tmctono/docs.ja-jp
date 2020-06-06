---
title: <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 23fe19258e09e9e8a5e05a94ccef0e40ee1cb5fd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400332"
---
# \<knownCertificates>
<span data-ttu-id="9bdb2-101">セキュリティ トークン サービス (STS) から発行されるセキュリティ資格情報を認証するために提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-101">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="9bdb2-102">構文</span><span class="sxs-lookup"><span data-stu-id="9bdb2-102">Syntax</span></span>  
  
```xml  
<knownCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bdb2-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9bdb2-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9bdb2-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bdb2-105">属性</span><span class="sxs-lookup"><span data-stu-id="9bdb2-105">Attributes</span></span>  
 <span data-ttu-id="9bdb2-106">なし。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9bdb2-107">子要素</span><span class="sxs-lookup"><span data-stu-id="9bdb2-107">Child Elements</span></span>  
  
|<span data-ttu-id="9bdb2-108">要素</span><span class="sxs-lookup"><span data-stu-id="9bdb2-108">Element</span></span>|<span data-ttu-id="9bdb2-109">説明</span><span class="sxs-lookup"><span data-stu-id="9bdb2-109">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-knowncertificates.md)|<span data-ttu-id="9bdb2-110">コレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-110">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9bdb2-111">親要素</span><span class="sxs-lookup"><span data-stu-id="9bdb2-111">Parent Elements</span></span>  
  
|<span data-ttu-id="9bdb2-112">要素</span><span class="sxs-lookup"><span data-stu-id="9bdb2-112">Element</span></span>|<span data-ttu-id="9bdb2-113">説明</span><span class="sxs-lookup"><span data-stu-id="9bdb2-113">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="9bdb2-114">サービス資格情報として発行されるトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-114">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bdb2-115">解説</span><span class="sxs-lookup"><span data-stu-id="9bdb2-115">Remarks</span></span>  
 <span data-ttu-id="9bdb2-116">発行されるトークンのシナリオには、3 つの段階があります。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-116">The issued token scenario has three stages.</span></span> <span data-ttu-id="9bdb2-117">最初の段階では、サービスにアクセスしようとしているクライアントは、*セキュリティで保護されたトークンサービス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-117">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="9bdb2-118">次に、セキュリティ トークン サービスがクライアントを認証し、その後、クライアントにトークン (通常は、SAML (Security Assertions Markup Language) トークン) を発行します。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-118">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="9bdb2-119">最後に、クライアントがトークンを持ってサービスに戻ります。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-119">The client then returns to the service with the token.</span></span> <span data-ttu-id="9bdb2-120">サービスはトークンを調べ、トークンを認証することでクライアントの認証を可能にするデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-120">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="9bdb2-121">トークンを認証するには、セキュリティ トークン サービスで使用される証明書がサービスによって認識されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-121">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="9bdb2-122">要素は、 [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) このようなセキュリティトークンサービス証明書のリポジトリです。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-122">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="9bdb2-123">証明書を追加するには、 [ \<knownCertificates> 要素](knowncertificates.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-123">To add certificates, use the [\<knownCertificates> element](knowncertificates.md).</span></span> <span data-ttu-id="9bdb2-124">次の [\<add>](add-of-knowncertificates.md) 例に示すように、各証明書のを挿入します。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-124">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="9bdb2-125">既定では、証明書はセキュリティ トークン サービスから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-125">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="9bdb2-126">このような "既知" の証明書により、正当なクライアントのみがサービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-126">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="9bdb2-127">フェデレーションサービスによってクライアントが認証されるために必要な条件を確認するには、「[方法: フェデレーションサービスで資格情報を構成](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-127">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="9bdb2-128">フェデレーションシナリオの詳細については、「[フェデレーションと発行済みトークン](../../../wcf/feature-details/federation-and-issued-tokens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-128">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="9bdb2-129">構成のコレクションにデータを設定する方法を示す例については、「」を参照してください [\<add>](add-of-knowncertificates.md) 。</span><span class="sxs-lookup"><span data-stu-id="9bdb2-129">For an example that shows how to populate the collection in configuration, see [\<add>](add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bdb2-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bdb2-130">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<add>](add-of-knowncertificates.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="9bdb2-131">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="9bdb2-131">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9bdb2-132">方法: フェデレーション サービスで資格情報を設定する</span><span class="sxs-lookup"><span data-stu-id="9bdb2-132">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="9bdb2-133">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="9bdb2-133">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="9bdb2-134">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="9bdb2-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-knowncertificates.md)
- [<span data-ttu-id="9bdb2-135">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="9bdb2-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
