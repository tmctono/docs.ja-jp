---
title: <issuerChannelBehaviors> 要素
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
no-loc:
- <system.serviceModel>
- <behaviors>
- <endpointBehaviors>
- <behavior>
- <clientCredentials>
- <issuedToken>
- <issuerChannelBehaviors>
- <dataContractSerializer>
ms.openlocfilehash: cbbfb9d3b5af47a360aa82cf837cd6749f61b641
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70893160"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="45b93-102">\<issuerChannelBehaviors > 要素</span><span class="sxs-lookup"><span data-stu-id="45b93-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="45b93-103">指定されたサービストークンサービスとの通信時に使用される Windows Communication Foundation (WCF) クライアントエンドポイントの動作 (構成で定義されている) のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="45b93-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="45b93-104">定義された動作には、 [ \<clientCredentials >](clientcredentials.md)要素を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="45b93-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

<span data-ttu-id="45b93-105">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="45b93-105">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="45b93-106">&nbsp;&nbsp;[\<System.servicemodel >](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="45b93-106">&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)</span></span>\
<span data-ttu-id="45b93-107">&nbsp;&nbsp;&nbsp;&nbsp;[\<動作 >](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="45b93-107">&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)</span></span>\
<span data-ttu-id="45b93-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors >](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="45b93-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)</span></span>\
<span data-ttu-id="45b93-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<動作 >](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="45b93-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="45b93-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials >](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="45b93-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)</span></span>\
<span data-ttu-id="45b93-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken >](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="45b93-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)</span></span>\
<span data-ttu-id="45b93-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="45b93-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors></span></span>

## <a name="syntax"></a><span data-ttu-id="45b93-113">構文</span><span class="sxs-lookup"><span data-stu-id="45b93-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="45b93-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="45b93-114">Attributes and elements</span></span>

<span data-ttu-id="45b93-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="45b93-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="45b93-116">属性</span><span class="sxs-lookup"><span data-stu-id="45b93-116">Attributes</span></span>

<span data-ttu-id="45b93-117">なし。</span><span class="sxs-lookup"><span data-stu-id="45b93-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45b93-118">子要素</span><span class="sxs-lookup"><span data-stu-id="45b93-118">Child elements</span></span>

|<span data-ttu-id="45b93-119">要素</span><span class="sxs-lookup"><span data-stu-id="45b93-119">Element</span></span>|<span data-ttu-id="45b93-120">説明</span><span class="sxs-lookup"><span data-stu-id="45b93-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45b93-121">\<add></span><span class="sxs-lookup"><span data-stu-id="45b93-121">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="45b93-122">コレクションに動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="45b93-122">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="45b93-123">親要素</span><span class="sxs-lookup"><span data-stu-id="45b93-123">Parent elements</span></span>

|<span data-ttu-id="45b93-124">要素</span><span class="sxs-lookup"><span data-stu-id="45b93-124">Element</span></span>|<span data-ttu-id="45b93-125">説明</span><span class="sxs-lookup"><span data-stu-id="45b93-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45b93-126">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="45b93-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="45b93-127">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="45b93-127">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="45b93-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="45b93-128">Remarks</span></span>

<span data-ttu-id="45b93-129">この要素を使用するのは、なんらかの動作 (`<clientCredentials>` 要素を含む動作以外) を使用してサービスと通信する必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="45b93-129">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="45b93-130">たとえば、 [ \<dataContractSerializer >](datacontractserializer-element.md) behavior 要素を含める必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="45b93-130">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="45b93-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="45b93-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="45b93-132">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="45b93-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="45b93-133">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="45b93-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="45b93-134">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="45b93-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="45b93-135">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="45b93-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="45b93-136">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="45b93-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="45b93-137">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="45b93-137">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="45b93-138">方法: ローカル発行者を構成する</span><span class="sxs-lookup"><span data-stu-id="45b93-138">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="45b93-139">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="45b93-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
