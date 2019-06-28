---
title: <peerAuthentication> 要素
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 6aa11c50ef950a8a9d902a0fb77fdf301d18f7cb
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423041"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="6352e-102">\<peerAuthentication > 要素</span><span class="sxs-lookup"><span data-stu-id="6352e-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="6352e-103">ピアツーピア クライアントの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6352e-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="6352e-104">ピア ツー ピア プログラミングの詳細については、次を参照してください。[ピア ツー ピア ネットワー キング](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)します。</span><span class="sxs-lookup"><span data-stu-id="6352e-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="6352e-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6352e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6352e-106">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="6352e-106">\<behaviors></span></span>  
<span data-ttu-id="6352e-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="6352e-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="6352e-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6352e-108">\<behavior></span></span>  
<span data-ttu-id="6352e-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="6352e-109">\<clientCredentials></span></span>  
<span data-ttu-id="6352e-110">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="6352e-110">\<peer></span></span>  
<span data-ttu-id="6352e-111">\<PeerAuthentication></span><span class="sxs-lookup"><span data-stu-id="6352e-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6352e-112">構文</span><span class="sxs-lookup"><span data-stu-id="6352e-112">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6352e-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6352e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6352e-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6352e-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6352e-115">属性</span><span class="sxs-lookup"><span data-stu-id="6352e-115">Attributes</span></span>  
  
|<span data-ttu-id="6352e-116">属性</span><span class="sxs-lookup"><span data-stu-id="6352e-116">Attribute</span></span>|<span data-ttu-id="6352e-117">説明</span><span class="sxs-lookup"><span data-stu-id="6352e-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="6352e-118">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="6352e-118">Optional string.</span></span> <span data-ttu-id="6352e-119">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="6352e-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="6352e-120">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6352e-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="6352e-121">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="6352e-121">Optional enumeration.</span></span> <span data-ttu-id="6352e-122">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6352e-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="6352e-123">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6352e-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="6352e-124">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="6352e-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="6352e-125">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="6352e-125">Optional enumeration.</span></span> <span data-ttu-id="6352e-126">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6352e-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="6352e-127">既定値は、`Online` です。</span><span class="sxs-lookup"><span data-stu-id="6352e-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="6352e-128">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="6352e-128">Optional enumeration.</span></span> <span data-ttu-id="6352e-129">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6352e-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="6352e-130">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6352e-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="6352e-131">に対して検証が実行、**信頼されたユーザー**指定したストアの場所に格納します。</span><span class="sxs-lookup"><span data-stu-id="6352e-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="6352e-132">既定値は `CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="6352e-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="6352e-133">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="6352e-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="6352e-134">値</span><span class="sxs-lookup"><span data-stu-id="6352e-134">Value</span></span>|<span data-ttu-id="6352e-135">説明</span><span class="sxs-lookup"><span data-stu-id="6352e-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6352e-136">String</span><span class="sxs-lookup"><span data-stu-id="6352e-136">String</span></span>|<span data-ttu-id="6352e-137">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="6352e-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="6352e-138">少なくとも、名前空間とタイプ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="6352e-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="6352e-139">省略可能な情報は、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンです。</span><span class="sxs-lookup"><span data-stu-id="6352e-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="6352e-140">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="6352e-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="6352e-141">値</span><span class="sxs-lookup"><span data-stu-id="6352e-141">Value</span></span>|<span data-ttu-id="6352e-142">説明</span><span class="sxs-lookup"><span data-stu-id="6352e-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6352e-143">列挙型</span><span class="sxs-lookup"><span data-stu-id="6352e-143">Enumeration</span></span>|<span data-ttu-id="6352e-144">`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust`、`Custom` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="6352e-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="6352e-145">既定値は `ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="6352e-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="6352e-146">詳細については、次を参照してください。 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="6352e-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="6352e-147">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="6352e-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="6352e-148">値</span><span class="sxs-lookup"><span data-stu-id="6352e-148">Value</span></span>|<span data-ttu-id="6352e-149">説明</span><span class="sxs-lookup"><span data-stu-id="6352e-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6352e-150">列挙型</span><span class="sxs-lookup"><span data-stu-id="6352e-150">Enumeration</span></span>|<span data-ttu-id="6352e-151">`NoCheck`、`Online`、`Offline` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="6352e-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="6352e-152">既定値は `Online` です。</span><span class="sxs-lookup"><span data-stu-id="6352e-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="6352e-153">詳細については、次を参照してください。 [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)します。</span><span class="sxs-lookup"><span data-stu-id="6352e-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="6352e-154">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="6352e-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="6352e-155">値</span><span class="sxs-lookup"><span data-stu-id="6352e-155">Value</span></span>|<span data-ttu-id="6352e-156">説明</span><span class="sxs-lookup"><span data-stu-id="6352e-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6352e-157">列挙型</span><span class="sxs-lookup"><span data-stu-id="6352e-157">Enumeration</span></span>|<span data-ttu-id="6352e-158">`LocalMachine` または `CurrentUser` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="6352e-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="6352e-159">既定値は、`CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="6352e-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="6352e-160">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="6352e-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="6352e-161">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="6352e-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6352e-162">子要素</span><span class="sxs-lookup"><span data-stu-id="6352e-162">Child Elements</span></span>  
 <span data-ttu-id="6352e-163">なし。</span><span class="sxs-lookup"><span data-stu-id="6352e-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6352e-164">親要素</span><span class="sxs-lookup"><span data-stu-id="6352e-164">Parent Elements</span></span>  
  
|<span data-ttu-id="6352e-165">要素</span><span class="sxs-lookup"><span data-stu-id="6352e-165">Element</span></span>|<span data-ttu-id="6352e-166">説明</span><span class="sxs-lookup"><span data-stu-id="6352e-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6352e-167">\<peer></span><span class="sxs-lookup"><span data-stu-id="6352e-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="6352e-168">ピア サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="6352e-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6352e-169">Remarks</span><span class="sxs-lookup"><span data-stu-id="6352e-169">Remarks</span></span>  
 <span data-ttu-id="6352e-170">`<authentication>` 要素は、<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> クラスに対応します。</span><span class="sxs-lookup"><span data-stu-id="6352e-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="6352e-171">この要素は、メッシュ内の近隣ノード間の認証時に呼び出される検証コントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="6352e-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="6352e-172">新しいピアが近隣ノードとの接続を確立しようとするとき、自身の資格情報を応答側のピアに渡します。</span><span class="sxs-lookup"><span data-stu-id="6352e-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="6352e-173">リモート パーティの資格情報を検証するために、応答側の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6352e-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="6352e-174">メッシュ内でピア接続が確立されるたびに、両方のピアが相互に認証されます。つまり、双方の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6352e-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6352e-175">例</span><span class="sxs-lookup"><span data-stu-id="6352e-175">Example</span></span>  
 <span data-ttu-id="6352e-176">次のコードは、証明書検証モードを `PeerOrChainTrust` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6352e-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6352e-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="6352e-177">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="6352e-178">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="6352e-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="6352e-179">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="6352e-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="6352e-180">[ピア チャネル メッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6352e-180">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="6352e-181">[ピア チャネル カスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6352e-181">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="6352e-182">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="6352e-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
