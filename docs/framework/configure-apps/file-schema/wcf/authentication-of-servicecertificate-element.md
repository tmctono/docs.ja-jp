---
title: <authentication> <serviceCertificate>要素
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398225"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="51350-102">\<serviceCertificate > 要素\<の認証 ></span><span class="sxs-lookup"><span data-stu-id="51350-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="51350-103">SSL/TLS ネゴシエーションを使用して取得されたサービス証明書を認証するためにクライアント プロキシが使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
<span data-ttu-id="51350-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="51350-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="51350-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="51350-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="51350-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="51350-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="51350-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="51350-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="51350-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="51350-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="51350-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="51350-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="51350-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="51350-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="51350-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<認証 >**</span><span class="sxs-lookup"><span data-stu-id="51350-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51350-112">構文</span><span class="sxs-lookup"><span data-stu-id="51350-112">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51350-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="51350-113">Attributes and Elements</span></span>  
 <span data-ttu-id="51350-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="51350-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51350-115">属性</span><span class="sxs-lookup"><span data-stu-id="51350-115">Attributes</span></span>  
  
|<span data-ttu-id="51350-116">属性</span><span class="sxs-lookup"><span data-stu-id="51350-116">Attribute</span></span>|<span data-ttu-id="51350-117">説明</span><span class="sxs-lookup"><span data-stu-id="51350-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51350-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="51350-118">customCertificateValidatorType</span></span>|<span data-ttu-id="51350-119">文字列。</span><span class="sxs-lookup"><span data-stu-id="51350-119">String.</span></span> <span data-ttu-id="51350-120">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="51350-120">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="51350-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="51350-121">certificateValidationMode</span></span>|<span data-ttu-id="51350-122">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="51350-123">`Custom` に設定されている場合、customCertificateValidator も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51350-123">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="51350-124">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="51350-124">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="51350-125">revocationMode</span><span class="sxs-lookup"><span data-stu-id="51350-125">revocationMode</span></span>|<span data-ttu-id="51350-126">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="51350-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="51350-127">既定値は、`Online` です。</span><span class="sxs-lookup"><span data-stu-id="51350-127">The default is `Online`.</span></span>|  
|<span data-ttu-id="51350-128">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="51350-128">trustedStoreLocation</span></span>|<span data-ttu-id="51350-129">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="51350-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="51350-130">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="51350-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="51350-131">指定されたストアの場所にある**信頼さ**れた People ストアに対して検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="51350-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="51350-132">既定値は `CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="51350-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="51350-133">customCertificateValidator 属性</span><span class="sxs-lookup"><span data-stu-id="51350-133">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="51350-134">値</span><span class="sxs-lookup"><span data-stu-id="51350-134">Value</span></span>|<span data-ttu-id="51350-135">説明</span><span class="sxs-lookup"><span data-stu-id="51350-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51350-136">String</span><span class="sxs-lookup"><span data-stu-id="51350-136">String</span></span>|<span data-ttu-id="51350-137">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-137">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="51350-138">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="51350-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="51350-139">値</span><span class="sxs-lookup"><span data-stu-id="51350-139">Value</span></span>|<span data-ttu-id="51350-140">説明</span><span class="sxs-lookup"><span data-stu-id="51350-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51350-141">列挙</span><span class="sxs-lookup"><span data-stu-id="51350-141">Enumeration</span></span>|<span data-ttu-id="51350-142">次のいずれかの値です。None、PeerTrust、ChainTrust、PeerOrChainTrust、Custom。</span><span class="sxs-lookup"><span data-stu-id="51350-142">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="51350-143">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51350-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="51350-144">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="51350-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="51350-145">値</span><span class="sxs-lookup"><span data-stu-id="51350-145">Value</span></span>|<span data-ttu-id="51350-146">説明</span><span class="sxs-lookup"><span data-stu-id="51350-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51350-147">列挙</span><span class="sxs-lookup"><span data-stu-id="51350-147">Enumeration</span></span>|<span data-ttu-id="51350-148">次のいずれかの値です。NoCheck、Online、Offline。</span><span class="sxs-lookup"><span data-stu-id="51350-148">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="51350-149">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51350-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="51350-150">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="51350-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="51350-151">値</span><span class="sxs-lookup"><span data-stu-id="51350-151">Value</span></span>|<span data-ttu-id="51350-152">説明</span><span class="sxs-lookup"><span data-stu-id="51350-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51350-153">列挙</span><span class="sxs-lookup"><span data-stu-id="51350-153">Enumeration</span></span>|<span data-ttu-id="51350-154">次のいずれかの値です。LocalMachine または CurrentUser。</span><span class="sxs-lookup"><span data-stu-id="51350-154">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="51350-155">既定値は CurrentUser です。</span><span class="sxs-lookup"><span data-stu-id="51350-155">The default is CurrentUser.</span></span> <span data-ttu-id="51350-156">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 LocalMachine の下にあります。</span><span class="sxs-lookup"><span data-stu-id="51350-156">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="51350-157">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 CurrentUser の下にあります。</span><span class="sxs-lookup"><span data-stu-id="51350-157">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51350-158">子要素</span><span class="sxs-lookup"><span data-stu-id="51350-158">Child Elements</span></span>  
 <span data-ttu-id="51350-159">なし。</span><span class="sxs-lookup"><span data-stu-id="51350-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51350-160">親要素</span><span class="sxs-lookup"><span data-stu-id="51350-160">Parent Elements</span></span>  
  
