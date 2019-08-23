---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 7facf3eb54637445d1ae20297effc92605c81a61
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934003"
---
# <a name="peerauthentication"></a><span data-ttu-id="7f16a-101">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="7f16a-101">\<peerAuthentication></span></span>
<span data-ttu-id="7f16a-102">ピア ノードで使用されるピア証明書の認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-102">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="7f16a-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7f16a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7f16a-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="7f16a-104">\<behaviors></span></span>  
<span data-ttu-id="7f16a-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7f16a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="7f16a-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7f16a-106">\<behavior></span></span>  
<span data-ttu-id="7f16a-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="7f16a-107">\<serviceCredentials></span></span>  
<span data-ttu-id="7f16a-108">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="7f16a-108">\<peer></span></span>  
<span data-ttu-id="7f16a-109">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="7f16a-109">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f16a-110">構文</span><span class="sxs-lookup"><span data-stu-id="7f16a-110">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f16a-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7f16a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7f16a-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f16a-113">属性</span><span class="sxs-lookup"><span data-stu-id="7f16a-113">Attributes</span></span>  
  
|<span data-ttu-id="7f16a-114">属性</span><span class="sxs-lookup"><span data-stu-id="7f16a-114">Attribute</span></span>|<span data-ttu-id="7f16a-115">説明</span><span class="sxs-lookup"><span data-stu-id="7f16a-115">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="7f16a-116">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="7f16a-116">Optional enumeration.</span></span> <span data-ttu-id="7f16a-117">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-117">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="7f16a-118">この属性は <xref:System.ServiceModel.Security.X509CertificateValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="7f16a-118">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="7f16a-119">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f16a-119">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="7f16a-120">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="7f16a-120">Optional string.</span></span> <span data-ttu-id="7f16a-121">ユーザー設定タイプの検証に使用されるタイプおよびアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-121">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="7f16a-122">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f16a-122">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="7f16a-123">この属性は <xref:System.IdentityModel.Selectors.X509CertificateValidator> 型です。</span><span class="sxs-lookup"><span data-stu-id="7f16a-123">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="7f16a-124">Windows Communication Foundation (WCF) は、信頼された people ストアに対してピア証明書を検証する既定のピア証明書検証コントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-124">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="7f16a-125">証明書が有効なルートまでつながっていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-125">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="7f16a-126">カスタム検証を実装して別の動作を指定したり、この属性を使用してカスタム検証を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-126">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="7f16a-127">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="7f16a-127">Optional enumeration.</span></span> <span data-ttu-id="7f16a-128">証明書失効モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-128">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="7f16a-129">この属性は <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="7f16a-129">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="7f16a-130">システムは、ピア証明書を失効証明書リストで検索して、それが失効していないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-130">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="7f16a-131">このチェックは、オンラインで、またはキャッシュされた失効リストをチェックする方法で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-131">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="7f16a-132">失効チェックは、この属性を NoCheck に設定することにより無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-132">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="7f16a-133">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="7f16a-133">Optional enumeration.</span></span> <span data-ttu-id="7f16a-134">WCF セキュリティシステムによってピア証明書が検証される、信頼されたストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-134">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="7f16a-135">この属性は <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 型です。</span><span class="sxs-lookup"><span data-stu-id="7f16a-135">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f16a-136">子要素</span><span class="sxs-lookup"><span data-stu-id="7f16a-136">Child Elements</span></span>  
 <span data-ttu-id="7f16a-137">なし。</span><span class="sxs-lookup"><span data-stu-id="7f16a-137">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f16a-138">親要素</span><span class="sxs-lookup"><span data-stu-id="7f16a-138">Parent Elements</span></span>  
  
|<span data-ttu-id="7f16a-139">要素</span><span class="sxs-lookup"><span data-stu-id="7f16a-139">Element</span></span>|<span data-ttu-id="7f16a-140">説明</span><span class="sxs-lookup"><span data-stu-id="7f16a-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f16a-141">\<peer></span><span class="sxs-lookup"><span data-stu-id="7f16a-141">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="7f16a-142">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-142">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f16a-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="7f16a-143">Remarks</span></span>  
 <span data-ttu-id="7f16a-144">`<authentication>` 要素は、<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> クラスに対応します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-144">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="7f16a-145">この要素は、メッシュ内の近隣ノード間の認証時に呼び出される検証コントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-145">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="7f16a-146">新しいピアが近隣ノードとの接続を確立しようとするとき、自身の資格情報を応答側のピアに渡します。</span><span class="sxs-lookup"><span data-stu-id="7f16a-146">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="7f16a-147">リモート パーティの資格情報を検証するために、応答側の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-147">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="7f16a-148">メッシュ内でピア接続が確立されるたびに、両方のピアが相互に認証されます。つまり、双方の検証が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7f16a-148">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f16a-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f16a-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="7f16a-150">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="7f16a-150">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7f16a-151">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="7f16a-151">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="7f16a-152">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="7f16a-152">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="7f16a-153">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="7f16a-153">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="7f16a-154">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="7f16a-154">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
