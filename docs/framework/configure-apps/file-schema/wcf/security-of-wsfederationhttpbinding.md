---
title: <security> の <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: ea029444cee331a235c7a2fc140b4321d7530063
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736328"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="495af-102">\<wsFederationHttpBinding > のセキュリティ > の \<</span><span class="sxs-lookup"><span data-stu-id="495af-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="495af-103">[\<wsFederationHttpBinding >](wsfederationhttpbinding.md)のセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="495af-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="495af-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="495af-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="495af-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="495af-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="495af-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="495af-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="495af-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="495af-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="495af-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="495af-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="495af-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="495af-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="495af-110">構文</span><span class="sxs-lookup"><span data-stu-id="495af-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="495af-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="495af-111">Attributes and Elements</span></span>  
 <span data-ttu-id="495af-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="495af-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="495af-113">属性</span><span class="sxs-lookup"><span data-stu-id="495af-113">Attributes</span></span>  
  
|<span data-ttu-id="495af-114">属性</span><span class="sxs-lookup"><span data-stu-id="495af-114">Attribute</span></span>|<span data-ttu-id="495af-115">説明</span><span class="sxs-lookup"><span data-stu-id="495af-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="495af-116">モード</span><span class="sxs-lookup"><span data-stu-id="495af-116">Mode</span></span>|<span data-ttu-id="495af-117">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="495af-117">Optional.</span></span> <span data-ttu-id="495af-118">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="495af-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="495af-119">既定値は `Message`です。</span><span class="sxs-lookup"><span data-stu-id="495af-119">The default value is `Message`.</span></span> <span data-ttu-id="495af-120">この属性は <xref:System.ServiceModel.WSFederationHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="495af-120">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="495af-121">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="495af-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="495af-122">[値]</span><span class="sxs-lookup"><span data-stu-id="495af-122">Value</span></span>|<span data-ttu-id="495af-123">説明</span><span class="sxs-lookup"><span data-stu-id="495af-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="495af-124">None</span><span class="sxs-lookup"><span data-stu-id="495af-124">None</span></span>|<span data-ttu-id="495af-125">SOAP メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="495af-125">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="495af-126">[メッセージ]</span><span class="sxs-lookup"><span data-stu-id="495af-126">Message</span></span>|<span data-ttu-id="495af-127">SOAP メッセージ セキュリティを使用して、整合性、機密性、サーバー認証、およびクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="495af-127">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="495af-128">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="495af-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="495af-129">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="495af-129">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="495af-130">クライアント認証は、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="495af-130">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="495af-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="495af-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="495af-132">整合性、機密性、およびサーバー認証は、HTTPS によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="495af-132">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="495af-133">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="495af-133">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="495af-134">クライアント認証は、SOAP メッセージ セキュリティによって提供され、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="495af-134">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="495af-135">子要素</span><span class="sxs-lookup"><span data-stu-id="495af-135">Child Elements</span></span>  
  
|<span data-ttu-id="495af-136">要素</span><span class="sxs-lookup"><span data-stu-id="495af-136">Element</span></span>|<span data-ttu-id="495af-137">説明</span><span class="sxs-lookup"><span data-stu-id="495af-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="495af-138">\< メッセージ ></span><span class="sxs-lookup"><span data-stu-id="495af-138">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="495af-139">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="495af-139">Defines the settings for the message-level security.</span></span> <span data-ttu-id="495af-140">この要素は <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="495af-140">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="495af-141">親要素</span><span class="sxs-lookup"><span data-stu-id="495af-141">Parent Elements</span></span>  
  
|<span data-ttu-id="495af-142">要素</span><span class="sxs-lookup"><span data-stu-id="495af-142">Element</span></span>|<span data-ttu-id="495af-143">説明</span><span class="sxs-lookup"><span data-stu-id="495af-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="495af-144">\<binding ></span><span class="sxs-lookup"><span data-stu-id="495af-144">\<binding></span></span>](bindings.md)|<span data-ttu-id="495af-145">[\<wsDualHttpBinding >](wsdualhttpbinding.md)のすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="495af-145">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="495af-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="495af-146">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="495af-147">方法 : WSFederationHttpBinding を作成する</span><span class="sxs-lookup"><span data-stu-id="495af-147">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="495af-148">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="495af-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="495af-149">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="495af-149">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="495af-150">バインディング</span><span class="sxs-lookup"><span data-stu-id="495af-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="495af-151">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="495af-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="495af-152">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="495af-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="495af-153">\<binding ></span><span class="sxs-lookup"><span data-stu-id="495af-153">\<binding></span></span>](bindings.md)
