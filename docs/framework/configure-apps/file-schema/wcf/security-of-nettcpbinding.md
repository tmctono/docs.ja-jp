---
title: <security> の <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: aa01e906ddd2f15007c72bfc2a45122cfb15ba2c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736370"
---
# <a name="security-of-nettcpbinding"></a><span data-ttu-id="eb6bc-102">\<security> の \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="eb6bc-102">\<security> of \<netTcpBinding></span></span>
<span data-ttu-id="eb6bc-103">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="eb6bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb6bc-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb6bc-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eb6bc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="eb6bc-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb6bc-107">属性</span><span class="sxs-lookup"><span data-stu-id="eb6bc-107">Attributes</span></span>  
  
|<span data-ttu-id="eb6bc-108">属性</span><span class="sxs-lookup"><span data-stu-id="eb6bc-108">Attribute</span></span>|<span data-ttu-id="eb6bc-109">説明</span><span class="sxs-lookup"><span data-stu-id="eb6bc-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb6bc-110">mode</span><span class="sxs-lookup"><span data-stu-id="eb6bc-110">mode</span></span>|<span data-ttu-id="eb6bc-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-111">Optional.</span></span> <span data-ttu-id="eb6bc-112">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="eb6bc-113">有効な値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-113">Valid values are shown below.</span></span> <span data-ttu-id="eb6bc-114">既定値は `Transport` です。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-114">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="eb6bc-115">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-115">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="eb6bc-116">mode 属性</span><span class="sxs-lookup"><span data-stu-id="eb6bc-116">mode Attribute</span></span>  
  
|<span data-ttu-id="eb6bc-117">値</span><span class="sxs-lookup"><span data-stu-id="eb6bc-117">Value</span></span>|<span data-ttu-id="eb6bc-118">説明</span><span class="sxs-lookup"><span data-stu-id="eb6bc-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb6bc-119">なし</span><span class="sxs-lookup"><span data-stu-id="eb6bc-119">None</span></span>|<span data-ttu-id="eb6bc-120">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-120">Security is disabled.</span></span>|  
|<span data-ttu-id="eb6bc-121">トランスポート</span><span class="sxs-lookup"><span data-stu-id="eb6bc-121">Transport</span></span>|<span data-ttu-id="eb6bc-122">トランスポート セキュリティは、TCP 経由の TLS または SPNaego を使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-122">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="eb6bc-123">サービスは、SSL 証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-123">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="eb6bc-124">このモードでは保護レベルを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-124">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="eb6bc-125">Message</span><span class="sxs-lookup"><span data-stu-id="eb6bc-125">Message</span></span>|<span data-ttu-id="eb6bc-126">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="eb6bc-127">既定では、SOAP 本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-127">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="eb6bc-128">このモードは、サービス資格情報をクライアントの帯域外で使用可能にするかどうか、使用するアルゴリズム スイート、メッセージ本文に適用する保護レベルなど、さまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-128">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="eb6bc-129">クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-129">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="eb6bc-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="eb6bc-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="eb6bc-131">トランスポート セキュリティは、メッセージ セキュリティと組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-131">Transport security is coupled with message security.</span></span> <span data-ttu-id="eb6bc-132">トランスポート セキュリティは、TCP 経由の TLS または SPNego によって提供され、整合性、機密性、およびサーバー認証が保証されます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-132">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="eb6bc-133">SOAP メッセージ セキュリティは、クライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-133">SOAP message security provides client authentication.</span></span> <span data-ttu-id="eb6bc-134">既定では、クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-134">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb6bc-135">子要素</span><span class="sxs-lookup"><span data-stu-id="eb6bc-135">Child Elements</span></span>  
  
|<span data-ttu-id="eb6bc-136">要素</span><span class="sxs-lookup"><span data-stu-id="eb6bc-136">Element</span></span>|<span data-ttu-id="eb6bc-137">Description</span><span class="sxs-lookup"><span data-stu-id="eb6bc-137">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|<span data-ttu-id="eb6bc-138">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-138">Defines the security settings for the transport.</span></span> <span data-ttu-id="eb6bc-139">この要素は <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-139">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[\<message>](message-element-of-nettcpbinding.md)|<span data-ttu-id="eb6bc-140">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-140">Defines the security settings for the message.</span></span> <span data-ttu-id="eb6bc-141">この要素は <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-141">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb6bc-142">親要素</span><span class="sxs-lookup"><span data-stu-id="eb6bc-142">Parent Elements</span></span>  
  
|<span data-ttu-id="eb6bc-143">要素</span><span class="sxs-lookup"><span data-stu-id="eb6bc-143">Element</span></span>|<span data-ttu-id="eb6bc-144">Description</span><span class="sxs-lookup"><span data-stu-id="eb6bc-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb6bc-145">binding</span><span class="sxs-lookup"><span data-stu-id="eb6bc-145">binding</span></span>|<span data-ttu-id="eb6bc-146">のバインディング要素 [\<netTcpBinding>](nettcpbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-146">The binding element of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb6bc-147">解説</span><span class="sxs-lookup"><span data-stu-id="eb6bc-147">Remarks</span></span>  
 <span data-ttu-id="eb6bc-148">標準バインディングにはそれぞれ、転送セキュリティ要件を制御するためのパラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-148">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="eb6bc-149">通常、これらのパラメーターには、使用されるセキュリティ レベル (メッセージ レベルまたはトランスポート レベル) を指定したセキュリティ モードと、クライアント資格情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-149">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="eb6bc-150">これらのパラメーターが提示するオプションの選択に基づいて、適切なセキュリティが設定されたチャネル スタックが構築されます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-150">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="eb6bc-151">WCF (Windows Communication Foundation) に用意されているシステム標準のバインディグは、最も一般的なシナリオ要件の一部を満たすように設計されたセットです。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-151">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="eb6bc-152">これらのバイディングでは、特定のシナリオを対象とするセキュリティ要件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-152">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="eb6bc-153">この構成要素によって、`netTcpBinding` のセキュリティ仕様が提供されます。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-153">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="eb6bc-154">これは、コンピューター間通信に適した、安全で信頼できる最適化されたバインディングです。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-154">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="eb6bc-155">既定では、このバインディングは、メッセージを配信するための TCP、メッセージの保護と認証を行うための Windows セキュリティ、信頼性を高めるための WS-ReliableMessaging、およびバイナリ メッセージのエンコーディングをサポートするランタイム通信スタックを生成します。</span><span class="sxs-lookup"><span data-stu-id="eb6bc-155">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb6bc-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb6bc-156">See also</span></span>

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="eb6bc-157">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="eb6bc-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="eb6bc-158">バインド</span><span class="sxs-lookup"><span data-stu-id="eb6bc-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eb6bc-159">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="eb6bc-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="eb6bc-160">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="eb6bc-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
