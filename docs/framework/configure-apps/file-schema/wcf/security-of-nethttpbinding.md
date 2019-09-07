---
title: <security> の <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 890cee3271c410a921b3a88f78d0705ba8718252
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399856"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="ceac6-102">\<netHttpBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="ceac6-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="ceac6-103">[ \<NetHttpBinding >](nethttpbinding.md)のセキュリティ機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="ceac6-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

<span data-ttu-id="ceac6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ceac6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ceac6-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ceac6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ceac6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ceac6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ceac6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ceac6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="ceac6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="ceac6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ceac6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<セキュリティ >**</span><span class="sxs-lookup"><span data-stu-id="ceac6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="ceac6-110">構文</span><span class="sxs-lookup"><span data-stu-id="ceac6-110">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ceac6-111">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ceac6-111">Attributes and elements</span></span>

<span data-ttu-id="ceac6-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ceac6-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ceac6-113">属性</span><span class="sxs-lookup"><span data-stu-id="ceac6-113">Attributes</span></span>

|<span data-ttu-id="ceac6-114">属性</span><span class="sxs-lookup"><span data-stu-id="ceac6-114">Attribute</span></span>|<span data-ttu-id="ceac6-115">説明</span><span class="sxs-lookup"><span data-stu-id="ceac6-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="ceac6-116">モード</span><span class="sxs-lookup"><span data-stu-id="ceac6-116">mode</span></span>|<span data-ttu-id="ceac6-117">任意。</span><span class="sxs-lookup"><span data-stu-id="ceac6-117">Optional.</span></span> <span data-ttu-id="ceac6-118">使用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="ceac6-118">Specifies the type of security that is used.</span></span> <span data-ttu-id="ceac6-119">既定値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="ceac6-119">The default is `None`.</span></span> <span data-ttu-id="ceac6-120">この属性は <xref:System.ServiceModel.BasicHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="ceac6-120">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="ceac6-121">mode 属性</span><span class="sxs-lookup"><span data-stu-id="ceac6-121">mode attribute</span></span>

|<span data-ttu-id="ceac6-122">値</span><span class="sxs-lookup"><span data-stu-id="ceac6-122">Value</span></span>|<span data-ttu-id="ceac6-123">説明</span><span class="sxs-lookup"><span data-stu-id="ceac6-123">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="ceac6-124">なし</span><span class="sxs-lookup"><span data-stu-id="ceac6-124">None</span></span>|<span data-ttu-id="ceac6-125">-メッセージは、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="ceac6-125">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="ceac6-126">Transport</span><span class="sxs-lookup"><span data-stu-id="ceac6-126">Transport</span></span>|<span data-ttu-id="ceac6-127">セキュリティは、HTTPS トランスポートを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-127">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="ceac6-128">SOAP メッセージは、HTTPS を使用してセキュリティ保護されます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-128">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="ceac6-129">サービスは、サービスの X.509 証明書を使用してクライアントに認証されます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-129">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="ceac6-130">クライアントは、提供される ClientCredentialType を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-130">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="ceac6-131">Message</span><span class="sxs-lookup"><span data-stu-id="ceac6-131">Message</span></span>|<span data-ttu-id="ceac6-132">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="ceac6-133">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="ceac6-134">このバインディングの場合、サーバー証明書をクライアントの帯域外で提供するように要求されます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="ceac6-135">このバインディングの唯一の有効な `ClientCredentialType` は、`Certificate` です。</span><span class="sxs-lookup"><span data-stu-id="ceac6-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="ceac6-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="ceac6-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="ceac6-137">整合性、機密性、およびサーバー認証は、トランスポート セキュリティによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="ceac6-138">クライアント認証は、SOAP メッセージ セキュリティで提供されます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="ceac6-139">このモードは、ユーザーがユーザー名およびパスワードを使用して認証し、メッセージ転送をセキュリティで保護するために既存の HTTP が配置されている場合に関連します。</span><span class="sxs-lookup"><span data-stu-id="ceac6-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="ceac6-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="ceac6-140">TransportCredentialOnly</span></span>|<span data-ttu-id="ceac6-141">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="ceac6-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="ceac6-142">http ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="ceac6-142">It provides http-based client authentication.</span></span> <span data-ttu-id="ceac6-143">このモードは注意して使用してください。</span><span class="sxs-lookup"><span data-stu-id="ceac6-143">This mode should be used with caution.</span></span> <span data-ttu-id="ceac6-144">トランスポートセキュリティが他の方法 (IPSec など) によって提供され、WCF インフラストラクチャによってクライアント認証のみが提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceac6-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ceac6-145">子要素</span><span class="sxs-lookup"><span data-stu-id="ceac6-145">Child elements</span></span>

|<span data-ttu-id="ceac6-146">要素</span><span class="sxs-lookup"><span data-stu-id="ceac6-146">Element</span></span>|<span data-ttu-id="ceac6-147">説明</span><span class="sxs-lookup"><span data-stu-id="ceac6-147">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ceac6-148">\<transport></span><span class="sxs-lookup"><span data-stu-id="ceac6-148">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="ceac6-149">基本 HTTP サービスのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ceac6-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="ceac6-150">この要素は、<xref:System.ServiceModel.HttpTransportSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="ceac6-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="ceac6-151">\<message></span><span class="sxs-lookup"><span data-stu-id="ceac6-151">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="ceac6-152">基本 HTTP サービスのメッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ceac6-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="ceac6-153">この要素は、<xref:System.ServiceModel.BasicHttpMessageSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="ceac6-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ceac6-154">親要素</span><span class="sxs-lookup"><span data-stu-id="ceac6-154">Parent elements</span></span>

|<span data-ttu-id="ceac6-155">要素</span><span class="sxs-lookup"><span data-stu-id="ceac6-155">Element</span></span>|<span data-ttu-id="ceac6-156">説明</span><span class="sxs-lookup"><span data-stu-id="ceac6-156">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="ceac6-157">バインド</span><span class="sxs-lookup"><span data-stu-id="ceac6-157">binding</span></span>|<span data-ttu-id="ceac6-158">[ \<BasicHttpBinding >](basichttpbinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="ceac6-158">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="ceac6-159">Remarks</span><span class="sxs-lookup"><span data-stu-id="ceac6-159">Remarks</span></span>

 <span data-ttu-id="ceac6-160">既定では、SOAP メッセージはセキュリティで保護されず、クライアントは認証されません。</span><span class="sxs-lookup"><span data-stu-id="ceac6-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="ceac6-161">この要素を使用すると、`netHttpBinding` 要素に追加のセキュリティ設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ceac6-161">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="ceac6-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="ceac6-162">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="ceac6-163">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ceac6-163">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ceac6-164">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="ceac6-164">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="ceac6-165">バインディング</span><span class="sxs-lookup"><span data-stu-id="ceac6-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ceac6-166">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="ceac6-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ceac6-167">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="ceac6-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ceac6-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="ceac6-168">\<binding></span></span>](../../../misc/binding.md)
