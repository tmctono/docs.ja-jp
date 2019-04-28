---
title: <security> の <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: f2750036aa4d3fbe41062ad041e50ff3a4be32b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670573"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="3b7ff-102">\<セキュリティ > の\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3b7ff-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="3b7ff-103">セキュリティ機能を定義、 [ \<basicHttpBinding >](basichttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>

<span data-ttu-id="3b7ff-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="3b7ff-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="3b7ff-105">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="3b7ff-105">\<bindings>\\</span></span>
<span data-ttu-id="3b7ff-106">\<netHttpBinding > \\</span><span class="sxs-lookup"><span data-stu-id="3b7ff-106">\<netHttpBinding>\\</span></span>
<span data-ttu-id="3b7ff-107">\<バインド > \\</span><span class="sxs-lookup"><span data-stu-id="3b7ff-107">\<binding>\\</span></span>
<span data-ttu-id="3b7ff-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="3b7ff-108">\<security></span></span>

## <a name="syntax"></a><span data-ttu-id="3b7ff-109">構文</span><span class="sxs-lookup"><span data-stu-id="3b7ff-109">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3b7ff-110">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3b7ff-110">Attributes and elements</span></span>

<span data-ttu-id="3b7ff-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3b7ff-112">属性</span><span class="sxs-lookup"><span data-stu-id="3b7ff-112">Attributes</span></span>

|<span data-ttu-id="3b7ff-113">属性</span><span class="sxs-lookup"><span data-stu-id="3b7ff-113">Attribute</span></span>|<span data-ttu-id="3b7ff-114">説明</span><span class="sxs-lookup"><span data-stu-id="3b7ff-114">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="3b7ff-115">モード</span><span class="sxs-lookup"><span data-stu-id="3b7ff-115">mode</span></span>|<span data-ttu-id="3b7ff-116">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-116">Optional.</span></span> <span data-ttu-id="3b7ff-117">使用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="3b7ff-118">既定値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-118">The default is `None`.</span></span> <span data-ttu-id="3b7ff-119">この属性は <xref:System.ServiceModel.BasicHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="3b7ff-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="3b7ff-120">mode attribute</span></span>

|<span data-ttu-id="3b7ff-121">[値]</span><span class="sxs-lookup"><span data-stu-id="3b7ff-121">Value</span></span>|<span data-ttu-id="3b7ff-122">説明</span><span class="sxs-lookup"><span data-stu-id="3b7ff-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="3b7ff-123">なし</span><span class="sxs-lookup"><span data-stu-id="3b7ff-123">None</span></span>|<span data-ttu-id="3b7ff-124">メッセージの数は、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-124">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="3b7ff-125">Transport</span><span class="sxs-lookup"><span data-stu-id="3b7ff-125">Transport</span></span>|<span data-ttu-id="3b7ff-126">セキュリティは、HTTPS トランスポートを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="3b7ff-127">SOAP メッセージは、HTTPS を使用したセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="3b7ff-128">サービスは、サービスの X.509 証明書を使用してクライアントに認証されます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="3b7ff-129">クライアントは、提供される ClientCredentialType を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="3b7ff-130">メッセージ</span><span class="sxs-lookup"><span data-stu-id="3b7ff-130">Message</span></span>|<span data-ttu-id="3b7ff-131">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="3b7ff-132">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="3b7ff-133">このバインディングの場合、サーバー証明書をクライアントの帯域外で提供するように要求されます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="3b7ff-134">このバインディングの唯一の有効な `ClientCredentialType` は、`Certificate` です。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="3b7ff-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="3b7ff-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="3b7ff-136">整合性、機密性、およびサーバー認証は、トランスポート セキュリティによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="3b7ff-137">クライアント認証は、SOAP メッセージ セキュリティで提供されます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="3b7ff-138">このモードは、ユーザーがユーザー名およびパスワードを使用して認証し、メッセージ転送をセキュリティで保護するために既存の HTTP が配置されている場合に関連します。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="3b7ff-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="3b7ff-139">TransportCredentialOnly</span></span>|<span data-ttu-id="3b7ff-140">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="3b7ff-141">http ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-141">It provides http-based client authentication.</span></span> <span data-ttu-id="3b7ff-142">このモードを使用するときは、十分に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-142">This mode should be used with caution.</span></span> <span data-ttu-id="3b7ff-143">これは、トランスポート セキュリティ (IPSec) などの他の方法で提供されるされ、クライアント認証だけが、WCF インフラストラクチャによって提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3b7ff-144">子要素</span><span class="sxs-lookup"><span data-stu-id="3b7ff-144">Child elements</span></span>

|<span data-ttu-id="3b7ff-145">要素</span><span class="sxs-lookup"><span data-stu-id="3b7ff-145">Element</span></span>|<span data-ttu-id="3b7ff-146">説明</span><span class="sxs-lookup"><span data-stu-id="3b7ff-146">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3b7ff-147">\<transport></span><span class="sxs-lookup"><span data-stu-id="3b7ff-147">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="3b7ff-148">基本 HTTP サービスのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="3b7ff-149">この要素は、<xref:System.ServiceModel.HttpTransportSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="3b7ff-150">\<message></span><span class="sxs-lookup"><span data-stu-id="3b7ff-150">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="3b7ff-151">基本 HTTP サービスのメッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="3b7ff-152">この要素は、<xref:System.ServiceModel.BasicHttpMessageSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-152">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3b7ff-153">親要素</span><span class="sxs-lookup"><span data-stu-id="3b7ff-153">Parent elements</span></span>

|<span data-ttu-id="3b7ff-154">要素</span><span class="sxs-lookup"><span data-stu-id="3b7ff-154">Element</span></span>|<span data-ttu-id="3b7ff-155">説明</span><span class="sxs-lookup"><span data-stu-id="3b7ff-155">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="3b7ff-156">バインド</span><span class="sxs-lookup"><span data-stu-id="3b7ff-156">binding</span></span>|<span data-ttu-id="3b7ff-157">バインド要素、 [ \<basicHttpBinding >](basichttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-157">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="3b7ff-158">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b7ff-158">Remarks</span></span>

 <span data-ttu-id="3b7ff-159">既定では、SOAP メッセージはセキュリティで保護されず、クライアントは認証されません。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="3b7ff-160">この要素を使用すると、`netHttpBinding` 要素に追加のセキュリティ設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3b7ff-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b7ff-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b7ff-161">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="3b7ff-162">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="3b7ff-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3b7ff-163">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="3b7ff-163">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="3b7ff-164">バインディング</span><span class="sxs-lookup"><span data-stu-id="3b7ff-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3b7ff-165">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="3b7ff-165">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3b7ff-166">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="3b7ff-166">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3b7ff-167">\<binding></span><span class="sxs-lookup"><span data-stu-id="3b7ff-167">\<binding></span></span>](../../../misc/binding.md)
