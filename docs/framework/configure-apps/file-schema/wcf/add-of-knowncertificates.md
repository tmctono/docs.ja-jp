---
title: <add> の <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 3eb5bf74f909e6036154b7f5f7c6181b09fefbff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704701"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="dac7d-102">\<追加 > の\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="dac7d-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="dac7d-103">既知の証明書のコレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="dac7d-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dac7d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dac7d-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="dac7d-105">\<behaviors></span></span>  
<span data-ttu-id="dac7d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="dac7d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="dac7d-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="dac7d-107">\<behavior></span></span>  
<span data-ttu-id="dac7d-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="dac7d-108">\<serviceCredentials></span></span>  
<span data-ttu-id="dac7d-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="dac7d-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="dac7d-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="dac7d-110">\<knownCertificates></span></span>  
<span data-ttu-id="dac7d-111">\<add></span><span class="sxs-lookup"><span data-stu-id="dac7d-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dac7d-112">構文</span><span class="sxs-lookup"><span data-stu-id="dac7d-112">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dac7d-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dac7d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="dac7d-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dac7d-115">属性</span><span class="sxs-lookup"><span data-stu-id="dac7d-115">Attributes</span></span>  
  
|<span data-ttu-id="dac7d-116">属性</span><span class="sxs-lookup"><span data-stu-id="dac7d-116">Attribute</span></span>|<span data-ttu-id="dac7d-117">説明</span><span class="sxs-lookup"><span data-stu-id="dac7d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dac7d-118">findValue</span><span class="sxs-lookup"><span data-stu-id="dac7d-118">findValue</span></span>|<span data-ttu-id="dac7d-119">文字列。</span><span class="sxs-lookup"><span data-stu-id="dac7d-119">String.</span></span> <span data-ttu-id="dac7d-120">検索対象の値。</span><span class="sxs-lookup"><span data-stu-id="dac7d-120">The value to search for.</span></span>|  
|<span data-ttu-id="dac7d-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="dac7d-121">storeLocation</span></span>|<span data-ttu-id="dac7d-122">列挙値。</span><span class="sxs-lookup"><span data-stu-id="dac7d-122">Enumeration.</span></span> <span data-ttu-id="dac7d-123">検索する 2 つの格納場所のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="dac7d-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="dac7d-124">storeName</span><span class="sxs-lookup"><span data-stu-id="dac7d-124">storeName</span></span>|<span data-ttu-id="dac7d-125">列挙値。</span><span class="sxs-lookup"><span data-stu-id="dac7d-125">Enumeration.</span></span> <span data-ttu-id="dac7d-126">検索するシステム ストアのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="dac7d-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="dac7d-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="dac7d-127">x509FindType</span></span>|<span data-ttu-id="dac7d-128">列挙値。</span><span class="sxs-lookup"><span data-stu-id="dac7d-128">Enumeration.</span></span> <span data-ttu-id="dac7d-129">検索する証明書フィールドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="dac7d-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="dac7d-130">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="dac7d-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="dac7d-131">値</span><span class="sxs-lookup"><span data-stu-id="dac7d-131">Value</span></span>|<span data-ttu-id="dac7d-132">説明</span><span class="sxs-lookup"><span data-stu-id="dac7d-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dac7d-133">String</span><span class="sxs-lookup"><span data-stu-id="dac7d-133">String</span></span>|<span data-ttu-id="dac7d-134">値は、検索されるフィールド (X509FindType 属性により指定される) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dac7d-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="dac7d-135">たとえば、サムプリント検索する場合、値は 16 進数の文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dac7d-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="dac7d-136">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="dac7d-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="dac7d-137">値</span><span class="sxs-lookup"><span data-stu-id="dac7d-137">Value</span></span>|<span data-ttu-id="dac7d-138">説明</span><span class="sxs-lookup"><span data-stu-id="dac7d-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dac7d-139">列挙</span><span class="sxs-lookup"><span data-stu-id="dac7d-139">Enumeration</span></span>|<span data-ttu-id="dac7d-140">次の値が含まれます。FindByThumbprint、FindBySubjectName、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName、FindByApplicationPolicy、FindByCertificatePolicy、FindByExtension、FindByKeyUsage、findbysubjectkeyidentifier です。</span><span class="sxs-lookup"><span data-stu-id="dac7d-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="dac7d-141">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="dac7d-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="dac7d-142">値</span><span class="sxs-lookup"><span data-stu-id="dac7d-142">Value</span></span>|<span data-ttu-id="dac7d-143">説明</span><span class="sxs-lookup"><span data-stu-id="dac7d-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dac7d-144">列挙型</span><span class="sxs-lookup"><span data-stu-id="dac7d-144">Enumeration</span></span>|<span data-ttu-id="dac7d-145">CurrentUser または LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="dac7d-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="dac7d-146">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="dac7d-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="dac7d-147">値</span><span class="sxs-lookup"><span data-stu-id="dac7d-147">Value</span></span>|<span data-ttu-id="dac7d-148">説明</span><span class="sxs-lookup"><span data-stu-id="dac7d-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dac7d-149">列挙</span><span class="sxs-lookup"><span data-stu-id="dac7d-149">Enumeration</span></span>|<span data-ttu-id="dac7d-150">次の値が含まれます。AddressBook、AuthRoot、CertificateAuthority、Disallowed、My、Root、TrustedPeople、および TrustedPublisher です。</span><span class="sxs-lookup"><span data-stu-id="dac7d-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dac7d-151">子要素</span><span class="sxs-lookup"><span data-stu-id="dac7d-151">Child Elements</span></span>  
 <span data-ttu-id="dac7d-152">なし。</span><span class="sxs-lookup"><span data-stu-id="dac7d-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dac7d-153">親要素</span><span class="sxs-lookup"><span data-stu-id="dac7d-153">Parent Elements</span></span>  
  
