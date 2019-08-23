---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 68e3a0802a10b14148188a81ee24ed901caa147f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925379"
---
# <a name="issuedtoken"></a><span data-ttu-id="10e87-101">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="10e87-101">\<issuedToken></span></span>
<span data-ttu-id="10e87-102">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="10e87-102">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="10e87-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="10e87-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="10e87-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="10e87-104">\<behaviors></span></span>  
<span data-ttu-id="10e87-105">endpointBehaviors セクション</span><span class="sxs-lookup"><span data-stu-id="10e87-105">endpointBehaviors section</span></span>  
<span data-ttu-id="10e87-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="10e87-106">\<behavior></span></span>  
<span data-ttu-id="10e87-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="10e87-107">\<clientCredentials></span></span>  
<span data-ttu-id="10e87-108">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="10e87-108">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e87-109">構文</span><span class="sxs-lookup"><span data-stu-id="10e87-109">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10e87-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="10e87-110">Attributes and Elements</span></span>  
 <span data-ttu-id="10e87-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="10e87-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10e87-112">属性</span><span class="sxs-lookup"><span data-stu-id="10e87-112">Attributes</span></span>  
  
|<span data-ttu-id="10e87-113">属性</span><span class="sxs-lookup"><span data-stu-id="10e87-113">Attribute</span></span>|<span data-ttu-id="10e87-114">説明</span><span class="sxs-lookup"><span data-stu-id="10e87-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="10e87-115">トークンがキャッシュされるかどうかを指定する省略可能なブール属性。</span><span class="sxs-lookup"><span data-stu-id="10e87-115">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="10e87-116">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="10e87-116">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="10e87-117">ハンドシェイク操作に使用されるランダム値 (エントロピ) を指定する省略可能な文字列属性。</span><span class="sxs-lookup"><span data-stu-id="10e87-117">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="10e87-118">値には、`ClientEntropy`、`ServerEntropy`、および `CombinedEntropy` があります。既定値は `CombinedEntropy` です。</span><span class="sxs-lookup"><span data-stu-id="10e87-118">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="10e87-119">この属性は <xref:System.ServiceModel.Security.SecurityKeyEntropyMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="10e87-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="10e87-120">トークンが更新されるまでに待機できる有効な期間 (トークン発行者によって提供される) のパーセンテージを指定する省略可能な整数属性。</span><span class="sxs-lookup"><span data-stu-id="10e87-120">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="10e87-121">値は 0 ～ 100 の範囲です。</span><span class="sxs-lookup"><span data-stu-id="10e87-121">Values are from 0 to 100.</span></span> <span data-ttu-id="10e87-122">既定値は 60 で、更新の実行までに待機できる期間の 60% を示します。</span><span class="sxs-lookup"><span data-stu-id="10e87-122">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="10e87-123">発行者との通信時に使用するチャネル動作を指定する省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="10e87-123">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="10e87-124">ローカル発行者との通信時に使用するチャネル動作を指定する省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="10e87-124">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="10e87-125">トークン発行者 (STS) が期間を指定しない場合に、発行済みトークンがキャッシュされる期間を指定する省略可能な Timespan 属性。</span><span class="sxs-lookup"><span data-stu-id="10e87-125">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="10e87-126">既定値は "10675199.02:48: 05.4775807" です。</span><span class="sxs-lookup"><span data-stu-id="10e87-126">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10e87-127">子要素</span><span class="sxs-lookup"><span data-stu-id="10e87-127">Child Elements</span></span>  
  
|<span data-ttu-id="10e87-128">要素</span><span class="sxs-lookup"><span data-stu-id="10e87-128">Element</span></span>|<span data-ttu-id="10e87-129">説明</span><span class="sxs-lookup"><span data-stu-id="10e87-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10e87-130">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="10e87-130">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="10e87-131">トークンのローカル発行者のアドレスと、エンドポイントとの通信に使用されるバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="10e87-131">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="10e87-132">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="10e87-132">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="10e87-133">ローカル発行者に接続するときに使用するエンドポイント動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="10e87-133">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10e87-134">親要素</span><span class="sxs-lookup"><span data-stu-id="10e87-134">Parent Elements</span></span>  
  
|<span data-ttu-id="10e87-135">要素</span><span class="sxs-lookup"><span data-stu-id="10e87-135">Element</span></span>|<span data-ttu-id="10e87-136">説明</span><span class="sxs-lookup"><span data-stu-id="10e87-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10e87-137">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="10e87-137">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="10e87-138">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="10e87-138">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10e87-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="10e87-139">Remarks</span></span>  
 <span data-ttu-id="10e87-140">発行済みトークンは、フェデレーション シナリオでセキュリティ トークン サービス (STS) を使用して認証するときに使用されるカスタム資格情報の種類です。</span><span class="sxs-lookup"><span data-stu-id="10e87-140">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="10e87-141">既定ではトークンは、SAML トークンです。</span><span class="sxs-lookup"><span data-stu-id="10e87-141">By default, the token is a SAML token.</span></span> <span data-ttu-id="10e87-142">詳細については、「[フェデレーションと発行済みトークン](../../../wcf/feature-details/federation-and-issued-tokens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10e87-142">For more information, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="10e87-143">との[フェデレーションおよび発行](../../../wcf/feature-details/federation-and-issued-tokens.md)されたトークン。</span><span class="sxs-lookup"><span data-stu-id="10e87-143">and [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="10e87-144">このセクションには、トークンのローカル発行者やセキュリティ トークン サービスで使用する動作の構成に使用する要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="10e87-144">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="10e87-145">ローカル発行者を使用するようにクライアントを構成する方法[については、「」を参照してください。ローカル発行者](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)を構成します。</span><span class="sxs-lookup"><span data-stu-id="10e87-145">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e87-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="10e87-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="10e87-147">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="10e87-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="10e87-148">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="10e87-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="10e87-149">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="10e87-149">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="10e87-150">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="10e87-150">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="10e87-151">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="10e87-151">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="10e87-152">方法: ローカル発行者を構成する</span><span class="sxs-lookup"><span data-stu-id="10e87-152">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="10e87-153">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="10e87-153">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
