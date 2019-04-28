---
title: <authentication> <serviceCertificate>要素
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: b96d53312d672eebd67de82f69cd9a0a2b5bd22e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704467"
---
# <a name="authentication-of-servicecertificate-element"></a><span data-ttu-id="83210-102">\<認証 > の\<serviceCertificate > 要素</span><span class="sxs-lookup"><span data-stu-id="83210-102">\<authentication> of \<serviceCertificate> Element</span></span>
<span data-ttu-id="83210-103">SSL/TLS ネゴシエーションを使用して取得されたサービス証明書を認証するためにクライアント プロキシが使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="83210-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="83210-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="83210-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="83210-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="83210-105">\<behaviors></span></span>  
<span data-ttu-id="83210-106">endpointBehaviors セクション</span><span class="sxs-lookup"><span data-stu-id="83210-106">endpointBehaviors section</span></span>  
<span data-ttu-id="83210-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="83210-107">\<behavior></span></span>  
<span data-ttu-id="83210-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="83210-108">\<clientCredentials></span></span>  
<span data-ttu-id="83210-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="83210-109">\<serviceCertificate></span></span>  
<span data-ttu-id="83210-110">\<authentication></span><span class="sxs-lookup"><span data-stu-id="83210-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83210-111">構文</span><span class="sxs-lookup"><span data-stu-id="83210-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83210-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="83210-112">Attributes and Elements</span></span>  
 <span data-ttu-id="83210-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="83210-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83210-114">属性</span><span class="sxs-lookup"><span data-stu-id="83210-114">Attributes</span></span>  
  
