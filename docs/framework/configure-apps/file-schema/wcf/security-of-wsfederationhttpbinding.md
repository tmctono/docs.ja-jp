---
title: <security> の <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 6c07d1ca18837f66548411262b84b9a326f5ec4a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399732"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="c67a6-102">\<wsFederationHttpBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="c67a6-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="c67a6-103">[ \<WsFederationHttpBinding >](wsfederationhttpbinding.md)のセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="c67a6-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="c67a6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c67a6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c67a6-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c67a6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c67a6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c67a6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c67a6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="c67a6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="c67a6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="c67a6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c67a6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="c67a6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67a6-110">構文</span><span class="sxs-lookup"><span data-stu-id="c67a6-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c67a6-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c67a6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c67a6-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c67a6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c67a6-113">属性</span><span class="sxs-lookup"><span data-stu-id="c67a6-113">Attributes</span></span>  
  
|<span data-ttu-id="c67a6-114">属性</span><span class="sxs-lookup"><span data-stu-id="c67a6-114">Attribute</span></span>|<span data-ttu-id="c67a6-115">説明</span><span class="sxs-lookup"><span data-stu-id="c67a6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c67a6-116">モード</span><span class="sxs-lookup"><span data-stu-id="c67a6-116">Mode</span></span>|<span data-ttu-id="c67a6-117">任意。</span><span class="sxs-lookup"><span data-stu-id="c67a6-117">Optional.</span></span> <span data-ttu-id="c67a6-118">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="c67a6-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="c67a6-119">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="c67a6-119">The default value is `Message`.</span></span> <span data-ttu-id="c67a6-120">この属性は <xref:System.ServiceModel.WSFederationHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="c67a6-120">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="c67a6-121">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="c67a6-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="c67a6-122">値</span><span class="sxs-lookup"><span data-stu-id="c67a6-122">Value</span></span>|<span data-ttu-id="c67a6-123">説明</span><span class="sxs-lookup"><span data-stu-id="c67a6-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c67a6-124">なし</span><span class="sxs-lookup"><span data-stu-id="c67a6-124">None</span></span>|<span data-ttu-id="c67a6-125">SOAP メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="c67a6-125">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="c67a6-126">Message</span><span class="sxs-lookup"><span data-stu-id="c67a6-126">Message</span></span>|<span data-ttu-id="c67a6-127">SOAP メッセージ セキュリティを使用して、整合性、機密性、サーバー認証、およびクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="c67a6-127">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="c67a6-128">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="c67a6-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="c67a6-129">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c67a6-129">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="c67a6-130">クライアント認証は、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c67a6-130">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="c67a6-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="c67a6-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="c67a6-132">整合性、機密性、およびサーバー認証は、HTTPS によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="c67a6-132">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="c67a6-133">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c67a6-133">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="c67a6-134">クライアント認証は、SOAP メッセージ セキュリティによって提供され、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c67a6-134">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c67a6-135">子要素</span><span class="sxs-lookup"><span data-stu-id="c67a6-135">Child Elements</span></span>  
  
|<span data-ttu-id="c67a6-136">要素</span><span class="sxs-lookup"><span data-stu-id="c67a6-136">Element</span></span>|<span data-ttu-id="c67a6-137">説明</span><span class="sxs-lookup"><span data-stu-id="c67a6-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c67a6-138">\<message></span><span class="sxs-lookup"><span data-stu-id="c67a6-138">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="c67a6-139">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="c67a6-139">Defines the settings for the message-level security.</span></span> <span data-ttu-id="c67a6-140">この要素は <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="c67a6-140">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c67a6-141">親要素</span><span class="sxs-lookup"><span data-stu-id="c67a6-141">Parent Elements</span></span>  
  
|<span data-ttu-id="c67a6-142">要素</span><span class="sxs-lookup"><span data-stu-id="c67a6-142">Element</span></span>|<span data-ttu-id="c67a6-143">説明</span><span class="sxs-lookup"><span data-stu-id="c67a6-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c67a6-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="c67a6-144">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c67a6-145">WsDualHttpBinding > のすべてのバインド機能を[ \<](wsdualhttpbinding.md)定義します。</span><span class="sxs-lookup"><span data-stu-id="c67a6-145">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c67a6-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="c67a6-146">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="c67a6-147">方法: WSFederationHttpBinding を作成する</span><span class="sxs-lookup"><span data-stu-id="c67a6-147">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="c67a6-148">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="c67a6-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c67a6-149">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="c67a6-149">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="c67a6-150">バインディング</span><span class="sxs-lookup"><span data-stu-id="c67a6-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c67a6-151">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="c67a6-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c67a6-152">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="c67a6-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c67a6-153">\<binding></span><span class="sxs-lookup"><span data-stu-id="c67a6-153">\<binding></span></span>](../../../misc/binding.md)
