---
title: <security> の <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: aa01e906ddd2f15007c72bfc2a45122cfb15ba2c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736370"
---
# <a name="security-of-nettcpbinding"></a><span data-ttu-id="03e7e-102">\<netTcpBinding > のセキュリティ > の \<</span><span class="sxs-lookup"><span data-stu-id="03e7e-102">\<security> of \<netTcpBinding></span></span>
<span data-ttu-id="03e7e-103">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="03e7e-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="03e7e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="03e7e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="03e7e-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="03e7e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="03e7e-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="03e7e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="03e7e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netTcpBinding >** ](nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="03e7e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="03e7e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="03e7e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="03e7e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="03e7e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03e7e-110">構文</span><span class="sxs-lookup"><span data-stu-id="03e7e-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03e7e-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="03e7e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="03e7e-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="03e7e-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03e7e-113">属性</span><span class="sxs-lookup"><span data-stu-id="03e7e-113">Attributes</span></span>  
  
|<span data-ttu-id="03e7e-114">属性</span><span class="sxs-lookup"><span data-stu-id="03e7e-114">Attribute</span></span>|<span data-ttu-id="03e7e-115">説明</span><span class="sxs-lookup"><span data-stu-id="03e7e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03e7e-116">モード</span><span class="sxs-lookup"><span data-stu-id="03e7e-116">mode</span></span>|<span data-ttu-id="03e7e-117">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="03e7e-117">Optional.</span></span> <span data-ttu-id="03e7e-118">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="03e7e-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="03e7e-119">有効な値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="03e7e-119">Valid values are shown below.</span></span> <span data-ttu-id="03e7e-120">既定値は `Transport`です。</span><span class="sxs-lookup"><span data-stu-id="03e7e-120">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="03e7e-121">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="03e7e-121">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="03e7e-122">mode 属性</span><span class="sxs-lookup"><span data-stu-id="03e7e-122">mode Attribute</span></span>  
  
|<span data-ttu-id="03e7e-123">[値]</span><span class="sxs-lookup"><span data-stu-id="03e7e-123">Value</span></span>|<span data-ttu-id="03e7e-124">説明</span><span class="sxs-lookup"><span data-stu-id="03e7e-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="03e7e-125">None</span><span class="sxs-lookup"><span data-stu-id="03e7e-125">None</span></span>|<span data-ttu-id="03e7e-126">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="03e7e-126">Security is disabled.</span></span>|  
|<span data-ttu-id="03e7e-127">Transport</span><span class="sxs-lookup"><span data-stu-id="03e7e-127">Transport</span></span>|<span data-ttu-id="03e7e-128">トランスポート セキュリティは、TCP 経由の TLS または SPNaego を使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-128">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="03e7e-129">サービスは、SSL 証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e7e-129">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="03e7e-130">このモードでの保護レベルを制御できます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-130">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="03e7e-131">[メッセージ]</span><span class="sxs-lookup"><span data-stu-id="03e7e-131">Message</span></span>|<span data-ttu-id="03e7e-132">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="03e7e-133">既定では、SOAP 本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-133">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="03e7e-134">このモードは、サービス資格情報をクライアントの帯域外で使用可能にするかどうか、使用するアルゴリズム スイート、メッセージ本文に適用する保護レベルなど、さまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="03e7e-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="03e7e-135">クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="03e7e-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="03e7e-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="03e7e-137">トランスポート セキュリティは、メッセージ セキュリティと組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-137">Transport security is coupled with message security.</span></span> <span data-ttu-id="03e7e-138">トランスポート セキュリティは、TCP 経由の TLS または SPNego によって提供され、整合性、機密性、およびサーバー認証が保証されます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-138">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="03e7e-139">SOAP メッセージ セキュリティは、クライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="03e7e-139">SOAP message security provides client authentication.</span></span> <span data-ttu-id="03e7e-140">既定では、クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-140">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03e7e-141">子要素</span><span class="sxs-lookup"><span data-stu-id="03e7e-141">Child Elements</span></span>  
  
|<span data-ttu-id="03e7e-142">要素</span><span class="sxs-lookup"><span data-stu-id="03e7e-142">Element</span></span>|<span data-ttu-id="03e7e-143">説明</span><span class="sxs-lookup"><span data-stu-id="03e7e-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03e7e-144">\<transport ></span><span class="sxs-lookup"><span data-stu-id="03e7e-144">\<transport></span></span>](transport-of-nettcpbinding.md)|<span data-ttu-id="03e7e-145">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="03e7e-145">Defines the security settings for the transport.</span></span> <span data-ttu-id="03e7e-146">この要素は <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="03e7e-146">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[<span data-ttu-id="03e7e-147">\< メッセージ ></span><span class="sxs-lookup"><span data-stu-id="03e7e-147">\<message></span></span>](message-element-of-nettcpbinding.md)|<span data-ttu-id="03e7e-148">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="03e7e-148">Defines the security settings for the message.</span></span> <span data-ttu-id="03e7e-149">この要素は <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="03e7e-149">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03e7e-150">親要素</span><span class="sxs-lookup"><span data-stu-id="03e7e-150">Parent Elements</span></span>  
  
