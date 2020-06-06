---
title: <security> の <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: ea029444cee331a235c7a2fc140b4321d7530063
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736328"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="eadca-102">\<security> の \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="eadca-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="eadca-103">のセキュリティ設定を定義し [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="eadca-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="eadca-104">構文</span><span class="sxs-lookup"><span data-stu-id="eadca-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eadca-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eadca-105">Attributes and Elements</span></span>  
 <span data-ttu-id="eadca-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="eadca-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eadca-107">属性</span><span class="sxs-lookup"><span data-stu-id="eadca-107">Attributes</span></span>  
  
|<span data-ttu-id="eadca-108">属性</span><span class="sxs-lookup"><span data-stu-id="eadca-108">Attribute</span></span>|<span data-ttu-id="eadca-109">説明</span><span class="sxs-lookup"><span data-stu-id="eadca-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eadca-110">モード</span><span class="sxs-lookup"><span data-stu-id="eadca-110">Mode</span></span>|<span data-ttu-id="eadca-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="eadca-111">Optional.</span></span> <span data-ttu-id="eadca-112">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="eadca-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="eadca-113">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="eadca-113">The default value is `Message`.</span></span> <span data-ttu-id="eadca-114">この属性は <xref:System.ServiceModel.WSFederationHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="eadca-114">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="eadca-115">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="eadca-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="eadca-116">値</span><span class="sxs-lookup"><span data-stu-id="eadca-116">Value</span></span>|<span data-ttu-id="eadca-117">説明</span><span class="sxs-lookup"><span data-stu-id="eadca-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eadca-118">なし</span><span class="sxs-lookup"><span data-stu-id="eadca-118">None</span></span>|<span data-ttu-id="eadca-119">SOAP メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="eadca-119">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="eadca-120">Message</span><span class="sxs-lookup"><span data-stu-id="eadca-120">Message</span></span>|<span data-ttu-id="eadca-121">SOAP メッセージ セキュリティを使用して、整合性、機密性、サーバー認証、およびクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="eadca-121">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="eadca-122">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="eadca-122">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="eadca-123">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eadca-123">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="eadca-124">クライアント認証は、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="eadca-124">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="eadca-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="eadca-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="eadca-126">整合性、機密性、およびサーバー認証は、HTTPS によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="eadca-126">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="eadca-127">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eadca-127">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="eadca-128">クライアント認証は、SOAP メッセージ セキュリティによって提供され、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="eadca-128">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eadca-129">子要素</span><span class="sxs-lookup"><span data-stu-id="eadca-129">Child Elements</span></span>  
  
|<span data-ttu-id="eadca-130">要素</span><span class="sxs-lookup"><span data-stu-id="eadca-130">Element</span></span>|<span data-ttu-id="eadca-131">Description</span><span class="sxs-lookup"><span data-stu-id="eadca-131">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="eadca-132">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="eadca-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="eadca-133">この要素は <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="eadca-133">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eadca-134">親要素</span><span class="sxs-lookup"><span data-stu-id="eadca-134">Parent Elements</span></span>  
  
|<span data-ttu-id="eadca-135">要素</span><span class="sxs-lookup"><span data-stu-id="eadca-135">Element</span></span>|<span data-ttu-id="eadca-136">Description</span><span class="sxs-lookup"><span data-stu-id="eadca-136">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="eadca-137">のすべてのバインディング機能を定義 [\<wsDualHttpBinding>](wsdualhttpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="eadca-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eadca-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="eadca-138">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="eadca-139">方法: WSFederationHttpBinding を作成する</span><span class="sxs-lookup"><span data-stu-id="eadca-139">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="eadca-140">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="eadca-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="eadca-141">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="eadca-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="eadca-142">バインド</span><span class="sxs-lookup"><span data-stu-id="eadca-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eadca-143">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="eadca-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="eadca-144">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="eadca-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
