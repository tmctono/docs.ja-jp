---
title: <security> の <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 650483099c7d70450cfc56a9a28efac076d64675
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162238"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="0dcba-102">\<security> の \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="0dcba-102">\<security> of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="0dcba-103">のセキュリティ設定を定義し [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="0dcba-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="0dcba-104">構文</span><span class="sxs-lookup"><span data-stu-id="0dcba-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0dcba-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0dcba-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0dcba-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0dcba-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0dcba-107">属性</span><span class="sxs-lookup"><span data-stu-id="0dcba-107">Attributes</span></span>  
  
|<span data-ttu-id="0dcba-108">属性</span><span class="sxs-lookup"><span data-stu-id="0dcba-108">Attribute</span></span>|<span data-ttu-id="0dcba-109">説明</span><span class="sxs-lookup"><span data-stu-id="0dcba-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0dcba-110">モード</span><span class="sxs-lookup"><span data-stu-id="0dcba-110">Mode</span></span>|<span data-ttu-id="0dcba-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="0dcba-111">Optional.</span></span> <span data-ttu-id="0dcba-112">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="0dcba-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="0dcba-113">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="0dcba-113">The default value is `Message`.</span></span> <span data-ttu-id="0dcba-114">この属性は <xref:System.ServiceModel.WSFederationHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="0dcba-114">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="0dcba-115">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="0dcba-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="0dcba-116">値</span><span class="sxs-lookup"><span data-stu-id="0dcba-116">Value</span></span>|<span data-ttu-id="0dcba-117">説明</span><span class="sxs-lookup"><span data-stu-id="0dcba-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0dcba-118">None</span><span class="sxs-lookup"><span data-stu-id="0dcba-118">None</span></span>|<span data-ttu-id="0dcba-119">SOAP メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="0dcba-119">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="0dcba-120">Message</span><span class="sxs-lookup"><span data-stu-id="0dcba-120">Message</span></span>|<span data-ttu-id="0dcba-121">SOAP メッセージ セキュリティを使用して、整合性、機密性、サーバー認証、およびクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="0dcba-121">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="0dcba-122">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="0dcba-122">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="0dcba-123">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dcba-123">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="0dcba-124">クライアント認証は、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="0dcba-124">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="0dcba-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="0dcba-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="0dcba-126">整合性、機密性、およびサーバー認証は、HTTPS によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="0dcba-126">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="0dcba-127">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dcba-127">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="0dcba-128">クライアント認証は、SOAP メッセージ セキュリティによって提供され、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="0dcba-128">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0dcba-129">子要素</span><span class="sxs-lookup"><span data-stu-id="0dcba-129">Child Elements</span></span>  
  
|<span data-ttu-id="0dcba-130">要素</span><span class="sxs-lookup"><span data-stu-id="0dcba-130">Element</span></span>|<span data-ttu-id="0dcba-131">説明</span><span class="sxs-lookup"><span data-stu-id="0dcba-131">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="0dcba-132">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="0dcba-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="0dcba-133">この要素は <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="0dcba-133">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0dcba-134">親要素</span><span class="sxs-lookup"><span data-stu-id="0dcba-134">Parent Elements</span></span>  
  
|<span data-ttu-id="0dcba-135">要素</span><span class="sxs-lookup"><span data-stu-id="0dcba-135">Element</span></span>|<span data-ttu-id="0dcba-136">説明</span><span class="sxs-lookup"><span data-stu-id="0dcba-136">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0dcba-137">のすべてのバインディング機能を定義 [\<wsDualHttpBinding>](wsdualhttpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="0dcba-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0dcba-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dcba-138">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="0dcba-139">方法: WSFederationHttpBinding を作成する</span><span class="sxs-lookup"><span data-stu-id="0dcba-139">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="0dcba-140">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0dcba-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0dcba-141">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="0dcba-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="0dcba-142">バインド</span><span class="sxs-lookup"><span data-stu-id="0dcba-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0dcba-143">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="0dcba-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0dcba-144">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="0dcba-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
