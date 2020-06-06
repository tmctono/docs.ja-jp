---
title: <message>の要素<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: dde763687dbc62d6fb342a21a4c614208f28d7e8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738995"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="e0bae-102">\<message>の要素\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e0bae-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="e0bae-103">要素のメッセージレベルセキュリティの設定を定義 [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="e0bae-104">構文</span><span class="sxs-lookup"><span data-stu-id="e0bae-104">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0bae-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e0bae-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e0bae-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0bae-107">属性</span><span class="sxs-lookup"><span data-stu-id="e0bae-107">Attributes</span></span>  
  
|<span data-ttu-id="e0bae-108">属性</span><span class="sxs-lookup"><span data-stu-id="e0bae-108">Attribute</span></span>|<span data-ttu-id="e0bae-109">説明</span><span class="sxs-lookup"><span data-stu-id="e0bae-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="e0bae-110">省略可能。</span><span class="sxs-lookup"><span data-stu-id="e0bae-110">Optional.</span></span> <span data-ttu-id="e0bae-111">メッセージの暗号化、署名、およびキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-111">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="e0bae-112">アルゴリズムとキー サイズは、<xref:System.ServiceModel.Security.SecurityAlgorithmSuite> クラスにより決まります。</span><span class="sxs-lookup"><span data-stu-id="e0bae-112">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="e0bae-113">これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。</span><span class="sxs-lookup"><span data-stu-id="e0bae-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="e0bae-114">それぞれの値については次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0bae-114">See the following table for possible values.</span></span> <span data-ttu-id="e0bae-115">既定値は Basic256 です。</span><span class="sxs-lookup"><span data-stu-id="e0bae-115">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="e0bae-116">発行されるキーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-116">Specifies the type of key to be issued.</span></span> <span data-ttu-id="e0bae-117">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0bae-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e0bae-118">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="e0bae-118">-   SymmetricKey</span></span><br /><span data-ttu-id="e0bae-119">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="e0bae-119">-   PublicKey</span></span><br /><span data-ttu-id="e0bae-120">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="e0bae-120">-   BearerKey</span></span><br /><br /> <span data-ttu-id="e0bae-121">既定値は SymmetricKey です。</span><span class="sxs-lookup"><span data-stu-id="e0bae-121">The default is SymmetricKey.</span></span> <span data-ttu-id="e0bae-122">この属性は <xref:System.IdentityModel.Tokens.SecurityKeyType> 型です。</span><span class="sxs-lookup"><span data-stu-id="e0bae-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="e0bae-123">発行されるトークンの型を指定する URI。</span><span class="sxs-lookup"><span data-stu-id="e0bae-123">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="e0bae-124">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="e0bae-124">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="e0bae-125">サービス資格情報がネゴシエーションの一部として交換されるか、帯域外で使用できるかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="e0bae-125">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="e0bae-126">既定値は `true` で、サービス資格情報がネゴシエートされます。</span><span class="sxs-lookup"><span data-stu-id="e0bae-126">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="e0bae-127">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="e0bae-127">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="e0bae-128">値</span><span class="sxs-lookup"><span data-stu-id="e0bae-128">Value</span></span>|<span data-ttu-id="e0bae-129">Description</span><span class="sxs-lookup"><span data-stu-id="e0bae-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e0bae-130">Basic128</span><span class="sxs-lookup"><span data-stu-id="e0bae-130">Basic128</span></span>|<span data-ttu-id="e0bae-131">Aes128 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-131">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-132">Basic192</span><span class="sxs-lookup"><span data-stu-id="e0bae-132">Basic192</span></span>|<span data-ttu-id="e0bae-133">Aes192 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-133">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-134">Basic256</span><span class="sxs-lookup"><span data-stu-id="e0bae-134">Basic256</span></span>|<span data-ttu-id="e0bae-135">Aes256 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-135">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-136">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e0bae-136">Basic256Rsa15</span></span>|<span data-ttu-id="e0bae-137">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-137">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-138">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="e0bae-138">Basic192Rsa15</span></span>|<span data-ttu-id="e0bae-139">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-139">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-140">TripleDes</span><span class="sxs-lookup"><span data-stu-id="e0bae-140">TripleDes</span></span>|<span data-ttu-id="e0bae-141">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-141">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-142">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="e0bae-142">Basic128Rsa15</span></span>|<span data-ttu-id="e0bae-143">メッセージの暗号化には Aes128 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-143">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-144">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="e0bae-144">TripleDesRsa15</span></span>|<span data-ttu-id="e0bae-145">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-145">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-146">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="e0bae-146">Basic128Sha256</span></span>|<span data-ttu-id="e0bae-147">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-147">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-148">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="e0bae-148">Basic192Sha256</span></span>|<span data-ttu-id="e0bae-149">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-149">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-150">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="e0bae-150">Basic256Sha256</span></span>|<span data-ttu-id="e0bae-151">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-151">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-152">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="e0bae-152">TripleDesSha256</span></span>|<span data-ttu-id="e0bae-153">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-153">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-154">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e0bae-154">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="e0bae-155">メッセージの暗号化には Aes128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-155">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-156">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e0bae-156">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="e0bae-157">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-157">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-158">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e0bae-158">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="e0bae-159">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-159">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e0bae-160">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e0bae-160">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="e0bae-161">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0bae-162">子要素</span><span class="sxs-lookup"><span data-stu-id="e0bae-162">Child Elements</span></span>  
  
|<span data-ttu-id="e0bae-163">要素</span><span class="sxs-lookup"><span data-stu-id="e0bae-163">Element</span></span>|<span data-ttu-id="e0bae-164">Description</span><span class="sxs-lookup"><span data-stu-id="e0bae-164">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="e0bae-165">このバインディングのクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-165">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="e0bae-166">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="e0bae-166">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="e0bae-167">セキュリティ トークンを発行するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-167">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="e0bae-168">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="e0bae-168">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="e0bae-169">発行者のエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-169">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="e0bae-170">トークン要求パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="e0bae-170">A collection of token request parameters.</span></span> <span data-ttu-id="e0bae-171">各パラメーターは、XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="e0bae-171">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e0bae-172">親要素</span><span class="sxs-lookup"><span data-stu-id="e0bae-172">Parent Elements</span></span>  
  
|<span data-ttu-id="e0bae-173">要素</span><span class="sxs-lookup"><span data-stu-id="e0bae-173">Element</span></span>|<span data-ttu-id="e0bae-174">Description</span><span class="sxs-lookup"><span data-stu-id="e0bae-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="e0bae-175">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e0bae-175">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0bae-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0bae-176">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="e0bae-177">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e0bae-177">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e0bae-178">バインド</span><span class="sxs-lookup"><span data-stu-id="e0bae-178">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e0bae-179">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="e0bae-179">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e0bae-180">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="e0bae-180">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
