---
title: <wsFederationHttpBinding> の <message> 要素
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 8e0903dd1313e68e2de65730e129079199ebe2f2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738986"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="68865-102">\<message > 要素 \<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="68865-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="68865-103">[\<wsFederationHttpBinding >](wsfederationhttpbinding.md)のメッセージレベルセキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="68865-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="68865-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="68865-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="68865-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="68865-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="68865-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="68865-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="68865-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="68865-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="68865-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="68865-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="68865-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**セキュリティ >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="68865-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="68865-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**メッセージ >**</span><span class="sxs-lookup"><span data-stu-id="68865-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68865-111">構文</span><span class="sxs-lookup"><span data-stu-id="68865-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68865-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="68865-112">Attributes and Elements</span></span>  
 <span data-ttu-id="68865-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="68865-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68865-114">属性</span><span class="sxs-lookup"><span data-stu-id="68865-114">Attributes</span></span>  
  
|<span data-ttu-id="68865-115">属性</span><span class="sxs-lookup"><span data-stu-id="68865-115">Attribute</span></span>|<span data-ttu-id="68865-116">説明</span><span class="sxs-lookup"><span data-stu-id="68865-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68865-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="68865-117">algorithmSuite</span></span>|<span data-ttu-id="68865-118">メッセージの暗号化とキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="68865-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="68865-119">この属性の有効な値については、「algorithmSuite 属性」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68865-119">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="68865-120">既定値は `Basic256`です。</span><span class="sxs-lookup"><span data-stu-id="68865-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="68865-121">この属性は <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 型です。</span><span class="sxs-lookup"><span data-stu-id="68865-121">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="68865-122">これらのアルゴリズムは、Security Policy Language (WS-SecurityPolicy) の仕様で指定されているアルゴリズムに対応付けられています。</span><span class="sxs-lookup"><span data-stu-id="68865-122">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="68865-123">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="68865-123">issuedKeyType</span></span>|<span data-ttu-id="68865-124">発行されるキーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="68865-124">Specifies the type of key to be issued.</span></span> <span data-ttu-id="68865-125">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="68865-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="68865-126">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="68865-126">-   SymmetricKey</span></span><br /><span data-ttu-id="68865-127">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="68865-127">-   PublicKey</span></span><br /><br /> <span data-ttu-id="68865-128">既定値は、 `SymmetricKey`です。</span><span class="sxs-lookup"><span data-stu-id="68865-128">The default is `SymmetricKey`.</span></span> <span data-ttu-id="68865-129">この属性は <xref:System.IdentityModel.Tokens.SecurityKeyType> 型です。</span><span class="sxs-lookup"><span data-stu-id="68865-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="68865-130">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="68865-130">issuedTokenType</span></span>|<span data-ttu-id="68865-131">発行されるトークンの型を指定する URI を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="68865-131">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="68865-132">既定値は、 `null`です。</span><span class="sxs-lookup"><span data-stu-id="68865-132">The default is `null`.</span></span>|  
|<span data-ttu-id="68865-133">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="68865-133">negotiateServiceCredential</span></span>|<span data-ttu-id="68865-134">サービス資格情報がネゴシエーションの一部として交換されるか、帯域外で使用できるかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="68865-134">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="68865-135">既定値は `true` で、サービス資格情報がネゴシエートされます。</span><span class="sxs-lookup"><span data-stu-id="68865-135">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="68865-136">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="68865-136">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="68865-137">[値]</span><span class="sxs-lookup"><span data-stu-id="68865-137">Value</span></span>|<span data-ttu-id="68865-138">説明</span><span class="sxs-lookup"><span data-stu-id="68865-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68865-139">Basic128</span><span class="sxs-lookup"><span data-stu-id="68865-139">Basic128</span></span>|<span data-ttu-id="68865-140">Basic128 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-140">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="68865-141">Basic192</span><span class="sxs-lookup"><span data-stu-id="68865-141">Basic192</span></span>|<span data-ttu-id="68865-142">Basic192 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-142">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="68865-143">Basic256</span><span class="sxs-lookup"><span data-stu-id="68865-143">Basic256</span></span>|<span data-ttu-id="68865-144">Basic256 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-144">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="68865-145">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="68865-145">Basic256Rsa15</span></span>|<span data-ttu-id="68865-146">メッセージの暗号化には Basic256 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-146">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="68865-147">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="68865-147">Basic192Rsa15</span></span>|<span data-ttu-id="68865-148">メッセージの暗号化には Basic192 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-148">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="68865-149">TripleDes</span><span class="sxs-lookup"><span data-stu-id="68865-149">TripleDes</span></span>|<span data-ttu-id="68865-150">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-150">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="68865-151">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="68865-151">Basic128Rsa15</span></span>|<span data-ttu-id="68865-152">メッセージの暗号化には Basic128 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-152">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="68865-153">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="68865-153">TripleDesRsa15</span></span>|<span data-ttu-id="68865-154">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-154">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="68865-155">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="68865-155">Basic128Sha256</span></span>|<span data-ttu-id="68865-156">メッセージの暗号化には Basic128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-156">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="68865-157">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="68865-157">Basic192Sha256</span></span>|<span data-ttu-id="68865-158">メッセージの暗号化には Basic192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-158">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="68865-159">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="68865-159">Basic256Sha256</span></span>|<span data-ttu-id="68865-160">メッセージの暗号化には Basic256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-160">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="68865-161">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="68865-161">TripleDesSha256</span></span>|<span data-ttu-id="68865-162">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="68865-163">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="68865-163">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="68865-164">メッセージの暗号化には Basic128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-164">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="68865-165">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="68865-165">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="68865-166">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-166">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="68865-167">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="68865-167">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="68865-168">メッセージの暗号化には Basic256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-168">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="68865-169">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="68865-169">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="68865-170">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68865-170">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68865-171">子要素</span><span class="sxs-lookup"><span data-stu-id="68865-171">Child Elements</span></span>  
  
|<span data-ttu-id="68865-172">要素</span><span class="sxs-lookup"><span data-stu-id="68865-172">Element</span></span>|<span data-ttu-id="68865-173">説明</span><span class="sxs-lookup"><span data-stu-id="68865-173">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68865-174">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="68865-174">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="68865-175">このバインディングのクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="68865-175">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="68865-176">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="68865-176">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="68865-177">issuer</span><span class="sxs-lookup"><span data-stu-id="68865-177">issuer</span></span>|<span data-ttu-id="68865-178">セキュリティ トークンを発行するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="68865-178">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="68865-179">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="68865-179">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="68865-180">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="68865-180">issuerMetadata</span></span>|<span data-ttu-id="68865-181">発行者のエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="68865-181">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="68865-182">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="68865-182">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="68865-183">トークン要求パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="68865-183">A collection of token request parameters.</span></span> <span data-ttu-id="68865-184">各パラメーターは、XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="68865-184">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68865-185">親要素</span><span class="sxs-lookup"><span data-stu-id="68865-185">Parent Elements</span></span>  
  
|<span data-ttu-id="68865-186">要素</span><span class="sxs-lookup"><span data-stu-id="68865-186">Element</span></span>|<span data-ttu-id="68865-187">説明</span><span class="sxs-lookup"><span data-stu-id="68865-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68865-188">\< セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="68865-188">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="68865-189">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="68865-189">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68865-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="68865-190">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="68865-191">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="68865-191">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="68865-192">バインディング</span><span class="sxs-lookup"><span data-stu-id="68865-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="68865-193">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="68865-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="68865-194">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="68865-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="68865-195">\<binding ></span><span class="sxs-lookup"><span data-stu-id="68865-195">\<binding></span></span>](bindings.md)
