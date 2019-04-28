---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: b8643a5321bbab692ebb704101c664105b4ab55c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763946"
---
# <a name="messagesenderauthentication"></a><span data-ttu-id="ca26d-101">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="ca26d-101">\<messageSenderAuthentication></span></span>
<span data-ttu-id="ca26d-102">メッセージ送信者により使用されるピア証明書の認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-102">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="ca26d-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ca26d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ca26d-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="ca26d-104">\<behaviors></span></span>  
<span data-ttu-id="ca26d-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ca26d-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="ca26d-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ca26d-106">\<behavior></span></span>  
<span data-ttu-id="ca26d-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ca26d-107">\<serviceCredentials></span></span>  
<span data-ttu-id="ca26d-108">\<ピア ></span><span class="sxs-lookup"><span data-stu-id="ca26d-108">\<peer></span></span>  
<span data-ttu-id="ca26d-109">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="ca26d-109">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca26d-110">構文</span><span class="sxs-lookup"><span data-stu-id="ca26d-110">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca26d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ca26d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ca26d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca26d-113">属性</span><span class="sxs-lookup"><span data-stu-id="ca26d-113">Attributes</span></span>  
  
|<span data-ttu-id="ca26d-114">属性</span><span class="sxs-lookup"><span data-stu-id="ca26d-114">Attribute</span></span>|<span data-ttu-id="ca26d-115">説明</span><span class="sxs-lookup"><span data-stu-id="ca26d-115">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="ca26d-116">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="ca26d-116">Optional enumeration.</span></span> <span data-ttu-id="ca26d-117">資格情報の検証に使用される 5 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-117">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="ca26d-118">この属性は <xref:System.ServiceModel.Security.X509CertificateValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="ca26d-118">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="ca26d-119">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca26d-119">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="ca26d-120">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="ca26d-120">Optional string.</span></span> <span data-ttu-id="ca26d-121">ユーザー設定タイプの検証に使用されるタイプおよびアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-121">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="ca26d-122">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca26d-122">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="ca26d-123">この属性は <xref:System.IdentityModel.Selectors.X509CertificateValidator> 型です。</span><span class="sxs-lookup"><span data-stu-id="ca26d-123">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="ca26d-124">Windows Communication Foundation (WCF) は、既定のピア信頼されたユーザー ストアに対してピア証明書を検証する証明書検証を提供します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-124">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="ca26d-125">証明書が有効なルートまでつながっていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-125">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="ca26d-126">カスタム検証を実装して別の動作を指定したり、この属性を使用してカスタム検証を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ca26d-126">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="ca26d-127">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="ca26d-127">Optional enumeration.</span></span> <span data-ttu-id="ca26d-128">証明書失効モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-128">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="ca26d-129">この属性は <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="ca26d-129">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="ca26d-130">システムは、ピア証明書を失効証明書リストで検索して、それが失効していないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-130">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="ca26d-131">このチェックは、オンラインで、またはキャッシュされた失効リストをチェックする方法で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ca26d-131">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="ca26d-132">失効チェックは、この属性を NoCheck に設定することにより無効にできます。</span><span class="sxs-lookup"><span data-stu-id="ca26d-132">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="ca26d-133">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="ca26d-133">Optional enumeration.</span></span> <span data-ttu-id="ca26d-134">WCF セキュリティ システムによってピア証明書を検証する信頼されたストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-134">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="ca26d-135">この属性は <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 型です。</span><span class="sxs-lookup"><span data-stu-id="ca26d-135">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca26d-136">子要素</span><span class="sxs-lookup"><span data-stu-id="ca26d-136">Child Elements</span></span>  
 <span data-ttu-id="ca26d-137">なし。</span><span class="sxs-lookup"><span data-stu-id="ca26d-137">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca26d-138">親要素</span><span class="sxs-lookup"><span data-stu-id="ca26d-138">Parent Elements</span></span>  
  
|<span data-ttu-id="ca26d-139">要素</span><span class="sxs-lookup"><span data-stu-id="ca26d-139">Element</span></span>|<span data-ttu-id="ca26d-140">説明</span><span class="sxs-lookup"><span data-stu-id="ca26d-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca26d-141">\<peer></span><span class="sxs-lookup"><span data-stu-id="ca26d-141">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="ca26d-142">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-142">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca26d-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca26d-143">Remarks</span></span>  
 <span data-ttu-id="ca26d-144">メッセージ認証を選択した場合は、この要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca26d-144">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="ca26d-145">によって提供される証明書を使用して出力チャネルでは、各メッセージが署名されて[\<証明書 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="ca26d-145">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="ca26d-146">すべてのメッセージは、アプリケーションに配信される前に、この要素の `customCertificateValidatorType` 属性で指定した検証を使用してメッセージ資格情報がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="ca26d-146">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="ca26d-147">検証は、資格情報を受け入れることも拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca26d-147">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca26d-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca26d-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="ca26d-149">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="ca26d-149">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ca26d-150">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ca26d-150">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="ca26d-151">[ピア チャネル メッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ca26d-151">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="ca26d-152">[ピア チャネル カスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ca26d-152">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="ca26d-153">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="ca26d-153">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
