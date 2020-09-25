---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: e08d2c0b42cfd8e302223915f0256f8cb2d1468b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204958"
---
# \<localIssuer>

<span data-ttu-id="0d96a-101">セキュリティ トークンの取得に使用される、ローカル発行者のアドレスとバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d96a-101">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**  
  
## <a name="syntax"></a><span data-ttu-id="0d96a-102">構文</span><span class="sxs-lookup"><span data-stu-id="0d96a-102">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d96a-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0d96a-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0d96a-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d96a-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d96a-105">属性</span><span class="sxs-lookup"><span data-stu-id="0d96a-105">Attributes</span></span>  
  
|<span data-ttu-id="0d96a-106">属性</span><span class="sxs-lookup"><span data-stu-id="0d96a-106">Attribute</span></span>|<span data-ttu-id="0d96a-107">説明</span><span class="sxs-lookup"><span data-stu-id="0d96a-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d96a-108">address</span><span class="sxs-lookup"><span data-stu-id="0d96a-108">address</span></span>|<span data-ttu-id="0d96a-109">必須の文字列。</span><span class="sxs-lookup"><span data-stu-id="0d96a-109">Required string.</span></span> <span data-ttu-id="0d96a-110">ローカル発行者の URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d96a-110">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="0d96a-111">binding</span><span class="sxs-lookup"><span data-stu-id="0d96a-111">binding</span></span>|<span data-ttu-id="0d96a-112">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="0d96a-112">Optional string.</span></span> <span data-ttu-id="0d96a-113">システム指定のバインディングの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="0d96a-113">One of the system-provided bindings.</span></span> <span data-ttu-id="0d96a-114">リストについては、「 [システム指定のバインディング](../../../wcf/system-provided-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d96a-114">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="0d96a-115">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d96a-115">bindingConfiguration</span></span>|<span data-ttu-id="0d96a-116">省略可能な文字列。</span><span class="sxs-lookup"><span data-stu-id="0d96a-116">Optional string.</span></span> <span data-ttu-id="0d96a-117">構成ファイル内に存在するバインディング構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d96a-117">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d96a-118">子要素</span><span class="sxs-lookup"><span data-stu-id="0d96a-118">Child Elements</span></span>  
  
|<span data-ttu-id="0d96a-119">要素</span><span class="sxs-lookup"><span data-stu-id="0d96a-119">Element</span></span>|<span data-ttu-id="0d96a-120">説明</span><span class="sxs-lookup"><span data-stu-id="0d96a-120">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="0d96a-121">ローカル発行者の ID 情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d96a-121">Specifies identity information for the local issuer.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="0d96a-122">ローカル発行者を正しくアドレス指定するために必要なアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="0d96a-122">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="0d96a-123">`add` キーワードを使用して、このコレクションにヘッダーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0d96a-123">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d96a-124">親要素</span><span class="sxs-lookup"><span data-stu-id="0d96a-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0d96a-125">要素</span><span class="sxs-lookup"><span data-stu-id="0d96a-125">Element</span></span>|<span data-ttu-id="0d96a-126">説明</span><span class="sxs-lookup"><span data-stu-id="0d96a-126">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="0d96a-127">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d96a-127">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d96a-128">解説</span><span class="sxs-lookup"><span data-stu-id="0d96a-128">Remarks</span></span>  

 <span data-ttu-id="0d96a-129">発行されたトークンをセキュリティ トークン サービス (STS) から取得する場合は、クライアント アプリケーションに、STS との通信に使用するアドレスとバインディングが構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d96a-129">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="0d96a-130">が <xref:System.ServiceModel.WSFederationHttpBinding> Security Token Service の URL を提供しない場合、またはフェデレーションバインディングの発行者アドレスが `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` またはの場合 `null` 、クライアントの Windows Communication Foundation (WCF) チャネルは、およびで指定された値を使用して `address` STS と通信し、発行され `binding` たトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="0d96a-130">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="0d96a-131">ローカル発行者の構成の詳細については、「 [方法: ローカル発行者を構成](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d96a-131">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d96a-132">例</span><span class="sxs-lookup"><span data-stu-id="0d96a-132">Example</span></span>  

 <span data-ttu-id="0d96a-133">次の例は、`address` 要素の `binding`、`bindingConfiguration`、および `localIssuer` 属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="0d96a-133">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0d96a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d96a-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="0d96a-135">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="0d96a-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0d96a-136">方法: ローカル発行者を設定する</span><span class="sxs-lookup"><span data-stu-id="0d96a-136">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="0d96a-137">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="0d96a-137">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0d96a-138">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="0d96a-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0d96a-139">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="0d96a-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0d96a-140">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0d96a-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0d96a-141">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0d96a-141">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0d96a-142">方法: フェデレーション クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="0d96a-142">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0d96a-143">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="0d96a-143">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
