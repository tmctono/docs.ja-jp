---
title: <messageSenderAuthentication> 要素
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: e7e636571c0dbb1845438c22f7e7509dfc7987f9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204789"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="182a9-102">\<messageSenderAuthentication> 要素</span><span class="sxs-lookup"><span data-stu-id="182a9-102">\<messageSenderAuthentication> element</span></span>

<span data-ttu-id="182a9-103">ピアツーピア メッセージ送信者の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="182a9-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="182a9-104">ピアツーピアプログラミングの詳細については、「 [ピアツーピアネットワーク](../../../wcf/feature-details/peer-to-peer-networking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="182a9-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="182a9-105">構文</span><span class="sxs-lookup"><span data-stu-id="182a9-105">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="182a9-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="182a9-106">Attributes and Elements</span></span>  

 <span data-ttu-id="182a9-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="182a9-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="182a9-108">属性</span><span class="sxs-lookup"><span data-stu-id="182a9-108">Attributes</span></span>  
  
|<span data-ttu-id="182a9-109">属性</span><span class="sxs-lookup"><span data-stu-id="182a9-109">Attribute</span></span>|<span data-ttu-id="182a9-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="182a9-110">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="182a9-111">カスタム型の検証に使用される型およびアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="182a9-111">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="182a9-112">`certificateValidationMode` が `Custom` に設定されている場合は、この属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="182a9-112">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="182a9-113">資格情報の検証に使用される 3 つのモードのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="182a9-113">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="182a9-114">`Custom` に設定されている場合、`customCertificateValidator` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="182a9-114">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="182a9-115">証明書失効リスト (CRL) のチェックに使用されるモードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="182a9-115">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="182a9-116">2 つのシステム格納場所 (`LocalMachine` または `CurrentUser`) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="182a9-116">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="182a9-117">この値は、サービス証明書がクライアントにネゴシエートされるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="182a9-117">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="182a9-118">指定されたストアの場所にある **信頼さ** れた People ストアに対して検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="182a9-118">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="182a9-119">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="182a9-119">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="182a9-120">値</span><span class="sxs-lookup"><span data-stu-id="182a9-120">Value</span></span>|<span data-ttu-id="182a9-121">説明</span><span class="sxs-lookup"><span data-stu-id="182a9-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="182a9-122">String</span><span class="sxs-lookup"><span data-stu-id="182a9-122">String</span></span>|<span data-ttu-id="182a9-123">任意。</span><span class="sxs-lookup"><span data-stu-id="182a9-123">Optional.</span></span> <span data-ttu-id="182a9-124">タイプ名およびアセンブリと、タイプの検索に使用される他のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="182a9-124">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="182a9-125">少なくとも、名前空間とタイプ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="182a9-125">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="182a9-126">省略可能な情報は、アセンブリ名、バージョン番号、カルチャ、および公開キー トークンです。</span><span class="sxs-lookup"><span data-stu-id="182a9-126">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="182a9-127">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="182a9-127">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="182a9-128">値</span><span class="sxs-lookup"><span data-stu-id="182a9-128">Value</span></span>|<span data-ttu-id="182a9-129">[説明]</span><span class="sxs-lookup"><span data-stu-id="182a9-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="182a9-130">列挙</span><span class="sxs-lookup"><span data-stu-id="182a9-130">Enumeration</span></span>|<span data-ttu-id="182a9-131">省略可能。</span><span class="sxs-lookup"><span data-stu-id="182a9-131">Optional.</span></span> <span data-ttu-id="182a9-132">`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust`、`Custom` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="182a9-132">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="182a9-133">既定では、 `ChainTrust`です。</span><span class="sxs-lookup"><span data-stu-id="182a9-133">The default is `ChainTrust`.</span></span> <span data-ttu-id="182a9-134">既定では、 `ChainTrust`です。</span><span class="sxs-lookup"><span data-stu-id="182a9-134">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="182a9-135">詳細については、「 [証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="182a9-135">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="182a9-136">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="182a9-136">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="182a9-137">値</span><span class="sxs-lookup"><span data-stu-id="182a9-137">Value</span></span>|<span data-ttu-id="182a9-138">[説明]</span><span class="sxs-lookup"><span data-stu-id="182a9-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="182a9-139">列挙</span><span class="sxs-lookup"><span data-stu-id="182a9-139">Enumeration</span></span>|<span data-ttu-id="182a9-140">`NoCheck`、`Online`、`Offline` のいずれかの値にします。</span><span class="sxs-lookup"><span data-stu-id="182a9-140">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="182a9-141">既定では、 `Online`です。</span><span class="sxs-lookup"><span data-stu-id="182a9-141">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="182a9-142">詳細については、「 [証明書の使用](../../../wcf/feature-details/working-with-certificates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="182a9-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="182a9-143">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="182a9-143">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="182a9-144">値</span><span class="sxs-lookup"><span data-stu-id="182a9-144">Value</span></span>|<span data-ttu-id="182a9-145">[説明]</span><span class="sxs-lookup"><span data-stu-id="182a9-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="182a9-146">列挙</span><span class="sxs-lookup"><span data-stu-id="182a9-146">Enumeration</span></span>|<span data-ttu-id="182a9-147">次のいずれかの値を指定できます。`LocalMachine` または `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="182a9-147">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="182a9-148">既定では、 `CurrentUser`です。</span><span class="sxs-lookup"><span data-stu-id="182a9-148">The default is `CurrentUser`.</span></span> <span data-ttu-id="182a9-149">クライアント アプリケーションがシステム アカウントで実行されている場合、証明書は通常 `LocalMachine` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="182a9-149">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="182a9-150">クライアント アプリケーションがユーザー アカウントで実行されている場合、証明書は通常 `CurrentUser` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="182a9-150">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="182a9-151">既定では、 `CurrentUser`です。</span><span class="sxs-lookup"><span data-stu-id="182a9-151">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="182a9-152">子要素</span><span class="sxs-lookup"><span data-stu-id="182a9-152">Child Elements</span></span>  

 <span data-ttu-id="182a9-153">なし。</span><span class="sxs-lookup"><span data-stu-id="182a9-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="182a9-154">親要素</span><span class="sxs-lookup"><span data-stu-id="182a9-154">Parent Elements</span></span>  
  
|<span data-ttu-id="182a9-155">要素</span><span class="sxs-lookup"><span data-stu-id="182a9-155">Element</span></span>|<span data-ttu-id="182a9-156">説明</span><span class="sxs-lookup"><span data-stu-id="182a9-156">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="182a9-157">ピア サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="182a9-157">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="182a9-158">解説</span><span class="sxs-lookup"><span data-stu-id="182a9-158">Remarks</span></span>  

 <span data-ttu-id="182a9-159">メッセージ認証を選択した場合は、この要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="182a9-159">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="182a9-160">出力チャネルの場合、各メッセージはによって提供される証明書を使用して署名され [\<certificate>](certificate-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="182a9-160">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="182a9-161">すべてのメッセージは、アプリケーションに配信される前に、この要素の `customCertificateValidatorType` 属性で指定した検証を使用してメッセージ資格情報がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="182a9-161">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="182a9-162">検証は、資格情報を受け入れることも拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="182a9-162">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="182a9-163">例</span><span class="sxs-lookup"><span data-stu-id="182a9-163">Example</span></span>  

 <span data-ttu-id="182a9-164">次のコードは、メッセージ送信者検証モードを `PeerOrChainTrust` に設定します。</span><span class="sxs-lookup"><span data-stu-id="182a9-164">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="182a9-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="182a9-165">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="182a9-166">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="182a9-166">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="182a9-167">ピアツーピアネットワーク</span><span class="sxs-lookup"><span data-stu-id="182a9-167">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="182a9-168">[ピア チャネル メッセージの認証](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="182a9-168">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="182a9-169">[ピア チャネル カスタム認証](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="182a9-169">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="182a9-170">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="182a9-170">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
