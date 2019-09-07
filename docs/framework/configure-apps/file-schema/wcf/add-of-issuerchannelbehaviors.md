---
title: <add> の <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398331"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="4b522-102">\<issuerchannelbehaviors \<の > を追加し ></span><span class="sxs-lookup"><span data-stu-id="4b522-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="4b522-103">STS と通信するときに使用されるエンドポイントの動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b522-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="4b522-104">いずれかのエンドポイント動作に[ \<clientCredentials >](clientcredentials.md)要素が含まれている場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4b522-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="4b522-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4b522-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4b522-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4b522-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4b522-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4b522-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4b522-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4b522-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="4b522-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4b522-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="4b522-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="4b522-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="4b522-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="4b522-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="4b522-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerChannelBehaviors >** ](issuerchannelbehaviors-element.md)</span><span class="sxs-lookup"><span data-stu-id="4b522-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)</span></span>\
<span data-ttu-id="4b522-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="4b522-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="4b522-114">構文</span><span class="sxs-lookup"><span data-stu-id="4b522-114">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4b522-115">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4b522-115">Attributes and Elements</span></span>

<span data-ttu-id="4b522-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b522-116">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="4b522-117">属性</span><span class="sxs-lookup"><span data-stu-id="4b522-117">Attributes</span></span>

|<span data-ttu-id="4b522-118">属性</span><span class="sxs-lookup"><span data-stu-id="4b522-118">Attribute</span></span>|<span data-ttu-id="4b522-119">説明</span><span class="sxs-lookup"><span data-stu-id="4b522-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="4b522-120">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="4b522-120">issuerAddress</span></span>|<span data-ttu-id="4b522-121">通信するためのセキュリティ トークン発行者の URI。</span><span class="sxs-lookup"><span data-stu-id="4b522-121">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="4b522-122">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="4b522-122">behaviorConfiguration</span></span>|<span data-ttu-id="4b522-123">同じ構成ファイルに定義されたエンドポイントの動作の名前。</span><span class="sxs-lookup"><span data-stu-id="4b522-123">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4b522-124">子要素</span><span class="sxs-lookup"><span data-stu-id="4b522-124">Child Elements</span></span>

<span data-ttu-id="4b522-125">なし。</span><span class="sxs-lookup"><span data-stu-id="4b522-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4b522-126">親要素</span><span class="sxs-lookup"><span data-stu-id="4b522-126">Parent Elements</span></span>

|<span data-ttu-id="4b522-127">要素</span><span class="sxs-lookup"><span data-stu-id="4b522-127">Element</span></span>|<span data-ttu-id="4b522-128">説明</span><span class="sxs-lookup"><span data-stu-id="4b522-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b522-129">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="4b522-129">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="4b522-130">指定されたサービストークンサービスと通信するときに使用される Windows Communication Foundation (WCF) クライアントエンドポイントの動作のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="4b522-130">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4b522-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b522-131">Remarks</span></span>

<span data-ttu-id="4b522-132">`issuerAddress` には、クライアントの通信相手となるセキュリティ トークン サービスの URI が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b522-132">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="4b522-133">`behaviorConfiguration`セキュリティトークンサービスから発行済みトークンを取得するために Windows Communication Foundation (WCF) によって作成されたチャネルでアプリケーションが使用するエンドポイント動作を指します。</span><span class="sxs-lookup"><span data-stu-id="4b522-133">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b522-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b522-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="4b522-135">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="4b522-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="4b522-136">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="4b522-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="4b522-137">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="4b522-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="4b522-138">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="4b522-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4b522-139">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="4b522-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="4b522-140">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="4b522-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="4b522-141">方法: ローカル発行者を構成する</span><span class="sxs-lookup"><span data-stu-id="4b522-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="4b522-142">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="4b522-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="4b522-143">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="4b522-143">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
