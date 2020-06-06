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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70893160"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="f0f0f-102">\<issuerChannelBehaviors> 要素</span><span class="sxs-lookup"><span data-stu-id="f0f0f-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="f0f0f-103">指定されたサービストークンサービスとの通信時に使用される Windows Communication Foundation (WCF) クライアントエンドポイントの動作 (構成で定義されている) のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="f0f0f-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="f0f0f-104">定義された動作に要素を含めることはできません [\<clientCredentials>](clientcredentials.md) 。</span><span class="sxs-lookup"><span data-stu-id="f0f0f-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors>

## <a name="syntax"></a><span data-ttu-id="f0f0f-105">構文</span><span class="sxs-lookup"><span data-stu-id="f0f0f-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f0f0f-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f0f0f-106">Attributes and elements</span></span>

<span data-ttu-id="f0f0f-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0f0f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f0f0f-108">属性</span><span class="sxs-lookup"><span data-stu-id="f0f0f-108">Attributes</span></span>

<span data-ttu-id="f0f0f-109">なし。</span><span class="sxs-lookup"><span data-stu-id="f0f0f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f0f0f-110">子要素</span><span class="sxs-lookup"><span data-stu-id="f0f0f-110">Child elements</span></span>

|<span data-ttu-id="f0f0f-111">要素</span><span class="sxs-lookup"><span data-stu-id="f0f0f-111">Element</span></span>|<span data-ttu-id="f0f0f-112">説明</span><span class="sxs-lookup"><span data-stu-id="f0f0f-112">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="f0f0f-113">コレクションに動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="f0f0f-113">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f0f0f-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f0f0f-114">Parent elements</span></span>

|<span data-ttu-id="f0f0f-115">要素</span><span class="sxs-lookup"><span data-stu-id="f0f0f-115">Element</span></span>|<span data-ttu-id="f0f0f-116">説明</span><span class="sxs-lookup"><span data-stu-id="f0f0f-116">Description</span></span>|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="f0f0f-117">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0f0f-117">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f0f0f-118">解説</span><span class="sxs-lookup"><span data-stu-id="f0f0f-118">Remarks</span></span>

<span data-ttu-id="f0f0f-119">この要素を使用するのは、なんらかの動作 (`<clientCredentials>` 要素を含む動作以外) を使用してサービスと通信する必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="f0f0f-119">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="f0f0f-120">たとえば、 [\<dataContractSerializer>](datacontractserializer-element.md) behavior 要素を含める必要がある場合などです。</span><span class="sxs-lookup"><span data-stu-id="f0f0f-120">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0f0f-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0f0f-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="f0f0f-122">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="f0f0f-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f0f0f-123">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="f0f0f-123">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f0f0f-124">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="f0f0f-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f0f0f-125">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="f0f0f-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f0f0f-126">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="f0f0f-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="f0f0f-127">方法: フェデレーション クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="f0f0f-127">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="f0f0f-128">方法: ローカル発行者を設定する</span><span class="sxs-lookup"><span data-stu-id="f0f0f-128">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="f0f0f-129">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="f0f0f-129">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
