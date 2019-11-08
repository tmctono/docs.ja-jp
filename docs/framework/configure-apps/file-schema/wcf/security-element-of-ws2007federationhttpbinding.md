---
title: <ws2007FederationHttpBinding> の <security> 要素
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738725"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="fa817-102">\<ws2007FederationHttpBinding > のセキュリティ > 要素 \<</span><span class="sxs-lookup"><span data-stu-id="fa817-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="fa817-103">[\<ws2007FederationHttpBinding >](ws2007federationhttpbinding.md)要素のセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="fa817-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="fa817-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa817-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa817-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="fa817-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fa817-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="fa817-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="fa817-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fa817-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="fa817-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="fa817-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="fa817-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="fa817-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa817-110">構文</span><span class="sxs-lookup"><span data-stu-id="fa817-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa817-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fa817-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fa817-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa817-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa817-113">属性</span><span class="sxs-lookup"><span data-stu-id="fa817-113">Attributes</span></span>  
  
|<span data-ttu-id="fa817-114">属性</span><span class="sxs-lookup"><span data-stu-id="fa817-114">Attribute</span></span>|<span data-ttu-id="fa817-115">説明</span><span class="sxs-lookup"><span data-stu-id="fa817-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="fa817-116">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fa817-116">Optional.</span></span> <span data-ttu-id="fa817-117">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa817-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="fa817-118">既定値は `Message`です。</span><span class="sxs-lookup"><span data-stu-id="fa817-118">The default value is `Message`.</span></span> <span data-ttu-id="fa817-119">この属性は <xref:System.ServiceModel.WSFederationHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="fa817-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="fa817-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="fa817-120">mode Attribute</span></span>  
  
|<span data-ttu-id="fa817-121">[値]</span><span class="sxs-lookup"><span data-stu-id="fa817-121">Value</span></span>|<span data-ttu-id="fa817-122">説明</span><span class="sxs-lookup"><span data-stu-id="fa817-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa817-123">None</span><span class="sxs-lookup"><span data-stu-id="fa817-123">None</span></span>|<span data-ttu-id="fa817-124">SOAP メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="fa817-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="fa817-125">[メッセージ]</span><span class="sxs-lookup"><span data-stu-id="fa817-125">Message</span></span>|<span data-ttu-id="fa817-126">SOAP メッセージ セキュリティを使用して、整合性、機密性、サーバー認証、およびクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="fa817-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="fa817-127">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="fa817-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="fa817-128">サービスは、証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa817-128">The service must be configured with a certificate.</span></span> <span data-ttu-id="fa817-129">クライアント認証は、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="fa817-129">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="fa817-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="fa817-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="fa817-131">整合性、機密性、およびサーバー認証は、HTTPS によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="fa817-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="fa817-132">サービスは、証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa817-132">The service must be configured with a certificate.</span></span> <span data-ttu-id="fa817-133">クライアント認証は、SOAP メッセージ セキュリティによって提供され、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="fa817-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa817-134">子要素</span><span class="sxs-lookup"><span data-stu-id="fa817-134">Child Elements</span></span>  
  
|<span data-ttu-id="fa817-135">要素</span><span class="sxs-lookup"><span data-stu-id="fa817-135">Element</span></span>|<span data-ttu-id="fa817-136">説明</span><span class="sxs-lookup"><span data-stu-id="fa817-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa817-137">\< メッセージ ></span><span class="sxs-lookup"><span data-stu-id="fa817-137">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="fa817-138">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="fa817-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="fa817-139">この要素は <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="fa817-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa817-140">親要素</span><span class="sxs-lookup"><span data-stu-id="fa817-140">Parent Elements</span></span>  
  
|<span data-ttu-id="fa817-141">要素</span><span class="sxs-lookup"><span data-stu-id="fa817-141">Element</span></span>|<span data-ttu-id="fa817-142">説明</span><span class="sxs-lookup"><span data-stu-id="fa817-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa817-143">\<binding ></span><span class="sxs-lookup"><span data-stu-id="fa817-143">\<binding></span></span>](bindings.md)|<span data-ttu-id="fa817-144">[\<wsDualHttpBinding >](wsdualhttpbinding.md)のすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="fa817-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa817-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa817-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="fa817-146">方法 : WSFederationHttpBinding を作成する</span><span class="sxs-lookup"><span data-stu-id="fa817-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="fa817-147">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="fa817-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fa817-148">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="fa817-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="fa817-149">バインディング</span><span class="sxs-lookup"><span data-stu-id="fa817-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fa817-150">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="fa817-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fa817-151">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="fa817-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="fa817-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="fa817-152">\<binding></span></span>](bindings.md)
