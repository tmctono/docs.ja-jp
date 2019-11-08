---
title: <ws2007FederationHttpBinding> の <message> 要素
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: dde763687dbc62d6fb342a21a4c614208f28d7e8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738995"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="6ce52-102">\<message > 要素 \<ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="6ce52-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="6ce52-103">[\<ws2007FederationHttpBinding >](ws2007federationhttpbinding.md)要素のメッセージレベルセキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="6ce52-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6ce52-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6ce52-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="6ce52-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6ce52-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6ce52-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6ce52-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6ce52-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="6ce52-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="6ce52-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6ce52-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**セキュリティ >** ](security-element-of-ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6ce52-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="6ce52-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**メッセージ >**</span><span class="sxs-lookup"><span data-stu-id="6ce52-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ce52-111">構文</span><span class="sxs-lookup"><span data-stu-id="6ce52-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ce52-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6ce52-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6ce52-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ce52-114">属性</span><span class="sxs-lookup"><span data-stu-id="6ce52-114">Attributes</span></span>  
  
|<span data-ttu-id="6ce52-115">属性</span><span class="sxs-lookup"><span data-stu-id="6ce52-115">Attribute</span></span>|<span data-ttu-id="6ce52-116">説明</span><span class="sxs-lookup"><span data-stu-id="6ce52-116">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="6ce52-117">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6ce52-117">Optional.</span></span> <span data-ttu-id="6ce52-118">メッセージの暗号化、署名、およびキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-118">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="6ce52-119">アルゴリズムとキー サイズは、<xref:System.ServiceModel.Security.SecurityAlgorithmSuite> クラスにより決まります。</span><span class="sxs-lookup"><span data-stu-id="6ce52-119">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="6ce52-120">これらのアルゴリズムは、Security Policy Language (WS-SecurityPolicy) の仕様で指定されているアルゴリズムに対応付けられています。</span><span class="sxs-lookup"><span data-stu-id="6ce52-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="6ce52-121">それぞれの値については次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ce52-121">See the following table for possible values.</span></span> <span data-ttu-id="6ce52-122">既定値は Basic256 です。</span><span class="sxs-lookup"><span data-stu-id="6ce52-122">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="6ce52-123">発行されるキーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="6ce52-124">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="6ce52-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6ce52-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="6ce52-125">-   SymmetricKey</span></span><br /><span data-ttu-id="6ce52-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="6ce52-126">-   PublicKey</span></span><br /><span data-ttu-id="6ce52-127">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="6ce52-127">-   BearerKey</span></span><br /><br /> <span data-ttu-id="6ce52-128">既定値は SymmetricKey です。</span><span class="sxs-lookup"><span data-stu-id="6ce52-128">The default is SymmetricKey.</span></span> <span data-ttu-id="6ce52-129">この属性は <xref:System.IdentityModel.Tokens.SecurityKeyType> 型です。</span><span class="sxs-lookup"><span data-stu-id="6ce52-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="6ce52-130">発行されるトークンの型を指定する URI。</span><span class="sxs-lookup"><span data-stu-id="6ce52-130">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="6ce52-131">既定値は、 `null`です。</span><span class="sxs-lookup"><span data-stu-id="6ce52-131">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="6ce52-132">サービス資格情報がネゴシエーションの一部として交換されるか、帯域外で使用できるかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="6ce52-132">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="6ce52-133">既定値は `true` で、サービス資格情報がネゴシエートされます。</span><span class="sxs-lookup"><span data-stu-id="6ce52-133">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="6ce52-134">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="6ce52-134">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="6ce52-135">[値]</span><span class="sxs-lookup"><span data-stu-id="6ce52-135">Value</span></span>|<span data-ttu-id="6ce52-136">説明</span><span class="sxs-lookup"><span data-stu-id="6ce52-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6ce52-137">Basic128</span><span class="sxs-lookup"><span data-stu-id="6ce52-137">Basic128</span></span>|<span data-ttu-id="6ce52-138">Aes128 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-138">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-139">Basic192</span><span class="sxs-lookup"><span data-stu-id="6ce52-139">Basic192</span></span>|<span data-ttu-id="6ce52-140">Aes192 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-140">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-141">Basic256</span><span class="sxs-lookup"><span data-stu-id="6ce52-141">Basic256</span></span>|<span data-ttu-id="6ce52-142">Aes256 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-142">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-143">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6ce52-143">Basic256Rsa15</span></span>|<span data-ttu-id="6ce52-144">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-144">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-145">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="6ce52-145">Basic192Rsa15</span></span>|<span data-ttu-id="6ce52-146">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-146">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-147">TripleDes</span><span class="sxs-lookup"><span data-stu-id="6ce52-147">TripleDes</span></span>|<span data-ttu-id="6ce52-148">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-148">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-149">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="6ce52-149">Basic128Rsa15</span></span>|<span data-ttu-id="6ce52-150">メッセージの暗号化には Aes128 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-150">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-151">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="6ce52-151">TripleDesRsa15</span></span>|<span data-ttu-id="6ce52-152">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-152">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-153">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="6ce52-153">Basic128Sha256</span></span>|<span data-ttu-id="6ce52-154">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-154">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-155">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="6ce52-155">Basic192Sha256</span></span>|<span data-ttu-id="6ce52-156">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-157">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="6ce52-157">Basic256Sha256</span></span>|<span data-ttu-id="6ce52-158">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-159">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="6ce52-159">TripleDesSha256</span></span>|<span data-ttu-id="6ce52-160">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-161">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6ce52-161">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="6ce52-162">メッセージの暗号化には Aes128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-162">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-163">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6ce52-163">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="6ce52-164">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-164">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-165">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6ce52-165">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="6ce52-166">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-166">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="6ce52-167">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="6ce52-167">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="6ce52-168">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-168">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ce52-169">子要素</span><span class="sxs-lookup"><span data-stu-id="6ce52-169">Child Elements</span></span>  
  
|<span data-ttu-id="6ce52-170">要素</span><span class="sxs-lookup"><span data-stu-id="6ce52-170">Element</span></span>|<span data-ttu-id="6ce52-171">説明</span><span class="sxs-lookup"><span data-stu-id="6ce52-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ce52-172">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="6ce52-172">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="6ce52-173">このバインディングのクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-173">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="6ce52-174">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="6ce52-174">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="6ce52-175">\<発行者 ></span><span class="sxs-lookup"><span data-stu-id="6ce52-175">\<issuer></span></span>](issuer.md)|<span data-ttu-id="6ce52-176">セキュリティ トークンを発行するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-176">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="6ce52-177">この要素は <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="6ce52-177">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="6ce52-178">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="6ce52-178">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="6ce52-179">発行者のエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-179">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="6ce52-180">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="6ce52-180">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="6ce52-181">トークン要求パラメーターのコレクション。</span><span class="sxs-lookup"><span data-stu-id="6ce52-181">A collection of token request parameters.</span></span> <span data-ttu-id="6ce52-182">各パラメーターは、XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="6ce52-182">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6ce52-183">親要素</span><span class="sxs-lookup"><span data-stu-id="6ce52-183">Parent Elements</span></span>  
  
|<span data-ttu-id="6ce52-184">要素</span><span class="sxs-lookup"><span data-stu-id="6ce52-184">Element</span></span>|<span data-ttu-id="6ce52-185">説明</span><span class="sxs-lookup"><span data-stu-id="6ce52-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ce52-186">\< セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="6ce52-186">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="6ce52-187">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6ce52-187">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ce52-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ce52-188">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="6ce52-189">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="6ce52-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6ce52-190">バインディング</span><span class="sxs-lookup"><span data-stu-id="6ce52-190">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6ce52-191">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="6ce52-191">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6ce52-192">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="6ce52-192">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6ce52-193">\<binding ></span><span class="sxs-lookup"><span data-stu-id="6ce52-193">\<binding></span></span>](bindings.md)