|<span data-ttu-id="83210-115">属性</span><span class="sxs-lookup"><span data-stu-id="83210-115">Attribute</span></span>|<span data-ttu-id="83210-116">説明</span><span class="sxs-lookup"><span data-stu-id="83210-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83210-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="83210-117">customCertificateValidatorType</span></span>|<span data-ttu-id="83210-118">文字列。</span><span class="sxs-lookup"><span data-stu-id="83210-118">String.</span></span> <span data-ttu-id="83210-119">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="83210-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="83210-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="83210-120">certificateValidationMode</span></span>|<span data-ttu-id="83210-121">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="83210-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="83210-122">`Custom` に設定されている場合、customCertificateValidator も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83210-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="83210-123">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="83210-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="83210-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="83210-124">revocationMode</span></span>|<span data-ttu-id="83210-125">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="83210-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="83210-126">既定値は、`Online` です。</span><span class="sxs-lookup"><span data-stu-id="83210-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="83210-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="83210-127">trustedStoreLocation</span></span>|<span data-ttu-id="83210-128">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="83210-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="83210-129">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="83210-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="83210-130">に対して検証が実行、**信頼されたユーザー**指定したストアの場所に格納します。</span><span class="sxs-lookup"><span data-stu-id="83210-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="83210-131">既定値は `CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="83210-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="83210-132">customCertificateValidator 属性</span><span class="sxs-lookup"><span data-stu-id="83210-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="83210-133">値</span><span class="sxs-lookup"><span data-stu-id="83210-133">Value</span></span>|<span data-ttu-id="83210-134">説明</span><span class="sxs-lookup"><span data-stu-id="83210-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83210-135">String</span><span class="sxs-lookup"><span data-stu-id="83210-135">String</span></span>|<span data-ttu-id="83210-136">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="83210-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="83210-137">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="83210-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="83210-138">値</span><span class="sxs-lookup"><span data-stu-id="83210-138">Value</span></span>|<span data-ttu-id="83210-139">説明</span><span class="sxs-lookup"><span data-stu-id="83210-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83210-140">列挙</span><span class="sxs-lookup"><span data-stu-id="83210-140">Enumeration</span></span>|<span data-ttu-id="83210-141">次のいずれかの値です。None、PeerTrust、ChainTrust、PeerOrChainTrust、Custom です。</span><span class="sxs-lookup"><span data-stu-id="83210-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="83210-142">詳細については、次を参照してください。 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="83210-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="83210-143">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="83210-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="83210-144">値</span><span class="sxs-lookup"><span data-stu-id="83210-144">Value</span></span>|<span data-ttu-id="83210-145">説明</span><span class="sxs-lookup"><span data-stu-id="83210-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83210-146">列挙</span><span class="sxs-lookup"><span data-stu-id="83210-146">Enumeration</span></span>|<span data-ttu-id="83210-147">次のいずれかの値です。NoCheck、Online、Offline にします。</span><span class="sxs-lookup"><span data-stu-id="83210-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="83210-148">詳細については、次を参照してください。 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="83210-148">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="83210-149">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="83210-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="83210-150">値</span><span class="sxs-lookup"><span data-stu-id="83210-150">Value</span></span>|<span data-ttu-id="83210-151">説明</span><span class="sxs-lookup"><span data-stu-id="83210-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83210-152">列挙</span><span class="sxs-lookup"><span data-stu-id="83210-152">Enumeration</span></span>|<span data-ttu-id="83210-153">次のいずれかの値です。LocalMachine または CurrentUser の場合は。</span><span class="sxs-lookup"><span data-stu-id="83210-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="83210-154">既定値は CurrentUser です。</span><span class="sxs-lookup"><span data-stu-id="83210-154">The default is CurrentUser.</span></span> <span data-ttu-id="83210-155">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 LocalMachine の下にあります。</span><span class="sxs-lookup"><span data-stu-id="83210-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="83210-156">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 CurrentUser の下にあります。</span><span class="sxs-lookup"><span data-stu-id="83210-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83210-157">子要素</span><span class="sxs-lookup"><span data-stu-id="83210-157">Child Elements</span></span>  
 <span data-ttu-id="83210-158">なし。</span><span class="sxs-lookup"><span data-stu-id="83210-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83210-159">親要素</span><span class="sxs-lookup"><span data-stu-id="83210-159">Parent Elements</span></span>  
  
|<span data-ttu-id="83210-160">要素</span><span class="sxs-lookup"><span data-stu-id="83210-160">Element</span></span>|<span data-ttu-id="83210-161">説明</span><span class="sxs-lookup"><span data-stu-id="83210-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83210-162">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="83210-162">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="83210-163">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="83210-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83210-164">Remarks</span><span class="sxs-lookup"><span data-stu-id="83210-164">Remarks</span></span>  
 <span data-ttu-id="83210-165">この構成要素の `certificateValidationMode` 属性は、証明書の認証に使用される信頼レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="83210-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="83210-166">既定のレベルは `ChainTrust` に設定され、チェーンの最上位の信頼された証明機関で終了する証明書の階層構造で各証明書を検索するよう指定します。</span><span class="sxs-lookup"><span data-stu-id="83210-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="83210-167">これは最もセキュリティで保護されているモードです。</span><span class="sxs-lookup"><span data-stu-id="83210-167">This is the most secure mode.</span></span> <span data-ttu-id="83210-168">また、値を `PeerOrChainTrust` に設定することもできます。これは、信頼されたチェーン内の証明書と共に、自己発行された証明書 (ピア信頼) も受け入れるよう指定します。</span><span class="sxs-lookup"><span data-stu-id="83210-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="83210-169">自己発行の資格情報は信頼された証明機関から購入したものである必要はないため、この値はクライアントとサービスの開発およびデバッグに使用されます。</span><span class="sxs-lookup"><span data-stu-id="83210-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="83210-170">クライアントを展開するときは、代わりに `ChainTrust` 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="83210-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="83210-171">値を `Custom` または `None` に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="83210-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="83210-172">`Custom` 値を使用するには、`customCertificateValidator` 属性を証明書の検証に使用するアセンブリと型に設定することも必要です。</span><span class="sxs-lookup"><span data-stu-id="83210-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="83210-173">独自のカスタム検証を作成するには、抽象 X509CertificateValidator クラスを継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83210-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="83210-174">詳細については、「[方法 :カスタム証明書の検証を使用するサービスを作成する](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)します。</span><span class="sxs-lookup"><span data-stu-id="83210-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="83210-175">`revocationMode` 属性は、証明書が失効していないかどうかをチェックする方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="83210-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="83210-176">既定値は `online` です。この場合、証明書が失効していないかどうかを自動的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="83210-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="83210-177">詳細については、次を参照してください。 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="83210-177">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83210-178">例</span><span class="sxs-lookup"><span data-stu-id="83210-178">Example</span></span>  
 <span data-ttu-id="83210-179">次の例は、2 つのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="83210-179">The following example does two tasks.</span></span> <span data-ttu-id="83210-180">クライアントとドメイン名をエンドポイントと通信するときに使用するのに必要なサービスの証明書をまずを指定します。 `www.contoso.com` HTTP プロトコルを経由します。</span><span class="sxs-lookup"><span data-stu-id="83210-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="83210-181">次に、認証中に使用される失効モードとストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="83210-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83210-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="83210-182">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [<span data-ttu-id="83210-183">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="83210-183">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="83210-184">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="83210-184">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="83210-185">方法: カスタム証明書の検証を使用するサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="83210-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="83210-186">\<authentication></span><span class="sxs-lookup"><span data-stu-id="83210-186">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="83210-187">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="83210-187">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="83210-188">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="83210-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
