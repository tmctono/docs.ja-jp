---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: b627105dc4aae49557b0a6684569719622e13f08
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180597"
---
# <a name="peerauthentication"></a><span data-ttu-id="1fa1d-101">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="1fa1d-101">\<peerAuthentication></span></span>
<span data-ttu-id="1fa1d-102">ピア ノードで使用されるピア証明書の認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-102">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="1fa1d-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1fa1d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1fa1d-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="1fa1d-104">\<behaviors></span></span>  
<span data-ttu-id="1fa1d-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1fa1d-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1fa1d-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1fa1d-106">\<behavior></span></span>  
<span data-ttu-id="1fa1d-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1fa1d-107">\<serviceCredentials></span></span>  
<span data-ttu-id="1fa1d-108">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="1fa1d-108">\<peer></span></span>  
<span data-ttu-id="1fa1d-109">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="1fa1d-109">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fa1d-110">構文</span><span class="sxs-lookup"><span data-stu-id="1fa1d-110">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fa1d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1fa1d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1fa1d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fa1d-113">属性</span><span class="sxs-lookup"><span data-stu-id="1fa1d-113">Attributes</span></span>  
  
|<span data-ttu-id="1fa1d-114">属性</span><span class="sxs-lookup"><span data-stu-id="1fa1d-114">Attribute</span></span>|<span data-ttu-id="1fa1d-115">説明</span><span class="sxs-lookup"><span data-stu-id="1fa1d-115">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="1fa1d-116">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-116">Optional enumeration.</span></span> <span data-ttu-id="1fa1d-117">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-117">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="1fa1d-118">この属性は <xref:System.ServiceModel.Security.X509CertificateValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-118">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="1fa1d-119">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-119">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="1fa1d-120">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-120">Optional string.</span></span> <span data-ttu-id="1fa1d-121">ユーザー設定タイプの検証に使用されるタイプおよびアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-121">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="1fa1d-122">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-122">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="1fa1d-123">この属性は <xref:System.IdentityModel.Selectors.X509CertificateValidator> 型です。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-123">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="1fa1d-124">Windows Communication Foundation (WCF) は、既定のピア信頼されたユーザー ストアに対してピア証明書を検証する証明書検証を提供します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-124">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="1fa1d-125">証明書が有効なルートまでつながっていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-125">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="1fa1d-126">カスタム検証を実装して別の動作を指定したり、この属性を使用してカスタム検証を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-126">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="1fa1d-127">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-127">Optional enumeration.</span></span> <span data-ttu-id="1fa1d-128">証明書失効モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-128">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="1fa1d-129">この属性は <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-129">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="1fa1d-130">システムは、ピア証明書を失効証明書リストで検索して、それが失効していないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-130">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="1fa1d-131">このチェックは、オンラインで、またはキャッシュされた失効リストをチェックする方法で実行されます。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-131">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="1fa1d-132">失効チェックは、この属性を NoCheck に設定することにより無効にできます。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-132">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="1fa1d-133">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-133">Optional enumeration.</span></span> <span data-ttu-id="1fa1d-134">WCF セキュリティ システムによってピア証明書を検証する信頼されたストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-134">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="1fa1d-135">この属性は <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 型です。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-135">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fa1d-136">子要素</span><span class="sxs-lookup"><span data-stu-id="1fa1d-136">Child Elements</span></span>  
 <span data-ttu-id="1fa1d-137">なし。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-137">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1fa1d-138">親要素</span><span class="sxs-lookup"><span data-stu-id="1fa1d-138">Parent Elements</span></span>  
  
|<span data-ttu-id="1fa1d-139">要素</span><span class="sxs-lookup"><span data-stu-id="1fa1d-139">Element</span></span>|<span data-ttu-id="1fa1d-140">説明</span><span class="sxs-lookup"><span data-stu-id="1fa1d-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fa1d-141">\<peer></span><span class="sxs-lookup"><span data-stu-id="1fa1d-141">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="1fa1d-142">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-142">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fa1d-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="1fa1d-143">Remarks</span></span>  
 <span data-ttu-id="1fa1d-144">`<authentication>` 要素は、<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> クラスに対応します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-144">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="1fa1d-145">この要素は、メッシュ内の近隣ノード間の認証時に呼び出される検証コントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-145">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="1fa1d-146">新しいピアが近隣ノードとの接続を確立しようとするとき、自身の資格情報を応答側のピアに渡します。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-146">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="1fa1d-147">リモート パーティの資格情報を検証するために、応答側の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-147">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="1fa1d-148">メッシュ内でピア接続が確立されるたびに、両方のピアが相互に認証されます。つまり、双方の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1fa1d-148">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fa1d-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fa1d-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="1fa1d-150">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="1fa1d-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1fa1d-151">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="1fa1d-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1fa1d-152">[ピア チャネル メッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1fa1d-152">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1fa1d-153">[ピア チャネル カスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1fa1d-153">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1fa1d-154">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="1fa1d-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