|<span data-ttu-id="03e7e-151">要素</span><span class="sxs-lookup"><span data-stu-id="03e7e-151">Element</span></span>|<span data-ttu-id="03e7e-152">説明</span><span class="sxs-lookup"><span data-stu-id="03e7e-152">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03e7e-153">バインド</span><span class="sxs-lookup"><span data-stu-id="03e7e-153">binding</span></span>|<span data-ttu-id="03e7e-154">[\<netTcpBinding >](nettcpbinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="03e7e-154">The binding element of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03e7e-155">Remarks</span><span class="sxs-lookup"><span data-stu-id="03e7e-155">Remarks</span></span>  
 <span data-ttu-id="03e7e-156">標準バインディングにはそれぞれ、転送セキュリティ要件を制御するためのパラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="03e7e-156">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="03e7e-157">通常、これらのパラメーターには、使用されるセキュリティ レベル (メッセージ レベルまたはトランスポート レベル) を指定したセキュリティ モードと、クライアント資格情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="03e7e-157">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="03e7e-158">これらのパラメーターが提示するオプションの選択に基づいて、適切なセキュリティが設定されたチャネル スタックが構築されます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-158">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="03e7e-159">WCF (Windows Communication Foundation) に用意されているシステム標準のバインディグは、最も一般的なシナリオ要件の一部を満たすように設計されたセットです。</span><span class="sxs-lookup"><span data-stu-id="03e7e-159">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="03e7e-160">これらのバイディングでは、特定のシナリオを対象とするセキュリティ要件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-160">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="03e7e-161">この構成要素によって、`netTcpBinding` のセキュリティ仕様が提供されます。</span><span class="sxs-lookup"><span data-stu-id="03e7e-161">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="03e7e-162">これは、コンピューター間通信に適した、安全で信頼できる最適化されたバインディングです。</span><span class="sxs-lookup"><span data-stu-id="03e7e-162">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="03e7e-163">既定では、このバインディングは、メッセージを配信するための TCP、メッセージの保護と認証を行うための Windows セキュリティ、信頼性を高めるための WS-ReliableMessaging、およびバイナリ メッセージのエンコーディングをサポートするランタイム通信スタックを生成します。</span><span class="sxs-lookup"><span data-stu-id="03e7e-163">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e7e-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="03e7e-164">See also</span></span>

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="03e7e-165">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="03e7e-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="03e7e-166">バインディング</span><span class="sxs-lookup"><span data-stu-id="03e7e-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="03e7e-167">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="03e7e-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="03e7e-168">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="03e7e-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="03e7e-169">\<binding ></span><span class="sxs-lookup"><span data-stu-id="03e7e-169">\<binding></span></span>](bindings.md)
