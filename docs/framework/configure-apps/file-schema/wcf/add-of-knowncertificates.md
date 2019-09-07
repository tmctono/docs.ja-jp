---
title: <add> の <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 29b067e6ec20992084f9ab3bab087222bdd56da2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400621"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="289fd-102">\<knowncertificates の\<> を追加 ></span><span class="sxs-lookup"><span data-stu-id="289fd-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="289fd-103">既知の証明書のコレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="289fd-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
<span data-ttu-id="289fd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="289fd-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="289fd-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="289fd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="289fd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="289fd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="289fd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenAuthentication >** ](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)</span></span>\
<span data-ttu-id="289fd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<knownCertificates >** ](knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownCertificates>**](knowncertificates.md)</span></span>\
<span data-ttu-id="289fd-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="289fd-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="289fd-113">構文</span><span class="sxs-lookup"><span data-stu-id="289fd-113">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="289fd-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="289fd-114">Attributes and Elements</span></span>  
 <span data-ttu-id="289fd-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="289fd-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="289fd-116">属性</span><span class="sxs-lookup"><span data-stu-id="289fd-116">Attributes</span></span>  
  
|<span data-ttu-id="289fd-117">属性</span><span class="sxs-lookup"><span data-stu-id="289fd-117">Attribute</span></span>|<span data-ttu-id="289fd-118">説明</span><span class="sxs-lookup"><span data-stu-id="289fd-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="289fd-119">findValue</span><span class="sxs-lookup"><span data-stu-id="289fd-119">findValue</span></span>|<span data-ttu-id="289fd-120">文字列。</span><span class="sxs-lookup"><span data-stu-id="289fd-120">String.</span></span> <span data-ttu-id="289fd-121">検索対象の値。</span><span class="sxs-lookup"><span data-stu-id="289fd-121">The value to search for.</span></span>|  
|<span data-ttu-id="289fd-122">storeLocation</span><span class="sxs-lookup"><span data-stu-id="289fd-122">storeLocation</span></span>|<span data-ttu-id="289fd-123">列挙値。</span><span class="sxs-lookup"><span data-stu-id="289fd-123">Enumeration.</span></span> <span data-ttu-id="289fd-124">検索する 2 つの格納場所のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="289fd-124">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="289fd-125">storeName</span><span class="sxs-lookup"><span data-stu-id="289fd-125">storeName</span></span>|<span data-ttu-id="289fd-126">列挙値。</span><span class="sxs-lookup"><span data-stu-id="289fd-126">Enumeration.</span></span> <span data-ttu-id="289fd-127">検索するシステム ストアのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="289fd-127">One of the system stores to search.</span></span>|  
|<span data-ttu-id="289fd-128">x509FindType</span><span class="sxs-lookup"><span data-stu-id="289fd-128">x509FindType</span></span>|<span data-ttu-id="289fd-129">列挙値。</span><span class="sxs-lookup"><span data-stu-id="289fd-129">Enumeration.</span></span> <span data-ttu-id="289fd-130">検索する証明書フィールドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="289fd-130">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="289fd-131">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="289fd-131">findValue Attribute</span></span>  
  
|<span data-ttu-id="289fd-132">値</span><span class="sxs-lookup"><span data-stu-id="289fd-132">Value</span></span>|<span data-ttu-id="289fd-133">説明</span><span class="sxs-lookup"><span data-stu-id="289fd-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="289fd-134">String</span><span class="sxs-lookup"><span data-stu-id="289fd-134">String</span></span>|<span data-ttu-id="289fd-135">値は、検索されるフィールド (X509FindType 属性により指定される) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="289fd-135">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="289fd-136">たとえば、サムプリント検索する場合、値は 16 進数の文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="289fd-136">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="289fd-137">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="289fd-137">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="289fd-138">値</span><span class="sxs-lookup"><span data-stu-id="289fd-138">Value</span></span>|<span data-ttu-id="289fd-139">説明</span><span class="sxs-lookup"><span data-stu-id="289fd-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="289fd-140">列挙</span><span class="sxs-lookup"><span data-stu-id="289fd-140">Enumeration</span></span>|<span data-ttu-id="289fd-141">次の値が含まれます。FindByThumbprint、FindBySubjectName、Findbysubjectdistinguishedname です、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="289fd-141">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="289fd-142">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="289fd-142">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="289fd-143">値</span><span class="sxs-lookup"><span data-stu-id="289fd-143">Value</span></span>|<span data-ttu-id="289fd-144">説明</span><span class="sxs-lookup"><span data-stu-id="289fd-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="289fd-145">列挙型</span><span class="sxs-lookup"><span data-stu-id="289fd-145">Enumeration</span></span>|<span data-ttu-id="289fd-146">CurrentUser または LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="289fd-146">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="289fd-147">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="289fd-147">storeName Attribute</span></span>  
  
