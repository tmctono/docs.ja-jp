---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 9f3feb11fbe45cbb4b952c70feaa99f9c481dd2b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157370"
---
# \<issuedToken>

<span data-ttu-id="0c07c-101">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c07c-101">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedToken>**  
  
## <a name="syntax"></a><span data-ttu-id="0c07c-102">構文</span><span class="sxs-lookup"><span data-stu-id="0c07c-102">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c07c-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0c07c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0c07c-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c07c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c07c-105">属性</span><span class="sxs-lookup"><span data-stu-id="0c07c-105">Attributes</span></span>  
  
|<span data-ttu-id="0c07c-106">属性</span><span class="sxs-lookup"><span data-stu-id="0c07c-106">Attribute</span></span>|<span data-ttu-id="0c07c-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="0c07c-107">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="0c07c-108">トークンがキャッシュされるかどうかを指定する省略可能なブール属性。</span><span class="sxs-lookup"><span data-stu-id="0c07c-108">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="0c07c-109">既定では、 `true`です。</span><span class="sxs-lookup"><span data-stu-id="0c07c-109">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="0c07c-110">ハンドシェイク操作に使用されるランダム値 (エントロピ) を指定する省略可能な文字列属性。</span><span class="sxs-lookup"><span data-stu-id="0c07c-110">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="0c07c-111">値には、`ClientEntropy`、`ServerEntropy`、および `CombinedEntropy` があります。既定値は `CombinedEntropy` です。</span><span class="sxs-lookup"><span data-stu-id="0c07c-111">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="0c07c-112">この属性は <xref:System.ServiceModel.Security.SecurityKeyEntropyMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="0c07c-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="0c07c-113">トークンが更新されるまでに待機できる有効な期間 (トークン発行者によって提供される) のパーセンテージを指定する省略可能な整数属性。</span><span class="sxs-lookup"><span data-stu-id="0c07c-113">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="0c07c-114">値は 0 ～ 100 の範囲です。</span><span class="sxs-lookup"><span data-stu-id="0c07c-114">Values are from 0 to 100.</span></span> <span data-ttu-id="0c07c-115">既定値は 60 で、更新の実行までに待機できる期間の 60% を示します。</span><span class="sxs-lookup"><span data-stu-id="0c07c-115">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="0c07c-116">発行者との通信時に使用するチャネル動作を指定する省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="0c07c-116">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="0c07c-117">ローカル発行者との通信時に使用するチャネル動作を指定する省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="0c07c-117">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="0c07c-118">トークン発行者 (STS) が期間を指定しない場合に、発行済みトークンがキャッシュされる期間を指定する省略可能な Timespan 属性。</span><span class="sxs-lookup"><span data-stu-id="0c07c-118">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="0c07c-119">既定値は "10675199.02:48: 05.4775807" です。</span><span class="sxs-lookup"><span data-stu-id="0c07c-119">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c07c-120">子要素</span><span class="sxs-lookup"><span data-stu-id="0c07c-120">Child Elements</span></span>  
  
|<span data-ttu-id="0c07c-121">要素</span><span class="sxs-lookup"><span data-stu-id="0c07c-121">Element</span></span>|<span data-ttu-id="0c07c-122">説明</span><span class="sxs-lookup"><span data-stu-id="0c07c-122">Description</span></span>|  
|-------------|-----------------|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="0c07c-123">トークンのローカル発行者のアドレスと、エンドポイントとの通信に使用されるバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c07c-123">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="0c07c-124">ローカル発行者に接続するときに使用するエンドポイント動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c07c-124">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c07c-125">親要素</span><span class="sxs-lookup"><span data-stu-id="0c07c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0c07c-126">要素</span><span class="sxs-lookup"><span data-stu-id="0c07c-126">Element</span></span>|<span data-ttu-id="0c07c-127">説明</span><span class="sxs-lookup"><span data-stu-id="0c07c-127">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="0c07c-128">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c07c-128">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c07c-129">解説</span><span class="sxs-lookup"><span data-stu-id="0c07c-129">Remarks</span></span>  

 <span data-ttu-id="0c07c-130">発行済みトークンは、フェデレーション シナリオでセキュリティ トークン サービス (STS) を使用して認証するときに使用されるカスタム資格情報の種類です。</span><span class="sxs-lookup"><span data-stu-id="0c07c-130">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="0c07c-131">既定ではトークンは、SAML トークンです。</span><span class="sxs-lookup"><span data-stu-id="0c07c-131">By default, the token is a SAML token.</span></span> <span data-ttu-id="0c07c-132">詳細については、「 [フェデレーションと発行済みトークン](../../../wcf/feature-details/federation-and-issued-tokens.md)」、および「 [フェデレーションと発行済みトークン](../../../wcf/feature-details/federation-and-issued-tokens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c07c-132">For more information, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md), and [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="0c07c-133">このセクションには、トークンのローカル発行者やセキュリティ トークン サービスで使用する動作の構成に使用する要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c07c-133">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="0c07c-134">ローカル発行者を使用するようにクライアントを構成する方法については、「 [方法: ローカル発行者を構成](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c07c-134">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c07c-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c07c-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="0c07c-136">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="0c07c-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0c07c-137">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0c07c-137">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0c07c-138">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="0c07c-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0c07c-139">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0c07c-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="0c07c-140">方法: フェデレーション クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="0c07c-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="0c07c-141">方法: ローカル発行者を設定する</span><span class="sxs-lookup"><span data-stu-id="0c07c-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="0c07c-142">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="0c07c-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
