---
title: <add> の <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920110"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="8cbf5-102">\<issuerchannelbehaviors \<の > を追加し ></span><span class="sxs-lookup"><span data-stu-id="8cbf5-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="8cbf5-103">STS と通信するときに使用されるエンドポイントの動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="8cbf5-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="8cbf5-104">いずれかのエンドポイント動作に[ \<clientCredentials >](clientcredentials.md)要素が含まれている場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="8cbf5-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="8cbf5-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8cbf5-105">\<system.ServiceModel></span></span>\
<span data-ttu-id="8cbf5-106">\<動作 > </span><span class="sxs-lookup"><span data-stu-id="8cbf5-106">\<behaviors></span></span>\
<span data-ttu-id="8cbf5-107">endpointbehaviors セクション\<の動作 > </span><span class="sxs-lookup"><span data-stu-id="8cbf5-107">endpointBehaviors section \<behavior></span></span>\
<span data-ttu-id="8cbf5-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8cbf5-108">\<clientCredentials></span></span>\
<span data-ttu-id="8cbf5-109">\<issuedToken > </span><span class="sxs-lookup"><span data-stu-id="8cbf5-109">\<issuedToken></span></span>\
<span data-ttu-id="8cbf5-110">\<issuerChannelBehaviors > 要素 </span><span class="sxs-lookup"><span data-stu-id="8cbf5-110">\<issuerChannelBehaviors> Element</span></span>\
<span data-ttu-id="8cbf5-111">\<add></span><span class="sxs-lookup"><span data-stu-id="8cbf5-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="8cbf5-112">構文</span><span class="sxs-lookup"><span data-stu-id="8cbf5-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8cbf5-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8cbf5-113">Attributes and Elements</span></span>

<span data-ttu-id="8cbf5-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cbf5-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="8cbf5-115">属性</span><span class="sxs-lookup"><span data-stu-id="8cbf5-115">Attributes</span></span>

|<span data-ttu-id="8cbf5-116">属性</span><span class="sxs-lookup"><span data-stu-id="8cbf5-116">Attribute</span></span>|<span data-ttu-id="8cbf5-117">説明</span><span class="sxs-lookup"><span data-stu-id="8cbf5-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="8cbf5-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="8cbf5-118">issuerAddress</span></span>|<span data-ttu-id="8cbf5-119">通信するためのセキュリティ トークン発行者の URI。</span><span class="sxs-lookup"><span data-stu-id="8cbf5-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="8cbf5-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8cbf5-120">behaviorConfiguration</span></span>|<span data-ttu-id="8cbf5-121">同じ構成ファイルに定義されたエンドポイントの動作の名前。</span><span class="sxs-lookup"><span data-stu-id="8cbf5-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="8cbf5-122">子要素</span><span class="sxs-lookup"><span data-stu-id="8cbf5-122">Child Elements</span></span>

<span data-ttu-id="8cbf5-123">なし。</span><span class="sxs-lookup"><span data-stu-id="8cbf5-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8cbf5-124">親要素</span><span class="sxs-lookup"><span data-stu-id="8cbf5-124">Parent Elements</span></span>

|<span data-ttu-id="8cbf5-125">要素</span><span class="sxs-lookup"><span data-stu-id="8cbf5-125">Element</span></span>|<span data-ttu-id="8cbf5-126">説明</span><span class="sxs-lookup"><span data-stu-id="8cbf5-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8cbf5-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="8cbf5-127">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="8cbf5-128">指定されたサービストークンサービスと通信するときに使用される Windows Communication Foundation (WCF) クライアントエンドポイントの動作のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="8cbf5-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8cbf5-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="8cbf5-129">Remarks</span></span>

<span data-ttu-id="8cbf5-130">`issuerAddress` には、クライアントの通信相手となるセキュリティ トークン サービスの URI が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8cbf5-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="8cbf5-131">`behaviorConfiguration`セキュリティトークンサービスから発行済みトークンを取得するために Windows Communication Foundation (WCF) によって作成されたチャネルでアプリケーションが使用するエンドポイント動作を指します。</span><span class="sxs-lookup"><span data-stu-id="8cbf5-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cbf5-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cbf5-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="8cbf5-133">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="8cbf5-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8cbf5-134">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="8cbf5-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8cbf5-135">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="8cbf5-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8cbf5-136">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="8cbf5-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8cbf5-137">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="8cbf5-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="8cbf5-138">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="8cbf5-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="8cbf5-139">方法: ローカル発行者を構成する</span><span class="sxs-lookup"><span data-stu-id="8cbf5-139">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="8cbf5-140">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="8cbf5-140">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8cbf5-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="8cbf5-141">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
