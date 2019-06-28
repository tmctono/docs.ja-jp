---
title: <messageSenderAuthentication> 要素
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 804c280bcdb0fecc87f71121b7d95b5fd0268de9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423122"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="9ac21-102">\<messageSenderAuthentication > 要素</span><span class="sxs-lookup"><span data-stu-id="9ac21-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="9ac21-103">ピアツーピア メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="9ac21-104">ピア ツー ピア プログラミングの詳細については、次を参照してください。[ピア ツー ピア ネットワー キング](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="9ac21-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9ac21-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ac21-106">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="9ac21-106">\<behaviors></span></span>  
<span data-ttu-id="9ac21-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9ac21-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="9ac21-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9ac21-108">\<behavior></span></span>  
<span data-ttu-id="9ac21-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9ac21-109">\<clientCredentials></span></span>  
<span data-ttu-id="9ac21-110">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="9ac21-110">\<peer></span></span>  
<span data-ttu-id="9ac21-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="9ac21-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac21-112">構文</span><span class="sxs-lookup"><span data-stu-id="9ac21-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ac21-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9ac21-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9ac21-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ac21-115">属性</span><span class="sxs-lookup"><span data-stu-id="9ac21-115">Attributes</span></span>  
  
|<span data-ttu-id="9ac21-116">属性</span><span class="sxs-lookup"><span data-stu-id="9ac21-116">Attribute</span></span>|<span data-ttu-id="9ac21-117">説明</span><span class="sxs-lookup"><span data-stu-id="9ac21-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="9ac21-118">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="9ac21-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="9ac21-119">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac21-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="9ac21-120">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="9ac21-121">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac21-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="9ac21-122">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="9ac21-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="9ac21-123">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="9ac21-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="9ac21-124">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9ac21-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="9ac21-125">に対して検証が実行、**信頼されたユーザー**指定したストアの場所に格納します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="9ac21-126">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="9ac21-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="9ac21-127">値</span><span class="sxs-lookup"><span data-stu-id="9ac21-127">Value</span></span>|<span data-ttu-id="9ac21-128">説明</span><span class="sxs-lookup"><span data-stu-id="9ac21-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ac21-129">String</span><span class="sxs-lookup"><span data-stu-id="9ac21-129">String</span></span>|<span data-ttu-id="9ac21-130">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9ac21-130">Optional.</span></span> <span data-ttu-id="9ac21-131">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="9ac21-132">少なくとも、名前空間とタイプ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ac21-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="9ac21-133">省略可能な情報は、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンです。</span><span class="sxs-lookup"><span data-stu-id="9ac21-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="9ac21-134">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="9ac21-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="9ac21-135">値</span><span class="sxs-lookup"><span data-stu-id="9ac21-135">Value</span></span>|<span data-ttu-id="9ac21-136">説明</span><span class="sxs-lookup"><span data-stu-id="9ac21-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ac21-137">列挙型</span><span class="sxs-lookup"><span data-stu-id="9ac21-137">Enumeration</span></span>|<span data-ttu-id="9ac21-138">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9ac21-138">Optional.</span></span> <span data-ttu-id="9ac21-139">`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust`、`Custom` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="9ac21-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="9ac21-140">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="9ac21-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="9ac21-141">既定値は `ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="9ac21-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="9ac21-142">詳細については、次を参照してください。 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="9ac21-143">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="9ac21-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="9ac21-144">値</span><span class="sxs-lookup"><span data-stu-id="9ac21-144">Value</span></span>|<span data-ttu-id="9ac21-145">説明</span><span class="sxs-lookup"><span data-stu-id="9ac21-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ac21-146">列挙型</span><span class="sxs-lookup"><span data-stu-id="9ac21-146">Enumeration</span></span>|<span data-ttu-id="9ac21-147">`NoCheck`、`Online`、`Offline` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="9ac21-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="9ac21-148">既定値は `Online` です。</span><span class="sxs-lookup"><span data-stu-id="9ac21-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="9ac21-149">詳細については、次を参照してください。 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-149">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="9ac21-150">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="9ac21-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="9ac21-151">値</span><span class="sxs-lookup"><span data-stu-id="9ac21-151">Value</span></span>|<span data-ttu-id="9ac21-152">説明</span><span class="sxs-lookup"><span data-stu-id="9ac21-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ac21-153">列挙型</span><span class="sxs-lookup"><span data-stu-id="9ac21-153">Enumeration</span></span>|<span data-ttu-id="9ac21-154">`LocalMachine` または `CurrentUser` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="9ac21-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="9ac21-155">既定値は、`CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="9ac21-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="9ac21-156">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="9ac21-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="9ac21-157">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="9ac21-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="9ac21-158">既定値は `CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="9ac21-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ac21-159">子要素</span><span class="sxs-lookup"><span data-stu-id="9ac21-159">Child Elements</span></span>  
 <span data-ttu-id="9ac21-160">なし。</span><span class="sxs-lookup"><span data-stu-id="9ac21-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ac21-161">親要素</span><span class="sxs-lookup"><span data-stu-id="9ac21-161">Parent Elements</span></span>  
  
|<span data-ttu-id="9ac21-162">要素</span><span class="sxs-lookup"><span data-stu-id="9ac21-162">Element</span></span>|<span data-ttu-id="9ac21-163">説明</span><span class="sxs-lookup"><span data-stu-id="9ac21-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ac21-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="9ac21-164">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="9ac21-165">ピア サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ac21-166">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ac21-166">Remarks</span></span>  
 <span data-ttu-id="9ac21-167">メッセージ認証を選択した場合は、この要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac21-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="9ac21-168">によって提供される証明書を使用して出力チャネルでは、各メッセージが署名されて[\<証明書 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-168">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="9ac21-169">すべてのメッセージは、アプリケーションに配信される前に、この要素の `customCertificateValidatorType` 属性で指定した検証を使用してメッセージ資格情報がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="9ac21-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="9ac21-170">検証は、資格情報を受け入れることも拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ac21-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ac21-171">例</span><span class="sxs-lookup"><span data-stu-id="9ac21-171">Example</span></span>  
 <span data-ttu-id="9ac21-172">次のコードは、メッセージ送信者検証モードを `PeerOrChainTrust` に設定します。</span><span class="sxs-lookup"><span data-stu-id="9ac21-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ac21-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ac21-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="9ac21-174">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="9ac21-174">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="9ac21-175">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="9ac21-175">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="9ac21-176">[ピア チャネル メッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9ac21-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="9ac21-177">[ピア チャネル カスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9ac21-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="9ac21-178">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="9ac21-178">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
