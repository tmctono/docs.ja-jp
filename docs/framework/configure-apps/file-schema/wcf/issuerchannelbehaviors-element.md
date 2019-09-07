---
title: <issuerChannelBehaviors> 要素
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 2c0e0d8d041565edd25c4b2c2802bfd2a589b4f7
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397898"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="5b6ca-102">\<issuerChannelBehaviors > 要素</span><span class="sxs-lookup"><span data-stu-id="5b6ca-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="5b6ca-103">指定されたサービストークンサービスとの通信時に使用される Windows Communication Foundation (WCF) クライアントエンドポイントの動作 (構成で定義されている) のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="5b6ca-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="5b6ca-104">定義された動作には、 [ \<clientCredentials >](clientcredentials.md)要素を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="5b6ca-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

<span data-ttu-id="5b6ca-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ca-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5b6ca-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ca-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5b6ca-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ca-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5b6ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="5b6ca-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ca-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="5b6ca-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ca-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="5b6ca-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ca-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="5b6ca-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerChannelBehaviors >**</span><span class="sxs-lookup"><span data-stu-id="5b6ca-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerChannelBehaviors>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="5b6ca-113">構文</span><span class="sxs-lookup"><span data-stu-id="5b6ca-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5b6ca-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5b6ca-114">Attributes and Elements</span></span>

<span data-ttu-id="5b6ca-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b6ca-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5b6ca-116">属性</span><span class="sxs-lookup"><span data-stu-id="5b6ca-116">Attributes</span></span>

<span data-ttu-id="5b6ca-117">なし。</span><span class="sxs-lookup"><span data-stu-id="5b6ca-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5b6ca-118">子要素</span><span class="sxs-lookup"><span data-stu-id="5b6ca-118">Child Elements</span></span>

|<span data-ttu-id="5b6ca-119">要素</span><span class="sxs-lookup"><span data-stu-id="5b6ca-119">Element</span></span>|<span data-ttu-id="5b6ca-120">説明</span><span class="sxs-lookup"><span data-stu-id="5b6ca-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5b6ca-121">\<add></span><span class="sxs-lookup"><span data-stu-id="5b6ca-121">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="5b6ca-122">コレクションに動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="5b6ca-122">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5b6ca-123">親要素</span><span class="sxs-lookup"><span data-stu-id="5b6ca-123">Parent Elements</span></span>

|<span data-ttu-id="5b6ca-124">要素</span><span class="sxs-lookup"><span data-stu-id="5b6ca-124">Element</span></span>|<span data-ttu-id="5b6ca-125">説明</span><span class="sxs-lookup"><span data-stu-id="5b6ca-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5b6ca-126">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="5b6ca-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="5b6ca-127">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b6ca-127">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5b6ca-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="5b6ca-128">Remarks</span></span>

<span data-ttu-id="5b6ca-129">この要素を使用するのは、なんらかの動作 (`<clientCredentials>` 要素を含む動作以外) を使用してサービスと通信する必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="5b6ca-129">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="5b6ca-130">たとえば、 [ \<dataContractSerializer >](datacontractserializer-element.md) behavior 要素を含める必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="5b6ca-130">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b6ca-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b6ca-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="5b6ca-132">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="5b6ca-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5b6ca-133">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="5b6ca-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5b6ca-134">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="5b6ca-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5b6ca-135">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="5b6ca-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5b6ca-136">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="5b6ca-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="5b6ca-137">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="5b6ca-137">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="5b6ca-138">方法: ローカル発行者を構成する</span><span class="sxs-lookup"><span data-stu-id="5b6ca-138">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="5b6ca-139">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="5b6ca-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