|<span data-ttu-id="dac7d-154">要素</span><span class="sxs-lookup"><span data-stu-id="dac7d-154">Element</span></span>|<span data-ttu-id="dac7d-155">説明</span><span class="sxs-lookup"><span data-stu-id="dac7d-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dac7d-156">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="dac7d-156">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|<span data-ttu-id="dac7d-157">セキュリティ トークンを検証するためのセキュリティ トークン サービス (STS) によって提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dac7d-158">Remarks</span><span class="sxs-lookup"><span data-stu-id="dac7d-158">Remarks</span></span>  
 <span data-ttu-id="dac7d-159">発行されるトークンのシナリオには、3 つの段階があります。</span><span class="sxs-lookup"><span data-stu-id="dac7d-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="dac7d-160">最初の段階でのサービスにアクセスしようとしています。 クライアントが参照される、*セキュア トークン サービス*します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="dac7d-161">次に、セキュリティ トークン サービスがクライアントを認証し、その後、クライアントにトークン (通常は、SAML (Security Assertions Markup Language) トークン) を発行します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="dac7d-162">最後に、クライアントがトークンを持ってサービスに戻ります。</span><span class="sxs-lookup"><span data-stu-id="dac7d-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="dac7d-163">サービスはトークンを調べ、トークンを認証することでクライアントの認証を可能にするデータを確認します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="dac7d-164">トークンを認証するには、セキュリティ トークン サービスで使用される証明書がサービスによって認識されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dac7d-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="dac7d-165">[ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)要素はこのようなセキュリティ トークン サービス証明書のリポジトリです。</span><span class="sxs-lookup"><span data-stu-id="dac7d-165">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="dac7d-166">証明書を追加するには、使用、 [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-166">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="dac7d-167">挿入、 [\<追加 > 要素\<knownCertificates > 要素](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)の各証明書、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="dac7d-167">Insert an [\<add> element \<knownCertificates> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="dac7d-168">既定では、証明書はセキュリティ トークン サービスから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dac7d-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="dac7d-169">このような "既知" の証明書により、正当なクライアントのみがサービスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="dac7d-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="dac7d-170">この構成要素の使い方の詳細についてと、フェデレーション サービスで認証するクライアントに必要な条件を確認するを参照してください。[方法。フェデレーション サービスで資格情報を構成](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="dac7d-171">フェデレーション シナリオの詳細については、次を参照してください。[フェデレーションと発行されたトークン](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dac7d-172">例</span><span class="sxs-lookup"><span data-stu-id="dac7d-172">Example</span></span>  
 <span data-ttu-id="dac7d-173">以下の例では、STS 証明書のリポジトリに証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dac7d-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="dac7d-174">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="dac7d-175">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="dac7d-175">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)
- [<span data-ttu-id="dac7d-176">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="dac7d-176">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="dac7d-177">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="dac7d-177">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="dac7d-178">方法: フェデレーション サービスで資格情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="dac7d-178">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="dac7d-179">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="dac7d-179">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