|<span data-ttu-id="51350-161">要素</span><span class="sxs-lookup"><span data-stu-id="51350-161">Element</span></span>|<span data-ttu-id="51350-162">説明</span><span class="sxs-lookup"><span data-stu-id="51350-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51350-163">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="51350-163">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="51350-164">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-164">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51350-165">Remarks</span><span class="sxs-lookup"><span data-stu-id="51350-165">Remarks</span></span>  
 <span data-ttu-id="51350-166">この構成要素の `certificateValidationMode` 属性は、証明書の認証に使用される信頼レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-166">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="51350-167">既定のレベルは `ChainTrust` に設定され、チェーンの最上位の信頼された証明機関で終了する証明書の階層構造で各証明書を検索するよう指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-167">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="51350-168">これは最もセキュリティで保護されているモードです。</span><span class="sxs-lookup"><span data-stu-id="51350-168">This is the most secure mode.</span></span> <span data-ttu-id="51350-169">また、値を `PeerOrChainTrust` に設定することもできます。これは、信頼されたチェーン内の証明書と共に、自己発行された証明書 (ピア信頼) も受け入れるよう指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-169">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="51350-170">自己発行の資格情報は信頼された証明機関から購入したものである必要はないため、この値はクライアントとサービスの開発およびデバッグに使用されます。</span><span class="sxs-lookup"><span data-stu-id="51350-170">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="51350-171">クライアントを展開するときは、代わりに `ChainTrust` 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="51350-171">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="51350-172">値を `Custom` または `None` に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="51350-172">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="51350-173">`Custom` 値を使用するには、`customCertificateValidator` 属性を証明書の検証に使用するアセンブリと型に設定することも必要です。</span><span class="sxs-lookup"><span data-stu-id="51350-173">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="51350-174">独自のカスタム検証を作成するには、抽象 X509CertificateValidator クラスを継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51350-174">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="51350-175">詳細については、「[方法 :カスタム証明書検証](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)を採用するサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="51350-175">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="51350-176">`revocationMode` 属性は、証明書が失効していないかどうかをチェックする方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-176">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="51350-177">既定値は `online` です。この場合、証明書が失効していないかどうかを自動的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="51350-177">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="51350-178">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51350-178">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51350-179">例</span><span class="sxs-lookup"><span data-stu-id="51350-179">Example</span></span>  
 <span data-ttu-id="51350-180">次の例は、2 つのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="51350-180">The following example does two tasks.</span></span> <span data-ttu-id="51350-181">まず、クライアントが HTTP プロトコル経由でドメイン名を`www.contoso.com`持つエンドポイントと通信するときに使用するサービス証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-181">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="51350-182">次に、認証中に使用される失効モードとストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="51350-182">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
     <add targetUri="http://www.contoso.com"
          findValue="www.contoso.com"
          storeLocation="LocalMachine"
          storeName="Root"
          x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="51350-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="51350-183">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="51350-184">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="51350-184">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="51350-185">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="51350-185">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="51350-186">方法: カスタム証明書の検証を使用するサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="51350-186">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="51350-187">\<authentication></span><span class="sxs-lookup"><span data-stu-id="51350-187">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="51350-188">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="51350-188">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="51350-189">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="51350-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
