---
title: <security> の <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: f84f6c0f9988dd2d07377bf694286922db9d8364
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936801"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="95fba-102">\<basicHttpBinding > の\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="95fba-102">\<security> of \<basicHttpBinding></span></span>
<span data-ttu-id="95fba-103">[ \<BasicHttpBinding >](basichttpbinding.md)のセキュリティ機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="95fba-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="95fba-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="95fba-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="95fba-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="95fba-105">\<bindings></span></span>  
<span data-ttu-id="95fba-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="95fba-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="95fba-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="95fba-107">\<binding></span></span>  
<span data-ttu-id="95fba-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="95fba-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95fba-109">構文</span><span class="sxs-lookup"><span data-stu-id="95fba-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95fba-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="95fba-110">Attributes and Elements</span></span>  
 <span data-ttu-id="95fba-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="95fba-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95fba-112">属性</span><span class="sxs-lookup"><span data-stu-id="95fba-112">Attributes</span></span>  
  
|<span data-ttu-id="95fba-113">属性</span><span class="sxs-lookup"><span data-stu-id="95fba-113">Attribute</span></span>|<span data-ttu-id="95fba-114">説明</span><span class="sxs-lookup"><span data-stu-id="95fba-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95fba-115">モード</span><span class="sxs-lookup"><span data-stu-id="95fba-115">mode</span></span>|<span data-ttu-id="95fba-116">任意。</span><span class="sxs-lookup"><span data-stu-id="95fba-116">Optional.</span></span> <span data-ttu-id="95fba-117">使用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="95fba-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="95fba-118">既定値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="95fba-118">The default is `None`.</span></span> <span data-ttu-id="95fba-119">この属性は <xref:System.ServiceModel.BasicHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="95fba-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="95fba-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="95fba-120">mode Attribute</span></span>  
  
|<span data-ttu-id="95fba-121">値</span><span class="sxs-lookup"><span data-stu-id="95fba-121">Value</span></span>|<span data-ttu-id="95fba-122">説明</span><span class="sxs-lookup"><span data-stu-id="95fba-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="95fba-123">なし</span><span class="sxs-lookup"><span data-stu-id="95fba-123">None</span></span>|<span data-ttu-id="95fba-124">-メッセージは、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="95fba-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="95fba-125">Transport</span><span class="sxs-lookup"><span data-stu-id="95fba-125">Transport</span></span>|<span data-ttu-id="95fba-126">セキュリティは、HTTPS トランスポートを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="95fba-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="95fba-127">SOAP メッセージは、HTTPS を使用してセキュリティ保護されます。</span><span class="sxs-lookup"><span data-stu-id="95fba-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="95fba-128">サービスは、サービスの X.509 証明書を使用してクライアントに認証されます。</span><span class="sxs-lookup"><span data-stu-id="95fba-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="95fba-129">クライアントは、提供される ClientCredentialType を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="95fba-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="95fba-130">トランスポートの[ \<>](transport-of-basichttpbinding.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95fba-130">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="95fba-131">Message</span><span class="sxs-lookup"><span data-stu-id="95fba-131">Message</span></span>|<span data-ttu-id="95fba-132">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="95fba-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="95fba-133">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="95fba-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="95fba-134">このバインディングの場合、サーバー証明書をクライアントの帯域外で提供するように要求されます。</span><span class="sxs-lookup"><span data-stu-id="95fba-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="95fba-135">このバインディングの唯一の有効な `ClientCredentialType` は、`Certificate` です。</span><span class="sxs-lookup"><span data-stu-id="95fba-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="95fba-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="95fba-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="95fba-137">整合性、機密性、およびサーバー認証は、トランスポート セキュリティによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="95fba-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="95fba-138">クライアント認証は、SOAP メッセージ セキュリティで提供されます。</span><span class="sxs-lookup"><span data-stu-id="95fba-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="95fba-139">このモードは、ユーザーがユーザー名およびパスワードを使用して認証し、メッセージ転送をセキュリティで保護するために既存の HTTP が配置されている場合に関連します。</span><span class="sxs-lookup"><span data-stu-id="95fba-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="95fba-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="95fba-140">TransportCredentialOnly</span></span>|<span data-ttu-id="95fba-141">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="95fba-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="95fba-142">http ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="95fba-142">It provides http-based client authentication.</span></span> <span data-ttu-id="95fba-143">このモードは注意して使用してください。</span><span class="sxs-lookup"><span data-stu-id="95fba-143">This mode should be used with caution.</span></span> <span data-ttu-id="95fba-144">トランスポートセキュリティが他の方法 (IPSec など) によって提供され、WCF インフラストラクチャによってクライアント認証のみが提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95fba-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95fba-145">子要素</span><span class="sxs-lookup"><span data-stu-id="95fba-145">Child Elements</span></span>  
  
|<span data-ttu-id="95fba-146">要素</span><span class="sxs-lookup"><span data-stu-id="95fba-146">Element</span></span>|<span data-ttu-id="95fba-147">説明</span><span class="sxs-lookup"><span data-stu-id="95fba-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95fba-148">\<transport></span><span class="sxs-lookup"><span data-stu-id="95fba-148">\<transport></span></span>](transport-of-basichttpbinding.md)|<span data-ttu-id="95fba-149">基本 HTTP サービスのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="95fba-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="95fba-150">この要素は、<xref:System.ServiceModel.HttpTransportSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="95fba-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="95fba-151">\<message></span><span class="sxs-lookup"><span data-stu-id="95fba-151">\<message></span></span>](message-of-basichttpbinding.md)|<span data-ttu-id="95fba-152">基本 HTTP サービスのメッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="95fba-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="95fba-153">この要素は、<xref:System.ServiceModel.BasicHttpMessageSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="95fba-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95fba-154">親要素</span><span class="sxs-lookup"><span data-stu-id="95fba-154">Parent Elements</span></span>  
  
|<span data-ttu-id="95fba-155">要素</span><span class="sxs-lookup"><span data-stu-id="95fba-155">Element</span></span>|<span data-ttu-id="95fba-156">説明</span><span class="sxs-lookup"><span data-stu-id="95fba-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95fba-157">バインド</span><span class="sxs-lookup"><span data-stu-id="95fba-157">binding</span></span>|<span data-ttu-id="95fba-158">[ \<BasicHttpBinding >](basichttpbinding.md)のバインド要素。</span><span class="sxs-lookup"><span data-stu-id="95fba-158">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95fba-159">Remarks</span><span class="sxs-lookup"><span data-stu-id="95fba-159">Remarks</span></span>  
 <span data-ttu-id="95fba-160">既定では、SOAP メッセージはセキュリティで保護されず、クライアントは認証されません。</span><span class="sxs-lookup"><span data-stu-id="95fba-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="95fba-161">この要素を使用すると、`basicHttpBinding` 要素に追加のセキュリティ設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="95fba-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95fba-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="95fba-162">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="95fba-163">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="95fba-163">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="95fba-164">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="95fba-164">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="95fba-165">バインディング</span><span class="sxs-lookup"><span data-stu-id="95fba-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="95fba-166">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="95fba-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="95fba-167">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="95fba-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="95fba-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="95fba-168">\<binding></span></span>](../../../misc/binding.md)
