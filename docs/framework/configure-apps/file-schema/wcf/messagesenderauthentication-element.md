---
title: <messageSenderAuthentication> 要素
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 1e63b6fa93e1abfa87c83da4b5d46f492c59b9bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931373"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="292ec-102">\<> 要素の認証の認証</span><span class="sxs-lookup"><span data-stu-id="292ec-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="292ec-103">ピアツーピア メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="292ec-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="292ec-104">ピアツーピアプログラミングの詳細については、「[ピアツーピアネットワーク](../../../wcf/feature-details/peer-to-peer-networking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="292ec-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="292ec-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="292ec-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="292ec-106">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="292ec-106">\<behaviors></span></span>  
<span data-ttu-id="292ec-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="292ec-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="292ec-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="292ec-108">\<behavior></span></span>  
<span data-ttu-id="292ec-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="292ec-109">\<clientCredentials></span></span>  
<span data-ttu-id="292ec-110">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="292ec-110">\<peer></span></span>  
<span data-ttu-id="292ec-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="292ec-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="292ec-112">構文</span><span class="sxs-lookup"><span data-stu-id="292ec-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="292ec-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="292ec-113">Attributes and Elements</span></span>  
 <span data-ttu-id="292ec-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="292ec-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="292ec-115">属性</span><span class="sxs-lookup"><span data-stu-id="292ec-115">Attributes</span></span>  
  
|<span data-ttu-id="292ec-116">属性</span><span class="sxs-lookup"><span data-stu-id="292ec-116">Attribute</span></span>|<span data-ttu-id="292ec-117">説明</span><span class="sxs-lookup"><span data-stu-id="292ec-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="292ec-118">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="292ec-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="292ec-119">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="292ec-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="292ec-120">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="292ec-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="292ec-121">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="292ec-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="292ec-122">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="292ec-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="292ec-123">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="292ec-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="292ec-124">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="292ec-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="292ec-125">指定されたストアの場所にある**信頼さ**れた People ストアに対して検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="292ec-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="292ec-126">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="292ec-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="292ec-127">値</span><span class="sxs-lookup"><span data-stu-id="292ec-127">Value</span></span>|<span data-ttu-id="292ec-128">説明</span><span class="sxs-lookup"><span data-stu-id="292ec-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="292ec-129">String</span><span class="sxs-lookup"><span data-stu-id="292ec-129">String</span></span>|<span data-ttu-id="292ec-130">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="292ec-130">Optional.</span></span> <span data-ttu-id="292ec-131">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="292ec-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="292ec-132">少なくとも、名前空間とタイプ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="292ec-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="292ec-133">省略可能な情報は、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンです。</span><span class="sxs-lookup"><span data-stu-id="292ec-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="292ec-134">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="292ec-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="292ec-135">値</span><span class="sxs-lookup"><span data-stu-id="292ec-135">Value</span></span>|<span data-ttu-id="292ec-136">説明</span><span class="sxs-lookup"><span data-stu-id="292ec-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="292ec-137">列挙型</span><span class="sxs-lookup"><span data-stu-id="292ec-137">Enumeration</span></span>|<span data-ttu-id="292ec-138">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="292ec-138">Optional.</span></span> <span data-ttu-id="292ec-139">`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust`、`Custom` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="292ec-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="292ec-140">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="292ec-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="292ec-141">既定値は `ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="292ec-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="292ec-142">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="292ec-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="292ec-143">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="292ec-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="292ec-144">値</span><span class="sxs-lookup"><span data-stu-id="292ec-144">Value</span></span>|<span data-ttu-id="292ec-145">説明</span><span class="sxs-lookup"><span data-stu-id="292ec-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="292ec-146">列挙型</span><span class="sxs-lookup"><span data-stu-id="292ec-146">Enumeration</span></span>|<span data-ttu-id="292ec-147">`NoCheck`、`Online`、`Offline` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="292ec-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="292ec-148">既定値は `Online` です。</span><span class="sxs-lookup"><span data-stu-id="292ec-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="292ec-149">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="292ec-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="292ec-150">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="292ec-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="292ec-151">値</span><span class="sxs-lookup"><span data-stu-id="292ec-151">Value</span></span>|<span data-ttu-id="292ec-152">説明</span><span class="sxs-lookup"><span data-stu-id="292ec-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="292ec-153">列挙型</span><span class="sxs-lookup"><span data-stu-id="292ec-153">Enumeration</span></span>|<span data-ttu-id="292ec-154">`LocalMachine` または `CurrentUser` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="292ec-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="292ec-155">既定値は、`CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="292ec-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="292ec-156">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="292ec-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="292ec-157">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="292ec-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="292ec-158">既定値は `CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="292ec-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="292ec-159">子要素</span><span class="sxs-lookup"><span data-stu-id="292ec-159">Child Elements</span></span>  
 <span data-ttu-id="292ec-160">なし。</span><span class="sxs-lookup"><span data-stu-id="292ec-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="292ec-161">親要素</span><span class="sxs-lookup"><span data-stu-id="292ec-161">Parent Elements</span></span>  
  
|<span data-ttu-id="292ec-162">要素</span><span class="sxs-lookup"><span data-stu-id="292ec-162">Element</span></span>|<span data-ttu-id="292ec-163">説明</span><span class="sxs-lookup"><span data-stu-id="292ec-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="292ec-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="292ec-164">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="292ec-165">ピア サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="292ec-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="292ec-166">Remarks</span><span class="sxs-lookup"><span data-stu-id="292ec-166">Remarks</span></span>  
 <span data-ttu-id="292ec-167">メッセージ認証を選択した場合は、この要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="292ec-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="292ec-168">出力チャネルの場合、各メッセージは、 [ \<証明書 >](certificate-element.md)によって提供される証明書を使用して署名されます。</span><span class="sxs-lookup"><span data-stu-id="292ec-168">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="292ec-169">すべてのメッセージは、アプリケーションに配信される前に、この要素の `customCertificateValidatorType` 属性で指定した検証を使用してメッセージ資格情報がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="292ec-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="292ec-170">検証は、資格情報を受け入れることも拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="292ec-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="292ec-171">例</span><span class="sxs-lookup"><span data-stu-id="292ec-171">Example</span></span>  
 <span data-ttu-id="292ec-172">次のコードは、メッセージ送信者検証モードを `PeerOrChainTrust` に設定します。</span><span class="sxs-lookup"><span data-stu-id="292ec-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="292ec-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="292ec-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="292ec-174">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="292ec-174">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="292ec-175">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="292ec-175">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="292ec-176">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="292ec-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="292ec-177">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="292ec-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="292ec-178">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="292ec-178">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
