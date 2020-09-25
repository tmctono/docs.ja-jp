---
title: <issuedTokenAuthentication> の <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 88657b6982108596c8d9030161390f76fcff6609
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202475"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a><span data-ttu-id="fabc6-102">\<issuedTokenAuthentication> の \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="fabc6-102">\<issuedTokenAuthentication> of \<serviceCredentials></span></span>

<span data-ttu-id="fabc6-103">サービス資格情報として発行されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-103">Specifies a custom token issued as a service credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="fabc6-104">構文</span><span class="sxs-lookup"><span data-stu-id="fabc6-104">Syntax</span></span>  
  
```xml  
<issuedTokenAuthentication allowUntrustedRsaIssuers="Boolean"
                           audienceUriMode="Always/BearerKeyOnly/Never"
                           customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                           certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                           revocationMode="NoCheck/Online/Offline"
                           samlSerializer="String"
                           trustedStoreLocation="CurrentUser/LocalMachine">
  <allowedAudienceUris>
    <add allowedAudienceUri="String" />
  </allowedAudienceUris>
  <knownCertificates>
    <add findValue="String"
         storeLocation="CurrentUser/LocalMachine"
         storeName=" CurrentUser/LocalMachine"
         x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fabc6-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fabc6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fabc6-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fabc6-107">属性</span><span class="sxs-lookup"><span data-stu-id="fabc6-107">Attributes</span></span>  
  
|<span data-ttu-id="fabc6-108">属性</span><span class="sxs-lookup"><span data-stu-id="fabc6-108">Attribute</span></span>|<span data-ttu-id="fabc6-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="fabc6-109">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="fabc6-110"><xref:System.IdentityModel.Tokens.SamlSecurityToken> インスタンスにより有効と見なされるように、<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> セキュリティ トークンのターゲットとなる URI のセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-110">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="fabc6-111">この属性の使い方の詳細については、「<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fabc6-111">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="fabc6-112">信頼できない RSA 証明書の発行者を許可するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="fabc6-112">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="fabc6-113">証明書は、信頼性を検証する証明機関 (CA) によって署名されます。</span><span class="sxs-lookup"><span data-stu-id="fabc6-113">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="fabc6-114">信頼できない発行者とは、証明書の署名が信頼できると指定されていない CA です。</span><span class="sxs-lookup"><span data-stu-id="fabc6-114">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="fabc6-115"><xref:System.IdentityModel.Tokens.SamlSecurityToken> セキュリティ トークンの <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> を検証するかどうかを指定する値を取得します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-115">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="fabc6-116">この値は、<xref:System.IdentityModel.Selectors.AudienceUriMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="fabc6-116">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="fabc6-117">この属性の使い方の詳細については、「<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fabc6-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="fabc6-118">証明書検証モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-118">Sets the certificate validation mode.</span></span> <span data-ttu-id="fabc6-119"><xref:System.ServiceModel.Security.X509CertificateValidationMode> の有効な値のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="fabc6-119">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="fabc6-120">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fabc6-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="fabc6-121">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="fabc6-121">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="fabc6-122">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="fabc6-122">Optional string.</span></span> <span data-ttu-id="fabc6-123">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="fabc6-123">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="fabc6-124">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fabc6-124">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="fabc6-125">失効状態の検証を行うかどうかに加え、検証をオンラインで実行するか、オフラインで実行するかを指定する失効モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-125">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="fabc6-126">この属性は <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="fabc6-126">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="fabc6-127">サービス資格情報に使用される SamlSerializer の型を指定する省略可能な文字列属性。</span><span class="sxs-lookup"><span data-stu-id="fabc6-127">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="fabc6-128">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="fabc6-128">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="fabc6-129">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="fabc6-129">Optional enumeration.</span></span> <span data-ttu-id="fabc6-130">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="fabc6-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fabc6-131">子要素</span><span class="sxs-lookup"><span data-stu-id="fabc6-131">Child Elements</span></span>  
  
|<span data-ttu-id="fabc6-132">要素</span><span class="sxs-lookup"><span data-stu-id="fabc6-132">Element</span></span>|<span data-ttu-id="fabc6-133">説明</span><span class="sxs-lookup"><span data-stu-id="fabc6-133">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="fabc6-134">サービス資格情報の信頼できる発行者を指定する <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> 要素のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-134">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fabc6-135">親要素</span><span class="sxs-lookup"><span data-stu-id="fabc6-135">Parent Elements</span></span>  
  
|<span data-ttu-id="fabc6-136">要素</span><span class="sxs-lookup"><span data-stu-id="fabc6-136">Element</span></span>|<span data-ttu-id="fabc6-137">説明</span><span class="sxs-lookup"><span data-stu-id="fabc6-137">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="fabc6-138">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-138">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fabc6-139">解説</span><span class="sxs-lookup"><span data-stu-id="fabc6-139">Remarks</span></span>  

 <span data-ttu-id="fabc6-140">発行されるトークンのシナリオには、3 つの段階があります。</span><span class="sxs-lookup"><span data-stu-id="fabc6-140">The issued token scenario has three stages.</span></span> <span data-ttu-id="fabc6-141">最初の段階では、サービスにアクセスしようとしているクライアントは、 *セキュリティで保護されたトークンサービス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="fabc6-141">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="fabc6-142">次に、セキュリティ トークン サービスがクライアントを認証し、その後、クライアントにトークン (通常は、SAML (Security Assertions Markup Language) トークン) を発行します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-142">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="fabc6-143">最後に、クライアントがトークンを持ってサービスに戻ります。</span><span class="sxs-lookup"><span data-stu-id="fabc6-143">The client then returns to the service with the token.</span></span> <span data-ttu-id="fabc6-144">サービスはトークンを調べ、トークンを認証することでクライアントの認証を可能にするデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-144">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="fabc6-145">トークンを認証するには、セキュリティ トークン サービスで使用される証明書がサービスによって認識されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fabc6-145">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="fabc6-146">この要素は、このようなセキュリティ トークン サービス証明書のリポジトリです。</span><span class="sxs-lookup"><span data-stu-id="fabc6-146">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="fabc6-147">証明書を追加するには、を使用し [\<knownCertificates>](knowncertificates.md) ます。</span><span class="sxs-lookup"><span data-stu-id="fabc6-147">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="fabc6-148">次の [\<add>](add-of-knowncertificates.md) 例に示すように、各証明書のを挿入します。</span><span class="sxs-lookup"><span data-stu-id="fabc6-148">Insert an [\<add>](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="fabc6-149">既定では、証明書はセキュリティ トークン サービスから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fabc6-149">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="fabc6-150">このような "既知" の証明書により、正当なクライアントのみがサービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="fabc6-150">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="fabc6-151">この構成要素の使用方法の詳細については、「 [方法: フェデレーションサービスで資格情報を構成する](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fabc6-151">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabc6-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="fabc6-152">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [<span data-ttu-id="fabc6-153">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="fabc6-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fabc6-154">方法: フェデレーション サービスで資格情報を設定する</span><span class="sxs-lookup"><span data-stu-id="fabc6-154">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
