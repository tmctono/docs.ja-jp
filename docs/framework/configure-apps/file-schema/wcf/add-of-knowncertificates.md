---
title: <add> の <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 453593918de15613edb801cca8a16c9dbf71aa90
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176085"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="6fdd9-102">\<add> の \<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="6fdd9-102">\<add> of \<knownCertificates></span></span>

<span data-ttu-id="6fdd9-103">既知の証明書のコレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="6fdd9-104">構文</span><span class="sxs-lookup"><span data-stu-id="6fdd9-104">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6fdd9-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6fdd9-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6fdd9-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6fdd9-107">属性</span><span class="sxs-lookup"><span data-stu-id="6fdd9-107">Attributes</span></span>  
  
|<span data-ttu-id="6fdd9-108">属性</span><span class="sxs-lookup"><span data-stu-id="6fdd9-108">Attribute</span></span>|<span data-ttu-id="6fdd9-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="6fdd9-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6fdd9-110">findValue</span><span class="sxs-lookup"><span data-stu-id="6fdd9-110">findValue</span></span>|<span data-ttu-id="6fdd9-111">文字列。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-111">String.</span></span> <span data-ttu-id="6fdd9-112">検索する値。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-112">The value to search for.</span></span>|  
|<span data-ttu-id="6fdd9-113">storeLocation</span><span class="sxs-lookup"><span data-stu-id="6fdd9-113">storeLocation</span></span>|<span data-ttu-id="6fdd9-114">列挙値。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-114">Enumeration.</span></span> <span data-ttu-id="6fdd9-115">検索する 2 つの格納場所のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-115">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="6fdd9-116">storeName</span><span class="sxs-lookup"><span data-stu-id="6fdd9-116">storeName</span></span>|<span data-ttu-id="6fdd9-117">列挙値。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-117">Enumeration.</span></span> <span data-ttu-id="6fdd9-118">検索するシステム ストアのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-118">One of the system stores to search.</span></span>|  
|<span data-ttu-id="6fdd9-119">x509FindType</span><span class="sxs-lookup"><span data-stu-id="6fdd9-119">x509FindType</span></span>|<span data-ttu-id="6fdd9-120">列挙値。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-120">Enumeration.</span></span> <span data-ttu-id="6fdd9-121">検索する証明書フィールドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-121">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="6fdd9-122">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="6fdd9-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="6fdd9-123">値</span><span class="sxs-lookup"><span data-stu-id="6fdd9-123">Value</span></span>|<span data-ttu-id="6fdd9-124">説明</span><span class="sxs-lookup"><span data-stu-id="6fdd9-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6fdd9-125">String</span><span class="sxs-lookup"><span data-stu-id="6fdd9-125">String</span></span>|<span data-ttu-id="6fdd9-126">値は、検索されるフィールド (X509FindType 属性により指定される) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="6fdd9-127">たとえば、サムプリント検索する場合、値は 16 進数の文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="6fdd9-128">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="6fdd9-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="6fdd9-129">値</span><span class="sxs-lookup"><span data-stu-id="6fdd9-129">Value</span></span>|<span data-ttu-id="6fdd9-130">[説明]</span><span class="sxs-lookup"><span data-stu-id="6fdd9-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6fdd9-131">列挙</span><span class="sxs-lookup"><span data-stu-id="6fdd9-131">Enumeration</span></span>|<span data-ttu-id="6fdd9-132">値は、FindByThumbprint、FindBySubjectName、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName、FindByApplicationPolicy、FindByCertificatePolicy、FindByExtension、FindByKeyUsage、FindBySubjectKeyIdentifier です。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="6fdd9-133">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="6fdd9-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="6fdd9-134">値</span><span class="sxs-lookup"><span data-stu-id="6fdd9-134">Value</span></span>|<span data-ttu-id="6fdd9-135">[説明]</span><span class="sxs-lookup"><span data-stu-id="6fdd9-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6fdd9-136">列挙</span><span class="sxs-lookup"><span data-stu-id="6fdd9-136">Enumeration</span></span>|<span data-ttu-id="6fdd9-137">CurrentUser または LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="6fdd9-138">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="6fdd9-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="6fdd9-139">値</span><span class="sxs-lookup"><span data-stu-id="6fdd9-139">Value</span></span>|<span data-ttu-id="6fdd9-140">[説明]</span><span class="sxs-lookup"><span data-stu-id="6fdd9-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6fdd9-141">列挙</span><span class="sxs-lookup"><span data-stu-id="6fdd9-141">Enumeration</span></span>|<span data-ttu-id="6fdd9-142">値は、AddressBook、AuthRoot、CertificateAuthority、Disallowed、My、Root、TrustedPeople、および TrustedPublisher です。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6fdd9-143">子要素</span><span class="sxs-lookup"><span data-stu-id="6fdd9-143">Child Elements</span></span>  

 <span data-ttu-id="6fdd9-144">なし。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6fdd9-145">親要素</span><span class="sxs-lookup"><span data-stu-id="6fdd9-145">Parent Elements</span></span>  
  
