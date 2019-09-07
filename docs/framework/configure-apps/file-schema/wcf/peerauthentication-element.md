---
title: <peerAuthentication> 要素
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 4c29c84a2cc56a890c8273e410ba31b5f3900732
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400079"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="233f4-102">\<peerAuthentication > 要素</span><span class="sxs-lookup"><span data-stu-id="233f4-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="233f4-103">ピアツーピア クライアントの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="233f4-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="233f4-104">ピアツーピアプログラミングの詳細については、「[ピアツーピアネットワーク](../../../wcf/feature-details/peer-to-peer-networking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233f4-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="233f4-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="233f4-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="233f4-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="233f4-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="233f4-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="233f4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="233f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="233f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="233f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="233f4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="233f4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="233f4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="233f4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ピア >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="233f4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="233f4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<peerAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="233f4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="233f4-113">構文</span><span class="sxs-lookup"><span data-stu-id="233f4-113">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="233f4-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="233f4-114">Attributes and Elements</span></span>  
 <span data-ttu-id="233f4-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="233f4-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="233f4-116">属性</span><span class="sxs-lookup"><span data-stu-id="233f4-116">Attributes</span></span>  
  
|<span data-ttu-id="233f4-117">属性</span><span class="sxs-lookup"><span data-stu-id="233f4-117">Attribute</span></span>|<span data-ttu-id="233f4-118">説明</span><span class="sxs-lookup"><span data-stu-id="233f4-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="233f4-119">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="233f4-119">Optional string.</span></span> <span data-ttu-id="233f4-120">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="233f4-120">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="233f4-121">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="233f4-121">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="233f4-122">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="233f4-122">Optional enumeration.</span></span> <span data-ttu-id="233f4-123">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="233f4-123">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="233f4-124">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="233f4-124">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="233f4-125">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="233f4-125">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="233f4-126">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="233f4-126">Optional enumeration.</span></span> <span data-ttu-id="233f4-127">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="233f4-127">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="233f4-128">既定値は、`Online` です。</span><span class="sxs-lookup"><span data-stu-id="233f4-128">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="233f4-129">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="233f4-129">Optional enumeration.</span></span> <span data-ttu-id="233f4-130">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="233f4-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="233f4-131">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="233f4-131">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="233f4-132">指定されたストアの場所にある**信頼さ**れた People ストアに対して検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="233f4-132">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="233f4-133">既定値は `CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="233f4-133">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="233f4-134">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="233f4-134">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="233f4-135">値</span><span class="sxs-lookup"><span data-stu-id="233f4-135">Value</span></span>|<span data-ttu-id="233f4-136">説明</span><span class="sxs-lookup"><span data-stu-id="233f4-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="233f4-137">String</span><span class="sxs-lookup"><span data-stu-id="233f4-137">String</span></span>|<span data-ttu-id="233f4-138">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="233f4-138">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="233f4-139">少なくとも、名前空間とタイプ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="233f4-139">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="233f4-140">省略可能な情報は、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンです。</span><span class="sxs-lookup"><span data-stu-id="233f4-140">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="233f4-141">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="233f4-141">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="233f4-142">値</span><span class="sxs-lookup"><span data-stu-id="233f4-142">Value</span></span>|<span data-ttu-id="233f4-143">説明</span><span class="sxs-lookup"><span data-stu-id="233f4-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="233f4-144">列挙型</span><span class="sxs-lookup"><span data-stu-id="233f4-144">Enumeration</span></span>|<span data-ttu-id="233f4-145">`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust`、`Custom` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="233f4-145">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="233f4-146">既定値は `ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="233f4-146">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="233f4-147">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233f4-147">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="233f4-148">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="233f4-148">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="233f4-149">値</span><span class="sxs-lookup"><span data-stu-id="233f4-149">Value</span></span>|<span data-ttu-id="233f4-150">説明</span><span class="sxs-lookup"><span data-stu-id="233f4-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="233f4-151">列挙型</span><span class="sxs-lookup"><span data-stu-id="233f4-151">Enumeration</span></span>|<span data-ttu-id="233f4-152">`NoCheck`、`Online`、`Offline` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="233f4-152">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="233f4-153">既定値は `Online` です。</span><span class="sxs-lookup"><span data-stu-id="233f4-153">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="233f4-154">詳細については、「[証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="233f4-154">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="233f4-155">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="233f4-155">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="233f4-156">値</span><span class="sxs-lookup"><span data-stu-id="233f4-156">Value</span></span>|<span data-ttu-id="233f4-157">説明</span><span class="sxs-lookup"><span data-stu-id="233f4-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="233f4-158">列挙型</span><span class="sxs-lookup"><span data-stu-id="233f4-158">Enumeration</span></span>|<span data-ttu-id="233f4-159">`LocalMachine` または `CurrentUser` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="233f4-159">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="233f4-160">既定値は、`CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="233f4-160">The default is `CurrentUser`.</span></span> <span data-ttu-id="233f4-161">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="233f4-161">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="233f4-162">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="233f4-162">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="233f4-163">子要素</span><span class="sxs-lookup"><span data-stu-id="233f4-163">Child Elements</span></span>  
 <span data-ttu-id="233f4-164">なし。</span><span class="sxs-lookup"><span data-stu-id="233f4-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="233f4-165">親要素</span><span class="sxs-lookup"><span data-stu-id="233f4-165">Parent Elements</span></span>  
  
|<span data-ttu-id="233f4-166">要素</span><span class="sxs-lookup"><span data-stu-id="233f4-166">Element</span></span>|<span data-ttu-id="233f4-167">説明</span><span class="sxs-lookup"><span data-stu-id="233f4-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="233f4-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="233f4-168">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="233f4-169">ピア サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="233f4-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="233f4-170">Remarks</span><span class="sxs-lookup"><span data-stu-id="233f4-170">Remarks</span></span>  
 <span data-ttu-id="233f4-171">`<authentication>` 要素は、<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> クラスに対応します。</span><span class="sxs-lookup"><span data-stu-id="233f4-171">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="233f4-172">この要素は、メッシュ内の近隣ノード間の認証時に呼び出される検証コントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="233f4-172">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="233f4-173">新しいピアが近隣ノードとの接続を確立しようとするとき、自身の資格情報を応答側のピアに渡します。</span><span class="sxs-lookup"><span data-stu-id="233f4-173">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="233f4-174">リモート パーティの資格情報を検証するために、応答側の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="233f4-174">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="233f4-175">メッシュ内でピア接続が確立されるたびに、両方のピアが相互に認証されます。つまり、双方の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="233f4-175">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="233f4-176">例</span><span class="sxs-lookup"><span data-stu-id="233f4-176">Example</span></span>  
 <span data-ttu-id="233f4-177">次のコードは、証明書検証モードを `PeerOrChainTrust` に設定します。</span><span class="sxs-lookup"><span data-stu-id="233f4-177">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="233f4-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="233f4-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="233f4-179">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="233f4-179">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="233f4-180">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="233f4-180">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="233f4-181">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="233f4-181">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="233f4-182">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="233f4-182">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="233f4-183">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="233f4-183">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
