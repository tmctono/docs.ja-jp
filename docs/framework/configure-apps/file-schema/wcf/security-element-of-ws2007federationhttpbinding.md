---
title: <security> の要素 <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 943ccc241aef15b58661699408b085d98cf86c3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183703"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="155cd-102">\<security> の要素 \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="155cd-102">\<security> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="155cd-103">要素のセキュリティ設定を定義し [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="155cd-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="155cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="155cd-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="155cd-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="155cd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="155cd-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="155cd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="155cd-107">属性</span><span class="sxs-lookup"><span data-stu-id="155cd-107">Attributes</span></span>  
  
|<span data-ttu-id="155cd-108">属性</span><span class="sxs-lookup"><span data-stu-id="155cd-108">Attribute</span></span>|<span data-ttu-id="155cd-109">説明</span><span class="sxs-lookup"><span data-stu-id="155cd-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="155cd-110">省略可能。</span><span class="sxs-lookup"><span data-stu-id="155cd-110">Optional.</span></span> <span data-ttu-id="155cd-111">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="155cd-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="155cd-112">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="155cd-112">The default value is `Message`.</span></span> <span data-ttu-id="155cd-113">この属性は <xref:System.ServiceModel.WSFederationHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="155cd-113">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="155cd-114">mode 属性</span><span class="sxs-lookup"><span data-stu-id="155cd-114">mode Attribute</span></span>  
  
|<span data-ttu-id="155cd-115">値</span><span class="sxs-lookup"><span data-stu-id="155cd-115">Value</span></span>|<span data-ttu-id="155cd-116">説明</span><span class="sxs-lookup"><span data-stu-id="155cd-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="155cd-117">None</span><span class="sxs-lookup"><span data-stu-id="155cd-117">None</span></span>|<span data-ttu-id="155cd-118">SOAP メッセージは、転送中はセキュリティで保護されません。</span><span class="sxs-lookup"><span data-stu-id="155cd-118">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="155cd-119">Message</span><span class="sxs-lookup"><span data-stu-id="155cd-119">Message</span></span>|<span data-ttu-id="155cd-120">SOAP メッセージ セキュリティを使用して、整合性、機密性、サーバー認証、およびクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="155cd-120">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="155cd-121">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="155cd-121">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="155cd-122">サービスは、証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="155cd-122">The service must be configured with a certificate.</span></span> <span data-ttu-id="155cd-123">クライアント認証は、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="155cd-123">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="155cd-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="155cd-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="155cd-125">整合性、機密性、およびサーバー認証は、HTTPS によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="155cd-125">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="155cd-126">サービスは、証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="155cd-126">The service must be configured with a certificate.</span></span> <span data-ttu-id="155cd-127">クライアント認証は、SOAP メッセージ セキュリティによって提供され、セキュリティ トークン サービスによってクライアントに発行されるトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="155cd-127">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="155cd-128">子要素</span><span class="sxs-lookup"><span data-stu-id="155cd-128">Child Elements</span></span>  
  
|<span data-ttu-id="155cd-129">要素</span><span class="sxs-lookup"><span data-stu-id="155cd-129">Element</span></span>|<span data-ttu-id="155cd-130">説明</span><span class="sxs-lookup"><span data-stu-id="155cd-130">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="155cd-131">メッセージ レベル セキュリティの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="155cd-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="155cd-132">この要素は <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="155cd-132">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="155cd-133">親要素</span><span class="sxs-lookup"><span data-stu-id="155cd-133">Parent Elements</span></span>  
  
|<span data-ttu-id="155cd-134">要素</span><span class="sxs-lookup"><span data-stu-id="155cd-134">Element</span></span>|<span data-ttu-id="155cd-135">説明</span><span class="sxs-lookup"><span data-stu-id="155cd-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="155cd-136">のすべてのバインディング機能を定義 [\<wsDualHttpBinding>](wsdualhttpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="155cd-136">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="155cd-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="155cd-137">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="155cd-138">方法: WSFederationHttpBinding を作成する</span><span class="sxs-lookup"><span data-stu-id="155cd-138">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="155cd-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="155cd-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="155cd-140">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="155cd-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="155cd-141">バインド</span><span class="sxs-lookup"><span data-stu-id="155cd-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="155cd-142">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="155cd-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="155cd-143">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="155cd-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
