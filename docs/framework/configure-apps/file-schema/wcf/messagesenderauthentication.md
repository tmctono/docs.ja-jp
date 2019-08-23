---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: c1d3662b2ceda83eb32abe99244e926332214698
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931323"
---
# <a name="messagesenderauthentication"></a><span data-ttu-id="c8bfb-101">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="c8bfb-101">\<messageSenderAuthentication></span></span>
<span data-ttu-id="c8bfb-102">メッセージ送信者により使用されるピア証明書の認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-102">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="c8bfb-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c8bfb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c8bfb-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="c8bfb-104">\<behaviors></span></span>  
<span data-ttu-id="c8bfb-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c8bfb-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="c8bfb-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c8bfb-106">\<behavior></span></span>  
<span data-ttu-id="c8bfb-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="c8bfb-107">\<serviceCredentials></span></span>  
<span data-ttu-id="c8bfb-108">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="c8bfb-108">\<peer></span></span>  
<span data-ttu-id="c8bfb-109">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="c8bfb-109">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8bfb-110">構文</span><span class="sxs-lookup"><span data-stu-id="c8bfb-110">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8bfb-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c8bfb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c8bfb-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8bfb-113">属性</span><span class="sxs-lookup"><span data-stu-id="c8bfb-113">Attributes</span></span>  
  
|<span data-ttu-id="c8bfb-114">属性</span><span class="sxs-lookup"><span data-stu-id="c8bfb-114">Attribute</span></span>|<span data-ttu-id="c8bfb-115">説明</span><span class="sxs-lookup"><span data-stu-id="c8bfb-115">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="c8bfb-116">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-116">Optional enumeration.</span></span> <span data-ttu-id="c8bfb-117">資格情報の検証に使用される 5 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-117">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="c8bfb-118">この属性は <xref:System.ServiceModel.Security.X509CertificateValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-118">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="c8bfb-119">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-119">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="c8bfb-120">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-120">Optional string.</span></span> <span data-ttu-id="c8bfb-121">ユーザー設定タイプの検証に使用されるタイプおよびアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-121">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="c8bfb-122">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-122">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="c8bfb-123">この属性は <xref:System.IdentityModel.Selectors.X509CertificateValidator> 型です。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-123">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="c8bfb-124">Windows Communication Foundation (WCF) は、信頼された people ストアに対してピア証明書を検証する既定のピア証明書検証コントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-124">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="c8bfb-125">証明書が有効なルートまでつながっていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-125">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="c8bfb-126">カスタム検証を実装して別の動作を指定したり、この属性を使用してカスタム検証を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-126">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="c8bfb-127">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-127">Optional enumeration.</span></span> <span data-ttu-id="c8bfb-128">証明書失効モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-128">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="c8bfb-129">この属性は <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-129">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="c8bfb-130">システムは、ピア証明書を失効証明書リストで検索して、それが失効していないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-130">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="c8bfb-131">このチェックは、オンラインで、またはキャッシュされた失効リストをチェックする方法で実行されます。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-131">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="c8bfb-132">失効チェックは、この属性を NoCheck に設定することにより無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-132">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="c8bfb-133">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-133">Optional enumeration.</span></span> <span data-ttu-id="c8bfb-134">WCF セキュリティシステムによってピア証明書が検証される、信頼されたストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-134">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="c8bfb-135">この属性は <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 型です。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-135">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8bfb-136">子要素</span><span class="sxs-lookup"><span data-stu-id="c8bfb-136">Child Elements</span></span>  
 <span data-ttu-id="c8bfb-137">なし。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-137">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8bfb-138">親要素</span><span class="sxs-lookup"><span data-stu-id="c8bfb-138">Parent Elements</span></span>  
  
|<span data-ttu-id="c8bfb-139">要素</span><span class="sxs-lookup"><span data-stu-id="c8bfb-139">Element</span></span>|<span data-ttu-id="c8bfb-140">説明</span><span class="sxs-lookup"><span data-stu-id="c8bfb-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8bfb-141">\<peer></span><span class="sxs-lookup"><span data-stu-id="c8bfb-141">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="c8bfb-142">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-142">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8bfb-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8bfb-143">Remarks</span></span>  
 <span data-ttu-id="c8bfb-144">メッセージ認証を選択した場合は、この要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-144">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="c8bfb-145">出力チャネルの場合、各メッセージは、 [ \<証明書 >](certificate-element.md)によって提供される証明書を使用して署名されます。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-145">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="c8bfb-146">すべてのメッセージは、アプリケーションに配信される前に、この要素の `customCertificateValidatorType` 属性で指定した検証を使用してメッセージ資格情報がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-146">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="c8bfb-147">検証は、資格情報を受け入れることも拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8bfb-147">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8bfb-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8bfb-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="c8bfb-149">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="c8bfb-149">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c8bfb-150">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="c8bfb-150">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="c8bfb-151">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c8bfb-151">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="c8bfb-152">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c8bfb-152">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="c8bfb-153">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="c8bfb-153">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
