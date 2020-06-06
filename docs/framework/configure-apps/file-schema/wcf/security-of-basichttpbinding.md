---
title: <security> の <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: c8e4f2d000a155eecd2a6c7faaaf4af525b24ca3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738709"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="1fbec-102">\<security> の \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1fbec-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="1fbec-103">のセキュリティ機能を定義 [\<basicHttpBinding>](basichttpbinding.md) します。</span><span class="sxs-lookup"><span data-stu-id="1fbec-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="1fbec-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fbec-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fbec-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1fbec-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1fbec-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1fbec-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fbec-107">属性</span><span class="sxs-lookup"><span data-stu-id="1fbec-107">Attributes</span></span>  
  
|<span data-ttu-id="1fbec-108">属性</span><span class="sxs-lookup"><span data-stu-id="1fbec-108">Attribute</span></span>|<span data-ttu-id="1fbec-109">説明</span><span class="sxs-lookup"><span data-stu-id="1fbec-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1fbec-110">mode</span><span class="sxs-lookup"><span data-stu-id="1fbec-110">mode</span></span>|<span data-ttu-id="1fbec-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="1fbec-111">Optional.</span></span> <span data-ttu-id="1fbec-112">使用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fbec-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="1fbec-113">既定値は、`None` です。</span><span class="sxs-lookup"><span data-stu-id="1fbec-113">The default is `None`.</span></span> <span data-ttu-id="1fbec-114">この属性は <xref:System.ServiceModel.BasicHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="1fbec-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="1fbec-115">mode 属性</span><span class="sxs-lookup"><span data-stu-id="1fbec-115">mode Attribute</span></span>  
  
|<span data-ttu-id="1fbec-116">値</span><span class="sxs-lookup"><span data-stu-id="1fbec-116">Value</span></span>|<span data-ttu-id="1fbec-117">説明</span><span class="sxs-lookup"><span data-stu-id="1fbec-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1fbec-118">なし</span><span class="sxs-lookup"><span data-stu-id="1fbec-118">None</span></span>|<span data-ttu-id="1fbec-119">-メッセージは、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="1fbec-119">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="1fbec-120">トランスポート</span><span class="sxs-lookup"><span data-stu-id="1fbec-120">Transport</span></span>|<span data-ttu-id="1fbec-121">セキュリティは、HTTPS トランスポートを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="1fbec-122">SOAP メッセージは、HTTPS を使用してセキュリティ保護されます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="1fbec-123">サービスは、サービスの X.509 証明書を使用してクライアントに認証されます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="1fbec-124">クライアントは、提供される ClientCredentialType を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-124">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="1fbec-125">「」を参照してください [\<transport>](transport-of-basichttpbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="1fbec-125">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="1fbec-126">Message</span><span class="sxs-lookup"><span data-stu-id="1fbec-126">Message</span></span>|<span data-ttu-id="1fbec-127">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="1fbec-128">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="1fbec-129">このバインディングの場合、サーバー証明書をクライアントの帯域外で提供するように要求されます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-129">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="1fbec-130">このバインディングの唯一の有効な `ClientCredentialType` は、`Certificate` です。</span><span class="sxs-lookup"><span data-stu-id="1fbec-130">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="1fbec-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="1fbec-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="1fbec-132">整合性、機密性、およびサーバー認証は、トランスポート セキュリティによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-132">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="1fbec-133">クライアント認証は、SOAP メッセージ セキュリティで提供されます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-133">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="1fbec-134">このモードは、ユーザーがユーザー名およびパスワードを使用して認証し、メッセージ転送をセキュリティで保護するために既存の HTTP が配置されている場合に関連します。</span><span class="sxs-lookup"><span data-stu-id="1fbec-134">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="1fbec-135">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="1fbec-135">TransportCredentialOnly</span></span>|<span data-ttu-id="1fbec-136">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="1fbec-136">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="1fbec-137">http ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="1fbec-137">It provides http-based client authentication.</span></span> <span data-ttu-id="1fbec-138">このモードを使用するときは、十分に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fbec-138">This mode should be used with caution.</span></span> <span data-ttu-id="1fbec-139">トランスポートセキュリティが他の方法 (IPSec など) によって提供され、WCF インフラストラクチャによってクライアント認証のみが提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fbec-139">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fbec-140">子要素</span><span class="sxs-lookup"><span data-stu-id="1fbec-140">Child Elements</span></span>  
  
|<span data-ttu-id="1fbec-141">要素</span><span class="sxs-lookup"><span data-stu-id="1fbec-141">Element</span></span>|<span data-ttu-id="1fbec-142">Description</span><span class="sxs-lookup"><span data-stu-id="1fbec-142">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|<span data-ttu-id="1fbec-143">基本 HTTP サービスのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1fbec-143">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="1fbec-144">この要素は、<xref:System.ServiceModel.HttpTransportSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="1fbec-144">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[\<message>](message-of-basichttpbinding.md)|<span data-ttu-id="1fbec-145">基本 HTTP サービスのメッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1fbec-145">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="1fbec-146">この要素は、<xref:System.ServiceModel.BasicHttpMessageSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="1fbec-146">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1fbec-147">親要素</span><span class="sxs-lookup"><span data-stu-id="1fbec-147">Parent Elements</span></span>  
  
|<span data-ttu-id="1fbec-148">要素</span><span class="sxs-lookup"><span data-stu-id="1fbec-148">Element</span></span>|<span data-ttu-id="1fbec-149">Description</span><span class="sxs-lookup"><span data-stu-id="1fbec-149">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1fbec-150">binding</span><span class="sxs-lookup"><span data-stu-id="1fbec-150">binding</span></span>|<span data-ttu-id="1fbec-151">のバインディング要素 [\<basicHttpBinding>](basichttpbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="1fbec-151">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fbec-152">解説</span><span class="sxs-lookup"><span data-stu-id="1fbec-152">Remarks</span></span>  
 <span data-ttu-id="1fbec-153">既定では、SOAP メッセージはセキュリティで保護されず、クライアントは認証されません。</span><span class="sxs-lookup"><span data-stu-id="1fbec-153">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="1fbec-154">この要素を使用すると、`basicHttpBinding` 要素に追加のセキュリティ設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1fbec-154">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbec-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fbec-155">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="1fbec-156">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1fbec-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1fbec-157">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="1fbec-157">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="1fbec-158">バインド</span><span class="sxs-lookup"><span data-stu-id="1fbec-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1fbec-159">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="1fbec-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1fbec-160">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="1fbec-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