|<span data-ttu-id="289fd-148">値</span><span class="sxs-lookup"><span data-stu-id="289fd-148">Value</span></span>|<span data-ttu-id="289fd-149">説明</span><span class="sxs-lookup"><span data-stu-id="289fd-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="289fd-150">列挙</span><span class="sxs-lookup"><span data-stu-id="289fd-150">Enumeration</span></span>|<span data-ttu-id="289fd-151">次の値が含まれます。アドレス帳、AuthRoot、CertificateAuthority、許可されていない、My、Root、TrustedPeople、Trustedpeople。</span><span class="sxs-lookup"><span data-stu-id="289fd-151">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="289fd-152">子要素</span><span class="sxs-lookup"><span data-stu-id="289fd-152">Child Elements</span></span>  
 <span data-ttu-id="289fd-153">なし。</span><span class="sxs-lookup"><span data-stu-id="289fd-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="289fd-154">親要素</span><span class="sxs-lookup"><span data-stu-id="289fd-154">Parent Elements</span></span>  
  
|<span data-ttu-id="289fd-155">要素</span><span class="sxs-lookup"><span data-stu-id="289fd-155">Element</span></span>|<span data-ttu-id="289fd-156">説明</span><span class="sxs-lookup"><span data-stu-id="289fd-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="289fd-157">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="289fd-157">\<knownCertificates></span></span>](knowncertificates.md)|<span data-ttu-id="289fd-158">セキュリティ トークンを検証するためのセキュリティ トークン サービス (STS) によって提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="289fd-158">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="289fd-159">Remarks</span><span class="sxs-lookup"><span data-stu-id="289fd-159">Remarks</span></span>  
 <span data-ttu-id="289fd-160">発行されるトークンのシナリオには、3 つの段階があります。</span><span class="sxs-lookup"><span data-stu-id="289fd-160">The issued token scenario has three stages.</span></span> <span data-ttu-id="289fd-161">最初の段階では、サービスにアクセスしようとしているクライアントは、*セキュリティで保護されたトークンサービス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="289fd-161">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="289fd-162">次に、セキュリティ トークン サービスがクライアントを認証し、その後、クライアントにトークン (通常は、SAML (Security Assertions Markup Language) トークン) を発行します。</span><span class="sxs-lookup"><span data-stu-id="289fd-162">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="289fd-163">最後に、クライアントがトークンを持ってサービスに戻ります。</span><span class="sxs-lookup"><span data-stu-id="289fd-163">The client then returns to the service with the token.</span></span> <span data-ttu-id="289fd-164">サービスはトークンを調べ、トークンを認証することでクライアントの認証を可能にするデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="289fd-164">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="289fd-165">トークンを認証するには、セキュリティ トークン サービスで使用される証明書がサービスによって認識されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="289fd-165">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="289fd-166">IssuedTokenAuthentication > 要素は、このようなセキュリティトークンサービス証明書のリポジトリです。 [ \<](issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-166">The [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="289fd-167">証明書を追加するには[ \<、> knowncertificates](knowncertificates.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="289fd-167">To add certificates, use the [\<knownCertificates>](knowncertificates.md).</span></span> <span data-ttu-id="289fd-168">次の例に示すように、各証明書の[ \<add > 要素 knowncertificates > 要素を挿入します。 \<](add-of-knowncertificates.md)</span><span class="sxs-lookup"><span data-stu-id="289fd-168">Insert an [\<add> element \<knownCertificates> Element](add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="289fd-169">既定では、証明書はセキュリティ トークン サービスから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="289fd-169">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="289fd-170">このような "既知" の証明書により、正当なクライアントのみがサービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="289fd-170">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="289fd-171">フェデレーションサービスによってクライアントが認証されるために必要な条件を確認し、この構成要素の使用方法の詳細[については、「」を参照してください。フェデレーションサービス](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)で資格情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="289fd-171">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="289fd-172">フェデレーションシナリオの詳細については、「[フェデレーションと発行済みトークン](../../../wcf/feature-details/federation-and-issued-tokens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="289fd-172">For more information about federated scenarios, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="289fd-173">例</span><span class="sxs-lookup"><span data-stu-id="289fd-173">Example</span></span>  
 <span data-ttu-id="289fd-174">以下の例では、STS 証明書のリポジトリに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="289fd-174">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="289fd-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="289fd-175">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="289fd-176">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="289fd-176">\<knownCertificates></span></span>](knowncertificates.md)
- [<span data-ttu-id="289fd-177">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="289fd-177">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="289fd-178">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="289fd-178">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="289fd-179">方法: フェデレーションサービスで資格情報を構成する</span><span class="sxs-lookup"><span data-stu-id="289fd-179">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="289fd-180">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="289fd-180">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
