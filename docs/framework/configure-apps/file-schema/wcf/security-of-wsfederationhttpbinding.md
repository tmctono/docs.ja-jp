---
title: <security> の <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 875ce7d548d59f32465da817e9e956217f346f60
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936532"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="21b47-102">\<wsFederationHttpBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="21b47-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="21b47-103">[ \<WsFederationHttpBinding >](wsfederationhttpbinding.md)のセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="21b47-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="21b47-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="21b47-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="21b47-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="21b47-105">\<bindings></span></span>  
<span data-ttu-id="21b47-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="21b47-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="21b47-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="21b47-107">\<binding></span></span>  
<span data-ttu-id="21b47-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="21b47-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21b47-109">構文</span><span class="sxs-lookup"><span data-stu-id="21b47-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21b47-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="21b47-110">Attributes and Elements</span></span>  
 <span data-ttu-id="21b47-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="21b47-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21b47-112">属性</span><span class="sxs-lookup"><span data-stu-id="21b47-112">Attributes</span></span>  
  
|<span data-ttu-id="21b47-113">属性</span><span class="sxs-lookup"><span data-stu-id="21b47-113">Attribute</span></span>|<span data-ttu-id="21b47-114">説明</span><span class="sxs-lookup"><span data-stu-id="21b47-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21b47-115">モード</span><span class="sxs-lookup"><span data-stu-id="21b47-115">Mode</span></span>|<span data-ttu-id="21b47-116">任意。</span><span class="sxs-lookup"><span data-stu-id="21b47-116">Optional.</span></span> <span data-ttu-id="21b47-117">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="21b47-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="21b47-118">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="21b47-118">The default value is `Message`.</span></span> <span data-ttu-id="21b47-119">この属性は <xref:System.ServiceModel.WSFederationHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="21b47-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="21b47-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="21b47-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="21b47-121">値</span><span class="sxs-lookup"><span data-stu-id="21b47-121">Value</span></span>|<span data-ttu-id="21b47-122">説明</span><span class="sxs-lookup"><span data-stu-id="21b47-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="21b47-123">なし</span><span class="sxs-lookup"><span data-stu-id="21b47-123">None</span></span>|<span data-ttu-id="21b47-124">SOAP メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="21b47-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="21b47-125">Message</span><span class="sxs-lookup"><span data-stu-id="21b47-125">Message</span></span>|<span data-ttu-id="21b47-126">SOAP メッセージ セキュリティを使用して、整合性、機密性、サーバー認証、およびクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="21b47-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="21b47-127">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="21b47-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="21b47-128">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21b47-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="21b47-129">クライアント認証は、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="21b47-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="21b47-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="21b47-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="21b47-131">整合性、機密性、およびサーバー認証は、HTTPS によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="21b47-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="21b47-132">このサービスは、証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21b47-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="21b47-133">クライアント認証は、SOAP メッセージ セキュリティによって提供され、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="21b47-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21b47-134">子要素</span><span class="sxs-lookup"><span data-stu-id="21b47-134">Child Elements</span></span>  
  
|<span data-ttu-id="21b47-135">要素</span><span class="sxs-lookup"><span data-stu-id="21b47-135">Element</span></span>|<span data-ttu-id="21b47-136">説明</span><span class="sxs-lookup"><span data-stu-id="21b47-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21b47-137">\<message></span><span class="sxs-lookup"><span data-stu-id="21b47-137">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="21b47-138">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="21b47-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="21b47-139">この要素は <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="21b47-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21b47-140">親要素</span><span class="sxs-lookup"><span data-stu-id="21b47-140">Parent Elements</span></span>  
  
|<span data-ttu-id="21b47-141">要素</span><span class="sxs-lookup"><span data-stu-id="21b47-141">Element</span></span>|<span data-ttu-id="21b47-142">説明</span><span class="sxs-lookup"><span data-stu-id="21b47-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21b47-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="21b47-143">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="21b47-144">WsDualHttpBinding > のすべてのバインド機能を[ \<](wsdualhttpbinding.md)定義します。</span><span class="sxs-lookup"><span data-stu-id="21b47-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21b47-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="21b47-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="21b47-146">方法: WSFederationHttpBinding を作成する</span><span class="sxs-lookup"><span data-stu-id="21b47-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="21b47-147">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="21b47-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="21b47-148">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="21b47-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="21b47-149">バインディング</span><span class="sxs-lookup"><span data-stu-id="21b47-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="21b47-150">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="21b47-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="21b47-151">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="21b47-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="21b47-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="21b47-152">\<binding></span></span>](../../../misc/binding.md)
