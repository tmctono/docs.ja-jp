---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 83061b283c9430af7bcda9cbc832811fa805ed4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756287"
---
# <a name="issuedtoken"></a><span data-ttu-id="e5cb0-101">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="e5cb0-101">\<issuedToken></span></span>
<span data-ttu-id="e5cb0-102">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-102">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="e5cb0-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e5cb0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5cb0-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="e5cb0-104">\<behaviors></span></span>  
<span data-ttu-id="e5cb0-105">endpointBehaviors セクション</span><span class="sxs-lookup"><span data-stu-id="e5cb0-105">endpointBehaviors section</span></span>  
<span data-ttu-id="e5cb0-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e5cb0-106">\<behavior></span></span>  
<span data-ttu-id="e5cb0-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e5cb0-107">\<clientCredentials></span></span>  
<span data-ttu-id="e5cb0-108">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="e5cb0-108">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5cb0-109">構文</span><span class="sxs-lookup"><span data-stu-id="e5cb0-109">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5cb0-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e5cb0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e5cb0-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5cb0-112">属性</span><span class="sxs-lookup"><span data-stu-id="e5cb0-112">Attributes</span></span>  
  
|<span data-ttu-id="e5cb0-113">属性</span><span class="sxs-lookup"><span data-stu-id="e5cb0-113">Attribute</span></span>|<span data-ttu-id="e5cb0-114">説明</span><span class="sxs-lookup"><span data-stu-id="e5cb0-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="e5cb0-115">トークンがキャッシュされるかどうかを指定する省略可能なブール属性。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-115">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="e5cb0-116">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-116">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="e5cb0-117">ハンドシェイク操作に使用されるランダム値 (エントロピ) を指定する省略可能な文字列属性。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-117">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="e5cb0-118">値には、`ClientEntropy`、`ServerEntropy`、および `CombinedEntropy` があります。既定値は `CombinedEntropy` です。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-118">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="e5cb0-119">この属性は <xref:System.ServiceModel.Security.SecurityKeyEntropyMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="e5cb0-120">トークンが更新されるまでに待機できる有効な期間 (トークン発行者によって提供される) のパーセンテージを指定する省略可能な整数属性。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-120">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="e5cb0-121">値は 0 ～ 100 の範囲です。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-121">Values are from 0 to 100.</span></span> <span data-ttu-id="e5cb0-122">既定値は 60 で、更新の実行までに待機できる期間の 60% を示します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-122">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="e5cb0-123">発行者との通信時に使用するチャネル動作を指定する省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-123">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="e5cb0-124">ローカル発行者との通信時に使用するチャネル動作を指定する省略可能な属性。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-124">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="e5cb0-125">トークン発行者 (STS) が期間を指定しない場合に、発行済みトークンがキャッシュされる期間を指定する省略可能な Timespan 属性。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-125">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="e5cb0-126">既定値は「10675199.02:48:05.4775807」</span><span class="sxs-lookup"><span data-stu-id="e5cb0-126">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5cb0-127">子要素</span><span class="sxs-lookup"><span data-stu-id="e5cb0-127">Child Elements</span></span>  
  
|<span data-ttu-id="e5cb0-128">要素</span><span class="sxs-lookup"><span data-stu-id="e5cb0-128">Element</span></span>|<span data-ttu-id="e5cb0-129">説明</span><span class="sxs-lookup"><span data-stu-id="e5cb0-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5cb0-130">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="e5cb0-130">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="e5cb0-131">トークンのローカル発行者のアドレスと、エンドポイントとの通信に使用されるバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-131">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="e5cb0-132">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="e5cb0-132">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="e5cb0-133">ローカル発行者に接続するときに使用するエンドポイント動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-133">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5cb0-134">親要素</span><span class="sxs-lookup"><span data-stu-id="e5cb0-134">Parent Elements</span></span>  
  
|<span data-ttu-id="e5cb0-135">要素</span><span class="sxs-lookup"><span data-stu-id="e5cb0-135">Element</span></span>|<span data-ttu-id="e5cb0-136">説明</span><span class="sxs-lookup"><span data-stu-id="e5cb0-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5cb0-137">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e5cb0-137">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="e5cb0-138">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-138">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5cb0-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5cb0-139">Remarks</span></span>  
 <span data-ttu-id="e5cb0-140">発行済みトークンは、フェデレーション シナリオでセキュリティ トークン サービス (STS) を使用して認証するときに使用されるカスタム資格情報の種類です。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-140">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="e5cb0-141">既定ではトークンは、SAML トークンです。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-141">By default, the token is a SAML token.</span></span> <span data-ttu-id="e5cb0-142">詳細については、次を参照してください。[フェデレーションと発行されたトークン](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-142">For more information, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="e5cb0-143">[フェデレーションと発行済みトークン](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-143">and [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="e5cb0-144">このセクションには、トークンのローカル発行者やセキュリティ トークン サービスで使用する動作の構成に使用する要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-144">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="e5cb0-145">ローカル発行者を使用するクライアントの構成については、次を参照してください。[方法。ローカル発行者を構成する](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-145">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5cb0-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5cb0-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="e5cb0-147">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="e5cb0-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="e5cb0-148">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e5cb0-148">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e5cb0-149">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="e5cb0-149">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e5cb0-150">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e5cb0-150">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="e5cb0-151">方法: フェデレーション クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-151">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="e5cb0-152">方法: ローカル発行者を構成します。</span><span class="sxs-lookup"><span data-stu-id="e5cb0-152">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="e5cb0-153">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="e5cb0-153">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
