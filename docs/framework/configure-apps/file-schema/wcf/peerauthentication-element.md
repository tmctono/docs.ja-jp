---
title: <peerAuthentication> 要素
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 093b0c4b6a7fbf54455ec523b52c1f3a9884cfa8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536016"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="16d1a-102">\<peerAuthentication> 要素</span><span class="sxs-lookup"><span data-stu-id="16d1a-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="16d1a-103">ピアツーピア クライアントの認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="16d1a-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="16d1a-104">ピアツーピアプログラミングの詳細については、「 [ピアツーピアネットワーク](../../../wcf/feature-details/peer-to-peer-networking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16d1a-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="16d1a-105">構文</span><span class="sxs-lookup"><span data-stu-id="16d1a-105">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16d1a-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="16d1a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="16d1a-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="16d1a-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16d1a-108">属性</span><span class="sxs-lookup"><span data-stu-id="16d1a-108">Attributes</span></span>  
  
|<span data-ttu-id="16d1a-109">属性</span><span class="sxs-lookup"><span data-stu-id="16d1a-109">Attribute</span></span>|<span data-ttu-id="16d1a-110">説明</span><span class="sxs-lookup"><span data-stu-id="16d1a-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="16d1a-111">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="16d1a-111">Optional string.</span></span> <span data-ttu-id="16d1a-112">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="16d1a-112">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="16d1a-113">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16d1a-113">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="16d1a-114">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-114">Optional enumeration.</span></span> <span data-ttu-id="16d1a-115">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="16d1a-115">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="16d1a-116">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16d1a-116">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="16d1a-117">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-117">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="16d1a-118">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-118">Optional enumeration.</span></span> <span data-ttu-id="16d1a-119">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="16d1a-119">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="16d1a-120">既定値は、`Online` です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-120">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="16d1a-121">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-121">Optional enumeration.</span></span> <span data-ttu-id="16d1a-122">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="16d1a-122">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="16d1a-123">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="16d1a-123">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="16d1a-124">指定されたストアの場所にある **信頼さ** れた People ストアに対して検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="16d1a-124">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="16d1a-125">既定値は、`CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-125">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="16d1a-126">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="16d1a-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="16d1a-127">[値]</span><span class="sxs-lookup"><span data-stu-id="16d1a-127">Value</span></span>|<span data-ttu-id="16d1a-128">説明</span><span class="sxs-lookup"><span data-stu-id="16d1a-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="16d1a-129">String</span><span class="sxs-lookup"><span data-stu-id="16d1a-129">String</span></span>|<span data-ttu-id="16d1a-130">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="16d1a-130">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="16d1a-131">少なくとも、名前空間とタイプ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-131">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="16d1a-132">省略可能な情報は、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンです。</span><span class="sxs-lookup"><span data-stu-id="16d1a-132">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="16d1a-133">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="16d1a-133">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="16d1a-134">[値]</span><span class="sxs-lookup"><span data-stu-id="16d1a-134">Value</span></span>|<span data-ttu-id="16d1a-135">説明</span><span class="sxs-lookup"><span data-stu-id="16d1a-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="16d1a-136">列挙</span><span class="sxs-lookup"><span data-stu-id="16d1a-136">Enumeration</span></span>|<span data-ttu-id="16d1a-137">`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust`、`Custom` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="16d1a-137">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="16d1a-138">既定値は、`ChainTrust` です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-138">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="16d1a-139">詳細については、「 [証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16d1a-139">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="16d1a-140">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="16d1a-140">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="16d1a-141">[値]</span><span class="sxs-lookup"><span data-stu-id="16d1a-141">Value</span></span>|<span data-ttu-id="16d1a-142">説明</span><span class="sxs-lookup"><span data-stu-id="16d1a-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="16d1a-143">列挙</span><span class="sxs-lookup"><span data-stu-id="16d1a-143">Enumeration</span></span>|<span data-ttu-id="16d1a-144">`NoCheck`、`Online`、`Offline` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="16d1a-144">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="16d1a-145">既定値は、`Online` です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-145">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="16d1a-146">詳細については、「 [証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16d1a-146">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="16d1a-147">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="16d1a-147">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="16d1a-148">[値]</span><span class="sxs-lookup"><span data-stu-id="16d1a-148">Value</span></span>|<span data-ttu-id="16d1a-149">説明</span><span class="sxs-lookup"><span data-stu-id="16d1a-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="16d1a-150">列挙</span><span class="sxs-lookup"><span data-stu-id="16d1a-150">Enumeration</span></span>|<span data-ttu-id="16d1a-151">次のいずれかの値を指定できます。`LocalMachine` または `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="16d1a-151">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="16d1a-152">既定値は、`CurrentUser` です。</span><span class="sxs-lookup"><span data-stu-id="16d1a-152">The default is `CurrentUser`.</span></span> <span data-ttu-id="16d1a-153">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="16d1a-153">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="16d1a-154">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="16d1a-154">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16d1a-155">子要素</span><span class="sxs-lookup"><span data-stu-id="16d1a-155">Child Elements</span></span>  
 <span data-ttu-id="16d1a-156">なし。</span><span class="sxs-lookup"><span data-stu-id="16d1a-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16d1a-157">親要素</span><span class="sxs-lookup"><span data-stu-id="16d1a-157">Parent Elements</span></span>  
  
|<span data-ttu-id="16d1a-158">要素</span><span class="sxs-lookup"><span data-stu-id="16d1a-158">Element</span></span>|<span data-ttu-id="16d1a-159">説明</span><span class="sxs-lookup"><span data-stu-id="16d1a-159">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="16d1a-160">ピア サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="16d1a-160">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16d1a-161">Remarks</span><span class="sxs-lookup"><span data-stu-id="16d1a-161">Remarks</span></span>  
 <span data-ttu-id="16d1a-162">`<authentication>` 要素は、<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> クラスに対応します。</span><span class="sxs-lookup"><span data-stu-id="16d1a-162">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="16d1a-163">この要素は、メッシュ内の近隣ノード間の認証時に呼び出される検証コントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="16d1a-163">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="16d1a-164">新しいピアが近隣ノードとの接続を確立しようとするとき、自身の資格情報を応答側のピアに渡します。</span><span class="sxs-lookup"><span data-stu-id="16d1a-164">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="16d1a-165">リモート パーティの資格情報を検証するために、応答側の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="16d1a-165">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="16d1a-166">メッシュ内でピア接続が確立されるたびに、両方のピアが相互に認証されます。つまり、双方の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="16d1a-166">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16d1a-167">例</span><span class="sxs-lookup"><span data-stu-id="16d1a-167">Example</span></span>  
 <span data-ttu-id="16d1a-168">次のコードは、証明書検証モードを `PeerOrChainTrust` に設定します。</span><span class="sxs-lookup"><span data-stu-id="16d1a-168">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="16d1a-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="16d1a-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="16d1a-170">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="16d1a-170">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="16d1a-171">ピアツーピアネットワーク</span><span class="sxs-lookup"><span data-stu-id="16d1a-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="16d1a-172">[ピア チャネル メッセージの認証](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="16d1a-172">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="16d1a-173">[ピア チャネル カスタム認証](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="16d1a-173">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="16d1a-174">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="16d1a-174">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
