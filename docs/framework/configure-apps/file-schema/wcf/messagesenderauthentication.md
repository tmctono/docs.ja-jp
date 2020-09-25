---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: e7888d01838312aa51397ca39133edb9318fac80
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204776"
---
# \<messageSenderAuthentication>

<span data-ttu-id="90eb3-101">メッセージ送信者により使用されるピア証明書の認証設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-101">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="90eb3-102">構文</span><span class="sxs-lookup"><span data-stu-id="90eb3-102">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90eb3-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="90eb3-103">Attributes and Elements</span></span>  

 <span data-ttu-id="90eb3-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90eb3-105">属性</span><span class="sxs-lookup"><span data-stu-id="90eb3-105">Attributes</span></span>  
  
|<span data-ttu-id="90eb3-106">属性</span><span class="sxs-lookup"><span data-stu-id="90eb3-106">Attribute</span></span>|<span data-ttu-id="90eb3-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="90eb3-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="90eb3-108">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="90eb3-108">Optional enumeration.</span></span> <span data-ttu-id="90eb3-109">資格情報の検証に使用される 5 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-109">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="90eb3-110">この属性は <xref:System.ServiceModel.Security.X509CertificateValidationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="90eb3-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="90eb3-111">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90eb3-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="90eb3-112">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="90eb3-112">Optional string.</span></span> <span data-ttu-id="90eb3-113">ユーザー設定タイプの検証に使用されるタイプおよびアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="90eb3-114">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90eb3-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="90eb3-115">この属性は <xref:System.IdentityModel.Selectors.X509CertificateValidator> 型です。</span><span class="sxs-lookup"><span data-stu-id="90eb3-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="90eb3-116">Windows Communication Foundation (WCF) は、信頼された people ストアに対してピア証明書を検証する既定のピア証明書検証コントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="90eb3-117">証明書が有効なルートまでつながっていることを検証します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="90eb3-118">カスタム検証を実装して別の動作を指定したり、この属性を使用してカスタム検証を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="90eb3-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="90eb3-119">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="90eb3-119">Optional enumeration.</span></span> <span data-ttu-id="90eb3-120">証明書失効モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="90eb3-121">この属性は <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="90eb3-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="90eb3-122">システムは、ピア証明書を失効証明書リストで検索して、それが失効していないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="90eb3-123">このチェックは、オンラインで、またはキャッシュされた失効リストをチェックする方法で実行されます。</span><span class="sxs-lookup"><span data-stu-id="90eb3-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="90eb3-124">失効チェックは、この属性を NoCheck に設定することにより無効にできます。</span><span class="sxs-lookup"><span data-stu-id="90eb3-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="90eb3-125">省略可能な列挙体です。</span><span class="sxs-lookup"><span data-stu-id="90eb3-125">Optional enumeration.</span></span> <span data-ttu-id="90eb3-126">WCF セキュリティシステムによってピア証明書が検証される、信頼されたストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="90eb3-127">この属性は <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 型です。</span><span class="sxs-lookup"><span data-stu-id="90eb3-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90eb3-128">子要素</span><span class="sxs-lookup"><span data-stu-id="90eb3-128">Child Elements</span></span>  

 <span data-ttu-id="90eb3-129">なし。</span><span class="sxs-lookup"><span data-stu-id="90eb3-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90eb3-130">親要素</span><span class="sxs-lookup"><span data-stu-id="90eb3-130">Parent Elements</span></span>  
  
|<span data-ttu-id="90eb3-131">要素</span><span class="sxs-lookup"><span data-stu-id="90eb3-131">Element</span></span>|<span data-ttu-id="90eb3-132">説明</span><span class="sxs-lookup"><span data-stu-id="90eb3-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="90eb3-133">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="90eb3-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90eb3-134">解説</span><span class="sxs-lookup"><span data-stu-id="90eb3-134">Remarks</span></span>  

 <span data-ttu-id="90eb3-135">メッセージ認証を選択した場合は、この要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90eb3-135">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="90eb3-136">出力チャネルの場合、各メッセージはによって提供される証明書を使用して署名され [\<certificate>](certificate-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="90eb3-136">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="90eb3-137">すべてのメッセージは、アプリケーションに配信される前に、この要素の `customCertificateValidatorType` 属性で指定した検証を使用してメッセージ資格情報がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="90eb3-137">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="90eb3-138">検証は、資格情報を受け入れることも拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="90eb3-138">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90eb3-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="90eb3-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="90eb3-140">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="90eb3-140">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="90eb3-141">ピアツーピアネットワーク</span><span class="sxs-lookup"><span data-stu-id="90eb3-141">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="90eb3-142">[ピア チャネル メッセージの認証](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="90eb3-142">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="90eb3-143">[ピア チャネル カスタム認証](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="90eb3-143">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="90eb3-144">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="90eb3-144">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
