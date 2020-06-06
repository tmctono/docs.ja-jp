---
title: <message>の要素<wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 8e0903dd1313e68e2de65730e129079199ebe2f2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738986"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="6a6ea-102">\<message>の要素\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="6a6ea-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="6a6ea-103">のメッセージレベルセキュリティの設定を定義し [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="6a6ea-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a6ea-104">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
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
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a6ea-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6a6ea-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6a6ea-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a6ea-107">属性</span><span class="sxs-lookup"><span data-stu-id="6a6ea-107">Attributes</span></span>  
  
|<span data-ttu-id="6a6ea-108">属性</span><span class="sxs-lookup"><span data-stu-id="6a6ea-108">Attribute</span></span>|<span data-ttu-id="6a6ea-109">説明</span><span class="sxs-lookup"><span data-stu-id="6a6ea-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a6ea-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="6a6ea-110">algorithmSuite</span></span>|<span data-ttu-id="6a6ea-111">メッセージの暗号化とキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="6a6ea-112">この属性の有効な値については、「algorithmSuite 属性」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-112">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="6a6ea-113">既定値は `Basic256` です。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-113">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="6a6ea-114">この属性は <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 型です。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-114">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="6a6ea-115">これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-115">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="6a6ea-116">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="6a6ea-116">issuedKeyType</span></span>|<span data-ttu-id="6a6ea-117">発行されるキーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="6a6ea-118">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6a6ea-119">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="6a6ea-119">-   SymmetricKey</span></span><br /><span data-ttu-id="6a6ea-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="6a6ea-120">-   PublicKey</span></span><br /><br /> <span data-ttu-id="6a6ea-121">既定値は、`SymmetricKey` です。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-121">The default is `SymmetricKey`.</span></span> <span data-ttu-id="6a6ea-122">この属性は <xref:System.IdentityModel.Tokens.SecurityKeyType> 型です。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="6a6ea-123">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="6a6ea-123">issuedTokenType</span></span>|<span data-ttu-id="6a6ea-124">発行されるトークンの型を指定する URI を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-124">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="6a6ea-125">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-125">The default is `null`.</span></span>|  
|<span data-ttu-id="6a6ea-126">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="6a6ea-126">negotiateServiceCredential</span></span>|<span data-ttu-id="6a6ea-127">サービス資格情報がネゴシエーションの一部として交換されるか、帯域外で使用できるかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-127">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="6a6ea-128">既定値は `true` で、サービス資格情報がネゴシエートされます。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-128">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="6a6ea-129">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="6a6ea-129">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="6a6ea-130">値</span><span class="sxs-lookup"><span data-stu-id="6a6ea-130">Value</span></span>|<span data-ttu-id="6a6ea-131">Description</span><span class="sxs-lookup"><span data-stu-id="6a6ea-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6a6ea-132">Basic128</span><span class="sxs-lookup"><span data-stu-id="6a6ea-132">Basic128</span></span>|<span data-ttu-id="6a6ea-133">Basic128 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-133">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-134">Basic192</span><span class="sxs-lookup"><span data-stu-id="6a6ea-134">Basic192</span></span>|<span data-ttu-id="6a6ea-135">Basic192 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-135">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-136">Basic256</span><span class="sxs-lookup"><span data-stu-id="6a6ea-136">Basic256</span></span>|<span data-ttu-id="6a6ea-137">Basic256 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-137">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-138">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6a6ea-138">Basic256Rsa15</span></span>|<span data-ttu-id="6a6ea-139">メッセージの暗号化には Basic256 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-139">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-140">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="6a6ea-140">Basic192Rsa15</span></span>|<span data-ttu-id="6a6ea-141">メッセージの暗号化には Basic192 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-141">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-142">TripleDes</span><span class="sxs-lookup"><span data-stu-id="6a6ea-142">TripleDes</span></span>|<span data-ttu-id="6a6ea-143">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-143">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-144">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="6a6ea-144">Basic128Rsa15</span></span>|<span data-ttu-id="6a6ea-145">メッセージの暗号化には Basic128 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-145">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-146">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="6a6ea-146">TripleDesRsa15</span></span>|<span data-ttu-id="6a6ea-147">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-147">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-148">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="6a6ea-148">Basic128Sha256</span></span>|<span data-ttu-id="6a6ea-149">メッセージの暗号化には Basic128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-149">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-150">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="6a6ea-150">Basic192Sha256</span></span>|<span data-ttu-id="6a6ea-151">メッセージの暗号化には Basic192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-151">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-152">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="6a6ea-152">Basic256Sha256</span></span>|<span data-ttu-id="6a6ea-153">メッセージの暗号化には Basic256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-153">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-154">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="6a6ea-154">TripleDesSha256</span></span>|<span data-ttu-id="6a6ea-155">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-155">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-156">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6a6ea-156">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="6a6ea-157">メッセージの暗号化には Basic128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-157">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-158">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6a6ea-158">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="6a6ea-159">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-159">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-160">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6a6ea-160">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="6a6ea-161">メッセージの暗号化には Basic256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-161">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6a6ea-162">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6a6ea-162">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="6a6ea-163">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-163">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a6ea-164">子要素</span><span class="sxs-lookup"><span data-stu-id="6a6ea-164">Child Elements</span></span>  
  
|<span data-ttu-id="6a6ea-165">要素</span><span class="sxs-lookup"><span data-stu-id="6a6ea-165">Element</span></span>|<span data-ttu-id="6a6ea-166">Description</span><span class="sxs-lookup"><span data-stu-id="6a6ea-166">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="6a6ea-167">このバインディングのクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-167">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="6a6ea-168">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-168">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="6a6ea-169">発行者</span><span class="sxs-lookup"><span data-stu-id="6a6ea-169">issuer</span></span>|<span data-ttu-id="6a6ea-170">セキュリティ トークンを発行するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-170">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="6a6ea-171">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-171">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="6a6ea-172">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="6a6ea-172">issuerMetadata</span></span>|<span data-ttu-id="6a6ea-173">発行者のエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-173">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="6a6ea-174">トークン要求パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-174">A collection of token request parameters.</span></span> <span data-ttu-id="6a6ea-175">各パラメーターは、XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-175">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a6ea-176">親要素</span><span class="sxs-lookup"><span data-stu-id="6a6ea-176">Parent Elements</span></span>  
  
|<span data-ttu-id="6a6ea-177">要素</span><span class="sxs-lookup"><span data-stu-id="6a6ea-177">Element</span></span>|<span data-ttu-id="6a6ea-178">Description</span><span class="sxs-lookup"><span data-stu-id="6a6ea-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="6a6ea-179">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6a6ea-179">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a6ea-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a6ea-180">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="6a6ea-181">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="6a6ea-181">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6a6ea-182">バインド</span><span class="sxs-lookup"><span data-stu-id="6a6ea-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6a6ea-183">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="6a6ea-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6a6ea-184">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="6a6ea-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
