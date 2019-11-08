---
title: <security> の <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736483"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="19ac9-102">\<netHttpBinding > のセキュリティ > の \<</span><span class="sxs-lookup"><span data-stu-id="19ac9-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="19ac9-103">[\<netHttpBinding >](nethttpbinding.md)のセキュリティ機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="19ac9-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

<span data-ttu-id="19ac9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19ac9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19ac9-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="19ac9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="19ac9-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="19ac9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="19ac9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="19ac9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="19ac9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="19ac9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="19ac9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="19ac9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="19ac9-110">構文</span><span class="sxs-lookup"><span data-stu-id="19ac9-110">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="19ac9-111">属性と要素</span><span class="sxs-lookup"><span data-stu-id="19ac9-111">Attributes and elements</span></span>

<span data-ttu-id="19ac9-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="19ac9-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="19ac9-113">属性</span><span class="sxs-lookup"><span data-stu-id="19ac9-113">Attributes</span></span>

|<span data-ttu-id="19ac9-114">属性</span><span class="sxs-lookup"><span data-stu-id="19ac9-114">Attribute</span></span>|<span data-ttu-id="19ac9-115">説明</span><span class="sxs-lookup"><span data-stu-id="19ac9-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="19ac9-116">モード</span><span class="sxs-lookup"><span data-stu-id="19ac9-116">mode</span></span>|<span data-ttu-id="19ac9-117">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="19ac9-117">Optional.</span></span> <span data-ttu-id="19ac9-118">使用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="19ac9-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="19ac9-119">既定値は、 `None`です。</span><span class="sxs-lookup"><span data-stu-id="19ac9-119">The default is `None`.</span></span> <span data-ttu-id="19ac9-120">この属性は <xref:System.ServiceModel.BasicHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="19ac9-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="19ac9-121">mode 属性</span><span class="sxs-lookup"><span data-stu-id="19ac9-121">mode attribute</span></span>

|<span data-ttu-id="19ac9-122">[値]</span><span class="sxs-lookup"><span data-stu-id="19ac9-122">Value</span></span>|<span data-ttu-id="19ac9-123">説明</span><span class="sxs-lookup"><span data-stu-id="19ac9-123">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="19ac9-124">None</span><span class="sxs-lookup"><span data-stu-id="19ac9-124">None</span></span>|<span data-ttu-id="19ac9-125">-メッセージは、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="19ac9-125">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="19ac9-126">Transport</span><span class="sxs-lookup"><span data-stu-id="19ac9-126">Transport</span></span>|<span data-ttu-id="19ac9-127">セキュリティは、HTTPS トランスポートを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="19ac9-128">SOAP メッセージは、HTTPS を使用したセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="19ac9-129">サービスは、サービスの X.509 証明書を使用してクライアントに認証されます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="19ac9-130">クライアントは、提供される ClientCredentialType を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-130">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="19ac9-131">[メッセージ]</span><span class="sxs-lookup"><span data-stu-id="19ac9-131">Message</span></span>|<span data-ttu-id="19ac9-132">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="19ac9-133">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="19ac9-134">このバインディングの場合、サーバー証明書をクライアントの帯域外で提供するように要求されます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="19ac9-135">このバインディングの唯一の有効な `ClientCredentialType` は、`Certificate` です。</span><span class="sxs-lookup"><span data-stu-id="19ac9-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="19ac9-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="19ac9-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="19ac9-137">整合性、機密性、およびサーバー認証は、トランスポート セキュリティによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="19ac9-138">クライアント認証は、SOAP メッセージ セキュリティで提供されます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="19ac9-139">このモードは、ユーザーがユーザー名およびパスワードを使用して認証し、メッセージ転送をセキュリティで保護するために既存の HTTP が配置されている場合に関連します。</span><span class="sxs-lookup"><span data-stu-id="19ac9-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="19ac9-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="19ac9-140">TransportCredentialOnly</span></span>|<span data-ttu-id="19ac9-141">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="19ac9-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="19ac9-142">http ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="19ac9-142">It provides http-based client authentication.</span></span> <span data-ttu-id="19ac9-143">このモードを使用するときは、十分に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19ac9-143">This mode should be used with caution.</span></span> <span data-ttu-id="19ac9-144">トランスポートセキュリティが他の方法 (IPSec など) によって提供され、WCF インフラストラクチャによってクライアント認証のみが提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19ac9-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="19ac9-145">子要素</span><span class="sxs-lookup"><span data-stu-id="19ac9-145">Child elements</span></span>

|<span data-ttu-id="19ac9-146">要素</span><span class="sxs-lookup"><span data-stu-id="19ac9-146">Element</span></span>|<span data-ttu-id="19ac9-147">説明</span><span class="sxs-lookup"><span data-stu-id="19ac9-147">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="19ac9-148">\<transport ></span><span class="sxs-lookup"><span data-stu-id="19ac9-148">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="19ac9-149">基本 HTTP サービスのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="19ac9-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="19ac9-150">この要素は、<xref:System.ServiceModel.HttpTransportSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="19ac9-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="19ac9-151">\< メッセージ ></span><span class="sxs-lookup"><span data-stu-id="19ac9-151">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="19ac9-152">基本 HTTP サービスのメッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="19ac9-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="19ac9-153">この要素は、<xref:System.ServiceModel.BasicHttpMessageSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="19ac9-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="19ac9-154">親要素</span><span class="sxs-lookup"><span data-stu-id="19ac9-154">Parent elements</span></span>

|<span data-ttu-id="19ac9-155">要素</span><span class="sxs-lookup"><span data-stu-id="19ac9-155">Element</span></span>|<span data-ttu-id="19ac9-156">説明</span><span class="sxs-lookup"><span data-stu-id="19ac9-156">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="19ac9-157">バインド</span><span class="sxs-lookup"><span data-stu-id="19ac9-157">binding</span></span>|<span data-ttu-id="19ac9-158">[\<basicHttpBinding >](basichttpbinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="19ac9-158">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="19ac9-159">Remarks</span><span class="sxs-lookup"><span data-stu-id="19ac9-159">Remarks</span></span>

 <span data-ttu-id="19ac9-160">既定では、SOAP メッセージはセキュリティで保護されず、クライアントは認証されません。</span><span class="sxs-lookup"><span data-stu-id="19ac9-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="19ac9-161">この要素を使用すると、`netHttpBinding` 要素に追加のセキュリティ設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="19ac9-161">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="19ac9-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="19ac9-162">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="19ac9-163">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="19ac9-163">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="19ac9-164">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="19ac9-164">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="19ac9-165">バインディング</span><span class="sxs-lookup"><span data-stu-id="19ac9-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="19ac9-166">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="19ac9-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="19ac9-167">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="19ac9-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="19ac9-168">\<binding ></span><span class="sxs-lookup"><span data-stu-id="19ac9-168">\<binding></span></span>](bindings.md)
