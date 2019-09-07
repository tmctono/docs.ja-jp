---
title: <messageSenderAuthentication> 要素
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397788"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="b674a-102">\<> 要素の認証の認証</span><span class="sxs-lookup"><span data-stu-id="b674a-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="b674a-103">ピアツーピア メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b674a-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="b674a-104">ピアツーピアプログラミングの詳細については、「[ピアツーピアネットワーク](../../../wcf/feature-details/peer-to-peer-networking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b674a-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="b674a-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b674a-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b674a-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b674a-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b674a-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b674a-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b674a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b674a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="b674a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b674a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="b674a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="b674a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="b674a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ピア >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="b674a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="b674a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の認証の認証**</span><span class="sxs-lookup"><span data-stu-id="b674a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b674a-113">構文</span><span class="sxs-lookup"><span data-stu-id="b674a-113">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b674a-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b674a-114">Attributes and Elements</span></span>  
 <span data-ttu-id="b674a-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b674a-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b674a-116">属性</span><span class="sxs-lookup"><span data-stu-id="b674a-116">Attributes</span></span>  
  
|<span data-ttu-id="b674a-117">属性</span><span class="sxs-lookup"><span data-stu-id="b674a-117">Attribute</span></span>|<span data-ttu-id="b674a-118">説明</span><span class="sxs-lookup"><span data-stu-id="b674a-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="b674a-119">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="b674a-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="b674a-120">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b674a-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="b674a-121">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b674a-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="b674a-122">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b674a-122">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="b674a-123">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="b674a-123">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="b674a-124">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="b674a-124">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="b674a-125">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b674a-125">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="b674a-126">指定されたストアの場所にある**信頼さ**れた People ストアに対して検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b674a-126">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="b674a-127">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="b674a-127">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="b674a-128">値</span><span class="sxs-lookup"><span data-stu-id="b674a-128">Value</span></span>|<span data-ttu-id="b674a-129">説明</span><span class="sxs-lookup"><span data-stu-id="b674a-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b674a-130">String</span><span class="sxs-lookup"><span data-stu-id="b674a-130">String</span></span>|<span data-ttu-id="b674a-131">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b674a-131">Optional.</span></span> <span data-ttu-id="b674a-132">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="b674a-132">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="b674a-133">少なくとも、名前空間とタイプ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="b674a-133">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="b674a-134">省略可能な情報は、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンです。</span><span class="sxs-lookup"><span data-stu-id="b674a-134">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="b674a-135">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="b674a-135">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="b674a-136">値</span><span class="sxs-lookup"><span data-stu-id="b674a-136">Value</span></span>|<span data-ttu-id="b674a-137">説明</span><span class="sxs-lookup"><span data-stu-id="b674a-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b674a-138">列挙型</span><span class="sxs-lookup"><span data-stu-id="b674a-138">Enumeration</span></span>|<span data-ttu-id="b674a-139">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b674a-139">Optional.</span></span> <span data-ttu-id="b674a-140">`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust`、`Custom` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="b674a-140">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="b674a-141">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="b674a-141">The default is `ChainTrust`.</span></span> <span data-ttu-id="b674a-142">既定値は `ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="b674a-142">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="b674a-143">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b674a-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="b674a-144">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="b674a-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="b674a-145">値</span><span class="sxs-lookup"><span data-stu-id="b674a-145">Value</span></span>|<span data-ttu-id="b674a-146">説明</span><span class="sxs-lookup"><span data-stu-id="b674a-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b674a-147">列挙型</span><span class="sxs-lookup"><span data-stu-id="b674a-147">Enumeration</span></span>|<span data-ttu-id="b674a-148">`NoCheck`、`Online`、`Offline` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="b674a-148">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="b674a-149">既定値は `Online` です。</span><span class="sxs-lookup"><span data-stu-id="b674a-149">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="b674a-150">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b674a-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="b674a-151">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="b674a-151">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="b674a-152">値</span><span class="sxs-lookup"><span data-stu-id="b674a-152">Value</span></span>|<span data-ttu-id="b674a-153">説明</span><span class="sxs-lookup"><span data-stu-id="b674a-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b674a-154">列挙型</span><span class="sxs-lookup"><span data-stu-id="b674a-154">Enumeration</span></span>|<span data-ttu-id="b674a-155">`LocalMachine` または `CurrentUser` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="b674a-155">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="b674a-156">既定値は、`CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="b674a-156">The default is `CurrentUser`.</span></span> <span data-ttu-id="b674a-157">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="b674a-157">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="b674a-158">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="b674a-158">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="b674a-159">既定値は `CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="b674a-159">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b674a-160">子要素</span><span class="sxs-lookup"><span data-stu-id="b674a-160">Child Elements</span></span>  
 <span data-ttu-id="b674a-161">なし。</span><span class="sxs-lookup"><span data-stu-id="b674a-161">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b674a-162">親要素</span><span class="sxs-lookup"><span data-stu-id="b674a-162">Parent Elements</span></span>  
  
|<span data-ttu-id="b674a-163">要素</span><span class="sxs-lookup"><span data-stu-id="b674a-163">Element</span></span>|<span data-ttu-id="b674a-164">説明</span><span class="sxs-lookup"><span data-stu-id="b674a-164">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b674a-165">\<peer></span><span class="sxs-lookup"><span data-stu-id="b674a-165">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="b674a-166">ピア サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="b674a-166">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b674a-167">Remarks</span><span class="sxs-lookup"><span data-stu-id="b674a-167">Remarks</span></span>  
 <span data-ttu-id="b674a-168">メッセージ認証を選択した場合は、この要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b674a-168">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="b674a-169">出力チャネルの場合、各メッセージは、 [ \<証明書 >](certificate-element.md)によって提供される証明書を使用して署名されます。</span><span class="sxs-lookup"><span data-stu-id="b674a-169">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="b674a-170">すべてのメッセージは、アプリケーションに配信される前に、この要素の `customCertificateValidatorType` 属性で指定した検証を使用してメッセージ資格情報がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="b674a-170">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="b674a-171">検証は、資格情報を受け入れることも拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="b674a-171">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b674a-172">例</span><span class="sxs-lookup"><span data-stu-id="b674a-172">Example</span></span>  
 <span data-ttu-id="b674a-173">次のコードは、メッセージ送信者検証モードを `PeerOrChainTrust` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b674a-173">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b674a-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="b674a-174">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="b674a-175">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="b674a-175">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="b674a-176">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="b674a-176">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="b674a-177">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b674a-177">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="b674a-178">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b674a-178">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="b674a-179">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="b674a-179">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
