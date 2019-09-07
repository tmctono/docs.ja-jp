---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 055b7b49d1f775d49ac20de18c18ca0433716a23
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397861"
---
# <a name="localissuer"></a><span data-ttu-id="1bb91-101">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="1bb91-101">\<localIssuer></span></span>
<span data-ttu-id="1bb91-102">セキュリティ トークンの取得に使用される、ローカル発行者のアドレスとバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="1bb91-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
<span data-ttu-id="1bb91-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1bb91-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1bb91-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1bb91-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1bb91-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1bb91-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1bb91-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1bb91-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="1bb91-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1bb91-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="1bb91-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="1bb91-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="1bb91-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="1bb91-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="1bb91-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<localIssuer >**</span><span class="sxs-lookup"><span data-stu-id="1bb91-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb91-111">構文</span><span class="sxs-lookup"><span data-stu-id="1bb91-111">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bb91-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1bb91-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1bb91-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bb91-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bb91-114">属性</span><span class="sxs-lookup"><span data-stu-id="1bb91-114">Attributes</span></span>  
  
|<span data-ttu-id="1bb91-115">属性</span><span class="sxs-lookup"><span data-stu-id="1bb91-115">Attribute</span></span>|<span data-ttu-id="1bb91-116">説明</span><span class="sxs-lookup"><span data-stu-id="1bb91-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bb91-117">address</span><span class="sxs-lookup"><span data-stu-id="1bb91-117">address</span></span>|<span data-ttu-id="1bb91-118">必須の文字列。</span><span class="sxs-lookup"><span data-stu-id="1bb91-118">Required string.</span></span> <span data-ttu-id="1bb91-119">ローカル発行者の URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="1bb91-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="1bb91-120">バインド</span><span class="sxs-lookup"><span data-stu-id="1bb91-120">binding</span></span>|<span data-ttu-id="1bb91-121">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="1bb91-121">Optional string.</span></span> <span data-ttu-id="1bb91-122">システム指定のバインディングの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="1bb91-122">One of the system-provided bindings.</span></span> <span data-ttu-id="1bb91-123">リストについては、「[システム指定のバインディング](../../../wcf/system-provided-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bb91-123">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="1bb91-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="1bb91-124">bindingConfiguration</span></span>|<span data-ttu-id="1bb91-125">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="1bb91-125">Optional string.</span></span> <span data-ttu-id="1bb91-126">構成ファイル内に存在するバインド構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="1bb91-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bb91-127">子要素</span><span class="sxs-lookup"><span data-stu-id="1bb91-127">Child Elements</span></span>  
  
|<span data-ttu-id="1bb91-128">要素</span><span class="sxs-lookup"><span data-stu-id="1bb91-128">Element</span></span>|<span data-ttu-id="1bb91-129">説明</span><span class="sxs-lookup"><span data-stu-id="1bb91-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bb91-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="1bb91-130">\<identity></span></span>](identity.md)|<span data-ttu-id="1bb91-131">ローカル発行者の ID 情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="1bb91-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="1bb91-132">\<headers></span><span class="sxs-lookup"><span data-stu-id="1bb91-132">\<headers></span></span>](headers-element.md)|<span data-ttu-id="1bb91-133">ローカル発行者を正しくアドレス指定するために必要なアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1bb91-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="1bb91-134">`add` キーワードを使用して、このコレクションにヘッダーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1bb91-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1bb91-135">親要素</span><span class="sxs-lookup"><span data-stu-id="1bb91-135">Parent Elements</span></span>  
  
|<span data-ttu-id="1bb91-136">要素</span><span class="sxs-lookup"><span data-stu-id="1bb91-136">Element</span></span>|<span data-ttu-id="1bb91-137">説明</span><span class="sxs-lookup"><span data-stu-id="1bb91-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bb91-138">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="1bb91-138">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="1bb91-139">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1bb91-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bb91-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="1bb91-140">Remarks</span></span>  
 <span data-ttu-id="1bb91-141">発行されたトークンをセキュリティ トークン サービス (STS) から取得する場合は、クライアント アプリケーションに、STS との通信に使用するアドレスとバインディングが構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bb91-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="1bb91-142">ときに、<xref:System.ServiceModel.WSFederationHttpBinding>またはフェデレーション バインディングの発行者アドレスが、セキュリティ トークン サービスの URL を指定していません `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` または`null`クライアントの Windows Communication Foundation (WCF) チャネルで指定された値を使用して`address`と`binding`発行済みトークンを取得するための STS と通信します。</span><span class="sxs-lookup"><span data-stu-id="1bb91-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="1bb91-143">ローカル発行者の構成の詳細について[は、「」を参照してください。ローカル発行者](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)を構成します。</span><span class="sxs-lookup"><span data-stu-id="1bb91-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb91-144">例</span><span class="sxs-lookup"><span data-stu-id="1bb91-144">Example</span></span>  
 <span data-ttu-id="1bb91-145">次の例は、`address` 要素の `binding`、`bindingConfiguration`、および `localIssuer` 属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="1bb91-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1bb91-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bb91-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="1bb91-147">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="1bb91-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1bb91-148">方法: ローカル発行者を構成する</span><span class="sxs-lookup"><span data-stu-id="1bb91-148">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="1bb91-149">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="1bb91-149">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1bb91-150">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="1bb91-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1bb91-151">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="1bb91-151">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1bb91-152">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1bb91-152">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1bb91-153">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1bb91-153">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="1bb91-154">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="1bb91-154">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="1bb91-155">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="1bb91-155">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
