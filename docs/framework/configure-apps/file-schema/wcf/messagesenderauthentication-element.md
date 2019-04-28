---
title: <messageSenderAuthentication> 要素
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 410fffd541926b9a2e75c04d26a2a1e08a262939
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764089"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="8e8e1-102">\<messageSenderAuthentication > 要素</span><span class="sxs-lookup"><span data-stu-id="8e8e1-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="8e8e1-103">ピアツーピア メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="8e8e1-104">ピア ツー ピア プログラミングの詳細については、次を参照してください。[ピア ツー ピア ネットワー キング](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="8e8e1-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8e8e1-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e8e1-106">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="8e8e1-106">\<behaviors></span></span>  
<span data-ttu-id="8e8e1-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8e8e1-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="8e8e1-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8e8e1-108">\<behavior></span></span>  
<span data-ttu-id="8e8e1-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8e8e1-109">\<clientCredentials></span></span>  
<span data-ttu-id="8e8e1-110">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="8e8e1-110">\<peer></span></span>  
<span data-ttu-id="8e8e1-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="8e8e1-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e8e1-112">構文</span><span class="sxs-lookup"><span data-stu-id="8e8e1-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e8e1-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8e8e1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8e8e1-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e8e1-115">属性</span><span class="sxs-lookup"><span data-stu-id="8e8e1-115">Attributes</span></span>  
  
|<span data-ttu-id="8e8e1-116">属性</span><span class="sxs-lookup"><span data-stu-id="8e8e1-116">Attribute</span></span>|<span data-ttu-id="8e8e1-117">説明</span><span class="sxs-lookup"><span data-stu-id="8e8e1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e8e1-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="8e8e1-118">customCertificateValidatorType</span></span>|<span data-ttu-id="8e8e1-119">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="8e8e1-120">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="8e8e1-121">certifcateValidationMode</span><span class="sxs-lookup"><span data-stu-id="8e8e1-121">certifcateValidationMode</span></span>|<span data-ttu-id="8e8e1-122">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="8e8e1-123">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|<span data-ttu-id="8e8e1-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="8e8e1-124">revocationMode</span></span>|<span data-ttu-id="8e8e1-125">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|<span data-ttu-id="8e8e1-126">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="8e8e1-126">trustedStoreLocation</span></span>|<span data-ttu-id="8e8e1-127">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-127">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="8e8e1-128">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-128">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="8e8e1-129">に対して検証が実行、**信頼されたユーザー**指定したストアの場所に格納します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-129">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="8e8e1-130">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="8e8e1-130">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="8e8e1-131">値</span><span class="sxs-lookup"><span data-stu-id="8e8e1-131">Value</span></span>|<span data-ttu-id="8e8e1-132">説明</span><span class="sxs-lookup"><span data-stu-id="8e8e1-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e8e1-133">String</span><span class="sxs-lookup"><span data-stu-id="8e8e1-133">String</span></span>|<span data-ttu-id="8e8e1-134">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-134">Optional.</span></span> <span data-ttu-id="8e8e1-135">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-135">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="8e8e1-136">少なくとも、名前空間とタイプ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-136">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="8e8e1-137">省略可能な情報は、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンです。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-137">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="8e8e1-138">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="8e8e1-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="8e8e1-139">値</span><span class="sxs-lookup"><span data-stu-id="8e8e1-139">Value</span></span>|<span data-ttu-id="8e8e1-140">説明</span><span class="sxs-lookup"><span data-stu-id="8e8e1-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e8e1-141">列挙型</span><span class="sxs-lookup"><span data-stu-id="8e8e1-141">Enumeration</span></span>|<span data-ttu-id="8e8e1-142">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-142">Optional.</span></span> <span data-ttu-id="8e8e1-143">`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust`、`Custom` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-143">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="8e8e1-144">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-144">The default is `ChainTrust`.</span></span> <span data-ttu-id="8e8e1-145">既定値は `ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="8e8e1-146">詳細については、次を参照してください。 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="8e8e1-147">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="8e8e1-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="8e8e1-148">値</span><span class="sxs-lookup"><span data-stu-id="8e8e1-148">Value</span></span>|<span data-ttu-id="8e8e1-149">説明</span><span class="sxs-lookup"><span data-stu-id="8e8e1-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e8e1-150">列挙型</span><span class="sxs-lookup"><span data-stu-id="8e8e1-150">Enumeration</span></span>|<span data-ttu-id="8e8e1-151">`NoCheck`、`Online`、`Offline` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="8e8e1-152">既定値は `Online` です。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="8e8e1-153">詳細については、次を参照してください。 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="8e8e1-154">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="8e8e1-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="8e8e1-155">値</span><span class="sxs-lookup"><span data-stu-id="8e8e1-155">Value</span></span>|<span data-ttu-id="8e8e1-156">説明</span><span class="sxs-lookup"><span data-stu-id="8e8e1-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e8e1-157">列挙型</span><span class="sxs-lookup"><span data-stu-id="8e8e1-157">Enumeration</span></span>|<span data-ttu-id="8e8e1-158">`LocalMachine` または `CurrentUser` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="8e8e1-159">既定値は、`CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="8e8e1-160">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="8e8e1-161">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="8e8e1-162">既定値は `CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-162">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e8e1-163">子要素</span><span class="sxs-lookup"><span data-stu-id="8e8e1-163">Child Elements</span></span>  
 <span data-ttu-id="8e8e1-164">なし。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e8e1-165">親要素</span><span class="sxs-lookup"><span data-stu-id="8e8e1-165">Parent Elements</span></span>  
  
|<span data-ttu-id="8e8e1-166">要素</span><span class="sxs-lookup"><span data-stu-id="8e8e1-166">Element</span></span>|<span data-ttu-id="8e8e1-167">説明</span><span class="sxs-lookup"><span data-stu-id="8e8e1-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e8e1-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="8e8e1-168">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="8e8e1-169">ピア サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e8e1-170">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e8e1-170">Remarks</span></span>  
 <span data-ttu-id="8e8e1-171">メッセージ認証を選択した場合は、この要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-171">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="8e8e1-172">によって提供される証明書を使用して出力チャネルでは、各メッセージが署名されて[\<証明書 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-172">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="8e8e1-173">すべてのメッセージは、アプリケーションに配信される前に、この要素の `customCertificateValidatorType` 属性で指定した検証を使用してメッセージ資格情報がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-173">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="8e8e1-174">検証は、資格情報を受け入れることも拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-174">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e8e1-175">例</span><span class="sxs-lookup"><span data-stu-id="8e8e1-175">Example</span></span>  
 <span data-ttu-id="8e8e1-176">次のコードは、メッセージ送信者検証モードを `PeerOrChainTrust` に設定します。</span><span class="sxs-lookup"><span data-stu-id="8e8e1-176">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="8e8e1-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e8e1-177">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="8e8e1-178">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="8e8e1-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="8e8e1-179">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="8e8e1-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="8e8e1-180">[ピア チャネル メッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8e8e1-180">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="8e8e1-181">[ピア チャネル カスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8e8e1-181">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="8e8e1-182">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="8e8e1-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
