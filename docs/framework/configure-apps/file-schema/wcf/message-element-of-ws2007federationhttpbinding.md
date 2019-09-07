---
title: <message>の要素<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: b1128bda6068a1fe3d8f5bb5ac29cc349f023b5b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397849"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="5372c-102">\<ws2007FederationHttpBinding > の\<メッセージ > 要素</span><span class="sxs-lookup"><span data-stu-id="5372c-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="5372c-103">Ws2007FederationHttpBinding > 要素の[ \<](ws2007federationhttpbinding.md)メッセージレベルセキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="5372c-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="5372c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5372c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5372c-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5372c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5372c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="5372c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="5372c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="5372c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="5372c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="5372c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="5372c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-element-of-ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="5372c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="5372c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<メッセージ >**</span><span class="sxs-lookup"><span data-stu-id="5372c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5372c-111">構文</span><span class="sxs-lookup"><span data-stu-id="5372c-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5372c-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5372c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5372c-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5372c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5372c-114">属性</span><span class="sxs-lookup"><span data-stu-id="5372c-114">Attributes</span></span>  
  
|<span data-ttu-id="5372c-115">属性</span><span class="sxs-lookup"><span data-stu-id="5372c-115">Attribute</span></span>|<span data-ttu-id="5372c-116">説明</span><span class="sxs-lookup"><span data-stu-id="5372c-116">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="5372c-117">任意。</span><span class="sxs-lookup"><span data-stu-id="5372c-117">Optional.</span></span> <span data-ttu-id="5372c-118">メッセージの暗号化、署名、およびキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="5372c-118">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="5372c-119">アルゴリズムとキー サイズは、<xref:System.ServiceModel.Security.SecurityAlgorithmSuite> クラスにより決まります。</span><span class="sxs-lookup"><span data-stu-id="5372c-119">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="5372c-120">これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。</span><span class="sxs-lookup"><span data-stu-id="5372c-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="5372c-121">それぞれの値については次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5372c-121">See the following table for possible values.</span></span> <span data-ttu-id="5372c-122">既定値は Basic256 です。</span><span class="sxs-lookup"><span data-stu-id="5372c-122">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="5372c-123">発行されるキーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5372c-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="5372c-124">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5372c-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5372c-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="5372c-125">-   SymmetricKey</span></span><br /><span data-ttu-id="5372c-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="5372c-126">-   PublicKey</span></span><br /><span data-ttu-id="5372c-127">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="5372c-127">-   BearerKey</span></span><br /><br /> <span data-ttu-id="5372c-128">既定値は SymmetricKey です。</span><span class="sxs-lookup"><span data-stu-id="5372c-128">The default is SymmetricKey.</span></span> <span data-ttu-id="5372c-129">この属性は <xref:System.IdentityModel.Tokens.SecurityKeyType> 型です。</span><span class="sxs-lookup"><span data-stu-id="5372c-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="5372c-130">発行されるトークンの型を指定する URI。</span><span class="sxs-lookup"><span data-stu-id="5372c-130">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="5372c-131">既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="5372c-131">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="5372c-132">サービス資格情報がネゴシエーションの一部として交換されるか、帯域外で使用できるかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="5372c-132">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="5372c-133">既定値は `true` で、サービス資格情報がネゴシエートされます。</span><span class="sxs-lookup"><span data-stu-id="5372c-133">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="5372c-134">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="5372c-134">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="5372c-135">値</span><span class="sxs-lookup"><span data-stu-id="5372c-135">Value</span></span>|<span data-ttu-id="5372c-136">説明</span><span class="sxs-lookup"><span data-stu-id="5372c-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5372c-137">Basic128</span><span class="sxs-lookup"><span data-stu-id="5372c-137">Basic128</span></span>|<span data-ttu-id="5372c-138">Aes128 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-138">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5372c-139">Basic192</span><span class="sxs-lookup"><span data-stu-id="5372c-139">Basic192</span></span>|<span data-ttu-id="5372c-140">Aes192 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-140">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5372c-141">Basic256</span><span class="sxs-lookup"><span data-stu-id="5372c-141">Basic256</span></span>|<span data-ttu-id="5372c-142">Aes256 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-142">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5372c-143">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5372c-143">Basic256Rsa15</span></span>|<span data-ttu-id="5372c-144">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-144">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5372c-145">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="5372c-145">Basic192Rsa15</span></span>|<span data-ttu-id="5372c-146">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-146">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5372c-147">TripleDes</span><span class="sxs-lookup"><span data-stu-id="5372c-147">TripleDes</span></span>|<span data-ttu-id="5372c-148">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-148">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5372c-149">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="5372c-149">Basic128Rsa15</span></span>|<span data-ttu-id="5372c-150">メッセージの暗号化には Aes128 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-150">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5372c-151">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="5372c-151">TripleDesRsa15</span></span>|<span data-ttu-id="5372c-152">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-152">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5372c-153">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="5372c-153">Basic128Sha256</span></span>|<span data-ttu-id="5372c-154">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-154">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5372c-155">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="5372c-155">Basic192Sha256</span></span>|<span data-ttu-id="5372c-156">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5372c-157">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="5372c-157">Basic256Sha256</span></span>|<span data-ttu-id="5372c-158">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5372c-159">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="5372c-159">TripleDesSha256</span></span>|<span data-ttu-id="5372c-160">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5372c-161">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5372c-161">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="5372c-162">メッセージの暗号化には Aes128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-162">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5372c-163">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5372c-163">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="5372c-164">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-164">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5372c-165">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5372c-165">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="5372c-166">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-166">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5372c-167">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5372c-167">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="5372c-168">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5372c-168">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5372c-169">子要素</span><span class="sxs-lookup"><span data-stu-id="5372c-169">Child Elements</span></span>  
  
|<span data-ttu-id="5372c-170">要素</span><span class="sxs-lookup"><span data-stu-id="5372c-170">Element</span></span>|<span data-ttu-id="5372c-171">説明</span><span class="sxs-lookup"><span data-stu-id="5372c-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5372c-172">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="5372c-172">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="5372c-173">このバインディングのクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="5372c-173">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="5372c-174">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="5372c-174">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="5372c-175">\<issuer></span><span class="sxs-lookup"><span data-stu-id="5372c-175">\<issuer></span></span>](issuer.md)|<span data-ttu-id="5372c-176">セキュリティ トークンを発行するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="5372c-176">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="5372c-177">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="5372c-177">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="5372c-178">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="5372c-178">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="5372c-179">発行者のエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="5372c-179">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="5372c-180">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="5372c-180">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="5372c-181">トークン要求パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="5372c-181">A collection of token request parameters.</span></span> <span data-ttu-id="5372c-182">各パラメーターは、XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="5372c-182">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5372c-183">親要素</span><span class="sxs-lookup"><span data-stu-id="5372c-183">Parent Elements</span></span>  
  
|<span data-ttu-id="5372c-184">要素</span><span class="sxs-lookup"><span data-stu-id="5372c-184">Element</span></span>|<span data-ttu-id="5372c-185">説明</span><span class="sxs-lookup"><span data-stu-id="5372c-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5372c-186">\<security></span><span class="sxs-lookup"><span data-stu-id="5372c-186">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="5372c-187">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="5372c-187">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5372c-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="5372c-188">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="5372c-189">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="5372c-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5372c-190">バインディング</span><span class="sxs-lookup"><span data-stu-id="5372c-190">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5372c-191">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="5372c-191">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5372c-192">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="5372c-192">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5372c-193">\<binding></span><span class="sxs-lookup"><span data-stu-id="5372c-193">\<binding></span></span>](../../../misc/binding.md)
