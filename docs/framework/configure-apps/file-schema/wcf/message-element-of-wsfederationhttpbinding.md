---
title: <message>の要素<wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 4730d7e573eefdfcd5704621d0a7ccaa15f76d3a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931578"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="8b26e-102">\<wsFederationHttpBinding > の\<メッセージ > 要素</span><span class="sxs-lookup"><span data-stu-id="8b26e-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="8b26e-103">[ \<WsFederationHttpBinding >](wsfederationhttpbinding.md)のメッセージレベルセキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="8b26e-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8b26e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8b26e-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8b26e-105">\<bindings></span></span>  
<span data-ttu-id="8b26e-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="8b26e-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="8b26e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8b26e-107">\<binding></span></span>  
<span data-ttu-id="8b26e-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="8b26e-108">\<security></span></span>  
<span data-ttu-id="8b26e-109">\<message></span><span class="sxs-lookup"><span data-stu-id="8b26e-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b26e-110">構文</span><span class="sxs-lookup"><span data-stu-id="8b26e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b26e-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8b26e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8b26e-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b26e-113">属性</span><span class="sxs-lookup"><span data-stu-id="8b26e-113">Attributes</span></span>  
  
|<span data-ttu-id="8b26e-114">属性</span><span class="sxs-lookup"><span data-stu-id="8b26e-114">Attribute</span></span>|<span data-ttu-id="8b26e-115">説明</span><span class="sxs-lookup"><span data-stu-id="8b26e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b26e-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="8b26e-116">algorithmSuite</span></span>|<span data-ttu-id="8b26e-117">メッセージの暗号化とキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="8b26e-118">この属性の有効な値については、「algorithmSuite 属性」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b26e-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="8b26e-119">既定値は `Basic256` です。</span><span class="sxs-lookup"><span data-stu-id="8b26e-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="8b26e-120">この属性は <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 型です。</span><span class="sxs-lookup"><span data-stu-id="8b26e-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="8b26e-121">これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。</span><span class="sxs-lookup"><span data-stu-id="8b26e-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="8b26e-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="8b26e-122">issuedKeyType</span></span>|<span data-ttu-id="8b26e-123">発行されるキーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="8b26e-124">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8b26e-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8b26e-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="8b26e-125">-   SymmetricKey</span></span><br /><span data-ttu-id="8b26e-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="8b26e-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="8b26e-127">既定値は `SymmetricKey` です。</span><span class="sxs-lookup"><span data-stu-id="8b26e-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="8b26e-128">この属性は <xref:System.IdentityModel.Tokens.SecurityKeyType> 型です。</span><span class="sxs-lookup"><span data-stu-id="8b26e-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="8b26e-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="8b26e-129">issuedTokenType</span></span>|<span data-ttu-id="8b26e-130">発行されるトークンの型を指定する URI を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="8b26e-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="8b26e-131">既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="8b26e-131">The default is `null`.</span></span>|  
|<span data-ttu-id="8b26e-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="8b26e-132">negotiateServiceCredential</span></span>|<span data-ttu-id="8b26e-133">サービス資格情報がネゴシエーションの一部として交換されるか、帯域外で使用できるかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="8b26e-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="8b26e-134">既定値は `true` で、サービス資格情報がネゴシエートされます。</span><span class="sxs-lookup"><span data-stu-id="8b26e-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="8b26e-135">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="8b26e-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="8b26e-136">値</span><span class="sxs-lookup"><span data-stu-id="8b26e-136">Value</span></span>|<span data-ttu-id="8b26e-137">説明</span><span class="sxs-lookup"><span data-stu-id="8b26e-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8b26e-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="8b26e-138">Basic128</span></span>|<span data-ttu-id="8b26e-139">Basic128 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="8b26e-140">Basic192</span></span>|<span data-ttu-id="8b26e-141">Basic192 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="8b26e-142">Basic256</span></span>|<span data-ttu-id="8b26e-143">Basic256 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8b26e-144">Basic256Rsa15</span></span>|<span data-ttu-id="8b26e-145">メッセージの暗号化には Basic256 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="8b26e-146">Basic192Rsa15</span></span>|<span data-ttu-id="8b26e-147">メッセージの暗号化には Basic192 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="8b26e-148">TripleDes</span></span>|<span data-ttu-id="8b26e-149">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="8b26e-150">Basic128Rsa15</span></span>|<span data-ttu-id="8b26e-151">メッセージの暗号化には Basic128 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="8b26e-152">TripleDesRsa15</span></span>|<span data-ttu-id="8b26e-153">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="8b26e-154">Basic128Sha256</span></span>|<span data-ttu-id="8b26e-155">メッセージの暗号化には Basic128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="8b26e-156">Basic192Sha256</span></span>|<span data-ttu-id="8b26e-157">メッセージの暗号化には Basic192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="8b26e-158">Basic256Sha256</span></span>|<span data-ttu-id="8b26e-159">メッセージの暗号化には Basic256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="8b26e-160">TripleDesSha256</span></span>|<span data-ttu-id="8b26e-161">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8b26e-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="8b26e-163">メッセージの暗号化には Basic128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8b26e-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="8b26e-165">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8b26e-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="8b26e-167">メッセージの暗号化には Basic256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="8b26e-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="8b26e-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="8b26e-169">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b26e-170">子要素</span><span class="sxs-lookup"><span data-stu-id="8b26e-170">Child Elements</span></span>  
  
|<span data-ttu-id="8b26e-171">要素</span><span class="sxs-lookup"><span data-stu-id="8b26e-171">Element</span></span>|<span data-ttu-id="8b26e-172">説明</span><span class="sxs-lookup"><span data-stu-id="8b26e-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b26e-173">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="8b26e-173">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="8b26e-174">このバインディングのクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="8b26e-175">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8b26e-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="8b26e-176">issuer</span><span class="sxs-lookup"><span data-stu-id="8b26e-176">issuer</span></span>|<span data-ttu-id="8b26e-177">セキュリティ トークンを発行するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="8b26e-178">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="8b26e-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="8b26e-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="8b26e-179">issuerMetadata</span></span>|<span data-ttu-id="8b26e-180">発行者のエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="8b26e-181">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="8b26e-181">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="8b26e-182">トークン要求パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="8b26e-182">A collection of token request parameters.</span></span> <span data-ttu-id="8b26e-183">各パラメーターは、XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="8b26e-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b26e-184">親要素</span><span class="sxs-lookup"><span data-stu-id="8b26e-184">Parent Elements</span></span>  
  
|<span data-ttu-id="8b26e-185">要素</span><span class="sxs-lookup"><span data-stu-id="8b26e-185">Element</span></span>|<span data-ttu-id="8b26e-186">説明</span><span class="sxs-lookup"><span data-stu-id="8b26e-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b26e-187">\<security></span><span class="sxs-lookup"><span data-stu-id="8b26e-187">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="8b26e-188">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b26e-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b26e-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b26e-189">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="8b26e-190">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="8b26e-190">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8b26e-191">バインディング</span><span class="sxs-lookup"><span data-stu-id="8b26e-191">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8b26e-192">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="8b26e-192">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8b26e-193">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="8b26e-193">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8b26e-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="8b26e-194">\<binding></span></span>](../../../misc/binding.md)