|<span data-ttu-id="6fdd9-146">要素</span><span class="sxs-lookup"><span data-stu-id="6fdd9-146">Element</span></span>|<span data-ttu-id="6fdd9-147">説明</span><span class="sxs-lookup"><span data-stu-id="6fdd9-147">Description</span></span>|  
|-------------|-----------------|  
|[\<knownCertificates>](knowncertificates.md)|<span data-ttu-id="6fdd9-148">セキュリティ トークンを検証するためのセキュリティ トークン サービス (STS) によって提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-148">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fdd9-149">解説</span><span class="sxs-lookup"><span data-stu-id="6fdd9-149">Remarks</span></span>  

 <span data-ttu-id="6fdd9-150">発行されるトークンのシナリオには、3 つの段階があります。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-150">The issued token scenario has three stages.</span></span> <span data-ttu-id="6fdd9-151">最初の段階では、サービスにアクセスしようとしているクライアントは、 *セキュリティで保護されたトークンサービス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-151">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="6fdd9-152">次に、セキュリティ トークン サービスがクライアントを認証し、その後、クライアントにトークン (通常は、SAML (Security Assertions Markup Language) トークン) を発行します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-152">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="6fdd9-153">最後に、クライアントがトークンを持ってサービスに戻ります。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-153">The client then returns to the service with the token.</span></span> <span data-ttu-id="6fdd9-154">サービスはトークンを調べ、トークンを認証することでクライアントの認証を可能にするデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-154">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="6fdd9-155">トークンを認証するには、セキュリティ トークン サービスで使用される証明書がサービスによって認識されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-155">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="6fdd9-156">要素は、 [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) このようなセキュリティトークンサービス証明書のリポジトリです。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-156">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="6fdd9-157">証明書を追加するには、を使用し [\<knownCertificates>](knowncertificates.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-157">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="6fdd9-158">次の例に示すように、各証明書の[ \<add> 要素 \<knownCertificates> 要素](add-of-knowncertificates.md)を挿入します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-158">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="6fdd9-159">既定では、証明書はセキュリティ トークン サービスから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-159">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="6fdd9-160">このような "既知" の証明書により、正当なクライアントのみがサービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-160">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="6fdd9-161">フェデレーションサービスによってクライアントが認証されるために必要な条件を確認するには、「 [方法: フェデレーションサービスで資格情報を構成](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-161">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="6fdd9-162">フェデレーションシナリオの詳細については、「 [フェデレーションと発行済みトークン](../../../wcf/feature-details/federation-and-issued-tokens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-162">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fdd9-163">例</span><span class="sxs-lookup"><span data-stu-id="6fdd9-163">Example</span></span>  

 <span data-ttu-id="6fdd9-164">以下の例では、STS 証明書のリポジトリに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-164">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="6fdd9-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fdd9-165">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [\<knownCertificates>](knowncertificates.md)
- [<span data-ttu-id="6fdd9-166">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="6fdd9-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="6fdd9-167">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="6fdd9-167">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="6fdd9-168">方法: フェデレーション サービスで資格情報を設定する</span><span class="sxs-lookup"><span data-stu-id="6fdd9-168">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="6fdd9-169">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="6fdd9-169">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
