---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 4ec5a99139112ae600c1c2bc44feb6d3f62da1e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931737"
---
# <a name="localissuer"></a><span data-ttu-id="76e08-101">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="76e08-101">\<localIssuer></span></span>
<span data-ttu-id="76e08-102">セキュリティ トークンの取得に使用される、ローカル発行者のアドレスとバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="76e08-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="76e08-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="76e08-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="76e08-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="76e08-104">\<behaviors></span></span>  
<span data-ttu-id="76e08-105">endpointBehaviors セクション</span><span class="sxs-lookup"><span data-stu-id="76e08-105">endpointBehaviors section</span></span>  
<span data-ttu-id="76e08-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="76e08-106">\<behavior></span></span>  
<span data-ttu-id="76e08-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="76e08-107">\<clientCredentials></span></span>  
<span data-ttu-id="76e08-108">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="76e08-108">\<issuedToken></span></span>  
<span data-ttu-id="76e08-109">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="76e08-109">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e08-110">構文</span><span class="sxs-lookup"><span data-stu-id="76e08-110">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76e08-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="76e08-111">Attributes and Elements</span></span>  
 <span data-ttu-id="76e08-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="76e08-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76e08-113">属性</span><span class="sxs-lookup"><span data-stu-id="76e08-113">Attributes</span></span>  
  
|<span data-ttu-id="76e08-114">属性</span><span class="sxs-lookup"><span data-stu-id="76e08-114">Attribute</span></span>|<span data-ttu-id="76e08-115">説明</span><span class="sxs-lookup"><span data-stu-id="76e08-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76e08-116">address</span><span class="sxs-lookup"><span data-stu-id="76e08-116">address</span></span>|<span data-ttu-id="76e08-117">必須の文字列。</span><span class="sxs-lookup"><span data-stu-id="76e08-117">Required string.</span></span> <span data-ttu-id="76e08-118">ローカル発行者の URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="76e08-118">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="76e08-119">バインド</span><span class="sxs-lookup"><span data-stu-id="76e08-119">binding</span></span>|<span data-ttu-id="76e08-120">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="76e08-120">Optional string.</span></span> <span data-ttu-id="76e08-121">システム指定のバインディングの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="76e08-121">One of the system-provided bindings.</span></span> <span data-ttu-id="76e08-122">リストについては、「[システム指定のバインディング](../../../wcf/system-provided-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76e08-122">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="76e08-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="76e08-123">bindingConfiguration</span></span>|<span data-ttu-id="76e08-124">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="76e08-124">Optional string.</span></span> <span data-ttu-id="76e08-125">構成ファイル内に存在するバインド構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="76e08-125">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76e08-126">子要素</span><span class="sxs-lookup"><span data-stu-id="76e08-126">Child Elements</span></span>  
  
|<span data-ttu-id="76e08-127">要素</span><span class="sxs-lookup"><span data-stu-id="76e08-127">Element</span></span>|<span data-ttu-id="76e08-128">説明</span><span class="sxs-lookup"><span data-stu-id="76e08-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76e08-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="76e08-129">\<identity></span></span>](identity.md)|<span data-ttu-id="76e08-130">ローカル発行者の ID 情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="76e08-130">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="76e08-131">\<headers></span><span class="sxs-lookup"><span data-stu-id="76e08-131">\<headers></span></span>](headers-element.md)|<span data-ttu-id="76e08-132">ローカル発行者を正しくアドレス指定するために必要なアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="76e08-132">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="76e08-133">`add` キーワードを使用して、このコレクションにヘッダーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="76e08-133">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76e08-134">親要素</span><span class="sxs-lookup"><span data-stu-id="76e08-134">Parent Elements</span></span>  
  
|<span data-ttu-id="76e08-135">要素</span><span class="sxs-lookup"><span data-stu-id="76e08-135">Element</span></span>|<span data-ttu-id="76e08-136">説明</span><span class="sxs-lookup"><span data-stu-id="76e08-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76e08-137">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="76e08-137">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="76e08-138">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="76e08-138">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76e08-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="76e08-139">Remarks</span></span>  
 <span data-ttu-id="76e08-140">発行されたトークンをセキュリティ トークン サービス (STS) から取得する場合は、クライアント アプリケーションに、STS との通信に使用するアドレスとバインディングが構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76e08-140">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="76e08-141">ときに、<xref:System.ServiceModel.WSFederationHttpBinding>またはフェデレーション バインディングの発行者アドレスが、セキュリティ トークン サービスの URL を指定していません `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` または`null`クライアントの Windows Communication Foundation (WCF) チャネルで指定された値を使用して`address`と`binding`発行済みトークンを取得するための STS と通信します。</span><span class="sxs-lookup"><span data-stu-id="76e08-141">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="76e08-142">ローカル発行者の構成の詳細について[は、「」を参照してください。ローカル発行者](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)を構成します。</span><span class="sxs-lookup"><span data-stu-id="76e08-142">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76e08-143">例</span><span class="sxs-lookup"><span data-stu-id="76e08-143">Example</span></span>  
 <span data-ttu-id="76e08-144">次の例は、`address` 要素の `binding`、`bindingConfiguration`、および `localIssuer` 属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="76e08-144">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="MyEndpointBehavior">
        <clientCredentials>
          <issuedToken cacheIssuedTokens="false"
                       defaultKeyEntropyMode="ClientEntropy">
            <localIssuer address="net.tcp://cohowinery/tokens"
                         binding="netTcpBinding"
                         bindingConfiguration="myTcpBindingConfig" />
          </issuedToken>
        </clientCredentials>
      </behavior>
    </endpointBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="76e08-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="76e08-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="76e08-146">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="76e08-146">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="76e08-147">方法: ローカル発行者を構成する</span><span class="sxs-lookup"><span data-stu-id="76e08-147">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="76e08-148">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="76e08-148">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="76e08-149">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="76e08-149">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="76e08-150">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="76e08-150">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="76e08-151">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="76e08-151">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="76e08-152">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="76e08-152">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="76e08-153">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="76e08-153">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="76e08-154">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="76e08-154">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
