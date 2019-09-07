---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: c6183a8d27d56c7199b815ccb31b06f983a51b33
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398401"
---
# <a name="messagesenderauthentication"></a><span data-ttu-id="bf3a2-101">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="bf3a2-101">\<messageSenderAuthentication></span></span>
<span data-ttu-id="bf3a2-102">メッセージ送信者により使用されるピア証明書の認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-102">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
<span data-ttu-id="bf3a2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf3a2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf3a2-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bf3a2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bf3a2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bf3a2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="bf3a2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bf3a2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="bf3a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bf3a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="bf3a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="bf3a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="bf3a2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ピア >** ](peer-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="bf3a2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)</span></span>\
<span data-ttu-id="bf3a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の認証の認証**</span><span class="sxs-lookup"><span data-stu-id="bf3a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf3a2-111">構文</span><span class="sxs-lookup"><span data-stu-id="bf3a2-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf3a2-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bf3a2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bf3a2-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf3a2-114">属性</span><span class="sxs-lookup"><span data-stu-id="bf3a2-114">Attributes</span></span>  
  
|<span data-ttu-id="bf3a2-115">属性</span><span class="sxs-lookup"><span data-stu-id="bf3a2-115">Attribute</span></span>|<span data-ttu-id="bf3a2-116">説明</span><span class="sxs-lookup"><span data-stu-id="bf3a2-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="bf3a2-117">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-117">Optional enumeration.</span></span> <span data-ttu-id="bf3a2-118">資格情報の検証に使用される 5 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="bf3a2-119">この属性は <xref:System.ServiceModel.Security.X509CertificateValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="bf3a2-120">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="bf3a2-121">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-121">Optional string.</span></span> <span data-ttu-id="bf3a2-122">ユーザー設定タイプの検証に使用されるタイプおよびアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="bf3a2-123">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="bf3a2-124">この属性は <xref:System.IdentityModel.Selectors.X509CertificateValidator> 型です。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="bf3a2-125">Windows Communication Foundation (WCF) は、信頼された people ストアに対してピア証明書を検証する既定のピア証明書検証コントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-125">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="bf3a2-126">証明書が有効なルートまでつながっていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="bf3a2-127">カスタム検証を実装して別の動作を指定したり、この属性を使用してカスタム検証を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="bf3a2-128">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-128">Optional enumeration.</span></span> <span data-ttu-id="bf3a2-129">証明書失効モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="bf3a2-130">この属性は <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="bf3a2-131">システムは、ピア証明書を失効証明書リストで検索して、それが失効していないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="bf3a2-132">このチェックは、オンラインで、またはキャッシュされた失効リストをチェックする方法で実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="bf3a2-133">失効チェックは、この属性を NoCheck に設定することにより無効にできます。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="bf3a2-134">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-134">Optional enumeration.</span></span> <span data-ttu-id="bf3a2-135">WCF セキュリティシステムによってピア証明書が検証される、信頼されたストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-135">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="bf3a2-136">この属性は <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 型です。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf3a2-137">子要素</span><span class="sxs-lookup"><span data-stu-id="bf3a2-137">Child Elements</span></span>  
 <span data-ttu-id="bf3a2-138">なし。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf3a2-139">親要素</span><span class="sxs-lookup"><span data-stu-id="bf3a2-139">Parent Elements</span></span>  
  
|<span data-ttu-id="bf3a2-140">要素</span><span class="sxs-lookup"><span data-stu-id="bf3a2-140">Element</span></span>|<span data-ttu-id="bf3a2-141">説明</span><span class="sxs-lookup"><span data-stu-id="bf3a2-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf3a2-142">\<peer></span><span class="sxs-lookup"><span data-stu-id="bf3a2-142">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="bf3a2-143">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf3a2-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf3a2-144">Remarks</span></span>  
 <span data-ttu-id="bf3a2-145">メッセージ認証を選択した場合は、この要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="bf3a2-146">出力チャネルの場合、各メッセージは、 [ \<証明書 >](certificate-element.md)によって提供される証明書を使用して署名されます。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-146">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="bf3a2-147">すべてのメッセージは、アプリケーションに配信される前に、この要素の `customCertificateValidatorType` 属性で指定した検証を使用してメッセージ資格情報がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="bf3a2-148">検証は、資格情報を受け入れることも拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf3a2-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3a2-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf3a2-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="bf3a2-150">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="bf3a2-150">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="bf3a2-151">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="bf3a2-151">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="bf3a2-152">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="bf3a2-152">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="bf3a2-153">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="bf3a2-153">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="bf3a2-154">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="bf3a2-154">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
