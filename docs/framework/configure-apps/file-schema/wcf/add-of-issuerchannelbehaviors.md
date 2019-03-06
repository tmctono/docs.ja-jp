---
title: <add> の <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 5c9937cb6302a194228461f3e2e06ecdf4d43269
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377756"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="29cca-102">\<add> of \<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="29cca-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="29cca-103">STS と通信するときに使用されるエンドポイントの動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="29cca-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="29cca-104">エンドポイントの動作が含まれている場合、 [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)要素、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="29cca-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="29cca-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="29cca-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="29cca-106">\<behaviors>\\</span><span class="sxs-lookup"><span data-stu-id="29cca-106">\<behaviors>\\</span></span>
<span data-ttu-id="29cca-107">endpointBehaviors セクション\<動作 > \\</span><span class="sxs-lookup"><span data-stu-id="29cca-107">endpointBehaviors section \<behavior>\\</span></span>
<span data-ttu-id="29cca-108">\<clientCredentials>\\</span><span class="sxs-lookup"><span data-stu-id="29cca-108">\<clientCredentials>\\</span></span>
<span data-ttu-id="29cca-109">\<issuedToken>\\</span><span class="sxs-lookup"><span data-stu-id="29cca-109">\<issuedToken>\\</span></span>
<span data-ttu-id="29cca-110">\<issuerChannelBehaviors > Element\\</span><span class="sxs-lookup"><span data-stu-id="29cca-110">\<issuerChannelBehaviors> Element\\</span></span>
<span data-ttu-id="29cca-111">\<add></span><span class="sxs-lookup"><span data-stu-id="29cca-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="29cca-112">構文</span><span class="sxs-lookup"><span data-stu-id="29cca-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="29cca-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="29cca-113">Attributes and Elements</span></span>

<span data-ttu-id="29cca-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="29cca-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="29cca-115">属性</span><span class="sxs-lookup"><span data-stu-id="29cca-115">Attributes</span></span>

|<span data-ttu-id="29cca-116">属性</span><span class="sxs-lookup"><span data-stu-id="29cca-116">Attribute</span></span>|<span data-ttu-id="29cca-117">説明</span><span class="sxs-lookup"><span data-stu-id="29cca-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="29cca-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="29cca-118">issuerAddress</span></span>|<span data-ttu-id="29cca-119">通信するためのセキュリティ トークン発行者の URI。</span><span class="sxs-lookup"><span data-stu-id="29cca-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="29cca-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="29cca-120">behaviorConfiguration</span></span>|<span data-ttu-id="29cca-121">同じ構成ファイルに定義されたエンドポイントの動作の名前。</span><span class="sxs-lookup"><span data-stu-id="29cca-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="29cca-122">子要素</span><span class="sxs-lookup"><span data-stu-id="29cca-122">Child Elements</span></span>

<span data-ttu-id="29cca-123">なし。</span><span class="sxs-lookup"><span data-stu-id="29cca-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="29cca-124">親要素</span><span class="sxs-lookup"><span data-stu-id="29cca-124">Parent Elements</span></span>

|<span data-ttu-id="29cca-125">要素</span><span class="sxs-lookup"><span data-stu-id="29cca-125">Element</span></span>|<span data-ttu-id="29cca-126">説明</span><span class="sxs-lookup"><span data-stu-id="29cca-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="29cca-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="29cca-127">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="29cca-128">指定されたサービス トークン サービスと通信するときに使用する Windows Communication Foundation (WCF) クライアント エンドポイントの動作のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="29cca-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="29cca-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="29cca-129">Remarks</span></span>

<span data-ttu-id="29cca-130">`issuerAddress` には、クライアントの通信相手となるセキュリティ トークン サービスの URI が含まれます。</span><span class="sxs-lookup"><span data-stu-id="29cca-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="29cca-131">`behaviorConfiguration` アプリケーションがセキュリティ トークン サービスから発行されたトークンを取得する Windows Communication Foundation (WCF) によって作成されたチャネルで使用するエンドポイントの動作を指します。</span><span class="sxs-lookup"><span data-stu-id="29cca-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="29cca-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="29cca-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="29cca-133">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="29cca-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="29cca-134">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="29cca-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="29cca-135">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="29cca-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="29cca-136">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="29cca-136">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="29cca-137">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="29cca-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="29cca-138">方法: フェデレーション クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cca-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="29cca-139">方法: ローカル発行者を構成します。</span><span class="sxs-lookup"><span data-stu-id="29cca-139">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="29cca-140">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="29cca-140">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="29cca-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="29cca-141">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
